---
title: Customer Insights бағдарламасынан деректерді экспорттау
description: Деректерді бөлісу үшін экспорттауы басқарыңыз.
ms.date: 03/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c1078ed0ba259a6e9cde3c7ede3570890ae48e67
ms.sourcegitcommit: 33a8e21b3bf6521bdb8346f81f79fce88091ddfd
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 05/10/2021
ms.locfileid: "6016621"
---
# <a name="exports-preview-overview"></a><span data-ttu-id="dcc27-103">Экспорттауларға (алдын ала қарау нұсқасы) шолу</span><span class="sxs-lookup"><span data-stu-id="dcc27-103">Exports (preview) overview</span></span>

<span data-ttu-id="dcc27-104">**Экспорттаулар** беті барлық конфигурацияланған экспорттарды көрсетеді.</span><span class="sxs-lookup"><span data-stu-id="dcc27-104">The **Exports** page shows you all configured exports.</span></span> <span data-ttu-id="dcc27-105">Экспорттау белгілі бір деректерді әртүрлі бағдарламалармен бөліседі.</span><span class="sxs-lookup"><span data-stu-id="dcc27-105">Exports share specific data with various applications.</span></span> <span data-ttu-id="dcc27-106">Олар тұтынушы профильдерін немесе нысандарын, схемалар мен салыстыру мәліметтерін қамтуы мүмкін.</span><span class="sxs-lookup"><span data-stu-id="dcc27-106">They can include customer profiles or entities, schemas, and mapping details.</span></span> <span data-ttu-id="dcc27-107">Әрбір экспорттау [аутентификация мен кіруді басқару үшін әкімші орнатқан қосылымды](connections.md) қажет етеді.</span><span class="sxs-lookup"><span data-stu-id="dcc27-107">Each export requires a [connection, set up by an administrator, to manage authentication and access](connections.md).</span></span>

<span data-ttu-id="dcc27-108">Экспорттау бетін көру үшін **Деректер** > **Экспорттау** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="dcc27-108">Go to **Data** > **Exports** to view the exports page.</span></span> <span data-ttu-id="dcc27-109">Пайдаланушының барлық рөлдерінде конфигурацияланған экспорттауды көруге рұқсаты бар.</span><span class="sxs-lookup"><span data-stu-id="dcc27-109">All user roles have access to view configured exports.</span></span> <span data-ttu-id="dcc27-110">Экспорттауды олардың атауы, қосылым атауы немесе қосылым түрі бойынша табу үшін пәрмен жолағындағы іздеу өрісін пайдаланыңыз.</span><span class="sxs-lookup"><span data-stu-id="dcc27-110">Use of the search field in the command bar to find exports by their name, connection name, or connection type.</span></span>

## <a name="set-up-a-new-export"></a><span data-ttu-id="dcc27-111">Жаңа экспорттауды орнату</span><span class="sxs-lookup"><span data-stu-id="dcc27-111">Set up a new export</span></span>

<span data-ttu-id="dcc27-112">Экспорттауды орнату немесе өңдеу үшін сізде қолжетімді қосылымдар болуы керек.</span><span class="sxs-lookup"><span data-stu-id="dcc27-112">To set up or edit an export, you need to have connections available to you.</span></span> <span data-ttu-id="dcc27-113">Қосылымдар сіздің [пайдаланушы рөліңізге](permissions.md) байланысты:</span><span class="sxs-lookup"><span data-stu-id="dcc27-113">Connections depend on your [user role](permissions.md):</span></span>
- <span data-ttu-id="dcc27-114">Әкімшілер барлық қосылымдарға қатынаса алады.</span><span class="sxs-lookup"><span data-stu-id="dcc27-114">Administrators have access to all connections.</span></span> <span data-ttu-id="dcc27-115">Сондай-ақ олар экспорттауды орнатқан кезде жаңа қосылымдар жасай алады.</span><span class="sxs-lookup"><span data-stu-id="dcc27-115">They can also create new connections when setting up an export.</span></span>
- <span data-ttu-id="dcc27-116">Салымшылар белгілі бір қосылымдарға қатынаса алады.</span><span class="sxs-lookup"><span data-stu-id="dcc27-116">Contributors can have access to specific connections.</span></span> <span data-ttu-id="dcc27-117">Олар қосылымдарды конфигурациялау және бөлісу үшін әкімшілерге тәуелді.</span><span class="sxs-lookup"><span data-stu-id="dcc27-117">They depend on administrators to configure and share connections.</span></span> <span data-ttu-id="dcc27-118">Қосымша ақпарат алу үшін [Салымшыларға экспорттау үшін қосылымды пайдалануға рұқсат беру](connections.md#allow-contributors-to-use-a-connection-for-exports) бөлімін қараңыз.</span><span class="sxs-lookup"><span data-stu-id="dcc27-118">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>
- <span data-ttu-id="dcc27-119">Көрушілер тек бұрыннан бар экспортты көре алады, бірақ оны жасай алмайды.</span><span class="sxs-lookup"><span data-stu-id="dcc27-119">Viewers can only view existing exports but not create them.</span></span>

1. <span data-ttu-id="dcc27-120">**Деректер** > **Экспорттау** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="dcc27-120">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="dcc27-121">Жаңа экспорттау мақсатты орнын жасау үшін **Экспорттау қосу** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="dcc27-121">Select **Add export** to create a new export destination.</span></span>

1. <span data-ttu-id="dcc27-122">**Экспортты орнату** тақтасында пайдаланылатын қосылымды таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="dcc27-122">In the **Set up export** pane, select which connection to use.</span></span> <span data-ttu-id="dcc27-123">[Қосылымдар](connections.md) әкімшілер арқылы басқарылады.</span><span class="sxs-lookup"><span data-stu-id="dcc27-123">[Connections](connections.md) are managed by administrators.</span></span> 

1. <span data-ttu-id="dcc27-124">Қажетті мәліметтерді енгізіңіз және экспорттауды жасау үшін **Сақтау** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="dcc27-124">Provide the required details and select **Save** to create the export.</span></span>

### <a name="edit-an-export"></a><span data-ttu-id="dcc27-125">Экспорттауды өңдеу</span><span class="sxs-lookup"><span data-stu-id="dcc27-125">Edit an export</span></span>

1. <span data-ttu-id="dcc27-126">Өңдеу қажет экспорттаудың мақсатты орнына арналған тік көп нүктені таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="dcc27-126">Select the vertical ellipsis for the export destination you want to edit.</span></span>

1. <span data-ttu-id="dcc27-127">Ашылмалы мәзірден **Өңдеу** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="dcc27-127">Select **Edit** from the drop-down menu.</span></span>

1. <span data-ttu-id="dcc27-128">Жаңарту керек мәндерді таңдаңыз және **Сақтау** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="dcc27-128">Change the values you want to update and select **Save**.</span></span>

## <a name="view-exports-and-export-details"></a><span data-ttu-id="dcc27-129">Экспорттауды және экспорттау туралы мәліметтерді көру</span><span class="sxs-lookup"><span data-stu-id="dcc27-129">View Exports and export details</span></span>

<span data-ttu-id="dcc27-130">Экспорттаудың мақсатты орындарын жасағаннан кейін олар **Деректер** > **Экспорттау** тармағында тізімделеді.</span><span class="sxs-lookup"><span data-stu-id="dcc27-130">After creating export destinations, they are listed on **Data** > **Exports**.</span></span> <span data-ttu-id="dcc27-131">Барлық пайдаланушылар қандай деректер бөлісілетінін және оның соңғы күйін көре алады.</span><span class="sxs-lookup"><span data-stu-id="dcc27-131">All users can see which data is shared and its latest status.</span></span>

1. <span data-ttu-id="dcc27-132">**Деректер** > **Экспорттау** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="dcc27-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="dcc27-133">Өңдеу рұқсаттары жоқ пайдаланушылар экспорттау туралы мәліметтерді көру үшін **Өңдеу** түймешігінің орнына **Көру** түймешігін таңдайды.</span><span class="sxs-lookup"><span data-stu-id="dcc27-133">Users without edit permissions select **View** instead of **Edit** see the export details.</span></span>

1. <span data-ttu-id="dcc27-134">Бұл бүйірлік тақта осы экспорттаудың орнатылуын көрсетеді.</span><span class="sxs-lookup"><span data-stu-id="dcc27-134">This side pane shows the set up of this export.</span></span> <span data-ttu-id="dcc27-135">Өңдеу рұқсаттарынсыз мәндерді өзгерту мүмкін емес.</span><span class="sxs-lookup"><span data-stu-id="dcc27-135">Without edit permissions, you can't change values.</span></span> <span data-ttu-id="dcc27-136">Экспорттау бетіне оралу үшін **Жабу** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="dcc27-136">Select **Close** to return to the exports page.</span></span>

## <a name="run-exports-on-demand"></a><span data-ttu-id="dcc27-137">Экспорттауды сұрау бойынша іске қосу</span><span class="sxs-lookup"><span data-stu-id="dcc27-137">Run exports on demand</span></span>

<span data-ttu-id="dcc27-138">Экспорттауды конфигурациялағаннан кейін, оның жұмыс қосылымды болғанша ол әр [жоспарланған жаңартумен](system.md#schedule-tab) іске қосылады.</span><span class="sxs-lookup"><span data-stu-id="dcc27-138">After configuring an export, it will run with every [scheduled refresh](system.md#schedule-tab) as long as it has a working connection.</span></span>

<span data-ttu-id="dcc27-139">Жоспарланған жаңартуды күтпестен деректерді экспорттау үшін **Деректер** > **Экспорттау** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="dcc27-139">To export data without waiting for a scheduled refresh, go to **Data** > **Exports**.</span></span> <span data-ttu-id="dcc27-140">Екі таңдауыңыз бар:</span><span class="sxs-lookup"><span data-stu-id="dcc27-140">You have two options:</span></span>

- <span data-ttu-id="dcc27-141">Барлық экспорттауларды іске қосу үшін пәрмен жолағында **Барлығын іске қосу** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="dcc27-141">To run all exports, select **Run all** in the command bar.</span></span> 
- <span data-ttu-id="dcc27-142">Бір рет экспорттауды іске қосу үшін тізім элементінен көп нүктені (...) таңдап, содан кейін **Іске қосу** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="dcc27-142">To run a single export, select the ellipsis (...) on a list item and then choose **Run**.</span></span>

## <a name="remove-an-export"></a><span data-ttu-id="dcc27-143">Экспорттауды алып тастау</span><span class="sxs-lookup"><span data-stu-id="dcc27-143">Remove an Export</span></span>

1. <span data-ttu-id="dcc27-144">**Деректер** > **Экспорттау** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="dcc27-144">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="dcc27-145">Алып тастау қажет экспорттау үшін тік көп нүктені таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="dcc27-145">Select the vertical ellipsis for the Export you want to remove.</span></span>

1. <span data-ttu-id="dcc27-146">Ашылмалы тізімнен **Алып тастау** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="dcc27-146">Select **Remove** from the dropdown menu.</span></span>

1. <span data-ttu-id="dcc27-147">Растау экранында **Жою** опциясын таңдау арқылы жоюды растаңыз.</span><span class="sxs-lookup"><span data-stu-id="dcc27-147">Confirm the removal by selecting **Remove** on the confirmation screen.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
