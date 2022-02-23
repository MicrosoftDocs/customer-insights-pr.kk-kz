---
title: Microsoft Dataverse ішіндегі Customer Insights деректері
description: Customer Insights нысандарын Microsoft Dataverse ішіндегі кестелер ретінде пайдаланыңыз.
ms.date: 11/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 6f74559b34a95ed976a4e353c2dbabe59e1a8839
ms.sourcegitcommit: 9558ff772ee6c944fcb8db4bfc8cda13b38a1bff
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 11/29/2021
ms.locfileid: "7866941"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>Microsoft Dataverse ішіндегі Customer Insights деректерімен жұмыс жасаңыз

Customer Insights шығыс нысандарын қол жетімді ету опциясын ұсынады [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro.md). Бұл біріктіру деректерді оңай бөлісуді және төмен кодты/кодсыз тәсіл арқылы реттелетін әзірлеуді қамтамасыз етеді. Шығарылатын нысандар Dataverse ішіндегі кестелер ретінде қолжетімді болады. Бұл кестелер сияқты сценарийлерді қосады [Power Automate арқылы автоматтандырылған жұмыс процестері](/power-automate/getting-started),[үлгіге негізделген қолданбалар](/powerapps/maker/model-driven-apps/) және [кенеп қолданбалары](/powerapps/maker/canvas-apps/) Power Apps арқылы. Деректерді Dataverse кестелеріне негізделген кез келген басқа қолданба үшін пайдалануға болады. Ағымдағы енгізу, негізінен, тұтынушы идентификаторы үшін қолжетімді аудитория туралы пайдалы мәліметтер нысандарын алуға болатын іздеуге қолдау көрсетеді.

## <a name="attach-a-dataverse-environment-to-customer-insights"></a>Customer Insights қызметіне Dataverse ортасын тіркеңіз

**Dataverse орталары бар ұйымдар**

Dataverse пайдаланатын ұйымдар мүмкін [олардың бар Dataverse орталарының бірін пайдаланыңыз](create-environment.md) әкімші аудитория түсініктерін орнатқанда. URL мекенжайын Dataverse ортасына беру арқылы ол олардың жаңа аудитория түсініктері ортасына қосылады. Ең жақсы өнімділікті қамтамасыз ету үшін Customer Insights және Dataverse орталары бір аймақта орналастырылуы керек.

**Жаңа ұйым**

Customer Insights орнату кезінде жаңа ұйым жасасаңыз, автоматты түрде жаңа Dataverse ортасын аласыз.

> [!NOTE]
> Егер сіздің ұйымдарыңыз жалға алушысында Dataverse қолданса, мынаны есте сақтау маңызды.[Dataverse ортасын жасауды әкімші басқарады](/power-platform/admin/control-environment-creation.md) . Мысалы, ұйымдық тіркелгіңізбен жаңа аудиториялық түсініктер ортасын орнатып жатсаңыз және әкімші әкімшілерден басқа барлығы үшін Dataverse сынақ орталарын жасауды өшірген болса, жаңа сынақ ортасын жасай алмайсыз.
> 
> Customer Insights жүйесінде жасалған Dataverse сынақ орталарында 3 ГБ жады бар, ол жалға алушыға құқығы бар жалпы сыйымдылыққа есептелмейді. Ақылы жазылымдар дерекқор үшін 15 ГБ және файлдарды сақтау үшін 20 ГБ Dataverse құқығын алады.

## <a name="output-entities"></a>Шығыс нысандар

Аудитория түсініктерінен кейбір шығыс нысандары Dataverse ішіндегі кестелер ретінде қолжетімді. Төмендегі бөлімдер осы кестелердің күтілетін схемасын сипаттайды.

- [Тұтынушы профилі](#customerprofile)
- [AlternateKey](#alternatekey)
- [Бірыңғай әрекет](#unifiedactivity)
- [CustomerMeasure](#customermeasure)
- [Арттыру](#enrichment)
- [Болжам](#prediction)
- [Сегмент мүшелігі](#segment-membership)


### <a name="customerprofile"></a>Тұтынушы профилі

Бұл кестеде Customer Insights бағдарламасындағы тұтынушының бірыңғай профилі бар. Тұтынушының бірыңғай профилінің схемасы біріктіру процесінде қолданылатын нысандар мен төлсипаттарға байланысты. Тұтынушы профилінің схемасы әдетте [Тұтынушы профилінің Common Data Model анықтамасы](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile) ішіндегі төлсипаттардың ішкі жинағын қамтиды.

### <a name="alternatekey"></a>AlternateKey

AlternateKey кестесінде біріктіру процесіне қатысқан нысандардың кілттері бар.

|Column  |Түр  |Сипаттамасы  |
|---------|---------|---------|
|DataSourceName    |String         | Деректер көзінің атауы. Мысалы: `datasource5`        |
|EntityName        | String        | Аудитория туралы пайдалы мәліметтер нысанының атауы. Мысалы: `contact1`        |
|AlternateValue    |String         |Тұтынушы идентификаторымен салыстырылатын балама идентификатор. Мысал: `cntid_1078`         |
|KeyRing           | Көп жолды мәтін        | JSON мәні  </br> Үлгі: [{"dataSourceName":" datasource5 ",</br>"entityName":" contact1",</br>"preferredKey":" cntid_1078",</br>"кілттер":[" cntid_1078"]}]       |
|CustomerId         | String        | Тұтынушының бірыңғай профилінің идентификаторы.         |
|AlternateKeyId     | GUID         |  Msdynci_identifier негізіндегі AlternateKey анықтамалық GUID идентификаторы       |
|msdynci_identifier |   String      |   `DataSourceName|EntityName|AlternateValue`  </br> Үлгі: `testdatasource|contact1|cntid_1078`    |

### <a name="unifiedactivity"></a>Бірыңғай әрекет

Бұл кестеде Customer Insights бағдарламасында қолжетімді пайдаланушылардың әрекеттері бар.

| Column            | Түр        | Сипаттамасы                                                                              |
|-------------------|-------------|------------------------------------------------------------------------------------------|
| CustomerId        | String      | Тұтынушы профилінің идентификаторы                                                                      |
| ActivityId        | String      | Тұтынушы әрекетінің ішкі идентификаторы (негізгі кілт)                                       |
| SourceEntityName  | String      | Бастапқы нысан атауы                                                                |
| SourceActivityId  | String      | Бастапқы көздегі негізгі кілт                                                       |
| ActivityType      | String      | Семантикалық әрекет түрі немесе реттелетін әрекет атауы                                        |
| ActivityTimeStamp | DATETIME    | Әрекеттің уақыт белгісі                                                                      |
| Атау             | String      | Әрекеттің тақырыбы немесе атауы                                                               |
| Сипаттамасы       | String      | Әрекет сипаттамасы                                                                     |
| URL мекенжайы               | String      | Әрекетке тән сыртқы URL мекенжай сілтемесі                                         |
| SemanticData      | JSON жолы | Әрекет түріне тән семантикалық салыстыру өрістеріне арналған негізгі мән жұптарының тізімін қамтиды |
| RangeIndex        | String      | Әрекеттің уақыт шкаласы мен тиімді ауқым сұрауларын сұрыптау үшін пайдаланылатын Unix уақыт белгісі |
| mydynci_unifiedactivityid   | GUID | Тұтынушы әрекетінің ішкі идентификаторы (ActivityId) |

### <a name="customermeasure"></a>CustomerMeasure

Бұл кестеде тұтынушы төлсипаттарына негізделген өлшемдердің шығыс деректері келтірілген.

| Column             | Түр             | Сипаттамасы                 |
|--------------------|------------------|-----------------------------|
| CustomerId         | String           | Тұтынушы профилінің идентификаторы        |
| Көрсеткіштер           | JSON жолы      | Өлшеу атауы мен берілген тұтынушы үшін мәндеріне арналған негізгі мән жұптарының тізімін қамтиды | 
| msdynci_identifier | String           | `Customer_Measure|CustomerId` |
| msdynci_customermeasureid | GUID      | Тұтынушы профилінің идентификаторы |


### <a name="enrichment"></a>Арттыру

Бұл кестеде нақтылау процесінің нәтижелері келтірілген.

| Column               | Түр             |  Сипаттамасы                                          |
|----------------------|------------------|------------------------------------------------------|
| CustomerId           | String           | Тұтынушы профилінің идентификаторы                                 |
| EnrichmentProvider   | String           | Нақтылау провайдерінің атауы                                  |
| EnrichmentType       | String           | Нақтылау түрі                                      |
| Мәндер               | JSON жолы      | Нақтылау процесінде жасалатын төлсипаттар тізімі |
| msdynci_enrichmentid | GUID             | Msdynci_identifier-ден жасалған анықтамалық GUID идентификаторы |
| msdynci_identifier   | String           | `EnrichmentProvider|EnrichmentType|CustomerId`         |

### <a name="prediction"></a>Болжам

Бұл кестеде үлгі болжамдарының нәтижелері келтірілген.

| Column               | Түр        | Сипаттамасы                                          |
|----------------------|-------------|------------------------------------------------------|
| CustomerId           | String      | Тұтынушы профилінің идентификаторы                                  |
| ModelProvider        | String      | Үлгі провайдерінің атауы                                      |
| Модель                | String      | Модель атауы                                                |
| Мәндер               | JSON жолы | Үлгіде жасалатын төлсипаттар тізімі |
| msdynci_predictionid | GUID        | Msdynci_identifier-ден жасалған анықтамалық GUID идентификаторы | 
| msdynci_identifier   | String      |  `Model|ModelProvider|CustomerId`                      |

### <a name="segment-membership"></a>Сегмент мүшелігі

Бұл кесте тұтынушы профильдерінің сегмент мүшелігі туралы ақпаратты қамтиды.

| Column        | Түр | Сипаттама                        |
|--------------------|--------------|-----------------------------|
| CustomerId        | String       | Тұтынушы профилінің идентификаторы        |
| SegmentProvider      | String       | Сегменттерді жариялайтын қолданба. Әдепкі: аудитория туралы түсініктер         |
| SegmentMembershipType | String       | Осы сегменттің мүшелік жазбасының тұтынушы түрі. Тұтынушы, Контакт немесе Тіркелгі сияқты бірнеше түрді қолдайды. Әдепкі: Тұтынушы  |
| Сегменттер       | JSON жолы  | Тұтынушы профилі мүшесі болып табылатын бірегей сегменттер тізімі      |
| msdynci_identifier  | String   | Сегмент мүшелігі жазбасының бірегей идентификаторы. `CustomerId|SegmentProvider|SegmentMembershipType|Name`  |
| msdynci_segmentmembershipid | GUID      | Детерминистік GUID жасалған`msdynci_identifier`          |
