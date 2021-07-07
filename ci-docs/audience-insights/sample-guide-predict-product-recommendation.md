---
title: Өнім ұсынысының болжамы бойынша нұсқаулық үлгісі
description: Кірістірілген өнім ұсынысы болжамының үлгісін байқап көру үшін осы үлгі нұсқаулығын пайдаланыңыз.
ms.date: 02/10/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: a85ee598ec747d0594755314e83a127ce0f2af95
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 06/24/2021
ms.locfileid: "6306173"
---
# <a name="product-recommendation-prediction-preview-sample-guide"></a><span data-ttu-id="50643-103">Өнім ұсынысының болжамы (алдын ала қарау) бойынша нұсқаулық үлгісі</span><span class="sxs-lookup"><span data-stu-id="50643-103">Product recommendation prediction (preview) sample guide</span></span>

<span data-ttu-id="50643-104">Біз сізге төменде берілген үлгі деректерін пайдаланып, өнім ұсынысы болжамының мысалын басынан аяғына дейін түсіндіреміз.</span><span class="sxs-lookup"><span data-stu-id="50643-104">We'll walk you through an end to end example of product recommendation prediction using the sample data provided below.</span></span>

## <a name="scenario"></a><span data-ttu-id="50643-105">Сценарий</span><span class="sxs-lookup"><span data-stu-id="50643-105">Scenario</span></span>

<span data-ttu-id="50643-106">Contoso — бұл жоғары сапалы кофе және кофе машиналарын шығаратын және оларды Contoso Coffee веб-сайты арқылы сататын компания.</span><span class="sxs-lookup"><span data-stu-id="50643-106">Contoso is a company that produces high-quality coffee and coffee machines, which they sell through their Contoso Coffee website.</span></span> <span data-ttu-id="50643-107">Олардың мақсаты - тұрақты тұтынушыларға қандай өнімдерді ұсыну керектігін түсіну.</span><span class="sxs-lookup"><span data-stu-id="50643-107">Their goal is to understand which products should they recommend to their recurring customers.</span></span> <span data-ttu-id="50643-108">Қандай тұтынушылардың **сатып алу ықтималдығы** жоғары екендігін білу оларға нақты элементтерге назар аудара отырып, маркетингтік күш-жігерді үнемдеуге көмектеседі.</span><span class="sxs-lookup"><span data-stu-id="50643-108">Knowing what customers are more **likely to purchase**, can help them save marketing efforts by focusing on specific items.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="50643-109">Алғышарттар</span><span class="sxs-lookup"><span data-stu-id="50643-109">Prerequisites</span></span>

- <span data-ttu-id="50643-110">Customer Insights бағдарламасында кемінде [Салымшы рұқсаттары](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="50643-110">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>
- <span data-ttu-id="50643-111">[Жаңа ортадағы](manage-environments.md) келесі қадамдарды орындауға кеңес береміз.</span><span class="sxs-lookup"><span data-stu-id="50643-111">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="50643-112">1-тапсырма – деректерді қабылдау</span><span class="sxs-lookup"><span data-stu-id="50643-112">Task 1 - Ingest data</span></span>

<span data-ttu-id="50643-113">[Деректерді қабылдау](data-sources.md) және [Power Query қосқыштарының көмегімен деректер көздерін импорттау туралы](connect-power-query.md) арнайы мақалаларды қарап шығыңыз.</span><span class="sxs-lookup"><span data-stu-id="50643-113">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md) specifically.</span></span> <span data-ttu-id="50643-114">Төмендегі ақпарат қабылданатын деректермен жалпылама танысқаныңызды болжайды.</span><span class="sxs-lookup"><span data-stu-id="50643-114">The following information assumes you familiarized with ingesting data in general.</span></span>

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="50643-115">eCommerce платформасынан тұтынушы деректерін қабылдау</span><span class="sxs-lookup"><span data-stu-id="50643-115">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="50643-116">**eCommerce** атты деректер көзін жасаңыз, импорттау опциясын таңдаңыз және **Мәтін/CSV** қосқышын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="50643-116">Create a data source named **eCommerce**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="50643-117">eCommerce контактілері үшін URL мекенжайын енгізіңіз https://aka.ms/ciadclasscontacts.</span><span class="sxs-lookup"><span data-stu-id="50643-117">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscontacts.</span></span>

1. <span data-ttu-id="50643-118">Деректерді өңдеу кезінде **Түрлендіру**, одан кейін **Бірінші жолды тақырып ретінде пайдалану** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="50643-118">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="50643-119">Төменде берілген бағандар үшін деректер түрін жаңартыңыз:</span><span class="sxs-lookup"><span data-stu-id="50643-119">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="50643-120">**Туған күні**: күні</span><span class="sxs-lookup"><span data-stu-id="50643-120">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="50643-121">**Жасалған уақыты**: күн/уақыт/белдеу</span><span class="sxs-lookup"><span data-stu-id="50643-121">**CreatedOn**: Date/Time/Zone</span></span>

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Туған күнін күнге түрлендіру.":::

5. <span data-ttu-id="50643-123">Оң жақ тақтадағы 'Атау' өрісінде деректер көзі атауын **Сұрау** атауынан **eCommerce контактілері** атауына өзгертіңіз</span><span class="sxs-lookup"><span data-stu-id="50643-123">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

6. <span data-ttu-id="50643-124">Деректерін көзін **Сақтау** опциясы арқылы сақтаңыз.</span><span class="sxs-lookup"><span data-stu-id="50643-124">**Save** the data source.</span></span>

### <a name="ingest-online-purchase-data"></a><span data-ttu-id="50643-125">Онлайн сатып алу деректерін қабылдау</span><span class="sxs-lookup"><span data-stu-id="50643-125">Ingest online purchase data</span></span>

1. <span data-ttu-id="50643-126">Бір **eCommerce** деректер көзіне басқа деректер жиынтығын қосыңыз.</span><span class="sxs-lookup"><span data-stu-id="50643-126">Add another data set to the same **eCommerce** data source.</span></span> <span data-ttu-id="50643-127">**Мәтін/CSV** қосқышын қайтадан таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="50643-127">Choose the **Text/CSV** connector again.</span></span>

1. <span data-ttu-id="50643-128">**Онлайн сатып алулар** деректері үшін URL мекенжайын енгізіңіз https://aka.ms/ciadclassonline.</span><span class="sxs-lookup"><span data-stu-id="50643-128">Enter the URL for **Online Purchases** data https://aka.ms/ciadclassonline.</span></span>

1. <span data-ttu-id="50643-129">Деректерді өңдеу кезінде **Түрлендіру**, одан кейін **Бірінші жолды тақырып ретінде пайдалану** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="50643-129">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="50643-130">Төменде берілген бағандар үшін деректер түрін жаңартыңыз:</span><span class="sxs-lookup"><span data-stu-id="50643-130">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="50643-131">**Сатып алынған күні**: күн/уақыт</span><span class="sxs-lookup"><span data-stu-id="50643-131">**PurchasedOn**: Date/Time</span></span>
   - <span data-ttu-id="50643-132">**Жалпы бағасы**: валюта</span><span class="sxs-lookup"><span data-stu-id="50643-132">**TotalPrice**: Currency</span></span>

1. <span data-ttu-id="50643-133">Бүйірлік тақтадағы **Атауы** өрісінде деректер көзі атауын **Сұрау** атауынан **eCommerce сатып алулары** атауына өзгертіңіз.</span><span class="sxs-lookup"><span data-stu-id="50643-133">In the **Name** field on the side pane, rename your data source from **Query** to **eCommercePurchases**.</span></span>

1. <span data-ttu-id="50643-134">Деректерін көзін **Сақтау** опциясы арқылы сақтаңыз.</span><span class="sxs-lookup"><span data-stu-id="50643-134">**Save** the data source.</span></span>


### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="50643-135">Тұтынушы деректерін адалдық схемасынан қабылдау</span><span class="sxs-lookup"><span data-stu-id="50643-135">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="50643-136">**Адалдық схемасы** атты деректер көзін жасаңыз, импорттау опциясын таңдаңыз және **Мәтін/CSV** қосқышын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="50643-136">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="50643-137">eCommerce контактілері үшін URL мекенжайын енгізіңіз https://aka.ms/ciadclasscustomerloyalty.</span><span class="sxs-lookup"><span data-stu-id="50643-137">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="50643-138">Деректерді өңдеу кезінде **Түрлендіру**, одан кейін **Бірінші жолды тақырып ретінде пайдалану** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="50643-138">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="50643-139">Төменде берілген бағандар үшін деректер түрін жаңартыңыз:</span><span class="sxs-lookup"><span data-stu-id="50643-139">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="50643-140">**Туған күні**: күні</span><span class="sxs-lookup"><span data-stu-id="50643-140">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="50643-141">**Марапаттар ұпайлары**: бүтін сан</span><span class="sxs-lookup"><span data-stu-id="50643-141">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="50643-142">**Жасалған уақыты**: күн/уақыт</span><span class="sxs-lookup"><span data-stu-id="50643-142">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="50643-143">Оң жақ тақтадағы **Атауы** өрісінде деректер көзі атауын **Сұрау** атауынан **адалдық тұтынушылары** атауына өзгертіңіз.</span><span class="sxs-lookup"><span data-stu-id="50643-143">In the **Name** field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="50643-144">Деректерін көзін **Сақтау** опциясы арқылы сақтаңыз.</span><span class="sxs-lookup"><span data-stu-id="50643-144">**Save** the data source.</span></span>

## <a name="task-2---data-unification"></a><span data-ttu-id="50643-145">2-тапсырма – деректерді біріктіру</span><span class="sxs-lookup"><span data-stu-id="50643-145">Task 2 - Data unification</span></span>

<span data-ttu-id="50643-146">Деректерді қабылдағаннан кейін біз енді тұтынушылардың бірыңғай профилін жасау үшін деректерді біріздендіру процесін бастаймыз.</span><span class="sxs-lookup"><span data-stu-id="50643-146">After ingesting the data, we now begin the data unification process to create a unified customer profile.</span></span> <span data-ttu-id="50643-147">Қосымша ақпарат алу үшін [Деректерді біріктіру](data-unification.md) бөлімін қараңыз.</span><span class="sxs-lookup"><span data-stu-id="50643-147">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="50643-148">Картаға түсіру</span><span class="sxs-lookup"><span data-stu-id="50643-148">Map</span></span>

1. <span data-ttu-id="50643-149">Деректерді қабылдағаннан кейін, eCommerce және адалдық деректеріндегі контактілерді жалпы деректер түрлерімен салыстырыңыз.</span><span class="sxs-lookup"><span data-stu-id="50643-149">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="50643-150">**Деректер** > **Біріктіру** > **Салыстыру** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="50643-150">Go to **Data** > **Unify** > **Map**.</span></span>

2. <span data-ttu-id="50643-151">Тұтынушы профилін ұсынатын нысандарды таңдаңыз – **eCommerce контактілері** және **адалдық тұтынушылары**.</span><span class="sxs-lookup"><span data-stu-id="50643-151">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span>

   ![ecommerce және адалдық деректер көздерін біріктіру.](media/unify-ecommerce-loyalty.png)

3. <span data-ttu-id="50643-153">**eCommerce контактілері** үшін негізгі кілт ретінде **Контакт идентификаторы** кілтін, ал **адалдық тұтынушылары** үшін негізгі кілт ретінде **Адалдық идентификаторы** кілтін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="50643-153">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   ![Адалдық идентификаторын негізгі кілт ретінде біріктіру.](media/unify-loyaltyid.png)

### <a name="match"></a><span data-ttu-id="50643-155">Сәйкестендіру</span><span class="sxs-lookup"><span data-stu-id="50643-155">Match</span></span>

1. <span data-ttu-id="50643-156">**Сәйкестендіру** қойыншасына өтіп **Орнату реті** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="50643-156">Go to the **Match** tab and select **Set Order**.</span></span>

2. <span data-ttu-id="50643-157">**Негізгі** ашылмалы тізімінде **eCommerce байланыстары: eCommerce** нысанын негізгі дереккөзі ретінде таңдаңыз және барлық жазбаларды қосыңыз.</span><span class="sxs-lookup"><span data-stu-id="50643-157">In the **Primary** dropdown list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

3. <span data-ttu-id="50643-158">**2 нысан** ашылмалы тізімінде **loyCustomers: LoyaltyScheme** нысанын таңдаңыз және барлық жазбаларды қосыңыз.</span><span class="sxs-lookup"><span data-stu-id="50643-158">In the **Entity 2** dropdown list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   ![Сәйкес eCommerce және адалдықты біріктіру.](media/unify-match-order.png)

4. <span data-ttu-id="50643-160">**Жаңа ереже жасау** опциясын таңдаңыз</span><span class="sxs-lookup"><span data-stu-id="50643-160">Select **Create a new rule**</span></span>

5. <span data-ttu-id="50643-161">Аты-жөні опциясы көмегімен алғашқы шартты қосыңыз.</span><span class="sxs-lookup"><span data-stu-id="50643-161">Add your first condition using FullName.</span></span>

   - <span data-ttu-id="50643-162">eCommerceContacts нысаны үшін ашылмалы тізімнен **FullName** өрісін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="50643-162">For eCommerceContacts select **FullName** in the dropdown.</span></span>
   - <span data-ttu-id="50643-163">loyCustomers нысаны үшін ашылмалы тізімнен **FullName** өрісін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="50643-163">For loyCustomers select **FullName** in the dropdown.</span></span>
   - <span data-ttu-id="50643-164">**Нормалдау** ашылмалы мәзірін таңдаңыз да, **Теру (телефон, аты, мекен-жайы, ...)** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="50643-164">Select the **Normalize** drop down and choose **Type (Phone, Name, Address, ...)**.</span></span>
   - <span data-ttu-id="50643-165">**Дәлдік деңгейі** мәнін орнатыңыз: **Негізгі** және **Мән** : **Жоғары**.</span><span class="sxs-lookup"><span data-stu-id="50643-165">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

6. <span data-ttu-id="50643-166">Жаңа ереже үшін **Аты-жөні, электрондық пошта** атауын енгіңіз.</span><span class="sxs-lookup"><span data-stu-id="50643-166">Enter the name **FullName, Email** for the new rule.</span></span>

   - <span data-ttu-id="50643-167">**Шарт қосу** опциясын таңдау арқылы электрондық пошта мекенжайына екінші шарт қосу</span><span class="sxs-lookup"><span data-stu-id="50643-167">Add a second condition for email address by selecting **Add Condition**</span></span>
   - <span data-ttu-id="50643-168">eCommerceContacts нысаны үшін ашылмалы тізімнен **EMail** өрісін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="50643-168">For entity eCommerceContacts, choose **EMail** in dropdown.</span></span>
   - <span data-ttu-id="50643-169">loyCustomers нысаны үшін ашылмалы тізімнен **EMail** өрісін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="50643-169">For entity loyCustomers, choose **EMail** in the dropdown.</span></span>
   - <span data-ttu-id="50643-170">Нормалдау өрісін бос қалдырыңыз.</span><span class="sxs-lookup"><span data-stu-id="50643-170">Leave Normalize blank.</span></span>
   - <span data-ttu-id="50643-171">**Дәлдік деңгейі** мәнін орнатыңыз: **Негізгі** және **Мән** : **Жоғары**.</span><span class="sxs-lookup"><span data-stu-id="50643-171">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   ![Атауы мен электрондық поштасы үшін сәйкестік ережесін біріктіру.](media/unify-match-rule.png)

7. <span data-ttu-id="50643-173">**Сақтау** және **Іске қосу** опцияларын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="50643-173">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="50643-174">Біріктіру</span><span class="sxs-lookup"><span data-stu-id="50643-174">Merge</span></span>

1. <span data-ttu-id="50643-175">**Біріктіру** қойыншасына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="50643-175">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="50643-176">**Адалдық тұтынушылары** нысанына арналған **Контакт идентификаторы** нысанында көрсетілетін атауды басқа идентификаторлардан ажырату үшін **Контакт идентификаторы АДАЛДЫҚ** атауына өзгертіңіз.</span><span class="sxs-lookup"><span data-stu-id="50643-176">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   ![контакт идентификаторы атауынан адалдық идентификаторы атауына өзгерту.](media/unify-merge-contactid.png)

1. <span data-ttu-id="50643-178">Біріктіру процесін бастау үшін **Сақтау** және **Іске қосу** опцияларын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="50643-178">Select **Save** and **Run** to start the Merge Process.</span></span>

## <a name="task-3---configure-product-recommendation-prediction"></a><span data-ttu-id="50643-179">3-тапсырма - Өнім ұсынысының болжамын конфигурациялау</span><span class="sxs-lookup"><span data-stu-id="50643-179">Task 3 - Configure product recommendation prediction</span></span>

<span data-ttu-id="50643-180">Бірыңғай тұтынушы профильдерімен біз енді жазылымдардың кетуін болжай аламыз.</span><span class="sxs-lookup"><span data-stu-id="50643-180">With the unified customer profiles in place, we can now run the subscription churn prediction.</span></span>

1. <span data-ttu-id="50643-181">**Сараптау** > **Болжам** тармағына өтіп, **Өнім ұсынысы** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="50643-181">Go to **Intelligence** > **Prediction** choose **Product recommendation**.</span></span>

1. <span data-ttu-id="50643-182">**Жұмысты бастау** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="50643-182">Select **Get started**.</span></span>

1. <span data-ttu-id="50643-183">**OOB өнім ұсынысы үлгісінің болжамы** үлгісінің және **OOBProductRecommendationModelPrediction** нысанының атауын енгізіңіз.</span><span class="sxs-lookup"><span data-stu-id="50643-183">Name the model **OOB Product Recommendation Model Prediction** and the output entity **OOBProductRecommendationModelPrediction**.</span></span>

1. <span data-ttu-id="50643-184">Үлгінің үш шартын анықтаңыз:</span><span class="sxs-lookup"><span data-stu-id="50643-184">Define three conditions for the model:</span></span>

   - <span data-ttu-id="50643-185">**Өнімдер саны**: бұл мәнді **5** мәніне орнатыңыз.</span><span class="sxs-lookup"><span data-stu-id="50643-185">**Number of products**: Set this value to **5**.</span></span> <span data-ttu-id="50643-186">Бұл параметр сіздің тұтынушыларыңызға қанша өнім ұсынғыңыз келетінін анықтайды.</span><span class="sxs-lookup"><span data-stu-id="50643-186">This setting defines how many products you want to recommend to your customers.</span></span>

   - <span data-ttu-id="50643-187">**Күтілетін қайта сатып алулар**: сіздің тұтынушыларыңыз бұрын сатып алған ұсыныстарға өнімдерді қосу керектігін көрсету үшін **Иә** мәнін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="50643-187">**Repeat purchases expected**: Select **Yes** to indicate that you want to include products in the recommendation that your customers have purchased before.</span></span>

   - <span data-ttu-id="50643-188">**Ретроспективті шолу терезесі**: кем дегенде **365 күн** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="50643-188">**Look back window:** Select at least **365 days**.</span></span> <span data-ttu-id="50643-189">Бұл параметр ұсыныстарға кіріс ретінде пайдалану үшін үлгінің тұтынушы әрекетіне қаншалықты терең ретроспективті шолу жасайтынын анықтайды.</span><span class="sxs-lookup"><span data-stu-id="50643-189">This setting defines how far the model will look back at the customer's activity to use it as input to their recommendations.</span></span>
   
   :::image type="content" source="media/product-recommendation-model-preferences.png" alt-text="Өнімнің ұсыныс үлгісіне арналған үлгі параметрлері.":::

1. <span data-ttu-id="50643-191">**Қажетті деректер** опциясын таңдап, сатып алу тарихы үшін **Деректер қосу** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="50643-191">Select **Required data** and select **Add data** for purchase history.</span></span>

1. <span data-ttu-id="50643-192">**eCommerce сатып алулары: eCommerce** нысанын қосыңыз және eCommerce өрістерін үлгі талап ететін тиісті өрістермен салыстырыңыз.</span><span class="sxs-lookup"><span data-stu-id="50643-192">Add the **eCommercePurchases : eCommerce** entity and map the fields from eCommerce to the corresponding fields required by the model.</span></span>

1. <span data-ttu-id="50643-193">**eCommerce сатып алулары: eCommerce** нысанына **eCommerce конатктілері: eCommerce** нысанымен қосылыңыз.</span><span class="sxs-lookup"><span data-stu-id="50643-193">Join the **eCommercePurchases : eCommerce** entity with **eCommerceContacts : eCommerce**.</span></span>

   ![eCommerce нысандарына қосылу.](media/model-purchase-join.png)

1. <span data-ttu-id="50643-195">Үлгі кестесін орнату үшін **Келесі** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="50643-195">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="50643-196">Үлгіге жаңа деректер түскен кезде жаңа мысалдарды білу үшін үнемі жаттығу керек.</span><span class="sxs-lookup"><span data-stu-id="50643-196">The model needs to train regularly to learn new patterns when there is new data ingested.</span></span> <span data-ttu-id="50643-197">Осы мысал үшін **Ай сайын** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="50643-197">For this example, select **Monthly**.</span></span>

1. <span data-ttu-id="50643-198">Барлық мәліметтерді қарап шыққаннан кейін **Сақтау және іске қосу** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="50643-198">After reviewing all the details, select **Save and Run**.</span></span>


## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="50643-199">4-тапсырма – үлгі нәтижелері мен түсіндірмелерін қарап шығу</span><span class="sxs-lookup"><span data-stu-id="50643-199">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="50643-200">Үлгі жаттығуды аяқтап, деректерді бағалауды жүргізсін.</span><span class="sxs-lookup"><span data-stu-id="50643-200">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="50643-201">Енді өнім ұсынысы үлгісінің түсіндірмелерін қарап шығуға болады.</span><span class="sxs-lookup"><span data-stu-id="50643-201">You can now review the product recommendation model explanations.</span></span> <span data-ttu-id="50643-202">Қосымша ақпарат алу үшін [Болжам күйі мен нәтижелерін қарап шығу](predict-subscription-churn.md#review-a-prediction-status-and-results) бөлімін қараңыз.</span><span class="sxs-lookup"><span data-stu-id="50643-202">For more information, see [Review a prediction status and results](predict-subscription-churn.md#review-a-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-purchased-products"></a><span data-ttu-id="50643-203">5-тапсырма - Жоғары сатып алынған өнімдердің сегментін жасау</span><span class="sxs-lookup"><span data-stu-id="50643-203">Task 5 - Create a segment of high purchased products</span></span>

<span data-ttu-id="50643-204">Өндіріс үлгісін іске қосу **Деректер** > **Нысандар** тармағында көре алатын жаңа нысанды жасайды.</span><span class="sxs-lookup"><span data-stu-id="50643-204">Running the production model creates a new entity that you can see in **Data** > **Entities**.</span></span>

<span data-ttu-id="50643-205">Үлгі жасаған нысан негізінде жаңа сегмент жасауға болады.</span><span class="sxs-lookup"><span data-stu-id="50643-205">You can create a new segment based on the entity created by the model.</span></span>

1. <span data-ttu-id="50643-206">**Сегменттер** бетіне өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="50643-206">Go to **Segments**.</span></span> <span data-ttu-id="50643-207">**Жаңа** опциясын таңдаңыз да, **Келесіден жасау** > **Интеллект** тармағын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="50643-207">Select **New** and choose **Create from** > **Intelligence**.</span></span>

   ![Үлгі шығысымен сегмент жасау.](media/segment-intelligence.png)

1. <span data-ttu-id="50643-209">**OOBProductRecommendationModelPrediction** соңғы нүктесін таңдап, сегментті анықтаңыз:</span><span class="sxs-lookup"><span data-stu-id="50643-209">Select the **OOBProductRecommendationModelPrediction** endpoint and define the segment:</span></span>

   - <span data-ttu-id="50643-210">Өріс: өнім идентификаторы</span><span class="sxs-lookup"><span data-stu-id="50643-210">Field: ProductID</span></span>
   - <span data-ttu-id="50643-211">Оператор: мәні</span><span class="sxs-lookup"><span data-stu-id="50643-211">Operator: Value</span></span>
   - <span data-ttu-id="50643-212">Мән: өнімнің ең маңызды үш идентификаторын таңдаңыз</span><span class="sxs-lookup"><span data-stu-id="50643-212">Value: Select the top three product IDs</span></span>

   :::image type="content" source="media/product-recommendation-quick-segment.png" alt-text="Үлгі нәтижелерінен сегмент жасаңыз.":::

<span data-ttu-id="50643-214">Енді сізде ең көп ұсынылған үш өнімді сатып алуға дайын тұтынушыларды анықтайтын динамикалық жаңартылған сегмент бар</span><span class="sxs-lookup"><span data-stu-id="50643-214">You now have a segment that is dynamically updated which identifies the customers who are more willing to purchase the three most recommended products</span></span> 

<span data-ttu-id="50643-215">Қосымша ақпаратты [Сегменттерді жасау және басқару](segments.md) бөлімінен қараңыз.</span><span class="sxs-lookup"><span data-stu-id="50643-215">For more information, see [Create and manage segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
