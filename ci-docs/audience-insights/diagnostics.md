---
title: Аудит Dynamics 365 Customer Insights Azure мониторымен
description: Журналдарды жіберу жолын үйреніңіз Microsoft Azure Монитор.
ms.date: 12/14/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: article
author: brndkfr
ms.author: bkief
manager: shellyha
ms.openlocfilehash: d962c359d70a068fcf939b61e340f86de088b419
ms.sourcegitcommit: 0c3c473e0220de9ee3c1f1ee1825de0b3b3663c3
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 12/14/2021
ms.locfileid: "7920870"
---
# <a name="log-forwarding-in-dynamics-365-customer-insights-with-azure-monitor-preview"></a>Жүйеге қайта бағыттау Dynamics 365 Customer Insights Azure мониторымен (алдын ала қарау)

Dynamics 365 Customer Insights Azure мониторымен тікелей интеграцияны қамтамасыз етеді. Azure Monitor ресурс журналдары журналдарды бақылауға және жіберуге мүмкіндік береді [Azure сақтау орны](https://azure.microsoft.com/services/storage/),[Azure Log Analytics](/azure/azure-monitor/logs/log-analytics-overview), немесе оларды ағынмен жіберіңіз [Azure оқиға хабтары](https://azure.microsoft.com/services/event-hubs/).

Customer Insights келесі оқиғалар журналдарын жібереді:

- **Аудит оқиғалары**
  - **APIEvent** - арқылы орындалатын өзгерістерді бақылауға мүмкіндік береді Dynamics 365 Customer Insights UI.
- **Операциялық оқиғалар**
  - **Жұмыс процесі оқиғасы** - Жұмыс процесі орнатуға мүмкіндік береді [Деректер көздері](data-sources.md),[біріктіру](data-unification.md) және [байыту](enrichment-hub.md) және соңында [экспорттау](export-destinations.md) деректерді басқа жүйелерге енгізу. Барлық осы қадамдарды жеке орындауға (мысалы, бір экспортты іске қосу) немесе реттелген (мысалы, қосымша байытуларды тартатын және бір рет деректерді басқа жүйеге экспорттауға мүмкіндік беретін біріктіру процесін іске қосатын деректер көздерінен деректерді жаңарту) болуы мүмкін. Қосымша мәліметтерді қараңыз [Жұмыс ағынының оқиғасының схемасы](#workflow-event-schema).
  - **APIEvent** - тұтынушылар данасына барлық API қоңыраулары Dynamics 365 Customer Insights. Қосымша мәліметтерді қараңыз [APIEvent схемасы](#api-event-schema).

## <a name="set-up-the-diagnostic-settings"></a>Диагностикалық параметрлерді орнатыңыз

### <a name="prerequisites"></a>Алғышарттар

Customer Insights жүйесінде диагностиканы конфигурациялау үшін келесі алғышарттар орындалуы керек:

- Сізде белсенді [Azure жазылымы](https://azure.microsoft.com/pricing/purchase-options/pay-as-you-go/).
- Сенде бар [Әкімші](permissions.md#administrator) Customer Insights ішіндегі рұқсаттар.
- Сізде бар **Қатысушы** және **Пайдаланушыға кіру әкімшісі** Azure жүйесіндегі тағайындалған ресурстағы рөл. Ресурс Azure Storage тіркелгісі, Azure Event Hub немесе Azure Log Analytics жұмыс кеңістігі болуы мүмкін. Қосымша ақпаратты қараңыз [Azure порталы арқылы Azure рөл тағайындауларын қосыңыз немесе жойыңыз](/azure/role-based-access-control/role-assignments-portal).
- [Тағайындалған жерге қойылатын талаптар](/azure/azure-monitor/platform/diagnostic-settings#destination-requirements) Azure Storage, Azure Event Hub немесе Azure Log Analytics үшін кездесті.
- Сізде кем дегенде бар **Оқырман** ресурс тиесілі ресурс тобының рөлі.

### <a name="set-up-diagnostics-with-azure-monitor"></a>Azure мониторымен диагностиканы орнатыңыз

1. Customer Insights ішінде таңдаңыз **Жүйе** > **Диагностика** осы дананы конфигурациялаған диагностикалық мақсаттарды көру үшін.

1. таңдаңыз **Баратын жерді қосыңыз**.

   > [!div class="mx-imgBorder"]
   > ![Диагностикалық байланыс](media/diagnostics-pane.png "Диагностикалық байланыс")

1. ішінде атауды көрсетіңіз **Диагностика тағайындау орнының атауы** өріс.

1. таңдаңыз **Жалға алушы** тағайындалған ресурсы бар Azure жазылымын таңдаңыз және таңдаңыз **кіру**.

1. таңдаңыз **Ресурс түрі** (Сақтау тіркелгісі, Event Hub немесе журнал талдауы).

1. таңдаңыз **Жазылым** тағайындалған ресурс үшін.

1. таңдаңыз **Ресурстар тобы** тағайындалған ресурс үшін.

1. таңдаңыз **Ресурс**.

1. растаңыз **Деректер құпиялылығы және сәйкестік** мәлімдеме.

1. таңдаңыз **Жүйеге қосылу** тағайындалған ресурсқа қосылу үшін. Егер API қолданыста болса және оқиғаларды жасаса, журналдар тағайындалған жерде 15 минуттан кейін пайда бола бастайды.

### <a name="remove-a-destination"></a>Мақсатты жою

1. Бару **Жүйе** > **Диагностика**.

1. Тізімнен диагностикалық мақсатты таңдаңыз.

1. Ішінде **Әрекеттер** бағанынан таңдаңыз **Жою** белгішесі.

1. Журналды қайта жіберуді тоқтату үшін жоюды растаңыз. Azure жазылымындағы ресурс жойылмайды. ішіндегі сілтемені таңдауға болады **Әрекеттер** таңдалған ресурс үшін Azure порталын ашу және оны сол жерден жою үшін баған.

## <a name="log-categories-and-event-schemas"></a>Журнал санаттары және оқиға схемалары

Қазіргі уақытта [API оқиғалары](apis.md) және жұмыс процесі оқиғаларына қолдау көрсетіледі және келесі санаттар мен схемалар қолданылады.
Журнал схемасы келесіге сәйкес келеді [Azure Monitor жалпы схемасы](/azure/azure-monitor/platform/resource-logs-schema#top-level-common-schema).

### <a name="categories"></a>Санаттар

Customer Insights екі санатты ұсынады:

- **Аудит оқиғалары** :[API оқиғалары](#api-event-schema) қызметтегі конфигурация өзгерістерін бақылау үшін. `POST|PUT|DELETE|PATCH` операциялар осы санатқа жатады.
- **Операциялық оқиғалар** :[API оқиғалары](#api-event-schema) немесе [жұмыс процесінің оқиғалары](#workflow-event-schema) қызметті пайдалану кезінде жасалады.  Мысалға,`GET` сұраулар немесе жұмыс процесінің орындалу оқиғалары.

## <a name="configuration-on-the-destination-resource"></a>Тағайындалған ресурстағы конфигурация

Ресурс түріне таңдауыңызға байланысты келесі қадамдар автоматты түрде қолданылады:

### <a name="storage-account"></a>Сақтау орны тіркелгісі

Customer Insights қызметінің директоры алады **Сақтау есептік жазбасының салымшысы** таңдалған ресурста рұқсат береді және таңдалған аттар кеңістігі астында екі контейнер жасайды:

- `insight-logs-audit` қамтитын **аудиторлық оқиғалар**
- `insight-logs-operational` қамтитын **операциялық оқиғалар**

### <a name="event-hub"></a>Оқиға хабы

Customer Insights қызметінің директоры алады **Azure Event Hubs деректер иесі** ресурсқа рұқсат береді және таңдалған аттар кеңістігінде екі оқиға хабын жасайды:

- `insight-logs-audit` қамтитын **аудиторлық оқиғалар**
- `insight-logs-operational` қамтитын **операциялық оқиғалар**

### <a name="log-analytics"></a>Log Analytics

Customer Insights қызметінің директоры алады **Log Analytics Contributor** ресурсқа рұқсат. Журналдар астында қолжетімді болады **Журналдар** > **Кестелер** > **Журналды басқару** таңдалған Log Analytics жұмыс кеңістігінде. кеңейтіңіз **Журналды басқару** шешімін тауып, орнын табыңыз`CIEventsAudit` және`CIEventsOperational` кестелер.

- `CIEventsAudit` қамтитын **аудиторлық оқиғалар**
- `CIEventsOperational` қамтитын **операциялық оқиғалар**

Астында **Сұраулар** терезені кеңейтіңіз **Аудит** шешімін тауып, іздеу арқылы берілген мысал сұрауларды табыңыз `CIEvents`.

## <a name="event-schemas"></a>Оқиға схемалары

API оқиғалары мен жұмыс үрдісінің оқиғалары ортақ құрылымға және олар ерекшеленетін мәліметтерге ие, қараңыз [API оқиға схемасы](#api-event-schema) немесе [жұмыс процесі оқиғасының схемасы](#workflow-event-schema).

### <a name="api-event-schema"></a>API оқиға схемасы

| Өріс             | Деректер түрі  | Міндетті/міндетті емес | Сипаттама       | Мысал        |
| ----------------- | --------- | ----------------- | --------------------- | ------------------------ |
| `time`            | Уақыт белгісі | Талап етіледі          | Оқиғаның уақыт белгісі (UTC)       | `2020-09-08T09:48:14.8050869Z`         |
| `resourceId`      | String    | Талап етіледі          | Оқиғаны шығарған дананың ResourceId         | `/SUBSCRIPTIONS/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX/RESOURCEGROUPS/<RESOURCEGROUPNAME>/`<br>`PROVIDERS/MICROSOFT.D365CUSTOMERINSIGHTS/`<br>`INSTANCES/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX`  |
| `operationName`   | String    | Талап етіледі          | Осы оқиға арқылы көрсетілген операцияның атауы.                                                                                                                | `Workflows.GetWorkFlowStatusAsync`                                                                                                                                       |
| `category`        | String    | Талап етіледі          | Оқиғаның журнал санаты. Немесе`Operational` немесе `Audit`. Барлық POST/PUT/PATCH/DELETE HTTP сұрауларымен тегтелген`Audit`, қалғанының бәрі бар`Operational` | `2020-09-08T09:48:14.8050869Z`                                                                                                                                           |
| `resultType`      | String    | Талап етіледі          | Оқиға жағдайы. `Success`,`ClientError`,`Failure`                                                                                                        |                                                                                                                                                                          |
| `resultSignature` | String    | Таңдаулы          | Оқиғаның нәтиже күйі. Егер операция REST API шақыруына сәйкес келсе, бұл HTTP күй коды.        | `200`             |
| `durationMs`      | Ұзын      | Таңдаулы          | Операция ұзақтығы миллисекундпен.     | `133`     |
| `callerIpAddress` | String    | Таңдаулы          | Қоңырау шалушының IP мекенжайы, егер операция жалпыға қолжетімді IP мекенжайынан келетін API қоңырауына сәйкес келсе.                                                 | `144.318.99.233`         |
| `identity`        | String    | Таңдаулы          | Пайдаланушының немесе операцияны орындаған қолданбаның идентификациясын сипаттайтын JSON нысаны.       | Қараңыз [Жеке басын куәландыратын](#identity-schema) бөлім.     |  |
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

Жұмыс процесі бірнеше қадамдарды қамтиды. [Деректер көздерін қабылдау](data-sources.md),[біріктіру](data-unification.md),[байыту](enrichment-hub.md), және [экспорт](export-destinations.md) деректер. Барлық осы қадамдар жеке орындалады немесе келесі процестермен реттеледі. 

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
| `time`          | Уақыт белгісі | Талап етіледі          | Оқиғаның уақыт белгісі (UTC).                                                                                                                                 | `2020-09-08T09:48:14.8050869Z`                                                                                                                                           |
| `resourceId`    | String    | Талап етіледі          | Оқиғаны шығарған дананың ResourceId.                                                                                                            | `/SUBSCRIPTIONS/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX/RESOURCEGROUPS/<RESOURCEGROUPNAME>/`<br>`PROVIDERS/MICROSOFT.D365CUSTOMERINSIGHTS/`<br>`INSTANCES/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX` |
| `operationName` | String    | Талап етіледі          | Осы оқиға арқылы көрсетілген операцияның атауы. `{OperationType}.[WorkFlow|Task][Started|Completed]`. Қараңыз [Операция түрлері](#operation-types) анықтама үшін. | `Segmentation.WorkflowStarted`,<br> `Segmentation.TaskStarted`, <br> `Segmentation.TaskCompleted`, <br> `Segmentation.WorkflowCompleted`                                 |
| `category`      | String    | Талап етіледі          | Оқиғаның журнал санаты. Әрқашан`Operational` Жұмыс процесі оқиғалары үшін                                                                                           | `Operational`                                                                                                                                                            | 
| `resultType`    | String    | Талап етіледі          | Оқиға жағдайы. `Running`,`Skipped`,`Successful`,`Failure`                                                                                            |                                                                                                                                                                          |
| `durationMs`    | Ұзын      | Таңдаулы          | Операция ұзақтығы миллисекундпен.                                                                                                                    | `133`                                                                                                                                                                    |
| `properties`    | String    | Таңдаулы          | Оқиғалардың белгілі бір санатына көбірек сипаттары бар JSON нысаны.                                                                                        | Ішкі бөлімді қараңыз [Жұмыс үрдісінің сипаттары](#workflow-properties-schema)                                                                                                       |
| `level`         | String    | Талап етіледі          | Оқиғаның ауырлық деңгейі.                                                                                                                                  | `Informational`, `Warning` немесе `Error`                                                                                                                                   |
|                 |

#### <a name="workflow-properties-schema"></a>Жұмыс үрдісінің сипаттары схемасы

Жұмыс процесі оқиғаларының келесі қасиеттері бар.

| Өріс              | Workflow | Тапсырма | Сипаттама            |
| ------------------------------- | -------- | ---- | ----------- |
| `properties.eventType`                       | Иә      | Иә  | Әрқашан`WorkflowEvent`, оқиғаны жұмыс процесі оқиғасы ретінде белгілеу.                                                                                                                                                                                                |
| `properties.workflowJobId`                   | Иә      | Иә  | Жұмыс үрдісінің идентификаторы. Жұмыс процесін орындаудағы барлық жұмыс процесі мен тапсырма оқиғалары бірдей болады `workflowJobId`.                                                                                                                                   |
| `properties.operationType`                   | Иә      | Иә  | Операция идентификаторы, [Операция түрлері] бөлімін қараңыз.(#operation-types)                                                                                                                                                                                       |
| `properties.tasksCount`                      | Иә      | No   | Тек жұмыс процесі. Жұмыс процесі іске қосатын тапсырмалар саны.                                                                                                                                                                                                       |
| `properties.submittedBy`                     | Иә      | No   | Қосымша. Тек жұмыс процесі оқиғалары. The Azure Active Directory [пайдаланушының объектінің идентификаторы](/azure/marketplace/find-tenant-object-id#find-user-object-id) жұмыс процесін кім іске қосты, сонымен қатар қараңыз `properties.workflowSubmissionKind`.                                   |
| `properties.workflowType`                    | Иә      | No   | `full` немесе`incremental` жаңарту.                                                                                                                                                                                                                            |
| `properties.workflowSubmissionKind`          | Иә      | No   | `OnDemand` немесе `Scheduled`.                                                                                                                                                                                                                                  |
| `properties.workflowStatus`                  | Иә      | No   | `Running` немесе `Successful`.                                                                                                                                                                                                                                 |
| `properties.startTimestamp`                  | Иә      | Иә  | UTC уақыт белгісі`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.endTimestamp`                    | Иә      | Иә  | UTC уақыт белгісі`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.submittedTimestamp`              | Иә      | Иә  | UTC уақыт белгісі`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.instanceId`                      | Иә      | Иә  | Тұтынушы түсініктері`instanceId`                                                                                                                                                                                                                              |  |
| `properties.identifier`                      | No       | Иә  | - OperationType = үшін`Export`, идентификатор экспорт конфигурациясының нұсқаулығы болып табылады. <br> - OperationType = үшін`Enrichment`, бұл байытудың нұсқаушысы <br> - OperationType үшін`Measures` және`Segmentation`, идентификатор нысан атауы болып табылады. |
| `properties.friendlyName`                    | No       | Иә  | Экспорттың немесе өңделетін нысанның пайдаланушыға ыңғайлы атауы.                                                                                                                                                                                           |
| `properties.error`                           | No       | Иә  | Қосымша. Қосымша мәліметтері бар қате хабары.                                                                                                                                                                                                                  |
| `properties.additionalInfo.Kind`             | No       | Иә  | Қосымша. OperationType үшін`Export` тек. Экспорт түрін анықтайды. Қосымша ақпаратты қараңыз [экспорттық бағыттарға шолу](export-destinations.md).                                                                                          |
| `properties.additionalInfo.AffectedEntities` | No       | Иә  | Қосымша. OperationType үшін`Export` тек. Экспортта конфигурацияланған нысандардың тізімін қамтиды.                                                                                                                                                            |
| `properties.additionalInfo.MessageCode`      | No       | Иә  | Қосымша. OperationType үшін`Export` тек. Экспортқа арналған толық хабарлама.                                                                                                                                                                                 |
| `properties.additionalInfo.entityCount`      | No       | Иә  | Қосымша. OperationType үшін`Segmentation` тек. Сегменттегі мүшелердің жалпы санын көрсетеді.                                                                                                                                                    |
