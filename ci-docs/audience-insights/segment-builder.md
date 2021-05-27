---
title: Сегменттерді жасау және басқару
description: Әр түрлі төлсипаттарға байланысты топқа тұтынушылар сегменттерін жасаңыз.
ms.date: 05/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 550e509a24701fe5fcdeb9d54311872dc954156c
ms.sourcegitcommit: 72603fb39c4d5dbca71128815a2e1692542ea4dc
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 05/19/2021
ms.locfileid: "6064944"
---
# <a name="create-and-manage-segments"></a><span data-ttu-id="93b8c-103">Сегменттерді жасау және басқару</span><span class="sxs-lookup"><span data-stu-id="93b8c-103">Create and manage segments</span></span>

<span data-ttu-id="93b8c-104">Бірыңғай тұтынушы нысаны мен оған қатысты нысандар айналасындағы күрделі сүзгілерді анықтаңыз.</span><span class="sxs-lookup"><span data-stu-id="93b8c-104">Define complex filters around the unified customer entity and its related entities.</span></span> <span data-ttu-id="93b8c-105">Өңдеуден кейін әрбір сегмент экспорттауға және әрекет етуге болатын тұтынушы жазбалары жинағын жасайды.</span><span class="sxs-lookup"><span data-stu-id="93b8c-105">Each segment, after processing, creates a set of customer records that you can export and take action on.</span></span> <span data-ttu-id="93b8c-106">Сегменттер **Сегменттер** бетінде басқарылады.</span><span class="sxs-lookup"><span data-stu-id="93b8c-106">Segments are managed on the **Segments** page.</span></span> 

<span data-ttu-id="93b8c-107">Келесі мысалда сегменттеу мүмкіндігі көрсетілген.</span><span class="sxs-lookup"><span data-stu-id="93b8c-107">The following example illustrates the segmentation capability.</span></span> <span data-ttu-id="93b8c-108">Біз соңғы 90 күнде кемінде $500 тауарына тапсырыс берген *және* арта түскен тұтынушыға қызмет көрсету қоңырауына қатысқан тұтынушылар үшін сегмент анықтадық.</span><span class="sxs-lookup"><span data-stu-id="93b8c-108">We've defined a segment for customers who ordered at least $500 of goods in the last 90 days *and* who were involved in a customer service call that got escalated.</span></span>

:::image type="content" source="media/segmentation-group1-2.png" alt-text="Тұтынушы сегментін көрсететін екі тобы бар сегмент құрастырушысы пайдаланушы интерфейсінің скриншоты.":::

## <a name="create-a-new-segment"></a><span data-ttu-id="93b8c-110">Жаңа сегментті жасау</span><span class="sxs-lookup"><span data-stu-id="93b8c-110">Create a new segment</span></span>

<span data-ttu-id="93b8c-111">Жаңа сегмент жасаудың бірнеше әдісі бар.</span><span class="sxs-lookup"><span data-stu-id="93b8c-111">There are multiple ways to create a new segment.</span></span> <span data-ttu-id="93b8c-112">Бұл бөлімде *бос сегментті* басынан бастап жасау жолы сипатталады.</span><span class="sxs-lookup"><span data-stu-id="93b8c-112">This section describes how to create a *blank segment* from scratch.</span></span> <span data-ttu-id="93b8c-113">Сондай‑ақ бұрыннан бар нысандар негізінде *жылдам сегмент* жасауға болады немесе *ұсынылған сегменттерді* алу үшін компьютерлік оқыту модельдерін пайдалануға болады.</span><span class="sxs-lookup"><span data-stu-id="93b8c-113">You can also create a *quick segment* based on existing entities or make use of machine learning models to get *suggested segments*.</span></span> <span data-ttu-id="93b8c-114">Қосымша ақпарат: [Сегменттерге шолу](segments.md).</span><span class="sxs-lookup"><span data-stu-id="93b8c-114">More information: [Segments overview](segments.md).</span></span>

<span data-ttu-id="93b8c-115">Сегментті жасау кезінде нобайды сақтай аласыз.</span><span class="sxs-lookup"><span data-stu-id="93b8c-115">While creating a segment, you can save a draft.</span></span> <span data-ttu-id="93b8c-116">Ол белсенді емес сегмент ретінде сақталады және оны жарамды конфигурация аяқталғаннан кейін белсендіру мүмкін емес.</span><span class="sxs-lookup"><span data-stu-id="93b8c-116">It will be saved as an inactive segment, and can't be activated it finished with a valid configuration.</span></span>

1. <span data-ttu-id="93b8c-117">**Сегменттер** бетіне өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="93b8c-117">Go to the **Segments** page.</span></span>

1. <span data-ttu-id="93b8c-118">**Жаңа** > **Бос сегмент** тармағын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="93b8c-118">Select **New** > **Blank segment**.</span></span>

1. <span data-ttu-id="93b8c-119">**Жаңа сегмент** тақтасында сегмент түрін таңдаңыз:</span><span class="sxs-lookup"><span data-stu-id="93b8c-119">In the **New segment** pane, choose a segment type:</span></span>

   - <span data-ttu-id="93b8c-120">**Динамикалық сегменттер** [қайталанатын кесте бойынша](segments.md#refresh-segments) жаңартылады.</span><span class="sxs-lookup"><span data-stu-id="93b8c-120">**Dynamic segments** [refresh](segments.md#refresh-segments) on a recurring schedule.</span></span>
   - <span data-ttu-id="93b8c-121">**Статикалық сегменттер** жасалған кезде бір рет іске қосылады.</span><span class="sxs-lookup"><span data-stu-id="93b8c-121">**Static segments** run once when you create it.</span></span>

1. <span data-ttu-id="93b8c-122">Сегмент үшін **Шығыс нысан атауы** параметрін беріңіз.</span><span class="sxs-lookup"><span data-stu-id="93b8c-122">Provide an **Output entity name** for the segment.</span></span> <span data-ttu-id="93b8c-123">Оған қоса, сегментті анықтауға көмектесетін сипаттама мен көрсетілетін атын беріңіз.</span><span class="sxs-lookup"><span data-stu-id="93b8c-123">Optionally, provide a display name, and a description that helps identifying the segment.</span></span>

1. <span data-ttu-id="93b8c-124">Топ анықталатын **Сегментті құрастыру құралы** бетіне өту үшін **Келесі** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="93b8c-124">Select **Next** to get to the **Segment builder** page where you define a group.</span></span> <span data-ttu-id="93b8c-125">Топ — тұтынушылар жинағы.</span><span class="sxs-lookup"><span data-stu-id="93b8c-125">A group is a set of customers.</span></span>

1. <span data-ttu-id="93b8c-126">Сегменттеу қажет төлсипаттан тұратын нысанды таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="93b8c-126">Choose the entity that includes the attribute you want to segment by.</span></span>

1. <span data-ttu-id="93b8c-127">Сегменттеу үшін төлсипат таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="93b8c-127">Choose the attribute to segment by.</span></span> <span data-ttu-id="93b8c-128">Бұл төлсипат төрт мәннің біреуіне ие болуы мүмкін: сандық, жолдық, күндік немесе логикалық.</span><span class="sxs-lookup"><span data-stu-id="93b8c-128">This attribute can have one of four value types: numerical, string, date, or Boolean.</span></span>

1. <span data-ttu-id="93b8c-129">Таңдалған төлсипат мәні мен операторды таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="93b8c-129">Choose an operator and a value for the selected attribute.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="93b8c-130">![Теңшелетін топ сүзгісі](media/customer-group-numbers.png "Тұтынушылар тобының сүзгісі")</span><span class="sxs-lookup"><span data-stu-id="93b8c-130">![Custom group filter](media/customer-group-numbers.png "Customer group filter")</span></span>

   |<span data-ttu-id="93b8c-131">Саны</span><span class="sxs-lookup"><span data-stu-id="93b8c-131">Number</span></span> |<span data-ttu-id="93b8c-132">Анықтама</span><span class="sxs-lookup"><span data-stu-id="93b8c-132">Definition</span></span>  |
   |---------|---------|
   |<span data-ttu-id="93b8c-133">1-көше</span><span class="sxs-lookup"><span data-stu-id="93b8c-133">1</span></span>     |<span data-ttu-id="93b8c-134">Entity</span><span class="sxs-lookup"><span data-stu-id="93b8c-134">Entity</span></span>          |
   |<span data-ttu-id="93b8c-135">2-көше</span><span class="sxs-lookup"><span data-stu-id="93b8c-135">2</span></span>     |<span data-ttu-id="93b8c-136">Атрибут</span><span class="sxs-lookup"><span data-stu-id="93b8c-136">Attribute</span></span>          |
   |<span data-ttu-id="93b8c-137">3</span><span class="sxs-lookup"><span data-stu-id="93b8c-137">3</span></span>    |<span data-ttu-id="93b8c-138">Амалдағыш</span><span class="sxs-lookup"><span data-stu-id="93b8c-138">Operator</span></span>         |
   |<span data-ttu-id="93b8c-139">4</span><span class="sxs-lookup"><span data-stu-id="93b8c-139">4</span></span>    |<span data-ttu-id="93b8c-140">Мәні</span><span class="sxs-lookup"><span data-stu-id="93b8c-140">Value</span></span>         |

   1. <span data-ttu-id="93b8c-141">Топқа қосымша шарттар қосу үшін екі логикалық операторды пайдалана аласыз:</span><span class="sxs-lookup"><span data-stu-id="93b8c-141">To add more conditions to a group, you can use two logical operators:</span></span>

      - <span data-ttu-id="93b8c-142">**ЖӘНЕ** операторы: екі шарт та сегменттеу процесінің бөлігі ретінде сақталуы қажет.</span><span class="sxs-lookup"><span data-stu-id="93b8c-142">**AND** operator: Both conditions must be met as part of the segmentation process.</span></span> <span data-ttu-id="93b8c-143">Әр түрлі нысандар бойынша шарттарды анықтаған кезде осы опция өте пайдалы болады.</span><span class="sxs-lookup"><span data-stu-id="93b8c-143">This option is most useful when you define conditions across different entities.</span></span>

      - <span data-ttu-id="93b8c-144">**НЕМЕСЕ** операторы: шарттардың бірі сегменттеу процесінің бөлігі болуы керек.</span><span class="sxs-lookup"><span data-stu-id="93b8c-144">**OR** operator: Either one of the conditions needs to be met as part of the segmentation process.</span></span> <span data-ttu-id="93b8c-145">Бір нысан үшін бірнеше шартты анықтаған кезде осы опция өте пайдалы болады.</span><span class="sxs-lookup"><span data-stu-id="93b8c-145">This option is most useful when you define multiple conditions for the same entity.</span></span>

      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="93b8c-146">![Шарты орындалуы керек НЕМЕСЕ операторы](media/segmentation-either-condition.png "Шарты орындалуы керек НЕМЕСЕ операторы")</span><span class="sxs-lookup"><span data-stu-id="93b8c-146">![OR operator where either condition needs to be met](media/segmentation-either-condition.png "OR operator where either condition needs to be met")</span></span>

      <span data-ttu-id="93b8c-147">Дәл қазір **ЖӘНЕ** операторының астына **НЕМЕСЕ** операторы енгізілуі мүмкін, бірақ басқа жолы жоқ.</span><span class="sxs-lookup"><span data-stu-id="93b8c-147">It's currently possible to nest an **OR** operator under an **AND** operator, but not the other way around.</span></span>

   1. <span data-ttu-id="93b8c-148">Әр топ тұтынушылар жиынтығына сәйкес келеді.</span><span class="sxs-lookup"><span data-stu-id="93b8c-148">Each group matches set of customers.</span></span> <span data-ttu-id="93b8c-149">Сіз өзіңіздің бизнес ісіңізге қажетті тұтынушыларды қосу үшін топтарды біріктіре аласыз.</span><span class="sxs-lookup"><span data-stu-id="93b8c-149">You can combine groups to include the customers required for your business case.</span></span>    
   <span data-ttu-id="93b8c-150">**Топ қосу** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="93b8c-150">Select **Add Group**.</span></span>

      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="93b8c-151">![Тұтынушылар тобын қосу тобы](media/customer-group-add-group.png "Тұтынушылар тобын қосу тобы")</span><span class="sxs-lookup"><span data-stu-id="93b8c-151">![Customer group add group](media/customer-group-add-group.png "Customer group add group")</span></span>

   1. <span data-ttu-id="93b8c-152">Орнатылған операторлардың бірін таңдаңыз: **Біріктіру**, **Қиылысу** немесе **Басқа**.</span><span class="sxs-lookup"><span data-stu-id="93b8c-152">Select one of the set operators: **Union**, **Intersect**, or **Except**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="93b8c-153">![Тұтынушылар тобын қосу бірлестігі](media/customer-group-union.png "Тұтынушылар тобын қосу бірлестігі")</span><span class="sxs-lookup"><span data-stu-id="93b8c-153">![Customer group add union](media/customer-group-union.png "Customer group add union")</span></span>

   - <span data-ttu-id="93b8c-154">**Бірлестік** екі топты біріктіреді.</span><span class="sxs-lookup"><span data-stu-id="93b8c-154">**Union** unites the two groups.</span></span>

   - <span data-ttu-id="93b8c-155">**Қиылысу** екі топты қабаттастырады.</span><span class="sxs-lookup"><span data-stu-id="93b8c-155">**Intersect** overlaps the two groups.</span></span> <span data-ttu-id="93b8c-156">Екі топқа да *ортақ болып табылатын* деректер бірыңғай топта сақталады.</span><span class="sxs-lookup"><span data-stu-id="93b8c-156">Only data that *is common* to both groups is retained in the unified group.</span></span>

   - <span data-ttu-id="93b8c-157">**Қоспағанда** екі топты біріктіреді.</span><span class="sxs-lookup"><span data-stu-id="93b8c-157">**Except** combines the two groups.</span></span> <span data-ttu-id="93b8c-158">B тобындағы деректер үшін *ортақ болып табылмайтын* A тобындағы деректер ғана сақталады.</span><span class="sxs-lookup"><span data-stu-id="93b8c-158">Only data in group A that *is not common* to data in group B is retained.</span></span>

1. <span data-ttu-id="93b8c-159">Егер нысан бірыңғай тұтынушы нысанына [қарым-қатынастар](relationships.md) арқылы қосылса, жарамды сегмент құру үшін қарым-қатынас жолын анықтау керек.</span><span class="sxs-lookup"><span data-stu-id="93b8c-159">If the entity is connected to the unified customer entity through [relationships](relationships.md), you need to define the relationship path to create a valid segment.</span></span> <span data-ttu-id="93b8c-160">Ашылмалы мәзірден **Customer: CustomerInsights** нысанын таңдағанға дейін қарым-қатынас жолынан нысандарды қосыңыз.</span><span class="sxs-lookup"><span data-stu-id="93b8c-160">Add the entities from the relationship path until you can select the **Customer:CustomerInsights** entity from the dropdown.</span></span> <span data-ttu-id="93b8c-161">Содан кейін әр қадам үшін **Барлық жазбалар** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="93b8c-161">Then, choose **All records** for each step.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="93b8c-162">![Сегмент құру кезіндегі қарым-қатынас жолы](media/segments-multiple-relationships.png "Сегмент құру кезіндегі қарым-қатынас жолы")</span><span class="sxs-lookup"><span data-stu-id="93b8c-162">![Relationship path during segment creation](media/segments-multiple-relationships.png "Relationship path during segment creation")</span></span>

1. <span data-ttu-id="93b8c-163">Әдепкі бойынша сегменттер анықталған сүзгілерге сәйкес келетін тұтынушы профильдерінің барлық төлсипаттарын қамтитын шығыс нысанын жасайды.</span><span class="sxs-lookup"><span data-stu-id="93b8c-163">By default, segments generate an output entity that contains all attributes of customer profiles which match the defined filters.</span></span> <span data-ttu-id="93b8c-164">Егер сегмент *Тұтынушы* нысанынан басқа нысандарға негізделген болса, осы нысандардан шығыс нысанға қосымша төлсипаттар қосуға болады.</span><span class="sxs-lookup"><span data-stu-id="93b8c-164">If a segment is based on other entities than the *Customer* entity, you can add more attributes from these entities to the output entity.</span></span> <span data-ttu-id="93b8c-165">Шығыс нысанға қосылатын төлсипаттарды таңдау үшін **Жоба төлсипаттары** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="93b8c-165">Select **Project attributes** to choose the attributes that will be appended to the output entity.</span></span>  
  
   <span data-ttu-id="93b8c-166">Мысал: сегмент *Тұтынушы* нысанына қатысты тұтынушы әрекеті деректерін қамтитын нысанға негізделген.</span><span class="sxs-lookup"><span data-stu-id="93b8c-166">Example: A segment is based on an entity that contains customer activity data which is related to the *Customer* entity.</span></span> <span data-ttu-id="93b8c-167">Сегмент соңғы 60 күнде анықтама қызметіне қоңырау шалған барлық тұтынушыларды іздейді.</span><span class="sxs-lookup"><span data-stu-id="93b8c-167">The segment looks for all customers that called the help desk in the last 60 days.</span></span> <span data-ttu-id="93b8c-168">Қоңырау ұзақтығын және қоңыраулар санын шығыс нысандағы барлық сәйкес келетін тұтынушылар жазбаларына қосуды таңдауға болады.</span><span class="sxs-lookup"><span data-stu-id="93b8c-168">You can choose to append the call duration and the number of calls to all matching customer records in the output entity.</span></span> <span data-ttu-id="93b8c-169">Бұл ақпарат онлайн анықтамалық мақалалар мен жиі қоңырау шалатын тұтынушыларға жиі қойылатын сұрақтарға пайдалы сілтемелері бар электрондық пошта хабарын жіберу үшін пайдалы болуы мүмкін.</span><span class="sxs-lookup"><span data-stu-id="93b8c-169">This information might be useful to send an email with helpful links to online help articles and FAQs to customers who called frequently.</span></span>

   > [!NOTE]
   > - <span data-ttu-id="93b8c-170">Жоспарланған төлсипаттар тек тұтынушы нысанымен біреуі көпке қатынасы бар нысандар үшін жұмыс істейді.</span><span class="sxs-lookup"><span data-stu-id="93b8c-170">Projected attributes only work for entities that have a one-to-many relationship with the customer entity.</span></span> <span data-ttu-id="93b8c-171">Мысалы, бір тұтынушы бірнеше жазылымға ие бола алады.</span><span class="sxs-lookup"><span data-stu-id="93b8c-171">For example, one customer can have multiple subscriptions.</span></span>
   > - <span data-ttu-id="93b8c-172">Сіз құрастырып жатқан сегмент сұрауының әр тобында қолданылатын нысанның төлсипаттарын ғана жобалай аласыз.</span><span class="sxs-lookup"><span data-stu-id="93b8c-172">You can only project attributes from an entity that is used in every group of segment query you are building.</span></span>
   > - <span data-ttu-id="93b8c-173">Жоспарланған төлсипаттар орнатылған операторларды пайдалану кезінде ескеріледі.</span><span class="sxs-lookup"><span data-stu-id="93b8c-173">Projected attributes are factored in when using set operators.</span></span>

1. <span data-ttu-id="93b8c-174">Сегментті сақтау үшін **Сақтау** пәрменін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="93b8c-174">Select **Save** to save your segment.</span></span> <span data-ttu-id="93b8c-175">Барлық талаптар тексерілсе, сегментіңіз сақталады және өңделеді.</span><span class="sxs-lookup"><span data-stu-id="93b8c-175">Your segment will be saved and processed if all requirements are validated.</span></span> <span data-ttu-id="93b8c-176">Болмаса, ол жоба ретінде сақталады.</span><span class="sxs-lookup"><span data-stu-id="93b8c-176">Otherwise, it will be saved as a draft.</span></span>

1. <span data-ttu-id="93b8c-177">**Сегменттер** бетіне кері өту үшін **Сегменттерге оралу** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="93b8c-177">Select **Back to segments** to go back to the **Segments** page.</span></span>



## <a name="quick-segments"></a><span data-ttu-id="93b8c-178">Жылдам сегменттер</span><span class="sxs-lookup"><span data-stu-id="93b8c-178">Quick segments</span></span>

<span data-ttu-id="93b8c-179">Жылдам сегменттер тезірек түсіну үшін бір оператормен қарапайым сегменттерді жылдам құруға мүмкіндік береді.</span><span class="sxs-lookup"><span data-stu-id="93b8c-179">Quick segments let you build simple segments with a single operator quickly for faster insights.</span></span>

1. <span data-ttu-id="93b8c-180">**Сегменттер** бетінде **Жаңа** > **Жасалатын орын** тармағын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="93b8c-180">On the **Segments** page, select **New** > **Create from**.</span></span>

   - <span data-ttu-id="93b8c-181">*Бірыңғай тұтынушы* нысанына негізделген сегментті құрастыру үшін **Профильдер** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="93b8c-181">Select the **Profiles** option to build a segment that is based on the *unified customer* entity.</span></span>
   - <span data-ttu-id="93b8c-182">Бұрын құрған өлшемдер бойынша сегмент құру үшін **Өлшемдер** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="93b8c-182">Select the **Measures** option to build a segment around  measures you have previously created.</span></span>
   - <span data-ttu-id="93b8c-183">**Болжамдар** немесе **Реттелетін үлгілер** мүмкіндіктерінің бірін пайдалану арқылы құрылған шығыс нысандарының бірінің айналасында сегмент құру үшін **Интеллект** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="93b8c-183">Select the **Intelligence** option to build a segment around one of the output entities you generated using either the **Predictions** or **Custom Models** capabilities.</span></span>

2. <span data-ttu-id="93b8c-184">**Жаңа жылдам сегмент** диалогтық терезесінде **Өріс** ашылмалы мәзірінен төлсипатты таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="93b8c-184">In the **New quick segment** dialog box, select an attribute from the **Field** dropdown.</span></span>

3. <span data-ttu-id="93b8c-185">Жүйе тұтынушылардың жақсырақ сегменттерін жасауға көмектесетін кейбір қосымша түсініктерді қамтамасыз етеді.</span><span class="sxs-lookup"><span data-stu-id="93b8c-185">The system will provide some additional insights that help you create better segments of your customers.</span></span>
   - <span data-ttu-id="93b8c-186">Санаттық өрістер үшін 10 үздік тұтынушы санын көрсетеміз.</span><span class="sxs-lookup"><span data-stu-id="93b8c-186">For categorical fields, we'll show 10 top customer counts.</span></span> <span data-ttu-id="93b8c-187">**Мән** таңдап, **Қарап шығу** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="93b8c-187">Choose a **Value** and select **Review**.</span></span>

   - <span data-ttu-id="93b8c-188">Сандық төлсипат үшін жүйе әрбір тұтынушы процентиліне қандай төлсипат мәні жататынын көрсетеді.</span><span class="sxs-lookup"><span data-stu-id="93b8c-188">For a numerical attribute, the system will show what attribute value falls under each customer's percentile.</span></span> <span data-ttu-id="93b8c-189">**Оператор** және **Мән** таңдап, **Қарап шығу** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="93b8c-189">Choose an **Operator** and a **Value**, then select **Review**.</span></span>

4. <span data-ttu-id="93b8c-190">Жүйе сізге **Болжалды сегмент өлшемін** береді.</span><span class="sxs-lookup"><span data-stu-id="93b8c-190">The system will provide you with an **Estimated segment size**.</span></span> <span data-ttu-id="93b8c-191">Сіз анықтаған сегментті құруды немесе басқа сегмент өлшемін алу үшін қайта кіруді таңдай аласыз.</span><span class="sxs-lookup"><span data-stu-id="93b8c-191">You can choose whether to generate the segment you've defined, or first revisit it to get a different segment size.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="93b8c-192">![Жылдам сегменттің атауы және болжамы](media/quick-segment-name.png "Жылдам сегменттің атауы және болжамы")</span><span class="sxs-lookup"><span data-stu-id="93b8c-192">![Name and estimation for a quick segment](media/quick-segment-name.png "Name and estimation for a quick segment")</span></span>

5. <span data-ttu-id="93b8c-193">Сегментіңіз үшін **Ат** беріңіз.</span><span class="sxs-lookup"><span data-stu-id="93b8c-193">Provide a **Name** for your segment.</span></span> <span data-ttu-id="93b8c-194">Оған қоса, **Көрсетілетін ат** беріңіз.</span><span class="sxs-lookup"><span data-stu-id="93b8c-194">Optionally, provide a **Display name**.</span></span>

6. <span data-ttu-id="93b8c-195">Сегментті жасау үшін **Сақтау** пәрменін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="93b8c-195">Select **Save** to create your segment.</span></span>

7. <span data-ttu-id="93b8c-196">Сегментті өңдеуді аяқтаған соң, сіз жасаған басқа сегмент сияқтыны көре аласыз.</span><span class="sxs-lookup"><span data-stu-id="93b8c-196">After the segment has finished processing, you can view it like any other segment you've created.</span></span>

## <a name="next-steps"></a><span data-ttu-id="93b8c-197">Келесі қадамдар</span><span class="sxs-lookup"><span data-stu-id="93b8c-197">Next steps</span></span>

<span data-ttu-id="93b8c-198">Тұтынушы деңгейі бойынша түсініктер алу үшін [Сегментті экспорттаңыз](export-destinations.md) және [Тұтынушы картасы](customer-card-add-in.md) мен [Қосқыштар](export-power-bi.md) параметрлерін зерттеңіз.</span><span class="sxs-lookup"><span data-stu-id="93b8c-198">[Export a segment](export-destinations.md) and explore the [Customer Card](customer-card-add-in.md) and [Connectors](export-power-bi.md) to get insights on the customer level.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
