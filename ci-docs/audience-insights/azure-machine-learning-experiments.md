---
title: Azure Machine Learning тәжірибелері
description: Dynamics 365 Customer Insights бағдарламасындағы Azure Machine Learning негізіндегі үлгілерді пайдаланыңыз.
ms.date: 11/30/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: naravill
ms.author: naravill
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: edd2cf488b52cef87b09b90336e48fdc7f470a68
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597426"
---
# <a name="use-azure-machine-learning-based-models"></a><span data-ttu-id="45610-103">Azure Machine Learning негізіндегі үлгілерді пайдаланыңыз</span><span class="sxs-lookup"><span data-stu-id="45610-103">Use Azure Machine Learning-based models</span></span>

<span data-ttu-id="45610-104">Dynamics 365 Customer Insights бағдарламасындағы бірыңғай деректер қосымша бизнес түсініктерін қалыптастыра алатын компьютерлік оқыту модельдерін құрудың көзі болып табылады.</span><span class="sxs-lookup"><span data-stu-id="45610-104">The unified data in Dynamics 365 Customer Insights is a source for building machine learning models that can generate additional business insights.</span></span> <span data-ttu-id="45610-105">Өз реттелетін үлгілеріңізі пайдалану үшін Customer Insights жүйесі Machine Learning Studio (классикалық) және Azure Machine Learning бағдарламаларымен бірігеді.</span><span class="sxs-lookup"><span data-stu-id="45610-105">Customer Insights integrates with Machine Learning Studio (classic) and Azure Machine Learning to use your own custom models.</span></span> <span data-ttu-id="45610-106">Machine Learning Studio (классикалық) бағдарламасында құрылған тәжірибелер мысалдары үшін [Machine Learning Studio (классикалық) тәжірибелері](machine-learning-studio-experiments.md) бөлімін қараңыз.</span><span class="sxs-lookup"><span data-stu-id="45610-106">Refer to [Machine Learning Studio (classic) experiments](machine-learning-studio-experiments.md) for examples of experiments built on Machine Learning Studio (classic).</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="45610-107">Алғышарттар</span><span class="sxs-lookup"><span data-stu-id="45610-107">Prerequisites</span></span>

- <span data-ttu-id="45610-108">Customer Insights бағдарламасына қатынасу</span><span class="sxs-lookup"><span data-stu-id="45610-108">Access to Customer Insights</span></span>
- <span data-ttu-id="45610-109">Белсенді Azure Enterprise жазылымы</span><span class="sxs-lookup"><span data-stu-id="45610-109">Active Azure Enterprise subscription</span></span>
- [<span data-ttu-id="45610-110">Бірыңғай тұтынушы профильдері</span><span class="sxs-lookup"><span data-stu-id="45610-110">Unified customer profiles</span></span>](data-unification.md)
- <span data-ttu-id="45610-111">[Нысанды Azure Blob қоймасына экспорттау](export-azure-blob-storage.md) конфигурацияланған</span><span class="sxs-lookup"><span data-stu-id="45610-111">[Entity export to Azure Blob storage](export-azure-blob-storage.md) configured</span></span>

## <a name="set-up-azure-machine-learning-workspace"></a><span data-ttu-id="45610-112">Azure Machine Learning жұмыс кеңістігін орнату</span><span class="sxs-lookup"><span data-stu-id="45610-112">Set up Azure Machine Learning workspace</span></span>

1. <span data-ttu-id="45610-113">Жұмыс кеңістігін жасау үшін түрлі опциялар бойынша [Azure Machine Learning жұмыс кеңістігін жасау](/azure/machine-learning/concept-workspace#-create-a-workspace) бөлімін қараңыз.</span><span class="sxs-lookup"><span data-stu-id="45610-113">See [create a Azure Machine Learning workspace](/azure/machine-learning/concept-workspace#-create-a-workspace) for different options to create the workspace.</span></span> <span data-ttu-id="45610-114">Үздік өнімділікке қол жеткізу мақсатында географиялық тұрғыдан сіздің Customer Insights ортаңызға жақын Azure аймағында жұмыс аймағын жасаңыз.</span><span class="sxs-lookup"><span data-stu-id="45610-114">For best performance, create the workspace in an Azure region that is geographically closest to your Customer Insights environment.</span></span>

1. <span data-ttu-id="45610-115">Жұмыс кеңістігіне [Azure Machine Learning Studio](https://ml.azure.com/) бағдарламасы арқылы қатынасыңыз.</span><span class="sxs-lookup"><span data-stu-id="45610-115">Access your workspace through the [Azure Machine Learning Studio](https://ml.azure.com/).</span></span> <span data-ttu-id="45610-116">Жұмыс кеңістігімен [өазара әрекеттесудің](/azure/machine-learning/concept-workspace#tools-for-workspace-interaction) бірнеше жолдары бар.</span><span class="sxs-lookup"><span data-stu-id="45610-116">There are several [ways to interact](/azure/machine-learning/concept-workspace#tools-for-workspace-interaction) with your workspace.</span></span>

## <a name="work-with-azure-machine-learning-designer"></a><span data-ttu-id="45610-117">Azure Machine Learning құрастырушысымен жұмыс істеңіз</span><span class="sxs-lookup"><span data-stu-id="45610-117">Work with Azure Machine Learning designer</span></span>

<span data-ttu-id="45610-118">Azure Machine Learning құрастырушысы Machine Learning Studio (классикалық) жүйесіне ұқсас деректер жиынтығы мен модульдерін сүйреп апаратын көрнекі кенеп бағдарламасын ұсынады.</span><span class="sxs-lookup"><span data-stu-id="45610-118">Azure Machine Learning designer provides a visual canvas where you can drag and drop datasets and modules, similar to Machine Learning Studio (classic).</span></span> <span data-ttu-id="45610-119">Құрастырушыдан жасалған топтамалық үдерістер тізбегі егер олар сәйкесінше конфигурацияланған болса Customer Insights жүйесіне бірігуі мүмкін.</span><span class="sxs-lookup"><span data-stu-id="45610-119">A batch pipeline created from the designer can be integrated into Customer Insights if they are configured accordingly.</span></span> 
   
## <a name="working-with-azure-machine-learning-sdk"></a><span data-ttu-id="45610-120">Azure Machine Learning SDK жүйесімен жұмыс істеу</span><span class="sxs-lookup"><span data-stu-id="45610-120">Working with Azure Machine Learning SDK</span></span>

<span data-ttu-id="45610-121">Деректерді зерттеушілер немесе AI әзірлеушілері компьютерлік оқыту жұмыс ағындарын құру үшін [Azure Machine Learning SDK](/python/api/overview/azure/ml/?preserve-view=true&view=azure-ml-py) жүйесін пайдаланады.</span><span class="sxs-lookup"><span data-stu-id="45610-121">Data scientists and AI developers use the [Azure Machine Learning SDK](/python/api/overview/azure/ml/?preserve-view=true&view=azure-ml-py) to build machine learning workflows.</span></span> <span data-ttu-id="45610-122">Қазіргі уақытта SDK арқылы оқытылған үлгілерді Customer Insights жүйесімен тікелей біріктіру мүмкін емес.</span><span class="sxs-lookup"><span data-stu-id="45610-122">Currently, models trained using the SDK can't be integrated directly with Customer Insights.</span></span> <span data-ttu-id="45610-123">Осы үлгіні тұтынатын топтамалық қорытынды үдерістер тізбегі Customer Insights жүйесімен біріктіру үшін қажет.</span><span class="sxs-lookup"><span data-stu-id="45610-123">A batch inference pipeline that consumes that model is required for integration with Customer Insights.</span></span>

## <a name="batch-pipeline-requirements-to-integrate-with-customer-insights"></a><span data-ttu-id="45610-124">Customer Insights жүйесімен біріктіруге арналған топтамалық үдерістер тізбегіне қойылатын талаптар</span><span class="sxs-lookup"><span data-stu-id="45610-124">Batch pipeline requirements to integrate with Customer Insights</span></span>

### <a name="dataset-configuration"></a><span data-ttu-id="45610-125">Деректер жинағы конфигурациясы</span><span class="sxs-lookup"><span data-stu-id="45610-125">Dataset Configuration</span></span>

<span data-ttu-id="45610-126">Customer Insights жүйесінен нысан деректерін пайдалану үшін топтамалық қорытынды құбырға деректер жиынтығын жасау қажет.</span><span class="sxs-lookup"><span data-stu-id="45610-126">You need to create datasets to use entity data from Customer Insights to your batch inference pipeline.</span></span> <span data-ttu-id="45610-127">Бұл деректер жиынтығы жұмыс кеңістігінде тіркелуі керек.</span><span class="sxs-lookup"><span data-stu-id="45610-127">These datasets need to be registered in the workspace.</span></span> <span data-ttu-id="45610-128">Қазіргі уақытта біз тек .csv пішіміндегі [кестелік деректер жиынтығына](/azure/machine-learning/how-to-create-register-datasets#tabulardataset) қолдау көрсетеміз.</span><span class="sxs-lookup"><span data-stu-id="45610-128">Currently, we only support [tabular datasets](/azure/machine-learning/how-to-create-register-datasets#tabulardataset) in .csv format.</span></span> <span data-ttu-id="45610-129">Нысан деректеріне сәйкес келетін деректер жиынтығын үдерістер тізбегі ретінде параметрленуі қажет.</span><span class="sxs-lookup"><span data-stu-id="45610-129">The datasets that correspond to entity data need to be parameterized as a pipeline parameter.</span></span>
   
* <span data-ttu-id="45610-130">Құрастырушыдағы деректер жиынтығы параметрлері</span><span class="sxs-lookup"><span data-stu-id="45610-130">Dataset parameters in Designer</span></span>
   
     <span data-ttu-id="45610-131">Құрастырушыда параметрге атау берілетін **Бағандарды деректер жиынтығында таңдау** терезесін ашып, **Үдерістер тізбегі параметрі ретінде орнату** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="45610-131">In the designer, open **Select Columns in Dataset** and select **Set as pipeline parameter** where you provide a name for the parameter.</span></span>

     > [!div class="mx-imgBorder"]
     > <span data-ttu-id="45610-132">![Құрастырушыдағы деректер жиынтығын параметрлеу](media/intelligence-designer-dataset-parameters.png "Құрастырушыдағы деректер жиынтығын параметрлеу")</span><span class="sxs-lookup"><span data-stu-id="45610-132">![Dataset parameterization in designer](media/intelligence-designer-dataset-parameters.png "Dataset parameterization in designer")</span></span>
   
* <span data-ttu-id="45610-133">SDK ішіндегі деректер жиынтығының параметрі (Python)</span><span class="sxs-lookup"><span data-stu-id="45610-133">Dataset parameter in SDK (Python)</span></span>
   
   ```python
   HotelStayActivity_dataset = Dataset.get_by_name(ws, name='Hotel Stay Activity Data')
   HotelStayActivity_pipeline_param = PipelineParameter(name="HotelStayActivity_pipeline_param", default_value=HotelStayActivity_dataset)
   HotelStayActivity_ds_consumption = DatasetConsumptionConfig("HotelStayActivity_dataset", HotelStayActivity_pipeline_param)
   ```

### <a name="batch-inference-pipeline"></a><span data-ttu-id="45610-134">Топтамалық қорытынды үдерістер тізбегі</span><span class="sxs-lookup"><span data-stu-id="45610-134">Batch inference pipeline</span></span>
  
* <span data-ttu-id="45610-135">Құрастырушыда оқыту үдерістер тізбегін қорытынды үдерістер тізбегін жасау немесе жаңарту үшін пайдалануға болады.</span><span class="sxs-lookup"><span data-stu-id="45610-135">In the designer, a training pipeline can be used to create or update an inference pipeline.</span></span> <span data-ttu-id="45610-136">Қазіргі уақытта тек топтамалық қорытынды үдерістер тізбегіне қолдау көрсетіледі.</span><span class="sxs-lookup"><span data-stu-id="45610-136">Currently, only batch inference pipelines are supported.</span></span>

* <span data-ttu-id="45610-137">SDK көмегімен үдерістер тізбегін соңғы нүктеге дейін жариялауға болады.</span><span class="sxs-lookup"><span data-stu-id="45610-137">Using the SDK, you can publish the pipeline to an endpoint.</span></span> <span data-ttu-id="45610-138">Қазіргі уақытта Customer Insights Machine Learning жұмыс кеңістігінде топтамалық үдерістер тізбегінің соңғы нүктесінде әдепкі үдерістер тізбегімен біріктіріледі.</span><span class="sxs-lookup"><span data-stu-id="45610-138">Currently, Customer Insights integrates with the default pipeline in a batch pipeline endpoint in the Machine Learning workspace.</span></span>
   
   ```python
   published_pipeline = pipeline.publish(name="ChurnInferencePipeline", description="Published Churn Inference pipeline")
   pipeline_endpoint = PipelineEndpoint.get(workspace=ws, name="ChurnPipelineEndpoint") 
   pipeline_endpoint.add_default(pipeline=published_pipeline)
   ```

### <a name="import-pipeline-data-into-customer-insights"></a><span data-ttu-id="45610-139">Үдерістер тізбегі деректерін Customer Insights жүйесіне импорттау</span><span class="sxs-lookup"><span data-stu-id="45610-139">Import pipeline data into Customer Insights</span></span>

* <span data-ttu-id="45610-140">Құрастырушы Azure сақтау құралына экспортталатын үдерістер тізбегінің шығысына мүмкіндік беретін [Деректер модулін экспорттауды](/azure/machine-learning/algorithm-module-reference/export-data) ұсынады.</span><span class="sxs-lookup"><span data-stu-id="45610-140">The designer provides the [Export Data module](/azure/machine-learning/algorithm-module-reference/export-data) that allows the output of a pipeline to be exported to Azure storage.</span></span> <span data-ttu-id="45610-141">Қазіргі уақытта модуль **Azure Blob сақтау құралы** түріндегі дерекқорын пайдаланып, **Дерекқор** және қатысты **Жол** элементтерін параметрлеуі қажет.</span><span class="sxs-lookup"><span data-stu-id="45610-141">Currently, the module must use the datastore type **Azure Blob Storage** and parameterize the **Datastore** and relative **Path**.</span></span> <span data-ttu-id="45610-142">Customer Insights жүйесі дерекқормен және өнімге қолжетімді жолмен үдерістер тізбегін орындау кезінде осы екі параметрді де алдын ала анықтайды.</span><span class="sxs-lookup"><span data-stu-id="45610-142">Customer Insights overrides both these parameters during pipeline execution with a datastore and path that is accessible to the product.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="45610-143">![Деректер модулінің конфигурациясын экспорттау](media/intelligence-designer-importdata.png "Деректер модулінің конфигурациясын экспорттау")</span><span class="sxs-lookup"><span data-stu-id="45610-143">![Export Data Module Configuration](media/intelligence-designer-importdata.png "Export Data Module Configuration")</span></span>
   
* <span data-ttu-id="45610-144">Қортынды шығысын кодты пайдаланып жазғанда, нәтижені жұмыс кеңістігіндегі *тіркелген дерекқор* ішіндегі жолға жүктеп салуға болады.</span><span class="sxs-lookup"><span data-stu-id="45610-144">When writing the inference output using code, you can upload the output to the a path within a *registered datastore* in the workspace.</span></span> <span data-ttu-id="45610-145">Егер жол мен дерекқор үдерістер тізбегінде параметрленсе, Customer insights жүйесі қорытынды нәтижесін оқып, импорттай алады.</span><span class="sxs-lookup"><span data-stu-id="45610-145">If the path and datastore are parameterized in the pipeline, Customer insights will be able to read and import the inference output.</span></span> <span data-ttu-id="45610-146">Қазіргі уақытта csv форматындағы бір кестелік нәтижеге қолдау көрсетіледі.</span><span class="sxs-lookup"><span data-stu-id="45610-146">Currently, a single tabular output in csv format is supported.</span></span> <span data-ttu-id="45610-147">Жолда каталог пен файл атауы болуы тиіс.</span><span class="sxs-lookup"><span data-stu-id="45610-147">The path must include the directory and filename.</span></span>

   ```python
   # In Pipeline setup script
      OutputPathParameter = PipelineParameter(name="output_path", default_value="HotelChurnOutput/HotelChurnOutput.csv")
      OutputDatastoreParameter = PipelineParameter(name="output_datastore", default_value="workspaceblobstore")
   ...
   # In pipeline execution script
      run = Run.get_context()
      ws = run.experiment.workspace
      datastore = Datastore.get(ws, output_datastore) # output_datastore is parameterized
      directory_name =  os.path.dirname(output_path)  # output_path is parameterized.
      
      # Datastore.upload() or Dataset.File.upload_directory() are supported methods to uplaod the data
      # datastore.upload(src_dir=<<working directory>>, target_path=directory_name, overwrite=False, show_progress=True)
      output_dataset = Dataset.File.upload_directory(src_dir=<<working directory>>, target = (datastore, directory_name)) # Remove trailing "/" from directory_name
   ```


[!INCLUDE[footer-include](../includes/footer-banner.md)]