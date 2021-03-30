---
title: Сегменттерді жасау және басқару
description: Әр түрлі төлсипаттарға байланысты топқа тұтынушылар сегменттерін жасаңыз.
ms.date: 03/02/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 4a6e8a3216a2c0738d60247054afa9fc18412f55
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597059"
---
# <a name="create-and-manage-segments"></a><span data-ttu-id="b5bf8-103">Сегменттерді жасау және басқару</span><span class="sxs-lookup"><span data-stu-id="b5bf8-103">Create and manage segments</span></span>

<span data-ttu-id="b5bf8-104">Сегменттер тұтынушыларды демографиялық, транзакциялық немесе әрекеттік төлсипаттар бойынша топтастыруға мүмкіндік береді.</span><span class="sxs-lookup"><span data-stu-id="b5bf8-104">Segments let you group your customers based on demographic, transactional, or behavioral attributes.</span></span> <span data-ttu-id="b5bf8-105">Іскери мақсаттарға жету үшін мақсатты жарнама науқандарына, сатылым әрекеттеріне және тұтынушыларға қолдау көрсету әрекеттеріне сегменттерді пайдалана аласыз.</span><span class="sxs-lookup"><span data-stu-id="b5bf8-105">You can use segments to target promotional campaigns, sales activities, and customer support actions to achieve your business goals.</span></span>

<span data-ttu-id="b5bf8-106">Тұтынушы профилі мен оған байланысты нысандар айналасынан кешенді сүзгілерді анықтай аласыз.</span><span class="sxs-lookup"><span data-stu-id="b5bf8-106">You can define complex filters around the Customer Profile entity and its related entities.</span></span> <span data-ttu-id="b5bf8-107">Өңдеуден кейін әрбір сегмент экспорттауға және әрекет етуге болатын тұтынушы жазбалары жинағын жасайды.</span><span class="sxs-lookup"><span data-stu-id="b5bf8-107">Each segment, after processing, creates a set of customer records that you can export and take action on.</span></span> <span data-ttu-id="b5bf8-108">Кейбір [қызмет шектеулерін](service-limits.md) қолданыңыз.</span><span class="sxs-lookup"><span data-stu-id="b5bf8-108">Some [service limits](service-limits.md) apply.</span></span>

<span data-ttu-id="b5bf8-109">Басқаша көрсетілмесе, барлық сегменттер қайталанатын кестеде жаңартылған **Динамикалық сегменттер** болып табылады.</span><span class="sxs-lookup"><span data-stu-id="b5bf8-109">Unless stated otherwise, all segments are **Dynamic segments**, which are refreshed on a recurring schedule.</span></span>

<span data-ttu-id="b5bf8-110">Келесі мысалда сегменттеу мүмкіндігі көрсетілген.</span><span class="sxs-lookup"><span data-stu-id="b5bf8-110">The following example illustrates the segmentation capability.</span></span> <span data-ttu-id="b5bf8-111">Біз соңғы 90 күнде кемінде $500 тауарына тапсырыс берген *және* арта түскен тұтынушыға қызмет көрсету қоңырауына қатысқан тұтынушылар үшін сегмент анықтадық.</span><span class="sxs-lookup"><span data-stu-id="b5bf8-111">We've defined a segment for customers who ordered at least $500 of goods in the last 90 days *and* who were involved in a customer service call that got escalated.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="b5bf8-112">![Бірнеше топ](media/segmentation-group1-2.png "Бірнеше топ")</span><span class="sxs-lookup"><span data-stu-id="b5bf8-112">![Multiple groups](media/segmentation-group1-2.png "Multiple groups")</span></span>

## <a name="create-a-new-segment"></a><span data-ttu-id="b5bf8-113">Жаңа сегментті жасау</span><span class="sxs-lookup"><span data-stu-id="b5bf8-113">Create a new segment</span></span>

<span data-ttu-id="b5bf8-114">Сегменттер **Сегменттер** бетінде басқарылады.</span><span class="sxs-lookup"><span data-stu-id="b5bf8-114">Segments are managed on the **Segments** page.</span></span>

1. <span data-ttu-id="b5bf8-115">Аудитория түсініктерінде **Сегменттер** бетіне өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="b5bf8-115">In audience insights, go to the **Segments** page.</span></span>

1. <span data-ttu-id="b5bf8-116">**Жаңа** > **Бос сегмент** тармағын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="b5bf8-116">Select **New** > **Blank segment**.</span></span>

1. <span data-ttu-id="b5bf8-117">**Жаңа сегмент** тақтасынан сегмент түрін таңдап, **Ат** беріңіз.</span><span class="sxs-lookup"><span data-stu-id="b5bf8-117">In the **New segment** pane, choose a segment type and provide a **Name**.</span></span>

   <span data-ttu-id="b5bf8-118">Оған қоса, сегментті анықтауға көмектесетін сипаттама мен көрсетілетін атын беріңіз.</span><span class="sxs-lookup"><span data-stu-id="b5bf8-118">Optionally, provide a display name, and a description that helps identifying the segment.</span></span>

1. <span data-ttu-id="b5bf8-119">Топ анықталатын **Сегментті құрастыру құралы** бетіне өту үшін **Келесі** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="b5bf8-119">Select **Next** to get to the **Segment builder** page where you define a group.</span></span> <span data-ttu-id="b5bf8-120">Топ — тұтынушылар жинағы.</span><span class="sxs-lookup"><span data-stu-id="b5bf8-120">A group is a set of customers.</span></span>

1. <span data-ttu-id="b5bf8-121">Сегменттеу қажет төлсипаттан тұратын нысанды таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="b5bf8-121">Choose the entity that includes the attribute you want to segment by.</span></span>

1. <span data-ttu-id="b5bf8-122">Сегменттеу үшін төлсипат таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="b5bf8-122">Choose the attribute to segment by.</span></span> <span data-ttu-id="b5bf8-123">Бұл төлсипат төрт мәннің біреуіне ие болуы мүмкін: сандық, жолдық, күндік немесе логикалық.</span><span class="sxs-lookup"><span data-stu-id="b5bf8-123">This attribute can have one of four value types: numerical, string, date, or Boolean.</span></span>

1. <span data-ttu-id="b5bf8-124">Таңдалған төлсипат мәні мен операторды таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="b5bf8-124">Choose an operator and a value for the selected attribute.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="b5bf8-125">![Теңшелетін топ сүзгісі](media/customer-group-numbers.png "Тұтынушылар тобының сүзгісі")</span><span class="sxs-lookup"><span data-stu-id="b5bf8-125">![Custom group filter](media/customer-group-numbers.png "Customer group filter")</span></span>

   |<span data-ttu-id="b5bf8-126">Нөмірі</span><span class="sxs-lookup"><span data-stu-id="b5bf8-126">Number</span></span> |<span data-ttu-id="b5bf8-127">Анықтама</span><span class="sxs-lookup"><span data-stu-id="b5bf8-127">Definition</span></span>  |
   |---------|---------|
   |<span data-ttu-id="b5bf8-128">1</span><span class="sxs-lookup"><span data-stu-id="b5bf8-128">1</span></span>     |<span data-ttu-id="b5bf8-129">Entity</span><span class="sxs-lookup"><span data-stu-id="b5bf8-129">Entity</span></span>          |
   |<span data-ttu-id="b5bf8-130">2</span><span class="sxs-lookup"><span data-stu-id="b5bf8-130">2</span></span>     |<span data-ttu-id="b5bf8-131">Төлсипат</span><span class="sxs-lookup"><span data-stu-id="b5bf8-131">Attribute</span></span>          |
   |<span data-ttu-id="b5bf8-132">3</span><span class="sxs-lookup"><span data-stu-id="b5bf8-132">3</span></span>    |<span data-ttu-id="b5bf8-133">Амалдағыш</span><span class="sxs-lookup"><span data-stu-id="b5bf8-133">Operator</span></span>         |
   |<span data-ttu-id="b5bf8-134">4</span><span class="sxs-lookup"><span data-stu-id="b5bf8-134">4</span></span>    |<span data-ttu-id="b5bf8-135">Мәні</span><span class="sxs-lookup"><span data-stu-id="b5bf8-135">Value</span></span>         |

8. <span data-ttu-id="b5bf8-136">Егер нысан бірыңғай тұтынушы нысанына [қарым-қатынастар](relationships.md) арқылы қосылса, жарамды сегмент құру үшін қарым-қатынас жолын анықтау керек.</span><span class="sxs-lookup"><span data-stu-id="b5bf8-136">If the entity is connected to the unified customer entity through [relationships](relationships.md), you need to define the relationship path to create a valid segment.</span></span> <span data-ttu-id="b5bf8-137">Ашылмалы мәзірден **Customer: CustomerInsights** нысанын таңдағанға дейін қарым-қатынас жолынан нысандарды қосыңыз.</span><span class="sxs-lookup"><span data-stu-id="b5bf8-137">Add the entities from the relationship path until you can select the **Customer:CustomerInsights** entity from the dropdown.</span></span> <span data-ttu-id="b5bf8-138">Содан кейін әр шарт үшін **Барлық жазбалар** таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="b5bf8-138">Then, choose **All records** for each condition.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="b5bf8-139">![Сегмент құру кезіндегі қарым-қатынас жолы](media/segments-multiple-relationships.png "Сегмент құру кезіндегі қарым-қатынас жолы")</span><span class="sxs-lookup"><span data-stu-id="b5bf8-139">![Relationship path during segment creation](media/segments-multiple-relationships.png "Relationship path during segment creation")</span></span>

1. <span data-ttu-id="b5bf8-140">Әдепкі бойынша сегменттер анықталған сүзгілерге сәйкес келетін тұтынушы профильдерінің барлық төлсипаттарын қамтитын шығыс нысанын жасайды.</span><span class="sxs-lookup"><span data-stu-id="b5bf8-140">By default, segments generate an output entity that contains all attributes of customer profiles which match the defined filters.</span></span> <span data-ttu-id="b5bf8-141">Егер сегмент *Тұтынушы* нысанынан басқа нысандарға негізделген болса, осы нысандардан шығыс нысанға қосымша төлсипаттар қосуға болады.</span><span class="sxs-lookup"><span data-stu-id="b5bf8-141">If a segment is based on other entities than the *Customer* entity, you can add more attributes from these entities to the output entity.</span></span> <span data-ttu-id="b5bf8-142">Шығыс нысанға қосылатын төлсипаттарды таңдау үшін **Жоба төлсипаттары** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="b5bf8-142">Select **Project attributes** to choose the attributes that will be appended to the output entity.</span></span>  

   
   <span data-ttu-id="b5bf8-143">Мысал: сегмент *Тұтынушы* нысанына қатысты тұтынушы әрекеті деректерін қамтитын нысанға негізделген.</span><span class="sxs-lookup"><span data-stu-id="b5bf8-143">Example: A segment is based on an entity that contains customer activity data which is related to the *Customer* entity.</span></span> <span data-ttu-id="b5bf8-144">Сегмент соңғы 60 күнде анықтама қызметіне қоңырау шалған барлық тұтынушыларды іздейді.</span><span class="sxs-lookup"><span data-stu-id="b5bf8-144">The segment looks for all customers that called the help desk in the last 60 days.</span></span> <span data-ttu-id="b5bf8-145">Қоңырау ұзақтығын және қоңыраулар санын шығыс нысандағы барлық сәйкес келетін тұтынушылар жазбаларына қосуды таңдауға болады.</span><span class="sxs-lookup"><span data-stu-id="b5bf8-145">You can choose to append the call duration and the number of calls to all matching customer records in the output entity.</span></span> <span data-ttu-id="b5bf8-146">Бұл ақпарат онлайн анықтамалық мақалалар мен жиі қоңырау шалатын тұтынушыларға жиі қойылатын сұрақтарға пайдалы сілтемелері бар электрондық пошта хабарын жіберу үшін пайдалы болуы мүмкін.</span><span class="sxs-lookup"><span data-stu-id="b5bf8-146">This information might be useful to send an email with helpful links to online help articles and FAQs to customers who called frequently.</span></span>

1. <span data-ttu-id="b5bf8-147">Сегментті сақтау үшін **Сақтау** пәрменін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="b5bf8-147">Select **Save** to save your segment.</span></span> <span data-ttu-id="b5bf8-148">Барлық талаптар тексерілсе, сегментіңіз сақталады және өңделеді.</span><span class="sxs-lookup"><span data-stu-id="b5bf8-148">Your segment will be saved and processed if all requirements are validated.</span></span> <span data-ttu-id="b5bf8-149">Болмаса, ол жоба ретінде сақталады.</span><span class="sxs-lookup"><span data-stu-id="b5bf8-149">Otherwise, it will be saved as a draft.</span></span>

1. <span data-ttu-id="b5bf8-150">**Сегменттер** бетіне кері өту үшін **Сегменттерге оралу** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="b5bf8-150">Select **Back to segments** to go back to the **Segments** page.</span></span>

## <a name="manage-existing-segments"></a><span data-ttu-id="b5bf8-151">Бұрыннан бар сегменттерді басқару</span><span class="sxs-lookup"><span data-stu-id="b5bf8-151">Manage existing segments</span></span>

<span data-ttu-id="b5bf8-152">**Сегменттер** бетінен барлық сақталған сегменттерді көруге және оларды басқаруға болады.</span><span class="sxs-lookup"><span data-stu-id="b5bf8-152">On the **Segments** page, you can view all your saved segments and manage them.</span></span>

<span data-ttu-id="b5bf8-153">Әрбір сегмент ол туралы қосымша ақпараттан тұратын қатар бойынша көрсетіледі.</span><span class="sxs-lookup"><span data-stu-id="b5bf8-153">Each segment is represented by a row that includes additional information about the segment.</span></span>

<span data-ttu-id="b5bf8-154">Баған тақырыбын таңдау арқылы бағандағы сегменттерді сұрыптауға болады.</span><span class="sxs-lookup"><span data-stu-id="b5bf8-154">You can sort the segments in a column by selecting the column heading.</span></span>

<span data-ttu-id="b5bf8-155">Сегменттерді сүзгілеу үшін жоғарғы оң жақ бұрыштағы **Іздеу** өрісін пайдаланыңыз.</span><span class="sxs-lookup"><span data-stu-id="b5bf8-155">Use the **Search** box in the top-right corner to filter the segments.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="b5bf8-156">![Бұрыннан бар сегментті басқаруға арналған опциялар](media/segments-selected-segment.png "Бұрыннан бар сегментті басқаруға арналған опциялар")</span><span class="sxs-lookup"><span data-stu-id="b5bf8-156">![Options to manage an existing segment](media/segments-selected-segment.png "Options to manage an existing segment")</span></span>

<span data-ttu-id="b5bf8-157">Сегментті таңдаған кезде келесі әрекет қолжетімді:</span><span class="sxs-lookup"><span data-stu-id="b5bf8-157">The following action are available when you select a segment:</span></span>

- <span data-ttu-id="b5bf8-158">Сегмент мәліметтерін, оның ішінде элементтер санының трендін, сегмент элементтерін алдын ала қарауын **қараңыз**.</span><span class="sxs-lookup"><span data-stu-id="b5bf8-158">**View** the segment details, including member count trend a preview of segment members.</span></span>
- <span data-ttu-id="b5bf8-159">Сипаттарын өзгерту үшін сегментті **өңдеңіз**.</span><span class="sxs-lookup"><span data-stu-id="b5bf8-159">**Edit** the segment to change its properties.</span></span>
- <span data-ttu-id="b5bf8-160">Сегменттің **Көшірмесін жасау** параметрі.</span><span class="sxs-lookup"><span data-stu-id="b5bf8-160">**Create duplicate** of a segment.</span></span> <span data-ttu-id="b5bf8-161">Оның сипаттарын бірден өзгертуді немесе жай көшірмесін сақтауды таңдауға болады.</span><span class="sxs-lookup"><span data-stu-id="b5bf8-161">You can choose to edit its properties right away or simply save the duplicate.</span></span>
- <span data-ttu-id="b5bf8-162">Ең соңғы деректерді қосу үшін сегментті **жаңартыңыз**.</span><span class="sxs-lookup"><span data-stu-id="b5bf8-162">**Refresh** the segment to include the latest data.</span></span>
- <span data-ttu-id="b5bf8-163">Сегментті **белсендіріңіз** немесе **өшіріңіз**.</span><span class="sxs-lookup"><span data-stu-id="b5bf8-163">**Activate** or **Deactivate** the segment.</span></span> <span data-ttu-id="b5bf8-164">Сегменттер екі мүмкін күйге ие - белсенді немесе белсенді емес.</span><span class="sxs-lookup"><span data-stu-id="b5bf8-164">Segments have two possible states - active or inactive.</span></span> <span data-ttu-id="b5bf8-165">Бұл күйлер сегментті редакциялау кезінде ыңғайлы.</span><span class="sxs-lookup"><span data-stu-id="b5bf8-165">These states come in handy when editing a segment.</span></span> <span data-ttu-id="b5bf8-166">Белсенді емес сегменттер үшін сегменттің анықтамасы бар, бірақ оған әлі тұтынушылар кірмейді.</span><span class="sxs-lookup"><span data-stu-id="b5bf8-166">For inactive segments, the segment definition exists but it doesn't contain any customers yet.</span></span> <span data-ttu-id="b5bf8-167">Сегментті белсендірген кезде оның күйі «белсенді емес» күйден «белсенді» күйге ауысады және сегменттің анықтамасына сәйкес келетін тұтынушыларды іздей бастайды.</span><span class="sxs-lookup"><span data-stu-id="b5bf8-167">When you activate a segment, its state changes from 'inactive' to 'active" and it starts looking for customers that match the segment definition.</span></span> <span data-ttu-id="b5bf8-168">Егер [жоспарланған жаңарту](system.md#schedule-tab) конфигурацияланған болса, белсенді емес сегменттерде жаңартуға тіпті әрекет жасалмағандығын көрсететін **Өткізілген** ретінде көрсетілген **Күй** параметрі болады.</span><span class="sxs-lookup"><span data-stu-id="b5bf8-168">If a [scheduled refresh](system.md#schedule-tab) is configured, inactive segments have the **Status** listed as **Skipped**, indicating that a refresh wasn't even attempted.</span></span> <span data-ttu-id="b5bf8-169">Белсенді емес сегмент белсендірілгенде, ол жаңарады және жоспарланған жаңартуларға қосылады.</span><span class="sxs-lookup"><span data-stu-id="b5bf8-169">When an inactive segment is activated, it will refresh and will be included in scheduled refreshes.</span></span>
  <span data-ttu-id="b5bf8-170">Болмаса, белгілі бір сегментті белсендіру мен ажырату үшін болашақ күн мен уақытты көрсету үшін **Белсендіру/ажырату** ашылмалы тізімінде **Кейінірек жоспарлау** функционалдығын пайдалана аласыз.</span><span class="sxs-lookup"><span data-stu-id="b5bf8-170">Alternatively, you can use the **Schedule later** functionality in the **Activate/Deactivate** dropdown to specify a future date and time for activation and deactivation of a particular segment.</span></span>
- <span data-ttu-id="b5bf8-171">Сегменттің **атын өзгертіңіз**.</span><span class="sxs-lookup"><span data-stu-id="b5bf8-171">**Rename** the segment.</span></span>
- <span data-ttu-id="b5bf8-172">Мүшелер тізімін .CSV файлы ретінде **жүктеп алыңыз**.</span><span class="sxs-lookup"><span data-stu-id="b5bf8-172">**Download** the list of members as a .CSV file.</span></span>
- <span data-ttu-id="b5bf8-173">**Қосу** опциясы сегменттегі тұтынушы идентификаторларының тізімін басқа бағдарламада өңдеуге жібереді.</span><span class="sxs-lookup"><span data-stu-id="b5bf8-173">**Add to** option sends the list of customer IDs in the segment for processing in another application.</span></span>
- <span data-ttu-id="b5bf8-174">Сегментті **жойыңыз**.</span><span class="sxs-lookup"><span data-stu-id="b5bf8-174">**Delete** the segment.</span></span>

## <a name="refresh-segments"></a><span data-ttu-id="b5bf8-175">Сегменттерді жаңарту</span><span class="sxs-lookup"><span data-stu-id="b5bf8-175">Refresh segments</span></span>

<span data-ttu-id="b5bf8-176">**Сегменттер** бетінен **Барлығын жаңарту** параметрін таңдау арқылы барлық сегменттерді жаңартуға немесе оларды таңдап, опциялардан **Жаңарту** параметрін таңдаған кезде бір не бірнеше сегментті жаңартуға болады.</span><span class="sxs-lookup"><span data-stu-id="b5bf8-176">You can refresh all segments at once by selecting **Refresh all** on the **Segments** page or you can refresh one or multiple segments when you select them and choose **Refresh** in from the options.</span></span> <span data-ttu-id="b5bf8-177">Сонымен қатар,**Әкімші** > **Жүйе** > **Жоспарлау** тармағындағы қайталанатын жаңартуды конфигурациялауға болады.</span><span class="sxs-lookup"><span data-stu-id="b5bf8-177">Alternatively, you can configure a recurring refresh on **Admin** > **System** > **Schedule**.</span></span>

> [!TIP]
> <span data-ttu-id="b5bf8-178">Тапсырмалар/процестерге арналған [күйдің алты түрі](system.md#status-types) бар.</span><span class="sxs-lookup"><span data-stu-id="b5bf8-178">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="b5bf8-179">Сонымен қатар, көптеген процестер [басқа кезектегі процестерге тәуелді](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="b5bf8-179">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="b5bf8-180">Бүкіл тапсырманың барысы туралы мәліметтерді көру үшін процестің күйін таңдай аласыз.</span><span class="sxs-lookup"><span data-stu-id="b5bf8-180">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="b5bf8-181">Бір жұмыс тапсырмаларының бірі үшін **Мәліметтерді көру** параметрін таңдағаннан кейін, қосымша ақпаратты көруге болады: өңдеу уақыты, соңғы өңделген күні және тапсырмаға қатысты барлық қателер мен ескертулер.</span><span class="sxs-lookup"><span data-stu-id="b5bf8-181">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="download-and-export-segments"></a><span data-ttu-id="b5bf8-182">Сегменттерді жүктеу және экспорттау</span><span class="sxs-lookup"><span data-stu-id="b5bf8-182">Download and export segments</span></span>

<span data-ttu-id="b5bf8-183">Өз сегменттеріңізді CSV файлына жүктей аласыз немесе оларды Dynamics 365 Sales бағдарламасына экспорттай аласыз.</span><span class="sxs-lookup"><span data-stu-id="b5bf8-183">You can download your segments to a CSV file or export them to Dynamics 365 Sales.</span></span>

### <a name="download-segments-to-a-csv-file"></a><span data-ttu-id="b5bf8-184">Сегменттерді CSV файлына жүктеу</span><span class="sxs-lookup"><span data-stu-id="b5bf8-184">Download segments to a CSV file</span></span>

1. <span data-ttu-id="b5bf8-185">Аудитория түсініктерінде **Сегменттер** бетіне өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="b5bf8-185">In audience insights, go to the **Segments** page.</span></span>

2. <span data-ttu-id="b5bf8-186">Белгілі бір сегмент тақтасында көп нүктені таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="b5bf8-186">Select the ellipsis in a specific segment's tile.</span></span>

3. <span data-ttu-id="b5bf8-187">Әрекеттер ашылмалы тізімінен **CSV ретінде жүктеп алу** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="b5bf8-187">Select **Download as CSV** from the actions drop-down list.</span></span>

### <a name="export-segments-to-dynamics-365-sales"></a><span data-ttu-id="b5bf8-188">Сегменттерді Dynamics 365 Sales бағдарламасына экспорттау</span><span class="sxs-lookup"><span data-stu-id="b5bf8-188">Export segments to Dynamics 365 Sales</span></span>

<span data-ttu-id="b5bf8-189">Dynamics 365 Sales бағдарламасына сегменттерді экспорттамас бұрын, әкімші Dynamics 365 Sales үшін [экспорттау межелі орнын құруы](export-destinations.md) қажет.</span><span class="sxs-lookup"><span data-stu-id="b5bf8-189">Before exporting segments to Dynamics 365 Sales, an admin needs to [create the export destination](export-destinations.md) for Dynamics 365 Sales.</span></span>

1. <span data-ttu-id="b5bf8-190">Аудитория түсініктерінде **Сегменттер** бетіне өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="b5bf8-190">In audience insights, go to the **Segments** page.</span></span>

2. <span data-ttu-id="b5bf8-191">Белгілі бір сегмент тақтасында көп нүктені таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="b5bf8-191">Select the ellipsis in a specific segment's tile.</span></span>

3. <span data-ttu-id="b5bf8-192">Әрекеттердің ашылмалы тізімінен **Тізімге қосу** опциясын таңдап, деректерді жіберу керек экспорттау межелі орнын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="b5bf8-192">Select **Add to** from the actions drop-down list and select the export destination you want to send the data to.</span></span>

## <a name="draft-mode-for-segments"></a><span data-ttu-id="b5bf8-193">Сегменттердің жоба режимі</span><span class="sxs-lookup"><span data-stu-id="b5bf8-193">Draft mode for segments</span></span>

<span data-ttu-id="b5bf8-194">Барлық сегментті өңдеу талаптары сақталса, сегментті жоба ретінде сақтауға және оған **Сегменттер** тақтасынан қатынасуға болады.</span><span class="sxs-lookup"><span data-stu-id="b5bf8-194">If not all requirements to process a segment are met, you can save the segment as a draft and access it from the **Segments** page.</span></span>

<span data-ttu-id="b5bf8-195">Ол белсенді емес сегмент ретінде сақталады және оны жарамды болғанға дейін қосу мүмкін емес.</span><span class="sxs-lookup"><span data-stu-id="b5bf8-195">It will be saved as an inactive segment, and can't be activated it until it's valid.</span></span>

## <a name="add-more-conditions-to-a-group"></a><span data-ttu-id="b5bf8-196">Топқа қосымша шарттар қосу</span><span class="sxs-lookup"><span data-stu-id="b5bf8-196">Add more conditions to a group</span></span>

<span data-ttu-id="b5bf8-197">Топқа қосымша шарттар қосу үшін екі логикалық операторды пайдалана аласыз:</span><span class="sxs-lookup"><span data-stu-id="b5bf8-197">To add more conditions to a group, you can use two logical operators:</span></span>

- <span data-ttu-id="b5bf8-198">**ЖӘНЕ** операторы: екі шарт та сегменттеу процесінің бөлігі ретінде сақталуы қажет.</span><span class="sxs-lookup"><span data-stu-id="b5bf8-198">**AND** operator: Both conditions must be met as part of the segmentation process.</span></span> <span data-ttu-id="b5bf8-199">Әр түрлі нысандар бойынша шарттарды анықтаған кезде осы опция өте пайдалы болады.</span><span class="sxs-lookup"><span data-stu-id="b5bf8-199">This option is most useful when you define conditions across different entities.</span></span>

- <span data-ttu-id="b5bf8-200">**НЕМЕСЕ** операторы: шарттардың бірі сегменттеу процесінің бөлігі болуы керек.</span><span class="sxs-lookup"><span data-stu-id="b5bf8-200">**OR** operator: Either one of the conditions needs to be met as part of the segmentation process.</span></span> <span data-ttu-id="b5bf8-201">Бір нысан үшін бірнеше шартты анықтаған кезде осы опция өте пайдалы болады.</span><span class="sxs-lookup"><span data-stu-id="b5bf8-201">This option is most useful when you define multiple conditions for the same entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="b5bf8-202">![Шарты орындалуы керек НЕМЕСЕ операторы](media/segmentation-either-condition.png "Шарты орындалуы керек НЕМЕСЕ операторы")</span><span class="sxs-lookup"><span data-stu-id="b5bf8-202">![OR operator where either condition needs to be met](media/segmentation-either-condition.png "OR operator where either condition needs to be met")</span></span>

<span data-ttu-id="b5bf8-203">Дәл қазір **ЖӘНЕ** операторының астына **НЕМЕСЕ** операторы енгізілуі мүмкін, бірақ басқа жолы жоқ.</span><span class="sxs-lookup"><span data-stu-id="b5bf8-203">It's currently possible to nest an **OR** operator under an **AND** operator, but not the other way around.</span></span>

## <a name="combine-multiple-groups"></a><span data-ttu-id="b5bf8-204">Бірнеше топты біріктіру</span><span class="sxs-lookup"><span data-stu-id="b5bf8-204">Combine multiple groups</span></span>

<span data-ttu-id="b5bf8-205">Әр топ тұтынушылардың белгілі бір жиынтығын шығарады.</span><span class="sxs-lookup"><span data-stu-id="b5bf8-205">Each group produces a specific set of customers.</span></span> <span data-ttu-id="b5bf8-206">Бизнес істерге қажетті тұтынушыларды қосу үшін осы топтарды біріктіруге болады.</span><span class="sxs-lookup"><span data-stu-id="b5bf8-206">You can combine these groups to include the customers required for your business case.</span></span>

1. <span data-ttu-id="b5bf8-207">Аудитория түсініктерінде **Сегменттер** бетіне өтіп, сегментті таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="b5bf8-207">In audience insights, go to the **Segments** page and select a segment.</span></span>

2. <span data-ttu-id="b5bf8-208">**Топ қосу** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="b5bf8-208">Select **Add Group**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="b5bf8-209">![Тұтынушылар тобын қосу тобы](media/customer-group-add-group.png "Тұтынушылар тобын қосу тобы")</span><span class="sxs-lookup"><span data-stu-id="b5bf8-209">![Customer group add group](media/customer-group-add-group.png "Customer group add group")</span></span>

3. <span data-ttu-id="b5bf8-210">Келесі орнатылған операторлардың біреуін таңдаңыз: **Бірлестік**, **Қиылысу** немесе **Басқа**.</span><span class="sxs-lookup"><span data-stu-id="b5bf8-210">Select one of the following set operators: **Union**, **Intersect**, or **Except**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="b5bf8-211">![Тұтынушылар тобын қосу бірлестігі](media/customer-group-union.png "Тұтынушылар тобын қосу бірлестігі")</span><span class="sxs-lookup"><span data-stu-id="b5bf8-211">![Customer group add union](media/customer-group-union.png "Customer group add union")</span></span>

   <span data-ttu-id="b5bf8-212">Жаңа топты анықтау үшін орнатылған операторды таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="b5bf8-212">Select a set operator to define a new group.</span></span> <span data-ttu-id="b5bf8-213">Сақталатын деректерді анықтау үшін әртүрлі топтарды сақтаңыз:</span><span class="sxs-lookup"><span data-stu-id="b5bf8-213">Save different groups to determine what data gets retained:</span></span>

   - <span data-ttu-id="b5bf8-214">**Бірлестік** екі топты біріктіреді.</span><span class="sxs-lookup"><span data-stu-id="b5bf8-214">**Union** unites the two groups.</span></span>

   - <span data-ttu-id="b5bf8-215">**Қиылысу** екі топты қабаттастырады.</span><span class="sxs-lookup"><span data-stu-id="b5bf8-215">**Intersect** overlaps the two groups.</span></span> <span data-ttu-id="b5bf8-216">Екі топқа да *ортақ болып табылатын* деректер бірыңғай топта сақталады.</span><span class="sxs-lookup"><span data-stu-id="b5bf8-216">Only data that *is common* to both groups is retained in the unified group.</span></span>

   - <span data-ttu-id="b5bf8-217">**Қоспағанда** екі топты біріктіреді.</span><span class="sxs-lookup"><span data-stu-id="b5bf8-217">**Except** combines the two groups.</span></span> <span data-ttu-id="b5bf8-218">B тобындағы деректер үшін *ортақ болып табылмайтын* A тобындағы деректер ғана сақталады.</span><span class="sxs-lookup"><span data-stu-id="b5bf8-218">Only data in group A that *is not common* to data in group B is retained.</span></span>

## <a name="view-processing-history-and-segment-members"></a><span data-ttu-id="b5bf8-219">Өңдеу журналы мен сегмент мүшелерін көру</span><span class="sxs-lookup"><span data-stu-id="b5bf8-219">View processing history and segment members</span></span>

<span data-ttu-id="b5bf8-220">Мәліметтерін қарап шығу арқылы сегмент туралы шоғырланған деректерді көре аласыз.</span><span class="sxs-lookup"><span data-stu-id="b5bf8-220">You can see consolidated data about a segment by reviewing its details.</span></span>

<span data-ttu-id="b5bf8-221">**Сегменттер** бетінен қарап шығу қажет сегментті таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="b5bf8-221">On the **Segments** page, select the segment you want to review.</span></span>

<span data-ttu-id="b5bf8-222">Беттің үстіңгі бөлігінде мүшелер санындағы өзгерістерді бейнелейтін тренд графигі бар.</span><span class="sxs-lookup"><span data-stu-id="b5bf8-222">The upper part of the page includes a trend graph that visualizes changes in member count.</span></span> <span data-ttu-id="b5bf8-223">Белгілі бір күндегі мүшелер санын көру үшін деректер нүктелеріне апарыңыз.</span><span class="sxs-lookup"><span data-stu-id="b5bf8-223">Hover over data points to see the member count on a specific date.</span></span>

<span data-ttu-id="b5bf8-224">Көрнекілендіру уақыты аралығын жаңрата аласыз.</span><span class="sxs-lookup"><span data-stu-id="b5bf8-224">You can update the time frame of the visualization.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="b5bf8-225">![Сегмент уақытының ауқымы](media/segment-time-range.png "Сегмент уақытының ауқымы")</span><span class="sxs-lookup"><span data-stu-id="b5bf8-225">![Segment time range](media/segment-time-range.png "Segment time range")</span></span>

<span data-ttu-id="b5bf8-226">Төменгі бөлікте сегмент элементтерінің тізімі бар.</span><span class="sxs-lookup"><span data-stu-id="b5bf8-226">The lower part contains a list of the segment members.</span></span>

> [!NOTE]
> <span data-ttu-id="b5bf8-227">Осы тізімде пайда болған өрістер сегмент нысандарының төлсипаттарына негізделген.</span><span class="sxs-lookup"><span data-stu-id="b5bf8-227">Fields that appear in this list are based on the attributes of your segment's entities.</span></span>
>
><span data-ttu-id="b5bf8-228">Тізім — сәйкес сегмент элементтерінің алдын ала көрінісі және сегменттің алғашқы 100 жазбасын көрсетеді, оны жылдам бағалауға және қажетінше анықтамаларын қарап шығуға болады.</span><span class="sxs-lookup"><span data-stu-id="b5bf8-228">The list is a preview of the matching segment members and shows the first 100 records of your segment so that you can quickly evaluate it and review its definitions if needed.</span></span> <span data-ttu-id="b5bf8-229">Барлық сәйкес жазбаларды көру үшін [сегментті экспорттауыңыз керек](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="b5bf8-229">To see all matching records, you need to [export the segment](export-destinations.md).</span></span>

## <a name="quick-segments"></a><span data-ttu-id="b5bf8-230">Жылдам сегменттер</span><span class="sxs-lookup"><span data-stu-id="b5bf8-230">Quick segments</span></span>

<span data-ttu-id="b5bf8-231">Сегментті құрастырғыштан басқа, сегменттер жасаудың тағы бір жолы бар.</span><span class="sxs-lookup"><span data-stu-id="b5bf8-231">In addition to the segment builder, there's another path for creating segments.</span></span> <span data-ttu-id="b5bf8-232">Жылдам сегменттер бір операторы бар қарапайым сегменттерді жылдам және жедел түсініктермен құруға мүмкіндік береді.</span><span class="sxs-lookup"><span data-stu-id="b5bf8-232">Quick segments let you build simple segments with a single operator quickly and with instant insights.</span></span>

1. <span data-ttu-id="b5bf8-233">**Сегменттер** бетінде **Жаңа** > **Келесіден жылдам құру** тармағын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="b5bf8-233">On the **Segments** page, select **New** > **Quickly create from**.</span></span>

   - <span data-ttu-id="b5bf8-234">Бірыңғай тұтынушы нысанына байланысты сегментті құрастыру үшін **Профильдер** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="b5bf8-234">Select the **Profiles** option to build a segment that is based on the unified Customer entity.</span></span>
   - <span data-ttu-id="b5bf8-235">Бастапқыда **Шаралар** бетінде жасалған шаралардың әрбір Тұтынушы төлсипаты түрі бойынша сегментті құрастыру үшін **Шаралар** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="b5bf8-235">Select the **Measures** option to build a segment around each of the Customer Attribute type of measures you have previously created on the **Measures** page.</span></span>
   - <span data-ttu-id="b5bf8-236">**Болжамдар** немесе **Реттелетін үлгілер** мүмкіндіктерінің бірін пайдалану арқылы құрылған шығыс нысандарының бірінің айналасында сегмент құру үшін **Интеллект** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="b5bf8-236">Select the **Intelligence** option to build a segment around one of the output entities you generated using either the **Predictions** or **Custom Models** capabilities.</span></span>

2. <span data-ttu-id="b5bf8-237">**Жаңа жылдам сегмент** диалогтық терезесінде **Өріс** ашылмалы мәзірінен төлсипатты таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="b5bf8-237">In the **New quick segment** dialog box, select an attribute from the **Field** dropdown.</span></span>

3. <span data-ttu-id="b5bf8-238">Жүйе тұтынушылардың жақсырақ сегменттерін жасауға көмектесетін кейбір қосымша түсініктерді қамтамасыз етеді.</span><span class="sxs-lookup"><span data-stu-id="b5bf8-238">The system will provide some additional insights that help you create better segments of your customers.</span></span>
   - <span data-ttu-id="b5bf8-239">Санаттық өрістер үшін 10 үздік тұтынушы санын көрсетеміз.</span><span class="sxs-lookup"><span data-stu-id="b5bf8-239">For categorical fields, we'll show 10 top customer counts.</span></span> <span data-ttu-id="b5bf8-240">**Мән** таңдап, **Қарап шығу** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="b5bf8-240">Choose a **Value** and select **Review**.</span></span>

   - <span data-ttu-id="b5bf8-241">Сандық төлсипат үшін жүйе әрбір тұтынушы процентиліне қандай төлсипат мәні жататынын көрсетеді.</span><span class="sxs-lookup"><span data-stu-id="b5bf8-241">For a numerical attribute, the system will show what attribute value falls under each customer's percentile.</span></span> <span data-ttu-id="b5bf8-242">**Оператор** және **Мән** таңдап, **Қарап шығу** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="b5bf8-242">Choose an **Operator** and a **Value**, then select **Review**.</span></span>

4. <span data-ttu-id="b5bf8-243">Жүйе сізге **Болжалды сегмент өлшемін** береді.</span><span class="sxs-lookup"><span data-stu-id="b5bf8-243">The system will provide you with an **Estimated segment size**.</span></span> <span data-ttu-id="b5bf8-244">Сіз анықтаған сегментті құруды немесе басқа сегмент өлшемін алу үшін қайта кіруді таңдай аласыз.</span><span class="sxs-lookup"><span data-stu-id="b5bf8-244">You can choose whether to generate the segment you've defined, or first revisit it to get a different segment size.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="b5bf8-245">![Жылдам сегменттің атауы және болжамы](media/quick-segment-name.png "Жылдам сегменттің атауы және болжамы")</span><span class="sxs-lookup"><span data-stu-id="b5bf8-245">![Name and estimation for a quick segment](media/quick-segment-name.png "Name and estimation for a quick segment")</span></span>

5. <span data-ttu-id="b5bf8-246">Сегментіңіз үшін **Ат** беріңіз.</span><span class="sxs-lookup"><span data-stu-id="b5bf8-246">Provide a **Name** for your segment.</span></span> <span data-ttu-id="b5bf8-247">Оған қоса, **Көрсетілетін ат** беріңіз.</span><span class="sxs-lookup"><span data-stu-id="b5bf8-247">Optionally, provide a **Display name**.</span></span>

6. <span data-ttu-id="b5bf8-248">Сегментті жасау үшін **Сақтау** пәрменін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="b5bf8-248">Select **Save** to create your segment.</span></span>

7. <span data-ttu-id="b5bf8-249">Сегментті өңдеуді аяқтаған соң, сіз жасаған басқа сегмент сияқтыны көре аласыз.</span><span class="sxs-lookup"><span data-stu-id="b5bf8-249">After the segment has finished processing, you can view it like any other segment you've created.</span></span>

<span data-ttu-id="b5bf8-250">Мына сценарийлер үшін ұсынылған сегменттер мүмкіндігінен бөлек сегментті құрастыру құралын пайдалануды ұсынамыз:</span><span class="sxs-lookup"><span data-stu-id="b5bf8-250">For the following scenarios, we advise using the segment builder rather than the recommended segments capability:</span></span>

- <span data-ttu-id="b5bf8-251">Оператор **Болады** операторынан өзгеше санаттық өрістерде сүзгілері бар сегменттерді жасау</span><span class="sxs-lookup"><span data-stu-id="b5bf8-251">Creating segments with filters on categorical fields where the operator is different than the **Is** operator</span></span>
- <span data-ttu-id="b5bf8-252">Оператор **Арасында**, **Үлкен** және **Кіші** операторларынан өзгеше сандық өрістерде сүзгілері бар сегменттерді жасау</span><span class="sxs-lookup"><span data-stu-id="b5bf8-252">Creating segments with filters on numerical fields where the operator is different than the **Between**, **Greater than**, and **Less than** operators</span></span>
- <span data-ttu-id="b5bf8-253">Күн түрі өрістерінде сүзгілері бар сегменттер құру</span><span class="sxs-lookup"><span data-stu-id="b5bf8-253">Creating segments with filters on date type fields</span></span>

## <a name="next-steps"></a><span data-ttu-id="b5bf8-254">Келесі қадамдар</span><span class="sxs-lookup"><span data-stu-id="b5bf8-254">Next steps</span></span>

<span data-ttu-id="b5bf8-255">Тұтынушы деңгейі бойынша түсініктер алу үшін [Сегментті экспорттаңыз](export-destinations.md) және [Тұтынушы картасы](customer-card-add-in.md) мен [Қосқыштар](export-power-bi.md) параметрлерін зерттеңіз.</span><span class="sxs-lookup"><span data-stu-id="b5bf8-255">[Export a segment](export-destinations.md) and explore the [Customer Card](customer-card-add-in.md) and [Connectors](export-power-bi.md) to get insights on the customer level.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]