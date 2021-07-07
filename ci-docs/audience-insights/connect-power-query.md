---
title: Деректерді Power Query қосқышы арқылы алу
description: Power Query негізіндегі деректер көздеріне арналған қосқыштар.
ms.date: 09/29/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.openlocfilehash: 50c231070ff9930c1ea82971bf4f8541a89d5027
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305898"
---
# <a name="connect-to-a-power-query-data-source"></a><span data-ttu-id="e9d00-103">Power Query деректер көзіне қосылыңыз</span><span class="sxs-lookup"><span data-stu-id="e9d00-103">Connect to a Power Query data source</span></span>

<span data-ttu-id="e9d00-104">Power Query деректерді қабылдау үшін қосқыштардың кең жиынтығын ұсынады.</span><span class="sxs-lookup"><span data-stu-id="e9d00-104">Power Query offers a broad set of connectors to ingest data.</span></span> <span data-ttu-id="e9d00-105">Бұл қосқыштардың көпшілігін Dynamics 365 Customer Insights қолдайды.</span><span class="sxs-lookup"><span data-stu-id="e9d00-105">Most of these connectors are supported by Dynamics 365 Customer Insights.</span></span> <span data-ttu-id="e9d00-106">Power Query қосқыштарына негізделген деректер көздерін қосу әдетте келесі бөлімде көрсетілген қадамдар бойынша жүреді.</span><span class="sxs-lookup"><span data-stu-id="e9d00-106">Adding data sources based on Power Query connectors generally follows the steps outlined in the next section.</span></span> <span data-ttu-id="e9d00-107">Дегенмен сіз қолданатын қосқышқа байланысты әртүрлі ақпарат қажет.</span><span class="sxs-lookup"><span data-stu-id="e9d00-107">However, depending on the connector you use, different information is required.</span></span> <span data-ttu-id="e9d00-108">Қосымша ақпарат алу үшін [Power Query қосқышына сілтеме](/power-query/connectors/) ішіндегі жеке қосқыштар туралы құжаттаманы қараңыз.</span><span class="sxs-lookup"><span data-stu-id="e9d00-108">For more information, see the documentation about individual connectors in the [Power Query connector reference](/power-query/connectors/).</span></span>

## <a name="create-a-new-data-source"></a><span data-ttu-id="e9d00-109">Жаңа деректер көзін жасау</span><span class="sxs-lookup"><span data-stu-id="e9d00-109">Create a new data source</span></span>

1. <span data-ttu-id="e9d00-110">Аудитория мәліметтерінде **Деректер** > **Деректер көздері** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="e9d00-110">In audience insights, go to **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="e9d00-111">**Деректер көзін қосу** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="e9d00-111">Select **Add data source**.</span></span>

1. <span data-ttu-id="e9d00-112">**Деректерді импорттау** әдісін таңдап, **Келесі** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="e9d00-112">Choose the **Import data** method and select **Next**.</span></span>

1. <span data-ttu-id="e9d00-113">Дерек көзі үшін **Атауы** өрісін толтырып, дерек көзін жасау үшін **Келесі** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="e9d00-113">Provide a **Name** for the data source, and select **Next** to create the data source.</span></span> <span data-ttu-id="e9d00-114">Нұсқаулықтар атауын енгізіңіз:</span><span class="sxs-lookup"><span data-stu-id="e9d00-114">Name guidelines:</span></span> 
   - <span data-ttu-id="e9d00-115">Әріптен бастаңыз.</span><span class="sxs-lookup"><span data-stu-id="e9d00-115">Start with a letter.</span></span>
   - <span data-ttu-id="e9d00-116">Тек әріптер мен сандарды пайдаланыңыз.</span><span class="sxs-lookup"><span data-stu-id="e9d00-116">Use letters and numbers only.</span></span> <span data-ttu-id="e9d00-117">Арнайы таңбалар мен бос орындарға рұқсат етілмейді.</span><span class="sxs-lookup"><span data-stu-id="e9d00-117">Special characters and spaces are not allowed.</span></span>
   - <span data-ttu-id="e9d00-118">3-64 аралығындағы таңбаларды пайдаланыңыз.</span><span class="sxs-lookup"><span data-stu-id="e9d00-118">Use between 3 and 64 characters.</span></span>

1. <span data-ttu-id="e9d00-119">[Қолжетімді қосқыштардың](#available-power-query-data-sources) бірін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="e9d00-119">Choose one of the [available connectors](#available-power-query-data-sources).</span></span> <span data-ttu-id="e9d00-120">Мысал үшін біз **Мәтін/CSV** қосқышын таңдаймыз.</span><span class="sxs-lookup"><span data-stu-id="e9d00-120">For this example, we select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="e9d00-121">Таңдалған қосқыш үшін **Қосылым параметрлері** ішінде талап етілетін мәліметтерді енгізіңіз және деректердің алдын ала қарауын көру үшін **Келесі** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="e9d00-121">Enter the required details in the **Connection settings** for the selected connector and select **Next** to see a preview of the data.</span></span>

1. <span data-ttu-id="e9d00-122">**Деректерді түрлендіру** пәрменін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="e9d00-122">Select **Transform data**.</span></span> <span data-ttu-id="e9d00-123">Бұл қадамда деректер көзіне нысандарды қосасыз.</span><span class="sxs-lookup"><span data-stu-id="e9d00-123">In this step, you'll add entities to your data source.</span></span> <span data-ttu-id="e9d00-124">Нысандар дерекқорлар болып табылады.</span><span class="sxs-lookup"><span data-stu-id="e9d00-124">Entities are datasets.</span></span> <span data-ttu-id="e9d00-125">Бірнеше деректер жиынынан тұратын дерекқор болса, әрбір деректер жиыны — жеке нысан.</span><span class="sxs-lookup"><span data-stu-id="e9d00-125">If you have a database that includes multiple datasets, each dataset is its own entity.</span></span>

1. <span data-ttu-id="e9d00-126">**Power Query - Сұрауларды өңдеу** диалогтік терезесі деректерді қарап шығуға және нақтылауға мүмкіндік береді.</span><span class="sxs-lookup"><span data-stu-id="e9d00-126">The **Power Query - Edit queries** dialog lets you review and refine the data.</span></span> <span data-ttu-id="e9d00-127">Таңдалған деректер көзінде анықталған жүйелердің нысандары сол жақ тақтада пайда болады.</span><span class="sxs-lookup"><span data-stu-id="e9d00-127">The entities that the systems identified in your selected data source appear in the left pane.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e9d00-128">![Сұраулар диалогын өңдеу](media/data-manager-configure-edit-queries.png "Сұраулар диалогын өңдеу")</span><span class="sxs-lookup"><span data-stu-id="e9d00-128">![Edit queries dialog](media/data-manager-configure-edit-queries.png "Edit queries dialog")</span></span>

1. <span data-ttu-id="e9d00-129">Сонымен қатар, деректеріңізді түрлендіре аласыз.</span><span class="sxs-lookup"><span data-stu-id="e9d00-129">You can also transform your data.</span></span> <span data-ttu-id="e9d00-130">Өңдейтін немесе түрлендіретін нысанды таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="e9d00-130">Select an entity to edit or transform.</span></span> <span data-ttu-id="e9d00-131">Түрлендірулерді қолдану үшін Power Query терезесіндегі параметрлерді қолданыңыз.</span><span class="sxs-lookup"><span data-stu-id="e9d00-131">Use the options in the Power Query window to apply transformations.</span></span> <span data-ttu-id="e9d00-132">Әр түрлендіру **Қолданылатын қадамдар** тізімінде беріледі.</span><span class="sxs-lookup"><span data-stu-id="e9d00-132">Each transformation gets listed under **Applied steps**.</span></span> <span data-ttu-id="e9d00-133">Power Query көптеген алдын ала жасалған трансформация параметрлерін ұсынады.</span><span class="sxs-lookup"><span data-stu-id="e9d00-133">Power Query provides numerous pre-built transformation options.</span></span> <span data-ttu-id="e9d00-134">Қосымша ақпарат алу үшін [Power Query түрлендірулері](/power-query/power-query-what-is-power-query#transformations) бөлімін қараңыз.</span><span class="sxs-lookup"><span data-stu-id="e9d00-134">For more information, see [Power Query Transformations](/power-query/power-query-what-is-power-query#transformations).</span></span>

1. <span data-ttu-id="e9d00-135">**Сұрауларды өңдеу** диалог терезесінен **Деректерді алу** параметрін таңдау арқылы деректер көзіне қосымша нысандарды қоса аласыз.</span><span class="sxs-lookup"><span data-stu-id="e9d00-135">You can add additional entities to your data source by selecting **Get data** in the **Edit queries** dialog.</span></span>

   <span data-ttu-id="e9d00-136">Осы түрлендірулер қатаң түрде ұсынылады:</span><span class="sxs-lookup"><span data-stu-id="e9d00-136">These transformations are highly recommended:</span></span>

   - <span data-ttu-id="e9d00-137">Егер сіз деректерді CSV файлынан қабылдап жатсаңыз, көбінесе тақырыптар бірінші қатарда қамтылады.</span><span class="sxs-lookup"><span data-stu-id="e9d00-137">If you're ingesting data from a CSV file, the first row often contains headers.</span></span> <span data-ttu-id="e9d00-138">**Кестені түрлендіру** пәрменіне өтіп, **Тақырыптарды бірінші қатар ретінде қолдану** опциясын қолданыңыз.</span><span class="sxs-lookup"><span data-stu-id="e9d00-138">Go to **Transform table** and select **Use headers as first row**.</span></span>
   - <span data-ttu-id="e9d00-139">Деректер түрінің тиісті түрде орнатылғанына көз жеткізіңіз.</span><span class="sxs-lookup"><span data-stu-id="e9d00-139">Ensure the data type is set appropriately.</span></span>

1. <span data-ttu-id="e9d00-140">Түрлендірулерді сақтау үшін Power Query терезесінің төменгі жағындағы **Сақтау** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="e9d00-140">Select **Save** at the bottom of the Power Query window to save the transformations.</span></span> <span data-ttu-id="e9d00-141">Сақтағаннан кейін сіз деректер көзін **Деректер** > **Деректер көздері** тармағы бойынша таба аласыз.</span><span class="sxs-lookup"><span data-stu-id="e9d00-141">After saving, you'll find your data source on **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="e9d00-142">**Деректер көздері** бетінің үстінде, **Сергіту** мәртебесінде жаңа деректер көзін байқайсыз.</span><span class="sxs-lookup"><span data-stu-id="e9d00-142">On the **Data sources** page, you'll notice the new data source is in **Refreshing** status.</span></span>

## <a name="available-power-query-data-sources"></a><span data-ttu-id="e9d00-143">Қолжетімді Power Query деректер көздері</span><span class="sxs-lookup"><span data-stu-id="e9d00-143">Available Power Query data sources</span></span>

<span data-ttu-id="e9d00-144">[Power Query қосқышына сілтеме](/power-query/connectors/) мекенжайынан Customer Insights бағдарламасына деректерді импорттау үшін таңдауға болатын қосқыштардың жаңартылған тізімін қараңыз.</span><span class="sxs-lookup"><span data-stu-id="e9d00-144">See the [Power Query connector reference](/power-query/connectors/) for an up-to-date list of connectors that you can select to import data to Customer Insights.</span></span> 

<span data-ttu-id="e9d00-145">**Customer Insights (деректер ағындары)** бағанында құсбелгісі бар қосқыштар Power Query негізінде жаңа деректер көздерін жасау үшін қолжетімді.</span><span class="sxs-lookup"><span data-stu-id="e9d00-145">Connectors with a checkmark in the **Customer Insights (Dataflows)** column are available to create new data sources based on Power Query.</span></span> <span data-ttu-id="e9d00-146">Алғышарттар, шектеулер және басқа да мәліметтер туралы көбірек білу үшін белгілі бір қосқыштың құжаттарын қарап шығыңыз.</span><span class="sxs-lookup"><span data-stu-id="e9d00-146">Review the documentation of a specific connector to learn more about its prerequisites, limitations, and other details.</span></span>

## <a name="edit-power-query-data-sources"></a><span data-ttu-id="e9d00-147">Power Query деректер көздерін өңдеу</span><span class="sxs-lookup"><span data-stu-id="e9d00-147">Edit Power Query data sources</span></span>

> [!NOTE]
> <span data-ttu-id="e9d00-148">Дәл қазір бағдарлама процестерінің бірінде қолданылатын деректер көздеріне өзгерістер жасауға болмайды (мысалы, *сегменттеу*, *сәйкестендіру* немесе *біріктіру*).</span><span class="sxs-lookup"><span data-stu-id="e9d00-148">It might not be possible to make changes to data sources that are currently being used in one of the app's processes (*segmentation*, *match*, or *merge*, for example).</span></span> 
>
> <span data-ttu-id="e9d00-149">**Параметрлер** бетімен әрбір белсенді процестің орындалу барысын бақылай аласыз.</span><span class="sxs-lookup"><span data-stu-id="e9d00-149">Using the **Settings** page, you can track the progress of each of the active processes.</span></span> <span data-ttu-id="e9d00-150">Процесс аяқталған кезде **Деректер көздері** бетіне оралып, өзгерістерді жасаңыз.</span><span class="sxs-lookup"><span data-stu-id="e9d00-150">When a process completes, you can return to the **Data Sources** page and make your changes.</span></span>

1. <span data-ttu-id="e9d00-151">Аудитория мәліметтерінде **Деректер** > **Деректер көздері** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="e9d00-151">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="e9d00-152">Өзгерту керек деректер көзі жанындағы тік көп нүктені таңдаңыз және ашылмалы мәзірден **Өңдеу** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="e9d00-152">Select the vertical ellipsis next to the data source you want to change and select **Edit** from the dropdown menu.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e9d00-153">![Өңдеу параметрі](media/edit-option-data-sources.png "Өңдеу параметрі")</span><span class="sxs-lookup"><span data-stu-id="e9d00-153">![Edit option](media/edit-option-data-sources.png "Edit option")</span></span>

3. <span data-ttu-id="e9d00-154">[Жаңа деректер көзін жасау](#create-a-new-data-source) бөлімінде сипатталғандай өзгерістер мен түрлендірулерді **Power Query - Сұраныстарды өңдеу** диалогтік терезесіне қолданыңыз.</span><span class="sxs-lookup"><span data-stu-id="e9d00-154">Apply your changes and transformations in the **Power Query - Edit queries** dialog as described in the [Create a new data source](#create-a-new-data-source) section.</span></span>

4. <span data-ttu-id="e9d00-155">Өзгерістеріңізді сақтау үшін Power Query қондырмасында өңдеуді аяқтағаннан кейін **Сақтау** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="e9d00-155">Select **Save** in Power Query after completing your edits to save your changes.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]