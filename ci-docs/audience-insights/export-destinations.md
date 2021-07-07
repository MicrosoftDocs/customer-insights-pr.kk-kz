---
title: Customer Insights бағдарламасынан деректерді экспорттау
description: Деректерді бөлісу үшін экспорттауы басқарыңыз.
ms.date: 06/14/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 28563e3a76535cb0c92bfcda4ef5037430d00cfa
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305485"
---
# <a name="exports-preview-overview"></a><span data-ttu-id="29b89-103">Экспорттауларға (алдын ала қарау нұсқасы) шолу</span><span class="sxs-lookup"><span data-stu-id="29b89-103">Exports (preview) overview</span></span>

<span data-ttu-id="29b89-104">**Экспорттаулар** беті барлық конфигурацияланған экспорттарды көрсетеді.</span><span class="sxs-lookup"><span data-stu-id="29b89-104">The **Exports** page shows you all configured exports.</span></span> <span data-ttu-id="29b89-105">Экспорттау белгілі бір деректерді әртүрлі бағдарламалармен бөліседі.</span><span class="sxs-lookup"><span data-stu-id="29b89-105">Exports share specific data with various applications.</span></span> <span data-ttu-id="29b89-106">Олар тұтынушы профильдерін немесе нысандарын, схемалар мен салыстыру мәліметтерін қамтуы мүмкін.</span><span class="sxs-lookup"><span data-stu-id="29b89-106">They can include customer profiles or entities, schemas, and mapping details.</span></span> <span data-ttu-id="29b89-107">Әрбір экспорттау [аутентификация мен кіруді басқару үшін әкімші орнатқан қосылымды](connections.md) қажет етеді.</span><span class="sxs-lookup"><span data-stu-id="29b89-107">Each export requires a [connection, set up by an administrator, to manage authentication and access](connections.md).</span></span>

<span data-ttu-id="29b89-108">Экспорттау бетін көру үшін **Деректер** > **Экспорттау** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="29b89-108">Go to **Data** > **Exports** to view the exports page.</span></span> <span data-ttu-id="29b89-109">Барлық пайдаланушы рөлдері конфигурацияланған экспорттауларды көре алады.</span><span class="sxs-lookup"><span data-stu-id="29b89-109">All user roles can view configured exports.</span></span> <span data-ttu-id="29b89-110">Пәрмен жолағындағы іздеу өрісін пайдалану арқылы экспорттауларды олардың атауы, қосылым атауы немесе қосылым түрі бойынша табыңыз.</span><span class="sxs-lookup"><span data-stu-id="29b89-110">Use the search field in the command bar to find exports by their name, connection name, or connection type.</span></span>

## <a name="set-up-a-new-export"></a><span data-ttu-id="29b89-111">Жаңа экспорттауды орнату</span><span class="sxs-lookup"><span data-stu-id="29b89-111">Set up a new export</span></span>

<span data-ttu-id="29b89-112">Экспорттауды орнату немесе өңдеу үшін сізде қолжетімді қосылымдар болуы керек.</span><span class="sxs-lookup"><span data-stu-id="29b89-112">To set up or edit an export, you need to have connections available to you.</span></span> <span data-ttu-id="29b89-113">Қосылымдар сіздің [пайдаланушы рөліңізге](permissions.md) байланысты:</span><span class="sxs-lookup"><span data-stu-id="29b89-113">Connections depend on your [user role](permissions.md):</span></span>
- <span data-ttu-id="29b89-114">Әкімшілер барлық қосылымдарға қатынаса алады.</span><span class="sxs-lookup"><span data-stu-id="29b89-114">Administrators have access to all connections.</span></span> <span data-ttu-id="29b89-115">Сондай-ақ олар экспорттауды орнатқан кезде жаңа қосылымдар жасай алады.</span><span class="sxs-lookup"><span data-stu-id="29b89-115">They can also create new connections when setting up an export.</span></span>
- <span data-ttu-id="29b89-116">Салымшылар белгілі бір қосылымдарға қатынаса алады.</span><span class="sxs-lookup"><span data-stu-id="29b89-116">Contributors can have access to specific connections.</span></span> <span data-ttu-id="29b89-117">Олар қосылымдарды конфигурациялау және бөлісу үшін әкімшілерге тәуелді.</span><span class="sxs-lookup"><span data-stu-id="29b89-117">They depend on administrators to configure and share connections.</span></span> <span data-ttu-id="29b89-118">Экспорттау тізімі салымшылардың экспорттауды өңдеп немесе тек **Сіздің рұқсаттарыңыз** бағанында көре алатындығын көрсетеді.</span><span class="sxs-lookup"><span data-stu-id="29b89-118">The exports list shows contributors whether they can edit or only view an export in the **Your permissions** column.</span></span> <span data-ttu-id="29b89-119">Қосымша ақпарат алу үшін [Салымшыларға экспорттау үшін қосылымды пайдалануға рұқсат беру](connections.md#allow-contributors-to-use-a-connection-for-exports) бөлімін қараңыз.</span><span class="sxs-lookup"><span data-stu-id="29b89-119">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>
- <span data-ttu-id="29b89-120">Көрушілер тек бұрыннан бар экспортты көре алады, бірақ оны жасай алмайды.</span><span class="sxs-lookup"><span data-stu-id="29b89-120">Viewers can only view existing exports but not create them.</span></span>

### <a name="define-a-new-export"></a><span data-ttu-id="29b89-121">Жаңа экспорттауды анықтау</span><span class="sxs-lookup"><span data-stu-id="29b89-121">Define a new export</span></span>

1. <span data-ttu-id="29b89-122">**Деректер** > **Экспорттау** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="29b89-122">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="29b89-123">Жаңа экспорттау жасау үшін **Экспорттау қосу** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="29b89-123">Select **Add export** to create a new export.</span></span>

1. <span data-ttu-id="29b89-124">**Экспортты орнату** тақтасында пайдаланылатын қосылымды таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="29b89-124">In the **Set up export** pane, select which connection to use.</span></span> <span data-ttu-id="29b89-125">[Қосылымдар](connections.md) әкімшілер арқылы басқарылады.</span><span class="sxs-lookup"><span data-stu-id="29b89-125">[Connections](connections.md) are managed by administrators.</span></span> 

1. <span data-ttu-id="29b89-126">Қажетті мәліметтерді енгізіңіз және экспорттауды жасау үшін **Сақтау** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="29b89-126">Provide the required details and select **Save** to create the export.</span></span>

### <a name="define-a-new-export-based-on-an-existing-export"></a><span data-ttu-id="29b89-127">Бұрыннан бар экспорттау негізінде жаңа экспорттауды анықтау</span><span class="sxs-lookup"><span data-stu-id="29b89-127">Define a new export based on an existing export</span></span>

1. <span data-ttu-id="29b89-128">**Деректер** > **Экспорттау** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="29b89-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="29b89-129">Экспорттаулар тізімінде көшірмесін жасау керек экспорттауды таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="29b89-129">In the list of exports, select the export you want to duplicate.</span></span>

1. <span data-ttu-id="29b89-130">Таңдалған экспорттаудың мәліметтері бар **Экспорттауды орнату** тақтасын ашу үшін пәрмен жолағынан **Көшірмесін жасау** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="29b89-130">Select **Create duplicate** in the command bar to open the **Set up export** pane with the details of the selected export.</span></span>

1. <span data-ttu-id="29b89-131">Экспорттауды қарап шығыңыз және бейімдеңіз және жаңа экспорттауды жасау үшін **Сақтау** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="29b89-131">Review and adapt the export and select **Save** to create a new export.</span></span>

### <a name="edit-an-export"></a><span data-ttu-id="29b89-132">Экспорттауды өңдеу</span><span class="sxs-lookup"><span data-stu-id="29b89-132">Edit an export</span></span>

1. <span data-ttu-id="29b89-133">**Деректер** > **Экспорттау** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="29b89-133">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="29b89-134">Экспорттаулар тізімінде өңдеу керек экспорттауды таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="29b89-134">In the list of exports, select the export you want to edit.</span></span>

1. <span data-ttu-id="29b89-135">Пәрмен жолағынан **Өңдеу** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="29b89-135">Select **Edit** in the command bar.</span></span>

1. <span data-ttu-id="29b89-136">Жаңарту керек мәндерді таңдаңыз және **Сақтау** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="29b89-136">Change the values you want to update and select **Save**.</span></span>

## <a name="view-exports-and-export-details"></a><span data-ttu-id="29b89-137">Экспорттауларды және экспорттау туралы мәліметтерді көру</span><span class="sxs-lookup"><span data-stu-id="29b89-137">View exports and export details</span></span>

<span data-ttu-id="29b89-138">Экспорттаудың мақсатты орындарын жасағаннан кейін олар **Деректер** > **Экспорттау** тармағында тізімделеді.</span><span class="sxs-lookup"><span data-stu-id="29b89-138">After creating export destinations, they're listed on **Data** > **Exports**.</span></span> <span data-ttu-id="29b89-139">Барлық пайдаланушылар қандай деректер бөлісілетінін және оның соңғы күйін көре алады.</span><span class="sxs-lookup"><span data-stu-id="29b89-139">All users can see which data is shared and its latest status.</span></span>

1. <span data-ttu-id="29b89-140">**Деректер** > **Экспорттау** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="29b89-140">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="29b89-141">Өңдеу рұқсаттары жоқ пайдаланушылар экспорттау мәліметтерін көру үшін **Өңдеу** түймешігінің орнына **Көру** түймешігін таңдайды.</span><span class="sxs-lookup"><span data-stu-id="29b89-141">Users without edit permissions select **View** instead of **Edit** to see the export details.</span></span>

1. <span data-ttu-id="29b89-142">Бүйірлік тақта экспорттаудың конфигурациясын көрсетеді.</span><span class="sxs-lookup"><span data-stu-id="29b89-142">The side pane shows the configuration of an export.</span></span> <span data-ttu-id="29b89-143">Өңдеу рұқсаттарынсыз мәндерді өзгерту мүмкін емес.</span><span class="sxs-lookup"><span data-stu-id="29b89-143">Without edit permissions, you can't change values.</span></span> <span data-ttu-id="29b89-144">Экспорттау бетіне оралу үшін **Жабу** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="29b89-144">Select **Close** to return to the exports page.</span></span>

## <a name="schedule-and-run-exports"></a><span data-ttu-id="29b89-145">Экспорттауды жоспарлау және іске қосу</span><span class="sxs-lookup"><span data-stu-id="29b89-145">Schedule and run exports</span></span>

<span data-ttu-id="29b89-146">Конфигурациялаған әрбір экспорттауда жаңарту кестесі бар.</span><span class="sxs-lookup"><span data-stu-id="29b89-146">Each export you configure has a refresh schedule.</span></span> <span data-ttu-id="29b89-147">Жаңарту кезінде жүйе экспорттауға қосу үшін жаңа немесе жаңартылған деректерді іздейді.</span><span class="sxs-lookup"><span data-stu-id="29b89-147">During a refresh, the system looks for new or updated data to include in an export.</span></span> <span data-ttu-id="29b89-148">Әдепкі бойынша, экспорттау әр [жоспарланған жүйені жаңарту](system.md#schedule-tab) бөлігі ретінде іске қосылады.</span><span class="sxs-lookup"><span data-stu-id="29b89-148">By default, exports are run as part of every [scheduled system refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="29b89-149">Экспорттауды қолмен іске қосу үшін жаңарту кестесін теңшеуге немесе оны өшіруге болады.</span><span class="sxs-lookup"><span data-stu-id="29b89-149">You can customize the refresh schedule or turn it off to run exports manually.</span></span>

<span data-ttu-id="29b89-150">Экспорттау кестесі сіздің ортаңыздың күйіне байланысты.</span><span class="sxs-lookup"><span data-stu-id="29b89-150">Export schedules depend on the state of your environment.</span></span> <span data-ttu-id="29b89-151">Егер жоспарланған экспорттау басталу керек кезде [тәуелділіктерде](system.md#refresh-policies) жаңартулар орындалып жатса, жүйе алдымен жаңартуларды аяқтайды, содан кейін экспорттауды іске қосады.</span><span class="sxs-lookup"><span data-stu-id="29b89-151">If there are updates in progress on [dependencies](system.md#refresh-policies) when a scheduled export should start, the system will first complete the updates and then run the export.</span></span> <span data-ttu-id="29b89-152">Экспорттаудың соңғы жаңартылған уақытын **Жаңартылған** бағанынан көре аласыз.</span><span class="sxs-lookup"><span data-stu-id="29b89-152">You can see when an export was last refreshed in column **Refreshed**.</span></span>

### <a name="schedule-exports"></a><span data-ttu-id="29b89-153">Экспорттауларды жоспарлау</span><span class="sxs-lookup"><span data-stu-id="29b89-153">Schedule exports</span></span>

<span data-ttu-id="29b89-154">Сіз жеке экспорттауға немесе бірнеше экспорттауға бір уақытта реттелетін жаңарту кестелерін анықтай аласыз.</span><span class="sxs-lookup"><span data-stu-id="29b89-154">You can define custom refresh schedules for individual exports or several exports at once.</span></span> <span data-ttu-id="29b89-155">Ағымдағы анықталған кесте экспорттау тізімінің **Кесте** бағанында тізімделген.</span><span class="sxs-lookup"><span data-stu-id="29b89-155">The currently defined schedule is listed in the **Schedule** column of the export list.</span></span> <span data-ttu-id="29b89-156">Кестені өзгертуге арналған рұқсат [экспорттауды өңдеу және анықтаумен](export-destinations.md#set-up-a-new-export) бірдей.</span><span class="sxs-lookup"><span data-stu-id="29b89-156">The permission to change the schedule is the same as for [editing and defining exports](export-destinations.md#set-up-a-new-export).</span></span> 

1. <span data-ttu-id="29b89-157">**Деректер** > **Экспорттау** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="29b89-157">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="29b89-158">Жоспарлау керек экспорттауды таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="29b89-158">Select the export you want to schedule.</span></span>

1. <span data-ttu-id="29b89-159">Пәрмен жолағынан **Жоспарлау** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="29b89-159">Select **Schedule** in the command bar.</span></span>

1. <span data-ttu-id="29b89-160">**Экспорттауды жоспарлау** тақтасында экспорттауды автоматты түрде іске қосу үшін **Жоспарлауды іске қосу** опциясын **Қосулы** күйіне орнатыңыз.</span><span class="sxs-lookup"><span data-stu-id="29b89-160">In the **Schedule export** pane, set the **Schedule run** to **On** to run the export automatically.</span></span> <span data-ttu-id="29b89-161">Оны қолмен жаңарту үшін **Өшірулі** күйіне орнатыңыз.</span><span class="sxs-lookup"><span data-stu-id="29b89-161">Set it to **Off** to refresh it manually.</span></span>

1. <span data-ttu-id="29b89-162">Автоматты түрде жаңартылған экспорттау үшін **Қайталану** мәнін таңдаңыз және ол үшін мәліметтерді көрсетіңіз.</span><span class="sxs-lookup"><span data-stu-id="29b89-162">For automatically refreshed exports, choose a **Recurrence** value and specify the details for it.</span></span> <span data-ttu-id="29b89-163">Анықталған уақыт қайталанудың барлық даналарына қолданылады.</span><span class="sxs-lookup"><span data-stu-id="29b89-163">The time defined applies to all instances of a recurrence.</span></span> <span data-ttu-id="29b89-164">Бұл экспорттау жаңартуды бастайтын уақыт.</span><span class="sxs-lookup"><span data-stu-id="29b89-164">It's the time when an export should start refreshing.</span></span>

1. <span data-ttu-id="29b89-165">**Сақтау** түймешігін таңдау арқылы өзгерістерді қолданыңыз және белсендіріңіз.</span><span class="sxs-lookup"><span data-stu-id="29b89-165">Apply and activate your changes by selecting **Save**.</span></span>

<span data-ttu-id="29b89-166">Бірнеше экспорттау үшін кестені өңдеген кезде, **Кестелерді сақтау немесе алдын ала анықтау** бөлімінен таңдау жасау керек болады:</span><span class="sxs-lookup"><span data-stu-id="29b89-166">When editing the schedule for several exports, you need to make a selection under **Keep or override schedules**:</span></span>
- <span data-ttu-id="29b89-167">**Жеке кестелерді сақтау**: таңдалған экспорттау үшін алдын ала анықталған кестені сақтаңыз және оларды тек өшіріңіз немесе қосыңыз.</span><span class="sxs-lookup"><span data-stu-id="29b89-167">**Keep individual schedules**: Persist the previously defined schedule for the selected exports and only disable or enable them.</span></span>
- <span data-ttu-id="29b89-168">**Барлық таңдалған экспорттаулар үшін жаңа кесте анықтау**: таңдалған экспорттаудың бұрыннан бар кестелерін алдын ала анықтаңыз,</span><span class="sxs-lookup"><span data-stu-id="29b89-168">**Define new schedule for all selected exports**: Override the existing schedules of the selected exports.</span></span>

### <a name="run-exports-on-demand"></a><span data-ttu-id="29b89-169">Экспорттауды сұрау бойынша іске қосу</span><span class="sxs-lookup"><span data-stu-id="29b89-169">Run exports on demand</span></span>

<span data-ttu-id="29b89-170">Жоспарланған жаңартуды күтпестен деректерді экспорттау үшін **Деректер** > **Экспорттау** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="29b89-170">To export data without waiting for a scheduled refresh, go to **Data** > **Exports**.</span></span>

- <span data-ttu-id="29b89-171">Барлық экспорттауларды іске қосу үшін пәрмен жолағында **Барлығын іске қосу** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="29b89-171">To run all exports, select **Run all** in the command bar.</span></span> <span data-ttu-id="29b89-172">Бұл әрекет тек белсенді кестесі бар экспорттауды іске қосады.</span><span class="sxs-lookup"><span data-stu-id="29b89-172">This action will only run exports that have an active schedule.</span></span>
- <span data-ttu-id="29b89-173">Бір рет экспорттауды іске қосу үшін оны тізімнен таңдаңыз және пәрмен жолағынан **Іске қосу** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="29b89-173">To run a single export, select it in the list and select **Run** in the command bar.</span></span> <span data-ttu-id="29b89-174">Осылайша сіз белсенді кестесі жоқ экспорттауды іске қосасыз.</span><span class="sxs-lookup"><span data-stu-id="29b89-174">That's how you run exports with no active schedule.</span></span> 

## <a name="remove-an-export"></a><span data-ttu-id="29b89-175">Экспорттауды алып тастау</span><span class="sxs-lookup"><span data-stu-id="29b89-175">Remove an Export</span></span>

1. <span data-ttu-id="29b89-176">**Деректер** > **Экспорттау** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="29b89-176">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="29b89-177">Жою керек экспорттауды таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="29b89-177">Select the export you want to remove.</span></span>

1. <span data-ttu-id="29b89-178">Пәрмен жолағынан **Жою** пәрменін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="29b89-178">Select **Remove** in the command bar.</span></span>

1. <span data-ttu-id="29b89-179">Растау экранында **Жою** опциясын таңдау арқылы жоюды растаңыз.</span><span class="sxs-lookup"><span data-stu-id="29b89-179">Confirm the removal by selecting **Remove** on the confirmation screen.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
