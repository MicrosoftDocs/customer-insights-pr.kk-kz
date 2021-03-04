---
title: Реттелетін компьютерлік оқыту үлгілері | Microsoft Docs
description: Dynamics 365 Customer Insights бағдарламасында Azure Machine Learning қызметінен реттелетін үлгілермен жұмыс жасаңыз.
ms.date: 11/19/2020
ms.reviewer: zacook
ms.service: dynamics-365-ai
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 34489faaecc5da1ce3dd68d799b3e0e0d9672ab7
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267241"
---
# <a name="custom-machine-learning-models"></a><span data-ttu-id="18dda-103">Реттелетін компьютерлік оқыту үлгілері</span><span class="sxs-lookup"><span data-stu-id="18dda-103">Custom machine learning models</span></span>

<span data-ttu-id="18dda-104">**Сараптау** > **Реттелетін үлгілер** тармағы Azure Machine Learning үлгілеріне байланысты жұмыс ағындарын басқаруға мүмкіндік береді.</span><span class="sxs-lookup"><span data-stu-id="18dda-104">**Intelligence** > **Custom models** lets you manage workflows based on Azure Machine Learning models.</span></span> <span data-ttu-id="18dda-105">Жұмыс ағындары сізге түсініктер құруға болатын деректерді таңдауға және нәтижелерді тұтынушының бірыңғай деректерімен салыстыруға көмектеседі.</span><span class="sxs-lookup"><span data-stu-id="18dda-105">Workflows help you choose the data you want to generate insights from and map the results to your unified customer data.</span></span> <span data-ttu-id="18dda-106">Реттелетін ML үлгілерін құру туралы қосымша ақпаратты [Azure Machine Learning бағдарламасына негізделген үлгілерді пайдалану](azure-machine-learning-experiments.md) бөлімінен қараңыз.</span><span class="sxs-lookup"><span data-stu-id="18dda-106">For more information about building custom ML models, see [Use Azure Machine Learning-based models](azure-machine-learning-experiments.md).</span></span>

## <a name="responsible-ai"></a><span data-ttu-id="18dda-107">Жауапты жасанды интелект</span><span class="sxs-lookup"><span data-stu-id="18dda-107">Responsible AI</span></span>

<span data-ttu-id="18dda-108">Болжамдар тұтынушылардың жақсы тәжірибесін жасауға, бизнес мүмкіндіктерін жақсартуға және кіріс ағындарына мүмкіндіктер ұсынады.</span><span class="sxs-lookup"><span data-stu-id="18dda-108">Predictions offer capabilities to create better customer experiences, improve business capabilities, and revenue streams.</span></span> <span data-ttu-id="18dda-109">Болжам мәнін оның әсері мен этикалық тәртіпте енгізілуі мүмкін жағымсыздықтарға теңестіруді қатаң түрде ұсынамыз.</span><span class="sxs-lookup"><span data-stu-id="18dda-109">We strongly recommend you balance the value of your prediction against the impact it has and biases that may be introduced in an ethical manner.</span></span> <span data-ttu-id="18dda-110">Microsoft корпорациясының [Жауапты жасанды интеллектке жүгіну](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6) жолы туралы қосымша ақпарат.</span><span class="sxs-lookup"><span data-stu-id="18dda-110">Learn more about how Microsoft is [addressing Responsible AI](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6).</span></span> <span data-ttu-id="18dda-111">Сонымен қатар Azure Machine Learning бағдарламасына тән [жауапты компьютерлік оқытуларға арналған әдістер мен процестер](https://docs.microsoft.com/azure/machine-learning/concept-responsible-ml) туралы біле аласыздар.</span><span class="sxs-lookup"><span data-stu-id="18dda-111">You can also learn about [techniques and processes for responsible machine learning](https://docs.microsoft.com/azure/machine-learning/concept-responsible-ml) specific to Azure Machine Learning.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="18dda-112">Алғышарттар</span><span class="sxs-lookup"><span data-stu-id="18dda-112">Prerequisites</span></span>

- <span data-ttu-id="18dda-113">Қазіргі уақытта бұл функция [Machine Learning Studio (классикалық)](https://studio.azureml.net) және [ Azure Machine Learning топтамалық құбырлары ](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines) арқылы жарияланған веб-қызметтерді қолдайды.</span><span class="sxs-lookup"><span data-stu-id="18dda-113">Currently, this feature supports web services published through [Machine Learning Studio (classic)](https://studio.azureml.net) and [Azure Machine Learning batch pipelines](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines).</span></span>

- <span data-ttu-id="18dda-114">Бұл мүмкіндікті пайдалану үшін сізге Azure Studio данасымен байланысты Azure Data Lake Gen2 сақтау орны тіркелгісі қажет.</span><span class="sxs-lookup"><span data-stu-id="18dda-114">You need an Azure Data Lake Gen2 storage account associated with your Azure Studio instance to use this feature.</span></span> <span data-ttu-id="18dda-115">Қосымша ақпарат алу үшін [Azure Data Lake Storage Gen2 сақтау орны тіркелгісін жасау](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-quickstart-create-account) бөлімін қараңыз</span><span class="sxs-lookup"><span data-stu-id="18dda-115">For more information, see [Create an Azure Data Lake Storage Gen2 storage account](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-quickstart-create-account)</span></span>

## <a name="add-a-new-workflow"></a><span data-ttu-id="18dda-116">Жаңа жұмыс ағынын қосу</span><span class="sxs-lookup"><span data-stu-id="18dda-116">Add a new workflow</span></span>

1. <span data-ttu-id="18dda-117">**Интеллект** > **Реттелетін үлгілер** тармағына өтіп, **Жаңа жұмыс ағыны** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="18dda-117">Go to **Intelligence** > **Custom models** and select **New workflow**.</span></span>

1. <span data-ttu-id="18dda-118">**Аты** өрісінде реттелетін үлгіге анықталатын ат беріңіз.</span><span class="sxs-lookup"><span data-stu-id="18dda-118">Give your custom model a recognizable name in the **Name** field.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="18dda-119">![Жаңа жұмыс ағыны тақтасының скриншоты](media/new-workflowv2.png "Жаңа жұмыс ағыны тақтасының скриншоты")</span><span class="sxs-lookup"><span data-stu-id="18dda-119">![Screenshot of the New workflow pane](media/new-workflowv2.png "Screenshot of the New workflow pane")</span></span>

1. <span data-ttu-id="18dda-120">**Веб-қызметті қамтитын қатысушы** ішіндегі веб-қызметтен тұратын ұйымды таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="18dda-120">Select the organization that contains the web service in **Tenant that contains your web service**.</span></span>

1. <span data-ttu-id="18dda-121">Azure Machine Learning жазылымы Customer Insights бағдарламасынан өзге қатысушыда болса, таңдалған ұйымның деректемелерімен **Жүйеге кіру** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="18dda-121">If your Azure Machine Learning subscription is in a different tenant than Customer Insights, select **Sign in** with your credentials for the selected organization.</span></span>

1. <span data-ttu-id="18dda-122">Веб-қызметіңізбен байланысты **Жұмыс кеңістіктері** пәрменін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="18dda-122">Select the **Workspaces** associated with your web service.</span></span> <span data-ttu-id="18dda-123">Берілген екі бөлім бар, олардың бірі Azure Machine Learning v1 (Machine Learning Studio (классикалық)) және Azure Machine Learning v2 (Azure Machine Learning).</span><span class="sxs-lookup"><span data-stu-id="18dda-123">There are two sections listed, one for Azure Machine Learning v1 (Machine Learning Studio (classic)) and Azure Machine Learning v2 (Azure Machine Learning).</span></span> <span data-ttu-id="18dda-124">Егер сіз Machine Learning Studio (классикалық) веб-қызметі үшін қай жұмыс кеңістігінің дұрыс екеніне сенімді болмасаңыз, **Кез келген** пәрменін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="18dda-124">If you're not sure which workspace is the right one for your Machine Learning Studio (classic) web service, select **Any**.</span></span>

1. <span data-ttu-id="18dda-125">**Үлгіңізді қамтитын веб-қызмет** ашылмалы тізімінен Machine Learning Studio (классикалық) веб-қызметін немесе Azure Machine Learning үрдістер тізбегін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="18dda-125">Choose the Machine Learning Studio (classic) web service or Azure Machine Learning pipeline in the **Web service that contains your model** dropdown.</span></span> <span data-ttu-id="18dda-126">Содан кейін **Келесі** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="18dda-126">Then, select **Next**.</span></span>
   - <span data-ttu-id="18dda-127">[Machine Learning Studio (классикалық) бағдарламасында веб-қызметті жариялау](https://docs.microsoft.com/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service) туралы қосымша ақпарат</span><span class="sxs-lookup"><span data-stu-id="18dda-127">Learn more about [publishing a web service in Machine Learning Studio (classic)](https://docs.microsoft.com/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service)</span></span>
   - <span data-ttu-id="18dda-128">[Azure Machine Learning бағдарламасындағы үрдістер тізбегін құрастырушы көмегімен жариялау](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) немесе [SDK](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk) туралы қосымша ақпарат.</span><span class="sxs-lookup"><span data-stu-id="18dda-128">Learn more about [publishing a pipeline in Azure Machine Learning using the designer](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) or [SDK](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk).</span></span> <span data-ttu-id="18dda-129">Үрдістер тізбегі [үрдістер тізбегінің соңғы нүктесі](https://docs.microsoft.com/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run) астында жариялануы тиіс.</span><span class="sxs-lookup"><span data-stu-id="18dda-129">Your pipeline must be published under a [pipeline endpoint](https://docs.microsoft.com/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).</span></span>

1. <span data-ttu-id="18dda-130">Әр **Веб-қызмет кірісі** үшін аудитория түсініктерінен сәйкес **Нысан** опциясын таңдап, **Келесі** пәрменін басыңыз.</span><span class="sxs-lookup"><span data-stu-id="18dda-130">For each **Web service input**, select the matching **Entity** from audience insights and select **Next**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="18dda-131">Реттелетін үлгінің жұмыс ағыны веб-қызметтің кіріс өрістерін өрістің атауы мен деректер түріне негізделген нысан төлсипаттарымен салыстыру үшін эвристиканы қолданады.</span><span class="sxs-lookup"><span data-stu-id="18dda-131">The custom model workflow will apply heuristics to map the web service input fields to the entity attributes based on the name and data type of the field.</span></span> <span data-ttu-id="18dda-132">Егер веб-қызмет өрісін нысанмен салыстыру мүмкін болмаса, қате көрсетіледі..</span><span class="sxs-lookup"><span data-stu-id="18dda-132">You'll see an error if a web service field can't be mapped to an entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="18dda-133">![Жұмыс ағынын конфигурациялау](media/intelligence-screen2-updated.png "Жұмыс ағынын конфигурациялау")</span><span class="sxs-lookup"><span data-stu-id="18dda-133">![Configure a workflow](media/intelligence-screen2-updated.png "Configure a workflow")</span></span>
   
1. <span data-ttu-id="18dda-134">**Үлгі шығысының параметрлері** қадамында келесі сипаттарды орнатыңыз:</span><span class="sxs-lookup"><span data-stu-id="18dda-134">In the **Model Output Parameters** step, set the following properties:</span></span>
   - <span data-ttu-id="18dda-135">Machine Learning Studio (классикалық)</span><span class="sxs-lookup"><span data-stu-id="18dda-135">Machine Learning Studio (classic)</span></span>
      1. <span data-ttu-id="18dda-136">Веб-қызметтің шығыс нәтижелері кіретін шығыс **Нысан атауын** енгізіңіз.</span><span class="sxs-lookup"><span data-stu-id="18dda-136">Enter the output **Entity name** you want web service output results to flow into.</span></span>
   - <span data-ttu-id="18dda-137">Azure Machine Learning</span><span class="sxs-lookup"><span data-stu-id="18dda-137">Azure Machine Learning</span></span>
      1. <span data-ttu-id="18dda-138">Үрдістер тізбегінің шығыс нәтижелері кіретін шығыс **Нысан атауын** енгізіңіз.</span><span class="sxs-lookup"><span data-stu-id="18dda-138">Enter the output **Entity name** you want pipeline output results to flow into.</span></span>
      1. <span data-ttu-id="18dda-139">Ашылмалы тізімнен топтама үрдістер тізбегінің **Шығыс деректер қоймасы параметрінің атауы** пәрменін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="18dda-139">Select the **Output data store parameter name** of your batch pipeline from the dropdown.</span></span>
      1. <span data-ttu-id="18dda-140">Ашылмалы тізімнен топтама үрдістер тізбегінің **Шығыс жолы параметрінің атауы** пәрменін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="18dda-140">Select the **Output Path parameter name** of your batch pipeline from the dropdown.</span></span>
      
      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="18dda-141">![Үлгі шығысының параметрлер бөлігі](media/intelligence-screen3-outputparameters.png "Үлгі шығысының параметрлер бөлігі")</span><span class="sxs-lookup"><span data-stu-id="18dda-141">![Model Output Parameter Pane](media/intelligence-screen3-outputparameters.png "Model Output Parameter Pane")</span></span>

1. <span data-ttu-id="18dda-142">Тұтынушыларды анықтайтын **Нәтижелердегі тұтынушы идентификаторы** ашылмалы тізіміндегі салыстыру төлсипатын таңдап, **Сақтау** опциясын басыңыз.</span><span class="sxs-lookup"><span data-stu-id="18dda-142">Select the matching attribute from the **Customer ID in results** drop-down list that identifies customers and select **Save**.</span></span>
   
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="18dda-143">![Нәтижелерді тұтынушы деректерімен байланыстыру бөлігі](media/intelligence-screen4-relatetocustomer.png "Нәтижелерді тұтынушы деректерімен байланыстыру бөлігі")</span><span class="sxs-lookup"><span data-stu-id="18dda-143">![Relate results to Customer data pane](media/intelligence-screen4-relatetocustomer.png "Relate results to Customer data pane")</span></span>

1. <span data-ttu-id="18dda-144">Жұмыс ағыны туралы мәліметтері бар **Жұмыс ағыны сақталған** экранын көресіз.</span><span class="sxs-lookup"><span data-stu-id="18dda-144">You'll see the **Workflow Saved** screen with details about the workflow.</span></span>    
   <span data-ttu-id="18dda-145">Azure Machine Learning үрдістер тізбегіне арналған жұмыс ағынын конфигурациялаған болсаңыз, аудитория түсініктері үрдістер тізбегін қамтитын жұмыс кеңістігіне қосылады.</span><span class="sxs-lookup"><span data-stu-id="18dda-145">If you configured a workflow for an Azure Machine Learning pipeline, audience insights will attach to the workspace that contains the pipeline.</span></span> <span data-ttu-id="18dda-146">Аудитория түсініктері Azure жұмыс кеңістігіндегі **Салымшы** рөлін алады.</span><span class="sxs-lookup"><span data-stu-id="18dda-146">Audience insights will get a **Contributor** role on the Azure workspace.</span></span>

1. <span data-ttu-id="18dda-147">**Дайын** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="18dda-147">Select **Done**.</span></span>

1. <span data-ttu-id="18dda-148">Енді жұмыс ағынын **Реттелетін үлгілер** бетінен іске қосуға болады.</span><span class="sxs-lookup"><span data-stu-id="18dda-148">You can now run the workflow from the **Custom Models** page.</span></span>

## <a name="edit-a-workflow"></a><span data-ttu-id="18dda-149">Жұмыс ағынын өңдеу</span><span class="sxs-lookup"><span data-stu-id="18dda-149">Edit a workflow</span></span>

1. <span data-ttu-id="18dda-150">**Реттелетін үлгілер** бетінде бастапқы жасалған жұмыс ағынынан кейінгі **Әрекеттер** бағанынан тік эллипсті таңдап, **Өңдеу** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="18dda-150">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created and select **Edit**.</span></span>

1. <span data-ttu-id="18dda-151">**Көрсетілетін атау** өрісіндегі жұмыс ағыныңыздың танымал атын жаңартуға болады, бірақ конфигурацияланған веб-қызметті немесе үрдістер тізбегін өзгерте алмайсыз.</span><span class="sxs-lookup"><span data-stu-id="18dda-151">You can update your workflow's recognizable name in the **Display name** field, but you can't change the configured web service or pipeline.</span></span> <span data-ttu-id="18dda-152">**Келесі** пәрменін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="18dda-152">Select **Next**.</span></span>

1. <span data-ttu-id="18dda-153">Әр **Веб қызметтің кірісі** үшін аудитория түсініктерінен сәйкес **Нысан** опциясын жаңарта аласыз.</span><span class="sxs-lookup"><span data-stu-id="18dda-153">For each **Web service input**, you can update the matching **Entity** from audience insights.</span></span> <span data-ttu-id="18dda-154">Содан кейін **Келесі** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="18dda-154">Then, select **Next**.</span></span>

1. <span data-ttu-id="18dda-155">**Үлгі шығысының параметрлері** қадамында келесі сипаттарды орнатыңыз:</span><span class="sxs-lookup"><span data-stu-id="18dda-155">In the **Model Output Parameters** step, set the following properties:</span></span>
   - <span data-ttu-id="18dda-156">Machine Learning Studio (классикалық)</span><span class="sxs-lookup"><span data-stu-id="18dda-156">Machine Learning Studio (classic)</span></span>
      1. <span data-ttu-id="18dda-157">Веб-қызметтің шығыс нәтижелері кіретін шығыс **Нысан атауын** енгізіңіз.</span><span class="sxs-lookup"><span data-stu-id="18dda-157">Enter the output **Entity name** you want web service output results to flow into.</span></span>
   - <span data-ttu-id="18dda-158">Azure Machine Learning</span><span class="sxs-lookup"><span data-stu-id="18dda-158">Azure Machine Learning</span></span>
      1. <span data-ttu-id="18dda-159">Үрдістер тізбегінің шығыс нәтижелері кіретін шығыс **Нысан атауын** енгізіңіз.</span><span class="sxs-lookup"><span data-stu-id="18dda-159">Enter the output **Entity name** you want pipeline output results to flow into.</span></span>
      1. <span data-ttu-id="18dda-160">Сынақ үрдістер тізбегі үшін **Шығыс деректер қоймасы параметрінің атауын** таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="18dda-160">Select the **Output data store parameter name** for your test pipeline.</span></span>
      1. <span data-ttu-id="18dda-161">Сынақ үрдістер тізбегі үшін **Шығыс жолы параметрінің атауын** таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="18dda-161">Select the **Output Path parameter name** for your test pipeline.</span></span>

1. <span data-ttu-id="18dda-162">Тұтынушыларды анықтайтын **Нәтижелердегі тұтынушы идентификаторы** ашылмалы тізіміндегі салыстыру төлсипатын таңдап, **Сақтау** опциясын басыңыз.</span><span class="sxs-lookup"><span data-stu-id="18dda-162">Select the matching attribute from the **Customer ID in results** drop-down list that identifies customers and select **Save**.</span></span>
   <span data-ttu-id="18dda-163">Тұтынушы нысанының тұтынушы идентификаторы бағанына ұқсас мәндері бар қорытынды нәтижесінен төлсипат таңдау керек.</span><span class="sxs-lookup"><span data-stu-id="18dda-163">You need to choose an attribute from the inference output with values similar to the Customer ID column of the Customer entity.</span></span> <span data-ttu-id="18dda-164">Егер деректер жиынында мұндай баған болмаса, жолды бірегей анықтайтын төлсипатты таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="18dda-164">If don't have such a column in your data set, choose an attribute that uniquely identifies the row.</span></span>

## <a name="run-a-workflow"></a><span data-ttu-id="18dda-165">Жұмыс үрдісін іске қосу</span><span class="sxs-lookup"><span data-stu-id="18dda-165">Run a workflow</span></span>

1. <span data-ttu-id="18dda-166">**Реттелетін үлгілер** бетінде бастапқы жасалған жұмыс ағынынан кейінгі **Әрекеттер** бағанынан тік эллипсті таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="18dda-166">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created.</span></span>

1. <span data-ttu-id="18dda-167">**Іске қосу** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="18dda-167">Select **Run**.</span></span>

<span data-ttu-id="18dda-168">Сонымен қатар жұмыс ағыны әрбір жоспарланған жаңартумен автоматты түрде іске қосылады.</span><span class="sxs-lookup"><span data-stu-id="18dda-168">Your workflow also runs automatically with every scheduled refresh.</span></span> <span data-ttu-id="18dda-169">[Жоспарланған жаңартуларды орнату](system.md#schedule-tab) туралы қосымша ақпарат.</span><span class="sxs-lookup"><span data-stu-id="18dda-169">Learn more about [setting up scheduled refreshes](system.md#schedule-tab).</span></span>

## <a name="delete-a-workflow"></a><span data-ttu-id="18dda-170">Жұмыс ағынын жою</span><span class="sxs-lookup"><span data-stu-id="18dda-170">Delete a workflow</span></span>

1. <span data-ttu-id="18dda-171">**Реттелетін үлгілер** бетінде бастапқы жасалған жұмыс ағынынан кейінгі **Әрекеттер** бағанынан тік эллипсті таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="18dda-171">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created.</span></span>

1. <span data-ttu-id="18dda-172">**Жою** параметрін таңдап, жоюды растаңыз.</span><span class="sxs-lookup"><span data-stu-id="18dda-172">Select **Delete** and confirm your deletion.</span></span>

<span data-ttu-id="18dda-173">Жұмыс ағыныңыз жойылады.</span><span class="sxs-lookup"><span data-stu-id="18dda-173">Your workflow will be deleted.</span></span> <span data-ttu-id="18dda-174">Жұмыс ағыны жасалған кездегі [нысан](entities.md) сақталады және оны **Нысандар** бетінде көруге болады.</span><span class="sxs-lookup"><span data-stu-id="18dda-174">The [entity](entities.md) that was created when you created the workflow persists, and can be viewed from the **Entities** page.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]