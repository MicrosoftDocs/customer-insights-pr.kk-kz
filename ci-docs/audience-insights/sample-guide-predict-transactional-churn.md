---
title: Транзакциялық кету болжамының үлгі нұсқаулығы
description: Кірістірілген транзакциялық кету болжамының үлгісін байқап көру үшін осы үлгі нұсқаулығын пайдаланыңыз.
ms.date: 11/19/2020
ms.reviewer: digranad
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 055708ed3f9f468cad83ecf976a460814bf05199
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643600"
---
# <a name="transactional-churn-prediction-preview-sample-guide"></a><span data-ttu-id="eae92-103">Транзакциялық кету болжамының (алдын ала қарау) үлгі нұсқаулығы</span><span class="sxs-lookup"><span data-stu-id="eae92-103">Transactional churn prediction (preview) sample guide</span></span>

<span data-ttu-id="eae92-104">Бұл нұсқаулық сізге төменде берілген деректерді пайдаланып, Customer Insights бағдарламасындағы транзакциялық кету болжамының мысалын басынан аяғына дейін түсіндіреді.</span><span class="sxs-lookup"><span data-stu-id="eae92-104">This guide will walk you through an end to end example of Transactional Churn prediction in Customer Insights using the data provided below.</span></span> <span data-ttu-id="eae92-105">Осы нұсқаулықта пайдаланылатын барлық деректер тұтынушының нақты деректері емес және Customer Insights жазылымының *Демо* ортасында табылған Contoso деректер жиынтығының бөлігі болып табылады.</span><span class="sxs-lookup"><span data-stu-id="eae92-105">All data used in this guide is not real customer data and is part of the Contoso dataset found in the *Demo* environment within your Customer Insights Subscription.</span></span>

## <a name="scenario"></a><span data-ttu-id="eae92-106">Сценарий</span><span class="sxs-lookup"><span data-stu-id="eae92-106">Scenario</span></span>

<span data-ttu-id="eae92-107">Contoso — бұл жоғары сапалы кофе және кофеқайнатқыштарын шығаратын, оларды Contoso Coffee веб-сайты арқылы сататын компания.</span><span class="sxs-lookup"><span data-stu-id="eae92-107">Contoso is a company that produces high-quality coffee and coffee machines, which they sell through their Contoso Coffee website.</span></span> <span data-ttu-id="eae92-108">Олардың мақсаты — жүйелі түрде олардың өнімдерін әдеттегідей сатып алатын тұтынушылардың қайсысы келесі 60 күн ішінде белсенді тұтынушы болуды тоқтататындығын білу.</span><span class="sxs-lookup"><span data-stu-id="eae92-108">Their goal is to know which customers who typically purchase their products on a regular basis, will stop being active customers in the next 60 days.</span></span> <span data-ttu-id="eae92-109">**Кетуі ықтимал** тұтынушыларды білу оларды қалдыруға назар аудара отырып, маркетингтік жұмыстарды үнемдеуге көмектеседі.</span><span class="sxs-lookup"><span data-stu-id="eae92-109">Knowing which of their customers is **likely to churn**, can help them save marketing efforts by focusing on keeping them.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="eae92-110">Алғышарттар</span><span class="sxs-lookup"><span data-stu-id="eae92-110">Prerequisites</span></span>

- <span data-ttu-id="eae92-111">Customer Insights бағдарламасында кемінде [Салымшы рұқсаттары](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="eae92-111">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>
- <span data-ttu-id="eae92-112">[Жаңа ортадағы](manage-environments.md) келесі қадамдарды орындауға кеңес береміз.</span><span class="sxs-lookup"><span data-stu-id="eae92-112">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="eae92-113">1-тапсырма – деректерді қабылдау</span><span class="sxs-lookup"><span data-stu-id="eae92-113">Task 1 - Ingest data</span></span>

<span data-ttu-id="eae92-114">[Деректерді қабылдау](data-sources.md) және [Power Query қосқыштарының көмегімен деректер көздерін импорттау туралы](connect-power-query.md) арнайы мақалаларды қарап шығыңыз.</span><span class="sxs-lookup"><span data-stu-id="eae92-114">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md) specifically.</span></span> <span data-ttu-id="eae92-115">Төмендегі ақпарат қабылданатын деректермен жалпылама танысқаныңызды болжайды.</span><span class="sxs-lookup"><span data-stu-id="eae92-115">The following information assumes you familiarized with ingesting data in general.</span></span> 

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="eae92-116">eCommerce платформасынан тұтынушы деректерін қабылдау</span><span class="sxs-lookup"><span data-stu-id="eae92-116">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="eae92-117">**eCommerce** атты деректер көзін жасаңыз, импорттау опциясын таңдаңыз және **Мәтін/CSV** қосқышын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="eae92-117">Create a data source named **eCommerce**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="eae92-118">eCommerce контактілері үшін URL мекенжайын енгізіңіз https://aka.ms/ciadclasscontacts.</span><span class="sxs-lookup"><span data-stu-id="eae92-118">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscontacts.</span></span>

1. <span data-ttu-id="eae92-119">Деректерді өңдеу кезінде **Түрлендіру**, одан кейін **Бірінші жолды тақырып ретінде пайдалану** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="eae92-119">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="eae92-120">Төменде берілген бағандар үшін деректер түрін жаңартыңыз:</span><span class="sxs-lookup"><span data-stu-id="eae92-120">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="eae92-121">**Туған күні**: күні</span><span class="sxs-lookup"><span data-stu-id="eae92-121">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="eae92-122">**Жасалған уақыты**: күн/уақыт/белдеу</span><span class="sxs-lookup"><span data-stu-id="eae92-122">**CreatedOn**: Date/Time/Zone</span></span>

   [!div class="mx-imgBorder"]
   <span data-ttu-id="eae92-123">![Туған күнін күнге түрлендіру](media/ecommerce-dob-date.PNG "туған күнін күнге түрлендіру")</span><span class="sxs-lookup"><span data-stu-id="eae92-123">![Transform DoB to Date](media/ecommerce-dob-date.PNG "transform date of birth to date")</span></span>

1. <span data-ttu-id="eae92-124">Оң жақ тақтадағы 'Атау' өрісінде деректер көзі атауын **Сұрау** атауынан **eCommerce контактілері** атауына өзгертіңіз</span><span class="sxs-lookup"><span data-stu-id="eae92-124">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

1. <span data-ttu-id="eae92-125">Деректер көзін сақтаңыз.</span><span class="sxs-lookup"><span data-stu-id="eae92-125">Save the data source.</span></span>

### <a name="ingest-online-purchase-data"></a><span data-ttu-id="eae92-126">Онлайн сатып алу деректерін қабылдау</span><span class="sxs-lookup"><span data-stu-id="eae92-126">Ingest online purchase data</span></span>

1. <span data-ttu-id="eae92-127">Бір **eCommerce** деректер көзіне басқа деректер жиынтығын қосыңыз.</span><span class="sxs-lookup"><span data-stu-id="eae92-127">Add another data set to the same **eCommerce** data source.</span></span> <span data-ttu-id="eae92-128">**Мәтін/CSV** қосқышын қайтадан таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="eae92-128">Choose the **Text/CSV** connector again.</span></span>

1. <span data-ttu-id="eae92-129">**Онлайн сатып алулар** деректері үшін URL мекенжайын енгізіңіз https://aka.ms/ciadclassonline.</span><span class="sxs-lookup"><span data-stu-id="eae92-129">Enter the URL for **Online Purchases** data https://aka.ms/ciadclassonline.</span></span>

1. <span data-ttu-id="eae92-130">Деректерді өңдеу кезінде **Түрлендіру**, одан кейін **Бірінші жолды тақырып ретінде пайдалану** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="eae92-130">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="eae92-131">Төменде берілген бағандар үшін деректер түрін жаңартыңыз:</span><span class="sxs-lookup"><span data-stu-id="eae92-131">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="eae92-132">**Сатып алынған күні**: күн/уақыт</span><span class="sxs-lookup"><span data-stu-id="eae92-132">**PurchasedOn**: Date/Time</span></span>
   - <span data-ttu-id="eae92-133">**Жалпы бағасы**: валюта</span><span class="sxs-lookup"><span data-stu-id="eae92-133">**TotalPrice**: Currency</span></span>
   
1. <span data-ttu-id="eae92-134">Оң жақ тақтадағы 'Атау' өрісінде деректер көзі атауын **Сұрау** атауынан **eCommerce сатып алулары** атауына өзгертіңіз.</span><span class="sxs-lookup"><span data-stu-id="eae92-134">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **eCommercePurchases**.</span></span>

1. <span data-ttu-id="eae92-135">Деректер көзін сақтаңыз.</span><span class="sxs-lookup"><span data-stu-id="eae92-135">Save the data source.</span></span>

### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="eae92-136">Тұтынушы деректерін адалдық схемасынан қабылдау</span><span class="sxs-lookup"><span data-stu-id="eae92-136">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="eae92-137">**Адалдық схемасы** атты деректер көзін жасаңыз, импорттау опциясын таңдаңыз және **Мәтін/CSV** қосқышын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="eae92-137">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="eae92-138">eCommerce контактілері үшін URL мекенжайын енгізіңіз https://aka.ms/ciadclasscustomerloyalty.</span><span class="sxs-lookup"><span data-stu-id="eae92-138">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="eae92-139">Деректерді өңдеу кезінде **Түрлендіру**, одан кейін **Бірінші жолды тақырып ретінде пайдалану** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="eae92-139">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="eae92-140">Төменде берілген бағандар үшін деректер түрін жаңартыңыз:</span><span class="sxs-lookup"><span data-stu-id="eae92-140">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="eae92-141">**Туған күні**: күні</span><span class="sxs-lookup"><span data-stu-id="eae92-141">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="eae92-142">**Марапаттар ұпайлары**: бүтін сан</span><span class="sxs-lookup"><span data-stu-id="eae92-142">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="eae92-143">**Жасалған уақыты**: күн/уақыт</span><span class="sxs-lookup"><span data-stu-id="eae92-143">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="eae92-144">Оң жақ тақтадағы 'Атау' өрісінде деректер көзі атауын **Сұрау** атауынан **адалдық тұтынушылары** атауына өзгертіңіз.</span><span class="sxs-lookup"><span data-stu-id="eae92-144">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="eae92-145">Деректер көзін сақтаңыз.</span><span class="sxs-lookup"><span data-stu-id="eae92-145">Save the data source.</span></span>


## <a name="task-2---data-unification"></a><span data-ttu-id="eae92-146">2-тапсырма – деректерді біріктіру</span><span class="sxs-lookup"><span data-stu-id="eae92-146">Task 2 - Data unification</span></span>

<span data-ttu-id="eae92-147">Деректерді қабылдағаннан кейін біз енді тұтынушының бірыңғай профилін жасау үшін **Салыстыру, сәйкестендіру, біріктіру** процесін бастаймыз.</span><span class="sxs-lookup"><span data-stu-id="eae92-147">After ingesting the data we now begin the **Map, Match, Merge** process to create a unified customer profile.</span></span> <span data-ttu-id="eae92-148">Қосымша ақпарат алу үшін [Деректерді біріктіру](data-unification.md) бөлімін қараңыз.</span><span class="sxs-lookup"><span data-stu-id="eae92-148">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="eae92-149">Картаға түсіру</span><span class="sxs-lookup"><span data-stu-id="eae92-149">Map</span></span>

1. <span data-ttu-id="eae92-150">Деректерді қабылдағаннан кейін, eCommerce және адалдық деректеріндегі контактілерді жалпы деректер түрлерімен салыстырыңыз.</span><span class="sxs-lookup"><span data-stu-id="eae92-150">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="eae92-151">**Деректер** > **Біріктіру** > **Салыстыру** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="eae92-151">Go to **Data** > **Unify** > **Map**.</span></span>

1. <span data-ttu-id="eae92-152">Тұтынушы профилін ұсынатын нысандарды таңдаңыз – **eCommerce контактілері** және **адалдық тұтынушылары**.</span><span class="sxs-lookup"><span data-stu-id="eae92-152">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span> 

   :::image type="content" source="media/unify-ecommerce-loyalty.PNG" alt-text="ecommerce және адалдық деректер көздерін біріктіру.":::

1. <span data-ttu-id="eae92-154">**eCommerce контактілері** үшін негізгі кілт ретінде **Контакт идентификаторы** кілтін, ал **адалдық тұтынушылары** үшін негізгі кілт ретінде **Адалдық идентификаторы** кілтін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="eae92-154">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   :::image type="content" source="media/unify-loyaltyid.PNG" alt-text="Адалдық идентификаторын негізгі кілт ретінде біріктіру.":::

### <a name="match"></a><span data-ttu-id="eae92-156">Сәйкестендіру</span><span class="sxs-lookup"><span data-stu-id="eae92-156">Match</span></span>

1. <span data-ttu-id="eae92-157">**Сәйкестендіру** қойыншасына өтіп **Орнату реті** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="eae92-157">Go to the **Match** tab and select **Set Order**.</span></span>

1. <span data-ttu-id="eae92-158">**Негізгі** ашылмалы тізімінде негізгі көз ретінде **eCommerce контактілері: eCommerce** опциясын таңдап, барлық жазбаларды қосыңыз.</span><span class="sxs-lookup"><span data-stu-id="eae92-158">In the **Primary** drop-down list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

1. <span data-ttu-id="eae92-159">**Нысан 2** ашылмалы тізімінде **адалдық тұтынушылары: адалдық схемасы** опциясын таңдап, барлық жазбаларды қосыңыз.</span><span class="sxs-lookup"><span data-stu-id="eae92-159">In the **Entity 2** drop-down list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   :::image type="content" source="media/unify-match-order.PNG" alt-text="Сәйкес eCommerce және адалдықты біріктіру.":::

1. <span data-ttu-id="eae92-161">**Жаңа ереже жасау** опциясын таңдаңыз</span><span class="sxs-lookup"><span data-stu-id="eae92-161">Select **Create a new rule**</span></span>

1. <span data-ttu-id="eae92-162">Аты-жөні опциясы көмегімен алғашқы шартты қосыңыз.</span><span class="sxs-lookup"><span data-stu-id="eae92-162">Add your first condition using FullName.</span></span>

   * <span data-ttu-id="eae92-163">eCommerce контактілері үшін ашылмалы мәзірде **Аты-жөні** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="eae92-163">For eCommerceContacts select **FullName** in the drop-down.</span></span>
   * <span data-ttu-id="eae92-164">Адалдық тұтынушылары үшін ашылмалы мәзірде **Аты-жөні** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="eae92-164">For loyCustomers select **FullName** in the drop-down.</span></span>
   * <span data-ttu-id="eae92-165">**Нормалдау** ашылмалы мәзірін таңдаңыз да, **Теру (телефон, аты, мекен-жайы, ...)** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="eae92-165">Select the **Normalize** drop down and choose **Type (Phone, Name, Address, ...)**.</span></span>
   * <span data-ttu-id="eae92-166">**Дәлдік деңгейі** мәнін орнатыңыз: **Негізгі** және **Мән** : **Жоғары**.</span><span class="sxs-lookup"><span data-stu-id="eae92-166">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

1. <span data-ttu-id="eae92-167">Жаңа ереже үшін **Аты-жөні, электрондық пошта** атауын енгіңіз.</span><span class="sxs-lookup"><span data-stu-id="eae92-167">Enter the name **FullName, Email** for the new rule.</span></span>

   * <span data-ttu-id="eae92-168">**Шарт қосу** опциясын таңдау арқылы электрондық пошта мекенжайына екінші шарт қосу</span><span class="sxs-lookup"><span data-stu-id="eae92-168">Add a second condition for email address by selecting **Add Condition**</span></span>
   * <span data-ttu-id="eae92-169">eCommerce контактілерінің нысаны үшін ашылмалы мәзірден **Электрондық пошта** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="eae92-169">For entity eCommerceContacts, choose **EMail** in drop-down.</span></span>
   * <span data-ttu-id="eae92-170">Адалдық тұтынушыларының нысаны үшін ашылмалы мәзірден **Электрондық пошта** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="eae92-170">For entity loyCustomers, choose **EMail** in the drop-down.</span></span> 
   * <span data-ttu-id="eae92-171">Нормалдау өрісін бос қалдырыңыз.</span><span class="sxs-lookup"><span data-stu-id="eae92-171">Leave Normalize blank.</span></span> 
   * <span data-ttu-id="eae92-172">**Дәлдік деңгейі** мәнін орнатыңыз: **Негізгі** және **Мән** : **Жоғары**.</span><span class="sxs-lookup"><span data-stu-id="eae92-172">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   :::image type="content" source="media/unify-match-rule.PNG" alt-text="Атауы мен электрондық поштасы үшін сәйкестік ережесін біріктіру.":::

7. <span data-ttu-id="eae92-174">**Сақтау** және **Іске қосу** опцияларын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="eae92-174">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="eae92-175">Біріктіру</span><span class="sxs-lookup"><span data-stu-id="eae92-175">Merge</span></span>

1. <span data-ttu-id="eae92-176">**Біріктіру** қойыншасына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="eae92-176">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="eae92-177">**Адалдық тұтынушылары** нысанына арналған **Контакт идентификаторы** нысанында көрсетілетін атауды басқа идентификаторлардан ажырату үшін **Контакт идентификаторы АДАЛДЫҚ** атауына өзгертіңіз.</span><span class="sxs-lookup"><span data-stu-id="eae92-177">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   :::image type="content" source="media/unify-merge-contactid.PNG" alt-text="контакт идентификаторы атауынан адалдық идентификаторы атауына өзгерту.":::

1. <span data-ttu-id="eae92-179">Біріктіру процесін бастау үшін **Сақтау** және **Іске қосу** опцияларын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="eae92-179">Select **Save** and **Run** to start the Merge Process.</span></span>



## <a name="task-3---configure-transaction-churn-prediction"></a><span data-ttu-id="eae92-180">3-тапсырма – транзакциялық кетудің болжамын конфигурациялау</span><span class="sxs-lookup"><span data-stu-id="eae92-180">Task 3 - Configure transaction churn prediction</span></span>

<span data-ttu-id="eae92-181">Бірыңғай тұтынушы профильдерімен біз енді жазылымдардың кетуін болжай аламыз.</span><span class="sxs-lookup"><span data-stu-id="eae92-181">With the unified customer profiles in place, we can now run the subscription churn prediction.</span></span> <span data-ttu-id="eae92-182">Толық қадамдарды [Жазылым бойынша тұтынушылардың кету болжамы (алдын ала қарау)](predict-subscription-churn.md) мақаласынан қараңыз.</span><span class="sxs-lookup"><span data-stu-id="eae92-182">For detailed steps, see the [Subscription churn prediction (preview)](predict-subscription-churn.md) article.</span></span> 

1. <span data-ttu-id="eae92-183">**Интеллект** > **Табу** тармағына өтіп, пайдалану үшін **Тұтынушылардың кету үлгісі** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="eae92-183">Go to **Intelligence** > **Discover** and select to use the **Customer churn model**.</span></span>

1. <span data-ttu-id="eae92-184">**Транзакциялық** опциясын таңдаңыз, содан кейін **Жұмысты бастау** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="eae92-184">Select the **Transactional** option and select **Get started**.</span></span>

1. <span data-ttu-id="eae92-185">**OOB eCommerce транзакциялық кетудің болжам** үлгісін және **OOBeCommerceChurnPrediction** шығыс нысанын атаңыз.</span><span class="sxs-lookup"><span data-stu-id="eae92-185">Name the model **OOB eCommerce Transaction Churn Prediction** and the output entity **OOBeCommerceChurnPrediction**.</span></span>

1. <span data-ttu-id="eae92-186">Кету үлгісі үшін екі шартты анықтаңыз:</span><span class="sxs-lookup"><span data-stu-id="eae92-186">Define two conditions for the churn model:</span></span>

   * <span data-ttu-id="eae92-187">**Болжам терезесі**: **кем дегенде 60** күн.</span><span class="sxs-lookup"><span data-stu-id="eae92-187">**Prediction window**: **at least 60** days.</span></span> <span data-ttu-id="eae92-188">Бұл параметр болашақта клиенттердің кетуін болжау қаншалықты қажет екенін анықтайды.</span><span class="sxs-lookup"><span data-stu-id="eae92-188">This setting defines how far into the future do we want to predict customer churn.</span></span>

   * <span data-ttu-id="eae92-189">**Кету анықтамасы**: **кем дегенде 60** күн.</span><span class="sxs-lookup"><span data-stu-id="eae92-189">**Churn definition**: **at least 60** days.</span></span> <span data-ttu-id="eae92-190">Кейін тұтынушы кетіп қалған деп саналатын сатып алусыз ұзақтық.</span><span class="sxs-lookup"><span data-stu-id="eae92-190">The duration without purchase after which a customer is considered churned.</span></span>

     :::image type="content" source="media/model-levers.PNG" alt-text="Болжам терезесі мен Кету анықтамасы үлгі түймешіктерін таңдау.":::

1. <span data-ttu-id="eae92-192">**Сатып алу тарихы (қажетті)** опциясын таңдап, жазылым тарихы үшін **Деректер қосу** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="eae92-192">Select **Purchase History (required)** and select **Add data** for subscription history.</span></span>

1. <span data-ttu-id="eae92-193">**eCommerce сатып алулары: eCommerce** нысанын қосыңыз және eCommerce өрістерін үлгі талап ететін тиісті өрістермен салыстырыңыз.</span><span class="sxs-lookup"><span data-stu-id="eae92-193">Add the **eCommercePurchases : eCommerce** entity and map the fields from eCommerce to the corresponding fields required by the model.</span></span>

1. <span data-ttu-id="eae92-194">**eCommerce сатып алулары: eCommerce** нысанына **eCommerce конатктілері: eCommerce** нысанымен қосылыңыз.</span><span class="sxs-lookup"><span data-stu-id="eae92-194">Join the **eCommercePurchases : eCommerce** entity with **eCommerceContacts : eCommerce**.</span></span>

   :::image type="content" source="media/model-purchase-join.PNG" alt-text="eCommerce нысандарына қосылу.":::

1. <span data-ttu-id="eae92-196">Үлгі кестесін орнату үшін **Келесі** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="eae92-196">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="eae92-197">Үлгіге жаңа деректер түскен кезде жаңа мысалдарды білу үшін үнемі жаттығу керек.</span><span class="sxs-lookup"><span data-stu-id="eae92-197">The model needs to train regularly to learn new patterns when there is new data ingested.</span></span> <span data-ttu-id="eae92-198">Осы мысал үшін **Ай сайын** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="eae92-198">For this example, select **Monthly**.</span></span>

1. <span data-ttu-id="eae92-199">Барлық мәліметтерді қарап шыққаннан кейін **Сақтау және іске қосу** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="eae92-199">After reviewing all the details, select **Save and Run**.</span></span>

## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="eae92-200">4-тапсырма – үлгі нәтижелері мен түсіндірмелерін қарап шығу</span><span class="sxs-lookup"><span data-stu-id="eae92-200">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="eae92-201">Үлгі жаттығуды аяқтап, деректерді бағалауды жүргізсін.</span><span class="sxs-lookup"><span data-stu-id="eae92-201">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="eae92-202">Енді жазылым бойынша тұтынушылардың кетуі үлгісінің түсіндірмелерін қарап шығуға болады.</span><span class="sxs-lookup"><span data-stu-id="eae92-202">You can now review the subscription churn model explanations.</span></span> <span data-ttu-id="eae92-203">Қосымша ақпарат алу үшін [Болжам күйі мен нәтижелерін қарап шығу](predict-subscription-churn.md#review-a-prediction-status-and-results) бөлімін қараңыз.</span><span class="sxs-lookup"><span data-stu-id="eae92-203">For more information, see [Review a prediction status and results](predict-subscription-churn.md#review-a-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-churn-risk-customers"></a><span data-ttu-id="eae92-204">5-тапсырма – кету қаупі жоғары тұтынушылардың сегментін жасау</span><span class="sxs-lookup"><span data-stu-id="eae92-204">Task 5 - Create a segment of high churn-risk customers</span></span>

<span data-ttu-id="eae92-205">Өндіріс үлгісін іске қосу **Деректер** > **Нысандар** тармағында көре алатын жаңа нысанды жасайды.</span><span class="sxs-lookup"><span data-stu-id="eae92-205">Running the production model creates a new entity that you can see in **Data** > **Entities**.</span></span>   

<span data-ttu-id="eae92-206">Үлгі жасаған нысан негізінде жаңа сегмент жасауға болады.</span><span class="sxs-lookup"><span data-stu-id="eae92-206">You can create a new segment based on the entity created by the model.</span></span>

1.  <span data-ttu-id="eae92-207">**Сегменттер** бетіне өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="eae92-207">Go to **Segments**.</span></span> <span data-ttu-id="eae92-208">**Жаңа** опциясын таңдаңыз да, **Келесіден жасау** > **Интеллект** тармағын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="eae92-208">Select **New** and choose **Create from** > **Intelligence**.</span></span> 

   :::image type="content" source="media/segment-intelligence.PNG" alt-text="Үлгі шығысымен сегмент жасау.":::

1. <span data-ttu-id="eae92-210">**OOBSubscriptionChurnPrediction** соңғы нүктесін таңдап, сегментті анықтаңыз:</span><span class="sxs-lookup"><span data-stu-id="eae92-210">Select the **OOBSubscriptionChurnPrediction** endpoint and define the segment:</span></span> 
   - <span data-ttu-id="eae92-211">Өріс: кету ұпайы</span><span class="sxs-lookup"><span data-stu-id="eae92-211">Field: ChurnScore</span></span>
   - <span data-ttu-id="eae92-212">Амалдағыш: келесіден артық</span><span class="sxs-lookup"><span data-stu-id="eae92-212">Operator: greater than</span></span>
   - <span data-ttu-id="eae92-213">Мән: 0,6</span><span class="sxs-lookup"><span data-stu-id="eae92-213">Value: 0.6</span></span>
   
   :::image type="content" source="media/segment-setup-subs.PNG" alt-text="Жазылым бойынша тұтынушылардың кетуі сегментін орнату.":::

<span data-ttu-id="eae92-215">Енді сізде бұл жазылым бизнесі үшін кету қаупі жоғары тұтынушыларды анықтайтын динамикалық түрде жаңартылатын сегмент бар.</span><span class="sxs-lookup"><span data-stu-id="eae92-215">You now have a segment that is dynamically updated which identifies high churn-risk customers for this subscription business.</span></span>

<span data-ttu-id="eae92-216">Қосымша ақпаратты [Сегменттерді жасау және басқару](segments.md) бөлімінен қараңыз.</span><span class="sxs-lookup"><span data-stu-id="eae92-216">For more information, see [Create and manage segments](segments.md).</span></span>
