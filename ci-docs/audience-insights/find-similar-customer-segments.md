---
title: Ұқсас тұтынушыларды AI көмегімен табу
description: Ұқсас тұтынушы сегменттерін жасанды интеллектпен табыңыз.
ms.date: 06/25/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: f588f45ed11efffbb335003642a4b92810153017
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596782"
---
# <a name="similar-customers-preview"></a><span data-ttu-id="ec22d-103">Ұқсас тұтынушылар (алдын ала қарау)</span><span class="sxs-lookup"><span data-stu-id="ec22d-103">Similar Customers (preview)</span></span>

<span data-ttu-id="ec22d-104">Бұл мүмкіндік жасанды интеллектіні пайдаланып тұтынушы негізінен ұқсас тұтынушыларды табуға мүмкіндік береді.</span><span class="sxs-lookup"><span data-stu-id="ec22d-104">This feature lets you find similar customers in your customer base using artificial intelligence.</span></span> <span data-ttu-id="ec22d-105">Осы мүмкіндікті пайдалану үшін жасалған кемінде бір сегмент болуы керек.</span><span class="sxs-lookup"><span data-stu-id="ec22d-105">You need to have at least one segment created to use this feature.</span></span> <span data-ttu-id="ec22d-106">Бұрыннан бар сегмент шарттарын кеңейту сегментке ұқсас тұтынушыларды табуға көмектеседі.</span><span class="sxs-lookup"><span data-stu-id="ec22d-106">Expanding the criteria of an existing segment help find customers that are similar to that segment.</span></span>

> [!NOTE]
> <span data-ttu-id="ec22d-107">*Ұқсас тұтынушыларды табу* мүмкіндігінде деректерді бағалау мен деректерге байланысты болжамдар жасау әрекеттері пайдаланылады, сол себепті Деректерді қорғау бойынша жалпы регламент ("GDPR") бойынша анықталған шарт ретінде профильдеу әдісі ретінде пайдаланылатын мүмкіндік бар.</span><span class="sxs-lookup"><span data-stu-id="ec22d-107">*Find similar customers* uses automated means to evaluate data and make predictions based on that data, and therefore has the capability to be used as a method of profiling, as that term is defined by the General Data Protection Regulation (“GDPR”).</span></span> <span data-ttu-id="ec22d-108">Тұтынушының деректерді өңдеу үшін осы мүмкіндікті пайдалануына GDPR, басқа заңдар немесе ережелер қатысты болуы мүмкін.</span><span class="sxs-lookup"><span data-stu-id="ec22d-108">Customer’s use of this feature to process data may be subject to GDPR or other laws or regulations.</span></span> <span data-ttu-id="ec22d-109">Болжамдарға қоса Dynamics 365 Customer Insights бағдарламасын пайдаланудың барлық қолданбалы заңдар мен ережелердің жеке өмірге, жеке деректерге, биометриялық деректерге, деректерді қорғауға және байланыстар құпиялылығына қатысты заңдарға сәйкес келуіне жауаптысыз.</span><span class="sxs-lookup"><span data-stu-id="ec22d-109">You are responsible for ensuring that your use of Dynamics 365 Customer Insights, including predictions, complies with all applicable laws and regulations, including laws related to privacy, personal data, biometric data, data protection, and confidentiality of communications.</span></span>

## <a name="finding-similar-customers"></a><span data-ttu-id="ec22d-110">Ұқсас тұтынушыларды табу</span><span class="sxs-lookup"><span data-stu-id="ec22d-110">Finding similar customers</span></span>

1. <span data-ttu-id="ec22d-111">Аудитория мәліметтерінде **Сегменттер** бөліміне өтіп, жаңа сегментті негіздегіңіз келетін сегментті таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="ec22d-111">In audience insights, go to **Segments** and select the segment you want to base your new segment on.</span></span> <span data-ttu-id="ec22d-112">Бұл — *бастапқы сегмент*.</span><span class="sxs-lookup"><span data-stu-id="ec22d-112">That's your *source segment*.</span></span>

1. <span data-ttu-id="ec22d-113">Әрекет жолағынан **Ұқсас тұтынушыларды табу** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="ec22d-113">In the action bar, select **Find similar customers**.</span></span>

1. <span data-ttu-id="ec22d-114">Жаңа сегментке ұсынылған атты қарап шығып, қажет болғанда өзгертіңіз.</span><span class="sxs-lookup"><span data-stu-id="ec22d-114">Review the suggested name for your new segment and change it if necessary.</span></span>

1. <span data-ttu-id="ec22d-115">Жаңа сегментті анықтайтын өрістерді қарап шығыңыз.</span><span class="sxs-lookup"><span data-stu-id="ec22d-115">Review the fields that define your new segment.</span></span> <span data-ttu-id="ec22d-116">Бұл өрістер жүйе бастапқы сегментіңізге ұқсас тұтынушыларды табуға әрекет жасайтын негізді анықтайды.</span><span class="sxs-lookup"><span data-stu-id="ec22d-116">These fields define the basis on which the system will try to find similar customers to your source segment.</span></span> <span data-ttu-id="ec22d-117">Әдепкі бойынша жүйе ұсынылған өрістерді таңдайды.</span><span class="sxs-lookup"><span data-stu-id="ec22d-117">The system will select recommended fields by default.</span></span>
  <span data-ttu-id="ec22d-118">Үлгі өнімділігін айтарлықтай төмендетуі мүмкін өрістер автоматты шығарылады:</span><span class="sxs-lookup"><span data-stu-id="ec22d-118">Fields that can significantly reduce the model performance are automatically excluded:</span></span>
  
   - <span data-ttu-id="ec22d-119">Мына деректер түрлері бар өрістер: StringType, BooleanType, CharType, LongType, IntType, DoubleType, FloatType, ShortType</span><span class="sxs-lookup"><span data-stu-id="ec22d-119">Fields with the following data types: StringType, BooleanType, CharType, LongType, IntType, DoubleType, FloatType, ShortType</span></span>
   - <span data-ttu-id="ec22d-120">2-ден аз немесе 30-дан көп элементтер саны бар өрістер (өрістегі элементтер саны)</span><span class="sxs-lookup"><span data-stu-id="ec22d-120">Fields with a cardinality (the number of elements in a field) of less than 2 or more than 30</span></span>

1. <span data-ttu-id="ec22d-121">Жаңа сегментіңізде **Барлық тұтынушылар** немесе **Белгілі бір бұрыннан бар сегмент** ішінде тек тұтынушылар қосу керек болса, таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="ec22d-121">Choose if you want to include **All customers** or only customers in a **Specific existing segment** in your new segment.</span></span>

1. <span data-ttu-id="ec22d-122">**Бастапқы сегменттегінің барлығын шығару** құсбелгісін таңдау арқылы бастапқы сегменттегі тұтынушыларды шығарыңыз.</span><span class="sxs-lookup"><span data-stu-id="ec22d-122">Exclude customers in your source segment by selecting the **Exclude everyone in source segment** checkbox.</span></span>

1. <span data-ttu-id="ec22d-123">Әдепкі бойынша жүйе шығыста мақсатты аудитория өлшемінің тек 20% бөлігін ұсынады.</span><span class="sxs-lookup"><span data-stu-id="ec22d-123">By default, the system suggests including only 20% of the target audience size in your output.</span></span> <span data-ttu-id="ec22d-124">Қажет болғанда осы шекті өңдеңіз.</span><span class="sxs-lookup"><span data-stu-id="ec22d-124">Edit this threshold as needed.</span></span> <span data-ttu-id="ec22d-125">Шекті арттыру дәлдікті азайтады.</span><span class="sxs-lookup"><span data-stu-id="ec22d-125">Increasing the threshold will reduce the precision.</span></span>

1. <span data-ttu-id="ec22d-126">Деректер жинағын талдайтын екілік классификация тапсырмасын (компьютерлік оқыту әдісі) бастау үшін беттің астынан **Іске қосу** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="ec22d-126">Select **Run** at the bottom of the page to start a binary classification task (a method of machine learning) which analyzes the dataset.</span></span>

## <a name="view-the-similar-segment"></a><span data-ttu-id="ec22d-127">Ұқсас сегментті қарау</span><span class="sxs-lookup"><span data-stu-id="ec22d-127">View the similar segment</span></span>

<span data-ttu-id="ec22d-128">Ұқсас сегментті өңдегеннен кейін **Сегменттер** бетінде тізімделген жаңа сегментті таба аласыз.</span><span class="sxs-lookup"><span data-stu-id="ec22d-128">After processing the similar segment, you'll find the new segment listed on the **Segments** page.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="ec22d-129">![Ұқсас тұтынушылар сегменті](media/expanded-segment.png "Ұқсас тұтынушылар сегменті")</span><span class="sxs-lookup"><span data-stu-id="ec22d-129">![Similar customers segment](media/expanded-segment.png "Similar customers segment")</span></span>

<span data-ttu-id="ec22d-130">Сегмент мәліметін ашу үшін әрекет жолағынан **Көру** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="ec22d-130">Select **View** in the action bar to open the segment detail.</span></span> <span data-ttu-id="ec22d-131">Бұл көріністе [ұқсастық көрсеткіштері](#about-similarity-scores) бойынша нәтижені тарату туралы ақпарат бар.</span><span class="sxs-lookup"><span data-stu-id="ec22d-131">This view contains information about the result distribution across [similarity scores](#about-similarity-scores).</span></span> <span data-ttu-id="ec22d-132">Сонымен қатар **Сегмент нөмірлерін алдын ала қарау** бөлімінен ұқсастық көрсеткіші мәндерін таба аласыз.</span><span class="sxs-lookup"><span data-stu-id="ec22d-132">You'll also find the similarity score values in the **Segment members preview**.</span></span>

## <a name="use-the-output-of-a-similar-segment"></a><span data-ttu-id="ec22d-133">Ұқсас сегмент шығысын пайдалану</span><span class="sxs-lookup"><span data-stu-id="ec22d-133">Use the output of a similar segment</span></span>

<span data-ttu-id="ec22d-134">Басқа сегменттермен жұмыс істеген кезде [ұқсас сегмент шығысымен жұмыс істей аласыз](segments.md).</span><span class="sxs-lookup"><span data-stu-id="ec22d-134">You can [work with the output of a similar segment](segments.md) as you do with other segments.</span></span> <span data-ttu-id="ec22d-135">Мысалы, сегментті экспорттаңыз немесе шараны құрастырыңыз.</span><span class="sxs-lookup"><span data-stu-id="ec22d-135">For example, export the segment or build a measure.</span></span>

## <a name="refresh-and-edit-a-similar-segment"></a><span data-ttu-id="ec22d-136">Ұқсас сегментті жаңарту және өңдеу</span><span class="sxs-lookup"><span data-stu-id="ec22d-136">Refresh and edit a similar segment</span></span>

<span data-ttu-id="ec22d-137">Ұқсас сегментті жаңарту үшін, оны **Сегменттер** бетінен таңдап, әрекет жолағынан **Жаңарту** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="ec22d-137">To refresh a similar segment, select it on the **Segments** page and select **Refresh** in the action bar.</span></span>

<span data-ttu-id="ec22d-138">Ұқсас сегментті өңдеу сіздің деректеріңізді қайта өңдейді.</span><span class="sxs-lookup"><span data-stu-id="ec22d-138">Editing a similar segment will reprocess your data.</span></span> <span data-ttu-id="ec22d-139">Бұрын жасалған сегмент жаңартылған деректермен жаңартылады.</span><span class="sxs-lookup"><span data-stu-id="ec22d-139">The previously created segment gets updated with refreshed data.</span></span>    
<span data-ttu-id="ec22d-140">Ұқсас сегментті өңдеу үшін, оны **Сегменттер** бетінен таңдап, әрекет жолағынан **Өңдеу** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="ec22d-140">To edit a similar segment, select it on the **Segments** page and select **Edit** in the action bar.</span></span> <span data-ttu-id="ec22d-141">Өзгерістерді қолданып, өңдеуді бастау үшін **Іске қосу** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="ec22d-141">Apply your changes and select **Run** to start the processing.</span></span>

## <a name="delete-a-similar-segment"></a><span data-ttu-id="ec22d-142">Ұқсас сегментті жою</span><span class="sxs-lookup"><span data-stu-id="ec22d-142">Delete a similar segment</span></span>

<span data-ttu-id="ec22d-143">**Сегменттер** бетінен сегментті таңдап, әрекет жолағынан **Жою** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="ec22d-143">Select the segment on the **Segments** page and select **Delete** in the action bar.</span></span> <span data-ttu-id="ec22d-144">Одан кейін жоюды растаңыз.</span><span class="sxs-lookup"><span data-stu-id="ec22d-144">Then, confirm your deletion.</span></span>

## <a name="about-similarity-scores"></a><span data-ttu-id="ec22d-145">Ұқсастық көрсеткіштері туралы</span><span class="sxs-lookup"><span data-stu-id="ec22d-145">About similarity scores</span></span>

<span data-ttu-id="ec22d-146">Екілік классификация компьютерлік оқыту моделі ұқсас сегментте тұтынушыларға көрсеткіш тағайындайды.</span><span class="sxs-lookup"><span data-stu-id="ec22d-146">The binary classification machine learning model assigns a score to customers in the similar segment.</span></span> <span data-ttu-id="ec22d-147">Көрсеткіш бастапқы сегменттегі тұтынушылар ұқсастығына байланысты.</span><span class="sxs-lookup"><span data-stu-id="ec22d-147">The score is based on the similarity to customers in the source segment.</span></span>

- <span data-ttu-id="ec22d-148">0,55-тен төмен ұқсастық көрсеткіштері — бастапқы сегментте жүйе тұтынушыларға *ұқсас емес* деп жіктелген тұтынушылар</span><span class="sxs-lookup"><span data-stu-id="ec22d-148">Similarity scores below 0.55 are customers the system classified as *not similar* to customers in the source segment</span></span>
- <span data-ttu-id="ec22d-149">0,55-0,7 аралығындағы ұқсастық көрсеткіштері *шамалы ұқсас* болып жіктеледі</span><span class="sxs-lookup"><span data-stu-id="ec22d-149">Similarity scores between 0.55 – 0.7 are classified as *somewhat similar*</span></span>
- <span data-ttu-id="ec22d-150">0,7-0,85 аралығындағы ұқсастық көрсеткіштері *ұқсас* болып жіктеледі</span><span class="sxs-lookup"><span data-stu-id="ec22d-150">Similarity scores between 0.7 – 0.85 are classified as *similar*</span></span>
- <span data-ttu-id="ec22d-151">0,85-1 аралығындағы ұқсастық көрсеткіштері — жүйе *өте ұқсас* деп жіктеген тұтынушылар</span><span class="sxs-lookup"><span data-stu-id="ec22d-151">Similarity scores between 0.85 – 1 are customers the system classified as *very similar*</span></span>

<span data-ttu-id="ec22d-152">0,4-тен төмен ұқсастық көрсеткіштері бар тұтынушылар модель шығысына қосылмайды.</span><span class="sxs-lookup"><span data-stu-id="ec22d-152">Customers with similarity scores below 0.4 aren't included in the model output.</span></span> <span data-ttu-id="ec22d-153">Жүйеде бастапқы сегментке ұқсас болып қарастырылмайды.</span><span class="sxs-lookup"><span data-stu-id="ec22d-153">The system doesn't consider them similar enough to the source segment.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]