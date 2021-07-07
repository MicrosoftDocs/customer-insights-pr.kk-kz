---
title: Тұтынушының өмір бойғы құндылығын болжау үлгі нұсқаулығы
description: Тұтынушының өмір бойғы құндылығын болжау моделін пайдаланып көру үшін осы нұсқаулықты пайдаланыңыз.
ms.date: 05/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: yashlundia
ms.author: yalundia
manager: shellyha
ms.openlocfilehash: 19c1fbadb79ba22c0dc11aa7c3b5b2415add70a7
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 06/24/2021
ms.locfileid: "6306356"
---
# <a name="customer-lifetime-value-clv-prediction-sample-guide"></a><span data-ttu-id="f682f-103">Тұтынушының өмір бойғы құндылығы (CLV) болжамының үлгі нұсқаулығы</span><span class="sxs-lookup"><span data-stu-id="f682f-103">Customer lifetime value (CLV) prediction sample guide</span></span>

<span data-ttu-id="f682f-104">Бұл нұсқаулық үлгі деректерін пайдалану арқылы Customer Insights бағдарламасында тұтынушының өмір бойғы құндылығы (CLV) болжамының мысалына шолу жасайды.</span><span class="sxs-lookup"><span data-stu-id="f682f-104">This guide will walk you through an end to end example of Customer lifetime value (CLV) prediction in Customer Insights using sample data.</span></span>

## <a name="scenario"></a><span data-ttu-id="f682f-105">Сценарий</span><span class="sxs-lookup"><span data-stu-id="f682f-105">Scenario</span></span>

<span data-ttu-id="f682f-106">Contoso — бұл сапалы кофе және кофе машиналарын шығаратын компания.</span><span class="sxs-lookup"><span data-stu-id="f682f-106">Contoso is a company that produces high-quality coffee and coffee machines.</span></span> <span data-ttu-id="f682f-107">Олар өнімдерді өздерінің Contoso Coffee веб-сайты арқылы сатады.</span><span class="sxs-lookup"><span data-stu-id="f682f-107">They sell the products through their Contoso Coffee website.</span></span> <span data-ttu-id="f682f-108">Компания өз тұтынушыларының алдағы 12 айда жасай алатын құнын (кірісін) түсінгісі келеді.</span><span class="sxs-lookup"><span data-stu-id="f682f-108">The company wants to understand the value (revenue) that their customers can generate in the next 12 months.</span></span> <span data-ttu-id="f682f-109">Алдағы 12 айдағы тұтынушыларының күтілетін кірісін білу маркетингтік әрекеттерін құндылығы жоғары тұтынушыларға бағыттауға көмектеседі.</span><span class="sxs-lookup"><span data-stu-id="f682f-109">Knowing the expected value of their customers in the next 12 months will help them steer their marketing efforts on high value customers.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f682f-110">Алғышарттар</span><span class="sxs-lookup"><span data-stu-id="f682f-110">Prerequisites</span></span>

- <span data-ttu-id="f682f-111">Кемінде аудитория туралы пайдалы мәліметтердегі [салымшы рұқсаттары](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="f682f-111">At least [Contributor permissions](permissions.md) in audience insights.</span></span>
- <span data-ttu-id="f682f-112">[Жаңа ортадағы](manage-environments.md) келесі қадамдарды орындауға кеңес береміз.</span><span class="sxs-lookup"><span data-stu-id="f682f-112">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="f682f-113">1-тапсырма – деректерді қабылдау</span><span class="sxs-lookup"><span data-stu-id="f682f-113">Task 1 - Ingest data</span></span>

<span data-ttu-id="f682f-114">[Деректерді қабылдау туралы ақпарат](data-sources.md) және [Деректер көзін Power Query қосқыштарының көмегімен импорттау](connect-power-query.md) бойынша мақалаларды қарап шығыңыз.</span><span class="sxs-lookup"><span data-stu-id="f682f-114">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md).</span></span> <span data-ttu-id="f682f-115">Төмендегі ақпарат қабылданатын деректермен жалпылама танысқаныңызды болжайды.</span><span class="sxs-lookup"><span data-stu-id="f682f-115">The following information assumes you familiarized with ingesting data in general.</span></span>

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="f682f-116">eCommerce платформасынан тұтынушы деректерін қабылдау</span><span class="sxs-lookup"><span data-stu-id="f682f-116">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="f682f-117">**eCommerce** атты деректер көзін жасаңыз, импорттау опциясын таңдаңыз және **Мәтін/CSV** қосқышын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="f682f-117">Create a data source named  **eCommerce** , choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="f682f-118">eCommerce контактілері үшін URL мекенжайын [https://aka.ms/ciadclasscontacts](https://aka.ms/ciadclasscontacts) енгізіңіз.</span><span class="sxs-lookup"><span data-stu-id="f682f-118">Enter the URL for eCommerce contacts [https://aka.ms/ciadclasscontacts](https://aka.ms/ciadclasscontacts).</span></span>

1. <span data-ttu-id="f682f-119">Деректерді өңдеу кезінде  **Түрлендіру** , одан кейін  **Бірінші жолды тақырып ретінде пайдалану** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="f682f-119">While editing the data, select  **Transform**  and then  **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="f682f-120">Төменде берілген бағандар үшін деректер түрін жаңартыңыз:</span><span class="sxs-lookup"><span data-stu-id="f682f-120">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="f682f-121">**Туған күні**: күні</span><span class="sxs-lookup"><span data-stu-id="f682f-121">**DateOfBirth** : Date</span></span>
   - <span data-ttu-id="f682f-122">**Жасалған уақыты**: күн/уақыт/белдеу</span><span class="sxs-lookup"><span data-stu-id="f682f-122">**CreatedOn** : Date/Time/Zone</span></span>

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Туған күнін күнге түрлендіру.":::

1. <span data-ttu-id="f682f-124">Оң жақ тақтадағы 'Атау' өрісінде деректер көзі атауын **Сұрау** атауынан **eCommerce контактілері** атауына өзгертіңіз</span><span class="sxs-lookup"><span data-stu-id="f682f-124">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

1. <span data-ttu-id="f682f-125">Деректерін көзін **Сақтау** опциясы арқылы сақтаңыз.</span><span class="sxs-lookup"><span data-stu-id="f682f-125">**Save** the data source.</span></span>

### <a name="ingest-online-purchase-data"></a><span data-ttu-id="f682f-126">Онлайн сатып алу деректерін қабылдау</span><span class="sxs-lookup"><span data-stu-id="f682f-126">Ingest online purchase data</span></span>

1. <span data-ttu-id="f682f-127">Бір **eCommerce** деректер көзіне басқа деректер жиынтығын қосыңыз.</span><span class="sxs-lookup"><span data-stu-id="f682f-127">Add another data set to the same **eCommerce** data source.</span></span> <span data-ttu-id="f682f-128">**Мәтін/CSV** қосқышын қайтадан таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="f682f-128">Choose the **Text/CSV** connector again.</span></span>

1. <span data-ttu-id="f682f-129">**Онлайн сатып алулар** деректері үшін URL мекенжайын енгізіңіз https://aka.ms/ciadclassonline.</span><span class="sxs-lookup"><span data-stu-id="f682f-129">Enter the URL for **Online Purchases** data https://aka.ms/ciadclassonline.</span></span>

1. <span data-ttu-id="f682f-130">Деректерді өңдеу кезінде **Түрлендіру**, одан кейін **Бірінші жолды тақырып ретінде пайдалану** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="f682f-130">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="f682f-131">Төменде берілген бағандар үшін деректер түрін жаңартыңыз:</span><span class="sxs-lookup"><span data-stu-id="f682f-131">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="f682f-132">**Сатып алынған күні**: күн/уақыт</span><span class="sxs-lookup"><span data-stu-id="f682f-132">**PurchasedOn**: Date/Time</span></span>
   - <span data-ttu-id="f682f-133">**Жалпы бағасы**: валюта</span><span class="sxs-lookup"><span data-stu-id="f682f-133">**TotalPrice**: Currency</span></span>

1. <span data-ttu-id="f682f-134">Бүйірлік тақтадағы **Атауы** өрісінде деректер көзі атауын **Сұрау** атауынан **eCommerce сатып алулары** атауына өзгертіңіз.</span><span class="sxs-lookup"><span data-stu-id="f682f-134">In the **Name** field on the side pane, rename your data source from **Query** to **eCommercePurchases**.</span></span>

1. <span data-ttu-id="f682f-135">Деректерін көзін **Сақтау** опциясы арқылы сақтаңыз.</span><span class="sxs-lookup"><span data-stu-id="f682f-135">**Save** the data source.</span></span>

### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="f682f-136">Тұтынушы деректерін адалдық схемасынан қабылдау</span><span class="sxs-lookup"><span data-stu-id="f682f-136">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="f682f-137">**Адалдық схемасы** атты деректер көзін жасаңыз, импорттау опциясын таңдаңыз және **Мәтін/CSV** қосқышын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="f682f-137">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="f682f-138">eCommerce контактілері үшін URL мекенжайын енгізіңіз https://aka.ms/ciadclasscustomerloyalty.</span><span class="sxs-lookup"><span data-stu-id="f682f-138">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="f682f-139">Деректерді өңдеу кезінде **Түрлендіру**, одан кейін **Бірінші жолды тақырып ретінде пайдалану** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="f682f-139">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="f682f-140">Төменде берілген бағандар үшін деректер түрін жаңартыңыз:</span><span class="sxs-lookup"><span data-stu-id="f682f-140">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="f682f-141">**Туған күні**: күні</span><span class="sxs-lookup"><span data-stu-id="f682f-141">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="f682f-142">**Марапаттар ұпайлары**: бүтін сан</span><span class="sxs-lookup"><span data-stu-id="f682f-142">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="f682f-143">**Жасалған уақыты**: күн/уақыт</span><span class="sxs-lookup"><span data-stu-id="f682f-143">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="f682f-144">Оң жақ тақтадағы **Атауы** өрісінде деректер көзі атауын **Сұрау** атауынан **адалдық тұтынушылары** атауына өзгертіңіз.</span><span class="sxs-lookup"><span data-stu-id="f682f-144">In the **Name** field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="f682f-145">Деректерін көзін **Сақтау** опциясы арқылы сақтаңыз.</span><span class="sxs-lookup"><span data-stu-id="f682f-145">**Save** the data source.</span></span>

### <a name="ingest-customer-data-from-website-reviews"></a><span data-ttu-id="f682f-146">Тұтынушы деректерін веб-сайт сараптауларынан қабылдау</span><span class="sxs-lookup"><span data-stu-id="f682f-146">Ingest customer data from website reviews</span></span>

1. <span data-ttu-id="f682f-147">**Веб-сайт** атты деректер көзін жасаңыз, импорттау опциясын таңдаңыз және **Мәтін/CSV** қосқышын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="f682f-147">Create a data source named **Website**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="f682f-148">eCommerce контактілері үшін URL мекенжайын енгізіңіз https://aka.ms/CI-ILT/WebReviews.</span><span class="sxs-lookup"><span data-stu-id="f682f-148">Enter the URL for eCommerce contacts https://aka.ms/CI-ILT/WebReviews.</span></span>

1. <span data-ttu-id="f682f-149">Деректерді өңдеу кезінде **Түрлендіру**, одан кейін **Бірінші жолды тақырып ретінде пайдалану** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="f682f-149">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="f682f-150">Төменде берілген бағандар үшін деректер түрін жаңартыңыз:</span><span class="sxs-lookup"><span data-stu-id="f682f-150">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="f682f-151">**ReviewRating**: ондық сан</span><span class="sxs-lookup"><span data-stu-id="f682f-151">**ReviewRating**: Decimal number</span></span>
   - <span data-ttu-id="f682f-152">**Сараптау күні**: күні</span><span class="sxs-lookup"><span data-stu-id="f682f-152">**ReviewDate**: Date</span></span>

1. <span data-ttu-id="f682f-153">Оң жақ тақтадағы "Атау" өрісінде деректер көзі атауын **Сұрау** атауынан **Сараптаулар** атауына өзгертіңіз.</span><span class="sxs-lookup"><span data-stu-id="f682f-153">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **Reviews**.</span></span>

1. <span data-ttu-id="f682f-154">Деректерін көзін **Сақтау** опциясы арқылы сақтаңыз.</span><span class="sxs-lookup"><span data-stu-id="f682f-154">**Save** the data source.</span></span>

## <a name="task-2---data-unification"></a><span data-ttu-id="f682f-155">2-тапсырма – деректерді біріктіру</span><span class="sxs-lookup"><span data-stu-id="f682f-155">Task 2 - Data unification</span></span>

<span data-ttu-id="f682f-156">Деректерді қабылдағаннан кейін біз енді тұтынушылардың бірыңғай профилін жасау үшін деректерді біріздендіру процесін бастаймыз.</span><span class="sxs-lookup"><span data-stu-id="f682f-156">After ingesting the data, we now begin the data unification process to create a unified customer profile.</span></span> <span data-ttu-id="f682f-157">Қосымша ақпарат алу үшін [Деректерді біріктіру](data-unification.md) бөлімін қараңыз.</span><span class="sxs-lookup"><span data-stu-id="f682f-157">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="f682f-158">Картаға түсіру</span><span class="sxs-lookup"><span data-stu-id="f682f-158">Map</span></span>

1. <span data-ttu-id="f682f-159">Деректерді қабылдағаннан кейін, eCommerce және адалдық деректеріндегі контактілерді жалпы деректер түрлерімен салыстырыңыз.</span><span class="sxs-lookup"><span data-stu-id="f682f-159">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="f682f-160">**Деректер** > **Біріктіру** > **Салыстыру** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="f682f-160">Go to **Data** > **Unify** > **Map**.</span></span>

1. <span data-ttu-id="f682f-161">Тұтынушы профилін ұсынатын нысандарды таңдаңыз – **eCommerce контактілері** және **адалдық тұтынушылары**.</span><span class="sxs-lookup"><span data-stu-id="f682f-161">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span> <span data-ttu-id="f682f-162">Содан кейін **Қолдану** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="f682f-162">Then, select **Apply**.</span></span>

   ![ecommerce және адалдық деректер көздерін біріктіру.](media/unify-ecommerce-loyalty.png)

1. <span data-ttu-id="f682f-164">**eCommerce контактілері** үшін негізгі кілт ретінде **Контакт идентификаторы** кілтін, ал **адалдық тұтынушылары** үшін негізгі кілт ретінде **Адалдық идентификаторы** кілтін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="f682f-164">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   ![Адалдық идентификаторын негізгі кілт ретінде біріктіру.](media/unify-loyaltyid.png)

1. <span data-ttu-id="f682f-166">**Сақтау** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="f682f-166">Select **Save**.</span></span>

### <a name="match"></a><span data-ttu-id="f682f-167">Сәйкестендіру</span><span class="sxs-lookup"><span data-stu-id="f682f-167">Match</span></span>

1. <span data-ttu-id="f682f-168">**Сәйкестендіру** қойыншасына өтіп **Орнату реті** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="f682f-168">Go to the **Match** tab and select **Set Order**.</span></span>

1. <span data-ttu-id="f682f-169">**Негізгі** ашылмалы тізімінде **eCommerce байланыстары: eCommerce** нысанын негізгі дереккөзі ретінде таңдаңыз және барлық жазбаларды қосыңыз.</span><span class="sxs-lookup"><span data-stu-id="f682f-169">In the **Primary** dropdown list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

1. <span data-ttu-id="f682f-170">**2 нысан** ашылмалы тізімінде **loyCustomers: LoyaltyScheme** нысанын таңдаңыз және барлық жазбаларды қосыңыз.</span><span class="sxs-lookup"><span data-stu-id="f682f-170">In the **Entity 2** dropdown list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   ![Сәйкес eCommerce және адалдықты біріктіру.](media/unify-match-order.png)

1. <span data-ttu-id="f682f-172">**Ереже қосу** түймешігін таңдаңыз</span><span class="sxs-lookup"><span data-stu-id="f682f-172">Select **Add rule**</span></span>

1. <span data-ttu-id="f682f-173">Аты-жөні опциясы көмегімен алғашқы шартты қосыңыз.</span><span class="sxs-lookup"><span data-stu-id="f682f-173">Add your first condition using FullName.</span></span>

   - <span data-ttu-id="f682f-174">eCommerceContacts нысаны үшін ашылмалы тізімнен **FullName** өрісін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="f682f-174">For eCommerceContacts select **FullName** in the dropdown.</span></span>
   - <span data-ttu-id="f682f-175">loyCustomers нысаны үшін ашылмалы тізімнен **FullName** өрісін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="f682f-175">For loyCustomers select **FullName** in the dropdown.</span></span>
   - <span data-ttu-id="f682f-176">**Қалыпқа келтіру** ашылмалы тізімін таңдаңыз және **Түрін (телефон, аты, мекенжайы, ...)** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="f682f-176">Select the **Normalize** dropdown and choose **Type (Phone, Name, Address, ...)**.</span></span>
   - <span data-ttu-id="f682f-177">**Дәлдік деңгейі** мәнін орнатыңыз: **Негізгі** және **Мән** : **Жоғары**.</span><span class="sxs-lookup"><span data-stu-id="f682f-177">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

1. <span data-ttu-id="f682f-178">Жаңа ереже үшін **Аты-жөні, электрондық пошта** атауын енгіңіз.</span><span class="sxs-lookup"><span data-stu-id="f682f-178">Enter the name **FullName, Email** for the new rule.</span></span>

   - <span data-ttu-id="f682f-179">**Шарт қосу** опциясын таңдау арқылы электрондық пошта мекенжайына екінші шарт қосу</span><span class="sxs-lookup"><span data-stu-id="f682f-179">Add a second condition for email address by selecting **Add Condition**</span></span>
   - <span data-ttu-id="f682f-180">eCommerceContacts нысаны үшін ашылмалы тізімнен **EMail** өрісін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="f682f-180">For entity eCommerceContacts, choose **EMail** in dropdown.</span></span>
   - <span data-ttu-id="f682f-181">loyCustomers нысаны үшін ашылмалы тізімнен **EMail** өрісін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="f682f-181">For entity loyCustomers, choose **EMail** in the dropdown.</span></span>
   - <span data-ttu-id="f682f-182">Нормалдау өрісін бос қалдырыңыз.</span><span class="sxs-lookup"><span data-stu-id="f682f-182">Leave Normalize blank.</span></span>
   - <span data-ttu-id="f682f-183">**Дәлдік деңгейі** мәнін орнатыңыз: **Негізгі** және **Мән** : **Жоғары**.</span><span class="sxs-lookup"><span data-stu-id="f682f-183">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   ![Атауы мен электрондық поштасы үшін сәйкестік ережесін біріктіру.](media/unify-match-rule.png)

1. <span data-ttu-id="f682f-185">**Дайын** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="f682f-185">Select **Done**.</span></span>

1. <span data-ttu-id="f682f-186">**Сақтау** және **Іске қосу** опцияларын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="f682f-186">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="f682f-187">Біріктіру</span><span class="sxs-lookup"><span data-stu-id="f682f-187">Merge</span></span>

1. <span data-ttu-id="f682f-188">**Біріктіру** қойыншасына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="f682f-188">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="f682f-189">**Адалдық тұтынушылары** нысанына арналған **Контакт идентификаторы** нысанында көрсетілетін атауды басқа идентификаторлардан ажырату үшін **Контакт идентификаторы АДАЛДЫҚ** атауына өзгертіңіз.</span><span class="sxs-lookup"><span data-stu-id="f682f-189">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   ![контакт идентификаторы атауынан адалдық идентификаторы атауына өзгерту.](media/unify-merge-contactid.png)

1. <span data-ttu-id="f682f-191">**Сақтау** түймешігін және **Біріктіруді және кейінгі процестерді іске қосу** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="f682f-191">Select **Save** and **Run merge and downstream processes**.</span></span>

## <a name="task-3---configure-customer-lifetime-value-prediction"></a><span data-ttu-id="f682f-192">3‑тапсырма - тұтынушының өмір бойғы құндылығын болжауды конфигурациялау</span><span class="sxs-lookup"><span data-stu-id="f682f-192">Task 3 - Configure customer lifetime value prediction</span></span>

<span data-ttu-id="f682f-193">Тұтынушылардың бірыңғай профильдері орнатылған кезде, біз тұтынушының өмір бойғы құндылығы болжам іске қоса аламыз.</span><span class="sxs-lookup"><span data-stu-id="f682f-193">With the unified customer profiles in place, we can now run the customer lifetime value prediction.</span></span> <span data-ttu-id="f682f-194">Толық қадамдар үшін [Тұтынушының өмір бойғы құндылығын болжау (алдын ала қарау нұсқасы)](predict-customer-lifetime-value.md) бөлімін қараңыз.</span><span class="sxs-lookup"><span data-stu-id="f682f-194">For detailed steps, see [Customer Lifetime Value prediction (preview)](predict-customer-lifetime-value.md).</span></span>

1. <span data-ttu-id="f682f-195">**Интеллект**  > **Болжамдар**  тармағына өтіңіз және **Тұтынушының өмір бойғы құндылығы үлгісі** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="f682f-195">Go to  **Intelligence**  > **Predictions**  and select the **Customer lifetime value model**.</span></span>

1. <span data-ttu-id="f682f-196">Бүйірлік тақтадағы ақпаратты қарап, **Жұмысты бастау** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="f682f-196">Go through the information in the side pane and select **Get started**.</span></span>

1. <span data-ttu-id="f682f-197">Үлгіні **OOB eCommerce CLV болжамы** деп және шығыс нысанды  **OOBeCommerceCLVPrediction** деп атаңыз.</span><span class="sxs-lookup"><span data-stu-id="f682f-197">Name the model **OOB eCommerce CLV Prediction** and the output entity  **OOBeCommerceCLVPrediction**.</span></span>

1. <span data-ttu-id="f682f-198">CLV моделіне арналған артықшылықтарды анықтаңыз:</span><span class="sxs-lookup"><span data-stu-id="f682f-198">Define model preferences for the CLV model:</span></span>
   - <span data-ttu-id="f682f-199">**Болжау уақыт кезеңі**: **12 ай немесе 1 жыл**.</span><span class="sxs-lookup"><span data-stu-id="f682f-199">**Prediction time period**: **12 months or 1 year**.</span></span> <span data-ttu-id="f682f-200">Бұл параметр тұтынушының өмір бойғы құндылығын қаншалықты болашаққа дейін болжауға болатындығын анықтайды.</span><span class="sxs-lookup"><span data-stu-id="f682f-200">This setting defines how far into the future to predict customer lifetime value.</span></span>
   - <span data-ttu-id="f682f-201">**Белсенді тұтынушылар**: белсенді тұтынушылар сіздің бизнесіңіз үшін нені білдіретінін көрсетіңіз.</span><span class="sxs-lookup"><span data-stu-id="f682f-201">**Active customers**: Specify what active customers mean for your business.</span></span> <span data-ttu-id="f682f-202">Тұтынушының белсенді деп саналатын кем дегенде бір транзакциясы болуы керек болатын тарихи уақыт аралығын орнатыңыз.</span><span class="sxs-lookup"><span data-stu-id="f682f-202">Set the historical time frame in which a customer must have had at least one transaction to be considered active.</span></span> <span data-ttu-id="f682f-203">Модель белсенді тұтынушылар үшін тұтынушының өмір бойғы құндылығын ғана болжайды.</span><span class="sxs-lookup"><span data-stu-id="f682f-203">The model will only predict CLV for active customers.</span></span> <span data-ttu-id="f682f-204">Модельге тарихи транзакция деректері негізінде уақыт кезеңін есептеуге немесе белгілі бір уақыт аралығын ұсынуға мүмкіндік беру арасында таңдау жасаңыз.</span><span class="sxs-lookup"><span data-stu-id="f682f-204">Choose between letting the model calculate the time period based on historical transaction data or provide a specific time frame.</span></span> <span data-ttu-id="f682f-205">Осы үлгі нұсқаулықта біз әдепкі опция болып табылатын **модельге сатып алу аралығын есептеуге мүмкіндік** бердік.</span><span class="sxs-lookup"><span data-stu-id="f682f-205">In this sample guide, we **let the model calculate purchase interval**, which is the default option.</span></span>
   - <span data-ttu-id="f682f-206">**Құндылығы жоғары тұтынушылар**: құндылығы жоғары тұтынушыларды үздік төлейтін тұтынушылардың процентилі ретінде анықтаңыз.</span><span class="sxs-lookup"><span data-stu-id="f682f-206">**High value customers**: Define high value customers as a percentile of top-paying customers.</span></span> <span data-ttu-id="f682f-207">Модель бұл кірісті құндылығы жоғары тұтынушылардың бизнес анықтамасына сәйкес нәтижелер беру үшін пайдаланады.</span><span class="sxs-lookup"><span data-stu-id="f682f-207">The model uses this input to provide results that fit your business definition of high value customers.</span></span> <span data-ttu-id="f682f-208">Модельге құндылығы жоғары тұтынушыларды анықтауға рұқсат беруді таңдауға болады.</span><span class="sxs-lookup"><span data-stu-id="f682f-208">You can choose to let the model define high value customers.</span></span> <span data-ttu-id="f682f-209">Мұнда процентилді шығаратын эвристикалық ереже қолданылады.</span><span class="sxs-lookup"><span data-stu-id="f682f-209">It uses a heuristic rule that derives the percentile.</span></span> <span data-ttu-id="f682f-210">Сондай‑ақ құндылығы жоғары тұтынушыларды үздік төлейтін болашақ тұтынушылардың процентилі ретінде анықтауға болады.</span><span class="sxs-lookup"><span data-stu-id="f682f-210">You can also define high value customers as a percentile of top future paying customers.</span></span> <span data-ttu-id="f682f-211">Осы үлгі нұсқаулықта біз құндылығы жоғары тұтынушыларды **белсенді төлейтін тұтынушылардың үздік 30%** ретінде қолмен анықтаңыз және **Келесі** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="f682f-211">In this sample guide, we manually define high value customers as **top 30% of active paying customers** and select **Next**.</span></span>

    :::image type="content" source="media/clv-model-preferences.png" alt-text="CLV моделіне арналған қадамдық тәжірибедегі параметрлер қадамы.":::

1. <span data-ttu-id="f682f-213">**Қажетті деректер** қадамында транзакция тарихы туралы деректерді беру **Деректер қосу** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="f682f-213">In the **Required Data** step, select **Add data** to provide the transaction history data.</span></span>

1. <span data-ttu-id="f682f-214">**eCommercePurchases : eCommerce** нысанын қосыңыз және үлгіге қажет төлсипаттарды көрсетіңіз:</span><span class="sxs-lookup"><span data-stu-id="f682f-214">Add the **eCommercePurchases : eCommerce** entity and map the attributes that are required by the model:</span></span>
   - <span data-ttu-id="f682f-215">Транзакция идентификаторы: eCommerce.eCommercePurchases.PurchaseId</span><span class="sxs-lookup"><span data-stu-id="f682f-215">Transaction ID: eCommerce.eCommercePurchases.PurchaseId</span></span>
   - <span data-ttu-id="f682f-216">Транзакция күні: eCommerce.eCommercePurchases.PurchasedOn</span><span class="sxs-lookup"><span data-stu-id="f682f-216">Transaction date: eCommerce.eCommercePurchases.PurchasedOn</span></span>
   - <span data-ttu-id="f682f-217">Транзакция сомасы: eCommerce.eCommercePurchases.TotalPrice</span><span class="sxs-lookup"><span data-stu-id="f682f-217">Transaction amount: eCommerce.eCommercePurchases.TotalPrice</span></span>
   - <span data-ttu-id="f682f-218">Өнім идентификаторы: eCommerce.eCommercePurchases.ProductId</span><span class="sxs-lookup"><span data-stu-id="f682f-218">Product ID: eCommerce.eCommercePurchases.ProductId</span></span>

1. <span data-ttu-id="f682f-219">**Келесі** пәрменін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="f682f-219">Select **Next**.</span></span>

1. <span data-ttu-id="f682f-220">**eCommercePurchases : eCommerce** нысаны мен  **eCommerceContacts : eCommerce** нысаны арасында қатынас орнатыңыз.</span><span class="sxs-lookup"><span data-stu-id="f682f-220">Set up the relationship between the **eCommercePurchases : eCommerce** entity and  **eCommerceContacts : eCommerce**.</span></span>

1. <span data-ttu-id="f682f-221">**Қосымша деректер (міндетті емес)** қадамы тұтынушының белсенділігі туралы көбірек деректер қосуға мүмкіндік береді.</span><span class="sxs-lookup"><span data-stu-id="f682f-221">The **Additional data (optional)** step allows you to add more customer activity data.</span></span> <span data-ttu-id="f682f-222">Бұл деректер тұтынушының сіздің бизнесіңізбен өзара әрекеттесуі туралы көбірек түсініктер алуға көмектеседі, бұл CLV құндылығына ықпал етуі мүмкін.</span><span class="sxs-lookup"><span data-stu-id="f682f-222">This data can help to get more insights for customer interactions with your business, which can contribute to CLV.</span></span> <span data-ttu-id="f682f-223">Веб-журналдар, тұтынушыға қызмет көрсету журналдары немесе марапаттар бағдарламасының тарихы сияқты тұтынушының негізгі өзара әрекеттесуін қосу болжамдардың дәлдігін жақсарта алады.</span><span class="sxs-lookup"><span data-stu-id="f682f-223">Adding key customer interactions like web logs, customer service logs, or rewards program history can improve the accuracy of predictions.</span></span> <span data-ttu-id="f682f-224">Тұтынушы әрекеті туралы қосымша деректерді қамту үшін **Деректер қосу** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="f682f-224">Select **Add data** to include more customer activity data.</span></span>

1. <span data-ttu-id="f682f-225">Тұтынушы әрекеті нысанын қосып, оның өрістерінің атауларын модельге қажет тиісті өрістермен салыстырыңыз:</span><span class="sxs-lookup"><span data-stu-id="f682f-225">Add the customer activity entity and map its fields names to the corresponding fields required by the model:</span></span>
   - <span data-ttu-id="f682f-226">Тұтынушы әрекетінің нысаны: Reviews:Website</span><span class="sxs-lookup"><span data-stu-id="f682f-226">Customer activity entity: Reviews:Website</span></span>
   - <span data-ttu-id="f682f-227">Бастапқы кілт: Website.Reviews.ReviewId</span><span class="sxs-lookup"><span data-stu-id="f682f-227">Primary key: Website.Reviews.ReviewId</span></span>
   - <span data-ttu-id="f682f-228">Уақыт белгісі: Website.Reviews.ReviewDate</span><span class="sxs-lookup"><span data-stu-id="f682f-228">Timestamp: Website.Reviews.ReviewDate</span></span>
   - <span data-ttu-id="f682f-229">Оқиға (әрекеттің атауы): Website.Reviews.ActivityTypeDisplay</span><span class="sxs-lookup"><span data-stu-id="f682f-229">Event (activity name): Website.Reviews.ActivityTypeDisplay</span></span>
   - <span data-ttu-id="f682f-230">Мәліметтер (сома немесе мән): Website.Reviews.ReviewRating</span><span class="sxs-lookup"><span data-stu-id="f682f-230">Details (amount or value): Website.Reviews.ReviewRating</span></span>

1. <span data-ttu-id="f682f-231">**Келесі** түймешігін таңдаңыз және транзакция деректері мен тұтынушы деректері арасындағы әрекет пен қатынасты конфигурациялаңыз:</span><span class="sxs-lookup"><span data-stu-id="f682f-231">Select **Next** and configure the activity and the relationship between the transaction data and the customer data:</span></span>  
   - <span data-ttu-id="f682f-232">Әреке түрі: бұрыннан барын таңдау</span><span class="sxs-lookup"><span data-stu-id="f682f-232">Activity type: Choose existing</span></span>
   - <span data-ttu-id="f682f-233">Әрекет белгісі: қарап шығу</span><span class="sxs-lookup"><span data-stu-id="f682f-233">Activity label: Review</span></span>
   - <span data-ttu-id="f682f-234">Сәйкес белгі: Website.Reviews.UserId</span><span class="sxs-lookup"><span data-stu-id="f682f-234">Corresponding label: Website.Reviews.UserId</span></span>
   - <span data-ttu-id="f682f-235">Тұтынушы нысаны: eCommerceContacts:eCommerce</span><span class="sxs-lookup"><span data-stu-id="f682f-235">Customer entity: eCommerceContacts:eCommerce</span></span>
   - <span data-ttu-id="f682f-236">Қатынас: WebsiteReviews</span><span class="sxs-lookup"><span data-stu-id="f682f-236">Relationship: WebsiteReviews</span></span>

1. <span data-ttu-id="f682f-237">Үлгі кестесін орнату үшін **Келесі** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="f682f-237">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="f682f-238">Модель жаңа деректер қабылданған кезде жаңа үлгілерді үйрену үшін үнемі жаттығуы керек.</span><span class="sxs-lookup"><span data-stu-id="f682f-238">The model needs to train regularly to learn new patterns when there's new data ingested.</span></span> <span data-ttu-id="f682f-239">Осы мысал үшін **Ай сайын** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="f682f-239">For this example, choose **Monthly**.</span></span>

1. <span data-ttu-id="f682f-240">Барлық мәліметтерді қарап шыққаннан кейін  **Сақтау және іске қосу** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="f682f-240">After reviewing all the details, select  **Save and Run**.</span></span>

## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="f682f-241">4-тапсырма – үлгі нәтижелері мен түсіндірмелерін қарап шығу</span><span class="sxs-lookup"><span data-stu-id="f682f-241">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="f682f-242">Үлгі жаттығуды аяқтап, деректерді бағалауды жүргізсін.</span><span class="sxs-lookup"><span data-stu-id="f682f-242">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="f682f-243">Содан кейін сіз CLV моделінің нәтижелері мен түсіндірмелерін қарап шығуға болады.</span><span class="sxs-lookup"><span data-stu-id="f682f-243">Next, you can review the CLV model results and explanations.</span></span> <span data-ttu-id="f682f-244">Қосымша ақпарат алу үшін [Болжам күйі мен нәтижелерін қарап шығу](predict-customer-lifetime-value.md#review-prediction-status-and-results) бөлімін қараңыз.</span><span class="sxs-lookup"><span data-stu-id="f682f-244">For more information, see [Review a prediction status and results](predict-customer-lifetime-value.md#review-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-value-customers"></a><span data-ttu-id="f682f-245">5-тапсырма - құндылығы жоғары тұтынушылар сегментін жасау</span><span class="sxs-lookup"><span data-stu-id="f682f-245">Task 5 - Create a segment of high value customers</span></span>

<span data-ttu-id="f682f-246">Модельді іске қосу **Деректер** > **Нысандар** тармағында тізімделген жаңа нысанды жасайды.</span><span class="sxs-lookup"><span data-stu-id="f682f-246">Running the model creates a new entity, which is listed on **Data** > **Entities**.</span></span> <span data-ttu-id="f682f-247">Модель жасаған нысан негізінде жаңа тұтынушы сегментін жасауға болады.</span><span class="sxs-lookup"><span data-stu-id="f682f-247">You can create a new customer segment based on the entity created by the model.</span></span>

1. <span data-ttu-id="f682f-248">**Сегменттер** бетіне өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="f682f-248">Go to **Segments**.</span></span> 

1. <span data-ttu-id="f682f-249">**Жаңа** опциясын таңдаңыз да, **Келесіден жасау** > **Интеллект** тармағын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="f682f-249">Select  **New** and choose **Create from** > **Intelligence**.</span></span>

   ![Үлгі шығысымен сегмент жасау.](media/segment-intelligence.png)

1. <span data-ttu-id="f682f-251">**OOBeCommerceCLVPrediction** нысанын таңдаңыз және сегментті анықтаңыз:</span><span class="sxs-lookup"><span data-stu-id="f682f-251">Select the  **OOBeCommerceCLVPrediction** entity and define the segment:</span></span>
  - <span data-ttu-id="f682f-252">Өріс: CLVScore</span><span class="sxs-lookup"><span data-stu-id="f682f-252">Field: CLVScore</span></span>
  - <span data-ttu-id="f682f-253">Амалдағыш: келесіден артық</span><span class="sxs-lookup"><span data-stu-id="f682f-253">Operator: greater than</span></span>
  - <span data-ttu-id="f682f-254">Мән: 1500</span><span class="sxs-lookup"><span data-stu-id="f682f-254">Value: 1500</span></span>

1. <span data-ttu-id="f682f-255">Сегментті **қарап шығу** және **сақтау** опцияларын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="f682f-255">Select **Review** and **Save** the segment.</span></span>

<span data-ttu-id="f682f-256">Енді сізде алдағы 12 айда $1500-ден көп кіріс әкелуі мүмкін деп болжанған тұтынушыларды анықтайтын сегмент бар.</span><span class="sxs-lookup"><span data-stu-id="f682f-256">You now have a segment that identifies customers who are predicted to generate more than $1500 of revenue in the next 12 months.</span></span> <span data-ttu-id="f682f-257">Егер қосымша деректер қабылданса, бұл сегмент динамикалық түрде жаңарады.</span><span class="sxs-lookup"><span data-stu-id="f682f-257">This segment gets updated dynamically if more data is ingested.</span></span>

<span data-ttu-id="f682f-258">Қосымша ақпаратты [Сегменттерді жасау және басқару](segments.md) бөлімінен қараңыз.</span><span class="sxs-lookup"><span data-stu-id="f682f-258">For more information, see [Create and manage segments](segments.md).</span></span>
