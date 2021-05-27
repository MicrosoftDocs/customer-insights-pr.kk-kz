---
title: Көрсеткіштер құру және басқару
description: Бизнесіңіздің өнімділігін талдау және көрсету үшін көрсеткіштерді анықтаңыз.
ms.date: 04/12/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wameng
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 402e5ef3515bce0e6f56788781b7bd909738aaa6
ms.sourcegitcommit: b833e333745d321edeaf96d3ed14458cbce02ff1
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 05/17/2021
ms.locfileid: "6049257"
---
# <a name="define-and-manage-measures"></a><span data-ttu-id="192ad-103">Көрсеткіштерді анықтау және басқару</span><span class="sxs-lookup"><span data-stu-id="192ad-103">Define and manage measures</span></span>

<span data-ttu-id="192ad-104">Өлшемдер тұтынушы әрекеттері мен бизнес өнімділігін жақсырақ түсінуге көмектеседі.</span><span class="sxs-lookup"><span data-stu-id="192ad-104">Measures help you to better understand customer behaviors and business performance.</span></span> <span data-ttu-id="192ad-105">Олар [бірыңғай профильдердегі](data-unification.md) қатысты мәндерді қарастырады.</span><span class="sxs-lookup"><span data-stu-id="192ad-105">They look at relevant values from [unified profiles](data-unification.md).</span></span> <span data-ttu-id="192ad-106">Мысалы, бизнес жеке тұтынушының сатып алу тарихын түсіну үшін *бір тұтынушы үшін жалпы шығын* параметрін көргісі келеді немесе бүкіл бизнестегі жиынтық деңгейдегі кірісті түсіну *компанияның жалпы сатылымы* параметрін өлшегісі келуі мүмкін.</span><span class="sxs-lookup"><span data-stu-id="192ad-106">For example, a business wants to see the *total spend per customer* to understand individual customer’s purchase history or measure *total sales of the company* to understand the aggregate-level revenue in the whole business.</span></span>  

<span data-ttu-id="192ad-107">Көрсеткіштер көрсеткіш құрастырушы, әртүрлі операторлары бар деректерді сұрау платформасы және қарапайым салыстыру опциялары арқылы жасалады.</span><span class="sxs-lookup"><span data-stu-id="192ad-107">Measures are created using the measure builder, a data query platform with various operators and simple mapping options.</span></span> <span data-ttu-id="192ad-108">Ол сізге деректерді сүзгілеуге, нәтижелерді топтастыруға, [нысандар қатынасы жолдарын](relationships.md) анықтауға және нәтижені алдын ала қарауға мүмкіндік береді.</span><span class="sxs-lookup"><span data-stu-id="192ad-108">It lets you filter the data, group results, detect [entity relationship paths](relationships.md), and preview the output.</span></span>

<span data-ttu-id="192ad-109">Тұтыну деректерін сұрау және түсініктерді шығару арқылы бизнес әрекеттерді жоспарлау үшін көрсеткіш құрастырушысын пайдаланыңыз.</span><span class="sxs-lookup"><span data-stu-id="192ad-109">Use the measure builder to plan business activities by querying customer data and extract insights.</span></span> <span data-ttu-id="192ad-110">Мысалы, *әр тұтынушыға шаққандағы жалпы шығын* және *әр тұтынушының жалпы кірісі* көрсеткішін жасау шығыны мен кірісі де жоғары тұтынушылар тобын анықтауға көмектеседі.</span><span class="sxs-lookup"><span data-stu-id="192ad-110">For example, creating a measure of *total spend per customer* and *total return per customer* helps identify a group of customers with high spend yet high return.</span></span> <span data-ttu-id="192ad-111">Келесі ең жақсы әрекеттерді жүргізу үшін [сегмент құруға](segments.md) болады.</span><span class="sxs-lookup"><span data-stu-id="192ad-111">You can [create a segment](segments.md) to drive next best actions.</span></span> 

## <a name="build-your-own-measure-from-scratch"></a><span data-ttu-id="192ad-112">Өз өлшеміңізді басынан бастап жасау</span><span class="sxs-lookup"><span data-stu-id="192ad-112">Build your own measure from scratch</span></span>

<span data-ttu-id="192ad-113">Бұл бөлімде жаңа көрсеткішті нөлден бастап жасау жолын үйренесіз.</span><span class="sxs-lookup"><span data-stu-id="192ad-113">This section walks you through creating a new measure from scratch.</span></span> <span data-ttu-id="192ad-114">Тұтынушы нысанымен қосылатын қарым-қатынас орнатылған деректер нысандарының деректер атрибуттарымен көрсеткіш құруға болады.</span><span class="sxs-lookup"><span data-stu-id="192ad-114">You can build a measure with data attributes from data entities that have a relationship set up to connect with the Customer entity.</span></span> 

1. <span data-ttu-id="192ad-115">Аудитория мәліметтерінде **Өлшемдер** параметріне өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="192ad-115">In audience insights, go to **Measures**.</span></span>

1. <span data-ttu-id="192ad-116">**Жаңа** түймешігін таңдаңыз және **Өзіңіздікін жасау** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="192ad-116">Select **New** and choose **Build your own**.</span></span>

1. <span data-ttu-id="192ad-117">**Атын өзгерту** пәрменін таңдап, көрсеткішке **Атау** беріңіз.</span><span class="sxs-lookup"><span data-stu-id="192ad-117">Select **Edit name** and provide a **Name** for the measure.</span></span> 
   > [!NOTE]
   > <span data-ttu-id="192ad-118">Егер сіздің жаңа өлшем конфигурацияңызда тек екі өріс болса, мысалы, CustomerID және бір есептеу, нәтиже жүйе арқылы жасалған Customer_Measure деп аталатын нысанға жаңа баған ретінде қосылады.</span><span class="sxs-lookup"><span data-stu-id="192ad-118">If your new measure configuration has only two fields, for example, CustomerID and one calculation, the output will be added as a new column to the system generated entity called Customer_Measure.</span></span> <span data-ttu-id="192ad-119">Көрсеткіш мәнін тұтынушының бірыңғай профилінен көре аласыз.</span><span class="sxs-lookup"><span data-stu-id="192ad-119">And you will be able to see the measure’s value in the unified customer profile.</span></span> <span data-ttu-id="192ad-120">Басқа көрсеткіштер өз нысандарын тудырады.</span><span class="sxs-lookup"><span data-stu-id="192ad-120">Other measures will generate their own entities.</span></span>

1. <span data-ttu-id="192ad-121">Конфигурация аймағында, **Функцияны таңдау** ашылмалы мәзірінен жиынтық функцияны таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="192ad-121">In the configuration area, choose the aggregation function from the **Select Function** drop-down menu.</span></span> <span data-ttu-id="192ad-122">Жиынтық функцияларға мыналар кіреді:</span><span class="sxs-lookup"><span data-stu-id="192ad-122">Aggregation functions include:</span></span> 
   - <span data-ttu-id="192ad-123">**Sum**</span><span class="sxs-lookup"><span data-stu-id="192ad-123">**Sum**</span></span>
   - <span data-ttu-id="192ad-124">**Орта есеппен**</span><span class="sxs-lookup"><span data-stu-id="192ad-124">**Average**</span></span>
   - <span data-ttu-id="192ad-125">**Саны**</span><span class="sxs-lookup"><span data-stu-id="192ad-125">**Count**</span></span>
   - <span data-ttu-id="192ad-126">**Бірегейді санау**</span><span class="sxs-lookup"><span data-stu-id="192ad-126">**Count Unique**</span></span>
   - <span data-ttu-id="192ad-127">**Ең көп**</span><span class="sxs-lookup"><span data-stu-id="192ad-127">**Max**</span></span>
   - <span data-ttu-id="192ad-128">**Min**</span><span class="sxs-lookup"><span data-stu-id="192ad-128">**Min**</span></span>
   - <span data-ttu-id="192ad-129">**Бірінші**: деректер жазбасының бірінші мәнін алады</span><span class="sxs-lookup"><span data-stu-id="192ad-129">**First**: takes the first value of the data record</span></span>
   - <span data-ttu-id="192ad-130">**Соңғы**: деректер жазбасына қосылған соңғы мәнді алады</span><span class="sxs-lookup"><span data-stu-id="192ad-130">**Last**: takes the last value that was added to the data record</span></span>

   :::image type="content" source="media/measure-operators.png" alt-text="Көрсеткіш есептеулеріне арналған операторлар.":::

1. <span data-ttu-id="192ad-132">Осы көрсеткішті құруға қажет деректерді таңдау үшін **Атрибут қосу** пәрменін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="192ad-132">Select **Add attribute** to select the data you need to create this measure.</span></span>
   
   1. <span data-ttu-id="192ad-133">**Атрибуттар** қойыншасын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="192ad-133">Select the **Attributes** tab.</span></span> 
   1. <span data-ttu-id="192ad-134">Деректер нысаны: өлшеу керек атрибутты қамтитын нысанды таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="192ad-134">Data entity: Choose the entity that includes the attribute you want to measure.</span></span> 
   1. <span data-ttu-id="192ad-135">Деректер атрибуты: көрсеткішті есептеу үшін жиынтық функцияда пайдаланылатын атрибутты таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="192ad-135">Data attribute: Choose the attribute you want to use in the aggregation function to calculate the measure.</span></span> <span data-ttu-id="192ad-136">Бір уақытта тек бір атрибутты таңдауға болады.</span><span class="sxs-lookup"><span data-stu-id="192ad-136">You can only select one attribute at a time.</span></span>
   1. <span data-ttu-id="192ad-137">Сондай-ақ **Көрсеткіштер** қойыншасын таңдау арқылы бұрыннан бар көрсеткіштен деректер атрибутын таңдауға болады. Болмаса, нысанды немесе көрсеткіш атауын іздей аласыз.</span><span class="sxs-lookup"><span data-stu-id="192ad-137">You can also select a data attribute from an existing measure by selecting the **Measures** tab. Or, you can search for an entity or measure name.</span></span> 
   1. <span data-ttu-id="192ad-138">Таңдалған атрибутты көрсеткішке қосу үшін **Қосу** пәрменін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="192ad-138">Select **Add** to add the selected attribute to the measure.</span></span>

   :::image type="content" source="media/measure-attribute-selection.png" alt-text="Есептеулерде пайдаланылатын атрибутты таңдаңыз.":::

1. <span data-ttu-id="192ad-140">Неғұрлым күрделі көрсеткіштерді құру үшін көрсеткіш функциясында қосымша атрибуттар қосуға немесе математикалық операторларды пайдалануға болады.</span><span class="sxs-lookup"><span data-stu-id="192ad-140">To build more complex measures, you can add more attributes or use math operators on your measure function.</span></span>

   :::image type="content" source="media/measure-math-operators.png" alt-text="Математикалық операторлармен күрделі көрсеткіш құрыңыз.":::

1. <span data-ttu-id="192ad-142">Сүзгілерді қосу үшін конфигурация аймағында **Сүзгі** түймешігін басыңыз.</span><span class="sxs-lookup"><span data-stu-id="192ad-142">To add filters, select the **Filter** in the configuration area.</span></span> 
  
   1. <span data-ttu-id="192ad-143">**Сүзгілер** тақтасының **Атрибут қосу** бөлімінде сүзгілер жасау үшін пайдаланылатын атрибутты таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="192ad-143">In **Add attribute** section of the **Filters** pane, select the attribute you want to use to create filters.</span></span>
   1. <span data-ttu-id="192ad-144">Әр таңдалған атрибутқа арналған сүзгіні анықтау үшін сүзгі операторларын орнатыңыз.</span><span class="sxs-lookup"><span data-stu-id="192ad-144">Set the filter operators to define the filter for every selected attribute.</span></span>
   1. <span data-ttu-id="192ad-145">Сүзгілерді көрсеткішке қосу үшін **Қолдану** пәрменін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="192ad-145">Select **Apply** to add the filters to the measure.</span></span>

1. <span data-ttu-id="192ad-146">Өлшемдерді қосу үшін конфигурация аймағында **Өлшем** түймешігін басыңыз.</span><span class="sxs-lookup"><span data-stu-id="192ad-146">To add dimensions, select **Dimension** in the configuration area.</span></span> <span data-ttu-id="192ad-147">Өлшемдер көрсеткіштің шығыс нысанында бағандар ретінде көрсетіледі.</span><span class="sxs-lookup"><span data-stu-id="192ad-147">Dimensions will show as columns in the measure output entity.</span></span>
   1. <span data-ttu-id="192ad-148">Көрсеткіш мәндері бойынша топтастыру керек деректер атрибуттарын қосу үшін **Өлшемдерді өңдеу** пәрменін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="192ad-148">Select **Edit dimensions** to add data attributes you want to group the measure values by.</span></span> <span data-ttu-id="192ad-149">Мысалы, қала немесе жыныс.</span><span class="sxs-lookup"><span data-stu-id="192ad-149">For example, city or gender.</span></span> <span data-ttu-id="192ad-150">Әдепкі бойынша *тұтынушы деңгейіндегі көрсеткіштер* жасау үшін *Тұтынушы идентификаторы* өлшемі таңдалады.</span><span class="sxs-lookup"><span data-stu-id="192ad-150">By default, the *CustomerID* dimension is selected to create *customer-level measures*.</span></span> <span data-ttu-id="192ad-151">*Бизнес деңгейіндегі көрсеткіштер* жасау керек болса, әдепкі өлшемді алып тастауға болады.</span><span class="sxs-lookup"><span data-stu-id="192ad-151">You can remove the default dimension if you want to create *business-level measures*.</span></span>
   1. <span data-ttu-id="192ad-152">Өлшемдерді көрсеткішке қосу үшін **Дайын** пәрменін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="192ad-152">Select **Done** to add the dimensions to the measure.</span></span>

1. <span data-ttu-id="192ad-153">Егер сіздің деректеріңізде бүтін санмен ауыстыру қажет мәндер болса, мысалы, *нөл* мәнін *0* санымен ауыстыру, **Ережелер** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="192ad-153">If there are values in your data that you need to replace with an integer, for example, replace *null* with *0*, select **Rules**.</span></span> <span data-ttu-id="192ad-154">Ережені конфигурациялап, ауыстыру ретінде тек бүтін сандарды таңдағаныңызға көз жеткізіңіз.</span><span class="sxs-lookup"><span data-stu-id="192ad-154">Configure the rule and make sure that you choose only whole numbers as replacements.</span></span>

1. <span data-ttu-id="192ad-155">Егер салыстырған деректер нысаны мен *Тұтынушы* нысаны арасында бірнеше жол болса, онда анықталған [нысан қатынасы жолдарының](relationships.md) бірін таңдау қажет.</span><span class="sxs-lookup"><span data-stu-id="192ad-155">If there are multiple paths between the data entity you mapped and the *Customer* entity, you have to choose one of the identified [entity relationship paths](relationships.md).</span></span> <span data-ttu-id="192ad-156">Көрсеткіш нәтижелері таңдалған жолға байланысты өзгеруі мүмкін.</span><span class="sxs-lookup"><span data-stu-id="192ad-156">Measure results can vary depending on the selected path.</span></span> 
   1. <span data-ttu-id="192ad-157">**Деректер параметрлері** қойыншасын таңдап, көрсеткішті анықтау үшін пайдаланылатын нысан жолын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="192ad-157">Select **Data preferences** and choose the entity path that should be used to identify your measure.</span></span> <span data-ttu-id="192ad-158">Егер *Тұтынушы* нысанына тек бір жолда болса, бұл басқару элементі көрсетілмейді.</span><span class="sxs-lookup"><span data-stu-id="192ad-158">If there's only a single path to the *Customer* entity, this control won't show.</span></span>
   1. <span data-ttu-id="192ad-159">Таңдауыңызды қолдану үшін **Дайын** пәрменін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="192ad-159">Select **Done** to apply your selection.</span></span> 

   :::image type="content" source="media/measures-data-preferences.png" alt-text="Көрсеткіштің нысан жолын таңдаңыз.":::

1. <span data-ttu-id="192ad-161">Көрсеткіштерге қосымша есептеулер қосу үшін **Жаңа есептеу** пәрменін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="192ad-161">To add more calculations for the measure, select **New calculation**.</span></span> <span data-ttu-id="192ad-162">Жаңа есептеулер үшін сол нысан жолындағы нысандарды ғана пайдалана аласыз.</span><span class="sxs-lookup"><span data-stu-id="192ad-162">You can only use entities on the same entity path for new calculations.</span></span> <span data-ttu-id="192ad-163">Қосымша есептеулер көрсеткіштің шығыс нысанында жаңа бағандар ретінде көрсетіледі.</span><span class="sxs-lookup"><span data-stu-id="192ad-163">More calculations will show as new columns in the measure output entity.</span></span>

1. <span data-ttu-id="192ad-164">Көрсеткіштен есептеуді **Көшіру**, **Атын өзгерту** немесе **Жою** үшін есептеуде **...** таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="192ad-164">Select **...** on the calculation to **Duplicate**, **Rename**, or **Remove** a calculation from a measure.</span></span>

1. <span data-ttu-id="192ad-165">**Алдын ала қарау нұсқасы** аймағында сүзгілер мен өлшемдерді қоса, көрсеткіштің шығыс нысанының деректер схемасын көресіз.</span><span class="sxs-lookup"><span data-stu-id="192ad-165">In the **Preview** area, you'll see the data schema of the measure output entity, including filters and dimensions.</span></span> <span data-ttu-id="192ad-166">Алдын ала қарау нұсқасы конфигурацияның өзгеруіне динамикалық түрде әсер етеді.</span><span class="sxs-lookup"><span data-stu-id="192ad-166">The preview reacts dynamically to changes in the configuration.</span></span>

1. <span data-ttu-id="192ad-167">Конфигурацияланған көрсеткіш бойынша нәтижелерді есептеу үшін **Іске қосу** пәрменін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="192ad-167">Select **Run** to calculate results for the configured measure.</span></span> <span data-ttu-id="192ad-168">Ағымдағы конфигурацияны сақтап, көрсеткішті кейінірек іске қосқыңыз келсе, **Сақтау және жабу** пәрменін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="192ad-168">Select **Save and close** if you want to keep the current configuration and run the measure later.</span></span>

1. <span data-ttu-id="192ad-169">Тізімдегі жаңадан жасалған көрсеткішті көру үшін **Көрсеткіштер** қойыншасына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="192ad-169">Go to **Measures** to see the newly created measure in the list.</span></span>

## <a name="use-a-template-to-build-a-measure"></a><span data-ttu-id="192ad-170">Өлшемді жасау үшін үлгіні пайдалану</span><span class="sxs-lookup"><span data-stu-id="192ad-170">Use a template to build a measure</span></span>

<span data-ttu-id="192ad-171">Оларды жасау үшін жалпы қолданылатын өлшемдердің алдын ала анықталған үлгілерін пайдалануға болады.</span><span class="sxs-lookup"><span data-stu-id="192ad-171">You can use predefined templates of commonly used measures to create them.</span></span> <span data-ttu-id="192ad-172">Үлгілердің толық сипаттамасы және қадамдық тәжірибе сізге тиімді өлшем жасауға көмектеседі.</span><span class="sxs-lookup"><span data-stu-id="192ad-172">Detailed descriptions of the templates and a guided experience help you with efficient measure creation.</span></span> <span data-ttu-id="192ad-173">*Бірыңғай әрекет* нысанындағы салыстырылған деректерде жасалған үлгілер.</span><span class="sxs-lookup"><span data-stu-id="192ad-173">Templates build on mapped data from the *Unified Activity* entity.</span></span> <span data-ttu-id="192ad-174">Үлгіден өлшем жасамас бұрын, [тұтынушы әрекеттерін](activities.md) конфигурациялағаныңызға көз жеткізіңіз.</span><span class="sxs-lookup"><span data-stu-id="192ad-174">So make sure you have configured [customer activities](activities.md) before you create a measure from a template.</span></span>

<span data-ttu-id="192ad-175">Қолжетімді өлшем үлгілері:</span><span class="sxs-lookup"><span data-stu-id="192ad-175">Available measure templates:</span></span> 
- <span data-ttu-id="192ad-176">Орташа транзакция құны (ATV)</span><span class="sxs-lookup"><span data-stu-id="192ad-176">Average transaction value (ATV)</span></span>
- <span data-ttu-id="192ad-177">Жалпы транзакция құны</span><span class="sxs-lookup"><span data-stu-id="192ad-177">Total transaction value</span></span>
- <span data-ttu-id="192ad-178">Орташа күн сайынғы табыс</span><span class="sxs-lookup"><span data-stu-id="192ad-178">Average daily revenue</span></span>
- <span data-ttu-id="192ad-179">Орташа жыл сайынғы табыс</span><span class="sxs-lookup"><span data-stu-id="192ad-179">Average yearly revenue</span></span>
- <span data-ttu-id="192ad-180">Транзакциялар саны</span><span class="sxs-lookup"><span data-stu-id="192ad-180">Transaction count</span></span>
- <span data-ttu-id="192ad-181">Алынған адалдық ұпайлары</span><span class="sxs-lookup"><span data-stu-id="192ad-181">Loyalty points earned</span></span>
- <span data-ttu-id="192ad-182">Қолданылған адалдық ұпайлары</span><span class="sxs-lookup"><span data-stu-id="192ad-182">Loyalty points redeemed</span></span>
- <span data-ttu-id="192ad-183">Адалдық ұпайларының балансы</span><span class="sxs-lookup"><span data-stu-id="192ad-183">Loyalty points balance</span></span>
- <span data-ttu-id="192ad-184">Белсенді тұтынушының мерзімі</span><span class="sxs-lookup"><span data-stu-id="192ad-184">Active customer lifespan</span></span>
- <span data-ttu-id="192ad-185">Адалдық бағдарламасына мүшелік ұзақтығы</span><span class="sxs-lookup"><span data-stu-id="192ad-185">Loyalty membership duration</span></span>
- <span data-ttu-id="192ad-186">Соңғы сатып алудан бергі уақыт</span><span class="sxs-lookup"><span data-stu-id="192ad-186">Time since last purchase</span></span>

<span data-ttu-id="192ad-187">Келесі процедура үлгі көмегімен жаңа өлшем жасау қадамдарын көрсетеді.</span><span class="sxs-lookup"><span data-stu-id="192ad-187">The following procedure outlines the steps to build a new measure using a template.</span></span>

1. <span data-ttu-id="192ad-188">Аудитория мәліметтерінде **Өлшемдер** параметріне өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="192ad-188">In audience insights, go to **Measures**.</span></span>

1. <span data-ttu-id="192ad-189">**Жаңа** түймешігін және **Үлгі таңдау** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="192ad-189">Select **New** and select **Choose a template**.</span></span>

   :::image type="content" source="media/measure-use-template.png" alt-text="Үлгіде бөлектелген жаңа өлшемді жасау кезіндегі ашылмалы мәзірдің скриншоты.":::

1. <span data-ttu-id="192ad-191">Сіздің қажеттілігіңізге сәйкес үлгіні тауып, **Үлгі таңдау** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="192ad-191">Find the template that fits your need and select **Choose template**.</span></span>

1. <span data-ttu-id="192ad-192">Қажетті деректерді қарап шығыңыз және барлық деректер орнында болса **Жұмысты бастау** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="192ad-192">Review the required data and select **Get started** if you have all the data in place.</span></span>

1. <span data-ttu-id="192ad-193">**Атын өңдеу** панелінде өлшеміңіздің атын және шығыс нысанын орнатыңыз.</span><span class="sxs-lookup"><span data-stu-id="192ad-193">In the **Edit name** pane, set the name for your measure and the output entity.</span></span> 

1. <span data-ttu-id="192ad-194">**Дайын** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="192ad-194">Select **Done**.</span></span>

1. <span data-ttu-id="192ad-195">**Уақыт аралығын орнату** бөлімінде пайдаланылатын деректердің уақыт аралығын анықтаңыз.</span><span class="sxs-lookup"><span data-stu-id="192ad-195">In the **Set time period** section, define the time frame of the data to use.</span></span> <span data-ttu-id="192ad-196">Жаңа өлшемнің бүкіл деректер жиынтығын қамтығанын қаласаңыз **Барлық уақытта** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="192ad-196">Choose if you want the new measure to cover the entire data set by selecting **All time**.</span></span> <span data-ttu-id="192ad-197">Немесе өлшем **Нақты уақыт кезеңі** параметріне фокусталғанын қаласаңыз.</span><span class="sxs-lookup"><span data-stu-id="192ad-197">Or if you want the measure to focus on a **Specific time period**.</span></span>

   :::image type="content" source="media/measure-set-time-period.png" alt-text="Үлгідегі өлшемді конфигурациялау кезінде уақыт кезеңі бөлімін көрсететін скриншот.":::

1. <span data-ttu-id="192ad-199">Келесі бөлімде әрекеттерді таңдау үшін **Деректер қосу** түймешігін таңдаңыз және *Бірыңғай әрекет* нысанындағы тиісті деректерді салыстырыңыз.</span><span class="sxs-lookup"><span data-stu-id="192ad-199">In the next section, select **Add data** to choose the activities and map the corresponding data from your *Unified Activity* entity.</span></span>

    1. <span data-ttu-id="192ad-200">1/2-қадам: **Әрекет түрі** бөлімінде пайдалану керек нысан түрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="192ad-200">Step 1 of 2: Under **Activity type**, choose the type of the entity you want to use.</span></span> <span data-ttu-id="192ad-201">**Әрекеттер** бөлімі үшін салыстыру керек нысандарды таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="192ad-201">For **Activities**, select the entities you want to map.</span></span>
    1. <span data-ttu-id="192ad-202">2/2-қадам: формулаға қажет құрамдас үшін *Бірыңғай әрекет* нысанынан төлсипатты таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="192ad-202">Step 2 of 2: Choose the attribute from the *Unified Activity* entity for the component required by the formula.</span></span> <span data-ttu-id="192ad-203">Мысалы, транзакцияның орташа мәні үшін бұл транзакция мәнін білдіретін төлсипат.</span><span class="sxs-lookup"><span data-stu-id="192ad-203">For example, for Average transaction value, it's the attribute representing the Transaction value.</span></span> <span data-ttu-id="192ad-204">**Әрекеттің уақыт белгісі** бөлімінде әрекеттің күні мен уақытын білдіретін бірыңғай қызмет нысанынан төлсипатты таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="192ad-204">For **Activity timestamp**, choose the attribute from the Unified Activity entity that represents the date and time of the activity.</span></span>
   
1. <span data-ttu-id="192ad-205">Деректерді салыстыру сәтті аяқталғаннан кейін, сіз **Аяқталды** күйін және салыстырылған әрекеттер мен төлсипаттардың атауын көресіз.</span><span class="sxs-lookup"><span data-stu-id="192ad-205">Once the data mapping is successful, you can see the status as **Complete** and the name of the mapped activities and attributes.</span></span>

   :::image type="content" source="media/measure-template-configured.png" alt-text="Аяқталған өлшем үлгісі конфигурациясының скриншоты.":::

1. <span data-ttu-id="192ad-207">Енді өлшем нәтижелерін есептеу үшін **Іске қосу** түймешігін таңдауға болады.</span><span class="sxs-lookup"><span data-stu-id="192ad-207">You can now select **Run** to calculate the results of the measure.</span></span> <span data-ttu-id="192ad-208">Оны кейінірек нақтылау үшін **Жобаны сақтау** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="192ad-208">To refine it later, select **Save draft**.</span></span>

## <a name="manage-your-measures"></a><span data-ttu-id="192ad-209">Көрсеткіштерді басқару</span><span class="sxs-lookup"><span data-stu-id="192ad-209">Manage your measures</span></span>

<span data-ttu-id="192ad-210">Өлшемдердің тізімін **Өлшемдер** бетінен табуға болады.</span><span class="sxs-lookup"><span data-stu-id="192ad-210">You can find the list of measures on the **Measures** page.</span></span>

<span data-ttu-id="192ad-211">Көрсеткіш түрі, жасаушы, жасалған күні, күйі және жағдайы туралы ақпаратты таба аласыз.</span><span class="sxs-lookup"><span data-stu-id="192ad-211">You'll find information about the measure type, the creator, creation date, status, and state.</span></span> <span data-ttu-id="192ad-212">Тізімнен көрсеткішті таңдағанда, нәтижені алдын ала қарап, .CSV файлын жүктеп ала аласыз.</span><span class="sxs-lookup"><span data-stu-id="192ad-212">When you select a measure from the list, you can preview the output and download a .CSV file.</span></span>

<span data-ttu-id="192ad-213">Барлық көрсеткішті бір уақытта жаңарту үшін, нақты көрсеткішті таңдамай **Барлығын жаңарту** опциясын басыңыз.</span><span class="sxs-lookup"><span data-stu-id="192ad-213">To refresh all of your measures at the same time, select **Refresh all** without selecting a specific measure.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="192ad-214">![Бір көрсеткішті басқару әрекеттері](media/measure-actions.png "Бір көрсеткішті басқару әрекеттері")</span><span class="sxs-lookup"><span data-stu-id="192ad-214">![Actions to manage single measures](media/measure-actions.png "Actions to manage single measures")</span></span>

<span data-ttu-id="192ad-215">Төмендегі параметрлер үшін тізімнен көрсеткішті таңдаңыз:</span><span class="sxs-lookup"><span data-stu-id="192ad-215">Select a measure from the list for the following options:</span></span>

- <span data-ttu-id="192ad-216">Мәліметтерді көру үшін көрсеткіш атауын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="192ad-216">Select the measure name to see its details.</span></span>
- <span data-ttu-id="192ad-217">Көрсеткіш конфигурациясын **өңдеңіз**.</span><span class="sxs-lookup"><span data-stu-id="192ad-217">**Edit** the configuration of the measure.</span></span>
- <span data-ttu-id="192ad-218">Соңғы деректерге негізделген көрсеткішті жаңарту үшін **Жаңарту** түймешігін басыңыз.</span><span class="sxs-lookup"><span data-stu-id="192ad-218">**Refresh** the measure based on the latest data.</span></span>
- <span data-ttu-id="192ad-219">Көрсеткіш **атауын өзгертіңіз**.</span><span class="sxs-lookup"><span data-stu-id="192ad-219">**Rename** the measure.</span></span>
- <span data-ttu-id="192ad-220">Көрсеткішті **жойыңыз**.</span><span class="sxs-lookup"><span data-stu-id="192ad-220">**Delete** the measure.</span></span>
- <span data-ttu-id="192ad-221">**Белсендіру** немесе **Ажырату** түймешігін басыңыз.</span><span class="sxs-lookup"><span data-stu-id="192ad-221">**Activate** or **Deactivate**.</span></span> <span data-ttu-id="192ad-222">Белсенді емес көрсеткіштер [жоспарланған жаңарту](system.md#schedule-tab) барысында жаңартылмайды.</span><span class="sxs-lookup"><span data-stu-id="192ad-222">Inactive measures won't get refreshed during a [scheduled refresh](system.md#schedule-tab).</span></span>

> [!TIP]
> <span data-ttu-id="192ad-223">Тапсырмалар/процестерге арналған [күйдің алты түрі](system.md#status-types) бар.</span><span class="sxs-lookup"><span data-stu-id="192ad-223">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="192ad-224">Сонымен қатар көптеген процестер [басқа кезектегі процестерге тәуелді](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="192ad-224">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="192ad-225">Бүкіл тапсырманың барысы туралы мәліметтерді көру үшін процестің күйін таңдай аласыз.</span><span class="sxs-lookup"><span data-stu-id="192ad-225">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="192ad-226">Бір жұмыс тапсырмаларының бірі үшін **Мәліметтерді көру** параметрін таңдағаннан кейін, қосымша ақпаратты көруге болады: өңдеу уақыты, соңғы өңделген күні және тапсырмаға қатысты барлық қателер мен ескертулер.</span><span class="sxs-lookup"><span data-stu-id="192ad-226">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="192ad-227">Келесі қадам</span><span class="sxs-lookup"><span data-stu-id="192ad-227">Next step</span></span>

<span data-ttu-id="192ad-228">[Тұтынушы сегментін](segments.md) жасау үшін бұрыннан бар көрсеткіштерді пайдалануға болады.</span><span class="sxs-lookup"><span data-stu-id="192ad-228">You cam use existing measures to create [a customer segment](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
