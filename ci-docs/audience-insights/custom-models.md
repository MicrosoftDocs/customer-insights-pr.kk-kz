---
title: Реттелетін компьютерлік оқыту үлгілері | Microsoft Docs
description: Dynamics 365 Customer Insights бағдарламасында Azure Machine Learning қызметінен реттелетін үлгілермен жұмыс жасаңыз.
ms.date: 11/19/2020
ms.reviewer: zacook
ms.service: dynamics-365-ai
ms.topic: article
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: ef248086b30b870359970529a7bfb37792be62d5
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668910"
---
# <a name="custom-machine-learning-models"></a>Реттелетін компьютерлік оқыту үлгілері

**Сараптау** > **Реттелетін үлгілер** тармағы Azure Machine Learning үлгілеріне байланысты жұмыс ағындарын басқаруға мүмкіндік береді. Жұмыс ағындары сізге түсініктер құруға болатын деректерді таңдауға және нәтижелерді тұтынушының бірыңғай деректерімен салыстыруға көмектеседі. Реттелетін ML үлгілерін құру туралы қосымша ақпаратты [Azure Machine Learning бағдарламасына негізделген үлгілерді пайдалану](azure-machine-learning-experiments.md) бөлімінен қараңыз.

## <a name="responsible-ai"></a>Жауапты жасанды интелект

Болжамдар тұтынушылардың жақсы тәжірибесін жасауға, бизнес мүмкіндіктерін жақсартуға және кіріс ағындарына мүмкіндіктер ұсынады. Болжам мәнін оның әсері мен этикалық тәртіпте енгізілуі мүмкін жағымсыздықтарға теңестіруді қатаң түрде ұсынамыз. Microsoft корпорациясының [Жауапты жасанды интеллектке жүгіну](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6) жолы туралы қосымша ақпарат. Сонымен қатар Azure Machine Learning бағдарламасына тән [жауапты компьютерлік оқытуларға арналған әдістер мен процестер](https://docs.microsoft.com/azure/machine-learning/concept-responsible-ml) туралы біле аласыздар.

## <a name="prerequisites"></a>Алғышарттар

- Қазіргі уақытта бұл функция [Machine Learning Studio (классикалық)](https://studio.azureml.net) және [ Azure Machine Learning топтамалық құбырлары ](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines) арқылы жарияланған веб-қызметтерді қолдайды.

- Бұл мүмкіндікті пайдалану үшін сізге Azure Studio данасымен байланысты Azure Data Lake Gen2 сақтау орны тіркелгісі қажет. Қосымша ақпарат алу үшін [Azure Data Lake Storage Gen2 сақтау орны тіркелгісін жасау](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-quickstart-create-account) бөлімін қараңыз

## <a name="add-a-new-workflow"></a>Жаңа жұмыс ағынын қосу

1. **Интеллект** > **Реттелетін үлгілер** тармағына өтіп, **Жаңа жұмыс ағыны** параметрін таңдаңыз.

1. **Аты** өрісінде реттелетін үлгіге анықталатын ат беріңіз.

   > [!div class="mx-imgBorder"]
   > ![Жаңа жұмыс ағыны тақтасының скриншоты](media/new-workflowv2.png "Жаңа жұмыс ағыны тақтасының скриншоты")

1. **Веб-қызметті қамтитын қатысушы** ішіндегі веб-қызметтен тұратын ұйымды таңдаңыз.

1. Azure Machine Learning жазылымы Customer Insights бағдарламасынан өзге қатысушыда болса, таңдалған ұйымның деректемелерімен **Жүйеге кіру** параметрін таңдаңыз.

1. Веб-қызметіңізбен байланысты **Жұмыс кеңістіктері** пәрменін таңдаңыз. Берілген екі бөлім бар, олардың бірі Azure Machine Learning v1 (Machine Learning Studio (классикалық)) және Azure Machine Learning v2 (Azure Machine Learning). Егер сіз Machine Learning Studio (классикалық) веб-қызметі үшін қай жұмыс кеңістігінің дұрыс екеніне сенімді болмасаңыз, **Кез келген** пәрменін таңдаңыз.

1. **Үлгіңізді қамтитын веб-қызмет** ашылмалы тізімінен Machine Learning Studio (классикалық) веб-қызметін немесе Azure Machine Learning үрдістер тізбегін таңдаңыз. Содан кейін **Келесі** түймешігін таңдаңыз.
   - [Machine Learning Studio (классикалық) бағдарламасында веб-қызметті жариялау](https://docs.microsoft.com/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service) туралы қосымша ақпарат
   - [Azure Machine Learning бағдарламасындағы үрдістер тізбегін құрастырушы көмегімен жариялау](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) немесе [SDK](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk) туралы қосымша ақпарат. 
     > [!NOTE]
     > Үрдістер тізбегі [үрдістер тізбегінің соңғы нүктесі](https://docs.microsoft.com/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run) астында жариялануы тиіс.

1. Әр **Веб-қызмет кірісі** үшін аудитория түсініктерінен сәйкес **Нысан** опциясын таңдап, **Келесі** пәрменін басыңыз.

   > [!div class="mx-imgBorder"]
   > ![Жұмыс ағынын конфигурациялау](media/intelligence-screen2-updated.png "Жұмыс ағынын конфигурациялау")

1. **Үлгі шығысының параметрлері** қадамында келесі сипаттарды орнатыңыз:
   - Machine Learning Studio (классикалық)
      1. Веб-қызметтің шығыс нәтижелері кіретін шығыс **Нысан атауын** енгізіңіз.
   - Azure Machine Learning
      1. Үрдістер тізбегінің шығыс нәтижелері кіретін шығыс **Нысан атауын** енгізіңіз.
      1. Ашылмалы тізімнен топтама үрдістер тізбегінің **Шығыс деректер қоймасы параметрінің атауы** пәрменін таңдаңыз.
      1. Ашылмалы тізімнен топтама үрдістер тізбегінің **Шығыс жолы параметрінің атауы** пәрменін таңдаңыз.
      
      > [!div class="mx-imgBorder"]
      > ![Үлгі шығысының параметрлер бөлігі](media/intelligence-screen3-outputparameters.png "Үлгі шығысының параметрлер бөлігі")

1. Тұтынушыларды анықтайтын **Нәтижелердегі тұтынушы идентификаторы** ашылмалы тізіміндегі салыстыру төлсипатын таңдап, **Сақтау** опциясын басыңыз.
   
   > [!div class="mx-imgBorder"]
   > ![Нәтижелерді тұтынушы деректерімен байланыстыру бөлігі](media/intelligence-screen4-relatetocustomer.png "Нәтижелерді тұтынушы деректерімен байланыстыру бөлігі")

1. Жұмыс ағыны туралы мәліметтері бар **Жұмыс ағыны сақталған** экранын көресіз.    
   Azure Machine Learning үрдістер тізбегіне арналған жұмыс ағынын конфигурациялаған болсаңыз, аудитория түсініктері үрдістер тізбегін қамтитын жұмыс кеңістігіне қосылады. Аудитория түсініктері Azure жұмыс кеңістігіндегі **Салымшы** рөлін алады.

1. **Дайын** опциясын таңдаңыз.

1. Енді жұмыс ағынын **Реттелетін үлгілер** бетінен іске қосуға болады.

## <a name="edit-a-workflow"></a>Жұмыс ағынын өңдеу

1. **Реттелетін үлгілер** бетінде бастапқы жасалған жұмыс ағынынан кейінгі **Әрекеттер** бағанынан тік эллипсті таңдап, **Өңдеу** параметрін таңдаңыз.

1. **Көрсетілетін атау** өрісіндегі жұмыс ағыныңыздың танымал атын жаңартуға болады, бірақ конфигурацияланған веб-қызметті немесе үрдістер тізбегін өзгерте алмайсыз. **Келесі** пәрменін таңдаңыз.

1. Әр **Веб қызметтің кірісі** үшін аудитория түсініктерінен сәйкес **Нысан** опциясын жаңарта аласыз. Содан кейін **Келесі** түймешігін таңдаңыз.

1. **Үлгі шығысының параметрлері** қадамында келесі сипаттарды орнатыңыз:
   - Machine Learning Studio (классикалық)
      1. Веб-қызметтің шығыс нәтижелері кіретін шығыс **Нысан атауын** енгізіңіз.
   - Azure Machine Learning
      1. Үрдістер тізбегінің шығыс нәтижелері кіретін шығыс **Нысан атауын** енгізіңіз.
      1. Сынақ үрдістер тізбегі үшін **Шығыс деректер қоймасы параметрінің атауын** таңдаңыз.
      1. Сынақ үрдістер тізбегі үшін **Шығыс жолы параметрінің атауын** таңдаңыз.

1. Тұтынушыларды анықтайтын **Нәтижелердегі тұтынушы идентификаторы** ашылмалы тізіміндегі салыстыру төлсипатын таңдап, **Сақтау** опциясын басыңыз.
   Тұтынушы нысанының тұтынушы идентификаторы бағанына ұқсас мәндері бар қорытынды нәтижесінен төлсипат таңдау керек. Егер деректер жиынында мұндай баған болмаса, жолды бірегей анықтайтын төлсипатты таңдаңыз.

## <a name="run-a-workflow"></a>Жұмыс үрдісін іске қосу

1. **Реттелетін үлгілер** бетінде бастапқы жасалған жұмыс ағынынан кейінгі **Әрекеттер** бағанынан тік эллипсті таңдаңыз.

1. **Іске қосу** параметрін таңдаңыз.

Сонымен қатар жұмыс ағыны әрбір жоспарланған жаңартумен автоматты түрде іске қосылады. [Жоспарланған жаңартуларды орнату](system.md#schedule-tab) туралы қосымша ақпарат.

## <a name="delete-a-workflow"></a>Жұмыс ағынын жою

1. **Реттелетін үлгілер** бетінде бастапқы жасалған жұмыс ағынынан кейінгі **Әрекеттер** бағанынан тік эллипсті таңдаңыз.

1. **Жою** параметрін таңдап, жоюды растаңыз.

Жұмыс ағыныңыз жойылады. Жұмыс ағыны жасалған кездегі [нысан](entities.md) сақталады және оны **Нысандар** бетінде көруге болады.