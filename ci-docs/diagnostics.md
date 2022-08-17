---
title: Диагностикалық журналдарды экспорттау (алдын ала қарау)
description: Журналдарды жіберу жолын үйреніңіз Microsoft Azure Монитор.
ms.date: 08/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: article
author: brndkfr
ms.author: bkief
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 60b039173fd938482c782c7394420d4951c222a7
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: MT
ms.contentlocale: kk-KZ
ms.lasthandoff: 08/10/2022
ms.locfileid: "9245932"
---
# <a name="export-diagnostic-logs-preview"></a>Диагностикалық журналдарды экспорттау (алдын ала қарау)

Azure Monitor арқылы Customer Insights жүйесінен журналдарды қайта жіберіңіз. Azure Monitor ресурс журналдары журналдарды бақылауға және жіберуге мүмкіндік береді [Azure сақтау орны](https://azure.microsoft.com/services/storage/),[Azure Log Analytics](/azure/azure-monitor/logs/log-analytics-overview), немесе оларды ағынмен жіберіңіз [Azure оқиға хабтары](https://azure.microsoft.com/services/event-hubs/).

Customer Insights келесі оқиғалар журналдарын жібереді:

- **Аудит оқиғалары**
  - **APIEvent** - арқылы өзгерістерді қадағалауға мүмкіндік береді Dynamics 365 Customer Insights UI.
- **Операциялық оқиғалар**
  - **Жұмыс процесі оқиғасы** - орнатуға мүмкіндік береді [деректер көздері](data-sources.md),[біріктіру](data-unification.md),[байыту](enrichment-hub.md), және [экспорт](export-destinations.md) деректерді басқа жүйелерге енгізу. Бұл қадамдарды жеке орындауға болады (мысалы, бір экспортты іске қосу). Олар сондай-ақ ұйымдастырылған іске қоса алады (мысалы, байытуларды тартатын және деректерді басқа жүйеге экспорттайтын біріктіру процесін іске қосатын деректер көздерінен деректерді жаңарту). Қосымша ақпаратты мына жерден қараңыз [Жұмыс ағынының оқиғасының схемасы](#workflow-event-schema).
  - **APIEvent** - тұтынушылар данасының барлық API қоңырауларын жібереді Dynamics 365 Customer Insights. Қосымша ақпаратты мына жерден қараңыз [APIEvent схемасы](#api-event-schema).

## <a name="set-up-the-diagnostic-settings"></a>Диагностикалық параметрлерді орнатыңыз

### <a name="prerequisites"></a>Алғышарттар

- Белсенді [Azure жазылымы](https://azure.microsoft.com/pricing/purchase-options/pay-as-you-go/).
- [Әкімші](permissions.md#admin) Customer Insights ішіндегі рұқсаттар.
- [Қатысушы және пайдаланушыға қол жеткізу әкімшісі рөлі](/azure/role-based-access-control/role-assignments-portal) Azure жүйесіндегі тағайындалған ресурста. Ресурс болуы мүмкін Azure Data Lake Storage тіркелгісі, Azure Event Hub немесе Azure Log Analytics жұмыс кеңістігі. Бұл рұқсат Customer Insights жүйесінде диагностикалық параметрлерді конфигурациялау кезінде қажет, бірақ оны сәтті орнатудан кейін өзгертуге болады.
- [Тағайындалған жерге қойылатын талаптар](/azure/azure-monitor/platform/diagnostic-settings#destination-requirements) Azure Storage, Azure Event Hub немесе Azure Log Analytics үшін орындалады.
- Кем дегенде **Оқырман** ресурс тиесілі ресурс тобының рөлі.

### <a name="set-up-diagnostics-with-azure-monitor"></a>Azure мониторымен диагностиканы орнатыңыз

1. Customer Insights бөліміне өтіңіз **Админ** > **Жүйе** және таңдаңыз **Диагностика** қойындысы.

1. таңдаңыз **Баратын жерді қосыңыз**.

   :::image type="content" source="media/diagnostics-pane.png" alt-text="Диагностикалық байланыс.":::

1. ішінде атауды көрсетіңіз **Диагностика тағайындау орнының атауы** өріс.

1. таңдаңыз **Ресурс түрі** (Сақтау тіркелгісі, Event Hub немесе Log Analytics).

1. таңдаңыз **Жазылым**, **тобы**, және **Ресурс** тағайындалған ресурс үшін. Қараңыз [Тағайындалған ресурстағы конфигурация](#configuration-on-the-destination-resource) рұқсат және журнал ақпараты үшін.

1. шолу [деректердің құпиялылығы және сәйкестігі](connections.md#data-privacy-and-compliance) және таңдаңыз **Мен келісемін**.

1. таңдаңыз **Жүйеге қосылу** тағайындалған ресурсқа қосылу үшін. Егер API қолданыста болса және оқиғаларды жасаса, журналдар тағайындалған жерде 15 минуттан кейін пайда бола бастайды.

## <a name="configuration-on-the-destination-resource"></a>Тағайындалған ресурстағы конфигурация

Ресурс түрін таңдауыңызға байланысты келесі өзгерістер автоматты түрде орын алады:

### <a name="storage-account"></a>Сақтау орны тіркелгісі

Customer Insights қызметінің директоры алады **Сақтау есептік жазбасының салымшысы** таңдалған ресурсқа рұқсат береді және таңдалған аттар кеңістігі астында екі контейнер жасайды:

- `insight-logs-audit` қамтитын **аудиторлық оқиғалар**
- `insight-logs-operational` қамтитын **операциялық оқиғалар**

### <a name="event-hub"></a>Оқиға хабы

Customer Insights қызметінің директоры алады **Azure Event Hubs деректер иесі** ресурста рұқсат алады және таңдалған аттар кеңістігінде екі оқиға хабын жасайды:

- `insight-logs-audit` қамтитын **аудиторлық оқиғалар**
- `insight-logs-operational` қамтитын **операциялық оқиғалар**

### <a name="log-analytics"></a>Log Analytics

Customer Insights қызметінің директоры алады **Log Analytics Contributor** ресурсқа рұқсат. Журналдар астында қол жетімді **Журналдар** > **Кестелер** > **Журналды басқару** таңдалған Log Analytics жұмыс кеңістігінде. кеңейтіңіз **Журналды басқару** шешімін тауып, орнын табыңыз`CIEventsAudit` және`CIEventsOperational` кестелер.

- `CIEventsAudit` қамтитын **аудиторлық оқиғалар**
- `CIEventsOperational` қамтитын **операциялық оқиғалар**

Астында **Сұраулар** терезені кеңейтіңіз **Аудит** шешімін тауып, іздеу арқылы берілген мысал сұрауларын табыңыз `CIEvents`.

## <a name="remove-a-diagnostics-destination"></a>Диагностикалық мақсатты жою

1. Бару **Админ** > **Жүйе** және таңдаңыз **Диагностика** қойындысы.

1. Тізімнен диагностикалық мақсатты таңдаңыз.

   > [!TIP]
   > Тағайындалған орынды жою журналды қайта жіберуді тоқтатады, бірақ Azure жазылымындағы ресурсты жоймайды. Azure жүйесіндегі ресурсты жою үшін, ішіндегі сілтемені таңдаңыз **Әрекеттер** таңдалған ресурс үшін Azure порталын ашу және оны сол жерде жою үшін баған. Содан кейін диагностика тағайындау орнын жойыңыз.

1. Ішінде **Әрекеттер** бағанынан таңдаңыз **Жою** белгішесі.

1. Тағайындалған орынды жою және журналды қайта жіберуді тоқтату үшін жоюды растаңыз.

## <a name="log-categories-and-event-schemas"></a>Журнал санаттары және оқиға схемалары

Қазіргі уақытта [API оқиғалары](apis.md) және жұмыс процесі оқиғаларына қолдау көрсетіледі және келесі санаттар мен схемалар қолданылады.
Журнал схемасы келесіге сәйкес келеді [Azure Monitor жалпы схемасы](/azure/azure-monitor/platform/resource-logs-schema#top-level-common-schema).

### <a name="categories"></a>Санаттар

Customer Insights екі санатты ұсынады:

- **Аудит оқиғалары** :[API оқиғалары](#api-event-schema) қызметтегі конфигурация өзгерістерін бақылау үшін. `POST|PUT|DELETE|PATCH` операциялар осы санатқа жатады.
- **Операциялық оқиғалар** :[API оқиғалары](#api-event-schema) немесе [жұмыс процесінің оқиғалары](#workflow-event-schema) қызметті пайдалану кезінде жасалады.  Мысалға,`GET` сұраулар немесе жұмыс процесінің орындалу оқиғалары.

## <a name="event-schemas"></a>Оқиға схемалары

API оқиғалары мен жұмыс процесі оқиғаларының жалпы құрылымы бар, бірақ аздаған айырмашылықтары бар. Қосымша ақпаратты қараңыз [API оқиға схемасы](#api-event-schema) немесе [жұмыс процесі оқиғасының схемасы](#workflow-event-schema).

### <a name="api-event-schema"></a>API оқиға схемасы

| Өріс             | Деректер түрі  | Міндетті/міндетті емес | Сипаттама       | Мысал        |
| ----------------- | --------- | ----------------- | --------------------- | ------------------------ |
| `time`            | Timestamp | Талап етіледі          | Оқиғаның уақыт белгісі (UTC)       | `2020-09-08T09:48:14.8050869Z`         |
| `resourceId`      | String    | Талап етіледі          | Оқиғаны шығарған дананың ResourceId         | `/SUBSCRIPTIONS/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX/RESOURCEGROUPS/<RESOURCEGROUPNAME>/`<br>`PROVIDERS/MICROSOFT.D365CUSTOMERINSIGHTS/`<br>`INSTANCES/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX`  |
| `operationName`   | String    | Талап етіледі          | Осы оқиға арқылы көрсетілген операцияның атауы.                                                                                                                | `Workflows.GetWorkFlowStatusAsync`                                                                                                                                       |
| `category`        | String    | Талап етіледі          | Оқиғаның журнал санаты. Немесе`Operational` немесе `Audit`. Барлық POST/PUT/PATCH/DELETE HTTP сұрауларымен тегтелген`Audit`, қалғанының бәрі бірге`Operational` | `2020-09-08T09:48:14.8050869Z`                                                                                                                                           |
| `resultType`      | String    | Талап етіледі          | Оқиға жағдайы. `Success`,`ClientError`,`Failure`                                                                                                        |                                                                                                                                                                          |
| `resultSignature` | String    | Таңдаулы          | Оқиғаның нәтижесі күйі. Егер операция REST API қоңырауына сәйкес келсе, бұл HTTP күй коды.        | `200`             |
| `durationMs`      | Ұзын      | Таңдаулы          | Операцияның ұзақтығы миллисекундпен.     | `133`     |
| `callerIpAddress` | String    | Таңдаулы          | Қоңырау шалушының IP мекенжайы, егер операция жалпыға қолжетімді IP мекенжайынан келетін API қоңырауына сәйкес келсе.                                                 | `144.318.99.233`         |
| `identity`        | String    | Таңдаулы          | Пайдаланушының немесе операцияны орындаған қолданбаның идентификациясын сипаттайтын JSON нысаны.       | Қараңыз [Жеке басын куәландыратын](#identity-schema) бөлім.     |  
| `properties`      | String    | Таңдаулы          | Оқиғалардың белгілі бір санатына көбірек сипаттары бар JSON нысаны.      | Қараңыз [Қасиеттер](#api-properties-schema) бөлім.    |
| `level`           | String    | Талап етіледі          | Оқиғаның ауырлық деңгейі.    | `Informational`,`Warning`,`Error`, немесе `Critical`.           |
| `uri`             | String    | Таңдаулы          | Абсолютті сұрау URI.    |               |

#### <a name="identity-schema"></a>Сәйкестендіру схемасы

The`identity` JSON нысанында келесі құрылым бар

```json
{
  "Authorization" : {
    "UserRole": "Admin",
    "RequiredRoles": [
      "Contributor",
      "Viewer"
      ]
    },
  "Claims" {
    "claimNameX" : "claimValueX",
    "claimNameY" : "claimValueY"
   }
}  
```

| Өріс                         | Сипаттама                                                                                                                          |
| ----------------------------- | ------------------------------------------------------------------------------------------------------------------------------------ |
| `Authorization.UserRole`      | Пайдаланушы немесе қолданба үшін тағайындалған рөл. Қосымша ақпаратты қараңыз [пайдаланушы рұқсаттары](permissions.md).                                     |
| `Authorization.RequiredRoles` | Операцияны орындау үшін қажетті рөлдер. `Admin` рөл барлық операцияларды жасауға рұқсат етіледі.                                                    |
| `Claims`                      | Пайдаланушының немесе қолданбаның JSON веб-токенінің (JWT) шағымдары. Шағым сипаттары ұйым мен ұйымға байланысты өзгереді Azure Active Directory конфигурация. |

#### <a name="api-properties-schema"></a>API сипаттарының схемасы

[API оқиғалары](apis.md) келесі қасиеттерге ие.

| Өріс                        | Сипаттама                                                                                                            |
| ---------------------------- | ---------------------------------------------------------------------------------------------------------------------- |
| `properties.eventType`       | Әрқашан`ApiEvent`, журнал оқиғасын API оқиғасы ретінде белгілеу.                                                                 |
| `properties.userAgent`       | Браузер агенті сұрауды жібереді немесе `unknown`.                                                                        |
| `properties.method`          | HTTP әдісі:`GET/POST/PUT/PATCH/HEAD`.                                                                                |
| `properties.path`            | Сұраныстың салыстырмалы жолы.                                                                                          |
| `properties.origin`          | Қайдан келетінін көрсететін URI немесе `unknown`.                                                                  |
| `properties.operationStatus` | `Success` HTTP күй коды < 400 үшін <br> `ClientError` HTTP күй коды < 500 үшін <br> `Error` HTTP күйі үшін >= 500 |
| `properties.tenantId`        | Ұйым идентификаторы                                                                                                        |
| `properties.tenantName`      | Ұйымның атауы.                                                                                              |
| `properties.callerObjectId`  | Azure Active Directory Қоңырау шалушының ObjectId.                                                                         |
| `properties.instanceId`      | Тұтынушы түсініктері`instanceId`                                                                                         |

### <a name="workflow-event-schema"></a>Жұмыс процесі оқиғасының схемасы

Жұмыс процесі бірнеше қадамдарды қамтиды. [Деректер көздерін қабылдау](data-sources.md),[біріктіру](data-unification.md),[байыту](enrichment-hub.md), және [экспорт](export-destinations.md) деректер. Барлық осы қадамдар жеке немесе келесі процестермен ұйымдастырылуы мүмкін.

#### <a name="operation-types"></a>Операция түрлері

| OperationType     | Топ                                     |
| ----------------- | ----------------------------------------- |
| Жұту         | [Деректер көздері](data-sources.md)           |
| Деректерді дайындау   | [Деректер көздері](data-sources.md)           |
| Картаға түсіру               | [Деректерді бірыңғайландыру](data-unification.md)   |
| Сәйкестендіру             | [Деректерді бірыңғайландыру](data-unification.md)   |
| Біріктіру             | [Деректерді бірыңғайландыру](data-unification.md)   |
| ProfileStore      | [Тұтынушы профильдері](customer-profiles.md) |
| Іздеу            | [Тұтынушы профильдері](customer-profiles.md) |
| Қызмет          | [Әрекеттер](activities.md)                  |
| AttributeMeasures | [Сегменттер мен өлшемдер](segments.md)      |
| EntityMeasures    | [Сегменттер мен өлшемдер](segments.md)      |
| Өлшемдер          | [Сегменттер мен өлшемдер](segments.md)      |
| Сегменттеу      | [Сегменттер мен өлшемдер](segments.md)      |
| Арттыру        | [Арттыру](enrichment-hub.md)                                          |
| Интеллект      | [Болжамдар](predictions-overview.md)                                          |
| AiBuilder         | [Болжамдар](predictions-overview.md)                                          |
| Пайдалы мәліметтер          | [Болжамдар](predictions-overview.md)                                          |
| Export            | [Экспорттаулар](export-destinations.md)                                          |
| Модельді басқару   | [Болжамдар](custom-models.md)                                           |
| Қарым-қатынас      | [Деректерді бірыңғайландыру](relationships.md)                                           |

#### <a name="field-description"></a>Өріс сипаттамасы

| Өріс           | Деректер түрі  | Міндетті/міндетті емес | Сипаттама                                                                                                                                                   | Мысал                                                                                                                                                                  |
| --------------- | --------- | ----------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `time`          | Timestamp | Талап етіледі          | Оқиғаның уақыт белгісі (UTC).                                                                                                                                 | `2020-09-08T09:48:14.8050869Z`                                                                                                                                           |
| `resourceId`    | String    | Талап етіледі          | Оқиғаны шығарған дананың ResourceId.                                                                                                            | `/SUBSCRIPTIONS/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX/RESOURCEGROUPS/<RESOURCEGROUPNAME>/`<br>`PROVIDERS/MICROSOFT.D365CUSTOMERINSIGHTS/`<br>`INSTANCES/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX` |
| `operationName` | String    | Талап етіледі          | Осы оқиға арқылы көрсетілген операцияның атауы. `{OperationType}.[WorkFlow|Task][Started|Completed]`. Қараңыз [Операция түрлері](#operation-types) анықтама үшін. | `Segmentation.WorkflowStarted`,<br> `Segmentation.TaskStarted`, <br> `Segmentation.TaskCompleted`, <br> `Segmentation.WorkflowCompleted`                                 |
| `category`      | String    | Талап етіледі          | Оқиғаның журнал санаты. Әрқашан`Operational` Жұмыс процесі оқиғалары үшін                                                                                           | `Operational`                                                                                                                                                            |
| `resultType`    | String    | Талап етіледі          | Оқиға жағдайы. `Running`,`Skipped`,`Successful`,`Failure`                                                                                            |                                                                                                                                                                          |
| `durationMs`    | Ұзын      | Таңдаулы          | Операцияның ұзақтығы миллисекундпен.                                                                                                                    | `133`                                                                                                                                                                    |
| `properties`    | String    | Таңдаулы          | Оқиғалардың белгілі бір санатына көбірек сипаттары бар JSON нысаны.                                                                                        | Ішкі бөлімді қараңыз [Жұмыс үрдісінің сипаттары](#workflow-properties-schema)                                                                                                       |
| `level`         | String    | Талап етіледі          | Оқиғаның ауырлық деңгейі.                                                                                                                                  | `Informational`, `Warning` немесе `Error`                                                                                                                                   |

#### <a name="workflow-properties-schema"></a>Жұмыс үрдісінің сипаттары схемасы

Жұмыс процесі оқиғаларының келесі қасиеттері бар.

| Өріс              | Workflow | Тапсырма | Сипаттама            |
| ------------------------------- | -------- | ---- | ----------- |
| `properties.eventType`                       | Иә      | Иә  | Әрқашан`WorkflowEvent`, оқиғаны жұмыс процесі оқиғасы ретінде белгілеу.                                                                                                                                                                                                |
| `properties.workflowJobId`                   | Иә      | Иә  | Жұмыс үрдісінің идентификаторы. Жұмыс процесін орындаудағы барлық жұмыс процесі мен тапсырма оқиғалары бірдей болады `workflowJobId`.                                                                                                                                   |
| `properties.operationType`                   | Иә      | Иә  | Операцияның идентификаторы, қараңыз [Операция түрлері](#operation-types).                                                                                                                                                                               |
| `properties.tasksCount`                      | Иә      | No   | Тек жұмыс процесі. Жұмыс процесі іске қосатын тапсырмалар саны.                                                                                                                                                                                                       |
| `properties.submittedBy`                     | Иә      | No   | Қосымша. Тек жұмыс процесі оқиғалары. The Azure Active Directory [пайдаланушының объектінің идентификаторы](/azure/marketplace/find-tenant-object-id#find-user-object-id) жұмыс процесін кім іске қосты, сондай-ақ қараңыз `properties.workflowSubmissionKind`.                                   |
| `properties.workflowType`                    | Иә      | No   | `full` немесе`incremental` жаңарту.                                                                                                                                                                                                                            |
| `properties.workflowSubmissionKind`          | Иә      | No   | `OnDemand` немесе `Scheduled`.                                                                                                                                                                                                                                  |
| `properties.workflowStatus`                  | Иә      | No   | `Running` немесе `Successful`.                                                                                                                                                                                                                                 |
| `properties.startTimestamp`                  | Иә      | Иә  | UTC уақыт белгісі`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.endTimestamp`                    | Иә      | Иә  | UTC уақыт белгісі`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.submittedTimestamp`              | Иә      | Иә  | UTC уақыт белгісі`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.instanceId`                      | Иә      | Иә  | Тұтынушы түсініктері`instanceId`                                                                                                                                                                                                                              |  
| `properties.identifier`                      | No       | Иә  | - OperationType = үшін`Export`, идентификатор экспорт конфигурациясының нұсқауы болып табылады. <br> - OperationType = үшін`Enrichment`, бұл байытудың нұсқаушысы <br> - OperationType үшін`Measures` және`Segmentation`, идентификатор нысан атауы болып табылады. |
| `properties.friendlyName`                    | No       | Иә  | Экспорттың немесе өңделетін нысанның пайдаланушыға ыңғайлы атауы.                                                                                                                                                                                           |
| `properties.error`                           | No       | Иә  | Қосымша. Қосымша мәліметтері бар қате хабары.                                                                                                                                                                                                                  |
| `properties.additionalInfo.Kind`             | No       | Иә  | Қосымша. OperationType үшін`Export` тек. Экспорт түрін анықтайды. Қосымша ақпарат алу үшін қараңыз [экспорттық бағыттарға шолу](export-destinations.md).                                                                                          |
| `properties.additionalInfo.AffectedEntities` | No       | Иә  | Қосымша. OperationType үшін`Export` тек. Экспортта конфигурацияланған нысандардың тізімін қамтиды.                                                                                                                                                            |
| `properties.additionalInfo.MessageCode`      | No       | Иә  | Қосымша. OperationType үшін`Export` тек. Экспортқа арналған толық хабарлама.                                                                                                                                                                                 |
| `properties.additionalInfo.entityCount`      | No       | Иә  | Қосымша. OperationType үшін`Segmentation` тек. Сегменттегі мүшелердің жалпы санын көрсетеді.                                                                                                                                                    |

[!INCLUDE [footer-include](includes/footer-banner.md)]
