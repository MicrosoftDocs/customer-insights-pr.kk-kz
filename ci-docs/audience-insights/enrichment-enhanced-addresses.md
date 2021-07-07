---
title: Мекенжайды нақтылау және толықтыру
description: Microsoft модельдерімен тұтынушы профильдерінің мекенжай ақпаратын толықтырыңыз және қалыпқа келтіріңіз.
ms.date: 04/21/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: e0ca731f944da9a7eaae7c2dc2d7568b6386089f
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305439"
---
# <a name="enrichment-of-customer-profiles-with-enhanced-addresses"></a><span data-ttu-id="f26cc-103">Тұтынушы профильдерін нақтыланған мекенжайлармен толықтыру</span><span class="sxs-lookup"><span data-stu-id="f26cc-103">Enrichment of customer profiles with enhanced addresses</span></span>

<span data-ttu-id="f26cc-104">Деректеріңіздегі мекенжайлар құрылымсыз, толық емес немесе қате болуы мүмкін.</span><span class="sxs-lookup"><span data-stu-id="f26cc-104">Addresses in your data can be unstructured, incomplete, or incorrect.</span></span> <span data-ttu-id="f26cc-105">Дәлдік пен түсініктер үшін мекенжайларды қалыпқа келтіру және [Common Data Model пішімінде](/common-data-model/schema/core/applicationcommon/address) толықтыру үшін Microsoft модельдерін пайдаланыңыз.</span><span class="sxs-lookup"><span data-stu-id="f26cc-105">Use Microsoft's models to normalize and enrich your addresses into the [Common Data Model format](/common-data-model/schema/core/applicationcommon/address) for better accuracy and insights.</span></span>

## <a name="how-we-enhance-addresses"></a><span data-ttu-id="f26cc-106">Мекенжайларды нақтылау жолы</span><span class="sxs-lookup"><span data-stu-id="f26cc-106">How we enhance addresses</span></span>

<span data-ttu-id="f26cc-107">Біздің модель мекенжайды нақтылау үшін екі сатылы процестен өтеді.</span><span class="sxs-lookup"><span data-stu-id="f26cc-107">Our model goes through a two-step process to enhance an address.</span></span> <span data-ttu-id="f26cc-108">Біріншіден, ол мекенжайды құрамдастарын анықтау үшін талдайды және оларды құрылымдық пішімге енгізеді.</span><span class="sxs-lookup"><span data-stu-id="f26cc-108">First, it parses the address to identify its components and puts them into a structured format.</span></span> <span data-ttu-id="f26cc-109">Содан кейін біз мекенжайдағы мәндерді түзету, толықтыру және стандарттау үшін AI қолданамыз.</span><span class="sxs-lookup"><span data-stu-id="f26cc-109">Then, we use AI to correct, complete, and standardize the values in the address.</span></span>

### <a name="example"></a><span data-ttu-id="f26cc-110">Мысал</span><span class="sxs-lookup"><span data-stu-id="f26cc-110">Example</span></span>

<span data-ttu-id="f26cc-111">Мекенжай туралы ақпарат стандартты емес пішімде болуы мүмкін және онда емле қателері болуы мүмкін.</span><span class="sxs-lookup"><span data-stu-id="f26cc-111">Address information might be in a nonstandard format and contain spelling errors.</span></span> <span data-ttu-id="f26cc-112">Модель осы мәселелерді түзете алады және тұтынушы бірыңғай профильдерінде тұрақты мекенжайларды жасай алады.</span><span class="sxs-lookup"><span data-stu-id="f26cc-112">The model can fix these issues and create consistent addresses in unified customer profiles.</span></span>

```Input
4567 w main stret californa missouri 54321 us
```

```Output
- Street1: 4567 W Main St
- City: California
- StateOrProvince: MO
- ZipOrPostalCode: 54321
- CountryOrRegion: United States of America

- Address: 4567 W Main St, California, MO, 54321, United States of America
```

### <a name="limitations"></a><span data-ttu-id="f26cc-113">Шектеулер</span><span class="sxs-lookup"><span data-stu-id="f26cc-113">Limitations</span></span>

<span data-ttu-id="f26cc-114">Нақтыланған мекенжайлар тек енгізілген мекенжай деректеріңіздегі мәндермен жұмыс істейді.</span><span class="sxs-lookup"><span data-stu-id="f26cc-114">Enhanced addresses only works with the values that already exist in your ingested address data.</span></span> <span data-ttu-id="f26cc-115">Модель келесі әрекеттерді орындамайды:</span><span class="sxs-lookup"><span data-stu-id="f26cc-115">The model doesn't:</span></span> 

1. <span data-ttu-id="f26cc-116">Мекенжайдың жарамды мекенжай екенін тексеру.</span><span class="sxs-lookup"><span data-stu-id="f26cc-116">Verify if the address is a valid address.</span></span>
2. <span data-ttu-id="f26cc-117">Пошта индексі немесе көше атаулары сияқты мәндердің кез келгені жарамды екенін тексеру.</span><span class="sxs-lookup"><span data-stu-id="f26cc-117">Verify if any of the values, such as ZIP codes or street names, are valid.</span></span>
3. <span data-ttu-id="f26cc-118">Ол танымайтын мәндерді өзгерту.</span><span class="sxs-lookup"><span data-stu-id="f26cc-118">Change values it doesn't recognize.</span></span>

<span data-ttu-id="f26cc-119">Модельде мекенжайларды нақтылау үшін компьютерлік оқытуға негізделген әдістер қолданылады.</span><span class="sxs-lookup"><span data-stu-id="f26cc-119">The model uses machine learning-based techniques to enhance addresses.</span></span> <span data-ttu-id="f26cc-120">Модель кіріс мәнін өзгерткен кезде біз жоғары сенімділік шегін қолданамыз, бірақ кез келген компьютерлік оқытуға негізделген модель сияқты 100 пайыз дәлдікке кепілдік берілмейді.</span><span class="sxs-lookup"><span data-stu-id="f26cc-120">While we apply a high confidence threshold for when the model changes an input value, as with any machine learning-based model, 100 percent accuracy is not guaranteed.</span></span>

## <a name="supported-countries-or-regions"></a><span data-ttu-id="f26cc-121">Қолдау көрсетілетін елдер немесе аймақтар</span><span class="sxs-lookup"><span data-stu-id="f26cc-121">Supported countries or regions</span></span>

<span data-ttu-id="f26cc-122">Қазіргі уақытта біз осы елдердегі немесе аймақтардағы мекенжайларды толықтыруға қолдау көрсетеміз:</span><span class="sxs-lookup"><span data-stu-id="f26cc-122">We currently support enriching addresses in these countries or regions:</span></span> 

- <span data-ttu-id="f26cc-123">Австралия</span><span class="sxs-lookup"><span data-stu-id="f26cc-123">Australia</span></span>
- <span data-ttu-id="f26cc-124">Канада</span><span class="sxs-lookup"><span data-stu-id="f26cc-124">Canada</span></span>
- <span data-ttu-id="f26cc-125">Ұлыбритания Біріккен Корольдігі</span><span class="sxs-lookup"><span data-stu-id="f26cc-125">United Kingdom</span></span>
- <span data-ttu-id="f26cc-126">Америка Құрама Штаттары</span><span class="sxs-lookup"><span data-stu-id="f26cc-126">United States</span></span>

<span data-ttu-id="f26cc-127">Мекенжайлар ел/аймақ мәнін қамтуы керек.</span><span class="sxs-lookup"><span data-stu-id="f26cc-127">Addresses must contain a country/region value.</span></span> <span data-ttu-id="f26cc-128">Біз қолдау көрсетілмейтін елдер мен аймақтар үшін және ешқандай ел немесе аймақ көрсетілмеген мекенжайларды өңдемейміз.</span><span class="sxs-lookup"><span data-stu-id="f26cc-128">We don't process addresses for countries or regions that aren't supported and addresses that have no country or region provided.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="f26cc-129">Жақсартуды конфигурациялау</span><span class="sxs-lookup"><span data-stu-id="f26cc-129">Configure the enrichment</span></span>

1. <span data-ttu-id="f26cc-130">**Деректер** > **Толықтыру** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="f26cc-130">Go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="f26cc-131">**Нақтыланған мекенжайлар** тақтасында **Менің деректерімді толықтыру** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="f26cc-131">Select **Enrich my data** on the **Enhanced addresses** tile.</span></span>

   :::image type="content" source="media/enhanced-addresses-tile.png" alt-text="Нақтыланған мекенжайлар тақтасының скриншоты.":::

1. <span data-ttu-id="f26cc-133">**Тұтынушылардың деректер жиынтығы** параметрін таңдаңыз және нақтылау керек мекенжайларды қамтитын нысанды таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="f26cc-133">Select the **Customer data set** and choose the entity containing the addresses you want to enrich.</span></span> <span data-ttu-id="f26cc-134">Барлық тұтынушы профильдеріндегі мекенжайларды толықтыру үшін *Тұтынушы* нысанын немесе тек сол сегменттегі тұтынушы профильдеріндегі мекенжайларды толықтыру үшін сегмент нысанын таңдауға болады.</span><span class="sxs-lookup"><span data-stu-id="f26cc-134">You can select the *Customer* entity to enrich addresses in all your customer profiles or select a segment entity to enrich addresses only in customer profiles contained in that segment.</span></span>

1. <span data-ttu-id="f26cc-135">Деректер жиынтығында мекенжайларды пішімдеу жолын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="f26cc-135">Select how addresses are formatted in your data set.</span></span> <span data-ttu-id="f26cc-136">Егер деректеріңіздегі мекенжайлар бір өрісті қолданса **Бір төлсипатты мекенжай** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="f26cc-136">Choose **Single-attribute address** if addresses in your data use a single field.</span></span> <span data-ttu-id="f26cc-137">Егер деректеріңіздегі мекенжайлар бірнеше деректер өрісін қолданса **Бірнеше төлсипатты мекенжай** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="f26cc-137">Choose **Multiple-attribute address** if addresses in your data use more than one data field.</span></span>

   > [!NOTE]
   > <span data-ttu-id="f26cc-138">Ел/аймақ бір төлсипатты және бірнеше төлсипатты мекенжайларда міндетті.</span><span class="sxs-lookup"><span data-stu-id="f26cc-138">Country/Region is mandatory in both single-attribute and multiple-attribute addresses.</span></span> <span data-ttu-id="f26cc-139">Жарамды немесе қолдау көрсетілетін ел/аймақ мәндері жоқ мекенжайлар толықтырылмайды.</span><span class="sxs-lookup"><span data-stu-id="f26cc-139">Addresses that don't contain valid or supported country/region values won't be enriched.</span></span>

1.  <span data-ttu-id="f26cc-140">Бірыңғай тұтынушы нысанындағы мекенжай өрістерін салыстырыңыз.</span><span class="sxs-lookup"><span data-stu-id="f26cc-140">Map the address fields from your unified customer entity.</span></span>

    :::image type="content" source="media/enhanced-address-mapping.png" alt-text="Нақтыланған мекенжай өрісін салыстыру беті.":::

1. <span data-ttu-id="f26cc-142">Өрістерді салыстыруды аяқтау үшін **Келесі** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="f26cc-142">Select **Next** to complete the field mapping.</span></span>

1. <span data-ttu-id="f26cc-143">Толықтыру атауын және шығыс нысан атауын көрсетіңіз.</span><span class="sxs-lookup"><span data-stu-id="f26cc-143">Provide a name for the enrichment and the output entity.</span></span>

1. <span data-ttu-id="f26cc-144">Таңдауларды қарап шыққаннан кейін **Жақсартуды сақтау** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="f26cc-144">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="f26cc-145">Толықтыру нәтижелері</span><span class="sxs-lookup"><span data-stu-id="f26cc-145">Enrichment results</span></span>

<span data-ttu-id="f26cc-146">Арттыру процесін бастау үшін пәрмендер жолағынан **Іске қосу** пәрменін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="f26cc-146">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="f26cc-147">Сондай-ақ жүйеге [жоспарланған жаңарту](system.md#schedule-tab) бөлігі ретінде арттыруды автоматты түрде іске қосуына мүмкіндік беруге болады.</span><span class="sxs-lookup"><span data-stu-id="f26cc-147">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="f26cc-148">Өңдеу уақыты сіздің тұтынушы деректеріңіздің көлеміне байланысты.</span><span class="sxs-lookup"><span data-stu-id="f26cc-148">The processing time depends on the size of your customer data.</span></span>

<span data-ttu-id="f26cc-149">Арттыру процесі аяқталғаннан кейін, жаңа арттырылған тұтынушы профильдерінің деректерін **Менің арттыруларым** астынан қарап шығуға болады.</span><span class="sxs-lookup"><span data-stu-id="f26cc-149">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="f26cc-150">Сонымен қатар соңғы жаңартудың уақыты мен арттырылған профильдер санын таба аласыз.</span><span class="sxs-lookup"><span data-stu-id="f26cc-150">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="f26cc-151">**Толықтырылған деректерді көру** параметрін таңдау арқылы әрбір толықтырылған профильдің толық көрінісіне қатынаса аласыз.</span><span class="sxs-lookup"><span data-stu-id="f26cc-151">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="f26cc-152">Келесі қадамдар</span><span class="sxs-lookup"><span data-stu-id="f26cc-152">Next steps</span></span>

<span data-ttu-id="f26cc-153">Толықтырылған тұтынушы деректерінің негізінде жасаңыз.</span><span class="sxs-lookup"><span data-stu-id="f26cc-153">Build on top of your enriched customer data.</span></span> <span data-ttu-id="f26cc-154">Тұтынушыларға жеке тәжірибелер ұсыну үшін [сегменттер](segments.md) мен [өлшемдер](measures.md) жасаңыз және тіпті [деректерді экспорттаңыз](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="f26cc-154">Create [segments](segments.md) and [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
