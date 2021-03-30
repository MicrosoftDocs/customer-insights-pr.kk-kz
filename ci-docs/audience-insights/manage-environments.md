---
title: Орталарды жасау және басқару
description: Қызметке қалай тіркелуге болатынын және орталарды басқару әдісі туралы мәлімет алыңыз.
ms.date: 02/01/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: 1c2dfdd2889b5cb6c5285b4d7cc7f52a3d6de4d1
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598300"
---
# <a name="manage-environments"></a><span data-ttu-id="54e75-103">Орталарды басқару</span><span class="sxs-lookup"><span data-stu-id="54e75-103">Manage environments</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="54e75-104">Бұл мақала жаңа ұйымды қалай құру керектігін және қоршаған ортаны қалай қамтамасыз ету керектігін түсіндіреді.</span><span class="sxs-lookup"><span data-stu-id="54e75-104">This article explains how to create a new organization and how to provision an environment.</span></span>

## <a name="sign-up-and-create-an-organization"></a><span data-ttu-id="54e75-105">Ұйымды тіркеу, жасау</span><span class="sxs-lookup"><span data-stu-id="54e75-105">Sign up and create an organization</span></span>

1. <span data-ttu-id="54e75-106">[Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/) веб-сайтына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="54e75-106">Go to the [Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/) website.</span></span>

2. <span data-ttu-id="54e75-107">**Жұмысты бастау** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="54e75-107">Select **Get Started**.</span></span>

3. <span data-ttu-id="54e75-108">Қажетті тіркелу сценарийін таңдап, сәйкес сілтемені таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="54e75-108">Choose your preferred sign-up scenario and select the corresponding link.</span></span>

4. <span data-ttu-id="54e75-109">Шарттар мен талаптарды қабылдап, ұйым жасауды бастау үшін **Жалғастыру** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="54e75-109">Accept the terms and conditions and select **Continue** to start creating the organization.</span></span>

5. <span data-ttu-id="54e75-110">Орта жасалғаннан кейін, [Customer Insights](https://home.ci.ai.dynamics.com) тармағына қайта бағытталасыз.</span><span class="sxs-lookup"><span data-stu-id="54e75-110">After the environment is created, you'll be redirected to [Customer Insights](https://home.ci.ai.dynamics.com).</span></span>

6. <span data-ttu-id="54e75-111">Қолданбаны зерттеу үшін демо орталарды пайдаланыңыз немесе келесі бөлімдегі қадамдарды орындау арқылы жаңа орта жасаңыз.</span><span class="sxs-lookup"><span data-stu-id="54e75-111">Use the demo environment to explore the app, or create a new environment by following the steps in the next section.</span></span>

7. <span data-ttu-id="54e75-112">Орта параметрлерін көрсеткеннен кейін **Жасау** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="54e75-112">After specifying the environment settings, select **Create**.</span></span>

8. <span data-ttu-id="54e75-113">Жүйеге орта сәтті жасалғаннан кейін кіресіз.</span><span class="sxs-lookup"><span data-stu-id="54e75-113">You'll be signed in after the environment was created successfully.</span></span>

## <a name="create-an-environment-in-an-existing-organization"></a><span data-ttu-id="54e75-114">Бұрыннан бар ұйымда орта жасау</span><span class="sxs-lookup"><span data-stu-id="54e75-114">Create an environment in an existing organization</span></span>

<span data-ttu-id="54e75-115">Жаңа ортаны жасаудың екі жолы бар.</span><span class="sxs-lookup"><span data-stu-id="54e75-115">There are two ways to create a new environment.</span></span> <span data-ttu-id="54e75-116">Толығымен жаңа конфигурацияны көрсетуге немесе бар ортадан кейбір конфигурация параметрлерін көшіруге болады.</span><span class="sxs-lookup"><span data-stu-id="54e75-116">You can either specify an entirely new configuration, or you can copy some configuration settings from an existing environment.</span></span>

<span data-ttu-id="54e75-117">Орта жасау үшін:</span><span class="sxs-lookup"><span data-stu-id="54e75-117">To create an environment:</span></span>

1. <span data-ttu-id="54e75-118">Бағдарлама тақырыбында **Орта** таңдау құралын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="54e75-118">Select the **Environment** picker in the header of the app.</span></span>

1. <span data-ttu-id="54e75-119">**Жаңа** пәрменін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="54e75-119">Select **New**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="54e75-120">![Орта параметрлері](media/environment-settings-dialog.png)</span><span class="sxs-lookup"><span data-stu-id="54e75-120">![Environment settings](media/environment-settings-dialog.png)</span></span>

1. <span data-ttu-id="54e75-121">**Жаңа орта жасау** диалогтік терезесінен **Жаңа орта** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="54e75-121">In the **Create new environment** dialog, select **New environment**.</span></span>

   <span data-ttu-id="54e75-122">Егер [ағымдағы ортадан деректерді көшіру](#additional-considerations-for-copy-configuration-preview) қажет болса, **Бұрыннан бар ортадан көшіру** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="54e75-122">If you want to [copy data from the current environment](#additional-considerations-for-copy-configuration-preview), select **Copy from existing environment**.</span></span> <span data-ttu-id="54e75-123">Деректерді көшіруге болатын ұйымда барлық қолжетімді орталар тізімін көресіз.</span><span class="sxs-lookup"><span data-stu-id="54e75-123">You'll see a list of all available environments in your organization where you can copy data from.</span></span>

1. <span data-ttu-id="54e75-124">Келесі мәліметтерді көрсетіңіз:</span><span class="sxs-lookup"><span data-stu-id="54e75-124">Provide the following details:</span></span>
   - <span data-ttu-id="54e75-125">**Атауы**: осы ортаның атауы.</span><span class="sxs-lookup"><span data-stu-id="54e75-125">**Name**: The name for this environment.</span></span> <span data-ttu-id="54e75-126">Бар ортадан көшірсеңіз, бірақ оны өзгерте алмасаңыз, осы өріс толтырулы болады.</span><span class="sxs-lookup"><span data-stu-id="54e75-126">This field is already filled in if you've copied an existing environment, but you can change it.</span></span>
   - <span data-ttu-id="54e75-127">**Аймақ**: қызмет орналастырылған аймақ.</span><span class="sxs-lookup"><span data-stu-id="54e75-127">**Region**: The region into which the service is deployed and hosted.</span></span>
   - <span data-ttu-id="54e75-128">**Түрі**: жұмыс немесе сынақ данасы ортасын жасау керектігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="54e75-128">**Type**: Select whether you want to create a Production or Sandbox environment.</span></span>

2. <span data-ttu-id="54e75-129">Қажет болса, **Қосымша параметрлер** опциясын таңдауға болады:</span><span class="sxs-lookup"><span data-stu-id="54e75-129">Optionally, you can select **Advanced settings**:</span></span>

   - <span data-ttu-id="54e75-130">**Барлық деректерді сақтау орны**: Customer Insights бағдарламасынан құрылған шығыс деректерін сақтау орнын көрсетеді.</span><span class="sxs-lookup"><span data-stu-id="54e75-130">**Save all data to**: Specifies where you want to store the output data generated from Customer Insights.</span></span> <span data-ttu-id="54e75-131">Сізде екі параметр болады: **Customer Insights сақтау орны** (Customer Insights тобы арқылы басқарылатын Azure Data Lake) және **Azure Data Lake Storage Gen2** (сіздің жеке Azure Data Lake Storage).</span><span class="sxs-lookup"><span data-stu-id="54e75-131">You'll have two options: **Customer Insights storage** (an Azure Data Lake managed by the Customer Insights team) and **Azure Data Lake Storage Gen2** (your own Azure Data Lake Storage).</span></span> <span data-ttu-id="54e75-132">Әдепкі бойынша Customer Insights сақтау орны параметрі таңдалады.</span><span class="sxs-lookup"><span data-stu-id="54e75-132">By default, the Customer Insights storage option is selected.</span></span>

   > [!NOTE]
   > <span data-ttu-id="54e75-133">Деректерд Azure Data Lake Storage сақтау орнында сақтау арқылы , деректердің сол Azure сақтау орнының тіркелгісі үшін тиісті географиялық орынға тасымалданып және сақталатындығына келісім бересіз және ол Dynamics 365 Customer Insights бағдарламасында сақталған орнынан бөлек болуы мүмкін.</span><span class="sxs-lookup"><span data-stu-id="54e75-133">By saving data to Azure Data Lake Storage, you agree that data will be transferred to and stored in the appropriate geographic location for that Azure storage account, which may differ from where data is stored in Dynamics 365 Customer Insights.</span></span> [<span data-ttu-id="54e75-134">Microsoft сенім орталығы туралы қосымша ақпарат.</span><span class="sxs-lookup"><span data-stu-id="54e75-134">Learn more at the Microsoft Trust Center.</span></span>](https://www.microsoft.com/trust-center)
   >
   > <span data-ttu-id="54e75-135">Ағымда қабылданбаған нысандар әрдайым Customer Insights бағдарламасы арқылы басқарылатын деректер көлінде сақталады.</span><span class="sxs-lookup"><span data-stu-id="54e75-135">Currently, ingested entities are always stored in the Customer Insights managed data lake.</span></span>
   > <span data-ttu-id="54e75-136">Біз тек ортаны құру кезінде таңдалған бірдей Azure аймағының Azure Data Lake Gen2 сақтау тіркелгілеріне қолдау көрсетеміз.</span><span class="sxs-lookup"><span data-stu-id="54e75-136">We support only Azure Data Lake Gen2 storage accounts from the same Azure region you selected when creating the environment.</span></span>
   > <span data-ttu-id="54e75-137">Біз тек Azure Data Lake Gen2 иерархиялық атау кеңістігінің (HNS) қосылған сақтау орнының тіркелгілеріне қолдау көрсетеміз.</span><span class="sxs-lookup"><span data-stu-id="54e75-137">We support only Azure Data Lake Gen2 Hierarchical Name Space (HNS) enabled storage accounts.</span></span>

   - <span data-ttu-id="54e75-138">Azure Data Lake Storage Gen2 опциясы үшін ресурсқа негізделген опция мен аутентификацияға арналған жазылымға негізделген опция арасында таңдау жасай аласыз.</span><span class="sxs-lookup"><span data-stu-id="54e75-138">For the Azure Data Lake Storage Gen2 option, you can choose between a resource-based option and a subscription-based option for authentication.</span></span> <span data-ttu-id="54e75-139">Қосымша ақпарат алу үшін [Аудитория мәліметтерін Azure субъект-қызметімен Azure Data Lake Storage Gen2 тіркелгісіне қосу](connect-service-principal.md) бөлімін қараңыз.</span><span class="sxs-lookup"><span data-stu-id="54e75-139">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="54e75-140">**Контейнер** атауы өзгертілмейді және "customerinsights" ретінде қарастырылады.</span><span class="sxs-lookup"><span data-stu-id="54e75-140">The **Container** name can't be changed and will be "customerinsights".</span></span>
   
   - <span data-ttu-id="54e75-141">Егер [болжамдарды](predictions.md) пайдалану немесе Microsoft Dataverse негізіндегі бағдарламалар мен шешімдермен деректерді бөлісуді конфигурациялау қажет болса, **Microsoft Dataverse қызметімен деректерді бөлісуді конфигурациялау және қосымша мүмкіндіктерді қосу** бөлімінде Microsoft Dataverse ортасының URL мекенжайын енгізіңіз.</span><span class="sxs-lookup"><span data-stu-id="54e75-141">If you want to use [predictions](predictions.md) or configure data sharing with applications and solutions based on Microsoft Dataverse, provide the Microsoft Dataverse environment URL under **Configure data sharing with Microsoft Dataverse and enable additional capabilities**.</span></span> <span data-ttu-id="54e75-142">Customer Insights шығыс деректерін Microsoft Dataverse басқарылатын Data Lake қызметімен ортақ пайдалану үшін **Деректерді бөлісуді қосу** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="54e75-142">Select **Enable data sharing** to share Customer Insights output data with a Microsoft Dataverse Managed Data Lake.</span></span>

     > [!NOTE]
     > - <span data-ttu-id="54e75-143">Барлық деректерді өз Azure Data Lake Storage қызметіңізге сақтағанда Microsoft Dataverse басқарылатын Data Lake қызметімен деректерді бөлісуге ағымдағы уақытта қолдау көрсетілмейді.</span><span class="sxs-lookup"><span data-stu-id="54e75-143">Data sharing with Microsoft Dataverse Managed Data Lake is currently not supported when you save all data to your own Azure Data Lake Storage.</span></span>
     > - <span data-ttu-id="54e75-144">Microsoft Dataverse басқарылатын Data Lake қызметімен деректерді бөлісуді қосқанда [нысанда жоқ мәндер болжамына](predictions.md) ағымдағы уақытта қолдау көрсетілмейді.</span><span class="sxs-lookup"><span data-stu-id="54e75-144">[Prediction of missing values in an entity](predictions.md) is not currently supported when you enable data sharing with Microsoft Dataverse Managed Data Lake.</span></span>

     > [!div class="mx-imgBorder"]
     > <span data-ttu-id="54e75-145">![Microsoft Dataverse қызметімен деректермен бөлісуге мүмкіндік беретін конфигурация параметрлері](media/Datasharing-with-DataverseMDL.png)</span><span class="sxs-lookup"><span data-stu-id="54e75-145">![Configuration options to enable data sharing with Microsoft Dataverse](media/Datasharing-with-DataverseMDL.png)</span></span>

   <span data-ttu-id="54e75-146">Деректерді қабылдау немесе сегмент құру сияқты процестерді іске қосқан кезде, жоғарыда көрсеткен сақтау тіркелгісінде сәйкес қалталар жасалады.</span><span class="sxs-lookup"><span data-stu-id="54e75-146">When you run processes, such as data ingestion or segment creation, corresponding folders will be created in the storage account you specified above.</span></span> <span data-ttu-id="54e75-147">Сіз іске қосқан процеске байланысты деректер файлдары мен model.json файлдарын жасалып, тиісті қосалқы қалталарға қосылады.</span><span class="sxs-lookup"><span data-stu-id="54e75-147">Data files and model.json files will be created and added to the respective subfolders based on the process you run.</span></span>

   <span data-ttu-id="54e75-148">Customer Insights жүйесінің бірнеше ортасын жасасаңыз және шығыс нысандарын осы орталардан сақтау тіркелгісінде сақтауды таңдасаңыз, ci_<environmentid> контейнерінде әр орта үшін бөлек қалталар жасалады.</span><span class="sxs-lookup"><span data-stu-id="54e75-148">If you create multiple environments of Customer Insights and choose to save the output entities from those environments in your storage account, separate folders will be created for each environment with ci_<environmentid> in the container.</span></span>

### <a name="additional-considerations-for-copy-configuration-preview"></a><span data-ttu-id="54e75-149">Көшірме конфигурациясына арналған қосымша қарастырулар (алдын ала қарау)</span><span class="sxs-lookup"><span data-stu-id="54e75-149">Additional considerations for copy configuration (preview)</span></span>

<span data-ttu-id="54e75-150">Мына конфигурация параметрлері көшіріледі:</span><span class="sxs-lookup"><span data-stu-id="54e75-150">The following configuration settings are copied:</span></span>

- <span data-ttu-id="54e75-151">Мүмкіндік конфигурациялары</span><span class="sxs-lookup"><span data-stu-id="54e75-151">Feature configurations</span></span>
- <span data-ttu-id="54e75-152">Қабылданған/импортталған деректер көздері</span><span class="sxs-lookup"><span data-stu-id="54e75-152">Ingested/imported data sources</span></span>
- <span data-ttu-id="54e75-153">Деректерді біріктіру (салыстыру, сәйкестендіру, біріктіру) конфигурациясы</span><span class="sxs-lookup"><span data-stu-id="54e75-153">Data unification (Map, Match, Merge) configuration</span></span>
- <span data-ttu-id="54e75-154">Сегменттер</span><span class="sxs-lookup"><span data-stu-id="54e75-154">Segments</span></span>
- <span data-ttu-id="54e75-155">Өлшемдер</span><span class="sxs-lookup"><span data-stu-id="54e75-155">Measures</span></span>
- <span data-ttu-id="54e75-156">Қатынастар</span><span class="sxs-lookup"><span data-stu-id="54e75-156">Relationships</span></span>
- <span data-ttu-id="54e75-157">Әрекеттер</span><span class="sxs-lookup"><span data-stu-id="54e75-157">Activities</span></span>
- <span data-ttu-id="54e75-158">Іздеу және сүзгілеу индексі</span><span class="sxs-lookup"><span data-stu-id="54e75-158">Search & filter Index</span></span>
- <span data-ttu-id="54e75-159">Мақсатты орындарды экспорттау</span><span class="sxs-lookup"><span data-stu-id="54e75-159">Export destinations</span></span>
- <span data-ttu-id="54e75-160">Жоспарланған жаңарту</span><span class="sxs-lookup"><span data-stu-id="54e75-160">Scheduled refresh</span></span>
- <span data-ttu-id="54e75-161">Арттырулар</span><span class="sxs-lookup"><span data-stu-id="54e75-161">Enrichments</span></span>
- <span data-ttu-id="54e75-162">Үлгіні басқару</span><span class="sxs-lookup"><span data-stu-id="54e75-162">Model management</span></span>
- <span data-ttu-id="54e75-163">Рөл тағайындаулары</span><span class="sxs-lookup"><span data-stu-id="54e75-163">Role assignments</span></span>

<span data-ttu-id="54e75-164">Мына конфигурация параметрлері *көшірілмейді*:</span><span class="sxs-lookup"><span data-stu-id="54e75-164">The following settings are *not* copied:</span></span>

- <span data-ttu-id="54e75-165">Тұтынушы профильдері.</span><span class="sxs-lookup"><span data-stu-id="54e75-165">Customer profiles.</span></span>
- <span data-ttu-id="54e75-166">Дереккөз деректемелері.</span><span class="sxs-lookup"><span data-stu-id="54e75-166">Data source credentials.</span></span> <span data-ttu-id="54e75-167">Әрбір дереккөз деректемелерін қамтамасыз етесіз және дереккөздерді қолмен жаңартасыз.</span><span class="sxs-lookup"><span data-stu-id="54e75-167">You'll have to provide the credentials for every data source and refresh the data sources manually.</span></span>
- <span data-ttu-id="54e75-168">Common Data Model қалтасы мен Common Data Service басқарылатын ағынының дереккөздері.</span><span class="sxs-lookup"><span data-stu-id="54e75-168">Data sources from Common Data Model folder and Common Data Service managed lake.</span></span> <span data-ttu-id="54e75-169">Осы дереккөздерді бастапқы ортадағымен бірдей атпен қолмен жасай аласыз.</span><span class="sxs-lookup"><span data-stu-id="54e75-169">You'll have to create those data sources manually with the same name as in the source environment.</span></span>

<span data-ttu-id="54e75-170">Ортаны көшірген кезде жаңа орта жасалған растау туралы хабарды көресіз.</span><span class="sxs-lookup"><span data-stu-id="54e75-170">When you copy an environment, you'll see a confirmation message that the new environment has been created.</span></span> <span data-ttu-id="54e75-171">Дереккөздер тізімін көру үшін **Дереккөздерге өту** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="54e75-171">Select **Go to data sources** to see the list of data sources.</span></span>

<span data-ttu-id="54e75-172">Барлық дереккөздер **Қажетті деректемелер** күйін көрсетеді.</span><span class="sxs-lookup"><span data-stu-id="54e75-172">All the data sources will show a **Credentials Required** status.</span></span> <span data-ttu-id="54e75-173">Дереккөздерді өңдеп, оларды жаңарту үшін деректемелерді енгізіңіз.</span><span class="sxs-lookup"><span data-stu-id="54e75-173">Edit the data sources and enter the credentials to refresh them.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="54e75-174">![Дереккөздер көшірілді](media/data-sources-copied.png)</span><span class="sxs-lookup"><span data-stu-id="54e75-174">![Data sources copied](media/data-sources-copied.png)</span></span>

<span data-ttu-id="54e75-175">Деректер көздерін жаңартқан соң, **Деректер** > **Біріктіру** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="54e75-175">After refreshing the data sources, go to **Data** > **Unify**.</span></span> <span data-ttu-id="54e75-176">Мұнда көз ортасынан параметрлерді таба аласыз.</span><span class="sxs-lookup"><span data-stu-id="54e75-176">Here you'll find settings from the source environment.</span></span> <span data-ttu-id="54e75-177">Оларды қажетінше өңдеңіз немесе біріктіру процесін бастау үшін **Іске қосу** параметрін таңдап, бірыңғай тұтынушы нысанын жасаңыз.</span><span class="sxs-lookup"><span data-stu-id="54e75-177">Edit them as needed or select **Run** to start the data unification process and create the unified customer entity.</span></span>

<span data-ttu-id="54e75-178">Деректерді біріктіру аяқталған кезде оларды да жаңарту үшін **Шаралар** және **Сегменттер** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="54e75-178">When the data unification is complete, go to **Measures** and **Segments** to refresh them too.</span></span>

## <a name="edit-an-existing-environment"></a><span data-ttu-id="54e75-179">Бұрыннан бар ортаны өңдеу</span><span class="sxs-lookup"><span data-stu-id="54e75-179">Edit an existing environment</span></span>

<span data-ttu-id="54e75-180">Бұрыннан бар орталардың кейбір мәліметтерін өңдеуге болады.</span><span class="sxs-lookup"><span data-stu-id="54e75-180">You can edit some of the details of existing environments.</span></span>

1.  <span data-ttu-id="54e75-181">Бағдарлама тақырыбында **Орта** таңдау құралын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="54e75-181">Select the **Environment** picker in the header of the app.</span></span>

2.  <span data-ttu-id="54e75-182">**Өңдеу** белгішесін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="54e75-182">Select the **Edit** icon.</span></span>

3. <span data-ttu-id="54e75-183">**Ортаны өңдеу** терезесінде ортаның **көрсетілетін атауы** өрісін жаңартуға болады, бірақ **Аймақ** немесе **Түрі** өрістерін өзгерту мүмкін емес.</span><span class="sxs-lookup"><span data-stu-id="54e75-183">In the **Edit environment** box, you can update the environment's **Display name**, but you can't change the **Region** or **Type**.</span></span>

4. <span data-ttu-id="54e75-184">Егер орта деректерді Azure Data Lake Storage Gen2 ішінде сақтауға конфигурацияланса, **Тіркелгі кілті** өрісін жаңартуға болады.</span><span class="sxs-lookup"><span data-stu-id="54e75-184">If an environment is configured to store data in Azure Data Lake Storage Gen2, you can update the **Account key**.</span></span> <span data-ttu-id="54e75-185">Дегенмен, **Тіркелгі атын** немесе **Контейнер** атын өзгерте алмайсыз.</span><span class="sxs-lookup"><span data-stu-id="54e75-185">However, you can't change the **Account name** or **Container** name.</span></span>

5. <span data-ttu-id="54e75-186">Оған қоса, тіркелгі кілтіне негізделген қосылымынан ресурстарға немесе жазылымға негізделген байланысқа дейін жаңарта аласыз.</span><span class="sxs-lookup"><span data-stu-id="54e75-186">Optionally, you can update from an account key based connection to a resource-based or subscription-based connection.</span></span> <span data-ttu-id="54e75-187">Жаңартылып біткенде жаңартудан кейін тіркелгі кілтіне оралу мүмкін емес.</span><span class="sxs-lookup"><span data-stu-id="54e75-187">Once upgraded, you cannot revert to account key after the update.</span></span> <span data-ttu-id="54e75-188">Қосымша ақпарат алу үшін [Аудитория мәліметтерін Azure субъект-қызметімен Azure Data Lake Storage Gen2 тіркелгісіне қосу](connect-service-principal.md) бөлімін қараңыз.</span><span class="sxs-lookup"><span data-stu-id="54e75-188">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="54e75-189">Байланысты жаңарту кезінде **Контейнер** ақпаратын өзгерту мүмкін емес.</span><span class="sxs-lookup"><span data-stu-id="54e75-189">You can't change **Container** information when updating the connection.</span></span>

## <a name="reset-an-existing-environment"></a><span data-ttu-id="54e75-190">Бұрыннан бар ортаны қалпына келтіру</span><span class="sxs-lookup"><span data-stu-id="54e75-190">Reset an existing environment</span></span>

<span data-ttu-id="54e75-191">Әкімші ретінде барлық конфигурацияларды жойып, қабылданған деректерді өшіргіңіз келсе, ортаны бос күйіне қалпына келтіре аласыз.</span><span class="sxs-lookup"><span data-stu-id="54e75-191">As an administrator, you can reset an environment to an empty state if you want to delete all configurations and remove the ingested data.</span></span>

1.  <span data-ttu-id="54e75-192">Бағдарлама тақырыбында **Орта** таңдау құралын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="54e75-192">Select the **Environment** picker in the header of the app.</span></span> 

2.  <span data-ttu-id="54e75-193">Қалпына келтіретін ортаны таңдап, көп нүктені **...** таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="54e75-193">Select the environment you want to reset and select the ellipsis **...**.</span></span> 

3. <span data-ttu-id="54e75-194">**Қалпына келтіру** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="54e75-194">Choose the **Reset** option.</span></span> 

4.  <span data-ttu-id="54e75-195">Жоюды растау үшін ортаның атын енгізіп, **Қалпына келтіру** пәрменін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="54e75-195">To confirm the deletion, enter the environment name and select **Reset**.</span></span>

## <a name="delete-an-existing-environment-available-only-for-admins"></a><span data-ttu-id="54e75-196">Бұрыннан бар ортаны жою (тек әкімшілер үшін қолжетімді)</span><span class="sxs-lookup"><span data-stu-id="54e75-196">Delete an existing environment (available only for admins)</span></span>

<span data-ttu-id="54e75-197">Әкімші ретінде басқаратын ортаны жоя аласыз.</span><span class="sxs-lookup"><span data-stu-id="54e75-197">As an administrator, you can delete an environment you administer.</span></span>

1.  <span data-ttu-id="54e75-198">Бағдарлама тақырыбында **Орта** таңдау құралын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="54e75-198">Select the **Environment** picker in the header of the app.</span></span>

2.  <span data-ttu-id="54e75-199">Қалпына келтіретін ортаны таңдап, көп нүктені **...** таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="54e75-199">Select the environment you want to reset and select the ellipsis **...**.</span></span> 

3. <span data-ttu-id="54e75-200">**Жою** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="54e75-200">Choose the **Delete** option.</span></span> 

4.  <span data-ttu-id="54e75-201">Жоюды растау үшін орта атауын енгізіңіз және **Жою** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="54e75-201">To confirm the deletion, enter the environment name and select **Delete**.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]