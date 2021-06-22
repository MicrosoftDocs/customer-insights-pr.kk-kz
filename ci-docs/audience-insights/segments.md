---
title: Аудитория туралы түсініктердегі сегменттер
description: Сегменттерге шолу және оларды құру және басқару жолы.
ms.date: 05/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 6cb7bd62bf0f61e6dc5811b20e5011e4a086c743
ms.sourcegitcommit: 84283d523a891298fca8aaf629d9f9ab2a1bc067
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 05/27/2021
ms.locfileid: "6111394"
---
# <a name="segments-overview"></a><span data-ttu-id="bdf38-103">Сегменттерге шолу</span><span class="sxs-lookup"><span data-stu-id="bdf38-103">Segments overview</span></span>

<span data-ttu-id="bdf38-104">Сегменттер тұтынушыларды демографиялық, транзакциялық немесе әрекеттік төлсипаттар бойынша топтастыруға мүмкіндік береді.</span><span class="sxs-lookup"><span data-stu-id="bdf38-104">Segments let you group your customers based on demographic, transactional, or behavioral attributes.</span></span> <span data-ttu-id="bdf38-105">Іскери мақсаттарға жету үшін мақсатты жарнама науқандарына, сатылым әрекеттеріне және тұтынушыларға қолдау көрсету әрекеттеріне сегменттерді пайдалана аласыз.</span><span class="sxs-lookup"><span data-stu-id="bdf38-105">You can use segments to target promotional campaigns, sales activities, and customer support actions to achieve your business goals.</span></span>

<span data-ttu-id="bdf38-106">Сегмент анықтамасының сүзгілеріне сәйкес келетін тұтынушы профильдері сегменттің *мүшелері* деп аталады.</span><span class="sxs-lookup"><span data-stu-id="bdf38-106">Customer profiles that match the filters of a segment definition are referred as *members* of a segment.</span></span> <span data-ttu-id="bdf38-107">Кейбір [қызмет шектеулерін](service-limits.md) қолданыңыз.</span><span class="sxs-lookup"><span data-stu-id="bdf38-107">Some [service limits](service-limits.md) apply.</span></span>

## <a name="create-a-new-segment"></a><span data-ttu-id="bdf38-108">Жаңа сегментті жасау</span><span class="sxs-lookup"><span data-stu-id="bdf38-108">Create a new segment</span></span>

<span data-ttu-id="bdf38-109">Жаңа сегмент жасаудың бірнеше әдісі бар:</span><span class="sxs-lookup"><span data-stu-id="bdf38-109">There are multiple ways to create a new segment:</span></span> 

- <span data-ttu-id="bdf38-110">Сегмент құрастырушысымен күрделі сегмент: [Бос сегмент](segment-builder.md#create-a-new-segment)</span><span class="sxs-lookup"><span data-stu-id="bdf38-110">Complex segment with segment builder: [Blank segment](segment-builder.md#create-a-new-segment)</span></span>
- <span data-ttu-id="bdf38-111">Бір операторы бар қарапайым сегменттер: [Жылдам сегмент](segment-builder.md#quick-segments)</span><span class="sxs-lookup"><span data-stu-id="bdf38-111">Simple segments with one operator: [Quick segment](segment-builder.md#quick-segments)</span></span>
- <span data-ttu-id="bdf38-112">Ұқсас тұтынушыларды табудың AI-әдісі: [Ұқсас тұтынушылар](find-similar-customer-segments.md)</span><span class="sxs-lookup"><span data-stu-id="bdf38-112">AI-powered way to find similar customers: [Similar Customers](find-similar-customer-segments.md)</span></span>
- <span data-ttu-id="bdf38-113">Көрсеткіштерге немесе төлсипаттарға негізделген жасанды интеллект ұсыныстары: [Көрсеткіштерді жақсарту үшін ұсынылған сегменттер](suggested-segments.md)</span><span class="sxs-lookup"><span data-stu-id="bdf38-113">AI-powered suggestions based on measures or attributes: [Suggested segments to improve measures](suggested-segments.md)</span></span>
- <span data-ttu-id="bdf38-114">Әрекеттерге негізделген ұсыныстар: [Тұтынушы әрекетінің негізінде ұсынылған сегменттер](suggested-segments-activity.md)</span><span class="sxs-lookup"><span data-stu-id="bdf38-114">Suggestions based on activities: [Suggested segments based on customer activity](suggested-segments-activity.md)</span></span>

## <a name="manage-existing-segments"></a><span data-ttu-id="bdf38-115">Бұрыннан бар сегменттерді басқару</span><span class="sxs-lookup"><span data-stu-id="bdf38-115">Manage existing segments</span></span>

<span data-ttu-id="bdf38-116">Барлық сақталған сегменттерді көру және оларды басқару үшін **Сегменттер** бетіне өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="bdf38-116">Go to the **Segments** page, to view all your saved segments and manage them.</span></span>

<span data-ttu-id="bdf38-117">Әрбір сегмент ол туралы қосымша ақпараттан тұратын қатар бойынша көрсетіледі.</span><span class="sxs-lookup"><span data-stu-id="bdf38-117">Each segment is represented by a row that includes additional information about the segment.</span></span>

:::image type="content" source="media/segments-selected-segment.png" alt-text="Опциялар ашылмалы тізімі және қолжетімді опциялары бар таңдалған сегмент.":::

<span data-ttu-id="bdf38-119">Сегментті таңдаған кезде келесі әрекет қолжетімді:</span><span class="sxs-lookup"><span data-stu-id="bdf38-119">The following action are available when you select a segment:</span></span>

- <span data-ttu-id="bdf38-120">Сегмент мәліметтерін, оның ішінде элементтер санының трендін, сегмент элементтерін алдын ала қарауын **қараңыз**.</span><span class="sxs-lookup"><span data-stu-id="bdf38-120">**View** the segment details, including member count trend a preview of segment members.</span></span>
- <span data-ttu-id="bdf38-121">Сипаттарын өзгерту үшін сегментті **өңдеңіз**.</span><span class="sxs-lookup"><span data-stu-id="bdf38-121">**Edit** the segment to change its properties.</span></span>
- <span data-ttu-id="bdf38-122">Сегменттің **Көшірмесін жасау** параметрі.</span><span class="sxs-lookup"><span data-stu-id="bdf38-122">**Create duplicate** of a segment.</span></span> <span data-ttu-id="bdf38-123">Оның сипаттарын бірден өзгертуді немесе жай көшірмесін сақтауды таңдауға болады.</span><span class="sxs-lookup"><span data-stu-id="bdf38-123">You can choose to edit its properties right away or simply save the duplicate.</span></span>
- <span data-ttu-id="bdf38-124">Ең соңғы деректерді қосу үшін сегментті **жаңартыңыз**.</span><span class="sxs-lookup"><span data-stu-id="bdf38-124">**Refresh** the segment to include the latest data.</span></span>
- <span data-ttu-id="bdf38-125">Сегментті **белсендіріңіз** немесе **өшіріңіз**.</span><span class="sxs-lookup"><span data-stu-id="bdf38-125">**Activate** or **Deactivate** the segment.</span></span> <span data-ttu-id="bdf38-126">Сегменттер екі мүмкін күйге ие - белсенді немесе белсенді емес.</span><span class="sxs-lookup"><span data-stu-id="bdf38-126">Segments have two possible states - active or inactive.</span></span> <span data-ttu-id="bdf38-127">Бұл күйлер сегментті редакциялау кезінде ыңғайлы.</span><span class="sxs-lookup"><span data-stu-id="bdf38-127">These states come in handy when editing a segment.</span></span> <span data-ttu-id="bdf38-128">Белсенді емес сегменттер үшін сегменттің анықтамасы бар, бірақ оған әлі тұтынушылар кірмейді.</span><span class="sxs-lookup"><span data-stu-id="bdf38-128">For inactive segments, the segment definition exists but it doesn't contain any customers yet.</span></span> <span data-ttu-id="bdf38-129">Сегментті белсендірген кезде оның күйі «белсенді емес» күйден «белсенді» күйге ауысады және сегменттің анықтамасына сәйкес келетін тұтынушыларды іздей бастайды.</span><span class="sxs-lookup"><span data-stu-id="bdf38-129">When you activate a segment, its state changes from 'inactive' to 'active" and it starts looking for customers that match the segment definition.</span></span> <span data-ttu-id="bdf38-130">Егер [жоспарланған жаңарту](system.md#schedule-tab) конфигурацияланған болса, белсенді емес сегменттерде жаңартуға тіпті әрекет жасалмағандығын көрсететін **Өткізілген** ретінде көрсетілген **Күй** параметрі болады.</span><span class="sxs-lookup"><span data-stu-id="bdf38-130">If a [scheduled refresh](system.md#schedule-tab) is configured, inactive segments have the **Status** listed as **Skipped**, indicating that a refresh wasn't even attempted.</span></span> <span data-ttu-id="bdf38-131">Белсенді емес сегмент белсендірілгенде, ол жаңарады және жоспарланған жаңартуларға қосылады.</span><span class="sxs-lookup"><span data-stu-id="bdf38-131">When an inactive segment is activated, it will refresh and will be included in scheduled refreshes.</span></span>
  <span data-ttu-id="bdf38-132">Болмаса, белгілі бір сегментті белсендіру мен ажырату үшін болашақ күн мен уақытты көрсету үшін **Белсендіру/ажырату** ашылмалы тізімінде **Кейінірек жоспарлау** функционалдығын пайдалана аласыз.</span><span class="sxs-lookup"><span data-stu-id="bdf38-132">Alternatively, you can use the **Schedule later** functionality in the **Activate/Deactivate** dropdown to specify a future date and time for activation and deactivation of a particular segment.</span></span>
- <span data-ttu-id="bdf38-133">Сегменттің **атын өзгертіңіз**.</span><span class="sxs-lookup"><span data-stu-id="bdf38-133">**Rename** the segment.</span></span>
- <span data-ttu-id="bdf38-134">Мүшелер тізімін .CSV файлы ретінде **жүктеп алыңыз**.</span><span class="sxs-lookup"><span data-stu-id="bdf38-134">**Download** the list of members as a .CSV file.</span></span>
- <span data-ttu-id="bdf38-135">Экспорттауға қатысты сегментті көру және оларды басқару үшін **экспорттауды басқарыңыз**.</span><span class="sxs-lookup"><span data-stu-id="bdf38-135">**Manage exports** to see exports related segment and manage them.</span></span> [<span data-ttu-id="bdf38-136">Экспорттаулар туралы қосымша ақпарат.</span><span class="sxs-lookup"><span data-stu-id="bdf38-136">Learn more about exports.</span></span>](export-destinations.md)
- <span data-ttu-id="bdf38-137">Сегментті **жойыңыз**.</span><span class="sxs-lookup"><span data-stu-id="bdf38-137">**Delete** the segment.</span></span>

## <a name="refresh-segments"></a><span data-ttu-id="bdf38-138">Сегменттерді жаңарту</span><span class="sxs-lookup"><span data-stu-id="bdf38-138">Refresh segments</span></span>

<span data-ttu-id="bdf38-139">**Сегменттер** бетінен **Барлығын жаңарту** параметрін таңдау арқылы барлық сегменттерді жаңартуға немесе оларды таңдап, опциялардан **Жаңарту** параметрін таңдаған кезде бір не бірнеше сегментті жаңартуға болады.</span><span class="sxs-lookup"><span data-stu-id="bdf38-139">You can refresh all segments at once by selecting **Refresh all** on the **Segments** page or you can refresh one or multiple segments when you select them and choose **Refresh** in from the options.</span></span> <span data-ttu-id="bdf38-140">Сонымен қатар **Әкімші** > **Жүйе** > **Жоспарлау** тармағындағы қайталанатын жаңартуды конфигурациялауға болады.</span><span class="sxs-lookup"><span data-stu-id="bdf38-140">Alternatively, you can configure a recurring refresh on **Admin** > **System** > **Schedule**.</span></span>

> [!TIP]
> <span data-ttu-id="bdf38-141">Тапсырмалар/процестерге арналған [күйдің алты түрі](system.md#status-types) бар.</span><span class="sxs-lookup"><span data-stu-id="bdf38-141">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="bdf38-142">Сонымен қатар көптеген процестер [басқа кезектегі процестерге тәуелді](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="bdf38-142">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="bdf38-143">Бүкіл тапсырманың барысы туралы мәліметтерді көру үшін процестің күйін таңдай аласыз.</span><span class="sxs-lookup"><span data-stu-id="bdf38-143">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="bdf38-144">Бір жұмыс тапсырмаларының бірі үшін **Мәліметтерді көру** параметрін таңдағаннан кейін, қосымша ақпаратты көруге болады: өңдеу уақыты, соңғы өңделген күні және тапсырмаға қатысты барлық қателер мен ескертулер.</span><span class="sxs-lookup"><span data-stu-id="bdf38-144">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="export-segments"></a><span data-ttu-id="bdf38-145">Сегменттерді экспорттау</span><span class="sxs-lookup"><span data-stu-id="bdf38-145">Export segments</span></span>

<span data-ttu-id="bdf38-146">Сегменттерді сегменттер бетінен немесе [экспорттау бетінен](export-destinations.md) экспорттауға болады.</span><span class="sxs-lookup"><span data-stu-id="bdf38-146">You can export a segment from the segments page or the [exports page](export-destinations.md).</span></span> 

1. <span data-ttu-id="bdf38-147">**Сегменттер** бетіне өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="bdf38-147">Go to the **Segments** page.</span></span>

1. <span data-ttu-id="bdf38-148">Экспорттау керек сегмент үшін **Тағы көрсету [...]** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="bdf38-148">Select **Show more [...]** for the segment you want to export.</span></span>

1. <span data-ttu-id="bdf38-149">Әрекеттер ашылмалы тізімінен **Экспорттауларды басқару** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="bdf38-149">Select **Manage exports** from the actions drop-down list.</span></span>

1. <span data-ttu-id="bdf38-150">**Сегментке арналған экспорттаулар (алдын ала қарау нұсқасы)** беті ашылады.</span><span class="sxs-lookup"><span data-stu-id="bdf38-150">The page **Exports (preview) for segment** opens.</span></span> <span data-ttu-id="bdf38-151">Ағымдағы сегменті бар немесе жоқ экспорттау бойынша топтастырылған барлық конфигурацияланған экспорттауларды көруге болады.</span><span class="sxs-lookup"><span data-stu-id="bdf38-151">You can see all configured exports grouped by by exports that contain the current segment or don't contain it.</span></span>

   1. <span data-ttu-id="bdf38-152">Таңдалған сегментті экспорттауға қосу үшін тізімнен экспорттауды таңдаңыз және **Сегмент қосу** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="bdf38-152">To add the selected segment to an export, select the export in the list and select **Add segment**.</span></span>

   1. <span data-ttu-id="bdf38-153">Таңдалған сегментпен жаңа экспорттау жасау үшін **Экспорттау қосу** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="bdf38-153">To create a new export with the selected segment, select **Add export**.</span></span> <span data-ttu-id="bdf38-154">Экспорттауды жасау туралы қосымша ақпаратты [Жаңа экспорттауды орнату](export-destinations.md#set-up-a-new-export) бөлімінен қараңыз.</span><span class="sxs-lookup"><span data-stu-id="bdf38-154">For more information about creating exports, see [Set up a new export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="bdf38-155">Сегменттерге арналған негізгі бетке оралу үшін **Артқа** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="bdf38-155">Select **Back** to return to the main page for segments.</span></span>

## <a name="view-processing-history-and-segment-members"></a><span data-ttu-id="bdf38-156">Өңдеу журналы мен сегмент мүшелерін көру</span><span class="sxs-lookup"><span data-stu-id="bdf38-156">View processing history and segment members</span></span>

<span data-ttu-id="bdf38-157">Мәліметтерін қарап шығу арқылы сегмент туралы шоғырланған деректерді көре аласыз.</span><span class="sxs-lookup"><span data-stu-id="bdf38-157">You can see consolidated data about a segment by reviewing its details.</span></span>

<span data-ttu-id="bdf38-158">**Сегменттер** бетінен қарап шығу қажет сегментті таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="bdf38-158">On the **Segments** page, select the segment you want to review.</span></span>

<span data-ttu-id="bdf38-159">Беттің үстіңгі бөлігінде мүшелер санындағы өзгерістерді бейнелейтін тренд графигі бар.</span><span class="sxs-lookup"><span data-stu-id="bdf38-159">The upper part of the page includes a trend graph that visualizes changes in member count.</span></span> <span data-ttu-id="bdf38-160">Белгілі бір күндегі мүшелер санын көру үшін деректер нүктелеріне апарыңыз.</span><span class="sxs-lookup"><span data-stu-id="bdf38-160">Hover over data points to see the member count on a specific date.</span></span>

<span data-ttu-id="bdf38-161">Көрнекілендіру уақыты аралығын жаңрата аласыз.</span><span class="sxs-lookup"><span data-stu-id="bdf38-161">You can update the time frame of the visualization.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="bdf38-162">![Сегмент уақытының ауқымы](media/segment-time-range.png "Сегмент уақытының ауқымы")</span><span class="sxs-lookup"><span data-stu-id="bdf38-162">![Segment time range](media/segment-time-range.png "Segment time range")</span></span>

<span data-ttu-id="bdf38-163">Төменгі бөлікте сегмент элементтерінің тізімі бар.</span><span class="sxs-lookup"><span data-stu-id="bdf38-163">The lower part contains a list of the segment members.</span></span>

> [!NOTE]
> <span data-ttu-id="bdf38-164">Осы тізімде пайда болған өрістер сегмент нысандарының төлсипаттарына негізделген.</span><span class="sxs-lookup"><span data-stu-id="bdf38-164">Fields that appear in this list are based on the attributes of your segment's entities.</span></span>
>
><span data-ttu-id="bdf38-165">Тізім — сәйкес сегмент элементтерінің алдын ала көрінісі және сегменттің алғашқы 100 жазбасын көрсетеді, оны жылдам бағалауға және қажетінше анықтамаларын қарап шығуға болады.</span><span class="sxs-lookup"><span data-stu-id="bdf38-165">The list is a preview of the matching segment members and shows the first 100 records of your segment so that you can quickly evaluate it and review its definitions if needed.</span></span> <span data-ttu-id="bdf38-166">Барлық сәйкес жазбаларды көру үшін [сегментті экспорттауыңыз керек](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="bdf38-166">To see all matching records, you need to [export the segment](export-destinations.md).</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)] 
