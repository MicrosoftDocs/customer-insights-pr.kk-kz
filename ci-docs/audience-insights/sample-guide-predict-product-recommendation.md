---
title: Өнім ұсынысының болжамы бойынша нұсқаулық үлгісі
description: Кірістірілген өнім ұсынысы болжамының үлгісін байқап көру үшін осы үлгі нұсқаулығын пайдаланыңыз.
ms.date: 02/10/2021
ms.reviewer: digranad
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 0ee873d9b7caa5f891cb2d5b8c665dec90ad0e59
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270508"
---
# <a name="product-recommendation-prediction-preview-sample-guide"></a><span data-ttu-id="a8e56-103">Өнім ұсынысының болжамы (алдын ала қарау) бойынша нұсқаулық үлгісі</span><span class="sxs-lookup"><span data-stu-id="a8e56-103">Product recommendation prediction (preview) sample guide</span></span>

<span data-ttu-id="a8e56-104">Біз сізге төменде берілген үлгі деректерін пайдаланып, өнім ұсынысы болжамының мысалын басынан аяғына дейін түсіндіреміз.</span><span class="sxs-lookup"><span data-stu-id="a8e56-104">We'll walk you through an end to end example of product recommendation prediction using the sample data provided below.</span></span>

## <a name="scenario"></a><span data-ttu-id="a8e56-105">Сценарий</span><span class="sxs-lookup"><span data-stu-id="a8e56-105">Scenario</span></span>

<span data-ttu-id="a8e56-106">Contoso — бұл жоғары сапалы кофе және кофеқайнатқыштарын шығаратын, оларды Contoso Coffee веб-сайты арқылы сататын компания.</span><span class="sxs-lookup"><span data-stu-id="a8e56-106">Contoso is a company that produces high-quality coffee and coffee machines, which they sell through their Contoso Coffee website.</span></span> <span data-ttu-id="a8e56-107">Олардың мақсаты - тұрақты тұтынушыларға қандай өнімдерді ұсыну керектігін түсіну.</span><span class="sxs-lookup"><span data-stu-id="a8e56-107">Their goal is to understand which products should they recommend to their recurring customers.</span></span> <span data-ttu-id="a8e56-108">Қандай тұтынушылардың **сатып алу ықтималдығы** жоғары екендігін білу оларға нақты элементтерге назар аудара отырып, маркетингтік күш-жігерді үнемдеуге көмектеседі.</span><span class="sxs-lookup"><span data-stu-id="a8e56-108">Knowing what customers are more **likely to purchase**, can help them save marketing efforts by focusing on specific items.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="a8e56-109">Алғышарттар</span><span class="sxs-lookup"><span data-stu-id="a8e56-109">Prerequisites</span></span>

- <span data-ttu-id="a8e56-110">Customer Insights бағдарламасында кемінде [Салымшы рұқсаттары](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="a8e56-110">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>
- <span data-ttu-id="a8e56-111">[Жаңа ортадағы](manage-environments.md) келесі қадамдарды орындауға кеңес береміз.</span><span class="sxs-lookup"><span data-stu-id="a8e56-111">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="a8e56-112">1-тапсырма – деректерді қабылдау</span><span class="sxs-lookup"><span data-stu-id="a8e56-112">Task 1 - Ingest data</span></span>

<span data-ttu-id="a8e56-113">[Деректерді қабылдау](data-sources.md) және [Power Query қосқыштарының көмегімен деректер көздерін импорттау туралы](connect-power-query.md) арнайы мақалаларды қарап шығыңыз.</span><span class="sxs-lookup"><span data-stu-id="a8e56-113">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md) specifically.</span></span> <span data-ttu-id="a8e56-114">Төмендегі ақпарат қабылданатын деректермен жалпылама танысқаныңызды болжайды.</span><span class="sxs-lookup"><span data-stu-id="a8e56-114">The following information assumes you familiarized with ingesting data in general.</span></span>

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="a8e56-115">eCommerce платформасынан тұтынушы деректерін қабылдау</span><span class="sxs-lookup"><span data-stu-id="a8e56-115">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="a8e56-116">**eCommerce** атты деректер көзін жасаңыз, импорттау опциясын таңдаңыз және **Мәтін/CSV** қосқышын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="a8e56-116">Create a data source named **eCommerce**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="a8e56-117">eCommerce контактілері үшін URL мекенжайын енгізіңіз https://aka.ms/ciadclasscontacts.</span><span class="sxs-lookup"><span data-stu-id="a8e56-117">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscontacts.</span></span>

1. <span data-ttu-id="a8e56-118">Деректерді өңдеу кезінде **Түрлендіру**, одан кейін **Бірінші жолды тақырып ретінде пайдалану** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="a8e56-118">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="a8e56-119">Төменде берілген бағандар үшін деректер түрін жаңартыңыз:</span><span class="sxs-lookup"><span data-stu-id="a8e56-119">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="a8e56-120">**Туған күні**: күні</span><span class="sxs-lookup"><span data-stu-id="a8e56-120">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="a8e56-121">**Жасалған уақыты**: күн/уақыт/белдеу</span><span class="sxs-lookup"><span data-stu-id="a8e56-121">**CreatedOn**: Date/Time/Zone</span></span>

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Туған күнін күнге түрлендіру.":::

5. <span data-ttu-id="a8e56-123">Оң жақ тақтадағы 'Атау' өрісінде деректер көзі атауын **Сұрау** атауынан **eCommerce контактілері** атауына өзгертіңіз</span><span class="sxs-lookup"><span data-stu-id="a8e56-123">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

6. <span data-ttu-id="a8e56-124">Деректерін көзін **Сақтау** опциясы арқылы сақтаңыз.</span><span class="sxs-lookup"><span data-stu-id="a8e56-124">**Save** the data source.</span></span>

### <a name="ingest-online-purchase-data"></a><span data-ttu-id="a8e56-125">Онлайн сатып алу деректерін қабылдау</span><span class="sxs-lookup"><span data-stu-id="a8e56-125">Ingest online purchase data</span></span>

1. <span data-ttu-id="a8e56-126">Бір **eCommerce** деректер көзіне басқа деректер жиынтығын қосыңыз.</span><span class="sxs-lookup"><span data-stu-id="a8e56-126">Add another data set to the same **eCommerce** data source.</span></span> <span data-ttu-id="a8e56-127">**Мәтін/CSV** қосқышын қайтадан таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="a8e56-127">Choose the **Text/CSV** connector again.</span></span>

1. <span data-ttu-id="a8e56-128">**Онлайн сатып алулар** деректері үшін URL мекенжайын енгізіңіз https://aka.ms/ciadclassonline.</span><span class="sxs-lookup"><span data-stu-id="a8e56-128">Enter the URL for **Online Purchases** data https://aka.ms/ciadclassonline.</span></span>

1. <span data-ttu-id="a8e56-129">Деректерді өңдеу кезінде **Түрлендіру**, одан кейін **Бірінші жолды тақырып ретінде пайдалану** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="a8e56-129">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="a8e56-130">Төменде берілген бағандар үшін деректер түрін жаңартыңыз:</span><span class="sxs-lookup"><span data-stu-id="a8e56-130">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="a8e56-131">**Сатып алынған күні**: күн/уақыт</span><span class="sxs-lookup"><span data-stu-id="a8e56-131">**PurchasedOn**: Date/Time</span></span>
   - <span data-ttu-id="a8e56-132">**Жалпы бағасы**: валюта</span><span class="sxs-lookup"><span data-stu-id="a8e56-132">**TotalPrice**: Currency</span></span>

1. <span data-ttu-id="a8e56-133">Бүйірлік тақтадағы **Атауы** өрісінде деректер көзі атауын **Сұрау** атауынан **eCommerce сатып алулары** атауына өзгертіңіз.</span><span class="sxs-lookup"><span data-stu-id="a8e56-133">In the **Name** field on the side pane, rename your data source from **Query** to **eCommercePurchases**.</span></span>

1. <span data-ttu-id="a8e56-134">Деректер көзін сақтаңыз.</span><span class="sxs-lookup"><span data-stu-id="a8e56-134">Save the data source.</span></span>


### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="a8e56-135">Тұтынушы деректерін адалдық схемасынан қабылдау</span><span class="sxs-lookup"><span data-stu-id="a8e56-135">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="a8e56-136">**Адалдық схемасы** атты деректер көзін жасаңыз, импорттау опциясын таңдаңыз және **Мәтін/CSV** қосқышын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="a8e56-136">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="a8e56-137">eCommerce контактілері үшін URL мекенжайын енгізіңіз https://aka.ms/ciadclasscustomerloyalty.</span><span class="sxs-lookup"><span data-stu-id="a8e56-137">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="a8e56-138">Деректерді өңдеу кезінде **Түрлендіру**, одан кейін **Бірінші жолды тақырып ретінде пайдалану** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="a8e56-138">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="a8e56-139">Төменде берілген бағандар үшін деректер түрін жаңартыңыз:</span><span class="sxs-lookup"><span data-stu-id="a8e56-139">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="a8e56-140">**Туған күні**: күні</span><span class="sxs-lookup"><span data-stu-id="a8e56-140">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="a8e56-141">**Марапаттар ұпайлары**: бүтін сан</span><span class="sxs-lookup"><span data-stu-id="a8e56-141">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="a8e56-142">**Жасалған уақыты**: күн/уақыт</span><span class="sxs-lookup"><span data-stu-id="a8e56-142">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="a8e56-143">Оң жақ тақтадағы **Атауы** өрісінде деректер көзі атауын **Сұрау** атауынан **адалдық тұтынушылары** атауына өзгертіңіз.</span><span class="sxs-lookup"><span data-stu-id="a8e56-143">In the **Name** field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="a8e56-144">Деректер көзін сақтаңыз.</span><span class="sxs-lookup"><span data-stu-id="a8e56-144">Save the data source.</span></span>

## <a name="task-2---data-unification"></a><span data-ttu-id="a8e56-145">2-тапсырма – деректерді біріктіру</span><span class="sxs-lookup"><span data-stu-id="a8e56-145">Task 2 - Data unification</span></span>

<span data-ttu-id="a8e56-146">Деректерді қабылдағаннан кейін біз енді тұтынушының бірыңғай профилін жасау үшін **Салыстыру, сәйкестендіру, біріктіру** процесін бастаймыз.</span><span class="sxs-lookup"><span data-stu-id="a8e56-146">After ingesting the data we now begin the **Map, Match, Merge** process to create a unified customer profile.</span></span> <span data-ttu-id="a8e56-147">Қосымша ақпарат алу үшін [Деректерді біріктіру](data-unification.md) бөлімін қараңыз.</span><span class="sxs-lookup"><span data-stu-id="a8e56-147">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="a8e56-148">Картаға түсіру</span><span class="sxs-lookup"><span data-stu-id="a8e56-148">Map</span></span>

1. <span data-ttu-id="a8e56-149">Деректерді қабылдағаннан кейін, eCommerce және адалдық деректеріндегі контактілерді жалпы деректер түрлерімен салыстырыңыз.</span><span class="sxs-lookup"><span data-stu-id="a8e56-149">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="a8e56-150">**Деректер** > **Біріктіру** > **Салыстыру** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="a8e56-150">Go to **Data** > **Unify** > **Map**.</span></span>

2. <span data-ttu-id="a8e56-151">Тұтынушы профилін ұсынатын нысандарды таңдаңыз – **eCommerce контактілері** және **адалдық тұтынушылары**.</span><span class="sxs-lookup"><span data-stu-id="a8e56-151">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span>

   ![ecommerce және адалдық деректер көздерін біріктіру.](media/unify-ecommerce-loyalty.png)

3. <span data-ttu-id="a8e56-153">**eCommerce контактілері** үшін негізгі кілт ретінде **Контакт идентификаторы** кілтін, ал **адалдық тұтынушылары** үшін негізгі кілт ретінде **Адалдық идентификаторы** кілтін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="a8e56-153">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   ![Адалдық идентификаторын негізгі кілт ретінде біріктіру.](media/unify-loyaltyid.png)

### <a name="match"></a><span data-ttu-id="a8e56-155">Сәйкестендіру</span><span class="sxs-lookup"><span data-stu-id="a8e56-155">Match</span></span>

1. <span data-ttu-id="a8e56-156">**Сәйкестендіру** қойыншасына өтіп **Орнату реті** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="a8e56-156">Go to the **Match** tab and select **Set Order**.</span></span>

2. <span data-ttu-id="a8e56-157">**Негізгі** ашылмалы тізімінде негізгі көз ретінде **eCommerce контактілері: eCommerce** опциясын таңдап, барлық жазбаларды қосыңыз.</span><span class="sxs-lookup"><span data-stu-id="a8e56-157">In the **Primary** drop-down list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

3. <span data-ttu-id="a8e56-158">**Нысан 2** ашылмалы тізімінде **адалдық тұтынушылары: адалдық схемасы** опциясын таңдап, барлық жазбаларды қосыңыз.</span><span class="sxs-lookup"><span data-stu-id="a8e56-158">In the **Entity 2** drop-down list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   ![Сәйкес eCommerce және адалдықты біріктіру.](media/unify-match-order.png)

4. <span data-ttu-id="a8e56-160">**Жаңа ереже жасау** опциясын таңдаңыз</span><span class="sxs-lookup"><span data-stu-id="a8e56-160">Select **Create a new rule**</span></span>

5. <span data-ttu-id="a8e56-161">Аты-жөні опциясы көмегімен алғашқы шартты қосыңыз.</span><span class="sxs-lookup"><span data-stu-id="a8e56-161">Add your first condition using FullName.</span></span>

   - <span data-ttu-id="a8e56-162">eCommerce контактілері үшін ашылмалы мәзірде **Аты-жөні** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="a8e56-162">For eCommerceContacts select **FullName** in the drop-down.</span></span>
   - <span data-ttu-id="a8e56-163">Адалдық тұтынушылары үшін ашылмалы мәзірде **Аты-жөні** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="a8e56-163">For loyCustomers select **FullName** in the drop-down.</span></span>
   - <span data-ttu-id="a8e56-164">**Нормалдау** ашылмалы мәзірін таңдаңыз да, **Теру (телефон, аты, мекен-жайы, ...)** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="a8e56-164">Select the **Normalize** drop down and choose **Type (Phone, Name, Address, ...)**.</span></span>
   - <span data-ttu-id="a8e56-165">**Дәлдік деңгейі** мәнін орнатыңыз: **Негізгі** және **Мән** : **Жоғары**.</span><span class="sxs-lookup"><span data-stu-id="a8e56-165">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

6. <span data-ttu-id="a8e56-166">Жаңа ереже үшін **Аты-жөні, электрондық пошта** атауын енгіңіз.</span><span class="sxs-lookup"><span data-stu-id="a8e56-166">Enter the name **FullName, Email** for the new rule.</span></span>

   - <span data-ttu-id="a8e56-167">**Шарт қосу** опциясын таңдау арқылы электрондық пошта мекенжайына екінші шарт қосу</span><span class="sxs-lookup"><span data-stu-id="a8e56-167">Add a second condition for email address by selecting **Add Condition**</span></span>
   - <span data-ttu-id="a8e56-168">eCommerce контактілерінің нысаны үшін ашылмалы мәзірден **Электрондық пошта** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="a8e56-168">For entity eCommerceContacts, choose **EMail** in drop-down.</span></span>
   - <span data-ttu-id="a8e56-169">Адалдық тұтынушыларының нысаны үшін ашылмалы мәзірден **Электрондық пошта** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="a8e56-169">For entity loyCustomers, choose **EMail** in the drop-down.</span></span>
   - <span data-ttu-id="a8e56-170">Нормалдау өрісін бос қалдырыңыз.</span><span class="sxs-lookup"><span data-stu-id="a8e56-170">Leave Normalize blank.</span></span>
   - <span data-ttu-id="a8e56-171">**Дәлдік деңгейі** мәнін орнатыңыз: **Негізгі** және **Мән** : **Жоғары**.</span><span class="sxs-lookup"><span data-stu-id="a8e56-171">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   ![Атауы мен электрондық поштасы үшін сәйкестік ережесін біріктіру.](media/unify-match-rule.png)

7. <span data-ttu-id="a8e56-173">**Сақтау** және **Іске қосу** опцияларын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="a8e56-173">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="a8e56-174">Біріктіру</span><span class="sxs-lookup"><span data-stu-id="a8e56-174">Merge</span></span>

1. <span data-ttu-id="a8e56-175">**Біріктіру** қойыншасына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="a8e56-175">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="a8e56-176">**Адалдық тұтынушылары** нысанына арналған **Контакт идентификаторы** нысанында көрсетілетін атауды басқа идентификаторлардан ажырату үшін **Контакт идентификаторы АДАЛДЫҚ** атауына өзгертіңіз.</span><span class="sxs-lookup"><span data-stu-id="a8e56-176">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   ![контакт идентификаторы атауынан адалдық идентификаторы атауына өзгерту.](media/unify-merge-contactid.png)

1. <span data-ttu-id="a8e56-178">Біріктіру процесін бастау үшін **Сақтау** және **Іске қосу** опцияларын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="a8e56-178">Select **Save** and **Run** to start the Merge Process.</span></span>

## <a name="task-3---configure-product-recommendation-prediction"></a><span data-ttu-id="a8e56-179">3-тапсырма - Өнім ұсынысының болжамын конфигурациялау</span><span class="sxs-lookup"><span data-stu-id="a8e56-179">Task 3 - Configure product recommendation prediction</span></span>

<span data-ttu-id="a8e56-180">Бірыңғай тұтынушы профильдерімен біз енді жазылымдардың кетуін болжай аламыз.</span><span class="sxs-lookup"><span data-stu-id="a8e56-180">With the unified customer profiles in place, we can now run the subscription churn prediction.</span></span>

1. <span data-ttu-id="a8e56-181">**Сараптау** > **Болжам** тармағына өтіп, **Өнім ұсынысы** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="a8e56-181">Go to **Intelligence** > **Prediction** choose **Product recommendation**.</span></span>

1. <span data-ttu-id="a8e56-182">**Жұмысты бастау** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="a8e56-182">Select **Get started**.</span></span>

1. <span data-ttu-id="a8e56-183">**OOB өнім ұсынысы үлгісінің болжамы** үлгісінің және **OOBProductRecommendationModelPrediction** нысанының атауын енгізіңіз.</span><span class="sxs-lookup"><span data-stu-id="a8e56-183">Name the model **OOB Product Recommendation Model Prediction** and the output entity **OOBProductRecommendationModelPrediction**.</span></span>

1. <span data-ttu-id="a8e56-184">Үлгінің үш шартын анықтаңыз:</span><span class="sxs-lookup"><span data-stu-id="a8e56-184">Define three conditions for the model:</span></span>

   - <span data-ttu-id="a8e56-185">**Өнімдер саны**: бұл мәнді **5** мәніне орнатыңыз.</span><span class="sxs-lookup"><span data-stu-id="a8e56-185">**Number of products**: Set this value to **5**.</span></span> <span data-ttu-id="a8e56-186">Бұл параметр сіздің тұтынушыларыңызға қанша өнім ұсынғыңыз келетінін анықтайды.</span><span class="sxs-lookup"><span data-stu-id="a8e56-186">This setting defines how many products you want to recommend to your customers.</span></span>

   - <span data-ttu-id="a8e56-187">**Клиенттердің жақында сатып алған өнімдерін ұсыну қажет пе?**: тұтынушыларыңыз бұрын сатып алған өнімдерді ұсынысқа қосқыңыз келетінін көрсету үшін **Иә** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="a8e56-187">**Suggest products customers have recently purchased?**: Select **Yes** to indicate that you want to include products in the recommendation that your customers have purchased before.</span></span>

   - <span data-ttu-id="a8e56-188">**Ретроспективті шолу терезесі**: кем дегенде **365 күн** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="a8e56-188">**Look back window:** Select at least **365 days**.</span></span> <span data-ttu-id="a8e56-189">Бұл параметр ұсыныстарға кіріс ретінде пайдалану үшін үлгінің тұтынушы әрекетіне қаншалықты терең ретроспективті шолу жасайтынын анықтайды.</span><span class="sxs-lookup"><span data-stu-id="a8e56-189">This setting defines how far the model will look back at the customer's activity to use it as input to their recommendations.</span></span>
   
   :::image type="content" source="media/product-recommendation-model-preferences.png" alt-text="Өнімнің ұсыныс үлгісіне арналған үлгі параметрлері.":::

1. <span data-ttu-id="a8e56-191">**Қажетті деректер** опциясын таңдап, сатып алу тарихы үшін **Деректер қосу** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="a8e56-191">Select **Required data** and select **Add data** for purchase history.</span></span>

1. <span data-ttu-id="a8e56-192">**eCommerce сатып алулары: eCommerce** нысанын қосыңыз және eCommerce өрістерін үлгі талап ететін тиісті өрістермен салыстырыңыз.</span><span class="sxs-lookup"><span data-stu-id="a8e56-192">Add the **eCommercePurchases : eCommerce** entity and map the fields from eCommerce to the corresponding fields required by the model.</span></span>

1. <span data-ttu-id="a8e56-193">**eCommerce сатып алулары: eCommerce** нысанына **eCommerce конатктілері: eCommerce** нысанымен қосылыңыз.</span><span class="sxs-lookup"><span data-stu-id="a8e56-193">Join the **eCommercePurchases : eCommerce** entity with **eCommerceContacts : eCommerce**.</span></span>

   ![eCommerce нысандарына қосылу.](media/model-purchase-join.png)

1. <span data-ttu-id="a8e56-195">Үлгі кестесін орнату үшін **Келесі** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="a8e56-195">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="a8e56-196">Үлгіге жаңа деректер түскен кезде жаңа мысалдарды білу үшін үнемі жаттығу керек.</span><span class="sxs-lookup"><span data-stu-id="a8e56-196">The model needs to train regularly to learn new patterns when there is new data ingested.</span></span> <span data-ttu-id="a8e56-197">Осы мысал үшін **Ай сайын** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="a8e56-197">For this example, select **Monthly**.</span></span>

1. <span data-ttu-id="a8e56-198">Барлық мәліметтерді қарап шыққаннан кейін **Сақтау және іске қосу** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="a8e56-198">After reviewing all the details, select **Save and Run**.</span></span>


## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="a8e56-199">4-тапсырма – үлгі нәтижелері мен түсіндірмелерін қарап шығу</span><span class="sxs-lookup"><span data-stu-id="a8e56-199">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="a8e56-200">Үлгі жаттығуды аяқтап, деректерді бағалауды жүргізсін.</span><span class="sxs-lookup"><span data-stu-id="a8e56-200">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="a8e56-201">Енді өнім ұсынысы үлгісінің түсіндірмелерін қарап шығуға болады.</span><span class="sxs-lookup"><span data-stu-id="a8e56-201">You can now review the product recommendation model explanations.</span></span> <span data-ttu-id="a8e56-202">Қосымша ақпарат алу үшін [Болжам күйі мен нәтижелерін қарап шығу](predict-subscription-churn.md#review-a-prediction-status-and-results) бөлімін қараңыз.</span><span class="sxs-lookup"><span data-stu-id="a8e56-202">For more information, see [Review a prediction status and results](predict-subscription-churn.md#review-a-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-purchased-products"></a><span data-ttu-id="a8e56-203">5-тапсырма - Жоғары сатып алынған өнімдердің сегментін жасау</span><span class="sxs-lookup"><span data-stu-id="a8e56-203">Task 5 - Create a segment of high purchased products</span></span>

<span data-ttu-id="a8e56-204">Өндіріс үлгісін іске қосу **Деректер** > **Нысандар** тармағында көре алатын жаңа нысанды жасайды.</span><span class="sxs-lookup"><span data-stu-id="a8e56-204">Running the production model creates a new entity that you can see in **Data** > **Entities**.</span></span>

<span data-ttu-id="a8e56-205">Үлгі жасаған нысан негізінде жаңа сегмент жасауға болады.</span><span class="sxs-lookup"><span data-stu-id="a8e56-205">You can create a new segment based on the entity created by the model.</span></span>

1. <span data-ttu-id="a8e56-206">**Сегменттер** бетіне өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="a8e56-206">Go to **Segments**.</span></span> <span data-ttu-id="a8e56-207">**Жаңа** опциясын таңдаңыз да, **Келесіден жасау** > **Интеллект** тармағын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="a8e56-207">Select **New** and choose **Create from** > **Intelligence**.</span></span>

   ![Үлгі шығысымен сегмент жасау.](media/segment-intelligence.png)

1. <span data-ttu-id="a8e56-209">**OOBProductRecommendationModelPrediction** соңғы нүктесін таңдап, сегментті анықтаңыз:</span><span class="sxs-lookup"><span data-stu-id="a8e56-209">Select the **OOBProductRecommendationModelPrediction** endpoint and define the segment:</span></span>

   - <span data-ttu-id="a8e56-210">Өріс: өнім идентификаторы</span><span class="sxs-lookup"><span data-stu-id="a8e56-210">Field: ProductID</span></span>
   - <span data-ttu-id="a8e56-211">Оператор: мәні</span><span class="sxs-lookup"><span data-stu-id="a8e56-211">Operator: Value</span></span>
   - <span data-ttu-id="a8e56-212">Мән: өнімнің ең маңызды үш идентификаторын таңдаңыз</span><span class="sxs-lookup"><span data-stu-id="a8e56-212">Value: Select the top three product IDs</span></span>

   :::image type="content" source="media/product-recommendation-quick-segment.png" alt-text="Үлгі нәтижелерінен сегмент жасаңыз.":::

<span data-ttu-id="a8e56-214">Енді сізде ең көп ұсынылған үш өнімді сатып алуға дайын тұтынушыларды анықтайтын динамикалық жаңартылған сегмент бар</span><span class="sxs-lookup"><span data-stu-id="a8e56-214">You now have a segment that is dynamically updated which identifies the customers who are more willing to purchase the three most recommended products</span></span> 

<span data-ttu-id="a8e56-215">Қосымша ақпаратты [Сегменттерді жасау және басқару](segments.md) бөлімінен қараңыз.</span><span class="sxs-lookup"><span data-stu-id="a8e56-215">For more information, see [Create and manage segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]