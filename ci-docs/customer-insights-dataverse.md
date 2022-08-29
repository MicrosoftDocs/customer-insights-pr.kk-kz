---
title: Microsoft Dataverse жүйесіндегі Customer Insights деректерімен жұмыс істеу
description: Customer Insights және қосу жолын үйреніңіз Microsoft Dataverse және экспортталатын шығыс нысандарын түсіну Dataverse.
ms.date: 08/15/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 0d536259f310b41fe12922baeebdc4569937db08
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: kk-KZ
ms.lasthandoff: 08/16/2022
ms.locfileid: "9303836"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>Microsoft Dataverse жүйесіндегі Customer Insights деректерімен жұмыс істеу

Customer Insights шығыс нысандарын [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro) жүйесінде қолжетімді ету мүмкіндігін ұсынады. Бұл интеграция төмен код/кодсыз тәсіл арқылы деректерді оңай бөлісуге және теңшелетін әзірлеуге мүмкіндік береді. The [шығару нысандары](#output-entities) а ішіндегі кестелер түрінде қол жетімді Dataverse қоршаған орта. Деректерді негізінде кез келген басқа қолданба үшін пайдалануға болады Dataverse кестелер. Бұл кестелер автоматтандырылған жұмыс процестері сияқты сценарийлерді қосады Power Automate немесе көмегімен қолданбалар құру Power Apps.

Сіздің Dataverse орта да мүмкіндік береді [көмегімен жергілікті деректер көздерінен деректерді қабылдау Power Platform деректер ағындары мен шлюздер](connect-power-query.md#add-data-from-on-premises-data-sources).

## <a name="prerequisites"></a>Алғышарттар

- Тұтынушы түсініктері және Dataverse орталар бір аймақта орналастырылуы керек.
- ішінде орнатылған жаһандық әкімші рөлі Dataverse қоршаған орта. Бұл болса, тексеріңіз [Dataverse ортамен байланысты](/power-platform/admin/control-user-access#associate-a-security-group-with-a-dataverse-environment) белгілі бір қауіпсіздік топтарына және сол қауіпсіздік топтарына қосылғаныңызға көз жеткізіңіз.
- Бұрыннан байланыстырылған басқа Customer Insights ортасы Dataverse қосқыңыз келетін орта. Қалай жасау керектігін біліңіз [бар қосылымды жою Dataverse қоршаған орта](#remove-an-existing-connection-to-a-dataverse-environment).
- А Microsoft Dataverse ортаны теңшесеңіз, бір сақтау тіркелгісіне қосылған орта [өзіңіздің пайдаланыңыз Azure Data Lake Storage](own-data-lake-storage.md).

## <a name="dataverse-storage-capacity-entitlement"></a>Dataverse сақтау сыйымдылығы құқығы

Customer Insights жазылымы ұйымыңыздың бар қосымша мүмкіндіктеріне құқық береді [Dataverse сақтау сыйымдылығы](/power-platform/admin/capacity-storage). Қосылған сыйымдылық жазылым пайдаланатын профильдер санына байланысты.

**Мысал:**

Сіз 100 000 тұтынушы профиліне 15 ГБ дерекқор жады және 20 ГБ файл жады аласыз деп есептесеңіз. Жазылымыңызда 300 000 тұтынушы профилі болса, жалпы сақтау сыйымдылығыңыз 45 ГБ (3 x 15 ГБ) дерекқор жады және 60 ГБ файл жады (3 x 20 ГБ) болады. Сол сияқты, сізде 30K есептік жазбасы бар B-to-B жазылымыңыз болса, жалпы сақтау сыйымдылығыңыз 45 ГБ (3 x 15 ГБ) дерекқор жады және 60 ГБ файл жады (3 x 20 ГБ) болады.

Журнал сыйымдылығы ұйымыңыз үшін қосымша емес және бекітілген.

Толық сыйымдылық құқықтары туралы қосымша ақпаратты қараңыз [Dynamics 365 лицензиялау нұсқаулығы](https://go.microsoft.com/fwlink/?LinkId=866544).

## <a name="connect-a-dataverse-environment-to-customer-insights"></a>Қосылу а Dataverse Customer Insights үшін орта

The **Microsoft Dataverse** қадам Customer Insights мәліметтерін өзіңіздің деректеріңізбен байланыстыруға мүмкіндік береді Dataverse кезінде орта [Customer Insights ортасын жасау](create-environment.md).

:::image type="content" source="media/dataverse-provisioning.png" alt-text="деректермен алмасу Microsoft Dataverse жаңа орталар үшін автоматты түрде қосылады.":::

1. URL мекенжайыңызды көрсетіңіз Dataverse ортаны таңдаңыз немесе сіз үшін біреуін жасау үшін бос қалдырыңыз.

   > [!NOTE]
   > Customer Insights және арасындағы байланысты орнатқаннан кейін Dataverse, үшін ұйым атауын өзгертпеңіз Dataverse қоршаған орта. ұйымның атауы қолданылады Dataverse URL және өзгертілген атау Customer Insights байланысын үзеді.

   [Power Platform әкімшілер жаңаны кім жасай алатынын басқара алады Dataverse орталар](/power-platform/admin/control-environment-creation). Жаңа Customer Insights ортасын орнатуға әрекеттеніп жатсаңыз және жасай алмасаңыз, әкімші мынаны жасауды өшірген болуы мүмкін.Dataverse әкімшілерден басқа барлығына арналған орталар.

1. Жеке Data Lake Storage есептік жазбаңызды пайдаланып жатсаңыз:
   1. таңдаңыз **Деректерді ортақ пайдалануды қосыңыз** -мен Dataverse.
   1. енгізіңіз **Рұқсаттар идентификаторы**. Рұқсат идентификаторын алу үшін, [деректермен бөлісуді қосыңыз Dataverse өзіңнен Azure Data Lake Storage](#enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview).

## <a name="enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview"></a>Деректерді ортақ пайдалануды қосыңыз Dataverse өзіңнен Azure Data Lake Storage (алдын ала қарау)

жылы [сенікі Azure Data Lake Storage есептік жазба](own-data-lake-storage.md), Customer Insights ортасын орнатқан пайдаланушыда кем дегенде бар екенін тексеріңіз **Blob деректерін оқу құралы** бойынша рұқсаттар`customerinsights` сақтау шотындағы контейнер.

### <a name="limitations"></a>Шектеулер

- A арасында тек бір-бірден салыстыру Dataverse ұйымдастыру және а Azure Data Lake Storage есептік жазба. Бір рет а Dataverse ұйым сақтау тіркелгісіне қосылған болса, ол басқа сақтау тіркелгісіне қосыла алмайды. Бұл шектеу алдын алады Dataverse бірнеше сақтау тіркелгілерін толтырудан.
- Azure Private Link параметріне кіру үшін қажет болса, деректерді ортақ пайдалану жұмыс істемейді Azure Data Lake Storage тіркелгі, себебі ол брандмауэрдің артында. Dataverse қазіргі уақытта Жеке сілтеме арқылы жеке соңғы нүктелерге қосылуды қолдамайды.

### <a name="set-up-security-groups-on-your-own-azure-data-lake-storage"></a>Қауіпсіздік топтарын өзіңіз орнатыңыз Azure Data Lake Storage

1. Azure жазылымында екі қауіпсіздік тобын жасаңыз - біреуі **Оқырман** қауіпсіздік тобы және біреуі **Қатысушы** қауіпсіздік тобын орнатыңыз Microsoft Dataverse екі қауіпсіздік тобының иесі ретінде қызмет көрсету.

1. Қол жеткізуді басқару тізімін (ACL) басқарыңыз`customerinsights` осы қауіпсіздік топтары арқылы сақтау тіркелгіңіздегі контейнер.
   1. қосыңыз Microsoft Dataverse қызмет көрсету және кез келген Dataverse Dynamics 365 Marketing сияқты бизнес қолданбаларына негізделген **Оқырман** қауіпсіздік тобы бар **тек оқуға арналған** рұқсаттар.
   1. қосу *тек* үшін Customers Insights қолданбасы **Қатысушы** екеуін де беру үшін қауіпсіздік тобы **оқу және жазу** профильдер мен түсініктерді жазу рұқсаттары.

### <a name="set-up-powershell"></a>PowerShell орнату

PowerShell сценарийлерін орындау үшін PowerShell бағдарламасын орнатыңыз.

1. соңғы нұсқасын орнатыңыз [Azure Active Directory Графикке арналған PowerShell](/powershell/azure/active-directory/install-adv2).
   1. Компьютерде пернетақтадағы Windows пернесін таңдап, **Windows PowerShell** іздеп, **Әкімші ретінде іске қосу** опциясын таңдаңыз.
   1. Ашылатын PowerShell терезесінде `Install-Module AzureAD` енгізіңіз.

1. Үш модульді импорттау.
   1. PowerShell терезесінде енгізіңіз`Install-Module -Name Az.Accounts` және қадамдарды орындаңыз.
   1. үшін қайталаңыз`Install-Module -Name Az.Resources` және `Install-Module -Name Az.Storage`.

### <a name="execute-powershell-scripts-and-obtain-the-permission-identifier"></a>PowerShell сценарийлерін орындаңыз және рұқсат идентификаторын алыңыз

1. Біздің инженерден іске қосу үшін қажет екі PowerShell сценарийін жүктеп алыңыз [GitHub репо](https://github.com/trin-msft/byol).
   - `CreateSecurityGroups.ps1`: Жалға алушының әкімші рұқсаттарын талап етеді.
   - `ByolSetup.ps1`: сақтау тіркелгісі/контейнер деңгейінде Storage Blob деректер иесі рұқсаттарын талап етеді. Бұл сценарий сізге рұқсатты жасайды. Сценарий сәтті іске қосылғаннан кейін рөл тағайындауыңызды қолмен жоюға болады.

1. Орындау`CreateSecurityGroups.ps1` Windows PowerShell жүйесінде Azure жазылымының идентификаторын қамтамасыз ету арқылы Azure Data Lake Storage. Қосымша ақпаратты және енгізілген логиканы қарап шығу үшін PowerShell сценарийін өңдегіште ашыңыз.

   Бұл сценарий Azure жазылымында екі қауіпсіздік тобын жасайды: біреуі Reader тобы үшін және екіншісі Contributor тобы үшін. Microsoft Dataverse қызмет осы қауіпсіздік топтарының екеуінің де иесі болып табылады.

1. ішінде пайдалану үшін осы сценарий жасаған екі қауіпсіздік тобының идентификаторы мәндерін сақтаңыз`ByolSetup.ps1` сценарий.

   > [!NOTE]
   > Қауіпсіздік тобын жасау жалға алушыда өшірілуі мүмкін. Бұл жағдайда қолмен орнату қажет болады және сіздің Azure AD админ керек еді [қауіпсіздік тобын құруды қосыңыз](/azure/active-directory/enterprise-users/groups-self-service-management).

1. Орындау`ByolSetup.ps1` Windows PowerShell жүйесінде Azure жазылымының идентификаторын қамтамасыз ету арқылы Azure Data Lake Storage, сақтау тіркелгісінің атауы, ресурс тобының атауы және Reader және Contributor қауіпсіздік тобының идентификаторы мәндері. Қосымша ақпаратты және енгізілген логиканы қарап шығу үшін PowerShell сценарийін өңдегіште ашыңыз.

   Бұл сценарий үшін қажетті рөлге негізделген қатынасты басқаруды қосады Microsoft Dataverse қызмет көрсету және кез келген Dataverse -негізделген іскерлік қолданбалар. Ол сонымен қатар қол жеткізуді басқару тізімін (ACL) жаңартады`customerinsights` көмегімен жасалған қауіпсіздік топтарына арналған контейнер`CreateSecurityGroups.ps1` сценарий. Қатысушылар тобы берілген *rwx* рұқсат және Оқырмандар тобы беріледі *rx* тек рұқсат.

1. Мынадай көрінетін шығыс жолын көшіріңіз:`https://DVBYODLDemo/customerinsights?rg=285f5727-a2ae-4afd-9549-64343a0gbabc&cg=720d2dae-4ac8-59f8-9e96-2fa675dbdabc`

1. Көшірілген шығыс жолын енгізіңіз **Рұқсаттар идентификаторы** үшін ортаны конфигурациялау қадамының өрісі Microsoft Dataverse.

   :::image type="content" source="media/dataverse-enable-datasharing-BYODL.png" alt-text="Деректерді ортақ пайдалануды қосу үшін конфигурация опциялары Azure Data Lake Storage бірге Microsoft Dataverse .":::

## <a name="remove-an-existing-connection-to-a-dataverse-environment"></a>A үшін бар қосылымды жойыңыз Dataverse қоршаған орта

a-ға қосылғанда Dataverse орта, қате туралы хабар **Бұл CDS ұйымы басқа Customer Insights данасына тіркелген** дегенді білдіреді Dataverse орта Customer Insights ортасында бұрыннан пайдаланылады. Жаһандық әкімші ретінде бұрыннан бар қосылымды жоюға болады Dataverse қоршаған орта. Өзгерістерді толтыру үшін бірнеше сағат кетуі мүмкін.

1. [Power Apps](https://make.powerapps.com) торабына өтіңіз.
1. Ортаны таңдау құралынан ортаны таңдаңыз.
1. Бару **Шешімдер**.
1. Аты аталған шешімді жойыңыз немесе жойыңыз **Dynamics 365 Customer Insights Тұтынушы картасының қондырмасы (алдын ала қарау)**.

НЕМЕСЕ

1. Өзіңізді ашыңыз Dataverse қоршаған орта.
1. Бару **Қосымша параметрлер** > **Шешімдер**.
1. жою **CustomerInsightsCustomerCard** шешім.

Қосылымды жою тәуелділіктерге байланысты орындалмаса, тәуелділіктерді де жою керек. Қосымша ақпаратты қараңыз [Тәуелділіктерді жою](/power-platform/alm/removing-dependencies).

## <a name="output-entities"></a>Шығыс нысандар

Customer Insights қолданбасының кейбір шығыс нысандары ішіндегі кестелер ретінде қол жетімді Dataverse. Төмендегі бөлімдер осы кестелердің күтілетін схемасын сипаттайды.

- [Тұтынушы профилі](#customerprofile)
- [AlternateKey](#alternatekey)
- [Бірыңғай әрекет](#unifiedactivity)
- [CustomerMeasure](#customermeasure)
- [Арттыру](#enrichment)
- [Болжам](#prediction)
- [Сегмент мүшелігі](#segment-membership)

### <a name="customerprofile"></a>Тұтынушы профилі

Бұл кестеде Customer Insights бағдарламасындағы тұтынушының бірыңғай профилі бар. Бірыңғай тұтынушы профилінің схемасы деректерді біріктіру процесінде пайдаланылатын нысандар мен атрибуттарға байланысты. Тұтынушы профилінің схемасы әдетте [Тұтынушы профилінің Common Data Model анықтамасы](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile) ішіндегі төлсипаттардың ішкі жинағын қамтиды.

### <a name="alternatekey"></a>AlternateKey

AlternateKey кестесінде біріктіру процесіне қатысқан нысандардың кілттері бар.

|Column  |Түр  |Сипаттамасы  |
|---------|---------|---------|
|DataSourceName    |String         | Деректер көзінің атауы. Мысалы: `datasource5`        |
|EntityName        | String        | Customer Insights ішіндегі нысанның атауы. Мысалы: `contact1`        |
|AlternateValue    |String         |Тұтынушы идентификаторымен салыстырылатын балама идентификатор. Мысал: `cntid_1078`         |
|KeyRing           | Көп жолды мәтін        | JSON мәні  </br> Үлгі: [{"dataSourceName":" datasource5 ",</br>"entityName":" contact1",</br>"preferredKey":" cntid_1078",</br>"keys":[" cntid_1078"]}]       |
|CustomerId         | String        | Тұтынушының бірыңғай профилінің идентификаторы.         |
|AlternateKeyId     | GUID         |  Msdynci_identifier негізіндегі AlternateKey анықтамалық GUID идентификаторы       |
|msdynci_identifier |   String      |   `DataSourceName|EntityName|AlternateValue`  </br> Үлгі: `testdatasource|contact1|cntid_1078`    |

### <a name="unifiedactivity"></a>Бірыңғай әрекет

Бұл кестеде Customer Insights бағдарламасында қолжетімді пайдаланушылардың әрекеттері бар.

| Column            | Түр        | Сипаттама                                                                              |
|-------------------|-------------|------------------------------------------------------------------------------------------|
| CustomerId        | String      | Тұтынушы профилінің идентификаторы                                                                      |
| ActivityId        | String      | Тұтынушы әрекетінің ішкі идентификаторы (негізгі кілт)                                       |
| SourceEntityName  | String      | Бастапқы нысан атауы                                                                |
| SourceActivityId  | String      | Бастапқы көздегі негізгі кілт                                                       |
| ActivityType      | String      | Семантикалық әрекет түрі немесе реттелетін әрекет атауы                                        |
| ActivityTimeStamp | DATETIME    | Әрекет уақыты белгісі                                                                      |
| Атау             | String      | Әрекеттің тақырыбы немесе атауы                                                               |
| Сипаттама       | String      | Әрекет сипаттамасы                                                                     |
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

| Column               | Түр        | Сипаттама                                          |
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
| SegmentProvider      | String       | Сегменттерді жариялайтын қолданба.      |
| SegmentMembershipType | String       | Осы сегмент мүшелігі жазбасы үшін тұтынушы түрі. Тұтынушы, Контакт немесе Тіркелгі сияқты бірнеше түрді қолдайды. Әдепкі: Тұтынушы  |
| Сегменттер       | JSON жолы  | Тұтынушы профилі мүшесі болып табылатын бірегей сегменттер тізімі      |
| msdynci_identifier  | String   | Сегмент мүшелігі жазбасының бірегей идентификаторы. `CustomerId|SegmentProvider|SegmentMembershipType|Name`  |
| msdynci_segmentmembershipid | GUID      | Детерминистік GUID жасалған`msdynci_identifier`          |


[!INCLUDE [footer-include](includes/footer-banner.md)]
