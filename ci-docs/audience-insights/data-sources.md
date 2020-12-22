---
title: Деректерді қабылдау үшін деректер көздерін пайдалану
description: Деректерді әртүрлі көздерден импорттау әдісін үйреніңіз.
ms.date: 11/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: a720641f7499fc71ff5bceeba48d296c51f77242
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643960"
---
# <a name="overview-about-data-sources"></a><span data-ttu-id="43462-103">Дерек көздеріне шолу</span><span class="sxs-lookup"><span data-stu-id="43462-103">Overview about data sources</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="43462-104">Dynamics 365 Customer Insights бағдарламасындағы аудитория түсініктерінің мүмкіндігі дерек көздерінің кең жиынындағы деректерге байланысады.</span><span class="sxs-lookup"><span data-stu-id="43462-104">The audience insights capability in Dynamics 365 Customer Insights connects to data from a broad set of sources.</span></span> <span data-ttu-id="43462-105">Дерек көзіне қосылуды көбінесе *деректерді қабылдау* процесі деп атайды.</span><span class="sxs-lookup"><span data-stu-id="43462-105">Connecting to a data source is often referred to as the process of *data ingestion*.</span></span> <span data-ttu-id="43462-106">Деректерді қабылдағаннан кейін, [біріктіру](data-unification.md) әрекетін жасауға және ол бойынша шаралар қабылдауға болады.</span><span class="sxs-lookup"><span data-stu-id="43462-106">After ingesting the data, you can [unify](data-unification.md) and take action on it.</span></span>

## <a name="add-a-data-source"></a><span data-ttu-id="43462-107">Деректер көзін қосу</span><span class="sxs-lookup"><span data-stu-id="43462-107">Add a data source</span></span>

<span data-ttu-id="43462-108">Таңдаған опцияға байланысты деректер көзін қосу әдісі туралы егжей-тегжейлі мақалаларды қараңыз.</span><span class="sxs-lookup"><span data-stu-id="43462-108">Refer to the detailed articles on how to add a data source, depending on which option you choose.</span></span>

<span data-ttu-id="43462-109">Деректер көзін үш негізгі жолмен қосуға болады:</span><span class="sxs-lookup"><span data-stu-id="43462-109">You can add a data source in three main ways:</span></span>

- [<span data-ttu-id="43462-110">Ондаған Power Query қосқыштары арқылы</span><span class="sxs-lookup"><span data-stu-id="43462-110">Through dozens of Power Query connectors</span></span>](connect-power-query.md)
- [<span data-ttu-id="43462-111">Common Data Model қалтасынан</span><span class="sxs-lookup"><span data-stu-id="43462-111">From a Common Data Model folder</span></span>](connect-common-data-model.md)
- [<span data-ttu-id="43462-112">Common Data Service көлінен</span><span class="sxs-lookup"><span data-stu-id="43462-112">From your own Common Data Service lake</span></span>](connect-common-data-service-lake.md)

> [!NOTE]
> <span data-ttu-id="43462-113">Жергілікті деректер көздерінен деректерді әлі қосуға болмайды.</span><span class="sxs-lookup"><span data-stu-id="43462-113">You can't add data from on-premises data sources yet.</span></span>

## <a name="review-ingested-data"></a><span data-ttu-id="43462-114">Қабылданған деректерді қарап шығу</span><span class="sxs-lookup"><span data-stu-id="43462-114">Review ingested data</span></span>

<span data-ttu-id="43462-115">Әр қабылданған деректер көзі атауын, күйін және осы көздер үшін соңғы рет жаңартылған деректерді көресіз.</span><span class="sxs-lookup"><span data-stu-id="43462-115">You'll see the name of each ingested data source, its status, and the last time the data was refreshed for that source.</span></span> <span data-ttu-id="43462-116">Деректер көздерінің тізімін әр баған бойынша сұрыптауға болады.</span><span class="sxs-lookup"><span data-stu-id="43462-116">You can sort the list of data sources by every column.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="43462-117">![Деректер көзі қосылды](media/configure-data-datasource-added.png "Деректер көзі қосылды")</span><span class="sxs-lookup"><span data-stu-id="43462-117">![Data source added](media/configure-data-datasource-added.png "Data source added")</span></span>

|<span data-ttu-id="43462-118">Күй</span><span class="sxs-lookup"><span data-stu-id="43462-118">Status</span></span>  |<span data-ttu-id="43462-119">Сипаттамасы</span><span class="sxs-lookup"><span data-stu-id="43462-119">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="43462-120">Орындалды</span><span class="sxs-lookup"><span data-stu-id="43462-120">Successful</span></span>   |<span data-ttu-id="43462-121">Уақыт **Қайта жаңартылған** бағанында көрсетілген болса, деректер көзі сәтті қабылданады.</span><span class="sxs-lookup"><span data-stu-id="43462-121">Data source was successfully ingested if a time is mentioned in the **Refreshed** column.</span></span>
|<span data-ttu-id="43462-122">Басталған жоқ</span><span class="sxs-lookup"><span data-stu-id="43462-122">Not started</span></span>   |<span data-ttu-id="43462-123">Деректер көзінде әлі қабылданған немесе жоба режиміндегі деректер жоқ.</span><span class="sxs-lookup"><span data-stu-id="43462-123">The data source has no data ingested yet or still in draft mode.</span></span>         |
|<span data-ttu-id="43462-124">Жаңартылуда</span><span class="sxs-lookup"><span data-stu-id="43462-124">Refreshing</span></span>    |<span data-ttu-id="43462-125">Деректер қабылдануда.</span><span class="sxs-lookup"><span data-stu-id="43462-125">Data ingestion is in progress.</span></span> <span data-ttu-id="43462-126">**Әрекеттер** бағанынан **Жаңартуды тоқтату** параметрін таңдау арқылы осы жұмыстан бас тарта аласыз.</span><span class="sxs-lookup"><span data-stu-id="43462-126">You can cancel this operation by selecting **Stop refreshing** in the **Actions** column.</span></span> <span data-ttu-id="43462-127">Деректер көзін жаңартуды тоқтату оның соңғы жаңарту күйін қайтарады.</span><span class="sxs-lookup"><span data-stu-id="43462-127">Stopping the refresh of a data source will revert it to its last refresh state.</span></span>       |
|<span data-ttu-id="43462-128">Сәтсіз аяқталған</span><span class="sxs-lookup"><span data-stu-id="43462-128">Failed</span></span>     |<span data-ttu-id="43462-129">Деректер қабылдау кезінде қателер орын алды.</span><span class="sxs-lookup"><span data-stu-id="43462-129">Data ingestion ran into errors.</span></span>         |

<span data-ttu-id="43462-130">Жаңарту күйі туралы қосымша мәліметтерді, оның ішінде қателіктер туралы және төмен ағынды процесті жаңарту туралы қарап шығу үшін **Жаңарту күйі** пәрменін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="43462-130">Select **Refresh status** to review more details on the refresh status, including error details and downstream process updates.</span></span>

<span data-ttu-id="43462-131">Деректерді жүктеуге біраз уақыт кетуі мүмкін.</span><span class="sxs-lookup"><span data-stu-id="43462-131">Loading data can take some time.</span></span> <span data-ttu-id="43462-132">Сәтті жаңартқан соң, қабылданған деректерді **Нысандар** бетінен қарап шығуға болады.</span><span class="sxs-lookup"><span data-stu-id="43462-132">After a successful refresh, the ingested data can be reviewed from the **Entities** page.</span></span> <span data-ttu-id="43462-133">Қосымша ақпаратты [Нысандар](entities.md) бөлімінен қараңыз.</span><span class="sxs-lookup"><span data-stu-id="43462-133">For more information, see [Entities](entities.md).</span></span>

## <a name="refresh-a-data-source"></a><span data-ttu-id="43462-134">Деректер көзін жаңарту</span><span class="sxs-lookup"><span data-stu-id="43462-134">Refresh a data source</span></span>

<span data-ttu-id="43462-135">Деректер көздерін автоматты кесте бойынша жаңартуға немесе сұраныс бойынша қолмен жаңартуға болады.</span><span class="sxs-lookup"><span data-stu-id="43462-135">Data sources can be refreshed on an automatic schedule or refreshed manually on demand.</span></span> 

<span data-ttu-id="43462-136">Барлық қабылданған деректер көздерінің жоспарланған жаңартуларын конфигурациялау үшін **Әкімші** > **Жүйе** > [**Кесте**](system.md#schedule-tab) тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="43462-136">Go to **Admin** > **System** > [**Schedule**](system.md#schedule-tab) to configure scheduled refreshes of all your ingested data sources.</span></span>

<span data-ttu-id="43462-137">Сұраныс бойынша деректер көзін жаңарту үшін келесі қадамдарды орындаңыз:</span><span class="sxs-lookup"><span data-stu-id="43462-137">To refresh a data source on demand, follow these steps:</span></span>

1. <span data-ttu-id="43462-138">Аудитория мәліметтерінде **Деректер** > **Деректер көздері** тармағына өтіңіз</span><span class="sxs-lookup"><span data-stu-id="43462-138">In audience insights, go to **Data** > **Data sources**</span></span>

2. <span data-ttu-id="43462-139">Жаңартқыңыз келетін деректер көзі жанындағы тік эллипсті таңдап, ашылмалы тізімнен **Жаңарту** пәрменін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="43462-139">Select the vertical ellipsis next to the data source you want to refresh and select **Refresh** from the drop-down list.</span></span>

3. <span data-ttu-id="43462-140">Қолмен жаңарту үшін деректер көзі іске қосылды.</span><span class="sxs-lookup"><span data-stu-id="43462-140">The data source is now triggered for a manual refresh.</span></span> <span data-ttu-id="43462-141">Деректер көзін жаңарту нысан схемасын және деректер көзінде көрсетілген барлық нысандар үшін деректерді жаңартады.</span><span class="sxs-lookup"><span data-stu-id="43462-141">Refreshing a data source will update both the entity schema as well as data for all the entities specified in the data source.</span></span>

4. <span data-ttu-id="43462-142">Бұрыннан жаңартудан бас тартқыңыз келсе, **Жаңартуды тоқтату** пәрменін таңдаңыз және деректер көзі соңғы жаңарту күйіне оралады.</span><span class="sxs-lookup"><span data-stu-id="43462-142">Select **Stop refreshing** if you want to cancel an existing refresh and the data source will revert to its last refresh status.</span></span>

## <a name="delete-a-data-source"></a><span data-ttu-id="43462-143">Деректер көзін жою</span><span class="sxs-lookup"><span data-stu-id="43462-143">Delete a data source</span></span>

1. <span data-ttu-id="43462-144">Аудитория мәліметтерінде **Деректер** > **Деректер көздері** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="43462-144">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="43462-145">Жою қажет деректер көзі жанындағы тік көп нүктені таңдаңыз және ашылмалы мәзірден **Жою** опциясын басыңыз.</span><span class="sxs-lookup"><span data-stu-id="43462-145">Select the vertical ellipsis next to the data source you want to remove and select **Delete** from the drop-down menu.</span></span>

3. <span data-ttu-id="43462-146">Жоюды растаңыз.</span><span class="sxs-lookup"><span data-stu-id="43462-146">Confirm your deletion.</span></span>
