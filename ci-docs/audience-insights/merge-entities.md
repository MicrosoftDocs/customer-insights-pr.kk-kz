---
title: Деректерді біріктіруде нысандарды біріктіру
description: Тұтынушылардың бірыңғай профильдерін жасау үшін деректерді біріктіріңіз.
ms.date: 04/16/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: 5d5ff4c6f091d1b50d0f6c8366bbe4f0e6428dac
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268509"
---
# <a name="merge-entities"></a><span data-ttu-id="025bd-103">Нысандарды біріктіру</span><span class="sxs-lookup"><span data-stu-id="025bd-103">Merge entities</span></span>

<span data-ttu-id="025bd-104">Біріктіру кезеңі — деректерді біріктіру процесіндегі соңғы кезең.</span><span class="sxs-lookup"><span data-stu-id="025bd-104">The merge phase is the last phase in the data unification process.</span></span> <span data-ttu-id="025bd-105">Оның мақсаты — қайшылықты деректерді қайта салыстыру.</span><span class="sxs-lookup"><span data-stu-id="025bd-105">Its purpose is reconciling conflicting data.</span></span> <span data-ttu-id="025bd-106">Қайшылықты деректер мысалдарына екі деректер жиынынан табылатын, бірақ әрқайсысы өзгеше көрінетін тұтынушы аты ("Грант Маршалл" және "Грант Маршал") немесе пішімі әр түрлі телефон нөмірі (617-803-091X және 617803091X) болуы мүмкін.</span><span class="sxs-lookup"><span data-stu-id="025bd-106">Examples of conflicting data could include a customer name found in two of your datasets but that shows up a little differently in each ("Grant Marshall" versus "Grant Marshal"), or a phone number that differs in format (617-803-091X versus 617803091X).</span></span> <span data-ttu-id="025bd-107">Осы қайшылықты деректер нүктелерін біріктіру төлсипат-төлсипат негізінде орындалады.</span><span class="sxs-lookup"><span data-stu-id="025bd-107">Merging those conflicting data points is done on an attribute-by-attribute basis.</span></span>

<span data-ttu-id="025bd-108">[Сәйкестендіру кезеңін](match-entities.md) аяқтаған соң, **Біріктіру** бетінен **Біріктіру** қатарын таңдау арқылы біріктіру кезеңін бастайсыз.</span><span class="sxs-lookup"><span data-stu-id="025bd-108">After completing the [match phase](match-entities.md), you start the merge phase by selecting the **Merge** tile on the **Unify** page.</span></span>

## <a name="review-system-recommendations"></a><span data-ttu-id="025bd-109">Жүйе ұсыныстарын қарап шығу</span><span class="sxs-lookup"><span data-stu-id="025bd-109">Review system recommendations</span></span>

<span data-ttu-id="025bd-110">**Біріктіру** бетінде бірыңғай тұтынушы профилінің нысанынан біріктіретін төлсипаттарды таңдап, оны шығарасыз (конфигурация процесінің нәтижесі).</span><span class="sxs-lookup"><span data-stu-id="025bd-110">On the **Merge** page, you choose and exclude attributes to merge within your unified customer profile entity (the result of the configuration process).</span></span> <span data-ttu-id="025bd-111">Жүйе кейбір төлсипаттарды автоматты түрде біріктіреді.</span><span class="sxs-lookup"><span data-stu-id="025bd-111">Some attributes are automatically merged by the system.</span></span>

### <a name="view-merged-attributes"></a><span data-ttu-id="025bd-112">Біріктірілген төлсипаттарды көру</span><span class="sxs-lookup"><span data-stu-id="025bd-112">View merged attributes</span></span>

<span data-ttu-id="025bd-113">Автоматты түрде біріктірілген төлсипаттардың біріне қосылған төлсипаттарды көру үшін біріктірілген төлсипатты таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="025bd-113">To view the attributes that are included in one of your automatically merged attributes, select that merged attribute.</span></span> <span data-ttu-id="025bd-114">Біріктірілген төлсипаттан тұратын екі төлсипатта біріктірілген төлсипаттан бөлек екі жаңа қатар көрсетіледі.</span><span class="sxs-lookup"><span data-stu-id="025bd-114">The two attributes that compose that merged attribute display in two new rows beneath the merged attribute.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="025bd-115">![Біріктірілген төлсипатты таңдау](media/configure-data-merge-profile-attributes.png "Біріктірілген төлсипатты таңдау")</span><span class="sxs-lookup"><span data-stu-id="025bd-115">![Select merged attribute](media/configure-data-merge-profile-attributes.png "Select merged attribute")</span></span>

### <a name="separate-merged-attributes"></a><span data-ttu-id="025bd-116">Біріктірілген төлсипаттарды бөлу</span><span class="sxs-lookup"><span data-stu-id="025bd-116">Separate merged attributes</span></span>

<span data-ttu-id="025bd-117">Автоматты түрде біріктірілген төлсипаттардың бірін бөлу немесе ажырату үшін **Профиль төлсипаттары** кестесінен төлсипатты табыңыз.</span><span class="sxs-lookup"><span data-stu-id="025bd-117">To separate or unmerge any of the automatically merged attributes, find the attribute in the **Profile attributes** table.</span></span>

1. <span data-ttu-id="025bd-118">Көп нүкте (...) түймешігін басыңыз.</span><span class="sxs-lookup"><span data-stu-id="025bd-118">Select the ellipsis (...) button.</span></span>
  
2. <span data-ttu-id="025bd-119">Ашылмалы тізімнен **Өрістерді бөлу** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="025bd-119">In the dropdown list, select **Separate fields**.</span></span>

### <a name="remove-merged-attributes"></a><span data-ttu-id="025bd-120">Біріктірілген төлсипаттарды жою</span><span class="sxs-lookup"><span data-stu-id="025bd-120">Remove merged attributes</span></span>

<span data-ttu-id="025bd-121">Соңғы тұтынушы профилінің нысанына төлсипатты шығару үшін оны **Профиль төлсипаттары** кестесінен табыңыз.</span><span class="sxs-lookup"><span data-stu-id="025bd-121">To exclude an attribute from the final customer profile entity, find it in the **Profile attributes** table.</span></span>

1. <span data-ttu-id="025bd-122">Көп нүкте (...) түймешігін басыңыз.</span><span class="sxs-lookup"><span data-stu-id="025bd-122">Select the ellipsis (...) button.</span></span>
  
2. <span data-ttu-id="025bd-123">Ашылмалы тізімнен **Біріктірмеу** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="025bd-123">In the dropdown list, select **Don't merge**.</span></span>

   <span data-ttu-id="025bd-124">Төлсипат **Тұтынушы жазбасынан жойылды** бөліміне көшірілді.</span><span class="sxs-lookup"><span data-stu-id="025bd-124">The attribute is moved to the **Removed from customer record** section.</span></span>

## <a name="manually-add-a-merged-attribute"></a><span data-ttu-id="025bd-125">Біріктірілген төлсипатты қолмен қосу</span><span class="sxs-lookup"><span data-stu-id="025bd-125">Manually add a merged attribute</span></span>

<span data-ttu-id="025bd-126">Біріктірілген төлсипатты қосу үшін **Біріктіру** бетіне өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="025bd-126">To add a merged attribute, go to the **Merge** page.</span></span>

1. <span data-ttu-id="025bd-127">**Біріктірілген төлсипатты қосу** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="025bd-127">Select **Add merged attribute**.</span></span>

2. <span data-ttu-id="025bd-128">Кейінірек **Біріктіру** бетінде анықтау үшін **Ат** беріңіз.</span><span class="sxs-lookup"><span data-stu-id="025bd-128">Provide a **Name** to identify it on the **Merge** page later.</span></span>

3. <span data-ttu-id="025bd-129">Қажет болса, бірыңғай тұтынушы профилінің нысанында пайда болатын **Көрсетілетін атын** беріңіз.</span><span class="sxs-lookup"><span data-stu-id="025bd-129">Optionally, provide a **Display name** to appear in the unified Customer Profile entity.</span></span>

4. <span data-ttu-id="025bd-130">Сәйкестендірілген нысандардан біріктіру қажет төлсипаттарды таңдау үшін **Көшірме төлсипаттарды таңдау** параметрін теңшеңіз.</span><span class="sxs-lookup"><span data-stu-id="025bd-130">Configure **Select duplicate attributes** to select the attributes that you want to merge from the matched entities.</span></span> <span data-ttu-id="025bd-131">Сонымен қатар, төлсипаттарды іздей аласыз.</span><span class="sxs-lookup"><span data-stu-id="025bd-131">You can also search for attributes.</span></span>

5. <span data-ttu-id="025bd-132">Бір төлсипатқа басқалардан жоғары басымдық беру үшін **Маңыздылығы бойынша саралау** параметрін орнатыңыз.</span><span class="sxs-lookup"><span data-stu-id="025bd-132">Set the **Rank by importance** to prioritize one attribute above the others.</span></span> <span data-ttu-id="025bd-133">Мысалы, *WebAccountCSV* нысанында *Толық аттары* төлсипаты туралы ең дұрыс деректер бар, *WebAccountCSV* параметрін таңдау арқылы *ContactCSV* бойынша осы нысанға басымдық бере аласыз.</span><span class="sxs-lookup"><span data-stu-id="025bd-133">For example, if the *WebAccountCSV* entity includes the most accurate data about the *Full Names* attribute, you could prioritize this entity over *ContactCSV* by selecting *WebAccountCSV*.</span></span> <span data-ttu-id="025bd-134">Нәтижесінде, *WebAccountCSV* параметрі бірінші басымдыққа өтеді, ал *Толық аты* төлсипатының мәндерін тартқан кезде *ContactCSV* параметрі екінші басымдыққа өтеді.</span><span class="sxs-lookup"><span data-stu-id="025bd-134">As a result, *WebAccountCSV* moves to first priority, while *ContactCSV* moves to second priority when pulling values for the *Full Name* attribute.</span></span>

## <a name="run-your-merge"></a><span data-ttu-id="025bd-135">Біріктіруді іске қосу</span><span class="sxs-lookup"><span data-stu-id="025bd-135">Run your merge</span></span>

<span data-ttu-id="025bd-136">Төлсипаттарды қолмен біріктіруге немесе жүйенің оларды біріктіруіне мүмкіндік беріп, үнемі біріктіруді іске қоса аласыз.</span><span class="sxs-lookup"><span data-stu-id="025bd-136">Whether you manually merge attributes or let the system merge them, you can always run your merge.</span></span> <span data-ttu-id="025bd-137">Процесті бастау үшін **Біріктіру** бетінен **Іске қосу** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="025bd-137">Select **Run** on the **Merge** page to start the process.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="025bd-138">![Деректерді біріктіру Сақтау және іске қосу](media/configure-data-merge-save-run.png "Деректерді біріктіру Сақтау және іске қосу")</span><span class="sxs-lookup"><span data-stu-id="025bd-138">![Data merge Save and Run](media/configure-data-merge-save-run.png "Data merge Save and Run")</span></span>

<span data-ttu-id="025bd-139">Қосымша өзгертулер енгізу және қадамды қайта бастау үшін аяқталмаған біріктіруді болдырмауға болады.</span><span class="sxs-lookup"><span data-stu-id="025bd-139">To make additional changes and rerun the step, you can cancel an in-progress merge.</span></span> <span data-ttu-id="025bd-140">**Жаңартылуда ...** мәтінін таңдап, пайда болған бүйірлік тақтадағы **Тапсырмадан бас тарту** опциясын басыңыз.</span><span class="sxs-lookup"><span data-stu-id="025bd-140">Select **Refreshing ...** and select **Cancel job**  in the side pane that appears.</span></span>

<span data-ttu-id="025bd-141">**Жаңартылуда ...** мәтіні **Сәтті орындалды** мәтініне өзгергеннен кейін, біріктіру аяқталады және деректердегі қайшылықтарды  көрсетілген саясатқа сәйкес шешеді.</span><span class="sxs-lookup"><span data-stu-id="025bd-141">After the **Refreshing ...** text changes to **Successful**, merge has completed and resolved contradictions in your data according to the policies you defined.</span></span> <span data-ttu-id="025bd-142">Біріктірілген және біріктірілмеген төлсипаттар бірыңғай профиль нысанына қосылады.</span><span class="sxs-lookup"><span data-stu-id="025bd-142">Merged and unmerged attributes are included in the unified profile entity.</span></span> <span data-ttu-id="025bd-143">Қосылмаған төлсипаттар бірыңғай профиль нысанына қосылмайды.</span><span class="sxs-lookup"><span data-stu-id="025bd-143">Excluded attributes aren't included in the unified profile entity.</span></span>

<span data-ttu-id="025bd-144">Егер бірінші рет біріктіру сәтті орындалмаса, барлық кейінгі процестер, соның ішінде толықтыру, сегменттеу және көрсеткіштер автоматты түрде қайта басталады.</span><span class="sxs-lookup"><span data-stu-id="025bd-144">If it wasn't the first time you ran a merge successfully, all downstream processes, including enrichment, segmentation, and measures will rerun automatically.</span></span> <span data-ttu-id="025bd-145">Барлық кейінгі процестер қайтадан басталғаннан кейін, тұтынушы профильдері сіз енгізген барлық өзгерістерді көрсетеді.</span><span class="sxs-lookup"><span data-stu-id="025bd-145">After all downstream processes have been rerun, the customer profiles reflect any changes you made.</span></span>

> [!TIP]
> <span data-ttu-id="025bd-146">Тапсырмалар/процестерге арналған [күйдің алты түрі](system.md#status-types) бар.</span><span class="sxs-lookup"><span data-stu-id="025bd-146">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="025bd-147">Сонымен қатар, көптеген процестер [басқа кезектегі процестерге тәуелді](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="025bd-147">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="025bd-148">Бүкіл тапсырманың барысы туралы мәліметтерді көру үшін процестің күйін таңдай аласыз.</span><span class="sxs-lookup"><span data-stu-id="025bd-148">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="025bd-149">Бір жұмыс тапсырмаларының бірі үшін **Мәліметтерді көру** параметрін таңдағаннан кейін, қосымша ақпаратты көруге болады: өңдеу уақыты, соңғы өңделген күні және тапсырмаға қатысты барлық қателер мен ескертулер.</span><span class="sxs-lookup"><span data-stu-id="025bd-149">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="025bd-150">Келесі қадам</span><span class="sxs-lookup"><span data-stu-id="025bd-150">Next Step</span></span>

<span data-ttu-id="025bd-151">Тұтынушылар туралы қосымша түсініктер алу үшін [әрекеттер](activities.md), [арттыру](enrichment-microsoft-graph.md) немесе [қарым-қатынастар](relationships.md) параметрін теңшеңіз.</span><span class="sxs-lookup"><span data-stu-id="025bd-151">Configure [activities](activities.md), [enrichment](enrichment-microsoft-graph.md), or [relationships](relationships.md) to gain more insights about your customers.</span></span>

<span data-ttu-id="025bd-152">Егер сіз әрекеттерді, арттыруды немесе қатынастарды әлдеқашан теңшеген болсаңыз немесе сегменттерді анықтасаңыз, олар соңғы тұтынушы деректерін пайдалану үшін автоматты түрде өңделеді.</span><span class="sxs-lookup"><span data-stu-id="025bd-152">If you already configured activities, enrichment, or relationships, or if you defined segments, they'll be processed automatically to use the latest customer data.</span></span>




[!INCLUDE[footer-include](../includes/footer-banner.md)]