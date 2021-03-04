---
title: Болжамдарды пайдалана отырып, жартылай нәтижелерді толтыру
description: Тұтынушының толық емес деректерін толтыру үшін болжамдарды қолданыңыз.
ms.date: 05/05/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
ms.reviewer: zacook
manager: shellyha
ms.openlocfilehash: 577232c7e901dfd54a195c3e9cfac5d1f0f866e6
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268279"
---
# <a name="complete-your-partial-data-with-predictions"></a><span data-ttu-id="0a8b5-103">Ішінара деректерді болжамдармен толтыру</span><span class="sxs-lookup"><span data-stu-id="0a8b5-103">Complete your partial data with predictions</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="0a8b5-104">Болжамдар тұтынушы түсінігін арттыруы мүмкін болжалды мәндерді оңай жасауға мүмкіндік береді.</span><span class="sxs-lookup"><span data-stu-id="0a8b5-104">Predictions lets you easily create predicted values that can enhance your understanding of a customer.</span></span> <span data-ttu-id="0a8b5-105">**Сараптау** > **Болжамдар** бетінде аудитория мәліметтерінің басқа бөліктерінде конфигурацияланған болжамдарды көру және оларды әрі қарай теңшеуге мүмкіндік беру үшін **Менің болжамдарым** пәрменін таңдауға болады.</span><span class="sxs-lookup"><span data-stu-id="0a8b5-105">On the **Intelligence** > **Predictions** page, you can select **My predictions** to see predictions that you've configured in other parts of audience insights, and allow you to further customize them.</span></span>

> [!NOTE]
> <span data-ttu-id="0a8b5-106">Ортаңызда Azure Data Lake Gen 2 сақтау орны қолданылса, бұл мүмкіндікті пайдалану мүмкін емес.</span><span class="sxs-lookup"><span data-stu-id="0a8b5-106">You can't use this feature if your environment uses Azure Data Lake Gen 2 storage.</span></span>
>
> <span data-ttu-id="0a8b5-107">Болжамдар мүмкіндігінде деректерді бағалауға және деректер негізінде болжамдарға жасауға автоматты құралдар қолданылады, сол себепті профильді әдісі ретінде қолданылатын мүмкіндігі бар және шарты Деректерді қорғау бойынша жалпы регламент ("GDPR") бойынша анықталады.</span><span class="sxs-lookup"><span data-stu-id="0a8b5-107">The predictions feature uses automated means to evaluate data and make predictions based on that data, and therefore has the capability to be used as a method of profiling, as that term is defined by the General Data Protection Regulation ("GDPR").</span></span> <span data-ttu-id="0a8b5-108">Тұтынушының деректерді өңдеу үшін осы мүмкіндікті пайдалануына GDPR, басқа заңдар немесе ережелер қатысты болуы мүмкін.</span><span class="sxs-lookup"><span data-stu-id="0a8b5-108">Customer's use of this feature to process data may be subject to GDPR or other laws or regulations.</span></span> <span data-ttu-id="0a8b5-109">Болжамдарға қоса Dynamics 365 Customer Insights бағдарламасын пайдаланудың барлық қолданбалы заңдар мен ережелердің жеке өмірге, жеке деректерге, биометриялық деректерге, деректерді қорғауға және байланыстар құпиялылығына қатысты заңдарға сәйкес келуіне жауаптысыз.</span><span class="sxs-lookup"><span data-stu-id="0a8b5-109">You are responsible for ensuring that your use of Dynamics 365 Customer Insights, including predictions, complies with all applicable laws and regulations, including laws related to privacy, personal data, biometric data, data protection, and confidentiality of communications.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="0a8b5-110">Алғышарттар</span><span class="sxs-lookup"><span data-stu-id="0a8b5-110">Prerequisites</span></span>

<span data-ttu-id="0a8b5-111">Ұйымыңыз болжамдар мүмкіндігін пайдалану алдында мына алғышарттар сақталуы тиіс:</span><span class="sxs-lookup"><span data-stu-id="0a8b5-111">Before your organization can use the predictions feature, the following prerequisites must be met:</span></span>

1. <span data-ttu-id="0a8b5-112">[Common Data Service қызметіне орнатылған](https://docs.microsoft.com/ai-builder/build-model#prerequisites) ұйымыңыздың данасы бар және ол Customer Insights жүйесімен бір ұйымда.</span><span class="sxs-lookup"><span data-stu-id="0a8b5-112">Your organization has an instance [set up in the Common Data Service](https://docs.microsoft.com/ai-builder/build-model#prerequisites) and it's in the same organization as Customer Insights.</span></span>

2. <span data-ttu-id="0a8b5-113">Қоршаған орта Common Data Service данасына тіркелген.</span><span class="sxs-lookup"><span data-stu-id="0a8b5-113">Your environment is attached to your Common Data Service instance.</span></span>

<span data-ttu-id="0a8b5-114">[Жаңа ортаны](manage-environments.md) жасасаңыз, оны **Ортаны жасау** диалогтық терезесінде теңшеп, **Кеңейтілген** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="0a8b5-114">If you're [creating a new environment](manage-environments.md), configure it in the **Create an environment** dialog and select **Advanced**.</span></span> <span data-ttu-id="0a8b5-115">Егер ортаны әлдеқашан жасап қойған болсаңыз, оның параметрлеріне өтіп, **Қосымша** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="0a8b5-115">If you've already created an environment, go to its settings and select **Advanced**.</span></span> <span data-ttu-id="0a8b5-116">Қалай болғанда да, **Болжамдарды қолдану** бөлімінде қоршаған ортаны қосқыңыз келетін Common Data Service данасының URL мекенжайын енгізіңіз.</span><span class="sxs-lookup"><span data-stu-id="0a8b5-116">Either way, in the **Use predictions** section, enter the Common Data Service instance URL to which you want to attach your environment.</span></span>

## <a name="create-a-prediction-in-the-customer-entity"></a><span data-ttu-id="0a8b5-117">Тұтынушы нысанында болжамды жасау</span><span class="sxs-lookup"><span data-stu-id="0a8b5-117">Create a prediction in the Customer entity</span></span>

1. <span data-ttu-id="0a8b5-118">Аудитория мәліметтерінде **Деректер** > **Нысандар** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="0a8b5-118">In audience insights, go to **Data** > **Entities**.</span></span>

2. <span data-ttu-id="0a8b5-119">**Тұтынушы** нысанын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="0a8b5-119">Select the **Customer** entity.</span></span>

3. <span data-ttu-id="0a8b5-120">**Customer: CustomerInsights** нысанынан **Өрістер** қойыншасын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="0a8b5-120">In the **Customer:CustomerInsights** entity, select on the **Fields** tab.</span></span>

4. <span data-ttu-id="0a8b5-121">Мәндерін болжау керек төлсипат атын тауып, **Қорытынды** бағанынан **Шолу** белгішесін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="0a8b5-121">Find the attribute name you wish to predict values for, then select the **Overview** icon in the **Summary** column.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="0a8b5-122">![Шолу белгішесі](media/intelligence-overviewicon.png "Шолу белгішесі")</span><span class="sxs-lookup"><span data-stu-id="0a8b5-122">![Overview icon](media/intelligence-overviewicon.png "Overview icon")</span></span>

5. <span data-ttu-id="0a8b5-123">Төлсипаттың жоқ мәндері жоғары деңгейлі болса, болжауды жалғастыру үшін **Жоқ мәндерді болжау** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="0a8b5-123">If there's a high rate of missing values for your attribute, select **Predict missing values** to continue with your prediction.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="0a8b5-124">![Жоқ мәндерді болжау түймесі көрсетілген шолу күйі](media/intelligence-overviewpredictmissingvalues.png "Жоқ мәндерді болжау түймесі көрсетілген шолу күйі")</span><span class="sxs-lookup"><span data-stu-id="0a8b5-124">![Overview status with predict missing values button shown](media/intelligence-overviewpredictmissingvalues.png "Overview status with predict missing values button shown")</span></span>

6. <span data-ttu-id="0a8b5-125">Болжам нәтижелері үшін **Көрсетілетін аты** мен **Шығыс нысаны атын** беріңіз.</span><span class="sxs-lookup"><span data-stu-id="0a8b5-125">Provide a **Display name** and an **Output entity name** for the results of the prediction.</span></span>

7. <span data-ttu-id="0a8b5-126">Алдын ала толтырылған опциялар тізімінде мәндерді болжалды санатпен салыстыруға болатын орын көрсетіледі.</span><span class="sxs-lookup"><span data-stu-id="0a8b5-126">A pre-populated list of options will show where you can map the values to a predicted category.</span></span> <span data-ttu-id="0a8b5-127">Бұндай жағдайда санат опциялары 0 немесе 1 болады, олар шынайы/жалған немесе болжамның екілік сипатымен салыстырылады.</span><span class="sxs-lookup"><span data-stu-id="0a8b5-127">In this case, your only category options will be 0 or 1, as they map to the true/false or binary nature of the prediction.</span></span> <span data-ttu-id="0a8b5-128">Санат бағанындағы соңғы болжамда "0" ретінде жіктелетін өріс мәндерін "0" мәнімен салыстырыңыз, ал соңғы болжамда "1" ретінде жіктелетін элементтерді "1" мәнімен салыстырыңыз.</span><span class="sxs-lookup"><span data-stu-id="0a8b5-128">In the Category column, map the field values you'd like to be classified as "0" in the final prediction to "0", and the items you'd like to be classified as "1" in the final prediction to "1".</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="0a8b5-129">![Өріс мәндерін санаттармен салыстыру көрсетілген мысал](media/intelligence-categorymapping.png "Өріс мәндерін санаттармен салыстыру көрсетілген мысал")</span><span class="sxs-lookup"><span data-stu-id="0a8b5-129">![Example showing mapped field values to categories](media/intelligence-categorymapping.png "Example showing mapped field values to categories")</span></span>

8. <span data-ttu-id="0a8b5-130">**Дайын** параметрін таңдасаңыз, болжам өңделеді.</span><span class="sxs-lookup"><span data-stu-id="0a8b5-130">Select **Done** and the prediction will be processed.</span></span> <span data-ttu-id="0a8b5-131">Деректер өлшемі мен кешенділігіне байланысты өңдеуге біраз уақыт кетуі мүмкін.</span><span class="sxs-lookup"><span data-stu-id="0a8b5-131">The processing will take some time, depending on the size and complexity of data.</span></span> <span data-ttu-id="0a8b5-132">Жасалған болжамның **Шығыс нысаны атына** байланысты нәтижелер жаңа нысанда қолжетімді болады.</span><span class="sxs-lookup"><span data-stu-id="0a8b5-132">Results will be available in a new entity based on the **Output entity name** of the prediction you created.</span></span>

## <a name="create-a-prediction-while-creating-a-segment"></a><span data-ttu-id="0a8b5-133">Сегментті жасау кезінде болжам жасаңыз</span><span class="sxs-lookup"><span data-stu-id="0a8b5-133">Create a prediction while creating a segment</span></span>

<span data-ttu-id="0a8b5-134">Сонымен қатар, сегментті жасаған кезде таңдаудың белгілі бір төлсипатының жоқ мәндерін болжауға болады.</span><span class="sxs-lookup"><span data-stu-id="0a8b5-134">Predicting missing values for a specific attribute of choice is also possible when creating a segment.</span></span> <span data-ttu-id="0a8b5-135">Әсіресе, бірыңғай Тұтынушы нысанына немесе Customer_Measure нысанына байланысты сегментті жылдам жасағанда.</span><span class="sxs-lookup"><span data-stu-id="0a8b5-135">Specifically, when you quickly create a segment based on either your unified Customer entity or Customer_Measure entity.</span></span>

<span data-ttu-id="0a8b5-136">Осы ағын бөлігі ретінде Тұтынушының қанағаттануы немесе Сатып алу сомасы сияқты сегментті негіздеу үшін белгілі бір төлсипатты таңдайсыз.</span><span class="sxs-lookup"><span data-stu-id="0a8b5-136">As part of this flow, you'll choose a specific attribute to base your segment on, such as Customer Satisfaction or Purchase Amount.</span></span> <span data-ttu-id="0a8b5-137">Сегментті жасағаннан кейін жүйе осы төлсипат үшін жетіспейтін мәндерді болжау әдісін ұсынады.</span><span class="sxs-lookup"><span data-stu-id="0a8b5-137">Upon segment creation, the system will suggest a method for predicting any missing values for this attribute.</span></span>

1. <span data-ttu-id="0a8b5-138">Аудитория мәліметтерінде **Сегменттер** бетіне өтіп, **Профильдер** қатарын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="0a8b5-138">In audience insights, go to **Segments** and select the **Profiles** tile.</span></span>

2. <span data-ttu-id="0a8b5-139">Сегментті жасау үшін **Өріс** параметрін таңдап, **Оператор** параметрін таңдап, **Қарап шығу** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="0a8b5-139">Choose a **Field** to create a segment on and select an **Operator**, then select **Review**.</span></span>

3. <span data-ttu-id="0a8b5-140">Сегмент үшін **Ат** және **Көрсетілетін ат** беріңіз.</span><span class="sxs-lookup"><span data-stu-id="0a8b5-140">Provide a **Name** and a **Display name** for the segment.</span></span>

4. <span data-ttu-id="0a8b5-141">**Сақтау** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="0a8b5-141">Select **Save**.</span></span>

5. <span data-ttu-id="0a8b5-142">Сіз жасаған сегментте көз өрісінде аяқталмаған деректер болса, жоқ мәндерді болжауды таңдай аласыз.</span><span class="sxs-lookup"><span data-stu-id="0a8b5-142">If the segment you created has incomplete data in the source field, you can choose to predict the missing values.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="0a8b5-143">![Болжам түймесі](media/segments-predictoption.png "Болжам түймесі")</span><span class="sxs-lookup"><span data-stu-id="0a8b5-143">![Prediction button](media/segments-predictoption.png "Prediction button")</span></span>

6. <span data-ttu-id="0a8b5-144">Болжам нәтижелері үшін **Көрсетілетін аты** мен **Шығыс нысаны атын** беріңіз.</span><span class="sxs-lookup"><span data-stu-id="0a8b5-144">Provide a **Display name** and an **Output entity name** for the results of the prediction.</span></span>

7. <span data-ttu-id="0a8b5-145">**Дайын** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="0a8b5-145">Select **Done**.</span></span> <span data-ttu-id="0a8b5-146">Болжам қысқа уақыт ішінде сіз **Шығыс нысанының атауы** өрісінде көрсеткен атпен жаңа нысанда жасалынады.</span><span class="sxs-lookup"><span data-stu-id="0a8b5-146">Your prediction will be generated shortly in a new entity with the name you provided for the **Output entity name**.</span></span>

## <a name="view-a-prediction"></a><span data-ttu-id="0a8b5-147">Болжамды көру</span><span class="sxs-lookup"><span data-stu-id="0a8b5-147">View a prediction</span></span>

1. <span data-ttu-id="0a8b5-148">Аудитория мәліметтерінде **Сараптау** > **Болжамдар** > **Менің болжамдарым** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="0a8b5-148">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="0a8b5-149">Қарап шығу керек болжамды таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="0a8b5-149">Select the prediction you want to review.</span></span>

3. <span data-ttu-id="0a8b5-150">**Әрекеттер** бағанынан көп нүктені таңдап, **Көрініс** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="0a8b5-150">Select the ellipsis in the **Actions** column and choose **View**.</span></span>

4. <span data-ttu-id="0a8b5-151">Болжам көрінісінде деректер нүктелерінің санын көресіз.</span><span class="sxs-lookup"><span data-stu-id="0a8b5-151">You'll see a number of data points in the view of your prediction.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="0a8b5-152">![Болжамдар беті](media/intelligence-predictionsviewpage.png "Болжамдар беті")</span><span class="sxs-lookup"><span data-stu-id="0a8b5-152">![Predictions page](media/intelligence-predictionsviewpage.png "Predictions page")</span></span>

   - <span data-ttu-id="0a8b5-153">**Болжалды мәндер** параметрінде өріс мәні мен санатты салыстыру кезеңі барысында жасалған салыстыру көрсетіледі.</span><span class="sxs-lookup"><span data-stu-id="0a8b5-153">**Predicted values** shows the mapping you created during the Field value to Category mapping phase.</span></span> <span data-ttu-id="0a8b5-154">Бұлар белгілі бір санатпен салыстырылған деректер жиынында мәндер.</span><span class="sxs-lookup"><span data-stu-id="0a8b5-154">These are the values in your dataset that have been mapped to a specific category.</span></span>
   <span data-ttu-id="0a8b5-155">-**Үздік ықпал жасаушылар** — белгілі бір санатпен салыстыратын өріс мәнінің болжам сенімділігіне әсер ететін деректер жиынындағы факторлар.</span><span class="sxs-lookup"><span data-stu-id="0a8b5-155">-**Top influencers** are the factors within your dataset that were most likely to influence the prediction's confidence of your Field value being mapped to a specific category.</span></span>
   - <span data-ttu-id="0a8b5-156">**Өнімділік** болжамдар жасау жолын көрсетеді.</span><span class="sxs-lookup"><span data-stu-id="0a8b5-156">**Performance** indicates how the predictions are doing.</span></span> <span data-ttu-id="0a8b5-157">Қосымша ақпарат алу үшін сілтемені таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="0a8b5-157">Select the link to learn more.</span></span>
   - <span data-ttu-id="0a8b5-158">**Алдын ала қарау** параметрі болжам мен ықтималдықтан шығыс деректер жиыны үлгілерін немесе болжалды мәннің сенімділігін көрсетеді, мұндағы 0 — белгісіз, 1 — белгілі.</span><span class="sxs-lookup"><span data-stu-id="0a8b5-158">**Preview** shows samples of the output dataset from your prediction and the likelihood, or our confidence, of the predicted value where 0 is uncertain, and 1 is certain.</span></span>

## <a name="update-a-prediction"></a><span data-ttu-id="0a8b5-159">Болжамды жаңарту</span><span class="sxs-lookup"><span data-stu-id="0a8b5-159">Update a prediction</span></span>

1. <span data-ttu-id="0a8b5-160">Аудитория мәліметтерінде **Сараптау** > **Болжамдар** > **Менің болжамдарым** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="0a8b5-160">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="0a8b5-161">Жаңарту керек болжамды таңдап, **Жаңарту** белгішесін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="0a8b5-161">Select the prediction you want to update and select the **Update** icon.</span></span>

3. <span data-ttu-id="0a8b5-162">Болжамді өңдеу жоспарланады.</span><span class="sxs-lookup"><span data-stu-id="0a8b5-162">The prediction will be scheduled for processing.</span></span> <span data-ttu-id="0a8b5-163">**Болжамдар** бетінің **Жаңартылған** бағанынан соңғы жаңартылған уақытты көре аласыз.</span><span class="sxs-lookup"><span data-stu-id="0a8b5-163">You can see the time it was last updated in the **Updated** column of the **Predictions** page.</span></span>

## <a name="edit-a-prediction"></a><span data-ttu-id="0a8b5-164">Болжамды өңдеу</span><span class="sxs-lookup"><span data-stu-id="0a8b5-164">Edit a prediction</span></span>

<span data-ttu-id="0a8b5-165">Болжамды жасаған соң, үлгінің тиімділігін арттыру үшін AI Builder құралында үлгіні теңшей аласыз.</span><span class="sxs-lookup"><span data-stu-id="0a8b5-165">After you've created a prediction, you can customize the model in the AI Builder to increase the effectiveness of your model.</span></span>  

1. <span data-ttu-id="0a8b5-166">Аудитория мәліметтерінде **Сараптау** > **Болжамдар** > **Менің болжамдарым** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="0a8b5-166">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="0a8b5-167">Өңдеу керек болжамды таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="0a8b5-167">Select the prediction you want to edit.</span></span>

3. <span data-ttu-id="0a8b5-168">**Әрекеттер** бағанынан көп нүктені таңдап, **Көрініс** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="0a8b5-168">Select the ellipsis in the **Actions** column and choose **View**.</span></span>

4. <span data-ttu-id="0a8b5-169">**AI Builder бағдарламасында теңшеу** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="0a8b5-169">Select **Customize in AI Builder**.</span></span>

5. <span data-ttu-id="0a8b5-170">AI Builder бағдарламасында үлгіні жаңартыңыз.</span><span class="sxs-lookup"><span data-stu-id="0a8b5-170">Update your model in the AI Builder.</span></span> <span data-ttu-id="0a8b5-171">[AI builder бағдарламасында үлгілерді басқару туралы қосымша ақпарат](https://docs.microsoft.com/ai-builder/manage-model#retrain-and-republish-existing-models).</span><span class="sxs-lookup"><span data-stu-id="0a8b5-171">[Learn more about managing models in the AI builder](https://docs.microsoft.com/ai-builder/manage-model#retrain-and-republish-existing-models).</span></span>

<span data-ttu-id="0a8b5-172">Болжамды келесі рет іске қосқанда сіз жасаған жаңартылған үлгі қолданылады.</span><span class="sxs-lookup"><span data-stu-id="0a8b5-172">The next run of your prediction will use the updated model you've created.</span></span>

> [!NOTE]
> <span data-ttu-id="0a8b5-173">AI Builder өнімінде жасалған жаңа үлгілер жоғарыда келтірілген тәжірибелер негізінде жасалмаса, аудитория мәліметтерінде көрсетілмейді.</span><span class="sxs-lookup"><span data-stu-id="0a8b5-173">New models created in AI Builder will not be displayed in audience insights unless the model was created from the experiences listed above.</span></span>

## <a name="remove-a-prediction"></a><span data-ttu-id="0a8b5-174">Болжамды жою</span><span class="sxs-lookup"><span data-stu-id="0a8b5-174">Remove a prediction</span></span>

1. <span data-ttu-id="0a8b5-175">Аудитория мәліметтерінде **Сараптау** > **Болжамдар** > **Менің болжамдарым** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="0a8b5-175">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="0a8b5-176">Жою керек болжамды таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="0a8b5-176">Select the prediction you want to delete.</span></span>

3. <span data-ttu-id="0a8b5-177">**Әрекеттер** бағанынан көп нүктені таңдап, **Жою** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="0a8b5-177">Select the ellipsis in the **Actions** column and choose **Delete**.</span></span>

4. <span data-ttu-id="0a8b5-178">Жоюды растаңыз.</span><span class="sxs-lookup"><span data-stu-id="0a8b5-178">Confirm the deletion.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="0a8b5-179">Ақауларды жою</span><span class="sxs-lookup"><span data-stu-id="0a8b5-179">Troubleshooting</span></span>

<span data-ttu-id="0a8b5-180">Егер Common Data Service процесін тіркеуді қатеге байланысты аяқтай алмасаңыз, оны қолмен аяқтауға болады.</span><span class="sxs-lookup"><span data-stu-id="0a8b5-180">If you can't complete the attach Common Data Service process due to an error, you can try to complete the process manually.</span></span> <span data-ttu-id="0a8b5-181">Тіркеу процесінде орын алуы мүмкін екі белгілі мәселе бар:</span><span class="sxs-lookup"><span data-stu-id="0a8b5-181">There are two known issues that can occur in the attach process:</span></span>

- <span data-ttu-id="0a8b5-182">Тұтынушы картасының қондырмасы шешімі орнатылмаған.</span><span class="sxs-lookup"><span data-stu-id="0a8b5-182">The Customer Card Add-in solution is not installed.</span></span>
    1. <span data-ttu-id="0a8b5-183">[Шешімді орнату және конфигурациялау үшін](customer-card-add-in.md) нұсқауларды орындаңыз.</span><span class="sxs-lookup"><span data-stu-id="0a8b5-183">Complete the instructions to [install and configure the solution](customer-card-add-in.md).</span></span>

- <span data-ttu-id="0a8b5-184">Бағдарлама рұқсаттары ұсынылмаған.</span><span class="sxs-lookup"><span data-stu-id="0a8b5-184">App permissions aren't granted.</span></span>
    1. <span data-ttu-id="0a8b5-185">[https://admin.powerplatform.microsoft.com](https://admin.powerplatform.microsoft.com) торабына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="0a8b5-185">Go to [https://admin.powerplatform.microsoft.com](https://admin.powerplatform.microsoft.com).</span></span>
    1. <span data-ttu-id="0a8b5-186">**Орталар** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="0a8b5-186">Select **Environments**.</span></span>
    1. <span data-ttu-id="0a8b5-187">Шешімді қосу керек ортаның жанындағы көп нүктені таңдаңыз және **Параметрлер** түймесін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="0a8b5-187">Select the ellipsis next to the environment you want to add the permission to and select **Settings**.</span></span>
    1. <span data-ttu-id="0a8b5-188">**Пайдаланушылар + рұқсаттар** бөлімін кеңейтіңіз және **Пайдаланушылар** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="0a8b5-188">Expand **Users + permissions** and select **Users**.</span></span>
    1. <span data-ttu-id="0a8b5-189">**+ Жаңа** параметрін және **Пайдаланушылар** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="0a8b5-189">Select **+ New** and select **User**.</span></span>
    1. <span data-ttu-id="0a8b5-190">Таңдалмаған болса **Бағдарлама пайдаланушысы** параметрін таңдаңыз және келесі ақпаратты енгізіңіз:</span><span class="sxs-lookup"><span data-stu-id="0a8b5-190">Select **Application User** if it's not already selected and enter the following information:</span></span>
        - <span data-ttu-id="0a8b5-191">**Пайдаланушы аты:** cihelp@microsoft.com</span><span class="sxs-lookup"><span data-stu-id="0a8b5-191">**User Name:** cihelp@microsoft.com</span></span>
        - <span data-ttu-id="0a8b5-192">**Бағдарлама идентификаторы:** 38c77d00-5fcb-4cce-9d93-af4738258e3c</span><span class="sxs-lookup"><span data-stu-id="0a8b5-192">**Application ID:** 38c77d00-5fcb-4cce-9d93-af4738258e3c</span></span>
        - <span data-ttu-id="0a8b5-193">**Аты:** тұтынушы</span><span class="sxs-lookup"><span data-stu-id="0a8b5-193">**First Name:** Customer</span></span>
        - <span data-ttu-id="0a8b5-194">**Тегі:** аналитикалық деректер</span><span class="sxs-lookup"><span data-stu-id="0a8b5-194">**Last Name:** Insights</span></span>
        - <span data-ttu-id="0a8b5-195">**Негізгі электрондық пошта:** cihelp@microsoft.com</span><span class="sxs-lookup"><span data-stu-id="0a8b5-195">**Primary Email:** cihelp@microsoft.com</span></span>
    1. <span data-ttu-id="0a8b5-196">**Сақтау және жабу** пәрменін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="0a8b5-196">Select **Save & Close**.</span></span>
    1. <span data-ttu-id="0a8b5-197">Өзіңіз жасаған пайдаланушыны таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="0a8b5-197">Select the user you just created.</span></span>
    1. <span data-ttu-id="0a8b5-198">Жоғарғы мәзір жолағында **Рөлдерді басқару** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="0a8b5-198">Select **Manage Roles** in the top menu bar.</span></span>
    1. <span data-ttu-id="0a8b5-199">**Жүйе әкімшісі**, содан кейін **OK** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="0a8b5-199">Select **System Administrator**, then select **OK**.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]