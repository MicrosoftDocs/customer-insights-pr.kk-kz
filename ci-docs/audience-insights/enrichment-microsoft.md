---
title: Тұтынушы профильдерін Microsoft деректерімен жақсарту
description: Тұтынушы деректерін бренд және қызығушылық ұқсастықтарымен жақсарту үшін Microsoft корпорациясының жеке деректерін пайдаланыңыз.
ms.date: 06/14/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: e92360bb886739cfe477ce1d2eb62219228a0292
ms.sourcegitcommit: d4b4053f6ee8f60f1a214982c4726c9de84615ef
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 06/14/2021
ms.locfileid: "6245714"
---
# <a name="enrich-customer-profiles-with-brand-and-interest-affinities-preview"></a><span data-ttu-id="a9810-103">Тұтынушы деректерін бренд және қызығушылық ұқсастықтарымен толықтыру (алдын ала қарау)</span><span class="sxs-lookup"><span data-stu-id="a9810-103">Enrich customer profiles with brand and interest affinities (preview)</span></span>

<span data-ttu-id="a9810-104">Тұтынушы деректерін бренд және қызығушылық ұқсастықтарымен жақсарту үшін Microsoft корпорациясының жеке деректерін пайдаланыңыз.</span><span class="sxs-lookup"><span data-stu-id="a9810-104">Use Microsoft's proprietary data to enrich your customer data with brand and interest affinities.</span></span> <span data-ttu-id="a9810-105">Тұтынушыларға ұқсас демографиясы бар адамдардың деректеріне байланысты осы ұқсастықтар анықталады.</span><span class="sxs-lookup"><span data-stu-id="a9810-105">These affinities are determined based on data from people with similar demographics to your customers.</span></span> <span data-ttu-id="a9810-106">Бұл ақпарат брендтер мен қызығушылықтарға тән ұқсастықтарға байланысты тұтынушыларды сегменттеуге көмектеседі.</span><span class="sxs-lookup"><span data-stu-id="a9810-106">This information helps you to better understand and segment your customers based on their affinities to specific brands and interests.</span></span>

<span data-ttu-id="a9810-107">Аудитория түсініктерінде [арттыруларды конфигурациялау және қарау](enrichment-hub.md) үшін **Деректер** > **Арттыру** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="a9810-107">In audience insights, go to **Data** > **Enrichment** to [configure and view enrichments](enrichment-hub.md).</span></span>

<span data-ttu-id="a9810-108">Бренд ұқсастықтары толықтыруын теңшеу үшін **Табу** қойыншасына өтіп, **Брендтер** тақтасынан **Деректерімді толықтыру** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="a9810-108">To configure brand affinities enrichment, go to the **Discover** tab and select **Enrich my data** on the **Brands** tile.</span></span>

<span data-ttu-id="a9810-109">Қызығушылық ұқсастықтары толықтыруын теңшеу үшін **Табу** қойыншасына өтіп, **Қызығушылықтар** тақтасынан **Деректерімді толықтыру** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="a9810-109">To configure interest affinities enrichment, go to the **Discover** tab and select **Enrich my data** on the **Interests** tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="a9810-110">![Брендтер мен қызығушылықтар қатарлары](media/BrandsInterest-tile-Hub.png "Брендтер мен қызығушылық қатарлары")</span><span class="sxs-lookup"><span data-stu-id="a9810-110">![Brands & Interests tiles](media/BrandsInterest-tile-Hub.png "Brands & Interest tiles")</span></span>

## <a name="how-we-determine-affinities"></a><span data-ttu-id="a9810-111">Ұқсастықтарды анықтау жолы</span><span class="sxs-lookup"><span data-stu-id="a9810-111">How we determine affinities</span></span>

<span data-ttu-id="a9810-112">Біз әртүрлі демографиялық сегменттер бойынша брендтер мен қызығушылықтар (жасы, жынысы немесе орнына байланысты) ұқсастықтарын табу үшін Microsoft деректерді онлайн іздеу қызметіне қолданамыз.</span><span class="sxs-lookup"><span data-stu-id="a9810-112">We use Microsoft’s online search data to find affinities for brands and interests across various demographic segments (defined by age, gender, or location).</span></span> <span data-ttu-id="a9810-113">Брендке немесе қызығушылыққа арналған онлайн іздеу көлемі демографиялық сегменттің басқа сегменттермен салыстырғанда сол брендке немесе қызығушылыққа қаншалықты жақын екенін анықтайды.</span><span class="sxs-lookup"><span data-stu-id="a9810-113">The online search volume for a brand or interest determines how much affinity a demographic segment, compared to other segments, has to that brand or interest.</span></span>

## <a name="affinity-level-and-score"></a><span data-ttu-id="a9810-114">Ұқсастық деңгейі және ұпай</span><span class="sxs-lookup"><span data-stu-id="a9810-114">Affinity level and score</span></span>

<span data-ttu-id="a9810-115">Әр арттырылған тұтынушы профилінде екі сәйкес мәнді ұсынамыз - ұқсастық деңгейі және ұқсастық ұпайы.</span><span class="sxs-lookup"><span data-stu-id="a9810-115">On every enriched customer profile, we provide two related values – affinity level and affinity score.</span></span> <span data-ttu-id="a9810-116">Бұл мәндер басқа демографиялық сегменттермен салыстырғанда сол профильдің демографиялық сегментіне, брендке немесе қызығушылыққа қаншалықты жақын екендігін анықтауға көмектеседі.</span><span class="sxs-lookup"><span data-stu-id="a9810-116">These values help you determine how strong the affinity is for that profile’s demographic segment, for a brand or interest, as compared to other demographic segments.</span></span>

<span data-ttu-id="a9810-117">*Ұқсастық деңгейі* төрт деңгейден тұрады, ал *ұқсастық ұпайы* ұқсастық деңгейлеріне салыстырылатын 100 балдық шкаламен есептеледі.</span><span class="sxs-lookup"><span data-stu-id="a9810-117">*Affinity level* consists of four levels and *affinity score* is calculated on a 100-point scale that maps to the affinity levels.</span></span>


|<span data-ttu-id="a9810-118">Ұқсастық деңгейі</span><span class="sxs-lookup"><span data-stu-id="a9810-118">Affinity level</span></span> |<span data-ttu-id="a9810-119">Жақындық ұпайы</span><span class="sxs-lookup"><span data-stu-id="a9810-119">Affinity score</span></span>  |
|---------|---------|
|<span data-ttu-id="a9810-120">Өте жоғары</span><span class="sxs-lookup"><span data-stu-id="a9810-120">Very high</span></span>     | <span data-ttu-id="a9810-121">85-100</span><span class="sxs-lookup"><span data-stu-id="a9810-121">85-100</span></span>       |
|<span data-ttu-id="a9810-122">Жоғары</span><span class="sxs-lookup"><span data-stu-id="a9810-122">High</span></span>     | <span data-ttu-id="a9810-123">70-84</span><span class="sxs-lookup"><span data-stu-id="a9810-123">70-84</span></span>        |
|<span data-ttu-id="a9810-124">Орташа</span><span class="sxs-lookup"><span data-stu-id="a9810-124">Medium</span></span>     | <span data-ttu-id="a9810-125">35-69</span><span class="sxs-lookup"><span data-stu-id="a9810-125">35-69</span></span>        |
|<span data-ttu-id="a9810-126">Төмен</span><span class="sxs-lookup"><span data-stu-id="a9810-126">Low</span></span>     | <span data-ttu-id="a9810-127">1-34</span><span class="sxs-lookup"><span data-stu-id="a9810-127">1-34</span></span>        |

<span data-ttu-id="a9810-128">Ұқсастықты өлшегіңіз келетін нақтылауға байланысты ұқсастық деңгейін де, ұпайды да пайдалануға болады.</span><span class="sxs-lookup"><span data-stu-id="a9810-128">Depending on the granularity you would like for measuring the affinity, you can use either affinity level or score.</span></span> <span data-ttu-id="a9810-129">Ұқсастық ұпайы нақты бақылауды ұсынады.</span><span class="sxs-lookup"><span data-stu-id="a9810-129">Affinity score gives you more precise control.</span></span>

## <a name="supported-countriesregions"></a><span data-ttu-id="a9810-130">Қолдау көрсетілетін елдер/аймақтар</span><span class="sxs-lookup"><span data-stu-id="a9810-130">Supported countries/regions</span></span>

<span data-ttu-id="a9810-131">Қазіргі уақытта біз келесі ел/аймақ параметрлерін қолдаймыз: Австралия, Канада (ағылшын), Франция, Германия, Біріккен Корольдік немесе Америка Құрама Штаттары (ағылшын).</span><span class="sxs-lookup"><span data-stu-id="a9810-131">We currently support the following country/region options: Australia, Canada (English), France, Germany, United Kingdom, or United States (English).</span></span>

<span data-ttu-id="a9810-132">Елді таңдау үшін **Брендтерді арттыру** немесе **Қызығушылықты арттыру** пәрменін таңдаңыз және **Ел/аймақ** жанында **Өзгерту** пәрменін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="a9810-132">To select a country, open the **Brands enrichment** or **Interest enrichment** and select **Change** next to **Country/Region**.</span></span> <span data-ttu-id="a9810-133">**Ел/аймақ параметрлері** тақтасында параметрді таңдап, **Қолдану** пәрменін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="a9810-133">In the **Country/Region settings** pane, choose an option and select **Apply**.</span></span>

### <a name="implications-related-to-country-selection"></a><span data-ttu-id="a9810-134">Елді таңдауға қатысты салдарлар</span><span class="sxs-lookup"><span data-stu-id="a9810-134">Implications related to country selection</span></span>

- <span data-ttu-id="a9810-135">[Өз брендтеріңізді таңдағанда](#define-your-brands-or-interests) жүйе таңдалған елге немесе аймаққа негізделген ұсыныстарды ұсынады.</span><span class="sxs-lookup"><span data-stu-id="a9810-135">When [choosing your own brands](#define-your-brands-or-interests), the system provides suggestions based on the selected country or region.</span></span>

- <span data-ttu-id="a9810-136">[Саланы таңдағанда](#define-your-brands-or-interests) таңдаған елге немесе аймаққа байланысты ең маңызды брендтер мен қызығушылықтарды аласыз.</span><span class="sxs-lookup"><span data-stu-id="a9810-136">When [choosing an industry](#define-your-brands-or-interests), you'll get the most relevant brands or interests based on the selected country or region.</span></span>

- <span data-ttu-id="a9810-137">[Профильдерді арттыру](#refresh-enrichment) кезінде біз таңдалған брендтер мен қызығушылықтар туралы мәліметтер алатын тұтынушылардың барлық профильдерін арттырамыз.</span><span class="sxs-lookup"><span data-stu-id="a9810-137">When [enriching profiles](#refresh-enrichment), we'll enrich all customer profiles for which we get data for the selected brands and interests.</span></span> <span data-ttu-id="a9810-138">Таңдалған елде немесе аймақта жоқ профильдерді қоса алғанда.</span><span class="sxs-lookup"><span data-stu-id="a9810-138">Including profiles that are not in the selected country or region.</span></span> <span data-ttu-id="a9810-139">Мысалы, егер сіз Германияны таңдаған болсаңыз, бізде АҚШ-та таңдалған брендтер мен қызығушылықтар туралы деректер қолжетімді болса, біз Америка Құрама Штаттарында орналасқан профильдерді жақсартамыз.</span><span class="sxs-lookup"><span data-stu-id="a9810-139">For example, if you selected Germany, we'll enrich profiles located in the United States if we have data available for the selected brands and interests in the US.</span></span>

## <a name="configure-enrichment"></a><span data-ttu-id="a9810-140">Толықтыруды теңшеу</span><span class="sxs-lookup"><span data-stu-id="a9810-140">Configure Enrichment</span></span>

<span data-ttu-id="a9810-141">Қадамдық тәжірибе сізге жақсартуды конфигурациялауға көмектеседі.</span><span class="sxs-lookup"><span data-stu-id="a9810-141">A guided experience helps you through the configuration of the enrichments.</span></span> 

### <a name="define-your-brands-or-interests"></a><span data-ttu-id="a9810-142">Брендтерді немесе қызығушылықтарды анықтау</span><span class="sxs-lookup"><span data-stu-id="a9810-142">Define your brands or interests</span></span>

<span data-ttu-id="a9810-143">Осы нұсқалардың біреуін немесе екеуін де қолдана отырып, бес брендті немесе қызығушылықтарды таңдаңыз:</span><span class="sxs-lookup"><span data-stu-id="a9810-143">Choose up to five brands or interests using one or both of these options:</span></span>

- <span data-ttu-id="a9810-144">**Өндіріс**: ашылмалы тізімнен өндірісті таңдаңыз және содан кейін сол өндіріске арналған үздік брендтер мен қызығушылықтардан таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="a9810-144">**Industry**: Select your industry from the drop-down list and then choose from the top brands or interests for that industry.</span></span>
- <span data-ttu-id="a9810-145">**Өзіңіздікін таңдаңыз**: ұйымыңызға сәйкес келетін брендті немесе қызығушылықты енгізіп, сәйкес ұсыныстардан таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="a9810-145">**Choose your own**: Enter a brand or interest that is relevant to your organization and then choose from the matching suggestions.</span></span> <span data-ttu-id="a9810-146">Егер іздеген бренд немесе қызығушылық көрсетілмесе, **Ұсыну** сілтемесі арқылы бізге кері байланыс жіберіңіз.</span><span class="sxs-lookup"><span data-stu-id="a9810-146">If we don't list a brand or interest you're looking for, send us feedback using the **Suggest** link.</span></span>

### <a name="review-enrichment-preferences"></a><span data-ttu-id="a9810-147">Арттыру параметрлерін қарап шығу</span><span class="sxs-lookup"><span data-stu-id="a9810-147">Review enrichment preferences</span></span>

<span data-ttu-id="a9810-148">Әдепкі арттыру параметрлерін қарап шығыңыз және қажет болған жағдайда оларды жаңартыңыз.</span><span class="sxs-lookup"><span data-stu-id="a9810-148">Review your default enrichment preferences and update them as needed.</span></span>

:::image type="content" source="media/affinity-enrichment-preferences.png" alt-text="Арттыру параметрлері терезесінің скриншоты.":::

### <a name="select-entity-to-enrich"></a><span data-ttu-id="a9810-150">Арттыру үшін нысанды таңдау</span><span class="sxs-lookup"><span data-stu-id="a9810-150">Select entity to enrich</span></span>

<span data-ttu-id="a9810-151">**Жақсартылған нысан** түймешігін таңдаңыз және Microsoft компания деректерімен жақсарту керек деректер жиынтығын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="a9810-151">Select **Enriched entity** and choose the data set you want to enrich with company data from the Microsoft.</span></span> <span data-ttu-id="a9810-152">Барлық тұтынушы профильдерін арттыру үшін Тұтынушы нысанын таңдауға болады немесе сол сегменттегі тек тұтынушы профильдерін арттыру үшін сегмент нысанын таңдауға болады.</span><span class="sxs-lookup"><span data-stu-id="a9810-152">You can select the Customer entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

### <a name="map-your-fields"></a><span data-ttu-id="a9810-153">Өрістерді салыстыру</span><span class="sxs-lookup"><span data-stu-id="a9810-153">Map your fields</span></span>

<span data-ttu-id="a9810-154">Тұтынушы деректерін арттыру үшін жүйені пайдаланғыңыз келетін демографиялық сегментті анықтау үшін бірыңғай тұтынушы нысан өрістерін салыстырыңыз.</span><span class="sxs-lookup"><span data-stu-id="a9810-154">Map fields from your unified customer entity to define the demographic segment you want the system to use for enriching your customer data.</span></span> <span data-ttu-id="a9810-155">Ел/аймақ және кем дегенде туған күні немесе жынысы төлсипаттарын салыстырыңыз.</span><span class="sxs-lookup"><span data-stu-id="a9810-155">Map Country/Region and at least Date of Birth or Gender attributes.</span></span> <span data-ttu-id="a9810-156">Сонымен қатар сіз қаланың (және облыстың/ауданның) немесе пошталық индекстің кем дегенде біреуін салыстыру қажет.</span><span class="sxs-lookup"><span data-stu-id="a9810-156">Additionally, you must map at least one of City (and State/Province) or Postal code.</span></span> <span data-ttu-id="a9810-157">Өрістердің салыстыруын анықтау үшін **Өңдеу** параметрін таңдап, орындалған кезде **Қолдану** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="a9810-157">Select **Edit** to define the mapping of the fields and select **Apply** when you're done.</span></span> <span data-ttu-id="a9810-158">Өрісті салыстыруды аяқтау үшін **Сақтау** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="a9810-158">Select **Save** to complete the field mapping.</span></span>

<span data-ttu-id="a9810-159">Келесі пішімдер мен мәндерге қолдау көрсетіледі, мәндер регистрді ескермейді:</span><span class="sxs-lookup"><span data-stu-id="a9810-159">The following formats and values are supported, values are not case-sensitive:</span></span>

- <span data-ttu-id="a9810-160">**Туған күні**: біз деректерді қабылдау кезінде туған күнді DateTime түріне түрлендіруді ұсынамыз.</span><span class="sxs-lookup"><span data-stu-id="a9810-160">**Date of Birth**: We recommend that date of birth is converted to DateTime type during data ingestion.</span></span> <span data-ttu-id="a9810-161">Я болмаса, бұл [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) «yyyy-MM-dd» немесе «yyyy-MM-ddTHH: mm: ssZ» пішіміндегі жол болуы мүмкін.</span><span class="sxs-lookup"><span data-stu-id="a9810-161">Alternatively, it can be a string in [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) format "yyyy-MM-dd" or "yyyy-MM-ddTHH:mm:ssZ".</span></span>
- <span data-ttu-id="a9810-162">**Жынысы**: ер, әйел, белгісіз</span><span class="sxs-lookup"><span data-stu-id="a9810-162">**Gender**: Male, Female, Unknown</span></span>
- <span data-ttu-id="a9810-163">**Пошта индексі**: АҚШ үшін бес цифрлық пошталық индекстер, барлық басқа жерде стандартты пошталық индекс</span><span class="sxs-lookup"><span data-stu-id="a9810-163">**Postal code**: Five-digit ZIP Codes for US, standard postal code everywhere else</span></span>
- <span data-ttu-id="a9810-164">**Қала**: ағылшын тіліндегі қала атауы</span><span class="sxs-lookup"><span data-stu-id="a9810-164">**City**: City name in English</span></span>
- <span data-ttu-id="a9810-165">**Штат/провинция**: АҚШ пен Канадаға арналған екі әріптік қысқарту.</span><span class="sxs-lookup"><span data-stu-id="a9810-165">**State/Province**: Two-letter abbreviation for the US and Canada.</span></span> <span data-ttu-id="a9810-166">Австралияға арналған екі немесе үш әріптік қысқарту.</span><span class="sxs-lookup"><span data-stu-id="a9810-166">Two or three letter abbreviation for Australia.</span></span> <span data-ttu-id="a9810-167">Франция, Германия немесе Біріккен Корольдік елдеріне қатысты емес.</span><span class="sxs-lookup"><span data-stu-id="a9810-167">Not applicable for France, Germany, or the UK.</span></span>
- <span data-ttu-id="a9810-168">**Ел/аймақ**:</span><span class="sxs-lookup"><span data-stu-id="a9810-168">**Country/Region**:</span></span>

  - <span data-ttu-id="a9810-169">АҚШ: Америка Құрама Штаттары, Құрама Штаттар, АҚШ, Америка</span><span class="sxs-lookup"><span data-stu-id="a9810-169">US: United States of America, United States, USA, US, America</span></span>
  - <span data-ttu-id="a9810-170">CA: Канада, CA</span><span class="sxs-lookup"><span data-stu-id="a9810-170">CA: Canada, CA</span></span>
  - <span data-ttu-id="a9810-171">GB: Біріккен Корольдік, UK, Ұлыбритания, Ұлыбритания, GB, Ұлыбритания және Солтүстік Ирландия Біріккен Корольдігі, Ұлыбритания Біріккен Корольдігі</span><span class="sxs-lookup"><span data-stu-id="a9810-171">GB: United Kingdom, UK, Great Britain, GB, United Kingdom of Great Britain and Northern Ireland, United Kingdom of Great Britain</span></span>
  - <span data-ttu-id="a9810-172">AU: Австралия, AU, Австралиялық одақ</span><span class="sxs-lookup"><span data-stu-id="a9810-172">AU: Australia, AU, Common Wealth of Australia</span></span>
  - <span data-ttu-id="a9810-173">FR: Франция, FR, Франция Республикасы</span><span class="sxs-lookup"><span data-stu-id="a9810-173">FR: France, FR, French Republic</span></span>
  - <span data-ttu-id="a9810-174">DE: Германия, германиялық, Deutschland, Allemagne, DE, Германия Федеративтік Республикасы, Германия Республикасы</span><span class="sxs-lookup"><span data-stu-id="a9810-174">DE: Germany, German, Deutschland, Allemagne, DE, Federal Republic of Germany, Republic of Germany</span></span>

## <a name="review-and-name-the-enrichment"></a><span data-ttu-id="a9810-175">Жақсартуды қарап шығу және ат беру</span><span class="sxs-lookup"><span data-stu-id="a9810-175">Review and name the enrichment</span></span>

<span data-ttu-id="a9810-176">Соңында сіз ақпаратты қарап шығып, жақсарту атын бересіз.</span><span class="sxs-lookup"><span data-stu-id="a9810-176">Finally, you get to review the information and provide a name for the enrichment.</span></span>

:::image type="content" source="media/enrichment-interests-summary.png" alt-text="Қызығушылықтарды қарап шығу және атау беру беті.":::

## <a name="refresh-enrichment"></a><span data-ttu-id="a9810-178">Арттыруды жаңарту</span><span class="sxs-lookup"><span data-stu-id="a9810-178">Refresh enrichment</span></span>

<span data-ttu-id="a9810-179">Демографиялық көрсеткіштерге арналған брендтерді, қызығушылықтарды және өрістерді салыстыруды конфигурациялағаннан кейін толықтыруды бастаңыз.</span><span class="sxs-lookup"><span data-stu-id="a9810-179">Run the enrichment after configuring brands, interests, and the field mapping for demographics.</span></span> <span data-ttu-id="a9810-180">Процесті бастау үшін бренд немесе қызығушылық конфигурациясы тақтасынан **Іске қосу** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="a9810-180">To start the process, select **Run** on the brand or interest configuration page.</span></span> <span data-ttu-id="a9810-181">Оған қоса жүйеде толықтыру процесін жоспарланған жаңарту бөлігі ретінде автоматты іске қосуға мүмкіндік бере аласыз.</span><span class="sxs-lookup"><span data-stu-id="a9810-181">Additionally, you can let the system run the enrichment automatically as part of a scheduled refresh.</span></span>
<span data-ttu-id="a9810-182">Тұтынушы деректерінің көлеміне байланысты, толықтыруды аяқтауға бірнеше минут кетуі мүмкін.</span><span class="sxs-lookup"><span data-stu-id="a9810-182">Depending on the size of your customer data, it may take several minutes for an enrichment run to complete.</span></span>

> [!TIP]
> <span data-ttu-id="a9810-183">Тапсырмалар/процестерге арналған [күйдің алты түрі](system.md#status-types) бар.</span><span class="sxs-lookup"><span data-stu-id="a9810-183">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="a9810-184">Сонымен қатар көптеген процестер [басқа кезектегі процестерге тәуелді](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="a9810-184">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="a9810-185">Бүкіл тапсырманың барысы туралы мәліметтерді көру үшін процестің күйін таңдай аласыз.</span><span class="sxs-lookup"><span data-stu-id="a9810-185">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="a9810-186">Бір жұмыс тапсырмаларының бірі үшін **Мәліметтерді көру** параметрін таңдағаннан кейін, қосымша ақпаратты көруге болады: өңдеу уақыты, соңғы өңделген күні және тапсырмаға қатысты барлық қателер мен ескертулер.</span><span class="sxs-lookup"><span data-stu-id="a9810-186">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="a9810-187">Толықтыру нәтижелері</span><span class="sxs-lookup"><span data-stu-id="a9810-187">Enrichment results</span></span>

<span data-ttu-id="a9810-188">Толықтыру процесін бастағаннан кейін толықтырылған тұтынушылардың жалпы санын және тұтынушылардың толықтырылған профильдеріндегі брендтердің немесе қызығушылықтардың өзгеруін қарастыру үшін **Менің толықтыруларым** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="a9810-188">After running the enrichment process, go to **My enrichments** to review the total number of enriched customers and a breakdown of brands or interests in the enriched customer profiles.</span></span>

:::image type="content" source="media/my-enrichments.png" alt-text="Толықтыру процесін іске қосқаннан кейінгі нәтижелерді алдын ала қарау":::

<span data-ttu-id="a9810-190">Диаграммадан **Толықтырылған деректерді қарау** опциясын таңдау арқылы толықтырылған деректерді қараңыз.</span><span class="sxs-lookup"><span data-stu-id="a9810-190">Review the enriched data by selecting **View enriched data** in the chart.</span></span> <span data-ttu-id="a9810-191">Брендтер үшін толықтырылған деректер **BrandAffinityFromMicrosoft** нысанына өтеді.</span><span class="sxs-lookup"><span data-stu-id="a9810-191">Enriched data for brands goes to the **BrandAffinityFromMicrosoft** entity.</span></span> <span data-ttu-id="a9810-192">**InterestAffinityFromMicrosoft** нысанындағы қызығушылықтарға арналған деректер.</span><span class="sxs-lookup"><span data-stu-id="a9810-192">Data for interests is in the **InterestAffinityFromMicrosoft** entity.</span></span> <span data-ttu-id="a9810-193">**Деректер** > **Нысандар** тармағындағы **Толықтыру** тобында тізімделген осы нысандарды да таба аласыз.</span><span class="sxs-lookup"><span data-stu-id="a9810-193">You'll also find these entities listed in the **Enrichment** group in **Data** > **Entities**.</span></span>

## <a name="see-enrichment-data-on-the-customer-card"></a><span data-ttu-id="a9810-194">Тұтынушы картасынан толықтыру деректерін көру</span><span class="sxs-lookup"><span data-stu-id="a9810-194">See enrichment data on the customer card</span></span>

<span data-ttu-id="a9810-195">Сонымен қатар жеке тұтынушы карталарынан бренд пен қызығушылық ұқсастықтарын көре аласыз.</span><span class="sxs-lookup"><span data-stu-id="a9810-195">Brand and interest affinities can also be viewed on individual customer cards.</span></span> <span data-ttu-id="a9810-196">**Тұтынушылар** тармағына өтіп, тұтынушы профилін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="a9810-196">Go to **Customers** and select a customer profile.</span></span> <span data-ttu-id="a9810-197">Тұтынушы картасында тұтынушының демографиялық профилінде қамтылған адамдар брендтері немесе қызығушылықтары сызбаларын табасыз.</span><span class="sxs-lookup"><span data-stu-id="a9810-197">In the customer card, you'll find charts for the brands or interests that people in that customer's demographic profile have affinity for.</span></span>

:::image type="content" source="media/enrichment-customer-card.png" alt-text="Толықтырылған деректері бар тұтынушы картасы":::

## <a name="next-steps"></a><span data-ttu-id="a9810-199">Келесі қадамдар</span><span class="sxs-lookup"><span data-stu-id="a9810-199">Next steps</span></span>

<span data-ttu-id="a9810-200">Толықтырылған тұтынушы деректерінің негізінде жасаңыз.</span><span class="sxs-lookup"><span data-stu-id="a9810-200">Build on top of your enriched customer data.</span></span> <span data-ttu-id="a9810-201">Тұтынушыларға жекелендірілген тәжірибелерді жеткізу үшін [Сегменттер](segments.md), [Шаралар](measures.md) жасаңыз және [деректерді экспорттаңыз](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="a9810-201">Create [Segments](segments.md), [Measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
