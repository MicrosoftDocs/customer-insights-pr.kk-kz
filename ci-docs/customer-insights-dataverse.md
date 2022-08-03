---
title: Microsoft Dataverse жүйесіндегі Customer Insights деректерімен жұмыс істеу
description: Customer Insights және қосу жолын үйреніңіз Microsoft Dataverse және экспортталатын шығыс нысандарын түсіну Dataverse.
ms.date: 07/15/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 89ff629033230de3c6252b6a3a16816d9b3c1287
ms.sourcegitcommit: 85b198de71ff2916fee5500ed7c37c823c889bbb
ms.translationtype: MT
ms.contentlocale: kk-KZ
ms.lasthandoff: 07/15/2022
ms.locfileid: "9153411"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>Microsoft Dataverse жүйесіндегі Customer Insights деректерімен жұмыс істеу

Customer Insights шығыс нысандарын ретінде қолжетімді ету опциясын ұсынады [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro). Бұл интеграция төмен код/кодсыз тәсіл арқылы деректерді оңай бөлісуге және теңшелетін әзірлеуге мүмкіндік береді. The [шығару нысандары](#output-entities) а ішіндегі кестелер түрінде қол жетімді Dataverse қоршаған орта. Деректерді негізінде кез келген басқа қолданба үшін пайдалануға болады Dataverse кестелер. Бұл кестелер автоматтандырылған жұмыс процестері сияқты сценарийлерді қосады Power Automate немесе көмегімен қолданбалар құру Power Apps.

Сіздің Dataverse орта да мүмкіндік береді [көмегімен жергілікті деректер көздерінен деректерді қабылдау Power Platform деректер ағындары мен шлюздер](connect-power-query.md#add-data-from-on-premises-data-sources).

## <a name="prerequisites"></a>Алғышарттар

- Тұтынушы түсініктері және Dataverse орталар бір аймақта орналастырылуы керек.
- Сізде жаһандық әкімші рөлі болуы керек Dataverse қоршаған орта. Бұл болса, тексеріңіз [Dataverse ортамен байланысты](/power-platform/admin/control-user-access#associate-a-security-group-with-a-dataverse-environment) белгілі бір қауіпсіздік топтарына және сол қауіпсіздік топтарына қосылғаныңызға көз жеткізіңіз.
- Басқа Customer Insights ортасымен бұрыннан байланыстырылған жоқ Dataverse қосқыңыз келетін орта. Қалай жасау керектігін біліңіз [бар қосылымды жою Dataverse қоршаған орта](#remove-an-existing-connection-to-a-dataverse-environment).
- А Microsoft Dataverse орта тек бір сақтау тіркелгісіне қосыла алады. Ол ортаны конфигурациялағанда ғана қолданылады [өзіңіздің пайдаланыңыз Azure Data Lake Storage](own-data-lake-storage.md).

## <a name="dataverse-storage-capacity-entitlement"></a>Dataverse сақтау сыйымдылығы құқығы

Customer Insights жазылымы ұйымыңыздың бар қосымша мүмкіндіктеріне құқық береді [Dataverse сақтау сыйымдылығы](/power-platform/admin/capacity-storage). Қосылған сыйымдылық жазылым пайдаланатын профильдер санына байланысты.

**Мысал:**

Сіз 100 000 тұтынушы профиліне 15 ГБ дерекқор жады және 20 ГБ файл жады аласыз деп есептесеңіз. Жазылымыңызда 300 000 тұтынушы профилі болса, жалпы сақтау орныңыз 45 ГБ (3 x 15 ГБ) дерекқор жады және 60 ГБ файл жады (3 x 20 ГБ) болады. Сол сияқты, сізде 30K есептік жазбасы бар B2B жазылымыңыз болса, жалпы сақтау сыйымдылығыңыз 45 ГБ (3 x 15 ГБ) дерекқор жады және 60 ГБ файл жады (3 x 20 ГБ) болады.

Журнал сыйымдылығы ұйымыңыз үшін қосымша емес және бекітілген.

Толық сыйымдылық құқықтары туралы қосымша ақпаратты қараңыз [Dynamics 365 лицензиялау нұсқаулығы](https://go.microsoft.com/fwlink/?LinkId=866544).

## <a name="connect-a-dataverse-environment-to-customer-insights"></a>Қосылу а Dataverse Customer Insights үшін орта

The **Microsoft Dataverse** қадам Customer Insights мәліметтерін өзіңіздің деректеріңізбен байланыстыруға мүмкіндік береді Dataverse кезінде орта [Customer Insights ортасын жасау](create-environment.md).

:::image type="content" source="media/dataverse-provisioning.png" alt-text="деректермен алмасу Microsoft Dataverse ең жаңа орталар үшін автоматты түрде қосылған.":::

Әкімшілер Customer Insights параметрін барын қосу үшін теңшей алады Dataverse қоршаған орта. URL мекенжайын беру арқылы Dataverse ортада, ол олардың жаңа Customer Insights ортасына қосылуда. Customer Insights және арасындағы байланысты орнатқаннан кейін Dataverse, үшін ұйым атауын өзгертпеңіз Dataverse қоршаған орта. ұйымның атауы қолданылады Dataverse URL және өзгертілген атау Customer Insights байланысын үзеді.

Барын пайдаланғыңыз келмесе Dataverse ортада жүйе клиентіңіздегі Customer Insights деректері үшін жаңа орта жасайды. [Power Platform әкімшілер ортаны кім жасай алатынын басқара алады](/power-platform/admin/control-environment-creation). Жаңа Customer Insights ортасын орнатып жатқанда және әкімші оны жасауды өшірген Dataverse әкімшілерден басқа барлығына арналған орталарды пайдалансаңыз, жаңа орта жасай алмауыңыз мүмкін.

**Деректерді ортақ пайдалануды қосыңыз** бірге Dataverse деректерді ортақ пайдалану құсбелгісін таңдау арқылы.

Жеке Data Lake Storage тіркелгісін пайдаланып жатсаңыз, сізге де қажет **Рұқсаттар идентификаторы**. Рұқсат идентификаторын алу жолы туралы қосымша ақпарат алу үшін келесі бөлімді қараңыз.

## <a name="enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview"></a>Деректерді ортақ пайдалануды қосыңыз Dataverse өзіңнен Azure Data Lake Storage (Алдын ала қарау)

Деректерді ортақ пайдалануды қосу Microsoft Dataverse сіздің ортаңыз болғанда [өзіңізді пайдаланады Azure Data Lake Storage есептік жазба](own-data-lake-storage.md) қосымша конфигурация қажет. Customer Insights ортасын орнатқан пайдаланушыда кем дегенде болуы керек **Blob деректерін оқу құралы** бойынша рұқсаттар *CustomerInsights* ішіндегі контейнер Azure Data Lake Storage есептік жазба.

1. Azure жазылымында екі қауіпсіздік тобын жасаңыз - біреуі **Оқырман** қауіпсіздік тобы және біреуі **Қатысушы** қауіпсіздік тобын орнатыңыз Microsoft Dataverse екі қауіпсіздік тобының иесі ретінде қызмет көрсету.
2. Осы қауіпсіздік топтары арқылы сақтау тіркелгіңіздегі CustomerInsights контейнеріндегі қатынасты басқару тізімін (ACL) басқарыңыз. қосыңыз Microsoft Dataverse қызмет көрсету және кез келген Dataverse Dynamics 365 Marketing сияқты бизнес қолданбаларына негізделген **Оқырман** қауіпсіздік тобы бар **тек оқуға арналған** рұқсаттар. қосу *тек* Customers Insights қолданбасы **Қатысушы** екеуін де беру үшін қауіпсіздік тобы **оқу және жазу** профильдер мен түсініктерді жазу рұқсаттары.

### <a name="limitations"></a>Шектеулер

Қолдану кезінде екі шектеу бар Dataverse өзіңмен Azure Data Lake Storage тіркелгі:

- A арасында бір-бірден салыстыру бар Dataverse ұйымдастыру және а Azure Data Lake Storage есептік жазба. Бір рет а Dataverse ұйым сақтау тіркелгісіне қосылған болса, ол басқа сақтау тіркелгісіне қосыла алмайды. Бұл шектеу а Dataverse бірнеше сақтау есептік жазбаларын толтырмайды.
- Azure Private Link параметріне кіру үшін қажет болса, деректерді ортақ пайдалану жұмыс істемейді Azure Data Lake Storage тіркелгі, себебі ол брандмауэрдің артында. Dataverse қазіргі уақытта Жеке сілтеме арқылы жеке соңғы нүктелерге қосылуды қолдамайды.

### <a name="set-up-powershell"></a>PowerShell орнату

PowerShell сценарийлерін орындау үшін алдымен PowerShell бағдарламасын сәйкесінше орнату керек.

1. соңғы нұсқасын орнатыңыз [Azure Active Directory Графикке арналған PowerShell](/powershell/azure/active-directory/install-adv2).
   1. Компьютерде пернетақтадағы Windows пернесін таңдап, **Windows PowerShell** іздеп, **Әкімші ретінде іске қосу** опциясын таңдаңыз.
   1. Ашылатын PowerShell терезесінде `Install-Module AzureAD` енгізіңіз.
2. Үш модульді импорттау.
    1. PowerShell терезесінде енгізіңіз`Install-Module -Name Az.Accounts` және қадамдарды орындаңыз.
    1. үшін қайталаңыз`Install-Module -Name Az.Resources` және `Install-Module -Name Az.Storage`.

### <a name="configuration-steps"></a>Конфигурация қадамдары

1. Біздің инженерден іске қосу үшін қажет екі PowerShell сценарийін жүктеп алыңыз [GitHub репо](https://github.com/trin-msft/byol).
    1. `CreateSecurityGroups.ps1`
       - Сізге керек *жалға алушы әкімшісі* осы PowerShell сценарийін іске қосу рұқсаттары.
       - Бұл PowerShell сценарийі Azure жазылымында екі қауіпсіздік тобын жасайды. Біреуі Оқырман тобына, екіншісі Қатысушы тобына және жасайды Microsoft Dataverse осы қауіпсіздік топтарының екеуінің де иесі ретінде қызмет көрсету.
       - Бұл PowerShell сценарийін Windows PowerShell жүйесінде сіздің Azure жазылым идентификаторын қамтамасыз ету арқылы орындаңыз Azure Data Lake Storage. Қосымша ақпаратты және орындалған логиканы қарап шығу үшін PowerShell сценарийін өңдегіште ашыңыз.
       - Осы сценарий арқылы жасалған екі қауіпсіздік тобының идентификаторы мәндерін сақтаңыз, себебі біз оларды файлда қолданамыз`ByolSetup.ps1` сценарий.

        > [!NOTE]
        > Қауіпсіздік тобын жасауды жалға алушыда өшіруге болады. Бұл жағдайда қолмен орнату қажет болады және сіздің Azure AD админ керек еді [қауіпсіздік тобын құруды қосыңыз](/azure/active-directory/enterprise-users/groups-self-service-management).

    2. `ByolSetup.ps1`
        - Сізге керек *Storage Blob деректерінің иесі* осы сценарийді іске қосу үшін сақтау тіркелгісі/контейнер деңгейіндегі рұқсаттар немесе осы сценарий сіз үшін біреуін жасайды. Сценарий сәтті іске қосылғаннан кейін рөл тағайындауыңызды қолмен жоюға болады.
        - Бұл PowerShell сценарийі үшін қажетті рөлге негізделген қатынасты басқаруды қосады Microsoft Dataverse қызмет көрсету және кез келген Dataverse -негізделген іскерлік қолданбалар. Ол сондай-ақ CustomerInsights контейнеріндегі қол жеткізуді басқару тізімін (ACL) келесімен жасалған қауіпсіздік топтары үшін жаңартады.`CreateSecurityGroups.ps1` сценарий. Contributor тобында болады *rwx* рұқсат және Оқырмандар тобы болады *rx* тек рұқсат.
        - Бұл PowerShell сценарийін Windows PowerShell жүйесінде сіздің Azure жазылымының идентификаторын қамтамасыз ету арқылы орындаңыз Azure Data Lake Storage, сақтау тіркелгісінің атауы, ресурс тобының атауы және Reader және Contributor қауіпсіздік тобының идентификаторы мәндері. Қосымша ақпаратты және орындалған логиканы қарап шығу үшін PowerShell сценарийін өңдегіште ашыңыз.
        - Сценарийді сәтті іске қосқаннан кейін шығыс жолын көшіріңіз. Шығару жолы келесідей көрінеді:`https://DVBYODLDemo/customerinsights?rg=285f5727-a2ae-4afd-9549-64343a0gbabc&cg=720d2dae-4ac8-59f8-9e96-2fa675dbdabc`

2. Жоғарыдан көшірілген шығыс жолын енгізіңіз **Рұқсаттар идентификаторы** үшін ортаны конфигурациялау қадамының өрісі Microsoft Dataverse.

:::image type="content" source="media/dataverse-enable-datasharing-BYODL.png" alt-text="Деректерді ортақ пайдалануды қосу үшін конфигурация опциялары Azure Data Lake Storage бірге Microsoft Dataverse .":::

### <a name="remove-an-existing-connection-to-a-dataverse-environment"></a>A үшін бар қосылымды жойыңыз Dataverse қоршаған орта

a-ға қосылғанда Dataverse орта, қате туралы хабар **Бұл CDS ұйымы басқа Customer Insights данасына тіркелген** дегенді білдіреді Dataverse орта Customer Insights ортасында бұрыннан пайдаланылады. Қолданыстағы қосылымды жаһандық әкімші ретінде жоюға болады Dataverse қоршаған орта. Өзгерістерді толтыру үшін бірнеше сағат кетуі мүмкін.

1. [Power Apps](https://make.powerapps.com) торабына өтіңіз.
1. Ортаны таңдау құралынан ортаны таңдаңыз.
1. Бару **Шешімдер**
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
| SegmentProvider      | String       | Сегменттерді жариялайтын қолданба.      |
| SegmentMembershipType | String       | Осы сегменттің мүшелік жазбасының тұтынушы түрі. Тұтынушы, Контакт немесе Тіркелгі сияқты бірнеше түрді қолдайды. Әдепкі: Тұтынушы  |
| Сегменттер       | JSON жолы  | Тұтынушы профилі мүшесі болып табылатын бірегей сегменттер тізімі      |
| msdynci_identifier  | String   | Сегмент мүшелігі жазбасының бірегей идентификаторы. `CustomerId|SegmentProvider|SegmentMembershipType|Name`  |
| msdynci_segmentmembershipid | GUID      | Детерминистік GUID жасалған`msdynci_identifier`          |

<!--
## FAQ: Update existing environments to use Microsoft Dataverse

Between mid-May 2022 and June 13, 2022, administrators can update the environment settings with a Dataverse environment that Customer Insights can use. On June 13, 2022, your environment will be updated automatically and we'll create a Dataverse environment on your tenant for you.

1. My environment uses my own Azure Data Lake Storage account. Do I still need to update?

   If there's already a Dataverse environment configured in your environment, the update isn't required. If no Dataverse is environment configured, the **Update now** button will create a Dataverse environment and update from the Customer Insights database to a Dataverse database.

1. Will we get extra Dataverse capacity, or will the update use my existing Dataverse capacity?

   - If there's already a Dataverse environment configured in your Customer Insights environment, or connected with other Dynamics 365 or Power Apps applications, the capacity remains unchanged.
   - If the Dataverse environment is new, it will add new storage and database capacity. The capacity added varies per environment and entitlements. You'll get 3 GB for trial and sandbox environment. Production environments get 15 GB.

1. I proceeded with the update and it seems like nothing happened. Is the update complete?

   If the notification in Customer Insights doesn't show anymore, the update is complete. You can check the status of the update by reviewing your environment settings.

1. Why do I still see the banner after completing the update steps?

   It can happen due to an upgrade or refresh failure. Contact support.

1. I received a "Failed to provision Dataverse environment" error after starting the update. What happened?

   It can happen due to an upgrade or refresh failure. Contact support.
   Common causes:
    - Insufficient capacity. There's no more capacity to create more environments. For more information, see [Manage capacity action](/power-platform/admin/capacity-storage#actions-to-take-for-a-storage-capacity-deficit).
    - Region mismatch between tenant region and Customer Insights environment region in the Australia and India regions.
    - Insufficient privileges to provision Dataverse. The users starting the update needs a Dynamics 365 admin role.
    - -->
