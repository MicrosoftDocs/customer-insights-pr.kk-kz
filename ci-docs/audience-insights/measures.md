---
title: Өлшемдерді жасау және өңдеу
description: Белгілі бір бизнес аймақтарының өнімділігін талдау және әсер ету үшін тұтынушыға қатысты шараларды анықтаңыз.
ms.date: 10/15/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: wameng
manager: shellyha
ms.openlocfilehash: 0e214a6eb66abd27f7292db3ce2c2a6e16a8ff33
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406249"
---
# <a name="define-and-manage-measures"></a><span data-ttu-id="c3632-103">Көрсеткіштерді анықтау және басқару</span><span class="sxs-lookup"><span data-stu-id="c3632-103">Define and manage measures</span></span>

<span data-ttu-id="c3632-104">**Шаралар** ішінде белгілі бір бизнес аймақтарының өнімділігі мен күйіне әсер ететін өнімділіктің негізгі көрсеткіштерін (KPI) көрсетеді.</span><span class="sxs-lookup"><span data-stu-id="c3632-104">**Measures** represent key performance indicators (KPIs) that reflect the performance and health of specific business areas.</span></span> <span data-ttu-id="c3632-105">Аудитория мәліметтері сіздің кодтауыңызды немесе өлшемдеріңізді қолмен тексеруді қажет етпейтін сұрау құрастырғышын пайдаланып, өлшемдердің әртүрлі түрлерін құрудың интуитивті тәжірибесін ұсынады.</span><span class="sxs-lookup"><span data-stu-id="c3632-105">Audience insights provides an intuitive experience for building different types of measures, using a query builder that doesn't require you to code or validate your measures manually.</span></span> <span data-ttu-id="c3632-106">**Басты** бетінен бизнес шараларды бақылауға, **Тұтынушы картасынан** белгілі бір тұтынушылардың шараларын көруге және **Сегменттер** бетінен тұтынушы сегменттерін анықтау шараларын пайдалануға болады.</span><span class="sxs-lookup"><span data-stu-id="c3632-106">You can track your business measures on the **Home** page, see measures for specific customers on the **Customer Card**, and use measures to define customer segments on the **Segments** page.</span></span>

## <a name="create-a-measure"></a><span data-ttu-id="c3632-107">Шараны жасау</span><span class="sxs-lookup"><span data-stu-id="c3632-107">Create a measure</span></span>

<span data-ttu-id="c3632-108">Бұл бөлімде шараны басынан жасау жолы көрсетілген.</span><span class="sxs-lookup"><span data-stu-id="c3632-108">This section walks you through creating a measure from scratch.</span></span> <span data-ttu-id="c3632-109">Тұтынушы нысаны арқылы қосылған бірнеше деректер көзінен деректері бар шараларды құрастыра аласыз.</span><span class="sxs-lookup"><span data-stu-id="c3632-109">You can build measures with data from multiple data sources that are connected through the Customer entity.</span></span> <span data-ttu-id="c3632-110">Кейбір [қызмет шектеулерін](service-limits.md) қолданыңыз.</span><span class="sxs-lookup"><span data-stu-id="c3632-110">Some [service limits](service-limits.md) apply.</span></span>

1. <span data-ttu-id="c3632-111">Аудитория мәліметтерінде **Өлшемдер** параметріне өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="c3632-111">In audience insights, go to **Measures**.</span></span>

2. <span data-ttu-id="c3632-112">**Жаңа шара** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="c3632-112">Select **New measure**.</span></span>

3. <span data-ttu-id="c3632-113">Шара **Түрін** таңдаңыз:</span><span class="sxs-lookup"><span data-stu-id="c3632-113">Choose the measure **Type**:</span></span>

   - <span data-ttu-id="c3632-114">**Тұтынушы төлсипаты**: тұтынушы көрсеткішіне, мәніне немесе күйіне әсер ететін тұтынушының жалғыз өрісі.</span><span class="sxs-lookup"><span data-stu-id="c3632-114">**Customer attribute**: A single field per customer that reflects a score, value, or state for the customer.</span></span> <span data-ttu-id="c3632-115">Тұтынушы төлсипаттары **Customer_Measure** деп аталатын жаңа жүйемен құрылған нысанда төлсипаттар ретінде жасалады.</span><span class="sxs-lookup"><span data-stu-id="c3632-115">Customer attributes are created as attributes in a new system-generated entity called **Customer_Measure**.</span></span>

   - <span data-ttu-id="c3632-116">**Тұтынушы шарасы**: таңдалған өлшемдер бойынша үзілісі бар тұтынушы әрекетіндегі түсініктер.</span><span class="sxs-lookup"><span data-stu-id="c3632-116">**Customer measure**: Insights on customer behavior with breakdown by selected dimensions.</span></span> <span data-ttu-id="c3632-117">Әрбір тұтынушы үшін бірнеше жазбасы бар әрбір шара үшін жаңа нысан құрылады.</span><span class="sxs-lookup"><span data-stu-id="c3632-117">A new entity is generated for each measure, potentially with multiple records per customer.</span></span>

   - <span data-ttu-id="c3632-118">**Бизнес шара**: бизнес өнімділігі мен күйін бақылайды.</span><span class="sxs-lookup"><span data-stu-id="c3632-118">**Business measure**: Tracks your business performance and health of the business.</span></span> <span data-ttu-id="c3632-119">Бизнес шараларда екі түрлі шығыс болуы мүмкін: **Басты** бетте көрсетілген сандық шығыс немесе **Нысандар** бетінен табылатын жаңа нысан.</span><span class="sxs-lookup"><span data-stu-id="c3632-119">Business measures can have two different outputs: a numeric output that shows on the **Home** page or a new entity that you find on the **Entities** page.</span></span>

4. <span data-ttu-id="c3632-120">**Атын** және қосымша **Көрсетілетін атын** беріп, **Келесі** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="c3632-120">Provide a **Name** and an optional **Display name**, then select **Next**.</span></span>

5. <span data-ttu-id="c3632-121">**Нысандар** бөлімінен ашылмалы тізімнен алғашқы нысанды таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="c3632-121">In the **Entities** section, select the first entity from the drop-down list.</span></span> <span data-ttu-id="c3632-122">Осы кезде қосымша нысандарды шара анықтамасының бөлігі ретінде қажеттілігін шешуіңіз керек.</span><span class="sxs-lookup"><span data-stu-id="c3632-122">At this point, you should decide whether additional entities are needed as part of your measure definition.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c3632-123">![Шара анықтамасы](media/measure-definition.png "Өлшем анықтамасы")</span><span class="sxs-lookup"><span data-stu-id="c3632-123">![Measure definition](media/measure-definition.png "Measure definition")</span></span>

   <span data-ttu-id="c3632-124">Қосымша нысандарды қосу үшін **Нысан қосу** параметрін таңдап, шара үшін пайдалану керек нысандарды таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="c3632-124">To add more entities, select **Add entity** and select entities you want to use for the measure.</span></span>

   > [!NOTE]
   > <span data-ttu-id="c3632-125">Бастапқы нысанға қарым-қатынастары бар нысандарды ғана таңдай аласыз.</span><span class="sxs-lookup"><span data-stu-id="c3632-125">You can select only entities that have relationships to your starting entity.</span></span> <span data-ttu-id="c3632-126">Анықтаушы қарым-қатынастар туралы қосымша ақпаратты [Қарым-қатынастар](relationships.md) бөлімін қараңыз.</span><span class="sxs-lookup"><span data-stu-id="c3632-126">For more information about defining relationships, see [Relationships](relationships.md).</span></span>

6. <span data-ttu-id="c3632-127">Оған қоса, айнымалыларды теңшей аласыз.</span><span class="sxs-lookup"><span data-stu-id="c3632-127">Optionally, you can configure variables.</span></span> <span data-ttu-id="c3632-128">**Айнымалылар** бөлімінен **Жаңа айнымалы** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="c3632-128">In the **Variables** section, select **New variable**.</span></span>

   <span data-ttu-id="c3632-129">Айнымалылар — әрбір таңдалған жазбада жасалған есептеулер.</span><span class="sxs-lookup"><span data-stu-id="c3632-129">Variables are calculations that are made on each of your selected records.</span></span> <span data-ttu-id="c3632-130">Мысалы, әрбір тұтынушы жазбасына арналған сату орны (POS) мен онлайн сатылым қосындысы.</span><span class="sxs-lookup"><span data-stu-id="c3632-130">For example, summing point-of-sale (POS) and online sales for each of your customers' records.</span></span>

7. <span data-ttu-id="c3632-131">Айнымалы үшін **Ат** беріңіз.</span><span class="sxs-lookup"><span data-stu-id="c3632-131">Provide a **Name** for the variable.</span></span>

8. <span data-ttu-id="c3632-132">**Өрнек** аймағынан есептеу басталатын өрісті таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="c3632-132">In the **Expression** area, choose a field to begin your calculation with.</span></span>

9. <span data-ttu-id="c3632-133">Есептеуге қосылатын қосымша өрістерді таңдаған кезде **Өрнек** аймағында өрнекті теріңіз.</span><span class="sxs-lookup"><span data-stu-id="c3632-133">Type an expression in the **Expression** area while choosing more fields to be included in your calculation.</span></span>

   > [!NOTE]
   > <span data-ttu-id="c3632-134">Қазіргі уақытта тек арифметикалық өрнектерге қолдау көрсетіледі.</span><span class="sxs-lookup"><span data-stu-id="c3632-134">Currently, only arithmetic expressions are supported.</span></span> <span data-ttu-id="c3632-135">Оған қоса, әр түрлі [нысан жолдарынан](relationships.md) нысандар үшін айнымалыны есептеуге қолдау көрсетілмейді.</span><span class="sxs-lookup"><span data-stu-id="c3632-135">Additionally, variable calculation isn't supported for entities from different [entity paths](relationships.md).</span></span>

10. <span data-ttu-id="c3632-136">**Дайын** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="c3632-136">Select **Done**.</span></span>

11. <span data-ttu-id="c3632-137">**Шара анықтамасы** бөлімінде жаңа шара нысанына немесе төлсипатқа таңдалған нысандар мен есептелген айнымалыларды біріктіру жолын анықтай аласыз.</span><span class="sxs-lookup"><span data-stu-id="c3632-137">In the **Measure definition** section, you'll define how your chosen entities and calculated variables are aggregated in a new measure entity or attribute.</span></span>

12. <span data-ttu-id="c3632-138">**Жаңа өлшем** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="c3632-138">Select **New dimension**.</span></span> <span data-ttu-id="c3632-139">Өлшемді *топтастыру реті* функциясы ретінде ойлай аласыз.</span><span class="sxs-lookup"><span data-stu-id="c3632-139">You can think of a dimension as a *group by* function.</span></span> <span data-ttu-id="c3632-140">Шара нысанының немесе төлсипатының деректер шығысы барлық анықталған өлшемдер бойынша топтастырылады.</span><span class="sxs-lookup"><span data-stu-id="c3632-140">The data output of your Measure entity or attribute will be grouped by all of your defined dimensions.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="c3632-141">![Біріктіру циклін таңдау](media/measures-businessreport-measure-definition2.png "Біріктіру циклін таңдау")</span><span class="sxs-lookup"><span data-stu-id="c3632-141">![Choose aggregate cycle](media/measures-businessreport-measure-definition2.png "Choose aggregate cycle")</span></span>

    <span data-ttu-id="c3632-142">Өлшем анықтамасының бөлігі ретінде мына анықтаманы таңдаңыз немесе енгізіңіз:</span><span class="sxs-lookup"><span data-stu-id="c3632-142">Select or enter the following information as part of your dimension's definition:</span></span>

    - <span data-ttu-id="c3632-143">**Нысан**: Шара нысанын анықтасаңыз, онда кемінде бір төлсипат болуы керек.</span><span class="sxs-lookup"><span data-stu-id="c3632-143">**Entity**: If you define a Measure entity, it should include at least one attribute.</span></span> <span data-ttu-id="c3632-144">Шара төлсипатын анықтасаңыз, онда әдепкі бойынша тек бір төлсипат болады.</span><span class="sxs-lookup"><span data-stu-id="c3632-144">If you define a Measure attribute, it will include only one attribute by default.</span></span> <span data-ttu-id="c3632-145">Бұл таңдауда төлсипат қосылған нысан таңдалады.</span><span class="sxs-lookup"><span data-stu-id="c3632-145">This selection is about choosing the entity that includes that attribute.</span></span>
    - <span data-ttu-id="c3632-146">**Өріс**: Шара нысанына немесе төлсипатына қосылатын белгілі бір төлсипатты таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="c3632-146">**Field**: Choose the specific attribute to be included either in your Measure entity or attribute.</span></span>
    - <span data-ttu-id="c3632-147">**Контейнер**: күнделікті, айлық немесе жылдық негізде деректерді біріктіру қажеттілігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="c3632-147">**Bucket**: Choose whether you want to aggregate data on a daily, monthly, or annual basis.</span></span> <span data-ttu-id="c3632-148">Бұл күн түрі төлсипатын таңдаған жағдайда ғана қажет таңдау.</span><span class="sxs-lookup"><span data-stu-id="c3632-148">It's a required selection only if you've selected a Date type attribute.</span></span>
    - <span data-ttu-id="c3632-149">**Ретінде**: жаңа өріс атын анықтайды.</span><span class="sxs-lookup"><span data-stu-id="c3632-149">**As**: Defines the name of your new field.</span></span>
    - <span data-ttu-id="c3632-150">**Көрсетілетін аты**: өрістің көрсетілетін атын анықтайды.</span><span class="sxs-lookup"><span data-stu-id="c3632-150">**Display name**: Defines the display name of your field.</span></span>

    > [!NOTE]
    > <span data-ttu-id="c3632-151">Бизнес шара жалғыз сандық нысан ретінде сақталады және шараға қосымша өлшемдер қосқанша **Басты** бетте пайда болады.</span><span class="sxs-lookup"><span data-stu-id="c3632-151">Your business measure will be saved as a single-number entity and will appear on the **Home** page unless you add more dimensions to your measure.</span></span> <span data-ttu-id="c3632-152">Қосымша өлшемдерді қосқан соң, **Басты** бетте шара *көрсетілмейді*.</span><span class="sxs-lookup"><span data-stu-id="c3632-152">After adding more dimensions, the measure will *not* show up on the **Home** page.</span></span>

13. <span data-ttu-id="c3632-153">Оған қоса, біріктіру функцияларын қосыңыз.</span><span class="sxs-lookup"><span data-stu-id="c3632-153">Optionally, add aggregation functions.</span></span> <span data-ttu-id="c3632-154">Шаралар нысанындағы немесе төлсипатындағы жаңа мәнде нәтижелерді жасаған біріктіру.</span><span class="sxs-lookup"><span data-stu-id="c3632-154">Any aggregation that you create results in a new value within your Measures entity or attribute.</span></span> <span data-ttu-id="c3632-155">Қолдау көрсетілетін біріктіру функциялары: **Мин**, **Макс**, **Орташа**, **Орташа**, **Қосынды**, **Бірегейді санау**, **Бірінші** (өлшем мәнінің бірінші жазбасын алады) және **Соңғы** (өлшем мәніне қосылған соңғы жазбаны алады).</span><span class="sxs-lookup"><span data-stu-id="c3632-155">Supported aggregation functions are: **Min**, **Max**, **Average**, **Median**, **Sum**, **Count Unique**, **First** (takes the first record of a dimension value), and **Last** (takes the last record added to a dimension value).</span></span>

14. <span data-ttu-id="c3632-156">Шараға өзгерістерді қолдану үшін **Сақтау** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="c3632-156">Select **Save** to apply your changes to the measure.</span></span>

## <a name="manage-your-measures"></a><span data-ttu-id="c3632-157">Көрсеткіштерді басқару</span><span class="sxs-lookup"><span data-stu-id="c3632-157">Manage your measures</span></span>

<span data-ttu-id="c3632-158">Кем дегенде бір өлшем жасағаннан кейін, сіз өлшемдер тізімін **Өлшемдер** бетінен көресіз.</span><span class="sxs-lookup"><span data-stu-id="c3632-158">After creating at least one measure, you'll see a list of measures on the **Measures** page.</span></span>

<span data-ttu-id="c3632-159">Шара түрі, жасаушы, жасалу күні мен уақыты, соңғы өңдеу күні мен уақыты, күйі (шара белсенді, белсенді емес немесе сәтсіз) және соңғы жаңарту күні мен уақыты туралы ақпаратты таба аласыз.</span><span class="sxs-lookup"><span data-stu-id="c3632-159">You'll find information about the measure type, the creator, creation date and time, last edit date and time, status (whether the measure is active, inactive, or failed), and last refresh date and time.</span></span> <span data-ttu-id="c3632-160">Тізімнен көрсеткішті таңдағанда, сіз оның нәтижесін алдын-ала көре аласыз.</span><span class="sxs-lookup"><span data-stu-id="c3632-160">When you select a measure from the list, you can see a preview of its output.</span></span>

<span data-ttu-id="c3632-161">Барлық көрсеткішті бір уақытта жаңарту үшін, нақты көрсеткішті таңдамай **Барлығын жаңарту** опциясын басыңыз.</span><span class="sxs-lookup"><span data-stu-id="c3632-161">To refresh all of your measures at the same time, select **Refresh all** without selecting a specific measure.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="c3632-162">![Бір көрсеткішті басқару әрекеттері](media/measure-actions.png "Бір көрсеткішті басқару әрекеттері")</span><span class="sxs-lookup"><span data-stu-id="c3632-162">![Actions to manage single measures](media/measure-actions.png "Actions to manage single measures")</span></span>

<span data-ttu-id="c3632-163">Болмаса, тізімнен көрсеткішті таңдаңыз және келесі әрекеттердің біреуін орындаңыз:</span><span class="sxs-lookup"><span data-stu-id="c3632-163">Alternatively, select a measure from the list and perform one of the following actions:</span></span>

- <span data-ttu-id="c3632-164">Мәліметтерді көру үшін көрсеткіш атауын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="c3632-164">Select the measure name to see its details.</span></span>
- <span data-ttu-id="c3632-165">Көрсеткіш конфигурациясын **өңдеңіз**.</span><span class="sxs-lookup"><span data-stu-id="c3632-165">**Edit** the configuration of the measure.</span></span>
- <span data-ttu-id="c3632-166">Көрсеткіш **атауын өзгертіңіз**.</span><span class="sxs-lookup"><span data-stu-id="c3632-166">**Rename** the measure.</span></span>
- <span data-ttu-id="c3632-167">Көрсеткішті **жойыңыз**.</span><span class="sxs-lookup"><span data-stu-id="c3632-167">**Delete** the measure.</span></span>
- <span data-ttu-id="c3632-168">Көрсеткішке арналған жаңарту процесін бастау үшін көп нүктені (...) таңдаңыз, содан кейін **Жаңарту** опциясын басыңыз.</span><span class="sxs-lookup"><span data-stu-id="c3632-168">Select the ellipsis (...) and then **Refresh** to start the refresh process for the measure.</span></span>
- <span data-ttu-id="c3632-169">Көрсеткіштің CSV файлын алу үшін көп нүктені (...) таңдаңыз, содан кейін **Жүктеу** опциясын басыңыз.</span><span class="sxs-lookup"><span data-stu-id="c3632-169">Select the ellipsis (...) and then **Download** to get a .CSV file of the measure.</span></span>

> [!TIP]
> <span data-ttu-id="c3632-170">Тапсырмалар/процестерге арналған [күйдің алты түрі](system.md#status-types) бар.</span><span class="sxs-lookup"><span data-stu-id="c3632-170">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="c3632-171">Сонымен қатар, көптеген процестер [басқа кезектегі процестерге тәуелді](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="c3632-171">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="c3632-172">Бүкіл тапсырманың барысы туралы мәліметтерді көру үшін процестің күйін таңдай аласыз.</span><span class="sxs-lookup"><span data-stu-id="c3632-172">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="c3632-173">Бір жұмыс тапсырмаларының бірі үшін **Мәліметтерді көру** параметрін таңдағаннан кейін, қосымша ақпаратты көруге болады: өңдеу уақыты, соңғы өңделген күні және тапсырмаға қатысты барлық қателер мен ескертулер.</span><span class="sxs-lookup"><span data-stu-id="c3632-173">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="c3632-174">Келесі қадам</span><span class="sxs-lookup"><span data-stu-id="c3632-174">Next step</span></span>

<span data-ttu-id="c3632-175">**Сегменттер** бетінде алғашқы тұтынушы сегментін жасау үшін бұрыннан бар өлшемдерді қолдана аласыз.</span><span class="sxs-lookup"><span data-stu-id="c3632-175">You cam use existing measures to create your first customer segment on the **Segments** page.</span></span> <span data-ttu-id="c3632-176">Қосымша ақпаратты [Сегменттер](segments.md) бөлімінен қараңыз.</span><span class="sxs-lookup"><span data-stu-id="c3632-176">For more information, see [Segments](segments.md).</span></span>
