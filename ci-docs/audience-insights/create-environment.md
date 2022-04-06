---
title: Customer Insights бағдарламасында орталар жасау
description: Dynamics 365 Customer Insights бағдарламасы үшін лицензияланған жазылымы бар орта жасау қадамдары.
ms.date: 03/28/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.custom: intro-internal
searchScope:
- ci-home
- customerInsights
ms.openlocfilehash: a538237322615f69f0a5cb43d394275bf79af00b
ms.sourcegitcommit: ae02ac950810242e2505d7d371b80210dc8a0777
ms.translationtype: MT
ms.contentlocale: kk-KZ
ms.lasthandoff: 03/29/2022
ms.locfileid: "8491920"
---
# <a name="create-an-environment-in-audience-insights"></a>Аудитория туралы түсініктерде орта жасау

Бұл мақалада ұйымыңыз Dynamics 365 Customer Insights жазылымын сатып алғаннан кейін жаңа ортаны қалай құру керектігі түсіндірілген. 

Ұйымдар әрбір Customer Insights лицензиясы үшін *екі* орта жасай алады. Егер сіздің ұйымыңыз бірнеше лицензияны сатып алса, қолжетімді орталардың санын арттыру үшін [біздің қолдау көрсету тобымызға хабарласыңыз](https://go.microsoft.com/fwlink/?linkid=2079641). Сыйымдылығы мен қондырма сыйымдылығы туралы қосымша ақпарат алу үшін [Dynamics 365 лицензиялау бойынша нұсқаулығын](https://go.microsoft.com/fwlink/?LinkId=866544) жүктеп алыңыз.

> [!NOTE]
> Егер сіз қызметті пайдаланып көргіңіз келсе, [Сынақ ортасын орнату](../trial-signup.md) бөлімін қараңыз.

## <a name="create-a-new-environment"></a>Жаңа орта жасау

Customer Insights үшін жазылым лицензиясын сатып алғаннан кейін жаһандық әкімші Microsoft 365 жалға алушы оларды ортаны жасауға шақыратын электрондық хат алады. Жұмысты бастау үшін [https://home.ci.ai.dynamics.com/start](https://home.ci.ai.dynamics.com/start) веб-сайтына өтіңіз. 

Нұсқаулық тәжірибе сізге жаңа орта үшін барлық қажетті ақпаратты жинау қадамдары арқылы көмектеседі. Орта жасау немесе басқару үшін аудитория туралы түсініктерде [әкімші рұқсаттары](permissions.md) болуы керек.

1. Аудитория туралы түсініктерде ортаны таңдау құралын ашып, **+ Жаңа** параметрін таңдаңыз.
  
   :::image type="content" source="../engagement-insights/media/environment-picker.png" alt-text="Ортаны таңдау құралын таңдау.":::

1. Келесі бөлімдерде көрсетілген нұсқаулық тәжірибені басшылыққа алыңыз.

### <a name="step-1-provide-environment-information"></a>1-қадам: орта туралы ақпарат беру

**Негізгі ақпарат** қадамында ортаны басынан жасау керектігін немесе [басқа ортадан деректерді көшіру](manage-environments.md#copy-the-environment-configuration) керектігін таңдаңыз.

   :::image type="content" source="media/environment-settings-dialog.png" alt-text="Жаңа Customer Insights ортасын жасауға арналған диалогтік терезе.":::

Келесі мәліметтерді көрсетіңіз:
   - **Атауы**: осы ортаның атауы. Бар ортадан көшірсеңіз, бірақ оны өзгерте алмасаңыз, осы өріс толтырулы болады.
   - **Өз бизнесіңізді таңдау**: жаңа орта үшін негізгі аудиторияны таңдаңыз. Жеке тұтынушылармен (бизнес-тұтынушы) немесе [бизнес тіркелгілерімен](work-with-business-accounts.md) (бизнес-бизнес) жұмыс істей аласыз.
   - **Түрі**: жұмыс немесе сынақ данасы ортасын жасау керектігін таңдаңыз. Сынақ данасы орталары жоспарланған деректерді жаңартуға мүмкіндік бермейді және алдын ала ендіру мен сынақтан өткізуге арналған. Сынақ дана орталары қазіргі таңда таңдалған өндірістік орта ретінде сол негізгі аудиторияны пайдаланады.
   - **Аймақ**: қызмет орналастырылған аймақ.

### <a name="step-2-configure-data-storage"></a>2-қадам: деректерді сақтауды конфигурациялау

**Деректерді сақтау** қадамында аудитория туралы түсініктердегі деректерді қайда сақтау керектігін таңдаңыз.

Сізде екі опция болады: **Customer Insights сақтау орны** (Customer Insights тобы басқаратын Azure деректер көлі) және **Azure Data Lake Storage** (жеке Azure Data Lake Storage сақтау орны). Әдепкі бойынша Customer Insights сақтау орны параметрі таңдалады.

:::image type="content" source="media/data-storage-environment.png" alt-text="Аудитория туралы түсініктер ақпаратын сақтау үшін Azure Data Lake Storage қызметін таңдау.":::

Деректерді Azure Data Lake Storage қызметін сақтау арқылы сіз деректер сол Azure сақтау тіркелгісі үшін тиісті географиялық орынға көшірілетініне және сақталатынына келісесіз. Бұл орын Dynamics 365 Customer Insights бағдарламасындағы деректер сақталатын жерден өзгеше болуы мүмкін. Қосымша ақпарат алу үшін [Microsoft сенім орталығына](https://www.microsoft.com/trust-center) хабарласыңыз.

> [!NOTE]
> Customer Insights бағдарламасы қазіргі уақытта келесілерге қолдау көрсетеді:
> - Data Lake арқылы басқарылатын Microsoft Dataverse жүйесінде сақталатын Power BI деректер ағындарындағы қабылданған нысандар.  
> - Ортаны жасау кезінде таңдаған Azure аймағындағы Azure Data Lake Storage тіркелгілері.
> - Azure Data Lake Storage Gen2 және бар тіркелгілер *иерархиялық аттар кеңістігі* қосылған. Azure Data Lake Gen1 сақтау тіркелгілеріне қолдау көрсетілмейді.

Azure Data Lake Storage опциясы үшін ресурсқа негізделген опция мен аутентификацияға арналған жазылымға негізделген опция арасында таңдау жасай аласыз. Қосымша ақпарат алу үшін [Azure субъект-қызметі арқылы Azure Data Lake Storage тіркелгісіне қосылу ](connect-service-principal.md) тақырыбын қараңыз. **Контейнер** атауы `customerinsights` болады және өзгерту мүмкін емес.

Деректерді қабылдау сияқты жүйелік процестер аяқталған кезде, жүйе сіз көрсеткен сақтау тіркелгісінде тиісті қалталарды жасайды. Деректер файлдары мен *model.json* файлдары жасалады және процесс атауының негізінде қалталарға қосылады.

Егер сіз Customer Insights бірнеше ортасын жасасаңыз және сол орталардағы шығыс нысандарын сақтау тіркелгісінде сақтауды таңдасаңыз, Customer Insights бағдарламасы контейнерде әр орта үшін `ci_environmentID` параметрі бар бөлек қалталар жасайды.

### <a name="step-3-connect-to-microsoft-dataverse"></a>3‑қадам: Microsoft Dataverse жүйесіне қосылу
   
**Microsoft Dataverse** қадамы Customer Insights бағдарламасын Dataverse ортасымен байланыстыруға мүмкіндік береді.

Өзіңізді қамтамасыз етіңіз Microsoft Dataverse негізінде іскери қолданбалармен деректерді (профильдер мен түсініктерді) ортақ пайдалану ортасы Dataverse, Dynamics 365 Marketing немесе үлгіге негізделген қолданбалар сияқты Power Apps. Өзіңіздің өрісіңіз болмаса, бұл өрісті бос қалдырыңыз Dataverse ортасы және біз сізге біреуін қамтамасыз етеміз.

Сіздің Dataverse орта да мүмкіндік береді [көмегімен жергілікті деректер көздерінен деректерді қабылдау Power Platform деректер ағындары мен шлюздер](data-sources.md#add-data-from-on-premises-data-sources). Сіз де пайдалана аласыз [қораптан шыққан болжам үлгілері](predictions-overview.md?tabs=b2c#out-of-box-models) a-ға қосылу арқылы Dataverse қоршаған орта.

> [!IMPORTANT]
> 1. Тұтынушы түсініктері және Dataverse деректерді ортақ пайдалану үшін бір аймақта болуы керек.
> 1. Сізде жаһандық әкімші рөлі болуы керек Dataverse қоршаған орта. Бұл болса, тексеріңіз [Dataverse ортамен байланысты](/power-platform/admin/control-user-access#associate-a-security-group-with-a-dataverse-environment) белгілі бір қауіпсіздік топтарына және сол қауіпсіздік топтарына қосылғаныңызға көз жеткізіңіз.
> 1. Бұрыннан бар Customer Insights ортасы онымен байланысты емес Dataverse қоршаған орта. Қалай жасау керектігін біліңіз [бар қосылымды жою Dataverse қоршаған орта](manage-environments.md#remove-an-existing-connection-to-a-dataverse-environment).

:::image type="content" source="media/dataverse-provisioning.png" alt-text="деректермен алмасу Microsoft Dataverse таза жаңа даналары үшін автоматты түрде қосылған.":::

Деректерді ортақ пайдалануды қосу туралы қосымша ақпарат алу үшін Microsoft Dataverse өзіңнен Azure Data Lake Storage, қараңыз [Қосылу Microsoft Dataverse](manage-environments.md#connect-to-microsoft-dataverse).

Customer Insights бағдарламасы келесі деректерді бөлісу сценарийлеріне қолдау көрсетпейді.
- Егер Dataverse жүйесімен деректер бөлісу опциясын қоссаңыз, [нысанда болжалды немесе жетіспейтін мәндерді жасау мүмкін емес болады](predictions.md).

### <a name="step-4-finalize-the-settings"></a>4-қадам: параметрлерді аяқтау

**Қарап шығу** қадамында барлық көрсетілген параметрлерді қарап шығыңыз. Барлығы аяқталған кезде ортаны орнату үшін **Жасау** түймешігін таңдаңыз. 

Параметрлердің көпшілігін кейінірек өзгертуге болады. Қосымша ақпаратты [Орталарды басқару](manage-environments.md) бөлімінен қараңыз.

## <a name="work-with-your-new-environment"></a>Жаңа ортамен жұмыс істеу

Customer Insights сақтау орнын конфигурациялауды бастауға көмектесетін келесі мақалаларды қарап шығыңыз: 

- [Қосымша пайдаланушыларды қосу және рұқсаттарды тағайындау](permissions.md).
- [Деректер көздерін енгізіңіз](data-sources.md) және оларды арқылы өткізіңіз[ мәліметтерді біріздендіру процесі](data-unification.md) алу[ тұтынушылардың бірыңғай профильдері](customer-profiles.md).
- [Тұтынушылардың бірыңғай профильдерін арттыру](enrichment-hub.md) немесе [болжамды модельдерді іске қосу](predictions-overview.md).
- Тұтынушыларды топтастыру үшін [сегменттер](segments.md) және KPI көрсеткіштерін қарап шығу үшін [өлшемдер](measures.md) жасаңыз.
- Деректеріңіздің қосалқы жиындарын басқа бағдарламаларда өңдеу үшін [байланыстар](connections.md) мен [экспорттауларды](export-destinations.md) орнатыңыз.