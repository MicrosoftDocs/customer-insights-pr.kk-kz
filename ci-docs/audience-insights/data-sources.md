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
ms.openlocfilehash: 0fc13d3ac0a5176637b6fe481dabe0b2aec11649
ms.sourcegitcommit: d89b19b2a3497722b78362aeee688ae7e94915d9
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 04/13/2021
ms.locfileid: "5887901"
---
# <a name="data-sources-overview"></a><span data-ttu-id="2e10d-103">Деректер көздеріне шолу</span><span class="sxs-lookup"><span data-stu-id="2e10d-103">Data sources overview</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="2e10d-104">Dynamics 365 Customer Insights бағдарламасындағы аудитория түсініктерінің мүмкіндігі дерек көздерінің кең жиынындағы деректерге байланысады.</span><span class="sxs-lookup"><span data-stu-id="2e10d-104">The audience insights capability in Dynamics 365 Customer Insights connects to data from a broad set of sources.</span></span> <span data-ttu-id="2e10d-105">Дерек көзіне қосылуды көбінесе *деректерді қабылдау* процесі деп атайды.</span><span class="sxs-lookup"><span data-stu-id="2e10d-105">Connecting to a data source is often referred to as the process of *data ingestion*.</span></span> <span data-ttu-id="2e10d-106">Деректерді қабылдағаннан кейін, [біріктіру](data-unification.md) әрекетін жасауға және ол бойынша шаралар қабылдауға болады.</span><span class="sxs-lookup"><span data-stu-id="2e10d-106">After ingesting the data, you can [unify](data-unification.md) and take action on it.</span></span>

## <a name="add-a-data-source"></a><span data-ttu-id="2e10d-107">Деректер көзін қосу</span><span class="sxs-lookup"><span data-stu-id="2e10d-107">Add a data source</span></span>

<span data-ttu-id="2e10d-108">Таңдаған опцияға байланысты деректер көзін қосу әдісі туралы егжей-тегжейлі мақалаларды қараңыз.</span><span class="sxs-lookup"><span data-stu-id="2e10d-108">Refer to the detailed articles on how to add a data source, depending on which option you choose.</span></span>

<span data-ttu-id="2e10d-109">Деректер көзін үш негізгі жолмен қосуға болады:</span><span class="sxs-lookup"><span data-stu-id="2e10d-109">You can add a data source in three main ways:</span></span>

- [<span data-ttu-id="2e10d-110">Ондаған Power Query қосқыштары арқылы</span><span class="sxs-lookup"><span data-stu-id="2e10d-110">Through dozens of Power Query connectors</span></span>](connect-power-query.md)
- [<span data-ttu-id="2e10d-111">Common Data Model қалтасынан</span><span class="sxs-lookup"><span data-stu-id="2e10d-111">From a Common Data Model folder</span></span>](connect-common-data-model.md)
- [<span data-ttu-id="2e10d-112">Common Data Service көлінен</span><span class="sxs-lookup"><span data-stu-id="2e10d-112">From your own Common Data Service lake</span></span>](connect-common-data-service-lake.md)

## <a name="add-data-from-on-premises-data-sources"></a><span data-ttu-id="2e10d-113">Жергілікті деректер көздерінен деректерді қосу</span><span class="sxs-lookup"><span data-stu-id="2e10d-113">Add data from on-premises data sources</span></span>

<span data-ttu-id="2e10d-114">Жергілікті деректер көздеріндегі деректерді Audience Insights бағдарламасына енгізуге Power Platform деректер ағындары негізінде қолдау көрсетіледі.</span><span class="sxs-lookup"><span data-stu-id="2e10d-114">Ingesting data from on-premises data sources in Audience Insights is supported based on Power Platform dataflows.</span></span> <span data-ttu-id="2e10d-115">Деректер ағындарын Customer Insights бағдарламасында ортаны орнату кезінде [Microsoft Dataverse ортасының URL мекенжайын қамтамасыз ету](manage-environments.md#create-an-environment-in-an-existing-organization) арқылы қосуға болады.</span><span class="sxs-lookup"><span data-stu-id="2e10d-115">Dataflows can be enabled in Customer Insights by [providing the Microsoft Dataverse environment URL](manage-environments.md#create-an-environment-in-an-existing-organization) when setting up the environment.</span></span>

<span data-ttu-id="2e10d-116">Dataverse ортасын Customer Insights бағдарламасымен байланыстырғаннан кейін жасалған деректер көздері әдепкі бойынша [Power Platform деректер ағындарын](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) пайдаланады.</span><span class="sxs-lookup"><span data-stu-id="2e10d-116">Data sources that are created after associating a Dataverse environment with Customer Insights will use [Power Platform dataflows](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) by default.</span></span> <span data-ttu-id="2e10d-117">Деректер ағындары деректер шлюздерін пайдаланып жергілікті байланысқа қолдау көрсетеді.</span><span class="sxs-lookup"><span data-stu-id="2e10d-117">Dataflows support on-prem connectivity using the data gateways.</span></span> <span data-ttu-id="2e10d-118">Dataverse ортасы жергілікті деректер шлюздерін пайдалану үшін байланыстырылғанға дейін болған деректер көздерін жойыңыз немесе қайта жасаңыз.</span><span class="sxs-lookup"><span data-stu-id="2e10d-118">Remove and recreate data sources that existed before a Dataverse environment was associated to use the on-premises data gateways.</span></span>

<span data-ttu-id="2e10d-119">Бұрыннан бар Power BI немесе Power Apps ортасындағы деректер шлюздері көрінеді және оларды Customer Insights бағдарламасында қайта пайдалануға болады.</span><span class="sxs-lookup"><span data-stu-id="2e10d-119">Data gateways from an existing Power BI or Power Apps environment will be visible and you can reuse in Customer Insights.</span></span> <span data-ttu-id="2e10d-120">Деректер көздері бетінде жергілікті деректер шлюздерін көруге және конфигурациялауға болатын Power Platform ортасына сілтеме көрсетіледі.</span><span class="sxs-lookup"><span data-stu-id="2e10d-120">The data sources page shows links to go the Power Platform environment where you can view and configure on-premises data gateways.</span></span>

:::image type="content" source="media/data-sources-onpremises-gateways.png" alt-text="Power Platform ортасын көрсететін сілтемелерді көрсететін деректер көздері бетінің скриншоты.":::

## <a name="review-ingested-data"></a><span data-ttu-id="2e10d-122">Қабылданған деректерді қарап шығу</span><span class="sxs-lookup"><span data-stu-id="2e10d-122">Review ingested data</span></span>

<span data-ttu-id="2e10d-123">Әр қабылданған деректер көзі атауын, күйін және осы көздер үшін соңғы рет жаңартылған деректерді көресіз.</span><span class="sxs-lookup"><span data-stu-id="2e10d-123">You'll see the name of each ingested data source, its status, and the last time the data was refreshed for that source.</span></span> <span data-ttu-id="2e10d-124">Деректер көздерінің тізімін әр баған бойынша сұрыптауға болады.</span><span class="sxs-lookup"><span data-stu-id="2e10d-124">You can sort the list of data sources by every column.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="2e10d-125">![Деректер көзі қосылды](media/configure-data-datasource-added.png "Деректер көзі қосылды")</span><span class="sxs-lookup"><span data-stu-id="2e10d-125">![Data source added](media/configure-data-datasource-added.png "Data source added")</span></span>

|<span data-ttu-id="2e10d-126">Күй</span><span class="sxs-lookup"><span data-stu-id="2e10d-126">Status</span></span>  |<span data-ttu-id="2e10d-127">Сипаттамасы</span><span class="sxs-lookup"><span data-stu-id="2e10d-127">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="2e10d-128">Орындалды</span><span class="sxs-lookup"><span data-stu-id="2e10d-128">Successful</span></span>   |<span data-ttu-id="2e10d-129">Уақыт **Қайта жаңартылған** бағанында көрсетілген болса, деректер көзі сәтті қабылданады.</span><span class="sxs-lookup"><span data-stu-id="2e10d-129">Data source was successfully ingested if a time is mentioned in the **Refreshed** column.</span></span>
|<span data-ttu-id="2e10d-130">Басталған жоқ</span><span class="sxs-lookup"><span data-stu-id="2e10d-130">Not started</span></span>   |<span data-ttu-id="2e10d-131">Деректер көзінде әлі қабылданған немесе жоба режиміндегі деректер жоқ.</span><span class="sxs-lookup"><span data-stu-id="2e10d-131">The data source has no data ingested yet or still in draft mode.</span></span>         |
|<span data-ttu-id="2e10d-132">Жаңартылуда</span><span class="sxs-lookup"><span data-stu-id="2e10d-132">Refreshing</span></span>    |<span data-ttu-id="2e10d-133">Деректер қабылдануда.</span><span class="sxs-lookup"><span data-stu-id="2e10d-133">Data ingestion is in progress.</span></span> <span data-ttu-id="2e10d-134">**Әрекеттер** бағанынан **Жаңартуды тоқтату** параметрін таңдау арқылы осы жұмыстан бас тарта аласыз.</span><span class="sxs-lookup"><span data-stu-id="2e10d-134">You can cancel this operation by selecting **Stop refreshing** in the **Actions** column.</span></span> <span data-ttu-id="2e10d-135">Деректер көзін жаңартуды тоқтату оның соңғы жаңарту күйін қайтарады.</span><span class="sxs-lookup"><span data-stu-id="2e10d-135">Stopping the refresh of a data source will revert it to its last refresh state.</span></span>       |
|<span data-ttu-id="2e10d-136">Сәтсіз аяқталған</span><span class="sxs-lookup"><span data-stu-id="2e10d-136">Failed</span></span>     |<span data-ttu-id="2e10d-137">Деректер қабылдау кезінде қателер орын алды.</span><span class="sxs-lookup"><span data-stu-id="2e10d-137">Data ingestion ran into errors.</span></span>         |

<span data-ttu-id="2e10d-138">Толығырақ мәліметтерді қарап шығу үшін кез келген деректер көзінің **Күй** бағанында мәнді таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="2e10d-138">Select the value in the **Status** column of any data source to review more details.</span></span> <span data-ttu-id="2e10d-139">**Орындалу барысы туралы мәліметтер** тақтасында **Деректер көздері** терезесін кеңейтіңіз.</span><span class="sxs-lookup"><span data-stu-id="2e10d-139">In the **Progress details** pane, expand **Data sources**.</span></span> <span data-ttu-id="2e10d-140">Жаңарту күйі туралы қосымша ақпаратты, оның ішінде қателер туралы және төмен ағынды процесті жаңарту туралы қарап шығу үшін **Мәліметтерді қарау** пәрменін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="2e10d-140">Select **See details** for more information about the refresh status, including error details and downstream process updates.</span></span>

<span data-ttu-id="2e10d-141">Деректерді жүктеуге біраз уақыт кетуі мүмкін.</span><span class="sxs-lookup"><span data-stu-id="2e10d-141">Loading data can take some time.</span></span> <span data-ttu-id="2e10d-142">Сәтті жаңартқан соң, қабылданған деректерді **Нысандар** бетінен қарап шығуға болады.</span><span class="sxs-lookup"><span data-stu-id="2e10d-142">After a successful refresh, the ingested data can be reviewed from the **Entities** page.</span></span> <span data-ttu-id="2e10d-143">Қосымша ақпаратты [Нысандар](entities.md) бөлімінен қараңыз.</span><span class="sxs-lookup"><span data-stu-id="2e10d-143">For more information, see [Entities](entities.md).</span></span>

## <a name="refresh-a-data-source"></a><span data-ttu-id="2e10d-144">Деректер көзін жаңарту</span><span class="sxs-lookup"><span data-stu-id="2e10d-144">Refresh a data source</span></span>

<span data-ttu-id="2e10d-145">Деректер көздерін автоматты кесте бойынша жаңартуға немесе сұраныс бойынша қолмен жаңартуға болады.</span><span class="sxs-lookup"><span data-stu-id="2e10d-145">Data sources can be refreshed on an automatic schedule or refreshed manually on demand.</span></span> 

<span data-ttu-id="2e10d-146">Барлық қабылданған деректер көздерінің жоспарланған жаңартуларын конфигурациялау үшін **Әкімші** > **Жүйе** > [**Кесте**](system.md#schedule-tab) тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="2e10d-146">Go to **Admin** > **System** > [**Schedule**](system.md#schedule-tab) to configure scheduled refreshes of all your ingested data sources.</span></span>

<span data-ttu-id="2e10d-147">Сұраныс бойынша деректер көзін жаңарту үшін келесі қадамдарды орындаңыз:</span><span class="sxs-lookup"><span data-stu-id="2e10d-147">To refresh a data source on demand, follow these steps:</span></span>

1. <span data-ttu-id="2e10d-148">Аудитория мәліметтерінде **Деректер** > **Деректер көздері** тармағына өтіңіз</span><span class="sxs-lookup"><span data-stu-id="2e10d-148">In audience insights, go to **Data** > **Data sources**</span></span>

2. <span data-ttu-id="2e10d-149">Жаңартқыңыз келетін деректер көзі жанындағы тік эллипсті таңдап, ашылмалы тізімнен **Жаңарту** пәрменін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="2e10d-149">Select the vertical ellipsis next to the data source you want to refresh and select **Refresh** from the drop-down list.</span></span>

3. <span data-ttu-id="2e10d-150">Қолмен жаңарту үшін деректер көзі іске қосылды.</span><span class="sxs-lookup"><span data-stu-id="2e10d-150">The data source is now triggered for a manual refresh.</span></span> <span data-ttu-id="2e10d-151">Деректер көзін жаңарту нысан схемасын да, деректер көзінде көрсетілген барлық нысандар үшін деректерді де жаңартады.</span><span class="sxs-lookup"><span data-stu-id="2e10d-151">Refreshing a data source will update both the entity schema and data for all the entities specified in the data source.</span></span>

4. <span data-ttu-id="2e10d-152">Бұрыннан жаңартудан бас тартқыңыз келсе, **Жаңартуды тоқтату** пәрменін таңдаңыз және деректер көзі соңғы жаңарту күйіне оралады.</span><span class="sxs-lookup"><span data-stu-id="2e10d-152">Select **Stop refreshing** if you want to cancel an existing refresh and the data source will revert to its last refresh status.</span></span>

## <a name="delete-a-data-source"></a><span data-ttu-id="2e10d-153">Деректер көзін жою</span><span class="sxs-lookup"><span data-stu-id="2e10d-153">Delete a data source</span></span>

1. <span data-ttu-id="2e10d-154">Аудитория мәліметтерінде **Деректер** > **Деректер көздері** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="2e10d-154">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="2e10d-155">Жою қажет деректер көзі жанындағы тік көп нүктені таңдаңыз және ашылмалы мәзірден **Жою** опциясын басыңыз.</span><span class="sxs-lookup"><span data-stu-id="2e10d-155">Select the vertical ellipsis next to the data source you want to remove and select **Delete** from the drop-down menu.</span></span>

3. <span data-ttu-id="2e10d-156">Жоюды растаңыз.</span><span class="sxs-lookup"><span data-stu-id="2e10d-156">Confirm your deletion.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
