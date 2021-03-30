---
title: Көрсеткіштер құру және басқару
description: Бизнесіңіздің өнімділігін талдау және көрсету үшін көрсеткіштерді анықтаңыз.
ms.date: 02/02/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wameng
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 202ea22d290be04e54ce9676b6b693162354607f
ms.sourcegitcommit: d3eb07dcc72624a2d5cfc95c7ea9faaa2c1b6001
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 03/16/2021
ms.locfileid: "5654739"
---
# <a name="define-and-manage-measures"></a><span data-ttu-id="e91b5-103">Көрсеткіштерді анықтау және басқару</span><span class="sxs-lookup"><span data-stu-id="e91b5-103">Define and manage measures</span></span>

<span data-ttu-id="e91b5-104">Көрсеткіштер [бірыңғай профильдерден](data-unification.md) тиісті құндылықтарды алу арқылы тұтынушы әрекеттері мен бизнес жүргізу өнімділігін жақсы түсінуге көмектеседі.</span><span class="sxs-lookup"><span data-stu-id="e91b5-104">Measures help you to better understand customer behaviors and business performance by retrieving relevant values from [unified profiles](data-unification.md).</span></span> <span data-ttu-id="e91b5-105">Мысалы, бизнес жеке тұтынушының сатып алу тарихын түсіну үшін *әр тұтынушыға шаққандағы жалпы шығын* көрсеткішін көргісі келеді.</span><span class="sxs-lookup"><span data-stu-id="e91b5-105">For example, a business wants to see the *total spend per customer* to understand individual customer’s purchase history.</span></span> <span data-ttu-id="e91b5-106">Болмаса, бүкіл бизнестегі табыстың жиынтық деңгейін түсіну үшін *компанияның жалпы сатылымы* көрсеткішін көргісі келеді.</span><span class="sxs-lookup"><span data-stu-id="e91b5-106">Or measure *total sales of the company* to understand the aggregate-level revenue in the whole business.</span></span>  

<span data-ttu-id="e91b5-107">Көрсеткіштер көрсеткіш құрастырушы, әртүрлі операторлары бар деректерді сұрау платформасы және қарапайым салыстыру опциялары арқылы жасалады.</span><span class="sxs-lookup"><span data-stu-id="e91b5-107">Measures are created using the measure builder, a data query platform with various operators and simple mapping options.</span></span> <span data-ttu-id="e91b5-108">Ол сізге деректерді сүзгілеуге, нәтижелерді топтастыруға, [нысандар қатынасы жолдарын](relationships.md) анықтауға және нәтижені алдын ала қарауға мүмкіндік береді.</span><span class="sxs-lookup"><span data-stu-id="e91b5-108">It lets you filter the data, group results, detect [entity relationship paths](relationships.md), and preview the output.</span></span>

<span data-ttu-id="e91b5-109">Тұтыну деректерін сұрау және түсініктерді шығару арқылы бизнес әрекеттерді жоспарлау үшін көрсеткіш құрастырушысын пайдаланыңыз.</span><span class="sxs-lookup"><span data-stu-id="e91b5-109">Use the measure builder to plan business activities by querying customer data and extract insights.</span></span> <span data-ttu-id="e91b5-110">Мысалы, *әр тұтынушыға шаққандағы жалпы шығын* және *әр тұтынушының жалпы кірісі* көрсеткішін жасау шығыны мен кірісі де жоғары тұтынушылар тобын анықтауға көмектеседі.</span><span class="sxs-lookup"><span data-stu-id="e91b5-110">For example, creating a measure of *total spend per customer* and *total return per customer* helps identify a group of customers with high spend yet high return.</span></span> <span data-ttu-id="e91b5-111">Келесі ең жақсы әрекеттерді жүргізу үшін [сегмент құруға](segments.md) болады.</span><span class="sxs-lookup"><span data-stu-id="e91b5-111">You can [create a segment](segments.md) to drive next best actions.</span></span> 

## <a name="create-a-measure"></a><span data-ttu-id="e91b5-112">Шараны жасау</span><span class="sxs-lookup"><span data-stu-id="e91b5-112">Create a measure</span></span>

<span data-ttu-id="e91b5-113">Бұл бөлімде жаңа көрсеткішті нөлден бастап жасау жолын үйренесіз.</span><span class="sxs-lookup"><span data-stu-id="e91b5-113">This section walks you through creating a new measure from scratch.</span></span> <span data-ttu-id="e91b5-114">Тұтынушы нысанымен қосылатын қарым-қатынас орнатылған деректер нысандарының деректер атрибуттарымен көрсеткіш құруға болады.</span><span class="sxs-lookup"><span data-stu-id="e91b5-114">You can build a measure with data attributes from data entities that have a relationship set up to connect with the Customer entity.</span></span> 

1. <span data-ttu-id="e91b5-115">Аудитория мәліметтерінде **Өлшемдер** параметріне өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="e91b5-115">In audience insights, go to **Measures**.</span></span>

1. <span data-ttu-id="e91b5-116">**Жаңа** пәрменін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="e91b5-116">Select **New**.</span></span>

1. <span data-ttu-id="e91b5-117">**Атын өзгерту** пәрменін таңдап, көрсеткішке **Атау** беріңіз.</span><span class="sxs-lookup"><span data-stu-id="e91b5-117">Select **Edit name** and provide a **Name** for the measure.</span></span> 
   > [!NOTE]
   > <span data-ttu-id="e91b5-118">Егер жаңа көрсеткіш конфигурацияңызда тек екі өріс болса, мысалы, тұтынушы идентификаторы және бір есептеу болса, нәтиже жүйе жасаған Customer_Measure нысанына жаңа баған ретінде қосылады.</span><span class="sxs-lookup"><span data-stu-id="e91b5-118">If your new measure configuration has only two fields, for exmample, CustomerID and one calculation, the output will be added as a new column to the system generated entity called Customer_Measure.</span></span> <span data-ttu-id="e91b5-119">Көрсеткіш мәнін тұтынушының бірыңғай профилінен көре аласыз.</span><span class="sxs-lookup"><span data-stu-id="e91b5-119">And you will be able to see the measure’s value in the unified customer profile.</span></span> <span data-ttu-id="e91b5-120">Басқа көрсеткіштер өз нысандарын тудырады.</span><span class="sxs-lookup"><span data-stu-id="e91b5-120">Other measures will generate their own entities.</span></span>

1. <span data-ttu-id="e91b5-121">Конфигурация аймағында, **Функцияны таңдау** ашылмалы мәзірінен жиынтық функцияны таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="e91b5-121">In the configuration area, choose the aggregation function from the **Select Function** drop-down menu.</span></span> <span data-ttu-id="e91b5-122">Жиынтық функцияларға мыналар кіреді:</span><span class="sxs-lookup"><span data-stu-id="e91b5-122">Aggregation functions include:</span></span> 
   - <span data-ttu-id="e91b5-123">**Sum**</span><span class="sxs-lookup"><span data-stu-id="e91b5-123">**Sum**</span></span>
   - <span data-ttu-id="e91b5-124">**Орта есеппен**</span><span class="sxs-lookup"><span data-stu-id="e91b5-124">**Average**</span></span>
   - <span data-ttu-id="e91b5-125">**Саны**</span><span class="sxs-lookup"><span data-stu-id="e91b5-125">**Count**</span></span>
   - <span data-ttu-id="e91b5-126">**Бірегейді санау**</span><span class="sxs-lookup"><span data-stu-id="e91b5-126">**Count Unique**</span></span>
   - <span data-ttu-id="e91b5-127">**Ең көп**</span><span class="sxs-lookup"><span data-stu-id="e91b5-127">**Max**</span></span>
   - <span data-ttu-id="e91b5-128">**Min**</span><span class="sxs-lookup"><span data-stu-id="e91b5-128">**Min**</span></span>
   - <span data-ttu-id="e91b5-129">**Бірінші**: деректер жазбасының бірінші мәнін алады</span><span class="sxs-lookup"><span data-stu-id="e91b5-129">**First**: takes the first value of the data record</span></span>
   - <span data-ttu-id="e91b5-130">**Соңғы**: деректер жазбасына қосылған соңғы мәнді алады</span><span class="sxs-lookup"><span data-stu-id="e91b5-130">**Last**: takes the last value that was added to the data record</span></span>

   :::image type="content" source="media/measure-operators.png" alt-text="Көрсеткіш есептеулеріне арналған операторлар.":::

1. <span data-ttu-id="e91b5-132">Осы көрсеткішті құруға қажет деректерді таңдау үшін **Атрибут қосу** пәрменін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="e91b5-132">Select **Add attribute** to select the data you need to create this measure.</span></span>
   
   1. <span data-ttu-id="e91b5-133">**Атрибуттар** қойыншасын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="e91b5-133">Select the **Attributes** tab.</span></span> 
   1. <span data-ttu-id="e91b5-134">Деректер нысаны: өлшеу керек атрибутты қамтитын нысанды таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="e91b5-134">Data entity: Choose the entity that includes the attribute you want to measure.</span></span> 
   1. <span data-ttu-id="e91b5-135">Деректер атрибуты: көрсеткішті есептеу үшін жиынтық функцияда пайдаланылатын атрибутты таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="e91b5-135">Data attribute: Choose the attribute you want to use in the aggregation function to calculate the measure.</span></span> <span data-ttu-id="e91b5-136">Бір уақытта тек бір атрибутты таңдауға болады.</span><span class="sxs-lookup"><span data-stu-id="e91b5-136">You can only select one attribute at a time.</span></span>
   1. <span data-ttu-id="e91b5-137">Сондай-ақ **Көрсеткіштер** қойыншасын таңдау арқылы бұрыннан бар көрсеткіштен деректер атрибутын таңдауға болады. Болмаса, нысанды немесе көрсеткіш атауын іздей аласыз.</span><span class="sxs-lookup"><span data-stu-id="e91b5-137">You can also select a data attribute from an existing measure by selecting the **Measures** tab. Or, you can search for an entity or measure name.</span></span> 
   1. <span data-ttu-id="e91b5-138">Таңдалған атрибутты көрсеткішке қосу үшін **Қосу** пәрменін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="e91b5-138">Select **Add** to add the selected attribute to the measure.</span></span>

   :::image type="content" source="media/measure-attribute-selection.png" alt-text="Есептеулерде пайдаланылатын атрибутты таңдаңыз.":::

1. <span data-ttu-id="e91b5-140">Неғұрлым күрделі көрсеткіштерді құру үшін көрсеткіш функциясында қосымша атрибуттар қосуға немесе математикалық операторларды пайдалануға болады.</span><span class="sxs-lookup"><span data-stu-id="e91b5-140">To build more complex measures, you can add more attributes or use math operators on your measure function.</span></span>

   :::image type="content" source="media/measure-math-operators.png" alt-text="Математикалық операторлармен күрделі көрсеткіш құрыңыз.":::

1. <span data-ttu-id="e91b5-142">Сүзгілерді қосу үшін конфигурация аймағында **Сүзгі** түймешігін басыңыз.</span><span class="sxs-lookup"><span data-stu-id="e91b5-142">To add filters, select the **Filter** in the configuration area.</span></span> 
  
   1. <span data-ttu-id="e91b5-143">**Сүзгілер** тақтасының **Атрибут қосу** бөлімінде сүзгілер жасау үшін пайдаланылатын атрибутты таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="e91b5-143">In **Add attribute** section of the **Filters** pane, select the attribute you want to use to create filters.</span></span>
   1. <span data-ttu-id="e91b5-144">Әр таңдалған атрибутқа арналған сүзгіні анықтау үшін сүзгі операторларын орнатыңыз.</span><span class="sxs-lookup"><span data-stu-id="e91b5-144">Set the filter operators to define the filter for every selected attribute.</span></span>
   1. <span data-ttu-id="e91b5-145">Сүзгілерді көрсеткішке қосу үшін **Қолдану** пәрменін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="e91b5-145">Select **Apply** to add the filters to the measure.</span></span>

1. <span data-ttu-id="e91b5-146">Өлшемдерді қосу үшін конфигурация аймағында **Өлшем** түймешігін басыңыз.</span><span class="sxs-lookup"><span data-stu-id="e91b5-146">To add dimensions, select **Dimension** in the configuration area.</span></span> <span data-ttu-id="e91b5-147">Өлшемдер көрсеткіштің шығыс нысанында бағандар ретінде көрсетіледі.</span><span class="sxs-lookup"><span data-stu-id="e91b5-147">Dimensions will show as columns in the measure output entity.</span></span>
   1. <span data-ttu-id="e91b5-148">Көрсеткіш мәндері бойынша топтастыру керек деректер атрибуттарын қосу үшін **Өлшемдерді өңдеу** пәрменін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="e91b5-148">Select **Edit dimensions** to add data attributes you want to group the measure values by.</span></span> <span data-ttu-id="e91b5-149">Мысалы, қала немесе жыныс.</span><span class="sxs-lookup"><span data-stu-id="e91b5-149">For example, city or gender.</span></span> <span data-ttu-id="e91b5-150">Әдепкі бойынша *тұтынушы деңгейіндегі көрсеткіштер* жасау үшін *Тұтынушы идентификаторы* өлшемі таңдалады.</span><span class="sxs-lookup"><span data-stu-id="e91b5-150">By default, the *CustomerID* dimension is selected to create *customer-level measures*.</span></span> <span data-ttu-id="e91b5-151">*Бизнес деңгейіндегі көрсеткіштер* жасау керек болса, әдепкі өлшемді алып тастауға болады.</span><span class="sxs-lookup"><span data-stu-id="e91b5-151">You can remove the default dimension if you want to create *business-level measures*.</span></span>
   1. <span data-ttu-id="e91b5-152">Өлшемдерді көрсеткішке қосу үшін **Дайын** пәрменін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="e91b5-152">Select **Done** to add the dimensions to the measure.</span></span>

1. <span data-ttu-id="e91b5-153">Егер салыстырған деректер нысаны мен *Тұтынушы* нысаны арасында бірнеше жол болса, онда анықталған [нысан қатынасы жолдарының](relationships.md) бірін таңдау қажет.</span><span class="sxs-lookup"><span data-stu-id="e91b5-153">If there are multiple paths between the data entity you mapped and the *Customer* entity, you have to choose one of the identified [entity relationship paths](relationships.md).</span></span> <span data-ttu-id="e91b5-154">Көрсеткіш нәтижелері таңдалған жолға байланысты өзгеруі мүмкін.</span><span class="sxs-lookup"><span data-stu-id="e91b5-154">Measure results can vary depending on the selected path.</span></span> 
   1. <span data-ttu-id="e91b5-155">**Деректер параметрлері** қойыншасын таңдап, көрсеткішті анықтау үшін пайдаланылатын нысан жолын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="e91b5-155">Select **Data preferences** and choose the entity path that should be used to identify your measure.</span></span> <span data-ttu-id="e91b5-156">Егер *Тұтынушы* нысанына тек бір жолда болса, бұл басқару элементі көрсетілмейді.</span><span class="sxs-lookup"><span data-stu-id="e91b5-156">If there's only a single path to the *Customer* entity, this control won't show.</span></span>
   1. <span data-ttu-id="e91b5-157">Таңдауыңызды қолдану үшін **Дайын** пәрменін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="e91b5-157">Select **Done** to apply your selection.</span></span> 

   :::image type="content" source="media/measures-data-preferences.png" alt-text="Көрсеткіштің нысан жолын таңдаңыз.":::

1. <span data-ttu-id="e91b5-159">Көрсеткіштерге қосымша есептеулер қосу үшін **Жаңа есептеу** пәрменін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="e91b5-159">To add more calculations for the measure, select **New calculation**.</span></span> <span data-ttu-id="e91b5-160">Жаңа есептеулер үшін сол нысан жолындағы нысандарды ғана пайдалана аласыз.</span><span class="sxs-lookup"><span data-stu-id="e91b5-160">You can only use entities on the same entity path for new calculations.</span></span> <span data-ttu-id="e91b5-161">Қосымша есептеулер көрсеткіштің шығыс нысанында жаңа бағандар ретінде көрсетіледі.</span><span class="sxs-lookup"><span data-stu-id="e91b5-161">More calculations will show as new columns in the measure output entity.</span></span>

1. <span data-ttu-id="e91b5-162">Көрсеткіштен есептеуді **Көшіру**, **Атын өзгерту** немесе **Жою** үшін есептеуде **...** таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="e91b5-162">Select **...** on the calculation to **Duplicate**, **Rename**, or **Remove** a calculation from a measure.</span></span>

1. <span data-ttu-id="e91b5-163">**Алдын ала қарау нұсқасы** аймағында сүзгілер мен өлшемдерді қоса, көрсеткіштің шығыс нысанының деректер схемасын көресіз.</span><span class="sxs-lookup"><span data-stu-id="e91b5-163">In the **Preview** area, you'll see the data schema of the measure output entity, including filters and dimensions.</span></span> <span data-ttu-id="e91b5-164">Алдын ала қарау нұсқасы конфигурацияның өзгеруіне динамикалық түрде әсер етеді.</span><span class="sxs-lookup"><span data-stu-id="e91b5-164">The preview reacts dynamically to changes in the configuration.</span></span>

1. <span data-ttu-id="e91b5-165">Конфигурацияланған көрсеткіш бойынша нәтижелерді есептеу үшін **Іске қосу** пәрменін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="e91b5-165">Select **Run** to calculate results for the configured measure.</span></span> <span data-ttu-id="e91b5-166">Ағымдағы конфигурацияны сақтап, көрсеткішті кейінірек іске қосқыңыз келсе, **Сақтау және жабу** пәрменін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="e91b5-166">Select **Save and close** if you want to keep the current configuration and run the measure later.</span></span>

1. <span data-ttu-id="e91b5-167">Тізімдегі жаңадан жасалған көрсеткішті көру үшін **Көрсеткіштер** қойыншасына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="e91b5-167">Go to **Measures** to see the newly created measure in the list.</span></span>

## <a name="manage-your-measures"></a><span data-ttu-id="e91b5-168">Көрсеткіштерді басқару</span><span class="sxs-lookup"><span data-stu-id="e91b5-168">Manage your measures</span></span>

<span data-ttu-id="e91b5-169">[Көрсеткішті жасағаннан](#create-a-measure) кейін, көрсеткіштер тізімін **Көрсеткіштер** бетінен көресіз.</span><span class="sxs-lookup"><span data-stu-id="e91b5-169">After [creating a measure](#create-a-measure), you see a list of measures on the **Measures** page.</span></span>

<span data-ttu-id="e91b5-170">Көрсеткіш түрі, жасаушы, жасалған күні, күйі және жағдайы туралы ақпаратты таба аласыз.</span><span class="sxs-lookup"><span data-stu-id="e91b5-170">You'll find information about the measure type, the creator, creation date, status, and state.</span></span> <span data-ttu-id="e91b5-171">Тізімнен көрсеткішті таңдағанда, нәтижені алдын-ала қарап, .CSV файлын жүктеп ала аласыз.</span><span class="sxs-lookup"><span data-stu-id="e91b5-171">When you select a measure from the list, you can preview the output and download a .CSV file.</span></span>

<span data-ttu-id="e91b5-172">Барлық көрсеткішті бір уақытта жаңарту үшін, нақты көрсеткішті таңдамай **Барлығын жаңарту** опциясын басыңыз.</span><span class="sxs-lookup"><span data-stu-id="e91b5-172">To refresh all of your measures at the same time, select **Refresh all** without selecting a specific measure.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="e91b5-173">![Бір көрсеткішті басқару әрекеттері](media/measure-actions.png "Бір көрсеткішті басқару әрекеттері")</span><span class="sxs-lookup"><span data-stu-id="e91b5-173">![Actions to manage single measures](media/measure-actions.png "Actions to manage single measures")</span></span>

<span data-ttu-id="e91b5-174">Төмендегі параметрлер үшін тізімнен көрсеткішті таңдаңыз:</span><span class="sxs-lookup"><span data-stu-id="e91b5-174">Select a measure from the list for the following options:</span></span>

- <span data-ttu-id="e91b5-175">Мәліметтерді көру үшін көрсеткіш атауын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="e91b5-175">Select the measure name to see its details.</span></span>
- <span data-ttu-id="e91b5-176">Көрсеткіш конфигурациясын **өңдеңіз**.</span><span class="sxs-lookup"><span data-stu-id="e91b5-176">**Edit** the configuration of the measure.</span></span>
- <span data-ttu-id="e91b5-177">Соңғы деректерге негізделген көрсеткішті жаңарту үшін **Жаңарту** түймешігін басыңыз.</span><span class="sxs-lookup"><span data-stu-id="e91b5-177">**Refresh** the measure based on the latest data.</span></span>
- <span data-ttu-id="e91b5-178">Көрсеткіш **атауын өзгертіңіз**.</span><span class="sxs-lookup"><span data-stu-id="e91b5-178">**Rename** the measure.</span></span>
- <span data-ttu-id="e91b5-179">Көрсеткішті **жойыңыз**.</span><span class="sxs-lookup"><span data-stu-id="e91b5-179">**Delete** the measure.</span></span>
- <span data-ttu-id="e91b5-180">**Белсендіру** немесе **Ажырату** түймешігін басыңыз.</span><span class="sxs-lookup"><span data-stu-id="e91b5-180">**Activate** or **Deactivate**.</span></span> <span data-ttu-id="e91b5-181">Белсенді емес көрсеткіштер [жоспарланған жаңарту](system.md#schedule-tab) барысында жаңартылмайды.</span><span class="sxs-lookup"><span data-stu-id="e91b5-181">Inactive measures won't get refreshed during a [scheduled refresh](system.md#schedule-tab).</span></span>

> [!TIP]
> <span data-ttu-id="e91b5-182">Тапсырмалар/процестерге арналған [күйдің алты түрі](system.md#status-types) бар.</span><span class="sxs-lookup"><span data-stu-id="e91b5-182">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="e91b5-183">Сонымен қатар, көптеген процестер [басқа кезектегі процестерге тәуелді](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="e91b5-183">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="e91b5-184">Бүкіл тапсырманың барысы туралы мәліметтерді көру үшін процестің күйін таңдай аласыз.</span><span class="sxs-lookup"><span data-stu-id="e91b5-184">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="e91b5-185">Бір жұмыс тапсырмаларының бірі үшін **Мәліметтерді көру** параметрін таңдағаннан кейін, қосымша ақпаратты көруге болады: өңдеу уақыты, соңғы өңделген күні және тапсырмаға қатысты барлық қателер мен ескертулер.</span><span class="sxs-lookup"><span data-stu-id="e91b5-185">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="e91b5-186">Келесі қадам</span><span class="sxs-lookup"><span data-stu-id="e91b5-186">Next step</span></span>

<span data-ttu-id="e91b5-187">[Тұтынушы сегментін](segments.md) жасау үшін бұрыннан бар көрсеткіштерді пайдалануға болады.</span><span class="sxs-lookup"><span data-stu-id="e91b5-187">You cam use existing measures to create [a customer segment](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]