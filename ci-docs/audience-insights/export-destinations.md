---
title: Customer Insights бағдарламасынан деректерді экспорттау
description: Деректерді бөлісу үшін экспорттауы басқарыңыз.
ms.date: 03/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 354ce9ef30fe918975d06290430996c84f8bd3f7
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896150"
---
# <a name="exports-preview-overview"></a><span data-ttu-id="03d92-103">Экспорттауларға (алдын ала қарау нұсқасы) шолу</span><span class="sxs-lookup"><span data-stu-id="03d92-103">Exports (preview) overview</span></span>

<span data-ttu-id="03d92-104">**Экспорттаулар** беті барлық конфигурацияланған экспорттарды көрсетеді.</span><span class="sxs-lookup"><span data-stu-id="03d92-104">The **Exports** page shows you all configured exports.</span></span> <span data-ttu-id="03d92-105">Экспорттау белгілі бір деректерді әртүрлі бағдарламалармен бөліседі.</span><span class="sxs-lookup"><span data-stu-id="03d92-105">Exports share specific data with various applications.</span></span> <span data-ttu-id="03d92-106">Олар тұтынушы профильдерін немесе нысандарын, схемалар мен салыстыру мәліметтерін қамтуы мүмкін.</span><span class="sxs-lookup"><span data-stu-id="03d92-106">They can include customer profiles or entities, schemas, and mapping details.</span></span> <span data-ttu-id="03d92-107">Әрбір экспорттау [аутентификация мен кіруді басқару үшін әкімші орнатқан қосылымды](connections.md) қажет етеді.</span><span class="sxs-lookup"><span data-stu-id="03d92-107">Each export requires a [connection, set up by an administrator, to manage authentication and access](connections.md).</span></span>

> [!NOTE]
> <span data-ttu-id="03d92-108">2021 жылдың наурыз айына дейін экспорттау тиісті қызметке автоматты түрде қосылым жасады.</span><span class="sxs-lookup"><span data-stu-id="03d92-108">Until March 2021, exports created a connection to the corresponding service automatically.</span></span> <span data-ttu-id="03d92-109">Экспорттау енді оларды жасамас бұрын [әкімші жасаған және бөліскен қосылымды](connections.md) қажет етеді.</span><span class="sxs-lookup"><span data-stu-id="03d92-109">Exports now require a [connection, created and shared by an administrator](connections.md) before you can create them.</span></span>

<span data-ttu-id="03d92-110">Экспорттау бетін көру үшін **Деректер** > **Экспорттау** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="03d92-110">Go to **Data** > **Exports** to view the exports page.</span></span> <span data-ttu-id="03d92-111">Пайдаланушының барлық рөлдерінде конфигурацияланған экспорттауды көруге рұқсаты бар.</span><span class="sxs-lookup"><span data-stu-id="03d92-111">All user roles have access to view configured exports.</span></span> <span data-ttu-id="03d92-112">Экспорттауды олардың атауы, қосылым атауы немесе қосылым түрі бойынша табу үшін пәрмен жолағындағы іздеу өрісін пайдаланыңыз.</span><span class="sxs-lookup"><span data-stu-id="03d92-112">Use of the search field in the command bar to find exports by their name, connection name, or connection type.</span></span>

## <a name="set-up-a-new-export"></a><span data-ttu-id="03d92-113">Жаңа экспорттауды орнату</span><span class="sxs-lookup"><span data-stu-id="03d92-113">Set up a new export</span></span>

<span data-ttu-id="03d92-114">Экспорттауды орнату немесе өңдеу үшін сізде қолжетімді қосылымдар болуы керек.</span><span class="sxs-lookup"><span data-stu-id="03d92-114">To set up or edit an export, you need to have connections available to you.</span></span> <span data-ttu-id="03d92-115">Қосылымдар сіздің [пайдаланушы рөліңізге](permissions.md) байланысты:</span><span class="sxs-lookup"><span data-stu-id="03d92-115">Connections depend on your [user role](permissions.md):</span></span>
- <span data-ttu-id="03d92-116">Әкімшілер барлық қосылымдарға қатынаса алады.</span><span class="sxs-lookup"><span data-stu-id="03d92-116">Administrators have access to all connections.</span></span> <span data-ttu-id="03d92-117">Сондай-ақ олар экспорттауды орнатқан кезде жаңа қосылымдар жасай алады.</span><span class="sxs-lookup"><span data-stu-id="03d92-117">They can also create new connections when setting up an export.</span></span>
- <span data-ttu-id="03d92-118">Салымшылар белгілі бір қосылымдарға қатынаса алады.</span><span class="sxs-lookup"><span data-stu-id="03d92-118">Contributors can have access to specific connections.</span></span> <span data-ttu-id="03d92-119">Олар қосылымдарды конфигурациялау және бөлісу үшін әкімшілерге тәуелді.</span><span class="sxs-lookup"><span data-stu-id="03d92-119">They depend on administrators to configure and share connections.</span></span> <span data-ttu-id="03d92-120">Қосымша ақпарат алу үшін [Салымшыларға экспорттау үшін қосылымды пайдалануға рұқсат беру](connections.md#allow-contributors-to-use-a-connection-for-exports) бөлімін қараңыз.</span><span class="sxs-lookup"><span data-stu-id="03d92-120">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>
- <span data-ttu-id="03d92-121">Көрушілер тек бұрыннан бар экспортты көре алады, бірақ оны жасай алмайды.</span><span class="sxs-lookup"><span data-stu-id="03d92-121">Viewers can only view existing exports but not create them.</span></span>

1. <span data-ttu-id="03d92-122">**Деректер** > **Экспорттау** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="03d92-122">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="03d92-123">Жаңа экспорттау мақсатты орнын жасау үшін **Экспорттау қосу** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="03d92-123">Select **Add export** to create a new export destination.</span></span>

1. <span data-ttu-id="03d92-124">**Экспортты орнату** тақтасында пайдаланылатын қосылымды таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="03d92-124">In the **Set up export** pane, select which connection to use.</span></span> <span data-ttu-id="03d92-125">[Қосылымдар](connections.md) әкімшілер арқылы басқарылады.</span><span class="sxs-lookup"><span data-stu-id="03d92-125">[Connections](connections.md) are managed by administrators.</span></span> 

1. <span data-ttu-id="03d92-126">Қажетті мәліметтерді енгізіңіз және экспорттауды жасау үшін **Сақтау** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="03d92-126">Provide the required details and select **Save** to create the export.</span></span>

### <a name="edit-an-export"></a><span data-ttu-id="03d92-127">Экспорттауды өңдеу</span><span class="sxs-lookup"><span data-stu-id="03d92-127">Edit an export</span></span>

1. <span data-ttu-id="03d92-128">Өңдеу қажет экспорттаудың мақсатты орнына арналған тік көп нүктені таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="03d92-128">Select the vertical ellipsis for the export destination you want to edit.</span></span>

1. <span data-ttu-id="03d92-129">Ашылмалы мәзірден **Өңдеу** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="03d92-129">Select **Edit** from the drop-down menu.</span></span>

1. <span data-ttu-id="03d92-130">Жаңарту керек мәндерді таңдаңыз және **Сақтау** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="03d92-130">Change the values you want to update and select **Save**.</span></span>

## <a name="view-exports-and-export-details"></a><span data-ttu-id="03d92-131">Экспорттауды және экспорттау туралы мәліметтерді көру</span><span class="sxs-lookup"><span data-stu-id="03d92-131">View Exports and export details</span></span>

<span data-ttu-id="03d92-132">Экспорттаудың мақсатты орындарын жасағаннан кейін олар **Деректер** > **Экспорттау** тармағында тізімделеді.</span><span class="sxs-lookup"><span data-stu-id="03d92-132">After creating export destinations, they are listed on **Data** > **Exports**.</span></span> <span data-ttu-id="03d92-133">Барлық пайдаланушылар қандай деректер бөлісілетінін және оның соңғы күйін көре алады.</span><span class="sxs-lookup"><span data-stu-id="03d92-133">All users can see which data is shared and its latest status.</span></span>

1. <span data-ttu-id="03d92-134">**Деректер** > **Экспорттау** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="03d92-134">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="03d92-135">Өңдеу рұқсаттары жоқ пайдаланушылар экспорттау туралы мәліметтерді көру үшін **Өңдеу** түймешігінің орнына **Көру** түймешігін таңдайды.</span><span class="sxs-lookup"><span data-stu-id="03d92-135">Users without edit permissions select **View** instead of **Edit** see the export details.</span></span>

1. <span data-ttu-id="03d92-136">Бұл бүйірлік тақта осы экспорттаудың орнатылуын көрсетеді.</span><span class="sxs-lookup"><span data-stu-id="03d92-136">This side pane shows the set up of this export.</span></span> <span data-ttu-id="03d92-137">Өңдеу рұқсаттарынсыз мәндерді өзгерту мүмкін емес.</span><span class="sxs-lookup"><span data-stu-id="03d92-137">Without edit permissions, you can't change values.</span></span> <span data-ttu-id="03d92-138">Экспорттау бетіне оралу үшін **Жабу** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="03d92-138">Select **Close** to return to the exports page.</span></span>

## <a name="run-exports-on-demand"></a><span data-ttu-id="03d92-139">Экспорттауды сұрау бойынша іске қосу</span><span class="sxs-lookup"><span data-stu-id="03d92-139">Run exports on demand</span></span>

<span data-ttu-id="03d92-140">Экспорттауды конфигурациялағаннан кейін, оның жұмыс қосылымды болғанша ол әр [жоспарланған жаңартумен](system.md#schedule-tab) іске қосылады.</span><span class="sxs-lookup"><span data-stu-id="03d92-140">After configuring an export, it will run with every [scheduled refresh](system.md#schedule-tab) as long as it has a working connection.</span></span>

<span data-ttu-id="03d92-141">Жоспарланған жаңартуды күтпестен деректерді экспорттау үшін **Деректер** > **Экспорттау** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="03d92-141">To export data without waiting for a scheduled refresh, go to **Data** > **Exports**.</span></span> <span data-ttu-id="03d92-142">Екі таңдауыңыз бар:</span><span class="sxs-lookup"><span data-stu-id="03d92-142">You have two options:</span></span>

- <span data-ttu-id="03d92-143">Барлық экспорттауларды іске қосу үшін пәрмен жолағында **Барлығын іске қосу** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="03d92-143">To run all exports, select **Run all** in the command bar.</span></span> 
- <span data-ttu-id="03d92-144">Бір рет экспорттауды іске қосу үшін тізім элементінен көп нүктені (...) таңдап, содан кейін **Іске қосу** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="03d92-144">To run a single export, select the ellipsis (...) on a list item and then choose **Run**.</span></span>

## <a name="remove-an-export"></a><span data-ttu-id="03d92-145">Экспорттауды алып тастау</span><span class="sxs-lookup"><span data-stu-id="03d92-145">Remove an Export</span></span>

1. <span data-ttu-id="03d92-146">**Деректер** > **Экспорттау** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="03d92-146">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="03d92-147">Алып тастау қажет экспорттау үшін тік көп нүктені таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="03d92-147">Select the vertical ellipsis for the Export you want to remove.</span></span>

1. <span data-ttu-id="03d92-148">Ашылмалы тізімнен **Алып тастау** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="03d92-148">Select **Remove** from the dropdown menu.</span></span>

1. <span data-ttu-id="03d92-149">Растау экранында **Жою** опциясын таңдау арқылы жоюды растаңыз.</span><span class="sxs-lookup"><span data-stu-id="03d92-149">Confirm the removal by selecting **Remove** on the confirmation screen.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
