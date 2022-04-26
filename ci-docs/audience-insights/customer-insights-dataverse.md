---
title: Microsoft Dataverse жүйесіндегі Customer Insights деректері
description: Customer Insights нысандарын Microsoft Dataverse жүйесінде кесте ретінде пайдаланыңыз.
ms.date: 04/05/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: bbbbf2a7f5edb81ee75f6e33988cd4721134b6e7
ms.sourcegitcommit: 0363559a1af7ae16da2a96b09d6a4a8a53a8cbb8
ms.translationtype: MT
ms.contentlocale: kk-KZ
ms.lasthandoff: 04/05/2022
ms.locfileid: "8547633"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>Microsoft Dataverse жүйесіндегі Customer Insights деректерімен жұмыс істеу

Customer Insights шығыс нысандарын [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro) жүйесінде қолжетімді ету мүмкіндігін ұсынады. Бұл интеграция төмен код/кодсыз тәсіл арқылы деректерді оңай бөлісуге және теңшелетін әзірлеуге мүмкіндік береді. The [шығару нысандары](#output-entities) а ішіндегі кестелер түрінде қол жетімді Dataverse қоршаған орта. Деректерді негізінде кез келген басқа қолданба үшін пайдалануға болады Dataverse кестелер. Бұл кестелер автоматтандырылған жұмыс процестері сияқты сценарийлерді қосады Power Automate немесе көмегімен қолданбалар құру Power Apps. Ағымдағы енгізу негізінен берілген тұтынушы идентификаторы үшін қолжетімді Customer Insights нысандарынан деректерді алуға болатын іздеулерді қолдайды.

## <a name="attach-a-dataverse-environment-to-customer-insights"></a>Dataverse жүйесін Customer Insights бағдарламасына тіркеу

**Қолданыстағы ұйым**

Әкімшілер Customer Insights параметрін конфигурациялай алады [бар пайдаланыңыз Dataverse қоршаған орта](create-environment.md) олар Customer Insights ортасын жасағанда. Dataverse ортасының URL мекенжайын ұсыну арқылы бұл олардың жаңа аудитория туралы пайдалы мәліметтер ортасына тіркеледі. Тұтынушы түсініктері және Dataverse орталар бір аймақта орналастырылуы керек. 

Барын пайдаланғыңыз келмесе Dataverse ортада жүйе клиентіңіздегі Customer Insights деректері үшін жаңа орта жасайды. 

> [!NOTE]
> Егер сіздің ұйымдарыңыз қатысушыда бұрыннан Dataverse ортасын пайдаланатын болса, [Dataverse ортасын жасауды әкімші басқаратынын](/power-platform/admin/control-environment-creation) есте ұстаған жөн. Мысалы, егер сіз ұйым тіркелгісімен жаңа аудитория туралы пайдалы мәліметтер ортасын орнатсаңыз және әкімші әкімшілерден басқалары үшін Dataverse сынақ орталарын жасауды өшірсе, сіз жаңа сынақ ортасын жасай алмайсыз.
> 
> Customer Insights бағдарламасында жасалған Dataverse сынақ орталарында 3 ГБ жады бар, бұл қатысушыға ұсынылған жалпы сыйымдылықта есептелмейді. Ақылы жазылымдар Dataverse құқығын дерекқор үшін 15 ГБ және файлдарды сақтау үшін 20 ГБ сыйымдылық алады.

**Жаңа ұйым**

Customer Insights орнату кезінде жаңа ұйым жасасаңыз, жүйе автоматты түрде жаңа ұйымды жасайды Dataverse сіз үшін ұйымыңыздағы орта.

## <a name="output-entities"></a>Шығыс нысандар

Аудитория туралы пайдалы мәліметтердегі кейбір шығыс нысандары Dataverse жүйесінде кестелер ретінде қолжетімді. Төмендегі бөлімдер осы кестелердің күтілетін схемасын сипаттайды.

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
|KeyRing           | Көп жолды мәтін        | JSON мәні  </br> Үлгі: [{"dataSourceName":" datasource5 ",</br>"entityName":" contact1",</br>"preferredKey":" cntid_1078",</br>"keys":[" cntid_1078"]}]       |
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

| Column        | Түр | Сипаттама                        |
|--------------------|--------------|-----------------------------|
| CustomerId        | String       | Тұтынушы профилінің идентификаторы        |
| SegmentProvider      | String       | Сегменттерді жариялайтын қолданба. Әдепкі: аудитория туралы түсініктер         |
| SegmentMembershipType | String       | Осы сегменттің мүшелік жазбасының тұтынушы түрі. Тұтынушы, Контакт немесе Тіркелгі сияқты бірнеше түрді қолдайды. Әдепкі: Тұтынушы  |
| Сегменттер       | JSON жолы  | Тұтынушы профилі мүшесі болып табылатын бірегей сегменттер тізімі      |
| msdynci_identifier  | String   | Сегмент мүшелігі жазбасының бірегей идентификаторы. `CustomerId|SegmentProvider|SegmentMembershipType|Name`  |
| msdynci_segmentmembershipid | GUID      | Детерминистік GUID жасалған`msdynci_identifier`          |
