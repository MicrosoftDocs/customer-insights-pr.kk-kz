---
title: Деректерді біріктіруде нысандарды біріктіру
description: Тұтынушылардың бірыңғай профильдерін жасау үшін деректерді біріктіріңіз.
ms.date: 05/10/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 86ab3cefa70e5fab4bdb27cde363adee26efee4c
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305651"
---
# <a name="merge-entities"></a><span data-ttu-id="b6b6c-103">Нысандарды біріктіру</span><span class="sxs-lookup"><span data-stu-id="b6b6c-103">Merge entities</span></span>

<span data-ttu-id="b6b6c-104">Біріктіру кезеңі — деректерді біріктіру процесіндегі соңғы кезең.</span><span class="sxs-lookup"><span data-stu-id="b6b6c-104">The merge phase is the last phase in the data unification process.</span></span> <span data-ttu-id="b6b6c-105">Оның мақсаты — қайшылықты деректерді қайта салыстыру.</span><span class="sxs-lookup"><span data-stu-id="b6b6c-105">Its purpose is reconciling conflicting data.</span></span> <span data-ttu-id="b6b6c-106">Қайшылықты деректер мысалдарына екі деректер жиынынан табылатын, бірақ әрқайсысы өзгеше көрінетін тұтынушы аты ("Грант Маршалл" және "Грант Маршал") немесе пішімі әр түрлі телефон нөмірі (617-803-091X және 617803091X) болуы мүмкін.</span><span class="sxs-lookup"><span data-stu-id="b6b6c-106">Examples of conflicting data could include a customer name found in two of your datasets but that shows up a little differently in each ("Grant Marshall" versus "Grant Marshal"), or a phone number that differs in format (617-803-091X versus 617803091X).</span></span> <span data-ttu-id="b6b6c-107">Осы қайшылықты деректер нүктелерін біріктіру төлсипат-төлсипат негізінде орындалады.</span><span class="sxs-lookup"><span data-stu-id="b6b6c-107">Merging those conflicting data points is done on an attribute-by-attribute basis.</span></span>

:::image type="content" source="media/merge-fields-page.png" alt-text="Бірыңғай тұтынушы профилін анықтайтын біріктірілген өрістермен кестені көрсететін деректерді біріздендіру процесіндегі бетті біріктіру.":::

<span data-ttu-id="b6b6c-109">[Сәйкестендіру кезеңін](match-entities.md) аяқтаған соң, **Біріктіру** бетінен **Біріктіру** қатарын таңдау арқылы біріктіру кезеңін бастайсыз.</span><span class="sxs-lookup"><span data-stu-id="b6b6c-109">After completing the [match phase](match-entities.md), you start the merge phase by selecting the **Merge** tile on the **Unify** page.</span></span>

## <a name="review-system-recommendations"></a><span data-ttu-id="b6b6c-110">Жүйе ұсыныстарын қарап шығу</span><span class="sxs-lookup"><span data-stu-id="b6b6c-110">Review system recommendations</span></span>

<span data-ttu-id="b6b6c-111">**Деректер** > **Біріздендіру** > **Біріктіру** тармағында бірыңғай тұтынушы профиліңізде біріктіру үшін төлсипаттарды таңдайсыз және алып тастайсыз.</span><span class="sxs-lookup"><span data-stu-id="b6b6c-111">On **Data** > **Unify** > **Merge**, you choose and exclude attributes to merge within your unified customer profile entity.</span></span> <span data-ttu-id="b6b6c-112">Тұтынушы бірыңғай профилі деректерді біріздендіру процесінің нәтижесі болып табылады.</span><span class="sxs-lookup"><span data-stu-id="b6b6c-112">The unified customer profile is the result of the data unification process.</span></span> <span data-ttu-id="b6b6c-113">Жүйе кейбір төлсипаттарды автоматты түрде біріктіреді.</span><span class="sxs-lookup"><span data-stu-id="b6b6c-113">Some attributes are automatically merged by the system.</span></span>

<span data-ttu-id="b6b6c-114">Автоматты түрде біріктірілген төлсипаттардың біріне қосылған төлсипаттарды көру үшін, сол біріктірілген төлсипатты кестенің **Тұтынушы өрістері** қойыншасынан таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="b6b6c-114">To view the attributes that are included in one of your automatically merged attributes, select that merged attribute in the **Customer fields** tab of the table.</span></span> <span data-ttu-id="b6b6c-115">Сол біріктірілген төлсипаттан тұратын төлсипатта біріктірілген төлсипаттан бөлек екі жаңа жол көрсетіледі.</span><span class="sxs-lookup"><span data-stu-id="b6b6c-115">The attributes that compose that merged attribute display in two new rows beneath the merged attribute.</span></span>

## <a name="separate-rename-exclude-and-edit-merged-fields"></a><span data-ttu-id="b6b6c-116">Біріктірілген өрістерді бөлу, атауын өзгерту, шығару және өңдеу</span><span class="sxs-lookup"><span data-stu-id="b6b6c-116">Separate, rename, exclude, and edit merged fields</span></span>

<span data-ttu-id="b6b6c-117">Тұтынушының бірыңғай профилін құру үшін жүйенің біріктірілген төлсипаттарды өңдеу әдісін өзгерте аласыз.</span><span class="sxs-lookup"><span data-stu-id="b6b6c-117">You can change how the system processes merged attributes to generate the unified customer profile.</span></span> <span data-ttu-id="b6b6c-118">**Қосымша көрсету** түймешігін таңдаңыз және өзгерту керек нәрсені таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="b6b6c-118">Select **Show more** and choose what you want to change.</span></span>

:::image type="content" source="media/manage-merged-attributes.png" alt-text="Біріктірілген төлсипаттарды басқаруға арналған Көбірек көрсету ашылмалы мәзіріндегі опциялар.":::

<span data-ttu-id="b6b6c-120">Қосымша ақпарат алу үшін келесі бөлімдерді қараңыз.</span><span class="sxs-lookup"><span data-stu-id="b6b6c-120">For more information, see the following sections.</span></span>

## <a name="separate-merged-fields"></a><span data-ttu-id="b6b6c-121">Біріктірілген өрістерді бөлу</span><span class="sxs-lookup"><span data-stu-id="b6b6c-121">Separate merged fields</span></span>

<span data-ttu-id="b6b6c-122">Біріктірілген өрістерді бөлу үшін кестеден төлсипатты табыңыз.</span><span class="sxs-lookup"><span data-stu-id="b6b6c-122">To separate merged fields, find the attribute in the table.</span></span> <span data-ttu-id="b6b6c-123">Бөлінген өрістер тұтынушы бірыңғай профилінде жеке деректер нүктелері ретінде көрсетіледі.</span><span class="sxs-lookup"><span data-stu-id="b6b6c-123">Separated fields show as individual data points on the unified customer profile.</span></span> 

1. <span data-ttu-id="b6b6c-124">Біріктірілген өрісті таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="b6b6c-124">Select the merged field.</span></span>
  
1. <span data-ttu-id="b6b6c-125">**Қосымша көрсету** түймешігін таңдаңыз және **Өрістерді бөлу** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="b6b6c-125">Select **Show more** and choose **Separate fields**.</span></span>
 
1. <span data-ttu-id="b6b6c-126">Бөлуді растаңыз.</span><span class="sxs-lookup"><span data-stu-id="b6b6c-126">Confirm the separation.</span></span>

1. <span data-ttu-id="b6b6c-127">Өзгерістерді өңдеу үшін **Сақтау** және **Іске қосу** түймешіктерін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="b6b6c-127">Select **Save** and **Run** to process the changes.</span></span>

## <a name="rename-merged-fields"></a><span data-ttu-id="b6b6c-128">Біріктірілген өрістердің атын өзгерту</span><span class="sxs-lookup"><span data-stu-id="b6b6c-128">Rename merged fields</span></span>

<span data-ttu-id="b6b6c-129">Біріктірілген төлсипаттардың көрсетілетін атауын өзгертіңіз.</span><span class="sxs-lookup"><span data-stu-id="b6b6c-129">Change the display name of merged attributes.</span></span> <span data-ttu-id="b6b6c-130">Шығыс нысанның атауын өзгерту мүмкін емес.</span><span class="sxs-lookup"><span data-stu-id="b6b6c-130">You can't change the name of the output entity.</span></span>

1. <span data-ttu-id="b6b6c-131">Біріктірілген өрісті таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="b6b6c-131">Select the merged field.</span></span>
  
1. <span data-ttu-id="b6b6c-132">**Қосымша көрсету** түймешігін таңдаңыз және **Атауын өзгерту** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="b6b6c-132">Select **Show more** and choose **Rename**.</span></span>

1. <span data-ttu-id="b6b6c-133">Өзгертілген көрсетілетін атауды растаңыз.</span><span class="sxs-lookup"><span data-stu-id="b6b6c-133">Confirm the changed display name.</span></span> 

1. <span data-ttu-id="b6b6c-134">Өзгерістерді өңдеу үшін **Сақтау** және **Іске қосу** түймешіктерін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="b6b6c-134">Select **Save** and **Run** to process the changes.</span></span>

## <a name="exclude-merged-fields"></a><span data-ttu-id="b6b6c-135">Біріктірілген өрістерді шығару</span><span class="sxs-lookup"><span data-stu-id="b6b6c-135">Exclude merged fields</span></span>

<span data-ttu-id="b6b6c-136">Төлсипатты бірыңғай тұтынушы профилінен алып тастаңыз.</span><span class="sxs-lookup"><span data-stu-id="b6b6c-136">Exclude an attribute from the unified customer profile.</span></span> <span data-ttu-id="b6b6c-137">Егер өріс басқа процестерде, мысалы сегментте қолданылса, оны тұтынушы профилінен шығармас бұрын оны осы процестерден алып тастаңыз.</span><span class="sxs-lookup"><span data-stu-id="b6b6c-137">If the field is used in other processes, for example in a segment, remove it from these processes before excluding it from the customer profile.</span></span> 

1. <span data-ttu-id="b6b6c-138">Біріктірілген өрісті таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="b6b6c-138">Select the merged field.</span></span>
  
1. <span data-ttu-id="b6b6c-139">**Қосымша көрсету** түймешігін таңдаңыз және **Шығару** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="b6b6c-139">Select **Show more** and choose **Exclude**.</span></span>

1. <span data-ttu-id="b6b6c-140">Шығаруды растаңыз.</span><span class="sxs-lookup"><span data-stu-id="b6b6c-140">Confirm the exclusion.</span></span>

1. <span data-ttu-id="b6b6c-141">Өзгерістерді өңдеу үшін **Сақтау** және **Іске қосу** түймешіктерін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="b6b6c-141">Select **Save** and **Run** to process the changes.</span></span> 

<span data-ttu-id="b6b6c-142">**Біріктіру** бетінде барлық шығарылған өрістердің тізімін көру үшін **Шығарылған өрістер** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="b6b6c-142">On the **Merge** page, select **Excluded fields** to see the list of all excluded fields.</span></span> <span data-ttu-id="b6b6c-143">Бұл тақта шығарылған өрістерді қайта қосуға мүмкіндік береді.</span><span class="sxs-lookup"><span data-stu-id="b6b6c-143">This pane lets you add excluded fields back.</span></span>

## <a name="manually-combine-fields"></a><span data-ttu-id="b6b6c-144">Өрістерді қолмен біріктіру</span><span class="sxs-lookup"><span data-stu-id="b6b6c-144">Manually combine fields</span></span>

<span data-ttu-id="b6b6c-145">Біріктірілген төлсипатты қолмен көрсетіңіз.</span><span class="sxs-lookup"><span data-stu-id="b6b6c-145">Specify a merged attribute manually.</span></span> 

1. <span data-ttu-id="b6b6c-146">**Біріктіру** бетінде **Өрістерді біріктіру** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="b6b6c-146">On the **Merge** page, select **Combine fields**.</span></span>

1. <span data-ttu-id="b6b6c-147">**Атауы** және **Шығыс өріс атауы** өрістерін енгізіңіз.</span><span class="sxs-lookup"><span data-stu-id="b6b6c-147">Provide a **Name** and an **Output field name**.</span></span>

1. <span data-ttu-id="b6b6c-148">Қосу керек өрісті таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="b6b6c-148">Choose a field to add.</span></span> <span data-ttu-id="b6b6c-149">Қосымша өрістерді біріктіру үшін **Өрістер қосу** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="b6b6c-149">Select **Add fields** to combine more fields.</span></span>

1. <span data-ttu-id="b6b6c-150">Шығаруды растаңыз.</span><span class="sxs-lookup"><span data-stu-id="b6b6c-150">Confirm the exclusion.</span></span>

1. <span data-ttu-id="b6b6c-151">Өзгерістерді өңдеу үшін **Сақтау** және **Іске қосу** түймешіктерін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="b6b6c-151">Select **Save** and **Run** to process the changes.</span></span> 

## <a name="change-the-order-of-fields"></a><span data-ttu-id="b6b6c-152">Өрістердің ретін өзгерту</span><span class="sxs-lookup"><span data-stu-id="b6b6c-152">Change the order of fields</span></span>

<span data-ttu-id="b6b6c-153">Кейбір нысандарда басқаларға қарағанда көбірек мәліметтер бар.</span><span class="sxs-lookup"><span data-stu-id="b6b6c-153">Some entities contain more details than others.</span></span> <span data-ttu-id="b6b6c-154">Егер нысан өріс туралы соңғы деректерді қамтыса, мәндерді біріктіру кезінде оны басқа ұйымдарға қарағанда бірінші орынға қоюға болады.</span><span class="sxs-lookup"><span data-stu-id="b6b6c-154">If an entity includes the latest data about a field, you can prioritize it over other entities when merging values.</span></span>

1. <span data-ttu-id="b6b6c-155">Біріктірілген өрісті таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="b6b6c-155">Select the merged field.</span></span>
  
1. <span data-ttu-id="b6b6c-156">**Қосымша көрсету** түймешігін таңдаңыз және **Өңдеу** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="b6b6c-156">Select **Show more** and choose **Edit**.</span></span>

1. <span data-ttu-id="b6b6c-157">**Өрістерді біріктіру** тақтасында ретті орнату үшін **Жоғары/төмен жылжыту** түймешігін таңдаңыз немесе оларды қажетті орынға сүйреп апарыңыз.</span><span class="sxs-lookup"><span data-stu-id="b6b6c-157">In the **Combine fields** pane, select **Move up/down** to set the order or drag and drop them in the desired position.</span></span>

1. <span data-ttu-id="b6b6c-158">Өзгерісті растаңыз.</span><span class="sxs-lookup"><span data-stu-id="b6b6c-158">Confirm the change.</span></span>

1. <span data-ttu-id="b6b6c-159">Өзгерістерді өңдеу үшін **Сақтау** және **Іске қосу** түймешіктерін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="b6b6c-159">Select **Save** and **Run** to process the changes.</span></span>

## <a name="run-your-merge"></a><span data-ttu-id="b6b6c-160">Біріктіруді іске қосу</span><span class="sxs-lookup"><span data-stu-id="b6b6c-160">Run your merge</span></span>

<span data-ttu-id="b6b6c-161">Төлсипаттарды қолмен біріктіруге немесе жүйенің оларды біріктіруіне мүмкіндік беріп, үнемі біріктіруді іске қоса аласыз.</span><span class="sxs-lookup"><span data-stu-id="b6b6c-161">Whether you manually merge attributes or let the system merge them, you can always run your merge.</span></span> <span data-ttu-id="b6b6c-162">Процесті бастау үшін **Біріктіру** бетінен **Іске қосу** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="b6b6c-162">Select **Run** on the **Merge** page to start the process.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="b6b6c-163">![Деректерді біріктіру Сақтау және іске қосу](media/configure-data-merge-save-run.png "Деректерді біріктіру Сақтау және іске қосу")</span><span class="sxs-lookup"><span data-stu-id="b6b6c-163">![Data merge Save and Run](media/configure-data-merge-save-run.png "Data merge Save and Run")</span></span>

<span data-ttu-id="b6b6c-164">Егер нәтиженің тек бірыңғай тұтынушы нысанында ғана көрсетілуін қаласаңыз **Тек біріктіруді іске қосу** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="b6b6c-164">Choose **Run only Merge** if you only want to see the output reflected in the unified customer entity.</span></span> <span data-ttu-id="b6b6c-165">Кейінгі процестер [жаңарту кестесінде анықталған](system.md#schedule-tab) ретінде жаңартылатын болады.</span><span class="sxs-lookup"><span data-stu-id="b6b6c-165">Downstream processes will be refreshed as [defined in the refresh schedule](system.md#schedule-tab).</span></span>

<span data-ttu-id="b6b6c-166">Жүйені өзгерістермен жаңарту үшін **Біріктіруді және кейінгі процестерді іске қосу** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="b6b6c-166">Choose **Run Merge and downstream processes** to refresh the system with your changes.</span></span> <span data-ttu-id="b6b6c-167">Барлық процестер, соның ішінде толықтыру, сегменттер және көрсеткіштер автоматты түрде қайта іске қосылады.</span><span class="sxs-lookup"><span data-stu-id="b6b6c-167">All processes, including enrichment, segments, and measures will rerun automatically.</span></span> <span data-ttu-id="b6b6c-168">Барлық кейінгі процестер аяқталғаннан кейін тұтынушы профильдері сіз жасаған барлық өзгерістерді көрсетеді.</span><span class="sxs-lookup"><span data-stu-id="b6b6c-168">After all downstream processes have completed, the customer profiles reflect any changes you made.</span></span>

<span data-ttu-id="b6b6c-169">Қосымша өзгертулер енгізу және қадамды қайта орындау үшін аяқталмаған біріктіруді болдырмауға болады.</span><span class="sxs-lookup"><span data-stu-id="b6b6c-169">To make more changes and rerun the step, you can cancel an in-progress merge.</span></span> <span data-ttu-id="b6b6c-170">**Жаңартылуда ...** мәтінін таңдап, пайда болған бүйірлік тақтадағы **Тапсырмадан бас тарту** опциясын басыңыз.</span><span class="sxs-lookup"><span data-stu-id="b6b6c-170">Select **Refreshing ...** and select **Cancel job**  in the side pane that appears.</span></span>

> [!TIP]
> <span data-ttu-id="b6b6c-171">Тапсырмалар/процестерге арналған [күйдің алты түрі](system.md#status-types) бар.</span><span class="sxs-lookup"><span data-stu-id="b6b6c-171">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="b6b6c-172">Сонымен қатар көптеген процестер [басқа кезектегі процестерге тәуелді](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="b6b6c-172">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="b6b6c-173">Бүкіл тапсырманың барысы туралы мәліметтерді көру үшін процестің күйін таңдай аласыз.</span><span class="sxs-lookup"><span data-stu-id="b6b6c-173">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="b6b6c-174">Бір жұмыс тапсырмаларының бірі үшін **Мәліметтерді көру** параметрін таңдағаннан кейін, қосымша ақпаратты көруге болады: өңдеу уақыты, соңғы өңделген күні және тапсырмаға қатысты барлық қателер мен ескертулер.</span><span class="sxs-lookup"><span data-stu-id="b6b6c-174">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="b6b6c-175">Келесі қадам</span><span class="sxs-lookup"><span data-stu-id="b6b6c-175">Next Step</span></span>

<span data-ttu-id="b6b6c-176">Тұтынушылар туралы қосымша түсініктер алу үшін [әрекеттер](activities.md), [арттыру](enrichment-hub.md) немесе [қарым-қатынастар](relationships.md) параметрін теңшеңіз.</span><span class="sxs-lookup"><span data-stu-id="b6b6c-176">Configure [activities](activities.md), [enrichment](enrichment-hub.md), or [relationships](relationships.md) to gain more insights about your customers.</span></span>

<span data-ttu-id="b6b6c-177">Егер сіз әрекеттерді, толықтыруды немесе сегменттерді конфигурациялаған болсаңыз, олар тұтынушылардың соңғы деректерін пайдалану үшін автоматты түрде өңделеді.</span><span class="sxs-lookup"><span data-stu-id="b6b6c-177">If you already configured activities, enrichment, or segments, they'll be processed automatically to use the latest customer data.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
