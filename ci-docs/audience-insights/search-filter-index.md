---
title: Тұтынушы профильдерін іздеу және сүзгілеу
description: Бірыңғай тұтынушы профильдері туралы ақпаратты жылдам тауып, көрсетілген төлсипаттарды сүзгілеңіз.
ms.date: 01/19/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: b6cc0ad1a47a6c00e3bf220271f42870fc53621b
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597150"
---
# <a name="customer-profiles-search--filter-index"></a><span data-ttu-id="df4ec-103">Тұтынушы профильдері: Іздеу және сүзгілеу индексі</span><span class="sxs-lookup"><span data-stu-id="df4ec-103">Customer profiles: Search & filter index</span></span>

<span data-ttu-id="df4ec-104">Тұтынушы деректерін біріктіру нәтижесі — жалпы тұтынушы негізіне бірыңғай көріністі қамтамасыз ететін Тұтынушы профилінің нысаны.</span><span class="sxs-lookup"><span data-stu-id="df4ec-104">The result of unifying your customer data is a Customer Profile entity that provides a unified view into your total customer base.</span></span> <span data-ttu-id="df4ec-105">[Белгілі бір тұтынушыны немесе тұтынушылар тобын](customer-profiles.md) жылдам табу үшін **Тұтынушылар** бетінде **Іздеу** және **Сүзгілеу** мүмкіндіктерін теңшей аласыз.</span><span class="sxs-lookup"><span data-stu-id="df4ec-105">To quickly [find information on a specific customer or group of customers](customer-profiles.md), you can configure the **Search** and **Filter** capabilities on the **Customers** page.</span></span> <span data-ttu-id="df4ec-106">Пайдаланушыларға іздеу және сүзгілеу үшін қолжетімді әкімшілердің **Іздеу және сүзгілеу индексі** бетінде төлсипаттарды өңдеу жолы туралы ақпаратты оқып шығыңыз.</span><span class="sxs-lookup"><span data-stu-id="df4ec-106">Read on to learn how admins can edit the attributes on the **Search & filter index** page, which are available to users for searching and filtering.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="df4ec-107">![Сүзгіні іздеу](media/search-filter.png "Сүзгіні іздеу")</span><span class="sxs-lookup"><span data-stu-id="df4ec-107">![Search filter](media/search-filter.png "Search filter")</span></span>

## <a name="add-fields-and-specify-attributes"></a><span data-ttu-id="df4ec-108">Өрістерді қосу және төлсипаттарды көрсету</span><span class="sxs-lookup"><span data-stu-id="df4ec-108">Add fields and specify attributes</span></span>

<span data-ttu-id="df4ec-109">Ізделетін төлсипаттарды әкімші ретінде алғаш рет анықтасаңыз, алдымен индекстелген өрістерді анықтауыңыз керек.</span><span class="sxs-lookup"><span data-stu-id="df4ec-109">If it's the first time you define searchable attributes as an administrator, you need to define indexed fields first.</span></span> <span data-ttu-id="df4ec-110">**Тұтынушылар** бетінде пайдаланушылар тұтынушыларды іздей және сүзгілей алатын барлық төлсипаттарды таңдауды ұсынамыз.</span><span class="sxs-lookup"><span data-stu-id="df4ec-110">We suggest you choose all the attributes by which users can search and filter customers on the **Customers** page.</span></span> <span data-ttu-id="df4ec-111">Деректерді біріктіру процесі барысында жасалған Тұтынушы профилі нысанында бар төлсипаттарды ғана көрсете аласыз.</span><span class="sxs-lookup"><span data-stu-id="df4ec-111">You can only specify attributes that exist in the Customer Profile entity that you created during the data unification process.</span></span>

1. <span data-ttu-id="df4ec-112">**Тұтынушылар** бетін ашып, **Іздеу және сүзгілеу индексі** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="df4ec-112">Open the **Customers** page and select **Search & filter index**.</span></span>

2. <span data-ttu-id="df4ec-113">Индекстелген өрістерді көрсету үшін **+ Қосу** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="df4ec-113">Select **+ Add** to specify the indexed fields.</span></span>

3. <span data-ttu-id="df4ec-114">Индекстелген өрістерді қосу керек тізімнен төлсипаттарды таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="df4ec-114">Select the attributes in the list you want to add as indexed fields.</span></span> <span data-ttu-id="df4ec-115">**Қосу** параметрін таңдау арқылы үнемі қосымша төлсипаттарды қоса аласыз.</span><span class="sxs-lookup"><span data-stu-id="df4ec-115">You can always add more attributes by selecting **Add**.</span></span> <span data-ttu-id="df4ec-116">**Жою** таңбасын таңдау арқылы таңдалған төлсипаттарды да жоя аласыз.</span><span class="sxs-lookup"><span data-stu-id="df4ec-116">You can also remove any selected attributes by selecting the **Remove** symbol.</span></span>

## <a name="explore-the-indexed-customer-fields-table"></a><span data-ttu-id="df4ec-117">Индекстелген тұтынушы өрістері кестесін зерттеу</span><span class="sxs-lookup"><span data-stu-id="df4ec-117">Explore the Indexed customer fields table</span></span>

<span data-ttu-id="df4ec-118">Кестеде мына ақпарат көрсетіледі.</span><span class="sxs-lookup"><span data-stu-id="df4ec-118">The following information is presented in the table.</span></span>

- <span data-ttu-id="df4ec-119">**Аты**: төлсипат атын Тұтынушы профилі нысанында пайда болғандай көрсетеді.</span><span class="sxs-lookup"><span data-stu-id="df4ec-119">**Name**: Represents the attribute's name as it appears in the Customer Profile entity.</span></span>
- <span data-ttu-id="df4ec-120">**Деректер түрі**: деректер түрі жол, сан немесе күн екендігін көрсетеді.</span><span class="sxs-lookup"><span data-stu-id="df4ec-120">**Data type**: Specifies whether the data type is a string, a number, or a date.</span></span>
- <span data-ttu-id="df4ec-121">**Іздеуге қосылған**: **Тұтынушылар** бетінде **Іздеу** өрісі көмегімен тұтынушыларды іздеуге қолданылуы мүмкін осы төлсипатты көрсетеді.</span><span class="sxs-lookup"><span data-stu-id="df4ec-121">**Included in search**: Specifies whether this attribute can be used for searching customers on the **Customers** page using the **Search** field.</span></span>
- <span data-ttu-id="df4ec-122">**Сүзгі қосу**: **Тұтынушылар** бетінде осы төлсипатты сүзгілеуге қолдану жолын анықтайтын басқару құралы.</span><span class="sxs-lookup"><span data-stu-id="df4ec-122">**Add Filter**: Control to define how this attribute can be used for filtering on the **Customers** page.</span></span>

## <a name="editing-filtering-options-for-a-given-attribute"></a><span data-ttu-id="df4ec-123">Берілген төлсипатты сүзгілеу опцияларын өңдеу</span><span class="sxs-lookup"><span data-stu-id="df4ec-123">Editing filtering options for a given attribute</span></span>

<span data-ttu-id="df4ec-124">**Тұтынушылар** бетіндегі **Сүзгі** мәзірінде әр түрлі төлсипат деңгейлері болуы мүмкін (мысалы, тұтынушыларды сүзгілейтін әр түрлі жас топтары).</span><span class="sxs-lookup"><span data-stu-id="df4ec-124">The **Filter** menu on the **Customers** page can include a varying number of attribute levels (for example, different age groups to filter customers by).</span></span>

1. <span data-ttu-id="df4ec-125">**Іздеу және сүзгілеу индексі** бетінде берілген төлсипат үшін **Өріс қосу** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="df4ec-125">Select **Add Filter** for a given attribute on the **Search & filter index** page.</span></span> <span data-ttu-id="df4ec-126">Нәтижелер санын және олар ұйымдастырылған ретті анықтай аласыз.</span><span class="sxs-lookup"><span data-stu-id="df4ec-126">You can define the number of results and the order in which they'll be organized.</span></span> <span data-ttu-id="df4ec-127">Төлсипат деректерінің түріне байланысты мына тақталардың бірі пайда болады.</span><span class="sxs-lookup"><span data-stu-id="df4ec-127">Depending on the attribute's data type, one of the following panes appears.</span></span>

- <span data-ttu-id="df4ec-128">Жол түріндегі төлсипаттар: **Жолды сүзгілеу опциялары** тақтасында қажетті нәтижелер саны мен олар ұйымдастырылған ретті көрсетіңіз.</span><span class="sxs-lookup"><span data-stu-id="df4ec-128">String-type attributes: Specify the number of desired results on the **String filter options** pane and the order policy by which they'll be organized.</span></span>

- <span data-ttu-id="df4ec-129">Сан түріндегі төлсипаттар: **Санын сүзгілеу опциялары** тақтасында қосылған аралықтар мен олар ұйымдастырылған ретті көрсетіңіз.</span><span class="sxs-lookup"><span data-stu-id="df4ec-129">Numerical-type attributes: Specify the intervals included on the **Number filter options** pane and the order policy by which they'll be organized.</span></span>

- <span data-ttu-id="df4ec-130">Күн түріндегі төлсипаттар: **Күнді сүзгілеу опциялары** тақтасында қосылған аралықтар мен олар ұйымдастырылған ретті көрсетіңіз.</span><span class="sxs-lookup"><span data-stu-id="df4ec-130">Date-type attributes:  Specify the intervals included on the **Date filter options** pane and the order policy by which they'll be organized.</span></span>

2. <span data-ttu-id="df4ec-131">Өзгерістерді қолдану үшін **Сақтау** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="df4ec-131">Select **Save** to apply your changes.</span></span>

3. <span data-ttu-id="df4ec-132">Параметрлерді қолдануға дайын болған кезде **Іске қосу** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="df4ec-132">Select **Run** once you're ready to apply your settings.</span></span>

## <a name="next-steps"></a><span data-ttu-id="df4ec-133">Келесі қадамдар</span><span class="sxs-lookup"><span data-stu-id="df4ec-133">Next steps</span></span>

<span data-ttu-id="df4ec-134">Тұтынушы профильдерін іздеу үшін **Тұтынушылар** бетіне өтіңіз немесе барлық тұтынушы профильдерінің қосалқы жиынын көру үшін индекстелген өрістерді пайдаланыңыз.</span><span class="sxs-lookup"><span data-stu-id="df4ec-134">Go to the **Customers** page to search for customer profiles or use the indexed fields to see a subset of all customer profiles.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]