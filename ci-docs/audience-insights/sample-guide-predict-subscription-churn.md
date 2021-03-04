---
title: Жазылым бойынша тұтынушылардың кетуі болжамының үлгі нұсқаулығы
description: Кірістірілген жазылым бойынша тұтынушылардың кетуі болжамының үлгісін байқап көру үшін осы үлгі нұсқаулығын пайдаланыңыз.
ms.date: 11/19/2020
ms.reviewer: digranad
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 3f1019ace424f89320c5a0d5058e928f4cbc7e62
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269843"
---
# <a name="subscription-churn-prediction-preview-sample-guide"></a><span data-ttu-id="ccdcb-103">Жазылым бойынша тұтынушылардың кетуі болжамының (алдын ала қарау) үлгі нұсқаулығы</span><span class="sxs-lookup"><span data-stu-id="ccdcb-103">Subscription churn prediction (preview) sample guide</span></span>

<span data-ttu-id="ccdcb-104">Біз сізге төменде берілген үлгі деректерін пайдаланып, жазылым бойынша тұтынушылардың кетуі болжамының мысалын басынан аяғына дейін түсіндіреміз.</span><span class="sxs-lookup"><span data-stu-id="ccdcb-104">We'll walk you through an end to end example of subscription churn prediction using the sample data provided below.</span></span> 

## <a name="scenario"></a><span data-ttu-id="ccdcb-105">Сценарий</span><span class="sxs-lookup"><span data-stu-id="ccdcb-105">Scenario</span></span>

<span data-ttu-id="ccdcb-106">Contoso — бұл жоғары сапалы кофе және кофеқайнатқыштарын шығаратын, оларды Contoso Coffee веб-сайты арқылы сататын компания.</span><span class="sxs-lookup"><span data-stu-id="ccdcb-106">Contoso is a company that produces high-quality coffee and coffee machines, which they sell through their Contoso Coffee website.</span></span> <span data-ttu-id="ccdcb-107">Олар жақында өз тұтынушылары үшін жүйелі түрде кофе алу мақсатында жазылым бизнесін бастады.</span><span class="sxs-lookup"><span data-stu-id="ccdcb-107">They recently started a subscription business for their customers to get coffee on a regular basis.</span></span> <span data-ttu-id="ccdcb-108">Олардың мақсаты — келесі бірнеше айда жазылушылардың қайсысы жазылудан бас тартуы мүмкін екенін түсіну.</span><span class="sxs-lookup"><span data-stu-id="ccdcb-108">Their goal is to understand, which subscribed customers might cancel their subscription in the next few months.</span></span> <span data-ttu-id="ccdcb-109">**Кетуі ықтимал** тұтынушыларды білу оларды қалдыруға назар аудара отырып, маркетингтік жұмыстарды үнемдеуге көмектеседі.</span><span class="sxs-lookup"><span data-stu-id="ccdcb-109">Knowing which of their customers is **likely to churn**, can help them save marketing efforts by focusing on keeping them.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="ccdcb-110">Алғышарттар</span><span class="sxs-lookup"><span data-stu-id="ccdcb-110">Prerequisites</span></span>

- <span data-ttu-id="ccdcb-111">Customer Insights бағдарламасында кемінде [Салымшы рұқсаттары](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="ccdcb-111">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>
- <span data-ttu-id="ccdcb-112">[Жаңа ортадағы](manage-environments.md) келесі қадамдарды орындауға кеңес береміз.</span><span class="sxs-lookup"><span data-stu-id="ccdcb-112">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="ccdcb-113">1-тапсырма – деректерді қабылдау</span><span class="sxs-lookup"><span data-stu-id="ccdcb-113">Task 1 - Ingest data</span></span>

<span data-ttu-id="ccdcb-114">[Деректерді қабылдау](data-sources.md) және [Power Query қосқыштарының көмегімен деректер көздерін импорттау туралы](connect-power-query.md) арнайы мақалаларды қарап шығыңыз.</span><span class="sxs-lookup"><span data-stu-id="ccdcb-114">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md) specifically.</span></span> <span data-ttu-id="ccdcb-115">Төмендегі ақпарат қабылданатын деректермен жалпылама танысқаныңызды болжайды.</span><span class="sxs-lookup"><span data-stu-id="ccdcb-115">The following information assumes you familiarized with ingesting data in general.</span></span> 

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="ccdcb-116">eCommerce платформасынан тұтынушы деректерін қабылдау</span><span class="sxs-lookup"><span data-stu-id="ccdcb-116">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="ccdcb-117">**eCommerce** атты деректер көзін жасаңыз, импорттау опциясын таңдаңыз және **Мәтін/CSV** қосқышын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="ccdcb-117">Create a data source named **eCommerce**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="ccdcb-118">eCommerce контактілері үшін URL мекенжайын енгізіңіз https://aka.ms/ciadclasscontacts.</span><span class="sxs-lookup"><span data-stu-id="ccdcb-118">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscontacts.</span></span>

1. <span data-ttu-id="ccdcb-119">Деректерді өңдеу кезінде **Түрлендіру**, одан кейін **Бірінші жолды тақырып ретінде пайдалану** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="ccdcb-119">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="ccdcb-120">Төменде берілген бағандар үшін деректер түрін жаңартыңыз:</span><span class="sxs-lookup"><span data-stu-id="ccdcb-120">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="ccdcb-121">**Туған күні**: күні</span><span class="sxs-lookup"><span data-stu-id="ccdcb-121">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="ccdcb-122">**Жасалған уақыты**: күн/уақыт/белдеу</span><span class="sxs-lookup"><span data-stu-id="ccdcb-122">**CreatedOn**: Date/Time/Zone</span></span>

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Туған күнін күнге түрлендіру.":::

1. <span data-ttu-id="ccdcb-124">Оң жақ тақтадағы **Атауы** өрісінде деректер көзі атауын **Сұрау** атауынан **eCommerce контактілері** атауына өзгертіңіз</span><span class="sxs-lookup"><span data-stu-id="ccdcb-124">In the **Name** field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

1. <span data-ttu-id="ccdcb-125">Деректер көзін сақтаңыз.</span><span class="sxs-lookup"><span data-stu-id="ccdcb-125">Save the data source.</span></span>

### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="ccdcb-126">Тұтынушы деректерін адалдық схемасынан қабылдау</span><span class="sxs-lookup"><span data-stu-id="ccdcb-126">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="ccdcb-127">**Адалдық схемасы** атты деректер көзін жасаңыз, импорттау опциясын таңдаңыз және **Мәтін/CSV** қосқышын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="ccdcb-127">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="ccdcb-128">eCommerce контактілері үшін URL мекенжайын енгізіңіз https://aka.ms/ciadclasscustomerloyalty.</span><span class="sxs-lookup"><span data-stu-id="ccdcb-128">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="ccdcb-129">Деректерді өңдеу кезінде **Түрлендіру**, одан кейін **Бірінші жолды тақырып ретінде пайдалану** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="ccdcb-129">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="ccdcb-130">Төменде берілген бағандар үшін деректер түрін жаңартыңыз:</span><span class="sxs-lookup"><span data-stu-id="ccdcb-130">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="ccdcb-131">**Туған күні**: күні</span><span class="sxs-lookup"><span data-stu-id="ccdcb-131">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="ccdcb-132">**Марапаттар ұпайлары**: бүтін сан</span><span class="sxs-lookup"><span data-stu-id="ccdcb-132">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="ccdcb-133">**Жасалған уақыты**: күн/уақыт</span><span class="sxs-lookup"><span data-stu-id="ccdcb-133">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="ccdcb-134">Оң жақ тақтадағы **Атауы** өрісінде деректер көзі атауын **Сұрау** атауынан **адалдық тұтынушылары** атауына өзгертіңіз.</span><span class="sxs-lookup"><span data-stu-id="ccdcb-134">In the **Name** field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="ccdcb-135">Деректер көзін сақтаңыз.</span><span class="sxs-lookup"><span data-stu-id="ccdcb-135">Save the data source.</span></span>

### <a name="ingest-subscription-information"></a><span data-ttu-id="ccdcb-136">Жазылым туралы ақпаратты қабылдау</span><span class="sxs-lookup"><span data-stu-id="ccdcb-136">Ingest subscription information</span></span>

1. <span data-ttu-id="ccdcb-137">**Жазылым тарихы** атты деректер көзін жасаңыз, импорттау опциясын таңдаңыз және **Мәтін/CSV** қосқышын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="ccdcb-137">Create a data source named **SubscriptionHistory**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="ccdcb-138">eCommerce контактілері үшін URL мекенжайын енгізіңіз https://aka.ms/ciadchurnsubscriptionhistory.</span><span class="sxs-lookup"><span data-stu-id="ccdcb-138">Enter the URL for eCommerce contacts https://aka.ms/ciadchurnsubscriptionhistory.</span></span>

1. <span data-ttu-id="ccdcb-139">Деректерді өңдеу кезінде **Түрлендіру**, одан кейін **Бірінші жолды тақырып ретінде пайдалану** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="ccdcb-139">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="ccdcb-140">Төменде берілген бағандар үшін деректер түрін жаңартыңыз:</span><span class="sxs-lookup"><span data-stu-id="ccdcb-140">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="ccdcb-141">**Жазылым идентификаторы**: бүтін сан</span><span class="sxs-lookup"><span data-stu-id="ccdcb-141">**SubscriptioID**: Whole Number</span></span>
   - <span data-ttu-id="ccdcb-142">**Жазылым сомасы**: валюта</span><span class="sxs-lookup"><span data-stu-id="ccdcb-142">**SubscriptionAmount**: Currency</span></span>
   - <span data-ttu-id="ccdcb-143">**Жазылымның аяқталу күні**: күн/уақыт</span><span class="sxs-lookup"><span data-stu-id="ccdcb-143">**SubscriptionEndDate**: Date/Time</span></span>
   - <span data-ttu-id="ccdcb-144">**Жазылымның басталу күні**: күн/уақыт</span><span class="sxs-lookup"><span data-stu-id="ccdcb-144">**SubscriptionStartDate**: Date/Time</span></span>
   - <span data-ttu-id="ccdcb-145">**Транзакция күні**: күн/уақыт</span><span class="sxs-lookup"><span data-stu-id="ccdcb-145">**TransactionDate**: Date/Time</span></span>
   - <span data-ttu-id="ccdcb-146">**Қайталануда**: шын/жалған</span><span class="sxs-lookup"><span data-stu-id="ccdcb-146">**IsRecurring**: True/False</span></span>
   - <span data-ttu-id="ccdcb-147">**Автоматты_түрде_қайта_жаңарту**: шын/жалған</span><span class="sxs-lookup"><span data-stu-id="ccdcb-147">**Is_auto_renew**: True/False</span></span>
   - <span data-ttu-id="ccdcb-148">**Ай ішінде қайталанатын жиілік**: бүтін сан</span><span class="sxs-lookup"><span data-stu-id="ccdcb-148">**RecurringFrequencyInMonths**: Whole Number</span></span>

1. <span data-ttu-id="ccdcb-149">Оң жақ тақтадағы **Атауы** өрісінде деректер көзі атауын **Сұрау** атауынан **Жазылым тарихы** атауына өзгертіңіз.</span><span class="sxs-lookup"><span data-stu-id="ccdcb-149">In the **Name** field on the right-hand pane, rename your data source from **Query** to **SubscriptionHistory**.</span></span>

1. <span data-ttu-id="ccdcb-150">Деректер көзін сақтаңыз.</span><span class="sxs-lookup"><span data-stu-id="ccdcb-150">Save the data source.</span></span>

### <a name="ingest-customer-data-from-website-reviews"></a><span data-ttu-id="ccdcb-151">Тұтынушы деректерін веб-сайт сараптауларынан қабылдау</span><span class="sxs-lookup"><span data-stu-id="ccdcb-151">Ingest customer data from website reviews</span></span>

1. <span data-ttu-id="ccdcb-152">**Веб-сайт** атты деректер көзін жасаңыз, импорттау опциясын таңдаңыз және **Мәтін/CSV** қосқышын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="ccdcb-152">Create a data source named **Website**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="ccdcb-153">eCommerce контактілері үшін URL мекенжайын енгізіңіз https://aka.ms/ciadclasswebsite.</span><span class="sxs-lookup"><span data-stu-id="ccdcb-153">Enter the URL for eCommerce contacts https://aka.ms/ciadclasswebsite.</span></span>

1. <span data-ttu-id="ccdcb-154">Деректерді өңдеу кезінде **Түрлендіру**, одан кейін **Бірінші жолды тақырып ретінде пайдалану** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="ccdcb-154">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="ccdcb-155">Төменде берілген бағандар үшін деректер түрін жаңартыңыз:</span><span class="sxs-lookup"><span data-stu-id="ccdcb-155">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="ccdcb-156">**Сараптау бағасы**: бүтін сан</span><span class="sxs-lookup"><span data-stu-id="ccdcb-156">**ReviewRating**: Whole Number</span></span>
   - <span data-ttu-id="ccdcb-157">**Сараптау күні**: күні</span><span class="sxs-lookup"><span data-stu-id="ccdcb-157">**ReviewDate**: Date</span></span>

1. <span data-ttu-id="ccdcb-158">Оң жақ тақтадағы 'Атау' өрісінде деректер көзі атауын **Сұрау** атауынан **веб сараптаулар** атауына өзгертіңіз.</span><span class="sxs-lookup"><span data-stu-id="ccdcb-158">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **webReviews**.</span></span>

## <a name="task-2---data-unification"></a><span data-ttu-id="ccdcb-159">2-тапсырма – деректерді біріктіру</span><span class="sxs-lookup"><span data-stu-id="ccdcb-159">Task 2 - Data unification</span></span>

<span data-ttu-id="ccdcb-160">Деректерді қабылдағаннан кейін біз енді тұтынушының бірыңғай профилін жасау үшін **Салыстыру, сәйкестендіру, біріктіру** процесін бастаймыз.</span><span class="sxs-lookup"><span data-stu-id="ccdcb-160">After ingesting the data we now begin the **Map, Match, Merge** process to create a unified customer profile.</span></span> <span data-ttu-id="ccdcb-161">Қосымша ақпарат алу үшін [Деректерді біріктіру](data-unification.md) бөлімін қараңыз.</span><span class="sxs-lookup"><span data-stu-id="ccdcb-161">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="ccdcb-162">Картаға түсіру</span><span class="sxs-lookup"><span data-stu-id="ccdcb-162">Map</span></span>

1. <span data-ttu-id="ccdcb-163">Деректерді қабылдағаннан кейін, eCommerce және адалдық деректеріндегі контактілерді жалпы деректер түрлерімен салыстырыңыз.</span><span class="sxs-lookup"><span data-stu-id="ccdcb-163">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="ccdcb-164">**Деректер** > **Біріктіру** > **Салыстыру** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="ccdcb-164">Go to **Data** > **Unify** > **Map**.</span></span>

1. <span data-ttu-id="ccdcb-165">Тұтынушы профилін ұсынатын нысандарды таңдаңыз – **eCommerce контактілері** және **адалдық тұтынушылары**.</span><span class="sxs-lookup"><span data-stu-id="ccdcb-165">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span> 

   :::image type="content" source="media/unify-ecommerce-loyalty.PNG" alt-text="ecommerce және адалдық деректер көздерін біріктіру.":::

1. <span data-ttu-id="ccdcb-167">**eCommerce контактілері** үшін негізгі кілт ретінде **Контакт идентификаторы** кілтін, ал **адалдық тұтынушылары** үшін негізгі кілт ретінде **Адалдық идентификаторы** кілтін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="ccdcb-167">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   :::image type="content" source="media/unify-loyaltyid.PNG" alt-text="Адалдық идентификаторын негізгі кілт ретінде біріктіру.":::

### <a name="match"></a><span data-ttu-id="ccdcb-169">Сәйкестендіру</span><span class="sxs-lookup"><span data-stu-id="ccdcb-169">Match</span></span>

1. <span data-ttu-id="ccdcb-170">**Сәйкестендіру** қойыншасына өтіп **Орнату реті** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="ccdcb-170">Go to the **Match** tab and select **Set Order**.</span></span>

1. <span data-ttu-id="ccdcb-171">**Негізгі** ашылмалы тізімінде негізгі көз ретінде **eCommerce контактілері: eCommerce** опциясын таңдап, барлық жазбаларды қосыңыз.</span><span class="sxs-lookup"><span data-stu-id="ccdcb-171">In the **Primary** drop-down list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

1. <span data-ttu-id="ccdcb-172">**Нысан 2** ашылмалы тізімінде **адалдық тұтынушылары: адалдық схемасы** опциясын таңдап, барлық жазбаларды қосыңыз.</span><span class="sxs-lookup"><span data-stu-id="ccdcb-172">In the **Entity 2** drop-down list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   :::image type="content" source="media/unify-match-order.PNG" alt-text="Сәйкес eCommerce және адалдықты біріктіру.":::

1. <span data-ttu-id="ccdcb-174">**Жаңа ереже жасау** опциясын таңдаңыз</span><span class="sxs-lookup"><span data-stu-id="ccdcb-174">Select **Create a new rule**</span></span>

1. <span data-ttu-id="ccdcb-175">Аты-жөні опциясы көмегімен алғашқы шартты қосыңыз.</span><span class="sxs-lookup"><span data-stu-id="ccdcb-175">Add your first condition using FullName.</span></span>

   * <span data-ttu-id="ccdcb-176">eCommerce контактілері үшін ашылмалы мәзірде **Аты-жөні** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="ccdcb-176">For eCommerceContacts select **FullName** in the drop-down.</span></span>
   * <span data-ttu-id="ccdcb-177">Адалдық тұтынушылары үшін ашылмалы мәзірде **Аты-жөні** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="ccdcb-177">For loyCustomers select **FullName** in the drop-down.</span></span>
   * <span data-ttu-id="ccdcb-178">**Нормалдау** ашылмалы мәзірін таңдаңыз да, **Теру (телефон, аты, мекен-жайы, ...)** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="ccdcb-178">Select the **Normalize** drop down and choose **Type (Phone, Name, Address, ...)**.</span></span>
   * <span data-ttu-id="ccdcb-179">**Дәлдік деңгейі** мәнін орнатыңыз: **Негізгі** және **Мән** : **Жоғары**.</span><span class="sxs-lookup"><span data-stu-id="ccdcb-179">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

1. <span data-ttu-id="ccdcb-180">Жаңа ереже үшін **Аты-жөні, электрондық пошта** атауын енгіңіз.</span><span class="sxs-lookup"><span data-stu-id="ccdcb-180">Enter the name **FullName, Email** for the new rule.</span></span>

   * <span data-ttu-id="ccdcb-181">**Шарт қосу** опциясын таңдау арқылы электрондық пошта мекенжайына екінші шарт қосу</span><span class="sxs-lookup"><span data-stu-id="ccdcb-181">Add a second condition for email address by selecting **Add Condition**</span></span>
   * <span data-ttu-id="ccdcb-182">eCommerce контактілерінің нысаны үшін ашылмалы мәзірден **Электрондық пошта** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="ccdcb-182">For entity eCommerceContacts, choose **EMail** in drop-down.</span></span>
   * <span data-ttu-id="ccdcb-183">Адалдық тұтынушыларының нысаны үшін ашылмалы мәзірден **Электрондық пошта** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="ccdcb-183">For entity loyCustomers, choose **EMail** in the drop-down.</span></span> 
   * <span data-ttu-id="ccdcb-184">Нормалдау өрісін бос қалдырыңыз.</span><span class="sxs-lookup"><span data-stu-id="ccdcb-184">Leave Normalize blank.</span></span> 
   * <span data-ttu-id="ccdcb-185">**Дәлдік деңгейі** мәнін орнатыңыз: **Негізгі** және **Мән** : **Жоғары**.</span><span class="sxs-lookup"><span data-stu-id="ccdcb-185">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   :::image type="content" source="media/unify-match-rule.PNG" alt-text="Атауы мен электрондық поштасы үшін сәйкестік ережесін біріктіру.":::

7. <span data-ttu-id="ccdcb-187">**Сақтау** және **Іске қосу** опцияларын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="ccdcb-187">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="ccdcb-188">Біріктіру</span><span class="sxs-lookup"><span data-stu-id="ccdcb-188">Merge</span></span>

1. <span data-ttu-id="ccdcb-189">**Біріктіру** қойыншасына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="ccdcb-189">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="ccdcb-190">**Адалдық тұтынушылары** нысанына арналған **Контакт идентификаторы** нысанында көрсетілетін атауды басқа идентификаторлардан ажырату үшін **Контакт идентификаторы АДАЛДЫҚ** атауына өзгертіңіз.</span><span class="sxs-lookup"><span data-stu-id="ccdcb-190">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   :::image type="content" source="media/unify-merge-contactid.PNG" alt-text="контакт идентификаторы атауынан адалдық идентификаторы атауына өзгерту.":::

1. <span data-ttu-id="ccdcb-192">Біріктіру процесін бастау үшін **Сақтау** және **Іске қосу** опцияларын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="ccdcb-192">Select **Save** and **Run** to start the Merge Process.</span></span>


## <a name="task-3---configure-the-subscription-churn-prediction"></a><span data-ttu-id="ccdcb-193">3-тапсырма – жазылым бойынша тұтынушылардың кетуі болжамын конфигурациялау</span><span class="sxs-lookup"><span data-stu-id="ccdcb-193">Task 3 - Configure the subscription churn prediction</span></span>

<span data-ttu-id="ccdcb-194">Бірыңғай тұтынушы профильдерімен біз енді жазылымдардың кетуін болжай аламыз.</span><span class="sxs-lookup"><span data-stu-id="ccdcb-194">With the unified customer profiles in place, we can now run the subscription churn prediction.</span></span> <span data-ttu-id="ccdcb-195">Толық қадамдарды [Жазылым бойынша тұтынушылардың кету болжамы (алдын ала қарау)](predict-subscription-churn.md) мақаласынан қараңыз.</span><span class="sxs-lookup"><span data-stu-id="ccdcb-195">For detailed steps, see the [Subscription churn prediction (preview)](predict-subscription-churn.md) article.</span></span> 

1. <span data-ttu-id="ccdcb-196">**Интеллект** > **Табу** тармағына өтіп, пайдалану үшін **Тұтынушылардың кету үлгісі** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="ccdcb-196">Go to **Intelligence** > **Discover** and select to use the **Customer churn model**.</span></span>

1. <span data-ttu-id="ccdcb-197">**Жазылым** опциясын таңдаңыз, содан кейін **Жұмысты бастау** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="ccdcb-197">Select the **Subscription** option and select **Get started**.</span></span>

1. <span data-ttu-id="ccdcb-198">**OOB жазылым бойынша тұтынушылардың кетуі болжамы** үлгісін және **OOBSubscriptionChurnPrediction** шығыс нысанын атаңыз.</span><span class="sxs-lookup"><span data-stu-id="ccdcb-198">Name the model **OOB Subscription Churn Prediction** and the output entity **OOBSubscriptionChurnPrediction**.</span></span>

1. <span data-ttu-id="ccdcb-199">Кету үлгісі үшін екі шартты анықтаңыз:</span><span class="sxs-lookup"><span data-stu-id="ccdcb-199">Define two conditions for the churn model:</span></span>

   * <span data-ttu-id="ccdcb-200">**Жазылым аяқталғаннан кейінгі күндер**: **кем дегенде 60** күн.</span><span class="sxs-lookup"><span data-stu-id="ccdcb-200">**Days since subscription ended**: **at least 60** days.</span></span> <span data-ttu-id="ccdcb-201">Тұтынушы жазылым аяқталғаннан кейін осы мерзім ішінде жазылымды ұзартпаса, тұтынушы кетіп қалған болып саналады.</span><span class="sxs-lookup"><span data-stu-id="ccdcb-201">If a customer doesn't renew the subscription in this period after their subscription ended, they are considered churned.</span></span> 

   * <span data-ttu-id="ccdcb-202">**Кету анықтамасы**: **кем дегенде 93** күн.</span><span class="sxs-lookup"><span data-stu-id="ccdcb-202">**Churn definition**: **at least 93** days.</span></span> <span data-ttu-id="ccdcb-203">Үлгі ұзақтығы кетуі мүмкін тұтынушыларды болжайды.</span><span class="sxs-lookup"><span data-stu-id="ccdcb-203">The duration the model predict which customers might churn.</span></span> <span data-ttu-id="ccdcb-204">Болашаққа неғұрлым алыс қарайтын болсаңыз, нәтижелер соғұрлым аз болады.</span><span class="sxs-lookup"><span data-stu-id="ccdcb-204">The further in the future you look, the less precise the results.</span></span>

     :::image type="content" source="media/model-subs-levers.PNG" alt-text="Болжам терезесі мен Кету анықтамасы үлгі түймешіктерін таңдау.":::

1. <span data-ttu-id="ccdcb-206">**Қажетті деректерді қосу** опциясын таңдап, жазылым тарихы үшін **Деректер қосу** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="ccdcb-206">Select **Add required data** and select **Add data** for subscription history.</span></span>

1. <span data-ttu-id="ccdcb-207">**Жазылым: жазылым тарихы** нысанын қосыңыз және eCommerce өрістерін үлгі талап ететін тиісті өрістермен салыстырыңыз.</span><span class="sxs-lookup"><span data-stu-id="ccdcb-207">Add the **Subscription : SubscriptionHistory** entity and map the fields from eCommerce to the corresponding fields required by the model.</span></span>

1. <span data-ttu-id="ccdcb-208">**eCommerce контактілері: eCommerce** көмегімен **Жазылым: жазылым тарихы** нысанына қосылыңыз, **eCommerce жазылымы** қарым-қатынасын атаңыз.</span><span class="sxs-lookup"><span data-stu-id="ccdcb-208">Join the **Subscription : SubscriptionHistory** entity with **eCommerceContacts : eCommerce**, name the relationship **eCommerceSubscription**.</span></span>

   :::image type="content" source="media/model-subscription-join.PNG" alt-text="eCommerce нысандарына қосылу.":::

1. <span data-ttu-id="ccdcb-210">Тұтынушы әрекеттерінде **веб сараптаулар: веб-сайт** нысанын қосыңыз және веб сараптаулардағы өрістерді үлгіге сәйкес өрістермен салыстырыңыз.</span><span class="sxs-lookup"><span data-stu-id="ccdcb-210">Under Customer Activities, add the **webReviews : Website** entity and map the fields from webReviews to the corresponding fields required by the model.</span></span> 
   - <span data-ttu-id="ccdcb-211">Бастапқы кілт: сараптау идентификаторы</span><span class="sxs-lookup"><span data-stu-id="ccdcb-211">Primary key: ReviewId</span></span>
   - <span data-ttu-id="ccdcb-212">Уақыт белгісі: сараптау күні</span><span class="sxs-lookup"><span data-stu-id="ccdcb-212">Timestamp: ReviewDate</span></span>
   - <span data-ttu-id="ccdcb-213">Оқиға: сараптау бағасы</span><span class="sxs-lookup"><span data-stu-id="ccdcb-213">Event: ReviewRating</span></span>

1. <span data-ttu-id="ccdcb-214">Веб-сайт сараптауларына арналған әрекетті конфигурациялаңыз.</span><span class="sxs-lookup"><span data-stu-id="ccdcb-214">Configure an activity for website reviews.</span></span> <span data-ttu-id="ccdcb-215">**Сараптау** әрекетін таңдап, **eCommerce контактілері: eCommerce** көмегімен **веб сараптаулар: веб-сайт** нысанына қосылыңыз.</span><span class="sxs-lookup"><span data-stu-id="ccdcb-215">Select the activity **Review** and join the **webReviews : Website** entity with **eCommerceContacts : eCommerce**.</span></span>

1. <span data-ttu-id="ccdcb-216">Үлгі кестесін орнату үшін **Келесі** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="ccdcb-216">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="ccdcb-217">Үлгіге жаңа деректер түскен кезде жаңа мысалдарды білу үшін үнемі жаттығу керек.</span><span class="sxs-lookup"><span data-stu-id="ccdcb-217">The model needs to train regularly to learn new patterns when there is new data ingested.</span></span> <span data-ttu-id="ccdcb-218">Осы мысал үшін **Ай сайын** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="ccdcb-218">For this example, select **Monthly**.</span></span>

1. <span data-ttu-id="ccdcb-219">Барлық мәліметтерді қарап шыққаннан кейін **Сақтау және іске қосу** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="ccdcb-219">After reviewing all the details, select **Save and Run**.</span></span>

## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="ccdcb-220">4-тапсырма – үлгі нәтижелері мен түсіндірмелерін қарап шығу</span><span class="sxs-lookup"><span data-stu-id="ccdcb-220">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="ccdcb-221">Үлгі жаттығуды аяқтап, деректерді бағалауды жүргізсін.</span><span class="sxs-lookup"><span data-stu-id="ccdcb-221">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="ccdcb-222">Енді жазылым бойынша тұтынушылардың кетуі үлгісінің түсіндірмелерін қарап шығуға болады.</span><span class="sxs-lookup"><span data-stu-id="ccdcb-222">You can now review the subscription churn model explanations.</span></span> <span data-ttu-id="ccdcb-223">Қосымша ақпарат алу үшін [Болжам күйі мен нәтижелерін қарап шығу](predict-subscription-churn.md#review-a-prediction-status-and-results) бөлімін қараңыз.</span><span class="sxs-lookup"><span data-stu-id="ccdcb-223">For more information, see [Review a prediction status and results](predict-subscription-churn.md#review-a-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-churn-risk-customers"></a><span data-ttu-id="ccdcb-224">5-тапсырма – кету қаупі жоғары тұтынушылардың сегментін жасау</span><span class="sxs-lookup"><span data-stu-id="ccdcb-224">Task 5 - Create a segment of high churn-risk customers</span></span>

<span data-ttu-id="ccdcb-225">Өндіріс үлгісін іске қосу **Деректер** > **Нысандар** тармағында көре алатын жаңа нысанды жасайды.</span><span class="sxs-lookup"><span data-stu-id="ccdcb-225">Running the production model creates a new entity that you can see in **Data** > **Entities**.</span></span>   

<span data-ttu-id="ccdcb-226">Үлгі жасаған нысан негізінде жаңа сегмент жасауға болады.</span><span class="sxs-lookup"><span data-stu-id="ccdcb-226">You can create a new segment based on the entity created by the model.</span></span>

1.  <span data-ttu-id="ccdcb-227">**Сегменттер** бетіне өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="ccdcb-227">Go to **Segments**.</span></span> <span data-ttu-id="ccdcb-228">**Жаңа** опциясын таңдаңыз да, **Келесіден жасау** > **Интеллект** тармағын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="ccdcb-228">Select **New** and choose **Create from** > **Intelligence**.</span></span> 

   :::image type="content" source="media/segment-intelligence.PNG" alt-text="Үлгі шығысымен сегмент жасау.":::

1. <span data-ttu-id="ccdcb-230">**OOBSubscriptionChurnPrediction** соңғы нүктесін таңдап, сегментті анықтаңыз:</span><span class="sxs-lookup"><span data-stu-id="ccdcb-230">Select the **OOBSubscriptionChurnPrediction** endpoint and define the segment:</span></span> 
   - <span data-ttu-id="ccdcb-231">Өріс: кету ұпайы</span><span class="sxs-lookup"><span data-stu-id="ccdcb-231">Field: ChurnScore</span></span>
   - <span data-ttu-id="ccdcb-232">Амалдағыш: келесіден артық</span><span class="sxs-lookup"><span data-stu-id="ccdcb-232">Operator: greater than</span></span>
   - <span data-ttu-id="ccdcb-233">Мән: 0,6</span><span class="sxs-lookup"><span data-stu-id="ccdcb-233">Value: 0.6</span></span>
   
   :::image type="content" source="media/segment-setup-subs.PNG" alt-text="Жазылым бойынша тұтынушылардың кетуі сегментін орнату.":::

<span data-ttu-id="ccdcb-235">Енді сізде бұл жазылым бизнесі үшін кету қаупі жоғары тұтынушыларды анықтайтын динамикалық түрде жаңартылатын сегмент бар.</span><span class="sxs-lookup"><span data-stu-id="ccdcb-235">You now have a segment that is dynamically updated which identifies high churn-risk customers for this subscription business.</span></span>

<span data-ttu-id="ccdcb-236">Қосымша ақпаратты [Сегменттерді жасау және басқару](segments.md) бөлімінен қараңыз.</span><span class="sxs-lookup"><span data-stu-id="ccdcb-236">For more information, see [Create and manage segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]