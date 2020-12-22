---
title: Сегменттерді жасау және басқару
description: Әр түрлі төлсипаттарға байланысты топқа тұтынушылар сегменттерін жасаңыз.
ms.date: 10/15/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: jimsonc
manager: shellyha
ms.openlocfilehash: 6931110c2ae93cd2792d319aa5a34f0df3088552
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406258"
---
# <a name="create-and-manage-segments"></a><span data-ttu-id="e0ffe-103">Сегменттерді жасау және басқару</span><span class="sxs-lookup"><span data-stu-id="e0ffe-103">Create and manage segments</span></span>

<span data-ttu-id="e0ffe-104">Сегменттер тұтынушыларды демографиялық, транзакциялық немесе әрекеттік төлсипаттар бойынша топтастыруға мүмкіндік береді.</span><span class="sxs-lookup"><span data-stu-id="e0ffe-104">Segments let you group your customers based on demographic, transactional, or behavioral attributes.</span></span> <span data-ttu-id="e0ffe-105">Іскери мақсаттарға жету үшін мақсатты жарнама науқандарына, сатылым әрекеттеріне және тұтынушыларға қолдау көрсету әрекеттеріне сегменттерді пайдалана аласыз.</span><span class="sxs-lookup"><span data-stu-id="e0ffe-105">You can use segments to target promotional campaigns, sales activities, and customer support actions to achieve your business goals.</span></span>

<span data-ttu-id="e0ffe-106">Тұтынушы профилі мен оған байланысты нысандар айналасынан кешенді сүзгілерді анықтай аласыз.</span><span class="sxs-lookup"><span data-stu-id="e0ffe-106">You can define complex filters around the Customer Profile entity and its related entities.</span></span> <span data-ttu-id="e0ffe-107">Өңдеуден кейін әрбір сегмент экспорттауға және әрекет етуге болатын тұтынушы жазбалары жинағын жасайды.</span><span class="sxs-lookup"><span data-stu-id="e0ffe-107">Each segment, after processing, creates a set of customer records that you can export and take action on.</span></span> <span data-ttu-id="e0ffe-108">Кейбір [қызмет шектеулерін](service-limits.md) қолданыңыз.</span><span class="sxs-lookup"><span data-stu-id="e0ffe-108">Some [service limits](service-limits.md) apply.</span></span>

<span data-ttu-id="e0ffe-109">Басқаша көрсетілмесе, барлық сегменттер қайталанатын кестеде жаңартылған **Динамикалық сегменттер** болып табылады.</span><span class="sxs-lookup"><span data-stu-id="e0ffe-109">Unless stated otherwise, all segments are **Dynamic segments**, which are refreshed on a recurring schedule.</span></span>

<span data-ttu-id="e0ffe-110">Келесі мысалда сегменттеу мүмкіндігі көрсетілген.</span><span class="sxs-lookup"><span data-stu-id="e0ffe-110">The following example illustrates the segmentation capability.</span></span> <span data-ttu-id="e0ffe-111">Біз соңғы 90 күнде кемінде $500 тауарына тапсырыс берген *және* арта түскен тұтынушыға қызмет көрсету қоңырауына қатысқан тұтынушылар үшін сегмент анықтадық.</span><span class="sxs-lookup"><span data-stu-id="e0ffe-111">We've defined a segment for customers who ordered at least $500 of goods in the last 90 days *and* who were involved in a customer service call that got escalated.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="e0ffe-112">![Бірнеше топ](media/segmentation-group1-2.png "Бірнеше топ")</span><span class="sxs-lookup"><span data-stu-id="e0ffe-112">![Multiple groups](media/segmentation-group1-2.png "Multiple groups")</span></span>

## <a name="create-a-new-segment"></a><span data-ttu-id="e0ffe-113">Жаңа сегментті жасау</span><span class="sxs-lookup"><span data-stu-id="e0ffe-113">Create a new segment</span></span>

<span data-ttu-id="e0ffe-114">Сегменттер **Сегменттер** бетінде басқарылады.</span><span class="sxs-lookup"><span data-stu-id="e0ffe-114">Segments are managed on the **Segments** page.</span></span>

1. <span data-ttu-id="e0ffe-115">Аудитория түсініктерінде **Сегменттер** бетіне өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="e0ffe-115">In audience insights, go to the **Segments** page.</span></span>

2. <span data-ttu-id="e0ffe-116">**Жаңа** > **Бос сегмент** тармағын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="e0ffe-116">Select **New** > **Blank segment**.</span></span>

3. <span data-ttu-id="e0ffe-117">**Жаңа сегмент** тақтасынан сегмент түрін таңдап, **Ат** беріңіз.</span><span class="sxs-lookup"><span data-stu-id="e0ffe-117">In the **New segment** pane, choose a segment type and provide a **Name**.</span></span>

   <span data-ttu-id="e0ffe-118">Оған қоса, сегментті анықтауға көмектесетін сипаттама мен көрсетілетін атын беріңіз.</span><span class="sxs-lookup"><span data-stu-id="e0ffe-118">Optionally, provide a display name, and a description that helps identifying the segment.</span></span>

4. <span data-ttu-id="e0ffe-119">Топ анықталатын **Сегментті құрастыру құралы** бетіне өту үшін **Келесі** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="e0ffe-119">Select **Next** to get to the **Segment builder** page where you define a group.</span></span> <span data-ttu-id="e0ffe-120">Топ — тұтынушылар жинағы.</span><span class="sxs-lookup"><span data-stu-id="e0ffe-120">A group is a set of customers.</span></span>

5. <span data-ttu-id="e0ffe-121">Сегменттеу қажет төлсипаттан тұратын нысанды таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="e0ffe-121">Choose the entity that includes the attribute you want to segment by.</span></span>

6. <span data-ttu-id="e0ffe-122">Сегменттеу үшін төлсипат таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="e0ffe-122">Choose the attribute to segment by.</span></span> <span data-ttu-id="e0ffe-123">Бұл төлсипат төрт мәннің біреуіне ие болуы мүмкін: сандық, жолдық, күндік немесе логикалық.</span><span class="sxs-lookup"><span data-stu-id="e0ffe-123">This attribute can have one of four value types: numerical, string, date, or Boolean.</span></span>

7. <span data-ttu-id="e0ffe-124">Таңдалған төлсипат мәні мен операторды таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="e0ffe-124">Choose an operator and a value for the selected attribute.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e0ffe-125">![Теңшелетін топ сүзгісі](media/customer-group-numbers.png "Тұтынушылар тобының сүзгісі")</span><span class="sxs-lookup"><span data-stu-id="e0ffe-125">![Custom group filter](media/customer-group-numbers.png "Customer group filter")</span></span>

   |<span data-ttu-id="e0ffe-126">Нөмірі</span><span class="sxs-lookup"><span data-stu-id="e0ffe-126">Number</span></span> |<span data-ttu-id="e0ffe-127">Анықтама</span><span class="sxs-lookup"><span data-stu-id="e0ffe-127">Definition</span></span>  |
   |---------|---------|
   |<span data-ttu-id="e0ffe-128">1</span><span class="sxs-lookup"><span data-stu-id="e0ffe-128">1</span></span>     |<span data-ttu-id="e0ffe-129">Entity</span><span class="sxs-lookup"><span data-stu-id="e0ffe-129">Entity</span></span>          |
   |<span data-ttu-id="e0ffe-130">2</span><span class="sxs-lookup"><span data-stu-id="e0ffe-130">2</span></span>     |<span data-ttu-id="e0ffe-131">Төлсипат</span><span class="sxs-lookup"><span data-stu-id="e0ffe-131">Attribute</span></span>          |
   |<span data-ttu-id="e0ffe-132">3</span><span class="sxs-lookup"><span data-stu-id="e0ffe-132">3</span></span>    |<span data-ttu-id="e0ffe-133">Амалдағыш</span><span class="sxs-lookup"><span data-stu-id="e0ffe-133">Operator</span></span>         |
   |<span data-ttu-id="e0ffe-134">4</span><span class="sxs-lookup"><span data-stu-id="e0ffe-134">4</span></span>    |<span data-ttu-id="e0ffe-135">Мәні</span><span class="sxs-lookup"><span data-stu-id="e0ffe-135">Value</span></span>         |

8. <span data-ttu-id="e0ffe-136">Егер нысан бірыңғай тұтынушы нысанына [қарым-қатынастар](relationships.md) арқылы қосылса, жарамды сегмент құру үшін қарым-қатынас жолын анықтау керек.</span><span class="sxs-lookup"><span data-stu-id="e0ffe-136">If the entity is connected to the unified customer entity through [relationships](relationships.md), you need to define the relationship path to create a valid segment.</span></span> <span data-ttu-id="e0ffe-137">Ашылмалы мәзірден **Customer: CustomerInsights** нысанын таңдағанға дейін қарым-қатынас жолынан нысандарды қосыңыз.</span><span class="sxs-lookup"><span data-stu-id="e0ffe-137">Add the entities from the relationship path until you can select the **Customer:CustomerInsights** entity from the dropdown.</span></span> <span data-ttu-id="e0ffe-138">Содан кейін әр шарт үшін **Барлық жазбалар** таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="e0ffe-138">Then, choose **All records** for each condition.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e0ffe-139">![Сегмент құру кезіндегі қарым-қатынас жолы](media/segments-multiple-relationships.png "Сегмент құру кезіндегі қарым-қатынас жолы")</span><span class="sxs-lookup"><span data-stu-id="e0ffe-139">![Relationship path during segment creation](media/segments-multiple-relationships.png "Relationship path during segment creation")</span></span>

9. <span data-ttu-id="e0ffe-140">Сегментті сақтау үшін **Сақтау** пәрменін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="e0ffe-140">Select **Save** to save your segment.</span></span> <span data-ttu-id="e0ffe-141">Барлық талаптар тексерілсе, сегментіңіз сақталады және өңделеді.</span><span class="sxs-lookup"><span data-stu-id="e0ffe-141">Your segment will be saved and processed if all requirements are validated.</span></span> <span data-ttu-id="e0ffe-142">Болмаса, ол жоба ретінде сақталады.</span><span class="sxs-lookup"><span data-stu-id="e0ffe-142">Otherwise, it will be saved as a draft.</span></span>

10. <span data-ttu-id="e0ffe-143">**Сегменттер** бетіне кері өту үшін **Сегменттерге оралу** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="e0ffe-143">Select **Back to segments** to go back to the **Segments** page.</span></span>

## <a name="manage-existing-segments"></a><span data-ttu-id="e0ffe-144">Бұрыннан бар сегменттерді басқару</span><span class="sxs-lookup"><span data-stu-id="e0ffe-144">Manage existing segments</span></span>

<span data-ttu-id="e0ffe-145">**Сегменттер** бетінен барлық сақталған сегменттерді көруге және оларды басқаруға болады.</span><span class="sxs-lookup"><span data-stu-id="e0ffe-145">On the **Segments** page, you can view all your saved segments and manage them.</span></span>

<span data-ttu-id="e0ffe-146">Әрбір сегмент ол туралы қосымша ақпараттан тұратын қатар бойынша көрсетіледі.</span><span class="sxs-lookup"><span data-stu-id="e0ffe-146">Each segment is represented by a row that includes additional information about the segment.</span></span>

<span data-ttu-id="e0ffe-147">Баған тақырыбын таңдау арқылы бағандағы сегменттерді сұрыптауға болады.</span><span class="sxs-lookup"><span data-stu-id="e0ffe-147">You can sort the segments in a column by selecting the column heading.</span></span>

<span data-ttu-id="e0ffe-148">Сегменттерді сүзгілеу үшін жоғарғы оң жақ бұрыштағы **Іздеу** өрісін пайдаланыңыз.</span><span class="sxs-lookup"><span data-stu-id="e0ffe-148">Use the **Search** box in the top-right corner to filter the segments.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="e0ffe-149">![Бұрыннан бар сегментті басқаруға арналған опциялар](media/segments-selected-segment.png "Бұрыннан бар сегментті басқаруға арналған опциялар")</span><span class="sxs-lookup"><span data-stu-id="e0ffe-149">![Options to manage an existing segment](media/segments-selected-segment.png "Options to manage an existing segment")</span></span>

<span data-ttu-id="e0ffe-150">Сегментті таңдаған кезде келесі әрекет қолжетімді:</span><span class="sxs-lookup"><span data-stu-id="e0ffe-150">The following action are available when you select a segment:</span></span>

- <span data-ttu-id="e0ffe-151">Сегмент мәліметтерін, оның ішінде элементтер санының трендін, сегмент элементтерін алдын ала қарауын **қараңыз**.</span><span class="sxs-lookup"><span data-stu-id="e0ffe-151">**View** the segment details, including member count trend a preview of segment members.</span></span>
- <span data-ttu-id="e0ffe-152">Сипаттарын өзгерту үшін сегментті **өңдеңіз**.</span><span class="sxs-lookup"><span data-stu-id="e0ffe-152">**Edit** the segment to change its properties.</span></span>
- <span data-ttu-id="e0ffe-153">Ең соңғы деректерді қосу үшін сегментті **жаңартыңыз**.</span><span class="sxs-lookup"><span data-stu-id="e0ffe-153">**Refresh** the segment to include the latest data.</span></span>
- <span data-ttu-id="e0ffe-154">Сегментті **белсендіріңіз** немесе **өшіріңіз**.</span><span class="sxs-lookup"><span data-stu-id="e0ffe-154">**Activate** or **Deactivate** the segment.</span></span> <span data-ttu-id="e0ffe-155">Сегменттер екі мүмкін күйге ие - белсенді немесе белсенді емес.</span><span class="sxs-lookup"><span data-stu-id="e0ffe-155">Segments have two possible states - active or inactive.</span></span> <span data-ttu-id="e0ffe-156">Бұл күйлер сегментті редакциялау кезінде ыңғайлы.</span><span class="sxs-lookup"><span data-stu-id="e0ffe-156">These states come in handy when editing a segment.</span></span> <span data-ttu-id="e0ffe-157">Белсенді емес сегменттер үшін сегменттің анықтамасы бар, бірақ оған әлі тұтынушылар кірмейді.</span><span class="sxs-lookup"><span data-stu-id="e0ffe-157">For inactive segments, the segment definition exists but it doesn't contain any customers yet.</span></span> <span data-ttu-id="e0ffe-158">Сегментті белсендірген кезде оның күйі «белсенді емес» күйден «белсенді» күйге ауысады және сегменттің анықтамасына сәйкес келетін тұтынушыларды іздей бастайды.</span><span class="sxs-lookup"><span data-stu-id="e0ffe-158">When you activate a segment, its state changes from 'inactive' to 'active" and it starts looking for customers that match the segment definition.</span></span> <span data-ttu-id="e0ffe-159">Егер [жоспарланған жаңарту](system.md#schedule-tab) конфигурацияланған болса, белсенді емес сегменттерде жаңартуға тіпті әрекет жасалмағандығын көрсететін **Өткізілген** ретінде көрсетілген **Күй** параметрі болады.</span><span class="sxs-lookup"><span data-stu-id="e0ffe-159">If a [scheduled refresh](system.md#schedule-tab) is configured, inactive segments have the **Status** listed as **Skipped**, indicating that a refresh wasn't even attempted.</span></span> <span data-ttu-id="e0ffe-160">Белсенді емес сегмент белсендірілгенде, ол жаңарады және жоспарланған жаңартуларға қосылады.</span><span class="sxs-lookup"><span data-stu-id="e0ffe-160">When an inactive segment is activated, it will refresh and will be included in scheduled refreshes.</span></span>
  <span data-ttu-id="e0ffe-161">Болмаса, белгілі бір сегментті белсендіру мен ажырату үшін болашақ күн мен уақытты көрсету үшін **Белсендіру/ажырату** ашылмалы тізімінде **Кейінірек жоспарлау** функционалдығын пайдалана аласыз.</span><span class="sxs-lookup"><span data-stu-id="e0ffe-161">Alternatively, you can use the **Schedule later** functionality in the **Activate/Deactivate** dropdown to specify a future date and time for activation and deactivation of a particular segment.</span></span>
- <span data-ttu-id="e0ffe-162">Сегменттің **атын өзгертіңіз**.</span><span class="sxs-lookup"><span data-stu-id="e0ffe-162">**Rename** the segment.</span></span>
- <span data-ttu-id="e0ffe-163">Мүшелер тізімін .CSV файлы ретінде **жүктеп алыңыз**.</span><span class="sxs-lookup"><span data-stu-id="e0ffe-163">**Download** the list of members as a .CSV file.</span></span>
- <span data-ttu-id="e0ffe-164">**Қосу** опциясы сегменттегі тұтынушы идентификаторларының тізімін басқа бағдарламада өңдеуге жібереді.</span><span class="sxs-lookup"><span data-stu-id="e0ffe-164">**Add to** option sends the list of customer IDs in the segment for processing in another application.</span></span>
- <span data-ttu-id="e0ffe-165">Сегментті **жойыңыз**.</span><span class="sxs-lookup"><span data-stu-id="e0ffe-165">**Delete** the segment.</span></span>

## <a name="refresh-segments"></a><span data-ttu-id="e0ffe-166">Сегменттерді жаңарту</span><span class="sxs-lookup"><span data-stu-id="e0ffe-166">Refresh segments</span></span>

<span data-ttu-id="e0ffe-167">**Сегменттер** бетінен **Барлығын жаңарту** параметрін таңдау арқылы барлық сегменттерді жаңартуға немесе оларды таңдап, опциялардан **Жаңарту** параметрін таңдаған кезде бір не бірнеше сегментті жаңартуға болады.</span><span class="sxs-lookup"><span data-stu-id="e0ffe-167">You can refresh all segments at once by selecting **Refresh all** on the **Segments** page or you can refresh one or multiple segments when you select them and choose **Refresh** in from the options.</span></span> <span data-ttu-id="e0ffe-168">Сонымен қатар,**Әкімші** > **Жүйе** > **Жоспарлау** тармағындағы қайталанатын жаңартуды конфигурациялауға болады.</span><span class="sxs-lookup"><span data-stu-id="e0ffe-168">Alternatively, you can configure a recurring refresh on **Admin** > **System** > **Schedule**.</span></span>

> [!TIP]
> <span data-ttu-id="e0ffe-169">Тапсырмалар/процестерге арналған [күйдің алты түрі](system.md#status-types) бар.</span><span class="sxs-lookup"><span data-stu-id="e0ffe-169">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="e0ffe-170">Сонымен қатар, көптеген процестер [басқа кезектегі процестерге тәуелді](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="e0ffe-170">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="e0ffe-171">Бүкіл тапсырманың барысы туралы мәліметтерді көру үшін процестің күйін таңдай аласыз.</span><span class="sxs-lookup"><span data-stu-id="e0ffe-171">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="e0ffe-172">Бір жұмыс тапсырмаларының бірі үшін **Мәліметтерді көру** параметрін таңдағаннан кейін, қосымша ақпаратты көруге болады: өңдеу уақыты, соңғы өңделген күні және тапсырмаға қатысты барлық қателер мен ескертулер.</span><span class="sxs-lookup"><span data-stu-id="e0ffe-172">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="download-and-export-segments"></a><span data-ttu-id="e0ffe-173">Сегменттерді жүктеу және экспорттау</span><span class="sxs-lookup"><span data-stu-id="e0ffe-173">Download and export segments</span></span>

<span data-ttu-id="e0ffe-174">Өз сегменттеріңізді CSV файлына жүктей аласыз немесе оларды Dynamics 365 Sales бағдарламасына экспорттай аласыз.</span><span class="sxs-lookup"><span data-stu-id="e0ffe-174">You can download your segments to a CSV file or export them to Dynamics 365 Sales.</span></span>

### <a name="download-segments-to-a-csv-file"></a><span data-ttu-id="e0ffe-175">Сегменттерді CSV файлына жүктеу</span><span class="sxs-lookup"><span data-stu-id="e0ffe-175">Download segments to a CSV file</span></span>

1. <span data-ttu-id="e0ffe-176">Аудитория түсініктерінде **Сегменттер** бетіне өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="e0ffe-176">In audience insights, go to the **Segments** page.</span></span>

2. <span data-ttu-id="e0ffe-177">Белгілі бір сегмент тақтасында көп нүктені таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="e0ffe-177">Select the ellipsis in a specific segment's tile.</span></span>

3. <span data-ttu-id="e0ffe-178">Әрекеттер ашылмалы тізімінен **CSV ретінде жүктеп алу** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="e0ffe-178">Select **Download as CSV** from the actions drop-down list.</span></span>

### <a name="export-segments-to-dynamics-365-sales"></a><span data-ttu-id="e0ffe-179">Сегменттерді Dynamics 365 Sales бағдарламасына экспорттау</span><span class="sxs-lookup"><span data-stu-id="e0ffe-179">Export segments to Dynamics 365 Sales</span></span>

<span data-ttu-id="e0ffe-180">Dynamics 365 Sales бағдарламасына сегменттерді экспорттамас бұрын, әкімші Dynamics 365 Sales үшін [экспорттау межелі орнын құруы](export-destinations.md) қажет.</span><span class="sxs-lookup"><span data-stu-id="e0ffe-180">Before exporting segments to Dynamics 365 Sales, an admin needs to [create the export destination](export-destinations.md) for Dynamics 365 Sales.</span></span>

1. <span data-ttu-id="e0ffe-181">Аудитория түсініктерінде **Сегменттер** бетіне өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="e0ffe-181">In audience insights, go to the **Segments** page.</span></span>

2. <span data-ttu-id="e0ffe-182">Белгілі бір сегмент тақтасында көп нүктені таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="e0ffe-182">Select the ellipsis in a specific segment's tile.</span></span>

3. <span data-ttu-id="e0ffe-183">Әрекеттердің ашылмалы тізімінен **Тізімге қосу** опциясын таңдап, деректерді жіберу керек экспорттау межелі орнын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="e0ffe-183">Select **Add to** from the actions drop-down list and select the export destination you want to send the data to.</span></span>

## <a name="draft-mode-for-segments"></a><span data-ttu-id="e0ffe-184">Сегменттердің жоба режимі</span><span class="sxs-lookup"><span data-stu-id="e0ffe-184">Draft mode for segments</span></span>

<span data-ttu-id="e0ffe-185">Барлық сегментті өңдеу талаптары сақталса, сегментті жоба ретінде сақтауға және оған **Сегменттер** тақтасынан қатынасуға болады.</span><span class="sxs-lookup"><span data-stu-id="e0ffe-185">If not all requirements to process a segment are met, you can save the segment as a draft and access it from the **Segments** page.</span></span>

<span data-ttu-id="e0ffe-186">Ол белсенді емес сегмент ретінде сақталады және оны жарамды болғанға дейін қосу мүмкін емес.</span><span class="sxs-lookup"><span data-stu-id="e0ffe-186">It will be saved as an inactive segment, and can't be activated it until it's valid.</span></span>

## <a name="add-more-conditions-to-a-group"></a><span data-ttu-id="e0ffe-187">Топқа қосымша шарттар қосу</span><span class="sxs-lookup"><span data-stu-id="e0ffe-187">Add more conditions to a group</span></span>

<span data-ttu-id="e0ffe-188">Топқа қосымша шарттар қосу үшін екі логикалық операторды пайдалана аласыз:</span><span class="sxs-lookup"><span data-stu-id="e0ffe-188">To add more conditions to a group, you can use two logical operators:</span></span>

- <span data-ttu-id="e0ffe-189">**ЖӘНЕ** операторы: екі шарт та сегменттеу процесінің бөлігі ретінде сақталуы қажет.</span><span class="sxs-lookup"><span data-stu-id="e0ffe-189">**AND** operator: Both conditions must be met as part of the segmentation process.</span></span> <span data-ttu-id="e0ffe-190">Әр түрлі нысандар бойынша шарттарды анықтаған кезде осы опция өте пайдалы болады.</span><span class="sxs-lookup"><span data-stu-id="e0ffe-190">This option is most useful when you define conditions across different entities.</span></span>

- <span data-ttu-id="e0ffe-191">**НЕМЕСЕ** операторы: шарттардың бірі сегменттеу процесінің бөлігі болуы керек.</span><span class="sxs-lookup"><span data-stu-id="e0ffe-191">**OR** operator: Either one of the conditions needs to be met as part of the segmentation process.</span></span> <span data-ttu-id="e0ffe-192">Бір нысан үшін бірнеше шартты анықтаған кезде осы опция өте пайдалы болады.</span><span class="sxs-lookup"><span data-stu-id="e0ffe-192">This option is most useful when you define multiple conditions for the same entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e0ffe-193">![Шарты орындалуы керек НЕМЕСЕ операторы](media/segmentation-either-condition.png "Шарты орындалуы керек НЕМЕСЕ операторы")</span><span class="sxs-lookup"><span data-stu-id="e0ffe-193">![OR operator where either condition needs to be met](media/segmentation-either-condition.png "OR operator where either condition needs to be met")</span></span>

<span data-ttu-id="e0ffe-194">Дәл қазір **ЖӘНЕ** операторының астына **НЕМЕСЕ** операторы енгізілуі мүмкін, бірақ басқа жолы жоқ.</span><span class="sxs-lookup"><span data-stu-id="e0ffe-194">It's currently possible to nest an **OR** operator under an **AND** operator, but not the other way around.</span></span>

## <a name="combine-multiple-groups"></a><span data-ttu-id="e0ffe-195">Бірнеше топты біріктіру</span><span class="sxs-lookup"><span data-stu-id="e0ffe-195">Combine multiple groups</span></span>

<span data-ttu-id="e0ffe-196">Әр топ тұтынушылардың белгілі бір жиынтығын шығарады.</span><span class="sxs-lookup"><span data-stu-id="e0ffe-196">Each group produces a specific set of customers.</span></span> <span data-ttu-id="e0ffe-197">Бизнес істерге қажетті тұтынушыларды қосу үшін осы топтарды біріктіруге болады.</span><span class="sxs-lookup"><span data-stu-id="e0ffe-197">You can combine these groups to include the customers required for your business case.</span></span>

1. <span data-ttu-id="e0ffe-198">Аудитория түсініктерінде **Сегменттер** бетіне өтіп, сегментті таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="e0ffe-198">In audience insights, go to the **Segments** page and select a segment.</span></span>

2. <span data-ttu-id="e0ffe-199">**Топ қосу** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="e0ffe-199">Select **Add Group**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e0ffe-200">![Тұтынушылар тобын қосу тобы](media/customer-group-add-group.png "Тұтынушылар тобын қосу тобы")</span><span class="sxs-lookup"><span data-stu-id="e0ffe-200">![Customer group add group](media/customer-group-add-group.png "Customer group add group")</span></span>

3. <span data-ttu-id="e0ffe-201">Келесі орнатылған операторлардың біреуін таңдаңыз: **Бірлестік**, **Қиылысу** немесе **Басқа**.</span><span class="sxs-lookup"><span data-stu-id="e0ffe-201">Select one of the following set operators: **Union**, **Intersect**, or **Except**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e0ffe-202">![Тұтынушылар тобын қосу бірлестігі](media/customer-group-union.png "Тұтынушылар тобын қосу бірлестігі")</span><span class="sxs-lookup"><span data-stu-id="e0ffe-202">![Customer group add union](media/customer-group-union.png "Customer group add union")</span></span>

   <span data-ttu-id="e0ffe-203">Жаңа топты анықтау үшін орнатылған операторды таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="e0ffe-203">Select a set operator to define a new group.</span></span> <span data-ttu-id="e0ffe-204">Сақталатын деректерді анықтау үшін әртүрлі топтарды сақтаңыз:</span><span class="sxs-lookup"><span data-stu-id="e0ffe-204">Save different groups to determine what data gets retained:</span></span>

   - <span data-ttu-id="e0ffe-205">**Бірлестік** екі топты біріктіреді.</span><span class="sxs-lookup"><span data-stu-id="e0ffe-205">**Union** unites the two groups.</span></span>

   - <span data-ttu-id="e0ffe-206">**Қиылысу** екі топты қабаттастырады.</span><span class="sxs-lookup"><span data-stu-id="e0ffe-206">**Intersect** overlaps the two groups.</span></span> <span data-ttu-id="e0ffe-207">Екі топқа да *ортақ болып табылатын* деректер бірыңғай топта сақталады.</span><span class="sxs-lookup"><span data-stu-id="e0ffe-207">Only data that *is common* to both groups is retained in the unified group.</span></span>

   - <span data-ttu-id="e0ffe-208">**Қоспағанда** екі топты біріктіреді.</span><span class="sxs-lookup"><span data-stu-id="e0ffe-208">**Except** combines the two groups.</span></span> <span data-ttu-id="e0ffe-209">B тобындағы деректер үшін *ортақ болып табылмайтын* A тобындағы деректер ғана сақталады.</span><span class="sxs-lookup"><span data-stu-id="e0ffe-209">Only data in group A that *is not common* to data in group B is retained.</span></span>

## <a name="view-processing-history-and-segment-members"></a><span data-ttu-id="e0ffe-210">Өңдеу журналы мен сегмент мүшелерін көру</span><span class="sxs-lookup"><span data-stu-id="e0ffe-210">View processing history and segment members</span></span>

<span data-ttu-id="e0ffe-211">Мәліметтерін қарап шығу арқылы сегмент туралы шоғырланған деректерді көре аласыз.</span><span class="sxs-lookup"><span data-stu-id="e0ffe-211">You can see consolidated data about a segment by reviewing its details.</span></span>

<span data-ttu-id="e0ffe-212">**Сегменттер** бетінен қарап шығу қажет сегментті таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="e0ffe-212">On the **Segments** page, select the segment you want to review.</span></span>

<span data-ttu-id="e0ffe-213">Беттің үстіңгі бөлігінде мүшелер санындағы өзгерістерді бейнелейтін тренд графигі бар.</span><span class="sxs-lookup"><span data-stu-id="e0ffe-213">The upper part of the page includes a trend graph that visualizes changes in member count.</span></span> <span data-ttu-id="e0ffe-214">Белгілі бір күндегі мүшелер санын көру үшін деректер нүктелеріне апарыңыз.</span><span class="sxs-lookup"><span data-stu-id="e0ffe-214">Hover over data points to see the member count on a specific date.</span></span>

<span data-ttu-id="e0ffe-215">Көрнекілендіру уақыты аралығын жаңрата аласыз.</span><span class="sxs-lookup"><span data-stu-id="e0ffe-215">You can update the time frame of the visualization.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="e0ffe-216">![Сегмент уақытының ауқымы](media/segment-time-range.png "Сегмент уақытының ауқымы")</span><span class="sxs-lookup"><span data-stu-id="e0ffe-216">![Segment time range](media/segment-time-range.png "Segment time range")</span></span>

<span data-ttu-id="e0ffe-217">Төменгі бөлікте сегмент элементтерінің тізімі бар.</span><span class="sxs-lookup"><span data-stu-id="e0ffe-217">The lower part contains a list of the segment members.</span></span>

> [!NOTE]
> <span data-ttu-id="e0ffe-218">Осы тізімде пайда болған өрістер сегмент нысандарының төлсипаттарына негізделген.</span><span class="sxs-lookup"><span data-stu-id="e0ffe-218">Fields that appear in this list are based on the attributes of your segment's entities.</span></span>
>
><span data-ttu-id="e0ffe-219">Тізім — сәйкес сегмент элементтерінің алдын ала көрінісі және сегменттің алғашқы 100 жазбасын көрсетеді, оны жылдам бағалауға және қажетінше анықтамаларын қарап шығуға болады.</span><span class="sxs-lookup"><span data-stu-id="e0ffe-219">The list is a preview of the matching segment members and shows the first 100 records of your segment so that you can quickly evaluate it and review its definitions if needed.</span></span> <span data-ttu-id="e0ffe-220">Барлық сәйкес жазбаларды көру үшін [сегментті экспорттауыңыз керек](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="e0ffe-220">To see all matching records, you need to [export the segment](export-destinations.md).</span></span>

## <a name="quick-segments"></a><span data-ttu-id="e0ffe-221">Жылдам сегменттер</span><span class="sxs-lookup"><span data-stu-id="e0ffe-221">Quick segments</span></span>

<span data-ttu-id="e0ffe-222">Сегментті құрастырғыштан басқа, сегменттер жасаудың тағы бір жолы бар.</span><span class="sxs-lookup"><span data-stu-id="e0ffe-222">In addition to the segment builder, there's another path for creating segments.</span></span> <span data-ttu-id="e0ffe-223">Жылдам сегменттер бір операторы бар қарапайым сегменттерді жылдам және жедел түсініктермен құруға мүмкіндік береді.</span><span class="sxs-lookup"><span data-stu-id="e0ffe-223">Quick segments let you build simple segments with a single operator quickly and with instant insights.</span></span>

1. <span data-ttu-id="e0ffe-224">**Сегменттер** бетінде **Жаңа** > **Келесіден жылдам құру** тармағын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="e0ffe-224">On the **Segments** page, select **New** > **Quickly create from**.</span></span>

   - <span data-ttu-id="e0ffe-225">Бірыңғай тұтынушы нысанына байланысты сегментті құрастыру үшін **Профильдер** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="e0ffe-225">Select the **Profiles** option to build a segment that is based on the unified Customer entity.</span></span>
   - <span data-ttu-id="e0ffe-226">Бастапқыда **Шаралар** бетінде жасалған шаралардың әрбір Тұтынушы төлсипаты түрі бойынша сегментті құрастыру үшін **Шаралар** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="e0ffe-226">Select the **Measures** option to build a segment around each of the Customer Attribute type of measures you have previously created on the **Measures** page.</span></span>
   - <span data-ttu-id="e0ffe-227">**Болжамдар** немесе **Реттелетін үлгілер** мүмкіндіктерінің бірін пайдалану арқылы құрылған шығыс нысандарының бірінің айналасында сегмент құру үшін **Интеллект** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="e0ffe-227">Select the **Intelligence** option to build a segment around one of the output entities you generated using either the **Predictions** or **Custom Models** capabilities.</span></span>

2. <span data-ttu-id="e0ffe-228">**Жаңа жылдам сегмент** диалогтық терезесінде **Өріс** ашылмалы мәзірінен төлсипатты таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="e0ffe-228">In the **New quick segment** dialog box, select an attribute from the **Field** dropdown.</span></span>

3. <span data-ttu-id="e0ffe-229">Жүйе тұтынушылардың жақсырақ сегменттерін жасауға көмектесетін кейбір қосымша түсініктерді қамтамасыз етеді.</span><span class="sxs-lookup"><span data-stu-id="e0ffe-229">The system will provide some additional insights that help you create better segments of your customers.</span></span>
   - <span data-ttu-id="e0ffe-230">Санаттық өрістер үшін 10 үздік тұтынушы санын көрсетеміз.</span><span class="sxs-lookup"><span data-stu-id="e0ffe-230">For categorical fields, we'll show 10 top customer counts.</span></span> <span data-ttu-id="e0ffe-231">**Мән** таңдап, **Қарап шығу** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="e0ffe-231">Choose a **Value** and select **Review**.</span></span>

   - <span data-ttu-id="e0ffe-232">Сандық төлсипат үшін жүйе әрбір тұтынушы процентиліне қандай төлсипат мәні жататынын көрсетеді.</span><span class="sxs-lookup"><span data-stu-id="e0ffe-232">For a numerical attribute, the system will show what attribute value falls under each customer's percentile.</span></span> <span data-ttu-id="e0ffe-233">**Оператор** және **Мән** таңдап, **Қарап шығу** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="e0ffe-233">Choose an **Operator** and a **Value**, then select **Review**.</span></span>

4. <span data-ttu-id="e0ffe-234">Жүйе сізге **Болжалды сегмент өлшемін** береді.</span><span class="sxs-lookup"><span data-stu-id="e0ffe-234">The system will provide you with an **Estimated segment size**.</span></span> <span data-ttu-id="e0ffe-235">Сіз анықтаған сегментті құруды немесе басқа сегмент өлшемін алу үшін қайта кіруді таңдай аласыз.</span><span class="sxs-lookup"><span data-stu-id="e0ffe-235">You can choose whether to generate the segment you've defined, or first revisit it to get a different segment size.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="e0ffe-236">![Жылдам сегменттің атауы және болжамы](media/quick-segment-name.png "Жылдам сегменттің атауы және болжамы")</span><span class="sxs-lookup"><span data-stu-id="e0ffe-236">![Name and estimation for a quick segment](media/quick-segment-name.png "Name and estimation for a quick segment")</span></span>

5. <span data-ttu-id="e0ffe-237">Сегментіңіз үшін **Ат** беріңіз.</span><span class="sxs-lookup"><span data-stu-id="e0ffe-237">Provide a **Name** for your segment.</span></span> <span data-ttu-id="e0ffe-238">Оған қоса, **Көрсетілетін ат** беріңіз.</span><span class="sxs-lookup"><span data-stu-id="e0ffe-238">Optionally, provide a **Display name**.</span></span>

6. <span data-ttu-id="e0ffe-239">Сегментті жасау үшін **Сақтау** пәрменін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="e0ffe-239">Select **Save** to create your segment.</span></span>

7. <span data-ttu-id="e0ffe-240">Сегментті өңдеуді аяқтаған соң, сіз жасаған басқа сегмент сияқтыны көре аласыз.</span><span class="sxs-lookup"><span data-stu-id="e0ffe-240">After the segment has finished processing, you can view it like any other segment you've created.</span></span>

<span data-ttu-id="e0ffe-241">Мына сценарийлер үшін ұсынылған сегменттер мүмкіндігінен бөлек сегментті құрастыру құралын пайдалануды ұсынамыз:</span><span class="sxs-lookup"><span data-stu-id="e0ffe-241">For the following scenarios, we advise using the segment builder rather than the recommended segments capability:</span></span>

- <span data-ttu-id="e0ffe-242">Оператор **Болады** операторынан өзгеше санаттық өрістерде сүзгілері бар сегменттерді жасау</span><span class="sxs-lookup"><span data-stu-id="e0ffe-242">Creating segments with filters on categorical fields where the operator is different than the **Is** operator</span></span>
- <span data-ttu-id="e0ffe-243">Оператор **Арасында**, **Үлкен** және **Кіші** операторларынан өзгеше сандық өрістерде сүзгілері бар сегменттерді жасау</span><span class="sxs-lookup"><span data-stu-id="e0ffe-243">Creating segments with filters on numerical fields where the operator is different than the **Between**, **Greater than**, and **Less than** operators</span></span>
- <span data-ttu-id="e0ffe-244">Күн түрі өрістерінде сүзгілері бар сегменттер құру</span><span class="sxs-lookup"><span data-stu-id="e0ffe-244">Creating segments with filters on date type fields</span></span>

## <a name="next-steps"></a><span data-ttu-id="e0ffe-245">Келесі қадамдар</span><span class="sxs-lookup"><span data-stu-id="e0ffe-245">Next steps</span></span>

<span data-ttu-id="e0ffe-246">Тұтынушы деңгейі бойынша түсініктер алу үшін [Сегментті экспорттаңыз](export-destinations.md) және [Тұтынушы картасы](customer-card-add-in.md) мен [Қосқыштар](export-power-bi.md) параметрлерін зерттеңіз.</span><span class="sxs-lookup"><span data-stu-id="e0ffe-246">[Export a segment](export-destinations.md) and explore the [Customer Card](customer-card-add-in.md) and [Connectors](export-power-bi.md) to get insights on the customer level.</span></span>
