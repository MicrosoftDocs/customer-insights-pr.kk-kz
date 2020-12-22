---
title: Деректерді біріктіруге арналған нысандарды картаға түсіріңіз
description: Тұтынушылардың бірыңғай профильдерін жасау үшін деректерді картаға түсіріңіз.
ms.date: 09/25/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: e98c7717f7707d43a9fd1fc6f6b0e9c49e4e7ee0
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406243"
---
# <a name="map-entities-and-attributes"></a><span data-ttu-id="e1cda-103">Нысандар мен атрибуттарды салыстыру</span><span class="sxs-lookup"><span data-stu-id="e1cda-103">Map entities and attributes</span></span>

<span data-ttu-id="e1cda-104">**Картаға түсіру** — аудитория мәліметтеріндегі деректерді біріктіру процесінің бірінші кезеңі.</span><span class="sxs-lookup"><span data-stu-id="e1cda-104">**Map** is the first stage in the data unification process of audience insights.</span></span> <span data-ttu-id="e1cda-105">Салыстыру түсіру үш кезеңнен тұрады:</span><span class="sxs-lookup"><span data-stu-id="e1cda-105">Mapping consists of three phases:</span></span>

- <span data-ttu-id="e1cda-106">*Нысан таңдауы*: тұтынушылар туралы толығырақ ақпараты бар деректер жиынына әкелетін біріккен нысандарды анықтаңыз.</span><span class="sxs-lookup"><span data-stu-id="e1cda-106">*Entity selection*: Identify the combinable entities that lead to a dataset with more complete information about your customers.</span></span>
- <span data-ttu-id="e1cda-107">*Төлсипат таңдауы*: әрбір нысан үшін *салыстыру* және *біріктіру* кезеңдерінде біріктіру және қайта салыстыру қажет бағандарды анықтаңыз.</span><span class="sxs-lookup"><span data-stu-id="e1cda-107">*Attribute selection*: For each entity, identify the columns you want to combine and reconcile in the *match* and *merge* phases.</span></span> <span data-ttu-id="e1cda-108">Бұл бағандар *Төлсипаттар* деп аталады.</span><span class="sxs-lookup"><span data-stu-id="e1cda-108">These columns are called *Attributes*.</span></span>
- <span data-ttu-id="e1cda-109">*Негізгі кілтті және семантикалық түрді таңдау*: әрбір нысан үшін сол нысан үшін негізгі кілт ретінде анықтағыңыз келетін төлсипатты анықтаңыз және әрбір төлсипат үшін сол төлсипатты ең жақсы сипаттайтын семантикалық түрді анықтаңыз.</span><span class="sxs-lookup"><span data-stu-id="e1cda-109">*Primary key and semantic type selection*: For each entity, identify an attribute you want to define as the primary key for that entity, and for each attribute, identify a semantic type that best describes that attribute.</span></span>

<span data-ttu-id="e1cda-110">Деректерді біріктірудің жалпы ағыны туралы қосымша ақпаратты [Біріктіру](data-unification.md) бөлімінен қараңыз.</span><span class="sxs-lookup"><span data-stu-id="e1cda-110">For more information about the general flow of data unification, see [Unify](data-unification.md).</span></span>

## <a name="select-the-first-entities"></a><span data-ttu-id="e1cda-111">Бірінші нысандарды таңдау</span><span class="sxs-lookup"><span data-stu-id="e1cda-111">Select the first entities</span></span>

1. <span data-ttu-id="e1cda-112">Аудитория мәліметтерінде **Деректер** > **Біріктіру** > **Картаға түсіру** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="e1cda-112">In audience insights, go to **Data** > **Unify** > **Map**.</span></span>

2. <span data-ttu-id="e1cda-113">**Нысандар таңдау** пәрменін таңдау арқылы салыстыру кезеңін бастаңыз.</span><span class="sxs-lookup"><span data-stu-id="e1cda-113">Start the map phase by selecting **Select entities**.</span></span>

3. <span data-ttu-id="e1cda-114">*Сәйкестендіру* және *біріктіру* кезеңдері ішінде пайдаланғыңыз келетін нысандар мен төлсипаттарды таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="e1cda-114">Select the entities and attributes you want to use in the *match* and *merge* phases.</span></span> <span data-ttu-id="e1cda-115">Сіз қажетті төлсипаттарды нысаннан жеке-жеке таңдай аласыз немесе нысан деңгейінде **Барлық өрістерді қосу** нысан деңгейіндегі құсбелгісін қою арқылы нысаннан барлық төлсипаттарды қоса аласыз.</span><span class="sxs-lookup"><span data-stu-id="e1cda-115">You can select the required attributes individually from an entity or include all attributes from an entity by selecting the **Include all fields** checkbox on the entity level.</span></span> <span data-ttu-id="e1cda-116">Деректерді біріктіру процесінің артықшылығын алу үшін кемінде екі нысанды таңдау ұсынылады.</span><span class="sxs-lookup"><span data-stu-id="e1cda-116">We recommend selecting at least two entities to benefit from the data unification process.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e1cda-117">![Нысандар мысалын қосу](media/data-manager-configure-map-add-entities-example.png "Нысандар мысалын қосу")</span><span class="sxs-lookup"><span data-stu-id="e1cda-117">![Add entities example](media/data-manager-configure-map-add-entities-example.png "Add entities example")</span></span>

   <span data-ttu-id="e1cda-118">Бұл мысалда біз **eCommerceContacts** және **loyCustomers** нысандарын қосамыз.</span><span class="sxs-lookup"><span data-stu-id="e1cda-118">In this example, we're adding the **eCommerceContacts** and **loyCustomers** entities.</span></span> <span data-ttu-id="e1cda-119">Осы нысандарды таңдау арқылы сіз онлайн бизнес тұтынушылардың қайсылары адалдық бағдарламасының мүшелері екендігі туралы түсінік ала аласыз.</span><span class="sxs-lookup"><span data-stu-id="e1cda-119">By choosing these entities, you can derive insights on which of the online business customers are loyalty program members.</span></span>
   
   <span data-ttu-id="e1cda-120">Сіз салыстыру қажет төлсипаттарды таңдау үшін барлық төлсипаттарда және нысандарда кілтсөздер бойынша іздей аласыз.</span><span class="sxs-lookup"><span data-stu-id="e1cda-120">You can search on keywords across all attributes and entities to select the required attributes you want to map.</span></span>
   
     > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e1cda-121">![Іздеу өрістерінің мысалы](media/data-manager-configure-map-search-fields-example.png "Іздеу өрістерінің мысалы")</span><span class="sxs-lookup"><span data-stu-id="e1cda-121">![Search fields example](media/data-manager-configure-map-search-fields-example.png "Search fields example")</span></span>

4. <span data-ttu-id="e1cda-122">Таңдауларыңызды растау үшін **Қолдану** пәрменін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="e1cda-122">Select **Apply** to confirm your selections.</span></span>

## <a name="select-primary-key-and-semantic-type-for-attributes"></a><span data-ttu-id="e1cda-123">Төлсипаттар үшін негізгі кілт пен семантикалық түрді таңдау</span><span class="sxs-lookup"><span data-stu-id="e1cda-123">Select primary key and semantic type for attributes</span></span>

<span data-ttu-id="e1cda-124">Нысандарды таңдағаннан кейін **Салыстыру** бетінде қарап шығуыңыз үшін таңдалған нысандар тізіледі.</span><span class="sxs-lookup"><span data-stu-id="e1cda-124">After selecting your entities, the **Map** page lists the selected entities for your review.</span></span> <span data-ttu-id="e1cda-125">Нысан үшін негізгі кілтті анықтаңыз және нысандағы төлсипаттың семантикалық түрін анықтаңыз.</span><span class="sxs-lookup"><span data-stu-id="e1cda-125">Define the primary key for an entity and identify the semantic type for an attribute in the entity.</span></span>

- <span data-ttu-id="e1cda-126">**Негізгі кілт**: әрбір нысанның негізгі кілті ретінде бір төлсипатты таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="e1cda-126">**Primary key**: Select one attribute as a primary key for each of your entities.</span></span> <span data-ttu-id="e1cda-127">Жарамды негізгі кілт болуы үшін төлсипат қайталанатын мәндерді, жетіспейтін мәндерді немесе бос мәндерді қамтымауы керек.</span><span class="sxs-lookup"><span data-stu-id="e1cda-127">For an attribute to be a valid primary key, it shouldn't include duplicate values, missing values, or null values.</span></span> <span data-ttu-id="e1cda-128">Жол, бүтін сан және GUID деректер түрі төлсипаттарына негізгі кілттер ретінде қолдау көрсетіледі және сіз ішінен таңдайтын өрісте көрсетіледі.</span><span class="sxs-lookup"><span data-stu-id="e1cda-128">String, integer, and GUID data type attributes are supported as primary keys and will be displayed in a field for you to select from.</span></span>

- <span data-ttu-id="e1cda-129">**Төлсипаттың семантикалық түрі**: электрондық пошта мекенжайы немесе аты сияқты төлсипаттардың санаттары.</span><span class="sxs-lookup"><span data-stu-id="e1cda-129">**Attribute semantic type**: Categories of your attributes, such as email address or name.</span></span> <span data-ttu-id="e1cda-130">Семантикаларды смарт болжауға арналған жасанды интеллект моделін пайдалану, уақытты үнемдеу және дәлдікті жақсарту үшін **Интеллектуалды салыстыру** параметрін **ҚОСУЛЫ** күйіне орнатыңыз.</span><span class="sxs-lookup"><span data-stu-id="e1cda-130">To use AI models for smart prediction of semantics, save time and improve accuracy, set **Intelligent mapping** to **ON**.</span></span> <span data-ttu-id="e1cda-131">Интеллектуалды салыстыру **Түр** өрісіндегі жасанды интеллектіге негізделген семантикалық ұсыныстарын бөліп көрсетеді.</span><span class="sxs-lookup"><span data-stu-id="e1cda-131">Intelligent mapping highlights AI-based semantics recommendation in the **Type** field.</span></span> <span data-ttu-id="e1cda-132">Егер **ӨШІРУЛІ** күйіне орнатылса, біздің тұрақты салыстыру бойынша ұсыныстарымыз көрсетіледі.</span><span class="sxs-lookup"><span data-stu-id="e1cda-132">If you set it to **OFF**, you will see our regular mapping recommendations.</span></span> <span data-ttu-id="e1cda-133">Қолжетімді опциялар тізімінен кез келген семантикалық түрді таңдауға және ұсынылған таңдаудан бас тартуға болады.</span><span class="sxs-lookup"><span data-stu-id="e1cda-133">You can select any semantic type from the available list of options and override the suggested selection.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="e1cda-134">![Атрибут түрі және семантикалық болжам](media/data-manager-configure-map-add-attributes-semantic-prediction.png "Атрибут түрі және семантикалық болжам")</span><span class="sxs-lookup"><span data-stu-id="e1cda-134">![Attribute type and semantic prediction](media/data-manager-configure-map-add-attributes-semantic-prediction.png "Attribute type and semantic prediction")</span></span>

<span data-ttu-id="e1cda-135">Сондай-ақ теңшелетін семантикалық түрді қосуға болады.</span><span class="sxs-lookup"><span data-stu-id="e1cda-135">Adding a custom semantic type is also possible.</span></span> <span data-ttu-id="e1cda-136">Төлсипат үшін түр өрісін таңдап, теңшелетін семантикалық төлсипат түрінің атын теріңіз.</span><span class="sxs-lookup"><span data-stu-id="e1cda-136">Select the type field for an attribute, and type your custom semantic type name.</span></span> <span data-ttu-id="e1cda-137">Осылайша жүйе анықтаған төлсипат түрлерін де өзгертуге болады.</span><span class="sxs-lookup"><span data-stu-id="e1cda-137">This way, you can also change the attribute types that were identified by the system.</span></span>

<span data-ttu-id="e1cda-138">Семантикалық түр автоматты түрде анықталатын барлық төлсипаттар **Салыстырылған өрістерді қарап шығу** бөлімінде топталады.</span><span class="sxs-lookup"><span data-stu-id="e1cda-138">All attributes for which a semantic type is automatically identified are grouped in the **Review mapped fields** section.</span></span> <span data-ttu-id="e1cda-139">Бұл төлсипаттарды және олардың семантикалық түрлерін қарап шығыңыз, өйткені олар деректерді бірыңғайландырудың біріктіру қадамында нысандарды біріктіру үшін пайдаланылады.</span><span class="sxs-lookup"><span data-stu-id="e1cda-139">Review these attributes and their semantic types because they'll be used to combine your entities in the merge step of data unification.</span></span>

<span data-ttu-id="e1cda-140">Семантикалық түрмен автоматты түрде салыстырылмаған төлсипаттар **Салыстырылмаған өрістерде деректерді анықтау** бөлімінде топталады.</span><span class="sxs-lookup"><span data-stu-id="e1cda-140">Attributes that aren't automatically mapped to a semantic type are grouped in the **Define the data in the unmapped fields** section.</span></span> <span data-ttu-id="e1cda-141">Салыстырылмаған төлсипаттар үшін үшін семантикалық түр өрісін таңдаңыз немесе теңшелетін төлсипат-түр атауын енгізіңіз.</span><span class="sxs-lookup"><span data-stu-id="e1cda-141">Select the semantic type field for the unmapped attributes, or enter your custom attribute-type name.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="e1cda-142">![Негізгі кілт және төлсипат түрі](media/data-manager-configure-map-add-attributes.png "Негізгі кілт және төлсипат түрі")</span><span class="sxs-lookup"><span data-stu-id="e1cda-142">![Primary key and attribute type](media/data-manager-configure-map-add-attributes.png "Primary key and attribute type")</span></span>

> [!NOTE]
> <span data-ttu-id="e1cda-143">Тұтынушы картасына тұтынушы атын толтыру үшін бір өріс Person.FullName семантикалық түрімен салыстырылуы керек.</span><span class="sxs-lookup"><span data-stu-id="e1cda-143">One field should map to the semantic type Person.FullName to populate the customer name in customer card.</span></span> <span data-ttu-id="e1cda-144">Әйтпесе, тұтынушы карталары атсыз болып шығады.</span><span class="sxs-lookup"><span data-stu-id="e1cda-144">Otherwise, the customer cards will appear nameless.</span></span> 

## <a name="add-and-remove-attributes-and-entities"></a><span data-ttu-id="e1cda-145">Төлсипаттар мен нысандарды қосу және жою</span><span class="sxs-lookup"><span data-stu-id="e1cda-145">Add and remove attributes and entities</span></span>

1. <span data-ttu-id="e1cda-146">**Бірыңғайландыру** > **Салыстыру** тармағында **Өрістерді өңдеу** пәрменін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="e1cda-146">On **Unify** > **Map**, select **Edit fields**.</span></span>

2. <span data-ttu-id="e1cda-147">**Өрістерді өңдеу** бөлігінде төлсипаттар мен нысандарды қосу немесе жою.</span><span class="sxs-lookup"><span data-stu-id="e1cda-147">In the **Edit fields** pane, add or remove attributes and entities.</span></span> <span data-ttu-id="e1cda-148">Қызықтыратын төлсипаттар мен нысандарды табу және таңдау үшін іздеуді немесе айналдыруды пайдаланыңыз.</span><span class="sxs-lookup"><span data-stu-id="e1cda-148">Use the search or scroll to find and select your attributes and entities of interest.</span></span> <span data-ttu-id="e1cda-149">Сәйкестендіріліп қойылған болса, төлсипатты немесе нысанды жоя алмайсыз.</span><span class="sxs-lookup"><span data-stu-id="e1cda-149">You can't remove an attribute or an entity if they've already been matched.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e1cda-150">![Төлсипаттарды қосу немесе жою](media/configure-data-map-edit.png "Төлсипаттарды қосу немесе жою")</span><span class="sxs-lookup"><span data-stu-id="e1cda-150">![Add or remove attributes](media/configure-data-map-edit.png "Add or remove attributes")</span></span>

3. <span data-ttu-id="e1cda-151">**Қолдану** түймесін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="e1cda-151">Select **Apply**.</span></span>

## <a name="add-images-to-profiles"></a><span data-ttu-id="e1cda-152">Профильдерге суреттер қосу</span><span class="sxs-lookup"><span data-stu-id="e1cda-152">Add images to profiles</span></span>

<span data-ttu-id="e1cda-153">Егер нысанда жалпыға қолжетімді профиль суреттері немесе логотиптерінің URL мекенжайлары болса, оларды бірыңғай тұтынушы профиліне қосуға болады.</span><span class="sxs-lookup"><span data-stu-id="e1cda-153">If an entity contains URLs to publicly available profile images or logos, you can add them to the unified customer profile.</span></span>

<span data-ttu-id="e1cda-154">Нысанды таңдап, профиль суретіне URL мекенжайы бар өрісті табыңыз.</span><span class="sxs-lookup"><span data-stu-id="e1cda-154">Select the entity and find the field that contains the URL to the profile image.</span></span> <span data-ttu-id="e1cda-155">**Түрі** кіріс өрісіне келесі мәнді қолмен енгізіңіз:</span><span class="sxs-lookup"><span data-stu-id="e1cda-155">In the **Type** input field, manually enter the following value:</span></span> 
- <span data-ttu-id="e1cda-156">Адам: Person.ProfileImagе</span><span class="sxs-lookup"><span data-stu-id="e1cda-156">For a person: Person.ProfileImage</span></span>
- <span data-ttu-id="e1cda-157">Ұйым: Organization.LogoImage</span><span class="sxs-lookup"><span data-stu-id="e1cda-157">For an organization: Organization.LogoImage</span></span>

<span data-ttu-id="e1cda-158">Бірыңғайландыру қадамдарын жалғастырыңыз және [Біріктіру](merge-entities.md) қадамында кескін URL мекенжайы бар төлсипаттың да қосылуын қамтамасыз етіңіз.</span><span class="sxs-lookup"><span data-stu-id="e1cda-158">Continue with the unification steps and ensure the attribute that contains the image URL is also added in the [Merge](merge-entities.md) step.</span></span>

## <a name="set-attributes-for-organizations"></a><span data-ttu-id="e1cda-159">Ұйымдардың төлсипаттарын орнату</span><span class="sxs-lookup"><span data-stu-id="e1cda-159">Set attributes for organizations</span></span>

<span data-ttu-id="e1cda-160">Ұйымдар (алдын ала қарау) үшін төлсипат түрі «Organization.Name» нысанымен салыстырылуы керек</span><span class="sxs-lookup"><span data-stu-id="e1cda-160">For organizations (Preview), the attribute type should be mapped to "Organization.Name"</span></span>
> [!div class="mx-imgBorder"]
> <span data-ttu-id="e1cda-161">![Негізгі кілт және төлсипат түрі: бизнес - бизнес](media/configure-data-map-edit-b2b.png "Негізгі кілт және төлсипат түрі: бизнес - бизнес")</span><span class="sxs-lookup"><span data-stu-id="e1cda-161">![Primary key and attribute type B2B](media/configure-data-map-edit-b2b.png "Primary key and attribute type B2B")</span></span>

## <a name="next-step"></a><span data-ttu-id="e1cda-162">Келесі қадам</span><span class="sxs-lookup"><span data-stu-id="e1cda-162">Next step</span></span>

<span data-ttu-id="e1cda-163">Деректерді біріктіру процесінің бөлігі ретінде **Сәйкестендіру** бетіне өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="e1cda-163">As part of the data unification process, go to the **Match** page.</span></span> <span data-ttu-id="e1cda-164">Осы кезең туралы ақпарат алу үшін [**Сәйкестендіру**](match-entities.md) бетіне кіріңіз.</span><span class="sxs-lookup"><span data-stu-id="e1cda-164">Visit [**Match**](match-entities.md) to learn about this phase.</span></span>

> [!TIP]
> <span data-ttu-id="e1cda-165">Мынаны бейнені қараңыз: [Жұмысты бастау: бірыңғай тұтынушы профилін жасау](https://youtu.be/oBfGEhucAxs).</span><span class="sxs-lookup"><span data-stu-id="e1cda-165">Check out the following video: [Getting Started: Creating a Unified Customer Profile](https://youtu.be/oBfGEhucAxs).</span></span>
