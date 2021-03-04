---
title: Common Data Model деректерін Azure Data Lake тіркелгісіне қосыңыз
description: Azure Data Lake Storage арқылы Common Data Model деректерімен жұмыс істеңіз.
ms.date: 05/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: 247e4d9c47ff2373065ebf3c6d554323e45a120b
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267867"
---
# <a name="connect-to-a-common-data-model-folder-using-an-azure-data-lake-account"></a><span data-ttu-id="de050-103">Common Data Model қалтасын Azure Data Lake тіркелгісі көмегімен қосу</span><span class="sxs-lookup"><span data-stu-id="de050-103">Connect to a Common Data Model folder using an Azure Data Lake account</span></span>

<span data-ttu-id="de050-104">Бұл мақалада Azure Data Lake Storage Gen2 тіркелгісін пайдаланып Common Data Model қалтасынан деректерді қабылдау жолы туралы ақпарат беріледі.</span><span class="sxs-lookup"><span data-stu-id="de050-104">This article provides information on how to ingest data from a Common Data Model folder using your Azure Data Lake Storage Gen2 account.</span></span>

## <a name="important-considerations"></a><span data-ttu-id="de050-105">Маңызды жайттар</span><span class="sxs-lookup"><span data-stu-id="de050-105">Important considerations</span></span>

- <span data-ttu-id="de050-106">Azure Data Lake ішіндегі деректер Common Data Model стандартына сәйкес келуі керек.</span><span class="sxs-lookup"><span data-stu-id="de050-106">Data in your Azure Data Lake needs to follow the Common Data Model standard.</span></span> <span data-ttu-id="de050-107">Қазіргі уақытта басқа пішімдерге қолдау көрсетілмейді.</span><span class="sxs-lookup"><span data-stu-id="de050-107">Other formats aren't supported at the moment.</span></span>

- <span data-ttu-id="de050-108">Деректерді қабылдау тек Azure Data Lake *Gen2* сақтау құралы тіркелгілеріне қолдау көрсетеді.</span><span class="sxs-lookup"><span data-stu-id="de050-108">Data ingestion supports Azure Data Lake *Gen2* storage accounts exclusively.</span></span> <span data-ttu-id="de050-109">Деректерді қабылдау үшін Azure Data Lake Gen1 сақтау тіркелгілерін пайдалану мүмкін емес.</span><span class="sxs-lookup"><span data-stu-id="de050-109">You can't use Azure Data Lake Gen1 storage accounts to ingest data.</span></span>

- <span data-ttu-id="de050-110">Azure субъек-қызметімен аутентификациялау үшін оның қатысушыда конфигурацияланғандығына көз жеткізіңіз.</span><span class="sxs-lookup"><span data-stu-id="de050-110">To authenticate with an Azure service principal, make sure it's configured in your tenant.</span></span> <span data-ttu-id="de050-111">Қосымша ақпарат алу үшін [Аудитория мәліметтерін Azure субъект-қызметімен Azure Data Lake Storage Gen2 тіркелгісіне қосу](connect-service-principal.md) бөлімін қараңыз.</span><span class="sxs-lookup"><span data-stu-id="de050-111">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span>

- <span data-ttu-id="de050-112">Қосып, деректер қабылданатын Azure Data Lake жүйесі Dynamics 365 Customer Insights ортасы секілді бір Azure аймағында болуы қажет.</span><span class="sxs-lookup"><span data-stu-id="de050-112">The Azure Data Lake you want to connect and ingest data from have to be in the same Azure region as the Dynamics 365 Customer Insights environment.</span></span> <span data-ttu-id="de050-113">Common Data Model қалтасына деректер көлінен түрлі Azure аймағында қосу жүйелеріне қолдау көрсетілмейді.</span><span class="sxs-lookup"><span data-stu-id="de050-113">Connections to a Common Data Model folder from a data lake in a different Azure region is not supported.</span></span> <span data-ttu-id="de050-114">Ортаның Azure аймағын білу үшін аудитория мәліметтерінде **Әкімші** > **Жүйе** > **Мәлімет** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="de050-114">To know the Azure region of the environment, go to **Admin** > **System** > **About** in audience insights.</span></span>

- <span data-ttu-id="de050-115">Онлайн қызметтердегі сақталған деректер Dynamics 365 Customer Insights деректердің өңделіп, сақталатын орнынан басқа орында сақталуы тиіс.</span><span class="sxs-lookup"><span data-stu-id="de050-115">Data stored in online services, may be stored in a different location than where data is processed or stored in Dynamics 365 Customer Insights.</span></span><span data-ttu-id="de050-116"> Онлайн қызметтерде сақталған деректерді импорттау немесе қосу арқылы сіз деректердің Dynamics 365 Customer Insights бағдарламасына тасымалдануына және сақталуына келісім бересіз. [Қосымша ақпаратты Microsoft сенім орталығынан қараңыз.](https://www.microsoft.com/trust-center)</span><span class="sxs-lookup"><span data-stu-id="de050-116"> By importing or connecting to data stored in online services, you agree that data can be transferred to and stored with Dynamics 365 Customer Insights. [Learn more at the Microsoft Trust Center.](https://www.microsoft.com/trust-center)</span></span>

## <a name="connect-to-a-common-data-model-folder"></a><span data-ttu-id="de050-117">Common Data Model қалтасына қосылыңыз</span><span class="sxs-lookup"><span data-stu-id="de050-117">Connect to a Common Data Model folder</span></span>

1. <span data-ttu-id="de050-118">Аудитория мәліметтерінде **Деректер** > **Деректер көздері** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="de050-118">In audience insights, go to **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="de050-119">**Деректер көзін қосу** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="de050-119">Select **Add data source**.</span></span>

1. <span data-ttu-id="de050-120">**Common Data Model қалтасына қосу** опциясын таңдап, деректер көзі үшін **Атауын** енгізіп, **Келесі** түймесін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="de050-120">Select **Connect to a Common Data Model folder**, enter a **Name** for the data source, and select **Next**.</span></span> <span data-ttu-id="de050-121">Нұсқаулықтар атауын енгізіңіз:</span><span class="sxs-lookup"><span data-stu-id="de050-121">Name guidelines:</span></span> 
   - <span data-ttu-id="de050-122">Әріптен бастаңыз.</span><span class="sxs-lookup"><span data-stu-id="de050-122">Start with a letter.</span></span>
   - <span data-ttu-id="de050-123">Тек әріптер мен сандарды пайдаланыңыз.</span><span class="sxs-lookup"><span data-stu-id="de050-123">Use letters and numbers only.</span></span> <span data-ttu-id="de050-124">Арнайы таңбалар мен бос орындарға рұқсат етілмейді.</span><span class="sxs-lookup"><span data-stu-id="de050-124">Special characters and spaces are not allowed.</span></span>
   - <span data-ttu-id="de050-125">3-64 аралығындағы таңбаларды пайдаланыңыз.</span><span class="sxs-lookup"><span data-stu-id="de050-125">Use between 3 and 64 characters.</span></span>

1. <span data-ttu-id="de050-126">Ресурсқа негізделген опция мен аутентификацияға арналған жазылымға негізделген опция арасында таңдау жасай аласыз.</span><span class="sxs-lookup"><span data-stu-id="de050-126">You can choose between using a resource-based option and a subscription-based option for authentication.</span></span> <span data-ttu-id="de050-127">Қосымша ақпарат алу үшін [Аудитория мәліметтерін Azure субъект-қызметімен Azure Data Lake Storage Gen2 тіркелгісіне қосу](connect-service-principal.md) бөлімін қараңыз.</span><span class="sxs-lookup"><span data-stu-id="de050-127">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="de050-128">**Контейнер** ақпаратын енгізіп, **Келесі** түймесін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="de050-128">Enter the **Container** information and select **Next**.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="de050-129">![Azure Data Lake үшін жаңа байланыс мәліметтерін енгізуге арналған диалогтік терезе](media/enter-new-storage-details.png)
   > </span><span class="sxs-lookup"><span data-stu-id="de050-129">![Dialog box to enter new connection details for Azure Data Lake](media/enter-new-storage-details.png)
   > </span></span>[!NOTE]
<span data-ttu-id="de050-130">Деректер көзіне қосылу және оны жасау үшін сізге контейнерге немесе жоғарыда аталған сақтау орны тіркелгісіне келесі рөлдердің бірі қажет:</span><span class="sxs-lookup"><span data-stu-id="de050-130">You need one of the following roles either to the container or the storage account referred above to be able to connect to and create a data source:</span></span>
   >  - <span data-ttu-id="de050-131">Сақтау орнының Blob деректерін оқу құралы</span><span class="sxs-lookup"><span data-stu-id="de050-131">Storage Blob Data Reader</span></span>
   >  - <span data-ttu-id="de050-132">Сақтау орнының Blob деректерінің иеленушісі</span><span class="sxs-lookup"><span data-stu-id="de050-132">Storage Blob Data Owner</span></span>
   >  - <span data-ttu-id="de050-133">Сақтау орнының Blob деректерін қосушы</span><span class="sxs-lookup"><span data-stu-id="de050-133">Storage Blob Data Contributor</span></span>

1. <span data-ttu-id="de050-134">**Common Data Model қалтасы** диалогтік терезесінде деректерді импорттайтын model.json немесе manifest.json файлын таңдап, **Келесі** түймесін басыңыз.</span><span class="sxs-lookup"><span data-stu-id="de050-134">In the **Select a Common Data Model folder** dialog, select the model.json or manifest.json file to import data from, and select **Next**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="de050-135">Ортадағы басқа деректер көзімен байланысты кез келген model.json немесе manifest.json файлы тізімде көрсетілмейді.</span><span class="sxs-lookup"><span data-stu-id="de050-135">Any model.json or manifest.json file associated with another data source in the environment won't show in the list.</span></span>

1. <span data-ttu-id="de050-136">Таңдалған model.json немесе manifest.json файлынан қолжетімді нысандардың тізімін аласыз.</span><span class="sxs-lookup"><span data-stu-id="de050-136">You'll get a list of available entities in the selected model.json or manifest.json file.</span></span> <span data-ttu-id="de050-137">Қолжетімді нысандар тізімін қарап шығып, одан таңдап, **Сақтау** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="de050-137">You can review and select from the list of available entities and select **Save**.</span></span> <span data-ttu-id="de050-138">Таңдалған нысандардың барлығы жаңа деректер көзінен қабылданады.</span><span class="sxs-lookup"><span data-stu-id="de050-138">All of the selected entities will be ingested from the new data source.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="de050-139">![Model.json файлындағы нысандар тізімін көрсететін диалогтық терезе](media/review-entities.png)</span><span class="sxs-lookup"><span data-stu-id="de050-139">![Dialog box showing a list of entities from a model.json file](media/review-entities.png)</span></span>

8. <span data-ttu-id="de050-140">Деректер профилін қосқыңыз келген деректер нысандарын көрсетіп, **Сақтау** түймесін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="de050-140">Indicate which data entities you want to enable data profiling and select **Save**.</span></span> <span data-ttu-id="de050-141">Деректер профилі талдау және басқа мүмкіндіктерді қосады.</span><span class="sxs-lookup"><span data-stu-id="de050-141">Data profiling enables analytics and other capabilities.</span></span> <span data-ttu-id="de050-142">Нысаннан барлық төлсипаттарды таңдайтын барлық нысанды таңдауға немесе белгілі бір төлсипаттарды таңдауға болады.</span><span class="sxs-lookup"><span data-stu-id="de050-142">You can select the whole entity, which selects all attributes from the entity, or select certain attributes of your choice.</span></span> <span data-ttu-id="de050-143">Әдепкі бойынша, деректерді профильдеу үшін ешбір нысан қосылмаған.</span><span class="sxs-lookup"><span data-stu-id="de050-143">By default, no entity is enabled for data profiling.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="de050-144">![Деректер профилін көрсететін диалогтік терезе](media/dataprofiling-entities.png)</span><span class="sxs-lookup"><span data-stu-id="de050-144">![Dialog box showing a data profiling](media/dataprofiling-entities.png)</span></span>

9. <span data-ttu-id="de050-145">Таңдауларды сақтаған соң, **Деректер көздері** беті ашылады.</span><span class="sxs-lookup"><span data-stu-id="de050-145">After saving your selections, the **Data sources** page opens.</span></span> <span data-ttu-id="de050-146">Енді Common Data Model қалтасы байланысын деректер көзі ретінде көруіңіз керек.</span><span class="sxs-lookup"><span data-stu-id="de050-146">You should now see the Common Data Model folder connection as a data source.</span></span>

> [!NOTE]
> <span data-ttu-id="de050-147">Model.json file немесе manifest.json файлы бір ортада тек бір деректер көзімен байланыса алады.</span><span class="sxs-lookup"><span data-stu-id="de050-147">A model.json file or manifest.json can only associate with one data source in the same environment.</span></span> <span data-ttu-id="de050-148">Алайда, сол model.json немесе manifest.json файлын бірнеше ортадағы деректер көздері үшін пайдалануға болады.</span><span class="sxs-lookup"><span data-stu-id="de050-148">However, the same model.json or manifest.json file can be used for data sources in multiple environments.</span></span>

## <a name="edit-a-common-data-model-folder-data-source"></a><span data-ttu-id="de050-149">Common Data Model қалта деректер көзін өңдеу</span><span class="sxs-lookup"><span data-stu-id="de050-149">Edit a Common Data Model folder data source</span></span>

<span data-ttu-id="de050-150">Common Data Model қалтасы бар сақтау тіркелгісіне кіру кілтін жаңартуға болады.</span><span class="sxs-lookup"><span data-stu-id="de050-150">You can update the access key for the storage account containing the Common Data Model folder.</span></span> <span data-ttu-id="de050-151">Сонымен қатар, model.json немесе manifest.json файлын өзгертуге болады.</span><span class="sxs-lookup"><span data-stu-id="de050-151">You may also change the model.json or manifest.json file.</span></span> <span data-ttu-id="de050-152">Сақтау орнының тіркелгісінен басқа контейнерге қосылу немесе тіркелгі атауын өзгерту үшін, [жаңа деректер көзі қосылымын жасау](#connect-to-a-common-data-model-folder) қажет.</span><span class="sxs-lookup"><span data-stu-id="de050-152">To connect to a different container from your storage account, or change the account name, [create a new data source connection](#connect-to-a-common-data-model-folder).</span></span>

1. <span data-ttu-id="de050-153">Аудитория мәліметтерінде **Деректер** > **Деректер көздері** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="de050-153">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="de050-154">Жаңарту керек деректер көзінің жанындағы көп нүктені таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="de050-154">Next to the data source you'd like to update, select the ellipsis.</span></span>

3. <span data-ttu-id="de050-155">Тізімнен **Өңдеу** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="de050-155">Select the **Edit** option from the list.</span></span>

4. <span data-ttu-id="de050-156">Оған қоса, **Қатынасу кілті** өрісін жаңартыңыз және **Келесі** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="de050-156">Optionally, update the **Access key** and select **Next**.</span></span>

   ![Бұрыннан бар деректер көзі үшін қатынасу кілтін өңдеу және жаңарту диалогтық терезесі](media/edit-access-key.png)

5. <span data-ttu-id="de050-158">Оған қос, тіркелгі кілтінің қосылымынан ресурстарға немесе жазылымға негізделген байланысқа дейін жаңарта аласыз.</span><span class="sxs-lookup"><span data-stu-id="de050-158">Optionally, you can update from an account key connection to a resource-based or a subscription-based connection.</span></span> <span data-ttu-id="de050-159">Қосымша ақпарат алу үшін [Аудитория мәліметтерін Azure субъект-қызметімен Azure Data Lake Storage Gen2 тіркелгісіне қосу](connect-service-principal.md) бөлімін қараңыз.</span><span class="sxs-lookup"><span data-stu-id="de050-159">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="de050-160">Байланысты жаңарту кезінде **Контейнер** ақпаратын өзгерту мүмкін емес.</span><span class="sxs-lookup"><span data-stu-id="de050-160">You can't change **Container** information when updating the connection.</span></span>
   > [!div class="mx-imgBorder"]

   > ![Бұрыннан бар сақтау орны тіркелгісіне Azure Data Lake қосылымы туралы мәліметтерді енгізуге арналған диалогтік терезе](media/enter-existing-storage-details.png)

   > [!NOTE]
   > <span data-ttu-id="de050-162">Деректер көзіне қосылу және оны жасау үшін сізге контейнерге немесе жоғарыда аталған сақтау орны тіркелгісіне келесі рөлдердің бірі қажет:</span><span class="sxs-lookup"><span data-stu-id="de050-162">You need one of the following roles either to the container or the storage account referred above to be able to connect to and create a data source:</span></span>
   >  - <span data-ttu-id="de050-163">Сақтау орнының Blob деректерін оқу құралы</span><span class="sxs-lookup"><span data-stu-id="de050-163">Storage Blob Data Reader</span></span>
   >  - <span data-ttu-id="de050-164">Сақтау орнының Blob деректерінің иеленушісі</span><span class="sxs-lookup"><span data-stu-id="de050-164">Storage Blob Data Owner</span></span>
   >  - <span data-ttu-id="de050-165">Сақтау орнының Blob деректерін қосушы</span><span class="sxs-lookup"><span data-stu-id="de050-165">Storage Blob Data Contributo</span></span>


6. <span data-ttu-id="de050-166">Қажет болса, контейнерден басқа нысандар жиынтығымен басқа model.json немесе manifest.json файлын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="de050-166">Optionally, choose a different model.json or manifest.json file with a different set of entities from the container.</span></span>

7. <span data-ttu-id="de050-167">Оған қоса, қабылданатын қосымша нысандарды таңдауға болады.</span><span class="sxs-lookup"><span data-stu-id="de050-167">Optionally, you can select additional entities to ingest.</span></span> <span data-ttu-id="de050-168">Сонымен қатар тәуелділіктер болмаса, бұрыннан таңдалған нысандарды жоя аласыз.</span><span class="sxs-lookup"><span data-stu-id="de050-168">You can also remove any already selected entities if there are no dependencies.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="de050-169">Егер бар model.json немесе manifest.json файлына және нысандар жиынтығына тәуелділіктер болса, сіз қате туралы хабарламаны көресіз және басқа model.json немесе manifest.json файлын таңдай алмайсыз.</span><span class="sxs-lookup"><span data-stu-id="de050-169">If there are dependencies on the existing model.json or manifest.json file and the set of entities, you'll see an error message and can't select a different model.json or manifest.json file.</span></span> <span data-ttu-id="de050-170">Model.json немесе manifest.json файлын өзгертпес бұрын осы тәуелділіктерді жойыңыз немесе тәуелділіктерді болдырмас үшін қолданғыңыз келетін model.json немесе manifest.json файлымен жаңа деректер көзін жасаңыз.</span><span class="sxs-lookup"><span data-stu-id="de050-170">Remove those dependencies before changing the model.json or manifest.json file or create a new data source with the model.json or manifest.json file that you want to use to avoid removing the dependencies.</span></span>

8. <span data-ttu-id="de050-171">Оған қоса, профильді қосу немесе өшіру үшін қосымша төлсипаттарды немесе нысандарды таңдауға болады.</span><span class="sxs-lookup"><span data-stu-id="de050-171">Optionally, you can select additional attributes or entities to enable data profiling on or disable already selected ones.</span></span>   


[!INCLUDE[footer-include](../includes/footer-banner.md)]