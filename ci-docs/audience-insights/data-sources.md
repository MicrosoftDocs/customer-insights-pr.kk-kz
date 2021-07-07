---
title: Деректерді қабылдау үшін деректер көздерін пайдалану
description: Деректерді әртүрлі көздерден импорттау әдісін үйреніңіз.
ms.date: 04/12/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 54dd7b629d4b4e7f640b932b0f9246e0602f46bd
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304703"
---
# <a name="data-sources-overview"></a><span data-ttu-id="b435b-103">Деректер көздеріне шолу</span><span class="sxs-lookup"><span data-stu-id="b435b-103">Data sources overview</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="b435b-104">Dynamics 365 Customer Insights бағдарламасындағы аудитория түсініктерінің мүмкіндігі дерек көздерінің кең жиынындағы деректерге байланысады.</span><span class="sxs-lookup"><span data-stu-id="b435b-104">The audience insights capability in Dynamics 365 Customer Insights connects to data from a broad set of sources.</span></span> <span data-ttu-id="b435b-105">Дерек көзіне қосылуды көбінесе *деректерді қабылдау* процесі деп атайды.</span><span class="sxs-lookup"><span data-stu-id="b435b-105">Connecting to a data source is often referred to as the process of *data ingestion*.</span></span> <span data-ttu-id="b435b-106">Деректерді қабылдағаннан кейін, [біріктіру](data-unification.md) әрекетін жасауға және ол бойынша шаралар қабылдауға болады.</span><span class="sxs-lookup"><span data-stu-id="b435b-106">After ingesting the data, you can [unify](data-unification.md) and take action on it.</span></span>

## <a name="add-a-data-source"></a><span data-ttu-id="b435b-107">Деректер көзін қосу</span><span class="sxs-lookup"><span data-stu-id="b435b-107">Add a data source</span></span>

<span data-ttu-id="b435b-108">Таңдаған опцияға байланысты деректер көзін қосу әдісі туралы егжей-тегжейлі мақалаларды қараңыз.</span><span class="sxs-lookup"><span data-stu-id="b435b-108">Refer to the detailed articles on how to add a data source, depending on which option you choose.</span></span>

<span data-ttu-id="b435b-109">Деректер көзін үш негізгі жолмен қосуға болады:</span><span class="sxs-lookup"><span data-stu-id="b435b-109">You can add a data source in three main ways:</span></span>

- [<span data-ttu-id="b435b-110">Ондаған Power Query қосқыштары арқылы</span><span class="sxs-lookup"><span data-stu-id="b435b-110">Through dozens of Power Query connectors</span></span>](connect-power-query.md)
- [<span data-ttu-id="b435b-111">Common Data Model қалтасынан</span><span class="sxs-lookup"><span data-stu-id="b435b-111">From a Common Data Model folder</span></span>](connect-common-data-model.md)
- [<span data-ttu-id="b435b-112">Microsoft Dataverse көлінен</span><span class="sxs-lookup"><span data-stu-id="b435b-112">From your own Microsoft Dataverse lake</span></span>](connect-common-data-service-lake.md)

## <a name="add-data-from-on-premises-data-sources"></a><span data-ttu-id="b435b-113">Жергілікті деректер көздерінен деректерді қосу</span><span class="sxs-lookup"><span data-stu-id="b435b-113">Add data from on-premises data sources</span></span>

<span data-ttu-id="b435b-114">Жергілікті деректер көздеріндегі деректерді аудитория туралы түсініктеріне енгізуге Microsoft Power Platform деректер ағындары негізінде қолдау көрсетіледі.</span><span class="sxs-lookup"><span data-stu-id="b435b-114">Ingesting data from on-premises data sources in audience insights is supported based on Microsoft Power Platform dataflows.</span></span> <span data-ttu-id="b435b-115">Деректер ағындарын Customer Insights бағдарламасында ортаны орнату кезінде [Microsoft Dataverse ортасының URL мекенжайын қамтамасыз ету](manage-environments.md#create-an-environment-in-an-existing-organization) арқылы қосуға болады.</span><span class="sxs-lookup"><span data-stu-id="b435b-115">Dataflows can be enabled in Customer Insights by [providing the Microsoft Dataverse environment URL](manage-environments.md#create-an-environment-in-an-existing-organization) when setting up the environment.</span></span>

<span data-ttu-id="b435b-116">Dataverse ортасын Customer Insights бағдарламасымен байланыстырғаннан кейін жасалған деректер көздері әдепкі бойынша [Power Platform деректер ағындарын](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) пайдаланады.</span><span class="sxs-lookup"><span data-stu-id="b435b-116">Data sources that are created after associating a Dataverse environment with Customer Insights will use [Power Platform dataflows](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) by default.</span></span> <span data-ttu-id="b435b-117">Деректер ағындары деректер шлюзін пайдалану арқылы жергілікті байланысқа қолдау көрсетеді.</span><span class="sxs-lookup"><span data-stu-id="b435b-117">Dataflows support on-premises connectivity using the data gateway.</span></span> <span data-ttu-id="b435b-118">Dataverse ортасы [жергілікті деректер шлюздерін пайдалану](/data-integration/gateway/service-gateway-app.md) үшін байланыстырылғанға дейін болған деректер көздерін жойыңыз немесе қайта жасаңыз.</span><span class="sxs-lookup"><span data-stu-id="b435b-118">Remove and recreate data sources that existed before a Dataverse environment was associated to [use the on-premises data gateways](/data-integration/gateway/service-gateway-app.md).</span></span>

<span data-ttu-id="b435b-119">Бұрыннан бар Power BI немесе Power Apps ортасындағы деректер шлюздері көрінеді және оларды Customer Insights бағдарламасында қайта пайдалануға болады.</span><span class="sxs-lookup"><span data-stu-id="b435b-119">Data gateways from an existing Power BI or Power Apps environment will be visible and you can reuse in Customer Insights.</span></span> <span data-ttu-id="b435b-120">Деректер көздері бетінде Microsoft Power Platform ортасына өтетін сілтемелер көрсетіледі, онда сіз жергілікті деректер шлюздерін көріп және конфигурациялай аласыз.</span><span class="sxs-lookup"><span data-stu-id="b435b-120">The data sources page shows links to go to the Microsoft Power Platform environment where you can view and configure on-premises data gateways.</span></span>

## <a name="review-ingested-data"></a><span data-ttu-id="b435b-121">Қабылданған деректерді қарап шығу</span><span class="sxs-lookup"><span data-stu-id="b435b-121">Review ingested data</span></span>

<span data-ttu-id="b435b-122">Әр қабылданған деректер көзі атауын, күйін және осы көздер үшін соңғы рет жаңартылған деректерді көресіз.</span><span class="sxs-lookup"><span data-stu-id="b435b-122">You'll see the name of each ingested data source, its status, and the last time the data was refreshed for that source.</span></span> <span data-ttu-id="b435b-123">Деректер көздерінің тізімін әр баған бойынша сұрыптауға болады.</span><span class="sxs-lookup"><span data-stu-id="b435b-123">You can sort the list of data sources by every column.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="b435b-124">![Деректер көзі қосылды](media/configure-data-datasource-added.png "Деректер көзі қосылды")</span><span class="sxs-lookup"><span data-stu-id="b435b-124">![Data source added](media/configure-data-datasource-added.png "Data source added")</span></span>

|<span data-ttu-id="b435b-125">Күй</span><span class="sxs-lookup"><span data-stu-id="b435b-125">Status</span></span>  |<span data-ttu-id="b435b-126">Сипаттамасы</span><span class="sxs-lookup"><span data-stu-id="b435b-126">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="b435b-127">Орындалды</span><span class="sxs-lookup"><span data-stu-id="b435b-127">Successful</span></span>   |<span data-ttu-id="b435b-128">Уақыт **Қайта жаңартылған** бағанында көрсетілген болса, деректер көзі сәтті қабылданады.</span><span class="sxs-lookup"><span data-stu-id="b435b-128">Data source was successfully ingested if a time is mentioned in the **Refreshed** column.</span></span>
|<span data-ttu-id="b435b-129">Басталған жоқ</span><span class="sxs-lookup"><span data-stu-id="b435b-129">Not started</span></span>   |<span data-ttu-id="b435b-130">Деректер көзінде әлі қабылданған немесе жоба режиміндегі деректер жоқ.</span><span class="sxs-lookup"><span data-stu-id="b435b-130">The data source has no data ingested yet or still in draft mode.</span></span>         |
|<span data-ttu-id="b435b-131">Жаңартылуда</span><span class="sxs-lookup"><span data-stu-id="b435b-131">Refreshing</span></span>    |<span data-ttu-id="b435b-132">Деректер қабылдануда.</span><span class="sxs-lookup"><span data-stu-id="b435b-132">Data ingestion is in progress.</span></span> <span data-ttu-id="b435b-133">**Әрекеттер** бағанынан **Жаңартуды тоқтату** параметрін таңдау арқылы осы жұмыстан бас тарта аласыз.</span><span class="sxs-lookup"><span data-stu-id="b435b-133">You can cancel this operation by selecting **Stop refreshing** in the **Actions** column.</span></span> <span data-ttu-id="b435b-134">Деректер көзін жаңартуды тоқтату оның соңғы жаңарту күйін қайтарады.</span><span class="sxs-lookup"><span data-stu-id="b435b-134">Stopping the refresh of a data source will revert it to its last refresh state.</span></span>       |
|<span data-ttu-id="b435b-135">Сәтсіз аяқталған</span><span class="sxs-lookup"><span data-stu-id="b435b-135">Failed</span></span>     |<span data-ttu-id="b435b-136">Деректер қабылдау кезінде қателер орын алды.</span><span class="sxs-lookup"><span data-stu-id="b435b-136">Data ingestion ran into errors.</span></span>         |

<span data-ttu-id="b435b-137">Толығырақ мәліметтерді қарап шығу үшін кез келген деректер көзінің **Күй** бағанында мәнді таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="b435b-137">Select the value in the **Status** column of any data source to review more details.</span></span> <span data-ttu-id="b435b-138">**Орындалу барысы туралы мәліметтер** тақтасында **Деректер көздері** терезесін кеңейтіңіз.</span><span class="sxs-lookup"><span data-stu-id="b435b-138">In the **Progress details** pane, expand **Data sources**.</span></span> <span data-ttu-id="b435b-139">Жаңарту күйі туралы қосымша ақпаратты, оның ішінде қателер туралы және төмен ағынды процесті жаңарту туралы қарап шығу үшін **Мәліметтерді қарау** пәрменін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="b435b-139">Select **See details** for more information about the refresh status, including error details and downstream process updates.</span></span>

<span data-ttu-id="b435b-140">Деректерді жүктеу уақыт алуы мүмкін.</span><span class="sxs-lookup"><span data-stu-id="b435b-140">Loading data can take time.</span></span> <span data-ttu-id="b435b-141">Сәтті жаңартқан соң, қабылданған деректерді **Нысандар** бетінен қарап шығуға болады.</span><span class="sxs-lookup"><span data-stu-id="b435b-141">After a successful refresh, the ingested data can be reviewed from the **Entities** page.</span></span> <span data-ttu-id="b435b-142">Қосымша ақпаратты [Нысандар](entities.md) бөлімінен қараңыз.</span><span class="sxs-lookup"><span data-stu-id="b435b-142">For more information, see [Entities](entities.md).</span></span>

## <a name="refresh-a-data-source"></a><span data-ttu-id="b435b-143">Деректер көзін жаңарту</span><span class="sxs-lookup"><span data-stu-id="b435b-143">Refresh a data source</span></span>

<span data-ttu-id="b435b-144">Деректер көздерін автоматты кесте бойынша жаңартуға немесе сұраныс бойынша қолмен жаңартуға болады.</span><span class="sxs-lookup"><span data-stu-id="b435b-144">Data sources can be refreshed on an automatic schedule or refreshed manually on demand.</span></span> 

<span data-ttu-id="b435b-145">Барлық қабылданған деректер көздерінің жоспарланған жаңартуларын конфигурациялау үшін **Әкімші** > **Жүйе** > [**Кесте**](system.md#schedule-tab) тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="b435b-145">Go to **Admin** > **System** > [**Schedule**](system.md#schedule-tab) to configure scheduled refreshes of all your ingested data sources.</span></span>

<span data-ttu-id="b435b-146">Сұраныс бойынша деректер көзін жаңарту үшін келесі қадамдарды орындаңыз:</span><span class="sxs-lookup"><span data-stu-id="b435b-146">To refresh a data source on demand, follow these steps:</span></span>

1. <span data-ttu-id="b435b-147">Аудитория мәліметтерінде **Деректер** > **Деректер көздері** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="b435b-147">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="b435b-148">Жаңарту керек деректер көзі жанындағы тік көп нүктені таңдаңыз және ашылмалы тізімнен **Жаңарту** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="b435b-148">Select the vertical ellipsis next to the data source you want to refresh and select **Refresh** from the dropdown list.</span></span>

3. <span data-ttu-id="b435b-149">Қолмен жаңарту үшін деректер көзі іске қосылды.</span><span class="sxs-lookup"><span data-stu-id="b435b-149">The data source is now triggered for a manual refresh.</span></span> <span data-ttu-id="b435b-150">Деректер көзін жаңарту нысан схемасын да, деректер көзінде көрсетілген барлық нысандар үшін деректерді де жаңартады.</span><span class="sxs-lookup"><span data-stu-id="b435b-150">Refreshing a data source will update both the entity schema and data for all the entities specified in the data source.</span></span>

4. <span data-ttu-id="b435b-151">Бұрыннан жаңартудан бас тартқыңыз келсе, **Жаңартуды тоқтату** пәрменін таңдаңыз және деректер көзі соңғы жаңарту күйіне оралады.</span><span class="sxs-lookup"><span data-stu-id="b435b-151">Select **Stop refreshing** if you want to cancel an existing refresh and the data source will revert to its last refresh status.</span></span>

## <a name="delete-a-data-source"></a><span data-ttu-id="b435b-152">Деректер көзін жою</span><span class="sxs-lookup"><span data-stu-id="b435b-152">Delete a data source</span></span>

1. <span data-ttu-id="b435b-153">Аудитория мәліметтерінде **Деректер** > **Деректер көздері** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="b435b-153">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="b435b-154">Жою керек деректер көзі жанындағы тік көп нүктені таңдаңыз және ашылмалы мәзірден **Жою** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="b435b-154">Select the vertical ellipsis next to the data source you want to remove and select **Delete** from the dropdown menu.</span></span>

3. <span data-ttu-id="b435b-155">Жоюды растаңыз.</span><span class="sxs-lookup"><span data-stu-id="b435b-155">Confirm your deletion.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
