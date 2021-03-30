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
# <a name="use-azure-machine-learning-based-models"></a>Azure Machine Learning негізіндегі үлгілерді пайдаланыңыз

Dynamics 365 Customer Insights бағдарламасындағы бірыңғай деректер қосымша бизнес түсініктерін қалыптастыра алатын компьютерлік оқыту модельдерін құрудың көзі болып табылады. Өз реттелетін үлгілеріңізі пайдалану үшін Customer Insights жүйесі Machine Learning Studio (классикалық) және Azure Machine Learning бағдарламаларымен бірігеді. Machine Learning Studio (классикалық) бағдарламасында құрылған тәжірибелер мысалдары үшін [Machine Learning Studio (классикалық) тәжірибелері](machine-learning-studio-experiments.md) бөлімін қараңыз. 

## <a name="prerequisites"></a>Алғышарттар

- Customer Insights бағдарламасына қатынасу
- Белсенді Azure Enterprise жазылымы
- [Бірыңғай тұтынушы профильдері](data-unification.md)
- [Нысанды Azure Blob қоймасына экспорттау](export-azure-blob-storage.md) конфигурацияланған

## <a name="set-up-azure-machine-learning-workspace"></a>Azure Machine Learning жұмыс кеңістігін орнату

1. Жұмыс кеңістігін жасау үшін түрлі опциялар бойынша [Azure Machine Learning жұмыс кеңістігін жасау](/azure/machine-learning/concept-workspace#-create-a-workspace) бөлімін қараңыз. Үздік өнімділікке қол жеткізу мақсатында географиялық тұрғыдан сіздің Customer Insights ортаңызға жақын Azure аймағында жұмыс аймағын жасаңыз.

1. Жұмыс кеңістігіне [Azure Machine Learning Studio](https://ml.azure.com/) бағдарламасы арқылы қатынасыңыз. Жұмыс кеңістігімен [өазара әрекеттесудің](/azure/machine-learning/concept-workspace#tools-for-workspace-interaction) бірнеше жолдары бар.

## <a name="work-with-azure-machine-learning-designer"></a>Azure Machine Learning құрастырушысымен жұмыс істеңіз

Azure Machine Learning құрастырушысы Machine Learning Studio (классикалық) жүйесіне ұқсас деректер жиынтығы мен модульдерін сүйреп апаратын көрнекі кенеп бағдарламасын ұсынады. Құрастырушыдан жасалған топтамалық үдерістер тізбегі егер олар сәйкесінше конфигурацияланған болса Customer Insights жүйесіне бірігуі мүмкін. 
   
## <a name="working-with-azure-machine-learning-sdk"></a>Azure Machine Learning SDK жүйесімен жұмыс істеу

Деректерді зерттеушілер немесе AI әзірлеушілері компьютерлік оқыту жұмыс ағындарын құру үшін [Azure Machine Learning SDK](/python/api/overview/azure/ml/?preserve-view=true&view=azure-ml-py) жүйесін пайдаланады. Қазіргі уақытта SDK арқылы оқытылған үлгілерді Customer Insights жүйесімен тікелей біріктіру мүмкін емес. Осы үлгіні тұтынатын топтамалық қорытынды үдерістер тізбегі Customer Insights жүйесімен біріктіру үшін қажет.

## <a name="batch-pipeline-requirements-to-integrate-with-customer-insights"></a>Customer Insights жүйесімен біріктіруге арналған топтамалық үдерістер тізбегіне қойылатын талаптар

### <a name="dataset-configuration"></a>Деректер жинағы конфигурациясы

Customer Insights жүйесінен нысан деректерін пайдалану үшін топтамалық қорытынды құбырға деректер жиынтығын жасау қажет. Бұл деректер жиынтығы жұмыс кеңістігінде тіркелуі керек. Қазіргі уақытта біз тек .csv пішіміндегі [кестелік деректер жиынтығына](/azure/machine-learning/how-to-create-register-datasets#tabulardataset) қолдау көрсетеміз. Нысан деректеріне сәйкес келетін деректер жиынтығын үдерістер тізбегі ретінде параметрленуі қажет.
   
* Құрастырушыдағы деректер жиынтығы параметрлері
   
     Құрастырушыда параметрге атау берілетін **Бағандарды деректер жиынтығында таңдау** терезесін ашып, **Үдерістер тізбегі параметрі ретінде орнату** опциясын таңдаңыз.

     > [!div class="mx-imgBorder"]
     > ![Құрастырушыдағы деректер жиынтығын параметрлеу](media/intelligence-designer-dataset-parameters.png "Құрастырушыдағы деректер жиынтығын параметрлеу")
   
* SDK ішіндегі деректер жиынтығының параметрі (Python)
   
   ```python
   HotelStayActivity_dataset = Dataset.get_by_name(ws, name='Hotel Stay Activity Data')
   HotelStayActivity_pipeline_param = PipelineParameter(name="HotelStayActivity_pipeline_param", default_value=HotelStayActivity_dataset)
   HotelStayActivity_ds_consumption = DatasetConsumptionConfig("HotelStayActivity_dataset", HotelStayActivity_pipeline_param)
   ```

### <a name="batch-inference-pipeline"></a>Топтамалық қорытынды үдерістер тізбегі
  
* Құрастырушыда оқыту үдерістер тізбегін қорытынды үдерістер тізбегін жасау немесе жаңарту үшін пайдалануға болады. Қазіргі уақытта тек топтамалық қорытынды үдерістер тізбегіне қолдау көрсетіледі.

* SDK көмегімен үдерістер тізбегін соңғы нүктеге дейін жариялауға болады. Қазіргі уақытта Customer Insights Machine Learning жұмыс кеңістігінде топтамалық үдерістер тізбегінің соңғы нүктесінде әдепкі үдерістер тізбегімен біріктіріледі.
   
   ```python
   published_pipeline = pipeline.publish(name="ChurnInferencePipeline", description="Published Churn Inference pipeline")
   pipeline_endpoint = PipelineEndpoint.get(workspace=ws, name="ChurnPipelineEndpoint") 
   pipeline_endpoint.add_default(pipeline=published_pipeline)
   ```

### <a name="import-pipeline-data-into-customer-insights"></a>Үдерістер тізбегі деректерін Customer Insights жүйесіне импорттау

* Құрастырушы Azure сақтау құралына экспортталатын үдерістер тізбегінің шығысына мүмкіндік беретін [Деректер модулін экспорттауды](/azure/machine-learning/algorithm-module-reference/export-data) ұсынады. Қазіргі уақытта модуль **Azure Blob сақтау құралы** түріндегі дерекқорын пайдаланып, **Дерекқор** және қатысты **Жол** элементтерін параметрлеуі қажет. Customer Insights жүйесі дерекқормен және өнімге қолжетімді жолмен үдерістер тізбегін орындау кезінде осы екі параметрді де алдын ала анықтайды.
   > [!div class="mx-imgBorder"]
   > ![Деректер модулінің конфигурациясын экспорттау](media/intelligence-designer-importdata.png "Деректер модулінің конфигурациясын экспорттау")
   
* Қортынды шығысын кодты пайдаланып жазғанда, нәтижені жұмыс кеңістігіндегі *тіркелген дерекқор* ішіндегі жолға жүктеп салуға болады. Егер жол мен дерекқор үдерістер тізбегінде параметрленсе, Customer insights жүйесі қорытынды нәтижесін оқып, импорттай алады. Қазіргі уақытта csv форматындағы бір кестелік нәтижеге қолдау көрсетіледі. Жолда каталог пен файл атауы болуы тиіс.

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