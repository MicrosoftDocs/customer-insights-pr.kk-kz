---
title: Орталарды жасау және басқару
description: Қызметке қалай тіркелуге болатынын және орталарды басқару әдісі туралы мәлімет алыңыз.
ms.date: 06/15/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: 904ce68336cba4b7a4d5a37692b72d091400559d
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304887"
---
# <a name="manage-environments"></a><span data-ttu-id="d3594-103">Орталарды басқару</span><span class="sxs-lookup"><span data-stu-id="d3594-103">Manage environments</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="d3594-104">Бұл мақала жаңа ұйымды қалай құру керектігін және қоршаған ортаны қалай қамтамасыз ету керектігін түсіндіреді.</span><span class="sxs-lookup"><span data-stu-id="d3594-104">This article explains how to create a new organization and how to provision an environment.</span></span>

## <a name="sign-up-and-create-an-organization"></a><span data-ttu-id="d3594-105">Ұйымды тіркеу, жасау</span><span class="sxs-lookup"><span data-stu-id="d3594-105">Sign up and create an organization</span></span>

1. <span data-ttu-id="d3594-106">[Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/) веб-сайтына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="d3594-106">Go to the [Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/) website.</span></span>

2. <span data-ttu-id="d3594-107">**Жұмысты бастау** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="d3594-107">Select **Get Started**.</span></span>

3. <span data-ttu-id="d3594-108">Қажетті тіркелу сценарийін таңдап, сәйкес сілтемені таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="d3594-108">Choose your preferred sign-up scenario and select the corresponding link.</span></span>

4. <span data-ttu-id="d3594-109">Шарттар мен талаптарды қабылдап, ұйым жасауды бастау үшін **Жалғастыру** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="d3594-109">Accept the terms and conditions and select **Continue** to start creating the organization.</span></span>

5. <span data-ttu-id="d3594-110">Орта жасалғаннан кейін, [Customer Insights](https://home.ci.ai.dynamics.com) тармағына қайта бағытталасыз.</span><span class="sxs-lookup"><span data-stu-id="d3594-110">After the environment is created, you'll be redirected to [Customer Insights](https://home.ci.ai.dynamics.com).</span></span>

6. <span data-ttu-id="d3594-111">Қолданбаны зерттеу үшін демо орталарды пайдаланыңыз немесе келесі бөлімдегі қадамдарды орындау арқылы жаңа орта жасаңыз.</span><span class="sxs-lookup"><span data-stu-id="d3594-111">Use the demo environment to explore the app, or create a new environment by following the steps in the next section.</span></span>

7. <span data-ttu-id="d3594-112">Орта параметрлерін көрсеткеннен кейін **Жасау** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="d3594-112">After specifying the environment settings, select **Create**.</span></span>

8. <span data-ttu-id="d3594-113">Жүйеге орта сәтті жасалғаннан кейін кіресіз.</span><span class="sxs-lookup"><span data-stu-id="d3594-113">You'll be signed in after the environment was created successfully.</span></span>

## <a name="create-an-environment-in-an-existing-organization"></a><span data-ttu-id="d3594-114">Бұрыннан бар ұйымда орта жасау</span><span class="sxs-lookup"><span data-stu-id="d3594-114">Create an environment in an existing organization</span></span>

<span data-ttu-id="d3594-115">Жаңа ортаны жасаудың екі жолы бар.</span><span class="sxs-lookup"><span data-stu-id="d3594-115">There are two ways to create a new environment.</span></span> <span data-ttu-id="d3594-116">Толығымен жаңа конфигурацияны көрсетуге немесе бар ортадан кейбір конфигурация параметрлерін көшіруге болады.</span><span class="sxs-lookup"><span data-stu-id="d3594-116">You can either specify an entirely new configuration, or you can copy some configuration settings from an existing environment.</span></span>

> [!NOTE]
> <span data-ttu-id="d3594-117">Ұйымдар әрбір Customer Insights лицензиясы үшін *екі* орта жасай алады.</span><span class="sxs-lookup"><span data-stu-id="d3594-117">Organizations can create *two* environments for every Customer Insights license.</span></span> <span data-ttu-id="d3594-118">Егер сіздің ұйымыңыз бірнеше лицензия сатып алса, қолжетімді орталардың санын арттыру үшін [біздің қолдау көрсету тобымызға хабарласыңыз](https://go.microsoft.com/fwlink/?linkid=2079641).</span><span class="sxs-lookup"><span data-stu-id="d3594-118">If your organization purchases more than once license, please [contact our support team](https://go.microsoft.com/fwlink/?linkid=2079641) to increase the number of available environments.</span></span> <span data-ttu-id="d3594-119">Сыйымдылық және қондырма сыйымдылығы туралы қосымша ақпарат алу үшін [Dynamics 365 лицензиялау нұсқаулығы](https://go.microsoft.com/fwlink/?LinkId=866544) құжатын жүктеп алыңыз.</span><span class="sxs-lookup"><span data-stu-id="d3594-119">For more information about capacity and add-on capacity, download [Dynamics 365 licensing guide](https://go.microsoft.com/fwlink/?LinkId=866544).</span></span>

<span data-ttu-id="d3594-120">Орта жасау үшін:</span><span class="sxs-lookup"><span data-stu-id="d3594-120">To create an environment:</span></span>

1. <span data-ttu-id="d3594-121">Бағдарлама тақырыбында **Орта** таңдау құралын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="d3594-121">Select the **Environment** picker in the header of the app.</span></span>

1. <span data-ttu-id="d3594-122">**Жаңа** пәрменін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="d3594-122">Select **New**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="d3594-123">![Орта параметрлері.](media/environment-settings-dialog.png)</span><span class="sxs-lookup"><span data-stu-id="d3594-123">![Environment settings.](media/environment-settings-dialog.png)</span></span>

1. <span data-ttu-id="d3594-124">**Орта жасау** диалогтік терезесінде **Жаңа орта** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="d3594-124">In the **Create an environment** dialog, select **New environment**.</span></span>

   <span data-ttu-id="d3594-125">Егер [ағымдағы ортадан деректерді көшіру](#considerations-for-copy-configuration-preview) қажет болса, **Бұрыннан бар ортадан көшіру** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="d3594-125">If you want to [copy data from the current environment](#considerations-for-copy-configuration-preview), select **Copy from existing environment**.</span></span> <span data-ttu-id="d3594-126">Деректерді көшіруге болатын ұйымда барлық қолжетімді орталар тізімін көресіз.</span><span class="sxs-lookup"><span data-stu-id="d3594-126">You'll see a list of all available environments in your organization where you can copy data from.</span></span>

1. <span data-ttu-id="d3594-127">Келесі мәліметтерді көрсетіңіз:</span><span class="sxs-lookup"><span data-stu-id="d3594-127">Provide the following details:</span></span>
   - <span data-ttu-id="d3594-128">**Атауы**: осы ортаның атауы.</span><span class="sxs-lookup"><span data-stu-id="d3594-128">**Name**: The name for this environment.</span></span> <span data-ttu-id="d3594-129">Бар ортадан көшірсеңіз, бірақ оны өзгерте алмасаңыз, осы өріс толтырулы болады.</span><span class="sxs-lookup"><span data-stu-id="d3594-129">This field is already filled in if you've copied an existing environment, but you can change it.</span></span>
   - <span data-ttu-id="d3594-130">**Түрі**: жұмыс немесе сынақ данасы ортасын жасау керектігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="d3594-130">**Type**: Select whether you want to create a Production or Sandbox environment.</span></span>
   - <span data-ttu-id="d3594-131">**Аймақ**: қызмет орналастырылған аймақ.</span><span class="sxs-lookup"><span data-stu-id="d3594-131">**Region**: The region into which the service is deployed and hosted.</span></span>
   
1. <span data-ttu-id="d3594-132">Қажет болса, **Қосымша параметрлер** опциясын таңдауға болады:</span><span class="sxs-lookup"><span data-stu-id="d3594-132">Optionally, you can select **Advanced settings**:</span></span>

   - <span data-ttu-id="d3594-133">**Барлық деректерді сақтау орны**: Customer Insights бағдарламасынан құрылған шығыс деректерін сақтау орнын көрсетеді.</span><span class="sxs-lookup"><span data-stu-id="d3594-133">**Save all data to**: Specifies where you want to store the output data generated from Customer Insights.</span></span> <span data-ttu-id="d3594-134">Сізде екі опция болады: **Customer Insights сақтау орны** (Customer Insights тобы басқаратын Azure Data Lake) және **Azure Data Lake Storage** (жеке Azure Data Lake Storage).</span><span class="sxs-lookup"><span data-stu-id="d3594-134">You'll have two options: **Customer Insights storage** (an Azure Data Lake managed by the Customer Insights team) and **Azure Data Lake Storage** (your own Azure Data Lake Storage).</span></span> <span data-ttu-id="d3594-135">Әдепкі бойынша Customer Insights сақтау орны параметрі таңдалады.</span><span class="sxs-lookup"><span data-stu-id="d3594-135">By default, the Customer Insights storage option is selected.</span></span>

     > [!NOTE]
     > <span data-ttu-id="d3594-136">Деректерд Azure Data Lake Storage сақтау орнында сақтау арқылы , деректердің сол Azure сақтау орнының тіркелгісі үшін тиісті географиялық орынға тасымалданып және сақталатындығына келісім бересіз және ол Dynamics 365 Customer Insights бағдарламасында сақталған орнынан бөлек болуы мүмкін.</span><span class="sxs-lookup"><span data-stu-id="d3594-136">By saving data to Azure Data Lake Storage, you agree that data will be transferred to and stored in the appropriate geographic location for that Azure storage account, which may differ from where data is stored in Dynamics 365 Customer Insights.</span></span> [<span data-ttu-id="d3594-137">Microsoft сенім орталығы туралы қосымша ақпарат.</span><span class="sxs-lookup"><span data-stu-id="d3594-137">Learn more at the Microsoft Trust Center.</span></span>](https://www.microsoft.com/trust-center)
     >
     > <span data-ttu-id="d3594-138">Ағымдағы уақытта қабылданбаған нысандар әрдайым Customer Insights бағдарламасы арқылы басқарылатын Data Lake ішінде сақталады.</span><span class="sxs-lookup"><span data-stu-id="d3594-138">Currently, ingested entities are always stored in the Customer Insights Managed Data Lake.</span></span> 
     > 
     > <span data-ttu-id="d3594-139">Біз тек ортаны жасау кезінде таңдалған бірдей Azure аймағындағы Azure Data Lake Storage тіркелгілеріне қолдау көрсетеміз.</span><span class="sxs-lookup"><span data-stu-id="d3594-139">We support only Azure Data Lake Storage accounts from the same Azure region you selected when creating the environment.</span></span> 
     > 
     > <span data-ttu-id="d3594-140">Біз тек иерархиялық атау кеңістігі қосылған Azure Data Lake Storage тіркелгілеріне қолдау көрсетеміз.</span><span class="sxs-lookup"><span data-stu-id="d3594-140">We support only Azure Data Lake Storage accounts that have hierarchical namespace enabled.</span></span>


   - <span data-ttu-id="d3594-141">Azure Data Lake Storage опциясы үшін ресурсқа негізделген опция мен аутентификацияға арналған жазылымға негізделген опция арасында таңдау жасай аласыз.</span><span class="sxs-lookup"><span data-stu-id="d3594-141">For the Azure Data Lake Storage option, you can choose between a resource-based option and a subscription-based option for authentication.</span></span> <span data-ttu-id="d3594-142">Қосымша ақпарат алу үшін [Аудитория мәліметтерін Azure субъект-қызметімен Azure Data Lake Storage Gen2 тіркелгісіне қосу](connect-service-principal.md) бөлімін қараңыз.</span><span class="sxs-lookup"><span data-stu-id="d3594-142">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="d3594-143">**Контейнер** атауын өзгерту мүмкін емес және ол `customerinsights` болады.</span><span class="sxs-lookup"><span data-stu-id="d3594-143">The **Container** name can't be changed and will be `customerinsights`.</span></span>
   
   - <span data-ttu-id="d3594-144">Егер [болжамдарды](predictions.md) пайдалану, Microsoft Dataverse бағдарламасымен деректер бөлісуді конфигурациялау немесе жергілікті деректер көздерінен деректерді қабылдауды қосу керек болса, Microsoft Dataverse ортасының URL мекенжайын **Microsoft Dataverse бағдарламасымен деректер бөлісуді конфигурациялау және қосымша мүмкіндіктерді қосу** бөлімінде қамтамасыз етіңіз.</span><span class="sxs-lookup"><span data-stu-id="d3594-144">If you want to use [predictions](predictions.md), configure data sharing with Microsoft Dataverse, or enable data ingestion from on-premises data sources, provide the Microsoft Dataverse environment URL under **Configure data sharing with Microsoft Dataverse and enable additional capabilities**.</span></span> <span data-ttu-id="d3594-145">Customer Insights шығыс деректерін Microsoft Dataverse басқарылатын Data Lake қызметімен ортақ пайдалану үшін **Деректерді бөлісуді қосу** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="d3594-145">Select **Enable data sharing** to share Customer Insights output data with a Microsoft Dataverse Managed Data Lake.</span></span>

     > [!NOTE]
     > - <span data-ttu-id="d3594-146">Барлық деректерді өз Azure Data Lake Storage қызметіңізге сақтағанда Microsoft Dataverse басқарылатын Data Lake қызметімен деректерді бөлісуге ағымдағы уақытта қолдау көрсетілмейді.</span><span class="sxs-lookup"><span data-stu-id="d3594-146">Data sharing with Microsoft Dataverse Managed Data Lake is currently not supported when you save all data to your own Azure Data Lake Storage.</span></span>
     > - <span data-ttu-id="d3594-147">Microsoft Dataverse басқарылатын Data Lake қызметімен деректерді бөлісуді қосқанда [нысанда жоқ мәндер болжамына](predictions.md) ағымдағы уақытта қолдау көрсетілмейді.</span><span class="sxs-lookup"><span data-stu-id="d3594-147">[Prediction of missing values in an entity](predictions.md) is not currently supported when you enable data sharing with Microsoft Dataverse Managed Data Lake.</span></span>

     > [!div class="mx-imgBorder"]
     > <span data-ttu-id="d3594-148">![Microsoft Dataverse бағдарламасымен деректер бөлісуді қосуға арналған конфигурация опциялары.](media/datasharing-with-DataverseMDL.png)</span><span class="sxs-lookup"><span data-stu-id="d3594-148">![Configuration options to enable data sharing with Microsoft Dataverse.](media/datasharing-with-DataverseMDL.png)</span></span>

   <span data-ttu-id="d3594-149">Деректерді қабылдау немесе сегмент құру сияқты процестерді іске қосқан кезде, жоғарыда көрсеткен сақтау тіркелгісінде сәйкес қалталар жасалады.</span><span class="sxs-lookup"><span data-stu-id="d3594-149">When you run processes, such as data ingestion or segment creation, corresponding folders will be created in the storage account you specified above.</span></span> <span data-ttu-id="d3594-150">Деректер файлдары және model.json файлдары жасалады және процесс атауына негізделген қалталарға қосылады.</span><span class="sxs-lookup"><span data-stu-id="d3594-150">Data files and model.json files will be created and added to folders based on the process name.</span></span>

   <span data-ttu-id="d3594-151">Customer Insights жүйесінің бірнеше ортасын жасасаңыз және шығыс нысандарын осы орталардан сақтау тіркелгісінде сақтауды таңдасаңыз, ci_<environmentid> контейнерінде әр орта үшін бөлек қалталар жасалады.</span><span class="sxs-lookup"><span data-stu-id="d3594-151">If you create multiple environments of Customer Insights and choose to save the output entities from those environments in your storage account, separate folders will be created for each environment with ci_<environmentid> in the container.</span></span>

### <a name="considerations-for-copy-configuration-preview"></a><span data-ttu-id="d3594-152">Конфигурацияны көшіруге қатысты мәселелер (алдын ала қарау нұсқасы)</span><span class="sxs-lookup"><span data-stu-id="d3594-152">Considerations for copy configuration (preview)</span></span>

<span data-ttu-id="d3594-153">Мына конфигурация параметрлері көшіріледі:</span><span class="sxs-lookup"><span data-stu-id="d3594-153">The following configuration settings are copied:</span></span>

- <span data-ttu-id="d3594-154">Мүмкіндік конфигурациялары</span><span class="sxs-lookup"><span data-stu-id="d3594-154">Feature configurations</span></span>
- <span data-ttu-id="d3594-155">Қабылданған/импортталған деректер көздері</span><span class="sxs-lookup"><span data-stu-id="d3594-155">Ingested/imported data sources</span></span>
- <span data-ttu-id="d3594-156">Деректерді біріктіру (салыстыру, сәйкестендіру, біріктіру) конфигурациясы</span><span class="sxs-lookup"><span data-stu-id="d3594-156">Data unification (Map, Match, Merge) configuration</span></span>
- <span data-ttu-id="d3594-157">Сегменттер</span><span class="sxs-lookup"><span data-stu-id="d3594-157">Segments</span></span>
- <span data-ttu-id="d3594-158">Өлшемдер</span><span class="sxs-lookup"><span data-stu-id="d3594-158">Measures</span></span>
- <span data-ttu-id="d3594-159">Қатынастар</span><span class="sxs-lookup"><span data-stu-id="d3594-159">Relationships</span></span>
- <span data-ttu-id="d3594-160">Әрекеттер</span><span class="sxs-lookup"><span data-stu-id="d3594-160">Activities</span></span>
- <span data-ttu-id="d3594-161">Іздеу және сүзгілеу индексі</span><span class="sxs-lookup"><span data-stu-id="d3594-161">Search & filter Index</span></span>
- <span data-ttu-id="d3594-162">Мақсатты орындарды экспорттау</span><span class="sxs-lookup"><span data-stu-id="d3594-162">Export destinations</span></span>
- <span data-ttu-id="d3594-163">Жоспарланған жаңарту</span><span class="sxs-lookup"><span data-stu-id="d3594-163">Scheduled refresh</span></span>
- <span data-ttu-id="d3594-164">Арттырулар</span><span class="sxs-lookup"><span data-stu-id="d3594-164">Enrichments</span></span>
- <span data-ttu-id="d3594-165">Үлгіні басқару</span><span class="sxs-lookup"><span data-stu-id="d3594-165">Model management</span></span>
- <span data-ttu-id="d3594-166">Рөл тағайындаулары</span><span class="sxs-lookup"><span data-stu-id="d3594-166">Role assignments</span></span>

<span data-ttu-id="d3594-167">Мына конфигурация параметрлері *көшірілмейді*:</span><span class="sxs-lookup"><span data-stu-id="d3594-167">The following settings are *not* copied:</span></span>

- <span data-ttu-id="d3594-168">Тұтынушы профильдері.</span><span class="sxs-lookup"><span data-stu-id="d3594-168">Customer profiles.</span></span>
- <span data-ttu-id="d3594-169">Дереккөз деректемелері.</span><span class="sxs-lookup"><span data-stu-id="d3594-169">Data source credentials.</span></span> <span data-ttu-id="d3594-170">Әрбір дереккөз деректемелерін қамтамасыз етесіз және дереккөздерді қолмен жаңартасыз.</span><span class="sxs-lookup"><span data-stu-id="d3594-170">You'll have to provide the credentials for every data source and refresh the data sources manually.</span></span>
- <span data-ttu-id="d3594-171">Common Data Model қалтасындағы және Dataverse жүйесі арқылы басқарылатын Data Lake қызметіндегі деректер көздері.</span><span class="sxs-lookup"><span data-stu-id="d3594-171">Data sources from Common Data Model folder and Dataverse managed Data Lake.</span></span> <span data-ttu-id="d3594-172">Осы дереккөздерді бастапқы ортадағымен бірдей атпен қолмен жасай аласыз.</span><span class="sxs-lookup"><span data-stu-id="d3594-172">You'll have to create those data sources manually with the same name as in the source environment.</span></span>

<span data-ttu-id="d3594-173">Ортаны көшірген кезде жаңа орта жасалған растау туралы хабарды көресіз.</span><span class="sxs-lookup"><span data-stu-id="d3594-173">When you copy an environment, you'll see a confirmation message that the new environment has been created.</span></span> <span data-ttu-id="d3594-174">Дереккөздер тізімін көру үшін **Дереккөздерге өту** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="d3594-174">Select **Go to data sources** to see the list of data sources.</span></span>

<span data-ttu-id="d3594-175">Барлық дереккөздер **Қажетті деректемелер** күйін көрсетеді.</span><span class="sxs-lookup"><span data-stu-id="d3594-175">All the data sources will show a **Credentials Required** status.</span></span> <span data-ttu-id="d3594-176">Дереккөздерді өңдеп, оларды жаңарту үшін деректемелерді енгізіңіз.</span><span class="sxs-lookup"><span data-stu-id="d3594-176">Edit the data sources and enter the credentials to refresh them.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="d3594-177">![Деректер көздері көшірілді.](media/data-sources-copied.png)</span><span class="sxs-lookup"><span data-stu-id="d3594-177">![Data sources copied.](media/data-sources-copied.png)</span></span>

<span data-ttu-id="d3594-178">Деректер көздерін жаңартқан соң, **Деректер** > **Біріктіру** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="d3594-178">After refreshing the data sources, go to **Data** > **Unify**.</span></span> <span data-ttu-id="d3594-179">Мұнда көз ортасынан параметрлерді таба аласыз.</span><span class="sxs-lookup"><span data-stu-id="d3594-179">Here you'll find settings from the source environment.</span></span> <span data-ttu-id="d3594-180">Оларды қажетінше өңдеңіз немесе біріктіру процесін бастау үшін **Іске қосу** параметрін таңдап, бірыңғай тұтынушы нысанын жасаңыз.</span><span class="sxs-lookup"><span data-stu-id="d3594-180">Edit them as needed or select **Run** to start the data unification process and create the unified customer entity.</span></span>

<span data-ttu-id="d3594-181">Деректерді біріктіру аяқталған кезде оларды да жаңарту үшін **Шаралар** және **Сегменттер** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="d3594-181">When the data unification is complete, go to **Measures** and **Segments** to refresh them too.</span></span>

## <a name="edit-an-existing-environment"></a><span data-ttu-id="d3594-182">Бұрыннан бар ортаны өңдеу</span><span class="sxs-lookup"><span data-stu-id="d3594-182">Edit an existing environment</span></span>

<span data-ttu-id="d3594-183">Бұрыннан бар орталардың кейбір мәліметтерін өңдеуге болады.</span><span class="sxs-lookup"><span data-stu-id="d3594-183">You can edit some of the details of existing environments.</span></span>

1.  <span data-ttu-id="d3594-184">Бағдарлама тақырыбында **Орта** таңдау құралын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="d3594-184">Select the **Environment** picker in the header of the app.</span></span>

2.  <span data-ttu-id="d3594-185">**Өңдеу** белгішесін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="d3594-185">Select the **Edit** icon.</span></span>

3. <span data-ttu-id="d3594-186">**Ортаны өңдеу** терезесінде ортаның **көрсетілетін атауы** өрісін жаңартуға болады, бірақ **Аймақ** немесе **Түрі** өрістерін өзгерту мүмкін емес.</span><span class="sxs-lookup"><span data-stu-id="d3594-186">In the **Edit environment** box, you can update the environment's **Display name**, but you can't change the **Region** or **Type**.</span></span>

4. <span data-ttu-id="d3594-187">Егер орта деректерді Azure Data Lake Storage қызметінде сақтау үшін конфигурацияланса, **Тіркелгі кілті** параметрін жаңартуға болады.</span><span class="sxs-lookup"><span data-stu-id="d3594-187">If an environment is configured to store data in Azure Data Lake Storage, you can update the **Account key**.</span></span> <span data-ttu-id="d3594-188">Дегенмен, **Тіркелгі атын** немесе **Контейнер** атын өзгерте алмайсыз.</span><span class="sxs-lookup"><span data-stu-id="d3594-188">However, you can't change the **Account name** or **Container** name.</span></span>

5. <span data-ttu-id="d3594-189">Оған қоса, тіркелгі кілтіне негізделген қосылымынан ресурстарға немесе жазылымға негізделген қосылымға жаңартуға болады.</span><span class="sxs-lookup"><span data-stu-id="d3594-189">Optionally, you can update from an account key-based connection to a resource-based or subscription-based connection.</span></span> <span data-ttu-id="d3594-190">Жаңартылып біткенде жаңартудан кейін тіркелгі кілтіне оралу мүмкін емес.</span><span class="sxs-lookup"><span data-stu-id="d3594-190">Once upgraded, you cannot revert to account key after the update.</span></span> <span data-ttu-id="d3594-191">Қосымша ақпарат алу үшін [Аудитория мәліметтерін Azure субъект-қызметімен Azure Data Lake Storage Gen2 тіркелгісіне қосу](connect-service-principal.md) бөлімін қараңыз.</span><span class="sxs-lookup"><span data-stu-id="d3594-191">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="d3594-192">Байланысты жаңарту кезінде **Контейнер** ақпаратын өзгерту мүмкін емес.</span><span class="sxs-lookup"><span data-stu-id="d3594-192">You can't change **Container** information when updating the connection.</span></span>

6. <span data-ttu-id="d3594-193">Қажет болса, Microsoft Dataverse ортасының URL мекенжайын **Microsoft Dataverse бағдарламасымен деректер бөлісуді конфигурациялау және қосымша мүмкіндіктерді қосу** бөлімінде қамтамасыз етуге болады.</span><span class="sxs-lookup"><span data-stu-id="d3594-193">Optionally, you can provide a Microsoft Dataverse environment URL under **Configure data sharing with Microsoft Dataverse and enable additional capabilities**.</span></span> <span data-ttu-id="d3594-194">Бұл мүмкіндіктер Microsoft Dataverse бағдарламасына негізделген бағдарламалармен және шешімдермен деректер бөлісуді конфигурациялауды, жергілікті деректер көздерінен деректерді қабылдауды немесе [болжамдарды](predictions.md) пайдалануды қамтиды.</span><span class="sxs-lookup"><span data-stu-id="d3594-194">These capabilities include data sharing with applications and solutions based on Microsoft Dataverse, data ingestion from on-premises data sources, or the use [predictions](predictions.md).</span></span> <span data-ttu-id="d3594-195">Customer Insights шығыс деректерін Microsoft Dataverse басқарылатын Data Lake қызметімен ортақ пайдалану үшін **Деректерді бөлісуді қосу** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="d3594-195">Select **Enable data sharing** to share Customer Insights output data with a Microsoft Dataverse Managed Data lake.</span></span>

   > [!NOTE]
   > - <span data-ttu-id="d3594-196">Барлық деректерді өз Azure Data Lake Storage қызметіңізге сақтағанда Microsoft Dataverse басқарылатын Data Lake қызметімен деректерді бөлісуге ағымдағы уақытта қолдау көрсетілмейді.</span><span class="sxs-lookup"><span data-stu-id="d3594-196">Data sharing with Microsoft Dataverse Managed Data Lake is currently not supported when you save all data to your own Azure Data Lake Storage.</span></span>
   > - <span data-ttu-id="d3594-197">[Нысандағы жетіспейтін мәндердің болжамына](predictions.md) қазіргі уақытта Microsoft Dataverse басқарылатын Data Lake қызметімен деректерді ортақ пайдалануды қосқан кезде қолдау көрсетілмейді.</span><span class="sxs-lookup"><span data-stu-id="d3594-197">[Prediction of missing values in an entity](predictions.md) is currently not supported when you enable data sharing with Microsoft Dataverse Managed Data Lake.</span></span>

   <span data-ttu-id="d3594-198">Microsoft Dataverse бағдарламасымен деректер бөлісуді қосқаннан кейін, деректер көздерін және басқа процестерді толықтай жаңарту басталады.</span><span class="sxs-lookup"><span data-stu-id="d3594-198">After enabling data sharing with Microsoft Dataverse, a full refresh of your data sources and other processes starts.</span></span> <span data-ttu-id="d3594-199">Егер процестер қазір іске қосылса, сіз Microsoft Dataverse бағдарламасымен деректер бөлісуді қосу опциясын көрмейсіз.</span><span class="sxs-lookup"><span data-stu-id="d3594-199">If processes are currently running, you don't see the option to enable data sharing with Microsoft Dataverse.</span></span> <span data-ttu-id="d3594-200">Деректермен бөлісуді қосу үшін сіз сол процестердің аяқталғанын күтіңіз немесе олардан бас тартыңыз.</span><span class="sxs-lookup"><span data-stu-id="d3594-200">Wait for those processes to complete or cancel them to enable data sharing.</span></span> 
   
   :::image type="content" source="media/datasharing-with-DataverseMDL.png" alt-text="Microsoft Dataverse бағдарламасымен деректер бөлісуді қосуға арналған конфигурация опциялары.":::
   
   <span data-ttu-id="d3594-202">Деректерді қабылдау немесе сегмент құру сияқты процестерді іске қосқан кезде, жоғарыда көрсеткен сақтау тіркелгісінде сәйкес қалталар жасалады.</span><span class="sxs-lookup"><span data-stu-id="d3594-202">When you run processes, such as data ingestion or segment creation, corresponding folders will be created in the storage account you specified above.</span></span> <span data-ttu-id="d3594-203">Деректер файлдары және model.json файлдары жасалады және сіз іске қосқан процеске байланысты тиісті ішкі қалталарға қосылады.</span><span class="sxs-lookup"><span data-stu-id="d3594-203">Data files and model.json files will be created and added to the respective subfolders, depending on the process you run.</span></span>

## <a name="reset-an-existing-environment"></a><span data-ttu-id="d3594-204">Бұрыннан бар ортаны қалпына келтіру</span><span class="sxs-lookup"><span data-stu-id="d3594-204">Reset an existing environment</span></span>

<span data-ttu-id="d3594-205">Әкімші ретінде барлық конфигурацияларды жойып, қабылданған деректерді өшіргіңіз келсе, ортаны бос күйіне қалпына келтіре аласыз.</span><span class="sxs-lookup"><span data-stu-id="d3594-205">As an administrator, you can reset an environment to an empty state if you want to delete all configurations and remove the ingested data.</span></span>

1.  <span data-ttu-id="d3594-206">Бағдарлама тақырыбында **Орта** таңдау құралын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="d3594-206">Select the **Environment** picker in the header of the app.</span></span> 

2.  <span data-ttu-id="d3594-207">Қалпына келтіру керек ортаны таңдап, көп нүктені (**...**) таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="d3594-207">Select the environment you want to reset and select the ellipsis (**...**).</span></span> 

3. <span data-ttu-id="d3594-208">**Қалпына келтіру** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="d3594-208">Choose the **Reset** option.</span></span> 

4.  <span data-ttu-id="d3594-209">Жоюды растау үшін ортаның атын енгізіп, **Қалпына келтіру** пәрменін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="d3594-209">To confirm the deletion, enter the environment name and select **Reset**.</span></span>

## <a name="delete-an-existing-environment"></a><span data-ttu-id="d3594-210">Бұрыннан бар ортаны жойыңыз</span><span class="sxs-lookup"><span data-stu-id="d3594-210">Delete an existing environment</span></span>

<span data-ttu-id="d3594-211">Әкімші ретінде басқаратын ортаны жоя аласыз.</span><span class="sxs-lookup"><span data-stu-id="d3594-211">As an administrator, you can delete an environment you administer.</span></span>

1.  <span data-ttu-id="d3594-212">Бағдарлама тақырыбында **Орта** таңдау құралын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="d3594-212">Select the **Environment** picker in the header of the app.</span></span>

2.  <span data-ttu-id="d3594-213">Қалпына келтіру керек ортаны таңдап, көп нүктені (**...**) таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="d3594-213">Select the environment you want to reset and select the ellipsis (**...**).</span></span> 

3. <span data-ttu-id="d3594-214">**Жою** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="d3594-214">Choose the **Delete** option.</span></span> 

4.  <span data-ttu-id="d3594-215">Жоюды растау үшін орта атауын енгізіңіз және **Жою** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="d3594-215">To confirm the deletion, enter the environment name and select **Delete**.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
