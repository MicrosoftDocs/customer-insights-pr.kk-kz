---
title: Деректерді қабылдау үшін деректер көздерін пайдалану
description: Деректерді әртүрлі көздерден импорттау әдісін үйреніңіз.
ms.date: 11/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 780dc61a82d6ed9856a37dc8f164fa946d982bbe
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595954"
---
# <a name="data-sources-overview"></a><span data-ttu-id="dc313-103">Деректер көздеріне шолу</span><span class="sxs-lookup"><span data-stu-id="dc313-103">Data sources overview</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="dc313-104">Dynamics 365 Customer Insights бағдарламасындағы аудитория түсініктерінің мүмкіндігі дерек көздерінің кең жиынындағы деректерге байланысады.</span><span class="sxs-lookup"><span data-stu-id="dc313-104">The audience insights capability in Dynamics 365 Customer Insights connects to data from a broad set of sources.</span></span> <span data-ttu-id="dc313-105">Дерек көзіне қосылуды көбінесе *деректерді қабылдау* процесі деп атайды.</span><span class="sxs-lookup"><span data-stu-id="dc313-105">Connecting to a data source is often referred to as the process of *data ingestion*.</span></span> <span data-ttu-id="dc313-106">Деректерді қабылдағаннан кейін, [біріктіру](data-unification.md) әрекетін жасауға және ол бойынша шаралар қабылдауға болады.</span><span class="sxs-lookup"><span data-stu-id="dc313-106">After ingesting the data, you can [unify](data-unification.md) and take action on it.</span></span>

## <a name="add-a-data-source"></a><span data-ttu-id="dc313-107">Деректер көзін қосу</span><span class="sxs-lookup"><span data-stu-id="dc313-107">Add a data source</span></span>

<span data-ttu-id="dc313-108">Таңдаған опцияға байланысты деректер көзін қосу әдісі туралы егжей-тегжейлі мақалаларды қараңыз.</span><span class="sxs-lookup"><span data-stu-id="dc313-108">Refer to the detailed articles on how to add a data source, depending on which option you choose.</span></span>

<span data-ttu-id="dc313-109">Деректер көзін үш негізгі жолмен қосуға болады:</span><span class="sxs-lookup"><span data-stu-id="dc313-109">You can add a data source in three main ways:</span></span>

- [<span data-ttu-id="dc313-110">Ондаған Power Query қосқыштары арқылы</span><span class="sxs-lookup"><span data-stu-id="dc313-110">Through dozens of Power Query connectors</span></span>](connect-power-query.md)
- [<span data-ttu-id="dc313-111">Common Data Model қалтасынан</span><span class="sxs-lookup"><span data-stu-id="dc313-111">From a Common Data Model folder</span></span>](connect-common-data-model.md)
- [<span data-ttu-id="dc313-112">Common Data Service көлінен</span><span class="sxs-lookup"><span data-stu-id="dc313-112">From your own Common Data Service lake</span></span>](connect-common-data-service-lake.md)

> [!NOTE]
> <span data-ttu-id="dc313-113">Жергілікті деректер көздерінен деректерді әлі қосуға болмайды.</span><span class="sxs-lookup"><span data-stu-id="dc313-113">You can't add data from on-premises data sources yet.</span></span>

## <a name="review-ingested-data"></a><span data-ttu-id="dc313-114">Қабылданған деректерді қарап шығу</span><span class="sxs-lookup"><span data-stu-id="dc313-114">Review ingested data</span></span>

<span data-ttu-id="dc313-115">Әр қабылданған деректер көзі атауын, күйін және осы көздер үшін соңғы рет жаңартылған деректерді көресіз.</span><span class="sxs-lookup"><span data-stu-id="dc313-115">You'll see the name of each ingested data source, its status, and the last time the data was refreshed for that source.</span></span> <span data-ttu-id="dc313-116">Деректер көздерінің тізімін әр баған бойынша сұрыптауға болады.</span><span class="sxs-lookup"><span data-stu-id="dc313-116">You can sort the list of data sources by every column.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="dc313-117">![Деректер көзі қосылды](media/configure-data-datasource-added.png "Деректер көзі қосылды")</span><span class="sxs-lookup"><span data-stu-id="dc313-117">![Data source added](media/configure-data-datasource-added.png "Data source added")</span></span>

|<span data-ttu-id="dc313-118">Күй</span><span class="sxs-lookup"><span data-stu-id="dc313-118">Status</span></span>  |<span data-ttu-id="dc313-119">Сипаттамасы</span><span class="sxs-lookup"><span data-stu-id="dc313-119">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="dc313-120">Орындалды</span><span class="sxs-lookup"><span data-stu-id="dc313-120">Successful</span></span>   |<span data-ttu-id="dc313-121">Уақыт **Қайта жаңартылған** бағанында көрсетілген болса, деректер көзі сәтті қабылданады.</span><span class="sxs-lookup"><span data-stu-id="dc313-121">Data source was successfully ingested if a time is mentioned in the **Refreshed** column.</span></span>
|<span data-ttu-id="dc313-122">Басталған жоқ</span><span class="sxs-lookup"><span data-stu-id="dc313-122">Not started</span></span>   |<span data-ttu-id="dc313-123">Деректер көзінде әлі қабылданған немесе жоба режиміндегі деректер жоқ.</span><span class="sxs-lookup"><span data-stu-id="dc313-123">The data source has no data ingested yet or still in draft mode.</span></span>         |
|<span data-ttu-id="dc313-124">Жаңартылуда</span><span class="sxs-lookup"><span data-stu-id="dc313-124">Refreshing</span></span>    |<span data-ttu-id="dc313-125">Деректер қабылдануда.</span><span class="sxs-lookup"><span data-stu-id="dc313-125">Data ingestion is in progress.</span></span> <span data-ttu-id="dc313-126">**Әрекеттер** бағанынан **Жаңартуды тоқтату** параметрін таңдау арқылы осы жұмыстан бас тарта аласыз.</span><span class="sxs-lookup"><span data-stu-id="dc313-126">You can cancel this operation by selecting **Stop refreshing** in the **Actions** column.</span></span> <span data-ttu-id="dc313-127">Деректер көзін жаңартуды тоқтату оның соңғы жаңарту күйін қайтарады.</span><span class="sxs-lookup"><span data-stu-id="dc313-127">Stopping the refresh of a data source will revert it to its last refresh state.</span></span>       |
|<span data-ttu-id="dc313-128">Сәтсіз аяқталған</span><span class="sxs-lookup"><span data-stu-id="dc313-128">Failed</span></span>     |<span data-ttu-id="dc313-129">Деректер қабылдау кезінде қателер орын алды.</span><span class="sxs-lookup"><span data-stu-id="dc313-129">Data ingestion ran into errors.</span></span>         |

<span data-ttu-id="dc313-130">Толығырақ мәліметтерді қарап шығу үшін кез келген деректер көзінің **Күй** бағанында мәнді таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="dc313-130">Select the value in the **Status** column of any data source to review more details.</span></span> <span data-ttu-id="dc313-131">**Орындалу барысы туралы мәліметтер** тақтасында **Деректер көздері** терезесін кеңейтіңіз.</span><span class="sxs-lookup"><span data-stu-id="dc313-131">In the **Progress details** pane, expand **Data sources**.</span></span> <span data-ttu-id="dc313-132">Жаңарту күйі туралы қосымша ақпаратты, оның ішінде қателер туралы және төмен ағынды процесті жаңарту туралы қарап шығу үшін **Мәліметтерді қарау** пәрменін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="dc313-132">Select **See details** for more information about the refresh status, including error details and downstream process updates.</span></span>

<span data-ttu-id="dc313-133">Деректерді жүктеуге біраз уақыт кетуі мүмкін.</span><span class="sxs-lookup"><span data-stu-id="dc313-133">Loading data can take some time.</span></span> <span data-ttu-id="dc313-134">Сәтті жаңартқан соң, қабылданған деректерді **Нысандар** бетінен қарап шығуға болады.</span><span class="sxs-lookup"><span data-stu-id="dc313-134">After a successful refresh, the ingested data can be reviewed from the **Entities** page.</span></span> <span data-ttu-id="dc313-135">Қосымша ақпаратты [Нысандар](entities.md) бөлімінен қараңыз.</span><span class="sxs-lookup"><span data-stu-id="dc313-135">For more information, see [Entities](entities.md).</span></span>

## <a name="refresh-a-data-source"></a><span data-ttu-id="dc313-136">Деректер көзін жаңарту</span><span class="sxs-lookup"><span data-stu-id="dc313-136">Refresh a data source</span></span>

<span data-ttu-id="dc313-137">Деректер көздерін автоматты кесте бойынша жаңартуға немесе сұраныс бойынша қолмен жаңартуға болады.</span><span class="sxs-lookup"><span data-stu-id="dc313-137">Data sources can be refreshed on an automatic schedule or refreshed manually on demand.</span></span> 

<span data-ttu-id="dc313-138">Барлық қабылданған деректер көздерінің жоспарланған жаңартуларын конфигурациялау үшін **Әкімші** > **Жүйе** > [**Кесте**](system.md#schedule-tab) тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="dc313-138">Go to **Admin** > **System** > [**Schedule**](system.md#schedule-tab) to configure scheduled refreshes of all your ingested data sources.</span></span>

<span data-ttu-id="dc313-139">Сұраныс бойынша деректер көзін жаңарту үшін келесі қадамдарды орындаңыз:</span><span class="sxs-lookup"><span data-stu-id="dc313-139">To refresh a data source on demand, follow these steps:</span></span>

1. <span data-ttu-id="dc313-140">Аудитория мәліметтерінде **Деректер** > **Деректер көздері** тармағына өтіңіз</span><span class="sxs-lookup"><span data-stu-id="dc313-140">In audience insights, go to **Data** > **Data sources**</span></span>

2. <span data-ttu-id="dc313-141">Жаңартқыңыз келетін деректер көзі жанындағы тік эллипсті таңдап, ашылмалы тізімнен **Жаңарту** пәрменін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="dc313-141">Select the vertical ellipsis next to the data source you want to refresh and select **Refresh** from the drop-down list.</span></span>

3. <span data-ttu-id="dc313-142">Қолмен жаңарту үшін деректер көзі іске қосылды.</span><span class="sxs-lookup"><span data-stu-id="dc313-142">The data source is now triggered for a manual refresh.</span></span> <span data-ttu-id="dc313-143">Деректер көзін жаңарту нысан схемасын және деректер көзінде көрсетілген барлық нысандар үшін деректерді жаңартады.</span><span class="sxs-lookup"><span data-stu-id="dc313-143">Refreshing a data source will update both the entity schema as well as data for all the entities specified in the data source.</span></span>

4. <span data-ttu-id="dc313-144">Бұрыннан жаңартудан бас тартқыңыз келсе, **Жаңартуды тоқтату** пәрменін таңдаңыз және деректер көзі соңғы жаңарту күйіне оралады.</span><span class="sxs-lookup"><span data-stu-id="dc313-144">Select **Stop refreshing** if you want to cancel an existing refresh and the data source will revert to its last refresh status.</span></span>

## <a name="delete-a-data-source"></a><span data-ttu-id="dc313-145">Деректер көзін жою</span><span class="sxs-lookup"><span data-stu-id="dc313-145">Delete a data source</span></span>

1. <span data-ttu-id="dc313-146">Аудитория мәліметтерінде **Деректер** > **Деректер көздері** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="dc313-146">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="dc313-147">Жою қажет деректер көзі жанындағы тік көп нүктені таңдаңыз және ашылмалы мәзірден **Жою** опциясын басыңыз.</span><span class="sxs-lookup"><span data-stu-id="dc313-147">Select the vertical ellipsis next to the data source you want to remove and select **Delete** from the drop-down menu.</span></span>

3. <span data-ttu-id="dc313-148">Жоюды растаңыз.</span><span class="sxs-lookup"><span data-stu-id="dc313-148">Confirm your deletion.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]