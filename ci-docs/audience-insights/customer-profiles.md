---
title: Тұтынушы профильдерін қарау
description: Тұтынушының бірыңғай деректерінің аралас көрінісін алыңыз.
ms.date: 12/01/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: 433e6ceda0ec7827bd672cff40f895d7719561df
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896334"
---
# <a name="customer-profiles"></a><span data-ttu-id="fc980-103">Тұтынушы профильдері</span><span class="sxs-lookup"><span data-stu-id="fc980-103">Customer profiles</span></span>

<span data-ttu-id="fc980-104">**Тұтынушылар** бетінде [барлық деректер көздерінен](data-sources.md) алынған профиль деректері негізінде тұтынушылардың біріктірілген көрінісі көрсетіледі.</span><span class="sxs-lookup"><span data-stu-id="fc980-104">The **Customers** page shows a combined view of your customers, based on profile data gathered from [all data sources](data-sources.md).</span></span> <span data-ttu-id="fc980-105">[Бірыңғай тұтынушы нысанын жасаған](data-unification.md) кезде тұтынушы профильдері қолжетімді.</span><span class="sxs-lookup"><span data-stu-id="fc980-105">Customer profiles are available once you [create the unified Customer entity](data-unification.md).</span></span> <span data-ttu-id="fc980-106">Тұтынушылардың толығырақ көріністерін алу үшін деректерді біріктіруді аяқтаңыз.</span><span class="sxs-lookup"><span data-stu-id="fc980-106">Make sure you complete the data unification process to get richer views of your customers.</span></span> <span data-ttu-id="fc980-107">Сонымен қатар, бет тұтынушыларды іздеуге мүмкіндік береді.</span><span class="sxs-lookup"><span data-stu-id="fc980-107">The page also lets you search for customers.</span></span>

<span data-ttu-id="fc980-108">Тұтынушылар жеке тұлғалар немесе ұйымдар болуы мүмкін (алдын ала қарау).</span><span class="sxs-lookup"><span data-stu-id="fc980-108">Customers can be individuals or organizations (preview).</span></span> <span data-ttu-id="fc980-109">Әрбір тұтынушы немесе ұйым профилі қатар бойынша көрсетіледі.</span><span class="sxs-lookup"><span data-stu-id="fc980-109">Each customer or organization profile is represented by a tile.</span></span> <span data-ttu-id="fc980-110">Белгілі бір тұтынушыдағы немесе ұйымдағы қосымша ақпаратты көру үшін қатарды таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="fc980-110">Select a tile to see additional information on that specific customer or organization.</span></span> <span data-ttu-id="fc980-111">Қосымша жазбаларды көру үшін беттің астындағы парақтау басқару құралдарын пайдаланыңыз.</span><span class="sxs-lookup"><span data-stu-id="fc980-111">Use the pagination controls at the bottom of the page to see additional records.</span></span>

> [!div class="mx-imgBorder"] 
> <span data-ttu-id="fc980-112">![Бизнес - тұтынушы профильдері](media/profiles-customers.png "Бизнес - тұтынушы профильдері")</span><span class="sxs-lookup"><span data-stu-id="fc980-112">![B2C customer profiles](media/profiles-customers.png "B2C customer profiles")</span></span>

<span data-ttu-id="fc980-113">Ұйымдар (алдын ала қарау)</span><span class="sxs-lookup"><span data-stu-id="fc980-113">Organizations (Preview)</span></span>
> [!div class="mx-imgBorder"] 
> <span data-ttu-id="fc980-114">![Бизнес - бизнес профильдері](media/profile-customers-b2b.png "Бизнес - бизнес профильдері")</span><span class="sxs-lookup"><span data-stu-id="fc980-114">![B2B customer profiles](media/profile-customers-b2b.png "B2B customer profiles")</span></span>

> [!NOTE]
> <span data-ttu-id="fc980-115">Шарлау кезінде **Тұтынушылар** опциясын таңдағанда қатарлар көрінбесе, әкімшіңіз **Іздеу және сүзгілеу индексі** опциясында [кемінде бір іздеу төлсипатын анықтауы](search-filter-index.md) қажет.</span><span class="sxs-lookup"><span data-stu-id="fc980-115">If you can't see the tiles when you select **Customers** in navigation, your administrator needs to [define at least one searchable attribute](search-filter-index.md) on the **Search & filter index**.</span></span>

## <a name="search-for-customers"></a><span data-ttu-id="fc980-116">Тұтынушыларды іздеу</span><span class="sxs-lookup"><span data-stu-id="fc980-116">Search for customers</span></span>

<span data-ttu-id="fc980-117">Іздеу терезесіне атын немесе кейбір басқа төлсипатты енгізу арқылы тұтынушыларды іздеңіз.</span><span class="sxs-lookup"><span data-stu-id="fc980-117">Search for customers by entering a name or some other attribute in the search box.</span></span> <span data-ttu-id="fc980-118">деректерді біріктіру процесі барысында жасалған Тұтынушы профилінде ғана ізделінеді.</span><span class="sxs-lookup"><span data-stu-id="fc980-118">The search only works within the Customer Profile entity created during the data unification process.</span></span>

<span data-ttu-id="fc980-119">Әкімші ретінде **Іздеу және сүзгілеу индексі** бетін пайдаланып ізделетін төлсипаттарды теңшей аласыз.</span><span class="sxs-lookup"><span data-stu-id="fc980-119">As an admin, you can configure the searchable attributes using the **Search & filter index** page.</span></span> <span data-ttu-id="fc980-120">Қосымша ақпаратты [Іздеу және сүзгілеу индексін басқару](search-filter-index.md) бөлімін қараңыз.</span><span class="sxs-lookup"><span data-stu-id="fc980-120">For more information, see [Manage search & filter index](search-filter-index.md).</span></span>

## <a name="filter-customers"></a><span data-ttu-id="fc980-121">Тұтынушыларды сүзгілеу</span><span class="sxs-lookup"><span data-stu-id="fc980-121">Filter customers</span></span>

<span data-ttu-id="fc980-122">Тұтынушыларды Тұтынушы профилі нысанының өрістері бойынша сүзгілей аласыз.</span><span class="sxs-lookup"><span data-stu-id="fc980-122">You can filter customers by the Customer Profile entity fields.</span></span> <span data-ttu-id="fc980-123">Іздеумен қатар, әкімшіңіз **Іздеу және сүзгілеу индексі** бетін пайдаланып сүзгіленетін өрістерді анықтауы керек.</span><span class="sxs-lookup"><span data-stu-id="fc980-123">Similar to search, your admin will first need to define the fields as filterable using the **Search & filter index** page.</span></span>

1. <span data-ttu-id="fc980-124">**Тұтынушылар** бетінде **Сүзгі** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="fc980-124">Select **Filter** on the **Customers** page.</span></span>

2. <span data-ttu-id="fc980-125">Тұтынушыларды сүзгілеу керек төлсипаттардан кейінгі терезелерді белгілеңіз.</span><span class="sxs-lookup"><span data-stu-id="fc980-125">Check the boxes next to the attributes you want to filter customers by.</span></span>

   > [!div class="mx-imgBorder"] 
   > <span data-ttu-id="fc980-126">![Тұтынушы профильдері](media/profiles-customers3.png "Тұтынушы профильдері")</span><span class="sxs-lookup"><span data-stu-id="fc980-126">![Customer profiles](media/profiles-customers3.png "Customer profiles")</span></span>

3. <span data-ttu-id="fc980-127">**Тұтынушылар** бетінде **Сүзгілерді жою** опциясын таңдау арқылы сүзгілерді алып тастаңыз.</span><span class="sxs-lookup"><span data-stu-id="fc980-127">Remove your filters by selecting **Clear filters** on the **Customers** page.</span></span>

##  <a name="customer-details-page"></a><span data-ttu-id="fc980-128">Тұтынушы мәліметтері беті</span><span class="sxs-lookup"><span data-stu-id="fc980-128">Customer details page</span></span>

<span data-ttu-id="fc980-129">**Тұтынушы мәліметтері бетін** ашу үшін тұтынушы қатарларының бірін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="fc980-129">Select any of the customer tiles to open the **Customer details page**.</span></span> <span data-ttu-id="fc980-130">Бұл көріністе таңдалған тұтынушыға арналған бірыңғай ақпарат бар.</span><span class="sxs-lookup"><span data-stu-id="fc980-130">This view contains unified information for the selected customer.</span></span>

<span data-ttu-id="fc980-131">Тұтынушы мәліметтері мыналарды қамтиды:</span><span class="sxs-lookup"><span data-stu-id="fc980-131">Customer details include:</span></span>

-   <span data-ttu-id="fc980-132">**Тұтынушы профилі қатары:** бұл қатар бірыңғай тұтынушы профилі нысанының әртүрлі мәндерін көрсетеді.</span><span class="sxs-lookup"><span data-stu-id="fc980-132">**Customer profile tile:** This tile shows the different values from the unified customer profile entity.</span></span> <span data-ttu-id="fc980-133">Бұл мәліметтер электрондық пошта мекен-жайын, атын, қаласын және т.с.с. қамтуы мүмкін.</span><span class="sxs-lookup"><span data-stu-id="fc980-133">These details can include email address, name, city, and so on.</span></span> 

-   <span data-ttu-id="fc980-134">**Ықтимал қызығушылықтар, әлеуетті брендтер:** бірінші тараптық арттыруды реттегеніңізді көрсетеді.</span><span class="sxs-lookup"><span data-stu-id="fc980-134">**Potential interests, potential brands:** Shows if you configured a first-party enrichment.</span></span> <span data-ttu-id="fc980-135">Бұл тұтынушыға ұқсас профилі бар тұтынушы брендтері үшін ықтимал қызығушылықтар мен ұқсастықтарды білдіреді.</span><span class="sxs-lookup"><span data-stu-id="fc980-135">It represents potential interests and affinities for brands a customer with a profile similar to this customer might have.</span></span> <span data-ttu-id="fc980-136">Қосымша ақпаратты [Тұтынушы профильдерін бренд және қызығушылық ұқсастықтарымен арттыру](enrichment-microsoft.md) бөлімінен қараңыз.</span><span class="sxs-lookup"><span data-stu-id="fc980-136">For more information, see [Enrich customer profiles with brand and interest affinities](enrichment-microsoft.md).</span></span>

-   <span data-ttu-id="fc980-137">**Өлшемдер:** белгілі бір түрдегі бір немесе бірнеше өлшемді конфигурациялағаныңызды көрсетеді: тұтынушының төлсипат өлшемдері.</span><span class="sxs-lookup"><span data-stu-id="fc980-137">**Measures:** Shows if you configured one or more measures of a specific type: customer attribute measures.</span></span> <span data-ttu-id="fc980-138">Олар сіздің тұтынушыларыңыздың жеке тұтынушылар деңгейіндегі есептелген KPI-ді қамтиды.</span><span class="sxs-lookup"><span data-stu-id="fc980-138">They include calculated KPIs around your customers on the individual customer level.</span></span> <span data-ttu-id="fc980-139">Қосымша ақпарат алу үшін [Өлшемдерді анықтау және басқару](measures.md) тақырыбын қараңыз.</span><span class="sxs-lookup"><span data-stu-id="fc980-139">For more information, see [Define and manage measures](measures.md).</span></span>

-   <span data-ttu-id="fc980-140">**Әрекеттің уақыт шкаласы:** Әрекеттерді конфигурациялағаныңызды көрсетеді.</span><span class="sxs-lookup"><span data-stu-id="fc980-140">**Activity timeline:** Shows if you have configured activities.</span></span> <span data-ttu-id="fc980-141">Уақыт кестесінің көрінісі осы тұтынушының соңғы әрекеттен бастап хронологиялық түрде сұрыпталған әрекеттерін қамтиды.</span><span class="sxs-lookup"><span data-stu-id="fc980-141">The timeline view contains chronologically sorted activities of this customer, starting with the most recent activity.</span></span> <span data-ttu-id="fc980-142">Қосымша ақпаратты [Тұтынушы әрекеттері](activities.md) бөлімінен қараңыз.</span><span class="sxs-lookup"><span data-stu-id="fc980-142">For more information, see [Customer activities](activities.md).</span></span>

<span data-ttu-id="fc980-143">Тұтынушыны іздеу парағына оралу үшін **Тұтынушыларға оралу** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="fc980-143">Select **Back to Customers** to return to the customer search page.</span></span>

## <a name="next-steps"></a><span data-ttu-id="fc980-144">Келесі қадамдар</span><span class="sxs-lookup"><span data-stu-id="fc980-144">Next steps</span></span>

<span data-ttu-id="fc980-145">[Қосымша дерек көздерін қосу ](data-sources.md)немесе [тұтынушы сегменттерін құру](segments.md).</span><span class="sxs-lookup"><span data-stu-id="fc980-145">[Add more data sources](data-sources.md) or [create customer segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]