---
title: Тұтынушы профильдерін Microsoft деректерімен жақсарту
description: Тұтынушы деректерін бренд және қызығушылық ұқсастықтарымен жақсарту үшін Microsoft корпорациясының жеке деректерін пайдаланыңыз.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: be042dd139607849b795c903fa58da2edb9ff589
ms.sourcegitcommit: 72603fb39c4d5dbca71128815a2e1692542ea4dc
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 05/19/2021
ms.locfileid: "6064898"
---
# <a name="enrich-customer-profiles-with-brand-and-interest-affinities-preview"></a><span data-ttu-id="7a2ac-103">Тұтынушы деректерін бренд және қызығушылық ұқсастықтарымен толықтыру (алдын ала қарау)</span><span class="sxs-lookup"><span data-stu-id="7a2ac-103">Enrich customer profiles with brand and interest affinities (preview)</span></span>

<span data-ttu-id="7a2ac-104">Тұтынушы деректерін бренд және қызығушылық ұқсастықтарымен жақсарту үшін Microsoft корпорациясының жеке деректерін пайдаланыңыз.</span><span class="sxs-lookup"><span data-stu-id="7a2ac-104">Use Microsoft's proprietary data to enrich your customer data with brand and interest affinities.</span></span> <span data-ttu-id="7a2ac-105">Тұтынушыларға ұқсас демографиясы бар адамдардың деректеріне байланысты осы ұқсастықтар анықталады.</span><span class="sxs-lookup"><span data-stu-id="7a2ac-105">These affinities are determined based on data from people with similar demographics to your customers.</span></span> <span data-ttu-id="7a2ac-106">Бұл ақпарат брендтер мен қызығушылықтарға тән ұқсастықтарға байланысты тұтынушыларды сегменттеуге көмектеседі.</span><span class="sxs-lookup"><span data-stu-id="7a2ac-106">This information helps you to better understand and segment your customers based on their affinities to specific brands and interests.</span></span>

<span data-ttu-id="7a2ac-107">Аудитория түсініктерінде [арттыруларды конфигурациялау және қарау](enrichment-hub.md) үшін **Деректер** > **Арттыру** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="7a2ac-107">In audience insights, go to **Data** > **Enrichment** to [configure and view enrichments](enrichment-hub.md).</span></span>

<span data-ttu-id="7a2ac-108">Бренд ұқсастықтары толықтыруын теңшеу үшін **Табу** қойыншасына өтіп, **Брендтер** тақтасынан **Деректерімді толықтыру** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="7a2ac-108">To configure brand affinities enrichment, go to the **Discover** tab and select **Enrich my data** on the **Brands** tile.</span></span>

<span data-ttu-id="7a2ac-109">Қызығушылық ұқсастықтары толықтыруын теңшеу үшін **Табу** қойыншасына өтіп, **Қызығушылықтар** тақтасынан **Деректерімді толықтыру** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="7a2ac-109">To configure interest affinities enrichment, go to the **Discover** tab and select **Enrich my data** on the **Interests** tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="7a2ac-110">![Брендтер мен қызығушылықтар қатарлары](media/BrandsInterest-tile-Hub.png "Брендтер мен қызығушылық қатарлары")</span><span class="sxs-lookup"><span data-stu-id="7a2ac-110">![Brands & Interests tiles](media/BrandsInterest-tile-Hub.png "Brands & Interest tiles")</span></span>

## <a name="how-we-determine-affinities"></a><span data-ttu-id="7a2ac-111">Ұқсастықтарды анықтау жолы</span><span class="sxs-lookup"><span data-stu-id="7a2ac-111">How we determine affinities</span></span>

<span data-ttu-id="7a2ac-112">Біз әртүрлі демографиялық сегменттер бойынша брендтер мен қызығушылықтар (жасы, жынысы немесе орнына байланысты) ұқсастықтарын табу үшін Microsoft деректерді онлайн іздеу қызметіне қолданамыз.</span><span class="sxs-lookup"><span data-stu-id="7a2ac-112">We use Microsoft’s online search data to find affinities for brands and interests across various demographic segments (defined by age, gender, or location).</span></span> <span data-ttu-id="7a2ac-113">Брендке немесе қызығушылыққа арналған онлайн іздеу көлемі демографиялық сегменттің басқа сегменттермен салыстырғанда сол брендке немесе қызығушылыққа қаншалықты жақын екенін анықтайды.</span><span class="sxs-lookup"><span data-stu-id="7a2ac-113">The online search volume for a brand or interest determines how much affinity a demographic segment, compared to other segments, has to that brand or interest.</span></span>

## <a name="affinity-level-and-score"></a><span data-ttu-id="7a2ac-114">Ұқсастық деңгейі және ұпай</span><span class="sxs-lookup"><span data-stu-id="7a2ac-114">Affinity level and score</span></span>

<span data-ttu-id="7a2ac-115">Әр арттырылған тұтынушы профилінде екі сәйкес мәнді ұсынамыз - ұқсастық деңгейі және ұқсастық ұпайы.</span><span class="sxs-lookup"><span data-stu-id="7a2ac-115">On every enriched customer profile, we provide two related values – affinity level and affinity score.</span></span> <span data-ttu-id="7a2ac-116">Бұл мәндер басқа демографиялық сегменттермен салыстырғанда сол профильдің демографиялық сегментіне, брендке немесе қызығушылыққа қаншалықты жақын екендігін анықтауға көмектеседі.</span><span class="sxs-lookup"><span data-stu-id="7a2ac-116">These values help you determine how strong the affinity is for that profile’s demographic segment, for a brand or interest, as compared to other demographic segments.</span></span>

<span data-ttu-id="7a2ac-117">*Ұқсастық деңгейі* төрт деңгейден тұрады, ал *ұқсастық ұпайы* ұқсастық деңгейлеріне салыстырылатын 100 балдық шкаламен есептеледі.</span><span class="sxs-lookup"><span data-stu-id="7a2ac-117">*Affinity level* consists of four levels and *affinity score* is calculated on a 100-point scale that maps to the affinity levels.</span></span>


|<span data-ttu-id="7a2ac-118">Ұқсастық деңгейі</span><span class="sxs-lookup"><span data-stu-id="7a2ac-118">Affinity level</span></span> |<span data-ttu-id="7a2ac-119">Жақындық ұпайы</span><span class="sxs-lookup"><span data-stu-id="7a2ac-119">Affinity score</span></span>  |
|---------|---------|
|<span data-ttu-id="7a2ac-120">Өте жоғары</span><span class="sxs-lookup"><span data-stu-id="7a2ac-120">Very high</span></span>     | <span data-ttu-id="7a2ac-121">85-100</span><span class="sxs-lookup"><span data-stu-id="7a2ac-121">85-100</span></span>       |
|<span data-ttu-id="7a2ac-122">Жоғары</span><span class="sxs-lookup"><span data-stu-id="7a2ac-122">High</span></span>     | <span data-ttu-id="7a2ac-123">70-84</span><span class="sxs-lookup"><span data-stu-id="7a2ac-123">70-84</span></span>        |
|<span data-ttu-id="7a2ac-124">Орташа</span><span class="sxs-lookup"><span data-stu-id="7a2ac-124">Medium</span></span>     | <span data-ttu-id="7a2ac-125">35-69</span><span class="sxs-lookup"><span data-stu-id="7a2ac-125">35-69</span></span>        |
|<span data-ttu-id="7a2ac-126">Төмен</span><span class="sxs-lookup"><span data-stu-id="7a2ac-126">Low</span></span>     | <span data-ttu-id="7a2ac-127">1-34</span><span class="sxs-lookup"><span data-stu-id="7a2ac-127">1-34</span></span>        |

<span data-ttu-id="7a2ac-128">Ұқсастықты өлшегіңіз келетін нақтылауға байланысты ұқсастық деңгейін де, ұпайды да пайдалануға болады.</span><span class="sxs-lookup"><span data-stu-id="7a2ac-128">Depending on the granularity you would like for measuring the affinity, you can use either affinity level or score.</span></span> <span data-ttu-id="7a2ac-129">Ұқсастық ұпайы нақты бақылауды ұсынады.</span><span class="sxs-lookup"><span data-stu-id="7a2ac-129">Affinity score gives you more precise control.</span></span>

## <a name="supported-countriesregions"></a><span data-ttu-id="7a2ac-130">Қолдау көрсетілетін елдер/аймақтар</span><span class="sxs-lookup"><span data-stu-id="7a2ac-130">Supported countries/regions</span></span>

<span data-ttu-id="7a2ac-131">Қазіргі уақытта біз келесі ел/аймақ параметрлерін қолдаймыз: Австралия, Канада (ағылшын), Франция, Германия, Біріккен Корольдік немесе Америка Құрама Штаттары (ағылшын).</span><span class="sxs-lookup"><span data-stu-id="7a2ac-131">We currently support the following country/region options: Australia, Canada (English), France, Germany, United Kingdom, or United States (English).</span></span>

<span data-ttu-id="7a2ac-132">Елді таңдау үшін **Брендтерді арттыру** немесе **Қызығушылықты арттыру** пәрменін таңдаңыз және **Ел/аймақ** жанында **Өзгерту** пәрменін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="7a2ac-132">To select a country, open the **Brands enrichment** or **Interest enrichment** and select **Change** next to **Country/Region**.</span></span> <span data-ttu-id="7a2ac-133">**Ел/аймақ параметрлері** тақтасында параметрді таңдап, **Қолдану** пәрменін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="7a2ac-133">In the **Country/Region settings** pane, choose an option and select **Apply**.</span></span>

### <a name="implications-related-to-country-selection"></a><span data-ttu-id="7a2ac-134">Елді таңдауға қатысты салдарлар</span><span class="sxs-lookup"><span data-stu-id="7a2ac-134">Implications related to country selection</span></span>

- <span data-ttu-id="7a2ac-135">[Өз брендтеріңізді таңдағанда](#define-your-brands-or-interests) жүйе таңдалған елге немесе аймаққа негізделген ұсыныстарды ұсынады.</span><span class="sxs-lookup"><span data-stu-id="7a2ac-135">When [choosing your own brands](#define-your-brands-or-interests), the system provides suggestions based on the selected country or region.</span></span>

- <span data-ttu-id="7a2ac-136">[Саланы таңдағанда](#define-your-brands-or-interests) таңдаған елге немесе аймаққа байланысты ең маңызды брендтер мен қызығушылықтарды аласыз.</span><span class="sxs-lookup"><span data-stu-id="7a2ac-136">When [choosing an industry](#define-your-brands-or-interests), you'll get the most relevant brands or interests based on the selected country or region.</span></span>

- <span data-ttu-id="7a2ac-137">[Профильдерді арттыру](#refresh-enrichment) кезінде біз таңдалған брендтер мен қызығушылықтар туралы мәліметтер алатын тұтынушылардың барлық профильдерін арттырамыз.</span><span class="sxs-lookup"><span data-stu-id="7a2ac-137">When [enriching profiles](#refresh-enrichment), we'll enrich all customer profiles for which we get data for the selected brands and interests.</span></span> <span data-ttu-id="7a2ac-138">Таңдалған елде немесе аймақта жоқ профильдерді қоса алғанда.</span><span class="sxs-lookup"><span data-stu-id="7a2ac-138">Including profiles that are not in the selected country or region.</span></span> <span data-ttu-id="7a2ac-139">Мысалы, егер сіз Германияны таңдаған болсаңыз, бізде АҚШ-та таңдалған брендтер мен қызығушылықтар туралы деректер қолжетімді болса, біз Америка Құрама Штаттарында орналасқан профильдерді жақсартамыз.</span><span class="sxs-lookup"><span data-stu-id="7a2ac-139">For example, if you selected Germany, we'll enrich profiles located in the United States if we have data available for the selected brands and interests in the US.</span></span>

## <a name="configure-enrichment"></a><span data-ttu-id="7a2ac-140">Толықтыруды теңшеу</span><span class="sxs-lookup"><span data-stu-id="7a2ac-140">Configure Enrichment</span></span>

<span data-ttu-id="7a2ac-141">Қадамдық тәжірибе сізге жақсартуды конфигурациялауға көмектеседі.</span><span class="sxs-lookup"><span data-stu-id="7a2ac-141">A guided experience helps you through the configuration of the enrichments.</span></span> 

### <a name="define-your-brands-or-interests"></a><span data-ttu-id="7a2ac-142">Брендтерді немесе қызығушылықтарды анықтау</span><span class="sxs-lookup"><span data-stu-id="7a2ac-142">Define your brands or interests</span></span>

<span data-ttu-id="7a2ac-143">Келесі параметрлердің бірін таңдаңыз:</span><span class="sxs-lookup"><span data-stu-id="7a2ac-143">Select one of the following options:</span></span>

- <span data-ttu-id="7a2ac-144">**Сала** : жүйе сіздің салаңызға қатысты ең жақсы брендтерді немесе қызығушылықтарды анықтайды және олармен тұтынушы деректерін толықтырады.</span><span class="sxs-lookup"><span data-stu-id="7a2ac-144">**Industry**: The system identifies the top brands or interests relevant to your industry and enriches your customer data with them.</span></span>
- <span data-ttu-id="7a2ac-145">**Өзіңіздікін таңдаңыз** : сіздің ұйымыңызға қатысты брендтер немесе қызығушылықтар тізімінен бес элементке дейін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="7a2ac-145">**Choose your own**: Select up to five items from the list of brands or interests that are most relevant to your organization.</span></span>

<span data-ttu-id="7a2ac-146">Брендті немесе қызығушылықты қосу үшін сәйкес шарттар бойынша ұсыныстар алу үшін оны кіріс аймағына енгізіңіз.</span><span class="sxs-lookup"><span data-stu-id="7a2ac-146">To add a brand or interest, enter it in the input area to get suggestions based on matching terms.</span></span> <span data-ttu-id="7a2ac-147">Егер іздеген бренд немесе қызығушылық көрсетілмесе, **Ұсыну** сілтемесі арқылы бізге кері байланыс жіберіңіз.</span><span class="sxs-lookup"><span data-stu-id="7a2ac-147">If we don't list a brand or interest you're looking for, send us feedback using the **Suggest** link.</span></span>

### <a name="review-enrichment-preferences"></a><span data-ttu-id="7a2ac-148">Арттыру параметрлерін қарап шығу</span><span class="sxs-lookup"><span data-stu-id="7a2ac-148">Review enrichment preferences</span></span>

<span data-ttu-id="7a2ac-149">Әдепкі арттыру параметрлерін қарап шығыңыз және қажет болған жағдайда оларды жаңартыңыз.</span><span class="sxs-lookup"><span data-stu-id="7a2ac-149">Review your default enrichment preferences and update them as needed.</span></span>

:::image type="content" source="media/affinity-enrichment-preferences.png" alt-text="Арттыру параметрлері терезесінің скриншоты.":::

### <a name="select-entity-to-enrich"></a><span data-ttu-id="7a2ac-151">Арттыру үшін нысанды таңдау</span><span class="sxs-lookup"><span data-stu-id="7a2ac-151">Select entity to enrich</span></span>

<span data-ttu-id="7a2ac-152">**Жақсартылған нысан** түймешігін таңдаңыз және Microsoft компания деректерімен жақсарту керек деректер жиынтығын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="7a2ac-152">Select **Enriched entity** and choose the data set you want to enrich with company data from the Microsoft.</span></span> <span data-ttu-id="7a2ac-153">Барлық тұтынушы профильдерін арттыру үшін Тұтынушы нысанын таңдауға болады немесе сол сегменттегі тек тұтынушы профильдерін арттыру үшін сегмент нысанын таңдауға болады.</span><span class="sxs-lookup"><span data-stu-id="7a2ac-153">You can select the Customer entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

### <a name="map-your-fields"></a><span data-ttu-id="7a2ac-154">Өрістерді салыстыру</span><span class="sxs-lookup"><span data-stu-id="7a2ac-154">Map your fields</span></span>

<span data-ttu-id="7a2ac-155">Тұтынушы деректерін арттыру үшін жүйені пайдаланғыңыз келетін демографиялық сегментті анықтау үшін бірыңғай тұтынушы нысан өрістерін салыстырыңыз.</span><span class="sxs-lookup"><span data-stu-id="7a2ac-155">Map fields from your unified customer entity to define the demographic segment you want the system to use for enriching your customer data.</span></span> <span data-ttu-id="7a2ac-156">Ел/аймақ және кем дегенде туған күні немесе жынысы төлсипаттарын салыстырыңыз.</span><span class="sxs-lookup"><span data-stu-id="7a2ac-156">Map Country/Region and at least Date of Birth or Gender attributes.</span></span> <span data-ttu-id="7a2ac-157">Сонымен қатар сіз қаланың (және облыстың/ауданның) немесе пошталық индекстің кем дегенде біреуін салыстыру қажет.</span><span class="sxs-lookup"><span data-stu-id="7a2ac-157">Additionally, you must map at least one of City (and State/Province) or Postal code.</span></span> <span data-ttu-id="7a2ac-158">Өрістердің салыстыруын анықтау үшін **Өңдеу** параметрін таңдап, орындалған кезде **Қолдану** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="7a2ac-158">Select **Edit** to define the mapping of the fields and select **Apply** when you're done.</span></span> <span data-ttu-id="7a2ac-159">Өрісті салыстыруды аяқтау үшін **Сақтау** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="7a2ac-159">Select **Save** to complete the field mapping.</span></span>

<span data-ttu-id="7a2ac-160">Келесі пішімдер мен мәндерге қолдау көрсетіледі, мәндер регистрді ескермейді:</span><span class="sxs-lookup"><span data-stu-id="7a2ac-160">The following formats and values are supported, values are not case-sensitive:</span></span>

- <span data-ttu-id="7a2ac-161">**Туған күні**: біз деректерді қабылдау кезінде туған күнді DateTime түріне түрлендіруді ұсынамыз.</span><span class="sxs-lookup"><span data-stu-id="7a2ac-161">**Date of Birth**: We recommend that date of birth is converted to DateTime type during data ingestion.</span></span> <span data-ttu-id="7a2ac-162">Я болмаса, бұл [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) «yyyy-MM-dd» немесе «yyyy-MM-ddTHH: mm: ssZ» пішіміндегі жол болуы мүмкін.</span><span class="sxs-lookup"><span data-stu-id="7a2ac-162">Alternatively, it can be a string in [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) format "yyyy-MM-dd" or "yyyy-MM-ddTHH:mm:ssZ".</span></span>
- <span data-ttu-id="7a2ac-163">**Жынысы**: ер, әйел, белгісіз</span><span class="sxs-lookup"><span data-stu-id="7a2ac-163">**Gender**: Male, Female, Unknown</span></span>
- <span data-ttu-id="7a2ac-164">**Пошта индексі**: АҚШ үшін бес цифрлық пошталық индекстер, барлық басқа жерде стандартты пошталық индекс</span><span class="sxs-lookup"><span data-stu-id="7a2ac-164">**Postal code**: Five-digit ZIP Codes for US, standard postal code everywhere else</span></span>
- <span data-ttu-id="7a2ac-165">**Қала**: ағылшын тіліндегі қала атауы</span><span class="sxs-lookup"><span data-stu-id="7a2ac-165">**City**: City name in English</span></span>
- <span data-ttu-id="7a2ac-166">**Штат/провинция**: АҚШ пен Канадаға арналған екі әріптік қысқарту.</span><span class="sxs-lookup"><span data-stu-id="7a2ac-166">**State/Province**: Two-letter abbreviation for the US and Canada.</span></span> <span data-ttu-id="7a2ac-167">Австралияға арналған екі немесе үш әріптік қысқарту.</span><span class="sxs-lookup"><span data-stu-id="7a2ac-167">Two or three letter abbreviation for Australia.</span></span> <span data-ttu-id="7a2ac-168">Франция, Германия немесе Біріккен Корольдік елдеріне қатысты емес.</span><span class="sxs-lookup"><span data-stu-id="7a2ac-168">Not applicable for France, Germany, or the UK.</span></span>
- <span data-ttu-id="7a2ac-169">**Ел/аймақ**:</span><span class="sxs-lookup"><span data-stu-id="7a2ac-169">**Country/Region**:</span></span>

  - <span data-ttu-id="7a2ac-170">АҚШ: Америка Құрама Штаттары, Құрама Штаттар, АҚШ, Америка</span><span class="sxs-lookup"><span data-stu-id="7a2ac-170">US: United States of America, United States, USA, US, America</span></span>
  - <span data-ttu-id="7a2ac-171">CA: Канада, CA</span><span class="sxs-lookup"><span data-stu-id="7a2ac-171">CA: Canada, CA</span></span>
  - <span data-ttu-id="7a2ac-172">GB: Біріккен Корольдік, UK, Ұлыбритания, Ұлыбритания, GB, Ұлыбритания және Солтүстік Ирландия Біріккен Корольдігі, Ұлыбритания Біріккен Корольдігі</span><span class="sxs-lookup"><span data-stu-id="7a2ac-172">GB: United Kingdom, UK, Great Britain, GB, United Kingdom of Great Britain and Northern Ireland, United Kingdom of Great Britain</span></span>
  - <span data-ttu-id="7a2ac-173">AU: Австралия, AU, Австралиялық одақ</span><span class="sxs-lookup"><span data-stu-id="7a2ac-173">AU: Australia, AU, Common Wealth of Australia</span></span>
  - <span data-ttu-id="7a2ac-174">FR: Франция, FR, Франция Республикасы</span><span class="sxs-lookup"><span data-stu-id="7a2ac-174">FR: France, FR, French Republic</span></span>
  - <span data-ttu-id="7a2ac-175">DE: Германия, германиялық, Deutschland, Allemagne, DE, Германия Федеративтік Республикасы, Германия Республикасы</span><span class="sxs-lookup"><span data-stu-id="7a2ac-175">DE: Germany, German, Deutschland, Allemagne, DE, Federal Republic of Germany, Republic of Germany</span></span>

## <a name="review-and-name-the-enrichment"></a><span data-ttu-id="7a2ac-176">Жақсартуды қарап шығу және ат беру</span><span class="sxs-lookup"><span data-stu-id="7a2ac-176">Review and name the enrichment</span></span>

<span data-ttu-id="7a2ac-177">Соңында сіз ақпаратты қарап шығып, жақсарту атын бересіз.</span><span class="sxs-lookup"><span data-stu-id="7a2ac-177">Finally, you get to review the information and provide a name for the enrichment.</span></span>

:::image type="content" source="media/enrichment-interests-summary.png" alt-text="Қызығушылықтарды қарап шығу және атау беру беті.":::

## <a name="refresh-enrichment"></a><span data-ttu-id="7a2ac-179">Арттыруды жаңарту</span><span class="sxs-lookup"><span data-stu-id="7a2ac-179">Refresh enrichment</span></span>

<span data-ttu-id="7a2ac-180">Демографиялық көрсеткіштерге арналған брендтерді, қызығушылықтарды және өрістерді салыстыруды конфигурациялағаннан кейін толықтыруды бастаңыз.</span><span class="sxs-lookup"><span data-stu-id="7a2ac-180">Run the enrichment after configuring brands, interests, and the field mapping for demographics.</span></span> <span data-ttu-id="7a2ac-181">Процесті бастау үшін бренд немесе қызығушылық конфигурациясы тақтасынан **Іске қосу** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="7a2ac-181">To start the process, select **Run** on the brand or interest configuration page.</span></span> <span data-ttu-id="7a2ac-182">Оған қоса жүйеде толықтыру процесін жоспарланған жаңарту бөлігі ретінде автоматты іске қосуға мүмкіндік бере аласыз.</span><span class="sxs-lookup"><span data-stu-id="7a2ac-182">Additionally, you can let the system run the enrichment automatically as part of a scheduled refresh.</span></span>
<span data-ttu-id="7a2ac-183">Тұтынушы деректерінің көлеміне байланысты, толықтыруды аяқтауға бірнеше минут кетуі мүмкін.</span><span class="sxs-lookup"><span data-stu-id="7a2ac-183">Depending on the size of your customer data, it may take several minutes for an enrichment run to complete.</span></span>

> [!TIP]
> <span data-ttu-id="7a2ac-184">Тапсырмалар/процестерге арналған [күйдің алты түрі](system.md#status-types) бар.</span><span class="sxs-lookup"><span data-stu-id="7a2ac-184">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="7a2ac-185">Сонымен қатар көптеген процестер [басқа кезектегі процестерге тәуелді](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="7a2ac-185">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="7a2ac-186">Бүкіл тапсырманың барысы туралы мәліметтерді көру үшін процестің күйін таңдай аласыз.</span><span class="sxs-lookup"><span data-stu-id="7a2ac-186">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="7a2ac-187">Бір жұмыс тапсырмаларының бірі үшін **Мәліметтерді көру** параметрін таңдағаннан кейін, қосымша ақпаратты көруге болады: өңдеу уақыты, соңғы өңделген күні және тапсырмаға қатысты барлық қателер мен ескертулер.</span><span class="sxs-lookup"><span data-stu-id="7a2ac-187">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="7a2ac-188">Толықтыру нәтижелері</span><span class="sxs-lookup"><span data-stu-id="7a2ac-188">Enrichment results</span></span>

<span data-ttu-id="7a2ac-189">Толықтыру процесін бастағаннан кейін толықтырылған тұтынушылардың жалпы санын және тұтынушылардың толықтырылған профильдеріндегі брендтердің немесе қызығушылықтардың өзгеруін қарастыру үшін **Менің толықтыруларым** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="7a2ac-189">After running the enrichment process, go to **My enrichments** to review the total number of enriched customers and a breakdown of brands or interests in the enriched customer profiles.</span></span>

:::image type="content" source="media/my-enrichments.png" alt-text="Толықтыру процесін іске қосқаннан кейінгі нәтижелерді алдын ала қарау":::

<span data-ttu-id="7a2ac-191">Диаграммадан **Толықтырылған деректерді қарау** опциясын таңдау арқылы толықтырылған деректерді қараңыз.</span><span class="sxs-lookup"><span data-stu-id="7a2ac-191">Review the enriched data by selecting **View enriched data** in the chart.</span></span> <span data-ttu-id="7a2ac-192">Брендтер үшін толықтырылған деректер **BrandAffinityFromMicrosoft** нысанына өтеді.</span><span class="sxs-lookup"><span data-stu-id="7a2ac-192">Enriched data for brands goes to the **BrandAffinityFromMicrosoft** entity.</span></span> <span data-ttu-id="7a2ac-193">**InterestAffinityFromMicrosoft** нысанындағы қызығушылықтарға арналған деректер.</span><span class="sxs-lookup"><span data-stu-id="7a2ac-193">Data for interests is in the **InterestAffinityFromMicrosoft** entity.</span></span> <span data-ttu-id="7a2ac-194">**Деректер** > **Нысандар** тармағындағы **Толықтыру** тобында тізімделген осы нысандарды да таба аласыз.</span><span class="sxs-lookup"><span data-stu-id="7a2ac-194">You'll also find these entities listed in the **Enrichment** group in **Data** > **Entities**.</span></span>

## <a name="see-enrichment-data-on-the-customer-card"></a><span data-ttu-id="7a2ac-195">Тұтынушы картасынан толықтыру деректерін көру</span><span class="sxs-lookup"><span data-stu-id="7a2ac-195">See enrichment data on the customer card</span></span>

<span data-ttu-id="7a2ac-196">Сонымен қатар жеке тұтынушы карталарынан бренд пен қызығушылық ұқсастықтарын көре аласыз.</span><span class="sxs-lookup"><span data-stu-id="7a2ac-196">Brand and interest affinities can also be viewed on individual customer cards.</span></span> <span data-ttu-id="7a2ac-197">**Тұтынушылар** тармағына өтіп, тұтынушы профилін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="7a2ac-197">Go to **Customers** and select a customer profile.</span></span> <span data-ttu-id="7a2ac-198">Тұтынушы картасында тұтынушының демографиялық профилінде қамтылған адамдар брендтері немесе қызығушылықтары сызбаларын табасыз.</span><span class="sxs-lookup"><span data-stu-id="7a2ac-198">In the customer card, you'll find charts for the brands or interests that people in that customer's demographic profile have affinity for.</span></span>

:::image type="content" source="media/enrichment-customer-card.png" alt-text="Толықтырылған деректері бар тұтынушы картасы":::

## <a name="next-steps"></a><span data-ttu-id="7a2ac-200">Келесі қадамдар</span><span class="sxs-lookup"><span data-stu-id="7a2ac-200">Next steps</span></span>

<span data-ttu-id="7a2ac-201">Толықтырылған тұтынушы деректерінің негізінде жасаңыз.</span><span class="sxs-lookup"><span data-stu-id="7a2ac-201">Build on top of your enriched customer data.</span></span> <span data-ttu-id="7a2ac-202">Тұтынушыларға жекелендірілген тәжірибелерді жеткізу үшін [Сегменттер](segments.md), [Шаралар](measures.md) жасаңыз және [деректерді экспорттаңыз](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="7a2ac-202">Create [Segments](segments.md), [Measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
