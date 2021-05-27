---
title: Әрекетке негізделген ұсынылған сегменттер.
description: Компьютерлік оқыту мүмкіндігіне сізге тұтынушы әрекетіне негізделген жаңа және қызықты сегменттерді табуға көмектесуіне мүмкіндік беріңіз.
ms.date: 05/11/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
manager: shellyha
ms.openlocfilehash: 14d9d4f0df6b5835f21fb63447d05853ee98a757
ms.sourcegitcommit: 8341fa964365c185b65bc4b71fc0c695ea127dc0
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 05/14/2021
ms.locfileid: "6034089"
---
# <a name="suggested-segments-based-on-activity-data-preview"></a><span data-ttu-id="2badd-103">Әрекет деректеріне негізделген ұсынылған сегменттер (алдын ала қарау нұсқасы)</span><span class="sxs-lookup"><span data-stu-id="2badd-103">Suggested segments based on activity data (preview)</span></span>

<span data-ttu-id="2badd-104">Customer Insights бағдарламасына түсетін тұтынушы әрекетінің негізінде тұтынушылардың қызықты сегменттерін анықтаңыз.</span><span class="sxs-lookup"><span data-stu-id="2badd-104">Discover interesting segments of your customers based on customer activity data that is ingested to Customer Insights.</span></span> <span data-ttu-id="2badd-105">Әрекет деректерінің мысалдары транзакциялар, қолдау көрсету қоңырауының ұзақтығы, сатып алу немесе қайтару әрекеттері болып табылады.</span><span class="sxs-lookup"><span data-stu-id="2badd-105">Examples of activity data are transactions, support call duration, purchases, or returns.</span></span> <span data-ttu-id="2badd-106">Сегменттерді ұсыну үшін әрекет деректері жаңалығы, жиілігі және ақшалай құны (немесе ұзақтығы) бойынша талданады.</span><span class="sxs-lookup"><span data-stu-id="2badd-106">To suggest segments, activity data gets analyzed for recency, frequency, and monetary value (or duration).</span></span> <span data-ttu-id="2badd-107">Сонымен қатар [көрсеткішті жақсарту немесе төлсипатқа не әсер ететіндігін жақсы түсіну үшін ұсынылған сегменттер](suggested-segments.md) жасауға болады.</span><span class="sxs-lookup"><span data-stu-id="2badd-107">Alternatively, you can generate [suggested segments to improve a measure or better understand what influences an attribute](suggested-segments.md).</span></span>

:::image type="content" source="media/suggested-segments-tab.png" alt-text="Әрекетке негізделген және төлсипатқа негізделген сегменттерге арналған сегмент ұсыныстарын көрсететін ұсынылған сегменттер қойыншасы.":::

## <a name="categorize-customers-by-activity"></a><span data-ttu-id="2badd-109">Тұтынушыларды әрекеті бойынша жіктеу</span><span class="sxs-lookup"><span data-stu-id="2badd-109">Categorize customers by activity</span></span>

<span data-ttu-id="2badd-110">Customer Insights бағдарламасында қолжетімді [әрекет деректерімен](activities.md) біз тұтынушылар топтарын ұсынатын ұсыныстар жасай аламыз:</span><span class="sxs-lookup"><span data-stu-id="2badd-110">With [activity data](activities.md) available in Customer Insights, we can generate suggestions that represent customer groups:</span></span>

- <span data-ttu-id="2badd-111">белсенді тұтынушылардың көбісі</span><span class="sxs-lookup"><span data-stu-id="2badd-111">most active customers</span></span> 
- <span data-ttu-id="2badd-112">ең көп сатып алулар жасаған тұтынушылар</span><span class="sxs-lookup"><span data-stu-id="2badd-112">customers that have made the most purchases</span></span> 
- <span data-ttu-id="2badd-113">ең көп табыс әкелген тұтынушылар</span><span class="sxs-lookup"><span data-stu-id="2badd-113">customers that generated the most revenue</span></span> 
- <span data-ttu-id="2badd-114">соңғы уақытта белсенді емес тұтынушылар</span><span class="sxs-lookup"><span data-stu-id="2badd-114">customers who haven’t been active lately</span></span> 
- <span data-ttu-id="2badd-115">сіздің бизнесіңізбен жиі араласатын тұтынушылар</span><span class="sxs-lookup"><span data-stu-id="2badd-115">customers who frequently interact with your business</span></span>  

<span data-ttu-id="2badd-116">Егер сізде бөлшек сауда бизнесі болса, сіз қай тұтынушылардың көбірек табыс әкелетінін біліп, оларды купонмен марапаттай аласыз.</span><span class="sxs-lookup"><span data-stu-id="2badd-116">If you have a retail business, you could find out which customers generate the most revenue and reward them with a coupon.</span></span> <span data-ttu-id="2badd-117">Немесе сіз кездейсоқ тұтынушыларды анықтап, сыйақы беру бағдарламасына қосылуды ұсына аласыз, осылайша олар сіздің бизнесіңізге жиі барады.</span><span class="sxs-lookup"><span data-stu-id="2badd-117">Or you can identify occasional customers and offer them to join a rewards program so they visit your business more often.</span></span>
<span data-ttu-id="2badd-118">Егер сіз денсаулық сақтау саласында жұмыс жасайтын болсаңыз және сіздің мақсатыңыз жеке емделушілерге шығындарды азайту болса.</span><span class="sxs-lookup"><span data-stu-id="2badd-118">If you're in the healthcare business providing public healthcare and your goal is to minimize the expenses for individual patients.</span></span> <span data-ttu-id="2badd-119">Мұны істеу тәсілі бірнеше рет келген кезде мүмкіндігінше ең жақсы көмек көрсету арқылы қайталанатын сапарларды азайту болуы мүмкін.</span><span class="sxs-lookup"><span data-stu-id="2badd-119">A way to do so could be to reduce recurring visits by providing best possible care in as few visits as possible.</span></span> <span data-ttu-id="2badd-120">Бұл жағдайда сіздің мақсатыңыз келу жиілігін төмендетіп және емделушілер үшін қайталанатын шығындарды азайту болып табылады.</span><span class="sxs-lookup"><span data-stu-id="2badd-120">In this case, your goal is to keep the visit frequency low and minimize recurring cost for the patients.</span></span> <span data-ttu-id="2badd-121">Немесе сіз жиі кездесуге баратын және шығындары жоғары емделушілердің сегменттерін анықтай аласыз және жеке тұлғаның емін жақсарту үшін осы жағдайларды талдай аласыз.</span><span class="sxs-lookup"><span data-stu-id="2badd-121">Or you can identify segments of patients who have frequent appointments and high recurring costs and analyze these cases to improve the treatment of the individual.</span></span> 

## <a name="required-data"></a><span data-ttu-id="2badd-122">Міндетті деректер</span><span class="sxs-lookup"><span data-stu-id="2badd-122">Required data</span></span>

<span data-ttu-id="2badd-123">Ұсыныстар таңдалған кіріс деректері негізінде жасалады.</span><span class="sxs-lookup"><span data-stu-id="2badd-123">Suggestions are generated based on the selected input data.</span></span> 

- <span data-ttu-id="2badd-124">Тұтынушы профильдері: барлық тұтынушылар немесе белгілі бір сегменттің мүшелері.</span><span class="sxs-lookup"><span data-stu-id="2badd-124">Customer profiles: All customers or members of a specific segment.</span></span> 

- <span data-ttu-id="2badd-125">Уақыт кезеңі: өткен ай, өткен жыл немесе кез келген реттелетін уақыт аралығы.</span><span class="sxs-lookup"><span data-stu-id="2badd-125">Time period: Last month, last year, or any custom time frame.</span></span>

- <span data-ttu-id="2badd-126">Әрекет түрі: сатып алу, бөлшек сауда транзакциялары, онлайн транзакциялар, тұтынушыға қолдау көрсету жағдайлары, жазылымдар және т.б.</span><span class="sxs-lookup"><span data-stu-id="2badd-126">Activity type: purchases, retail transactions, online transactions, customer support cases, subscriptions, and so on.</span></span>  

- <span data-ttu-id="2badd-127">Customer Insights бағдарламасындағы әрекет деректерін қамтитын нысан: UnifiedActivity нысаны немесе белгілі бір әрекетке арналған нысан.</span><span class="sxs-lookup"><span data-stu-id="2badd-127">Entity in Customer Insights that contains the activity data: The UnifiedActivity entity or the entity for a specific activity.</span></span> 

- <span data-ttu-id="2badd-128">Қамтылатын өлшемдер: бизнес талаптарыңызға байланысты жаңалық, жиілік немесе ақшалай өлшем.</span><span class="sxs-lookup"><span data-stu-id="2badd-128">Dimensions to include: Recency, frequency, or monetary dimension, depending on your business requirements.</span></span>

## <a name="generate-suggested-segments"></a><span data-ttu-id="2badd-129">Ұсынылатын сегменттер жасау</span><span class="sxs-lookup"><span data-stu-id="2badd-129">Generate suggested segments</span></span>

1. <span data-ttu-id="2badd-130">**Сегменттер** бетіне өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="2badd-130">Go to **Segments**.</span></span>

1. <span data-ttu-id="2badd-131">**Ұсыныстар (алдын ала қарау)** қойыншасын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="2badd-131">Select the **Suggestions (preview)** tab.</span></span>

1. <span data-ttu-id="2badd-132">**Жаңа ұсыныстар табу** опциясын таңдаңыз және **Тұтынушы әрекетін көру немесе болжау** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="2badd-132">Select **Find new suggestions** and choose **See or anticipate customer behavior**.</span></span> <span data-ttu-id="2badd-133">Қадамдық тәжірибені іске қосу **Бастау** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="2badd-133">Select **Start** to run the guided experience.</span></span>

   :::image type="content" source="media/suggested-segments-activity-wizard.png" alt-text="Әрекетке негізделген ұсынылған сегментке арналған конфигурация шеберінің бірінші қадамы.":::

1. <span data-ttu-id="2badd-135">Қажетті кіріс деректерін беріңіз және жалғастыру үшін **Келесі** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="2badd-135">Provide the required input data and select **Next** proceed.</span></span>

   - <span data-ttu-id="2badd-136">Тұтынушыларды таңдаңыз: барлық тұтынушыларды немесе белгілі бір сегментті қосыңыз.</span><span class="sxs-lookup"><span data-stu-id="2badd-136">Choose customers: Include all customers or a specific segment.</span></span>
   - <span data-ttu-id="2badd-137">Әрекетті таңдаңыз: әрекет түрін және әрекетті сипаттайтын нысандарды таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="2badd-137">Choose activity: Select the activity type and the entities that describe the activity.</span></span>
   - <span data-ttu-id="2badd-138">Параметрлер: қарастырылатын уақыт кезеңін, ұсыныстардың факторларын орнатыңыз және төлсипаттарды салыстырыңыз.</span><span class="sxs-lookup"><span data-stu-id="2badd-138">Preferences: Set the time period to consider, the factors for suggestions, and map the attributes.</span></span>

1. <span data-ttu-id="2badd-139">Кірісті тексеріп, модельді іске қосу және ұсыныстар жасау үшін **Іске қосу** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="2badd-139">Review your input and select **Run** to run the model and generate suggestions.</span></span>

1. <span data-ttu-id="2badd-140">Тұтынушы профильдері мен таңдалған әрекеттер санына байланысты, оны аяқтауға бірнеше минут кетуі мүмкін.</span><span class="sxs-lookup"><span data-stu-id="2badd-140">Depending on the number of customer profiles and selected activities, it can take a few minutes to complete.</span></span> 

<span data-ttu-id="2badd-141">Ұсыныстарды жасағаннан кейін оларды сіз өзіңізді қызықтыратын өлшем немесе мән бойынша сүзгілеуге болады.</span><span class="sxs-lookup"><span data-stu-id="2badd-141">After generating the suggestions, you can filter them by the dimension or value you're most interested in.</span></span> 

## <a name="view-details-of-a-suggested-segment"></a><span data-ttu-id="2badd-142">Ұсынылатын сегмент мәліметтерін қарау</span><span class="sxs-lookup"><span data-stu-id="2badd-142">View details of a suggested segment</span></span>

<span data-ttu-id="2badd-143">Ұсыныстар жасалғаннан кейін сіз оларды **Әрекетке негізделген ұсыныстар** бөліміндегі **Сегменттер** > **Ұсыныстар (алдын ала қарау нұсқасы)** тармағынан таба аласыз.</span><span class="sxs-lookup"><span data-stu-id="2badd-143">Once the suggestions are generated, you'll find them listed on **Segments** > **Suggestions (preview)** in the **Activity-based suggestions** section.</span></span>

:::image type="content" source="media/suggested-segments-details.png" alt-text="Ұсынылған сегменттің толық деректерін көрсететін кеңейтілген бүйірлік тақта.":::

<span data-ttu-id="2badd-145">Сол сегменттің мәліметтерін қарау үшін ұсынылған сегментте **Ұсынысты көру** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="2badd-145">Select **See suggestion** on a suggested segment to view the details of that segment.</span></span> <span data-ttu-id="2badd-146">Бүйірлік тақта мақсатты топпен салыстырғанда әр өлшемнің мөлшері сияқты мәліметтерді ұсынады.</span><span class="sxs-lookup"><span data-stu-id="2badd-146">The side pane provides details like the extent of each dimension in comparison to the target group.</span></span> <span data-ttu-id="2badd-147">Сондай-ақ ол сегменттегі ықтимал мүшелер саны және жалпы тұтынушылардың тиісті пайызын көрсетеді.</span><span class="sxs-lookup"><span data-stu-id="2badd-147">It also highlights the number of potential members in the segment and the corresponding percentage of the total customers.</span></span> <span data-ttu-id="2badd-148">Егер сіз ұсынысты сегмент ретінде қалдырғыңыз келсе, **Сегмент жасау** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="2badd-148">If you want to keep the suggestion as a segment, select **Create segment**.</span></span>    

## <a name="save-a-suggestion-as-a-segment"></a><span data-ttu-id="2badd-149">Ұсынысты сегмент ретінде сақтаңыз</span><span class="sxs-lookup"><span data-stu-id="2badd-149">Save a suggestion as a segment</span></span>

1. <span data-ttu-id="2badd-150">**Сегменттер** > **Ұсыныстар (алдын ала қарау)** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="2badd-150">Go to **Segments** > **Suggestions (preview)**.</span></span>

1. <span data-ttu-id="2badd-151">Сақтау қажет сегментті таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="2badd-151">Select the segment you want to save.</span></span> 

1. <span data-ttu-id="2badd-152">Бүйірлік тақтадан **Сегмент жасау** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="2badd-152">In the side pane, select **Create segment**.</span></span> 

1. <span data-ttu-id="2badd-153">Сегментті сақтағаннан кейін, ол **Барлық сегменттер** қойыншасындағы сегменттер тізімінде көрсетіледі. Мұны енді [кез келген басқа сегмент сияқты жаңартуға немесе жоюға](segments.md) болады.</span><span class="sxs-lookup"><span data-stu-id="2badd-153">After saving the segment, it will show in the list of segments on the **All segments** tab. It can now be [refreshed or deleted like any other segment](segments.md).</span></span> <span data-ttu-id="2badd-154">Сегмент туралы мәліметтерді өңдеу мүмкін емес.</span><span class="sxs-lookup"><span data-stu-id="2badd-154">You can't edit the segment details.</span></span> <span data-ttu-id="2badd-155">Дегенмен сіз ұсыныстарға енгізу критерийлерін өзгерте аласыз және әртүрлі ұсыныстар жасай аласыз.</span><span class="sxs-lookup"><span data-stu-id="2badd-155">However, you can change the input criteria for the suggestions and generate different suggestions.</span></span>

## <a name="refresh-or-edit-a-set-of-suggestions"></a><span data-ttu-id="2badd-156">Ұсыныстар жиынтығын жаңарту немесе өңдеу</span><span class="sxs-lookup"><span data-stu-id="2badd-156">Refresh or edit a set of suggestions</span></span>

1. <span data-ttu-id="2badd-157">**Сегменттер** > **Ұсыныстар (алдын ала қарау нұсқасы)** тармағына өтіңіз және **Әрекетке негізделген ұсыныстар** бөлімінде сегментті табыңыз.</span><span class="sxs-lookup"><span data-stu-id="2badd-157">Go to **Segments** > **Suggestions (preview)** and look for the segment in the **Activity-based suggestions** section.</span></span>

1. <span data-ttu-id="2badd-158">Конфигурацияланған төлсипаттарды сақтай отырып, ұсыныстарды жаңарту үшін **Ұсыныстарды жаңарту** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="2badd-158">Select **Refresh suggestions** to refresh the suggestions while keeping configured attributes.</span></span> <span data-ttu-id="2badd-159">Немесе конфигурацияланған төлсипаттарды өзгерту үшін **Ұсыныстарды өңдеу** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="2badd-159">Or select **Edit suggestions** to modify the configured attributes.</span></span> <span data-ttu-id="2badd-160">Жүйе процесті қайта іске қосады, соңғы деректер негізінде сегмент ұсыныстарын жасайды және ағымдағы ұсыныстарды ауыстырады.</span><span class="sxs-lookup"><span data-stu-id="2badd-160">The system will rerun the process, generate segment suggestions based on the latest data, and replace the current suggestions.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
