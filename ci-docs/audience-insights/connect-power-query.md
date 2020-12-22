---
title: Деректерді Power Query қосқышы арқылы алу
description: Power Query негізіндегі деректер көздеріне арналған қосқыштар.
ms.date: 09/29/2020
ms.reviewer: adkuppa
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 8a170cc5b64b4b383501021232c83948e838a0e2
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406230"
---
# <a name="connect-to-a-power-query-data-source"></a><span data-ttu-id="12a35-103">Power Query деректер көзіне қосылыңыз</span><span class="sxs-lookup"><span data-stu-id="12a35-103">Connect to a Power Query data source</span></span>

<span data-ttu-id="12a35-104">Power Query деректерді қабылдау үшін қосқыштардың кең жиынтығын ұсынады.</span><span class="sxs-lookup"><span data-stu-id="12a35-104">Power Query offers a broad set of connectors to ingest data.</span></span> <span data-ttu-id="12a35-105">Бұл қосқыштардың көпшілігін Dynamics 365 Customer Insights қолдайды.</span><span class="sxs-lookup"><span data-stu-id="12a35-105">Most of these connectors are supported by Dynamics 365 Customer Insights.</span></span> <span data-ttu-id="12a35-106">Power Query қосқыштарына негізделген деректер көздерін қосу әдетте келесі бөлімде көрсетілген қадамдар бойынша жүреді.</span><span class="sxs-lookup"><span data-stu-id="12a35-106">Adding data sources based on Power Query connectors generally follows the steps outlined in the next section.</span></span> <span data-ttu-id="12a35-107">Дегенмен сіз қолданатын қосқышқа байланысты әртүрлі ақпарат қажет.</span><span class="sxs-lookup"><span data-stu-id="12a35-107">However, depending on the connector you use, different information is required.</span></span> <span data-ttu-id="12a35-108">Қосымша ақпарат алу үшін [Power Query қосқышына сілтеме](https://docs.microsoft.com/power-query/connectors/) ішіндегі жеке қосқыштар туралы құжаттаманы қараңыз.</span><span class="sxs-lookup"><span data-stu-id="12a35-108">For more information, see the documentation about individual connectors in the [Power Query connector reference](https://docs.microsoft.com/power-query/connectors/).</span></span>

## <a name="create-a-new-data-source"></a><span data-ttu-id="12a35-109">Жаңа деректер көзін жасау</span><span class="sxs-lookup"><span data-stu-id="12a35-109">Create a new data source</span></span>

1. <span data-ttu-id="12a35-110">Аудитория мәліметтерінде **Деректер** > **Деректер көздері** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="12a35-110">In audience insights, go to **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="12a35-111">**Деректер көзін қосу** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="12a35-111">Select **Add data source**.</span></span>

1. <span data-ttu-id="12a35-112">**Деректерді импорттау** әдісін таңдап, **Келесі** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="12a35-112">Choose the **Import data** method and select **Next**.</span></span>

1. <span data-ttu-id="12a35-113">Дерек көзі үшін **Атауы** өрісін толтырып, дерек көзін жасау үшін **Келесі** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="12a35-113">Provide a **Name** for the data source, and select **Next** to create the data source.</span></span>

1. <span data-ttu-id="12a35-114">[Қолжетімді қосқыштардың](#available-power-query-data-sources) бірін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="12a35-114">Choose one of the [available connectors](#available-power-query-data-sources).</span></span> <span data-ttu-id="12a35-115">Мысал үшін біз **Мәтін/CSV** қосқышын таңдаймыз.</span><span class="sxs-lookup"><span data-stu-id="12a35-115">For this example, we select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="12a35-116">Таңдалған қосқыш үшін **Қосылым параметрлері** ішінде талап етілетін мәліметтерді енгізіңіз және деректердің алдын ала қарауын көру үшін **Келесі** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="12a35-116">Enter the required details in the **Connection settings** for the selected connector and select **Next** to see a preview of the data.</span></span>

1. <span data-ttu-id="12a35-117">**Деректерді түрлендіру** пәрменін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="12a35-117">Select **Transform data**.</span></span> <span data-ttu-id="12a35-118">Бұл қадамда деректер көзіне нысандарды қосасыз.</span><span class="sxs-lookup"><span data-stu-id="12a35-118">In this step, you'll add entities to your data source.</span></span> <span data-ttu-id="12a35-119">Нысандар дерекқорлар болып табылады.</span><span class="sxs-lookup"><span data-stu-id="12a35-119">Entities are datasets.</span></span> <span data-ttu-id="12a35-120">Бірнеше деректер жиынынан тұратын дерекқор болса, әрбір деректер жиыны — жеке нысан.</span><span class="sxs-lookup"><span data-stu-id="12a35-120">If you have a database that includes multiple datasets, each dataset is its own entity.</span></span>

1. <span data-ttu-id="12a35-121">**Power Query - Сұрауларды өңдеу** диалогтік терезесі деректерді қарап шығуға және нақтылауға мүмкіндік береді.</span><span class="sxs-lookup"><span data-stu-id="12a35-121">The **Power Query - Edit queries** dialog lets you review and refine the data.</span></span> <span data-ttu-id="12a35-122">Таңдалған деректер көзінде анықталған жүйелердің нысандары сол жақ тақтада пайда болады.</span><span class="sxs-lookup"><span data-stu-id="12a35-122">The entities that the systems identified in your selected data source appear in the left pane.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="12a35-123">![Сұраулар диалогын өңдеу](media/data-manager-configure-edit-queries.png "Сұраулар диалогын өңдеу")</span><span class="sxs-lookup"><span data-stu-id="12a35-123">![Edit queries dialog](media/data-manager-configure-edit-queries.png "Edit queries dialog")</span></span>

1. <span data-ttu-id="12a35-124">Сонымен қатар, деректеріңізді түрлендіре аласыз.</span><span class="sxs-lookup"><span data-stu-id="12a35-124">You can also transform your data.</span></span> <span data-ttu-id="12a35-125">Өңдейтін немесе түрлендіретін нысанды таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="12a35-125">Select an entity to edit or transform.</span></span> <span data-ttu-id="12a35-126">Түрлендірулерді қолдану үшін Power Query терезесіндегі параметрлерді қолданыңыз.</span><span class="sxs-lookup"><span data-stu-id="12a35-126">Use the options in the Power Query window to apply transformations.</span></span> <span data-ttu-id="12a35-127">Әр түрлендіру **Қолданылатын қадамдар** тізімінде беріледі.</span><span class="sxs-lookup"><span data-stu-id="12a35-127">Each transformation gets listed under **Applied steps**.</span></span> <span data-ttu-id="12a35-128">Power Query көптеген алдын ала жасалған трансформация параметрлерін ұсынады.</span><span class="sxs-lookup"><span data-stu-id="12a35-128">Power Query provides numerous pre-built transformation options.</span></span> <span data-ttu-id="12a35-129">Қосымша ақпарат алу үшін [Power Query түрлендірулері](https://docs.microsoft.com/power-query/power-query-what-is-power-query#transformations) бөлімін қараңыз.</span><span class="sxs-lookup"><span data-stu-id="12a35-129">For more information, see [Power Query Transformations](https://docs.microsoft.com/power-query/power-query-what-is-power-query#transformations).</span></span>

1. <span data-ttu-id="12a35-130">**Сұрауларды өңдеу** диалог терезесінен **Деректерді алу** параметрін таңдау арқылы деректер көзіне қосымша нысандарды қоса аласыз.</span><span class="sxs-lookup"><span data-stu-id="12a35-130">You can add additional entities to your data source by selecting **Get data** in the **Edit queries** dialog.</span></span>

   <span data-ttu-id="12a35-131">Осы түрлендірулер қатаң түрде ұсынылады:</span><span class="sxs-lookup"><span data-stu-id="12a35-131">These transformations are highly recommended:</span></span>

   - <span data-ttu-id="12a35-132">Егер сіз деректерді CSV файлынан қабылдап жатсаңыз, көбінесе тақырыптар бірінші қатарда қамтылады.</span><span class="sxs-lookup"><span data-stu-id="12a35-132">If you're ingesting data from a CSV file, the first row often contains headers.</span></span> <span data-ttu-id="12a35-133">**Кестені түрлендіру** пәрменіне өтіп, **Тақырыптарды бірінші қатар ретінде қолдану** опциясын қолданыңыз.</span><span class="sxs-lookup"><span data-stu-id="12a35-133">Go to **Transform table** and select **Use headers as first row**.</span></span>
   - <span data-ttu-id="12a35-134">Деректер түрінің тиісті түрде орнатылғанына көз жеткізіңіз.</span><span class="sxs-lookup"><span data-stu-id="12a35-134">Ensure the data type is set appropriately.</span></span>

1. <span data-ttu-id="12a35-135">Түрлендірулерді сақтау үшін Power Query терезесінің төменгі жағындағы **Сақтау** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="12a35-135">Select **Save** at the bottom of the Power Query window to save the transformations.</span></span> <span data-ttu-id="12a35-136">Сақтағаннан кейін сіз деректер көзін **Деректер** > **Деректер көздері** тармағы бойынша таба аласыз.</span><span class="sxs-lookup"><span data-stu-id="12a35-136">After saving, you'll find your data source on **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="12a35-137">**Деректер көздері** бетінің үстінде, **Сергіту** мәртебесінде жаңа деректер көзін байқайсыз.</span><span class="sxs-lookup"><span data-stu-id="12a35-137">On the **Data sources** page, you'll notice the new data source is in **Refreshing** status.</span></span>

## <a name="available-power-query-data-sources"></a><span data-ttu-id="12a35-138">Қолжетімді Power Query деректер көздері</span><span class="sxs-lookup"><span data-stu-id="12a35-138">Available Power Query data sources</span></span>

<span data-ttu-id="12a35-139">[Power Query қосқышына сілтеме](https://docs.microsoft.com/power-query/connectors/) мекенжайынан Customer Insights бағдарламасына деректерді импорттау үшін таңдауға болатын қосқыштардың жаңартылған тізімін қараңыз.</span><span class="sxs-lookup"><span data-stu-id="12a35-139">See the [Power Query connector reference](https://docs.microsoft.com/power-query/connectors/) for an up-to-date list of connectors that you can select to import data to Customer Insights.</span></span> 

<span data-ttu-id="12a35-140">**Customer Insights (деректер ағындары)** бағанында құсбелгісі бар қосқыштар Power Query негізінде жаңа деректер көздерін жасау үшін қолжетімді.</span><span class="sxs-lookup"><span data-stu-id="12a35-140">Connectors with a checkmark in the **Customer Insights (Dataflows)** column are available to create new data sources based on Power Query.</span></span> <span data-ttu-id="12a35-141">Алғышарттар, шектеулер және басқа да мәліметтер туралы көбірек білу үшін белгілі бір қосқыштың құжаттарын қарап шығыңыз.</span><span class="sxs-lookup"><span data-stu-id="12a35-141">Review the documentation of a specific connector to learn more about its prerequisites, limitations, and other details.</span></span>

## <a name="edit-power-query-data-sources"></a><span data-ttu-id="12a35-142">Power Query деректер көздерін өңдеу</span><span class="sxs-lookup"><span data-stu-id="12a35-142">Edit Power Query data sources</span></span>

> [!NOTE]
> <span data-ttu-id="12a35-143">Дәл қазір бағдарлама процестерінің бірінде қолданылатын деректер көздеріне өзгерістер жасауға болмайды (мысалы, *сегменттеу*, *сәйкестендіру* немесе *біріктіру*).</span><span class="sxs-lookup"><span data-stu-id="12a35-143">It might not be possible to make changes to data sources that are currently being used in one of the app's processes (*segmentation*, *match*, or *merge*, for example).</span></span> 
>
> <span data-ttu-id="12a35-144">**Параметрлер** бетімен әрбір белсенді процестің орындалу барысын бақылай аласыз.</span><span class="sxs-lookup"><span data-stu-id="12a35-144">Using the **Settings** page, you can track the progress of each of the active processes.</span></span> <span data-ttu-id="12a35-145">Процесс аяқталған кезде **Деректер көздері** бетіне оралып, өзгерістерді жасаңыз.</span><span class="sxs-lookup"><span data-stu-id="12a35-145">When a process completes, you can return to the **Data Sources** page and make your changes.</span></span>

1. <span data-ttu-id="12a35-146">Аудитория мәліметтерінде **Деректер** > **Деректер көздері** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="12a35-146">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="12a35-147">Өзгерту қажет деректер көзі жанындағы тік көп нүктені таңдаңыз және ашылмалы мәзірден **Өңдеу** опциясын басыңыз.</span><span class="sxs-lookup"><span data-stu-id="12a35-147">Select the vertical ellipsis next to the data source you want to change and select **Edit** from the drop-down menu.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="12a35-148">![Өңдеу параметрі](media/edit-option-data-sources.png "Өңдеу параметрі")</span><span class="sxs-lookup"><span data-stu-id="12a35-148">![Edit option](media/edit-option-data-sources.png "Edit option")</span></span>

3. <span data-ttu-id="12a35-149">[Жаңа деректер көзін жасау](#create-a-new-data-source) бөлімінде сипатталғандай өзгерістер мен түрлендірулерді **Power Query - Сұраныстарды өңдеу** диалогтік терезесіне қолданыңыз.</span><span class="sxs-lookup"><span data-stu-id="12a35-149">Apply your changes and transformations in the **Power Query - Edit queries** dialog as described in the [Create a new data source](#create-a-new-data-source) section.</span></span>

4. <span data-ttu-id="12a35-150">Өзгерістеріңізді сақтау үшін Power Query қондырмасында өңдеуді аяқтағаннан кейін **Сақтау** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="12a35-150">Select **Save** in Power Query after completing your edits to save your changes.</span></span>
