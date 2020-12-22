---
title: Тұтынушы профильдерін іздеу және сүзгілеу
description: Бірыңғай тұтынушы профильдері туралы ақпаратты жылдам тауып, көрсетілген төлсипаттарды сүзгілеңіз.
ms.date: 04/16/2020
ms.reviewer: nimagen
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 1842ad333c23bb155abc89167556163ae79cdd34
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406253"
---
# <a name="customer-profiles-search--filter-index"></a><span data-ttu-id="36773-103">Тұтынушы профильдері: Іздеу және сүзгілеу индексі</span><span class="sxs-lookup"><span data-stu-id="36773-103">Customer profiles: Search & filter index</span></span>

<span data-ttu-id="36773-104">Тұтынушы деректерін біріктіру нәтижесі — жалпы тұтынушы негізіне бірыңғай көріністі қамтамасыз ететін Тұтынушы профилінің нысаны.</span><span class="sxs-lookup"><span data-stu-id="36773-104">The result of unifying your customer data is a Customer Profile entity that provides a unified view into your total customer base.</span></span> <span data-ttu-id="36773-105">[Белгілі бір тұтынушыны немесе тұтынушылар тобын](customer-profiles.md) жылдам табу үшін **Тұтынушылар** бетінде **Іздеу** және **Сүзгілеу** мүмкіндіктерін теңшей аласыз.</span><span class="sxs-lookup"><span data-stu-id="36773-105">To quickly [find information on a specific customer or group of customers](customer-profiles.md), you can configure the **Search** and **Filter** capabilities on the **Customers** page.</span></span> <span data-ttu-id="36773-106">Пайдаланушыларға іздеу және сүзгілеу үшін қолжетімді әкімшілердің **Іздеу және сүзгілеу индексі** бетінде төлсипаттарды өңдеу жолы туралы ақпаратты оқып шығыңыз.</span><span class="sxs-lookup"><span data-stu-id="36773-106">Read on to learn how admins can edit the attributes on the **Search & filter index** page, which are available to users for searching and filtering.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="36773-107">![Сүзгіні іздеу](media/search-filter.png "Сүзгіні іздеу")</span><span class="sxs-lookup"><span data-stu-id="36773-107">![Search filter](media/search-filter.png "Search filter")</span></span>

## <a name="add-fields-and-specify-attributes"></a><span data-ttu-id="36773-108">Өрістерді қосу және төлсипаттарды көрсету</span><span class="sxs-lookup"><span data-stu-id="36773-108">Add fields and specify attributes</span></span>

<span data-ttu-id="36773-109">Ізделетін төлсипаттарды әкімші ретінде алғаш рет анықтасаңыз, алдымен индекстелген өрістерді анықтауыңыз керек.</span><span class="sxs-lookup"><span data-stu-id="36773-109">If it's the first time you define searchable attributes as an administrator, you need to define indexed fields first.</span></span> <span data-ttu-id="36773-110">**Тұтынушылар** бетінде пайдаланушылар тұтынушыларды іздей және сүзгілей алатын барлық төлсипаттарды таңдауды ұсынамыз.</span><span class="sxs-lookup"><span data-stu-id="36773-110">We suggest you choose all the attributes by which users can search and filter customers on the **Customers** page.</span></span> <span data-ttu-id="36773-111">Деректерді біріктіру процесі барысында жасалған Тұтынушы профилі нысанында бар төлсипаттарды ғана көрсете аласыз.</span><span class="sxs-lookup"><span data-stu-id="36773-111">You can only specify attributes that exist in the Customer Profile entity that you created during the data unification process.</span></span>

1. <span data-ttu-id="36773-112">**Тұтынушылар** бетін ашып, **Іздеу және сүзгілеу индексі** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="36773-112">Open the **Customers** page and select **Search & filter index**.</span></span>

> [!NOTE]
> <span data-ttu-id="36773-113">Карта бетінде анықталғанда мына семантикалық түрлерден Тұтынушы нысанында қолжетімді төлсипаттардан әдепкі іздеу индексінің конфигурациясын жазасыз.</span><span class="sxs-lookup"><span data-stu-id="36773-113">We create a default search index configuration on the available attributes in the Customer entity from the following semantic types as defined on the Map page.</span></span>
> - <span data-ttu-id="36773-114">Тұлғаның аты, тегі, әкесінің аты, аты-жөні</span><span class="sxs-lookup"><span data-stu-id="36773-114">Person First name, Last name, Middle name, Full Name</span></span>
> - <span data-ttu-id="36773-115">Ұйымның аты</span><span class="sxs-lookup"><span data-stu-id="36773-115">Organization Name</span></span>
> - <span data-ttu-id="36773-116">Электрондық пошта мекенжайы</span><span class="sxs-lookup"><span data-stu-id="36773-116">Email address</span></span>
> - <span data-ttu-id="36773-117">Телефон нөмірі</span><span class="sxs-lookup"><span data-stu-id="36773-117">Phone number</span></span>
> - <span data-ttu-id="36773-118">Орын туралы ақпарат</span><span class="sxs-lookup"><span data-stu-id="36773-118">Location information</span></span>

2. <span data-ttu-id="36773-119">Индекстелген өрістерді көрсету үшін **+ Қосу** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="36773-119">Select **+ Add** to specify the indexed fields.</span></span>

3. <span data-ttu-id="36773-120">Индекстелген өрістерді қосу керек тізімнен төлсипаттарды таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="36773-120">Select the attributes in the list you want to add as indexed fields.</span></span> <span data-ttu-id="36773-121">**Қосу** параметрін таңдау арқылы үнемі қосымша төлсипаттарды қоса аласыз.</span><span class="sxs-lookup"><span data-stu-id="36773-121">You can always add more attributes by selecting **Add**.</span></span> <span data-ttu-id="36773-122">**Жою** таңбасын таңдау арқылы таңдалған төлсипаттарды да жоя аласыз.</span><span class="sxs-lookup"><span data-stu-id="36773-122">You can also remove any selected attributes by selecting the **Remove** symbol.</span></span>

## <a name="explore-the-indexed-customer-fields-table"></a><span data-ttu-id="36773-123">Индекстелген тұтынушы өрістері кестесін зерттеу</span><span class="sxs-lookup"><span data-stu-id="36773-123">Explore the Indexed customer fields table</span></span>

<span data-ttu-id="36773-124">Кестеде мына ақпарат көрсетіледі.</span><span class="sxs-lookup"><span data-stu-id="36773-124">The following information is presented in the table.</span></span>

- <span data-ttu-id="36773-125">**Аты**: төлсипат атын Тұтынушы профилі нысанында пайда болғандай көрсетеді.</span><span class="sxs-lookup"><span data-stu-id="36773-125">**Name**: Represents the attribute's name as it appears in the Customer Profile entity.</span></span>
- <span data-ttu-id="36773-126">**Деректер түрі**: деректер түрі жол, сан немесе күн екендігін көрсетеді.</span><span class="sxs-lookup"><span data-stu-id="36773-126">**Data type**: Specifies whether the data type is a string, a number, or a date.</span></span>
- <span data-ttu-id="36773-127">**Іздеуге қосылған**: **Тұтынушылар** бетінде **Іздеу** өрісі көмегімен тұтынушыларды іздеуге қолданылуы мүмкін осы төлсипатты көрсетеді.</span><span class="sxs-lookup"><span data-stu-id="36773-127">**Included in search**: Specifies whether this attribute can be used for searching customers on the **Customers** page using the **Search** field.</span></span>
- <span data-ttu-id="36773-128">**Сүзгі қосу**: **Тұтынушылар** бетінде осы төлсипатты сүзгілеуге қолдану жолын анықтайтын басқару құралы.</span><span class="sxs-lookup"><span data-stu-id="36773-128">**Add Filter**: Control to define how this attribute can be used for filtering on the **Customers** page.</span></span>

## <a name="editing-filtering-options-for-a-given-attribute"></a><span data-ttu-id="36773-129">Берілген төлсипатты сүзгілеу опцияларын өңдеу</span><span class="sxs-lookup"><span data-stu-id="36773-129">Editing filtering options for a given attribute</span></span>

<span data-ttu-id="36773-130">**Тұтынушылар** бетіндегі **Сүзгі** мәзірінде әр түрлі төлсипат деңгейлері болуы мүмкін (мысалы, тұтынушыларды сүзгілейтін әр түрлі жас топтары).</span><span class="sxs-lookup"><span data-stu-id="36773-130">The **Filter** menu on the **Customers** page can include a varying number of attribute levels (for example, different age groups to filter customers by).</span></span>

1. <span data-ttu-id="36773-131">**Іздеу және сүзгілеу индексі** бетінде берілген төлсипат үшін **Өріс қосу** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="36773-131">Select **Add Filter** for a given attribute on the **Search & filter index** page.</span></span> <span data-ttu-id="36773-132">Нәтижелер санын және олар ұйымдастырылған ретті анықтай аласыз.</span><span class="sxs-lookup"><span data-stu-id="36773-132">You can define the number of results and the order in which they'll be organized.</span></span> <span data-ttu-id="36773-133">Төлсипат деректерінің түріне байланысты мына тақталардың бірі пайда болады.</span><span class="sxs-lookup"><span data-stu-id="36773-133">Depending on the attribute's data type, one of the following panes appears.</span></span>

- <span data-ttu-id="36773-134">Жол түріндегі төлсипаттар: **Жолды сүзгілеу опциялары** тақтасында қажетті нәтижелер саны мен олар ұйымдастырылған ретті көрсетіңіз.</span><span class="sxs-lookup"><span data-stu-id="36773-134">String-type attributes: Specify the number of desired results on the **String filter options** pane and the order policy by which they'll be organized.</span></span>

- <span data-ttu-id="36773-135">Сан түріндегі төлсипаттар: **Санын сүзгілеу опциялары** тақтасында қосылған аралықтар мен олар ұйымдастырылған ретті көрсетіңіз.</span><span class="sxs-lookup"><span data-stu-id="36773-135">Numerical-type attributes: Specify the intervals included on the **Number filter options** pane and the order policy by which they'll be organized.</span></span>

- <span data-ttu-id="36773-136">Күн түріндегі төлсипаттар: **Күнді сүзгілеу опциялары** тақтасында қосылған аралықтар мен олар ұйымдастырылған ретті көрсетіңіз.</span><span class="sxs-lookup"><span data-stu-id="36773-136">Date-type attributes:  Specify the intervals included on the **Date filter options** pane and the order policy by which they'll be organized.</span></span>

2. <span data-ttu-id="36773-137">Өзгерістерді қолдану үшін **Сақтау** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="36773-137">Select **Save** to apply your changes.</span></span>

3. <span data-ttu-id="36773-138">Параметрлерді қолдануға дайын болған кезде **Іске қосу** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="36773-138">Select **Run** once you're ready to apply your settings.</span></span>
