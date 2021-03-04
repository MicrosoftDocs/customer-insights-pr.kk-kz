---
title: Тұтынушы әрекеттері
description: Тұтынушылар әрекеттерін анықтап, оларды тұтынушылардың уақыт кестесінде қарап шығыңыз.
ms.date: 10/13/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: adkuppa
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: dcef8f0547009e1488f1abe91423fa0bf5b061de
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267439"
---
# <a name="customer-activities"></a><span data-ttu-id="1e36f-103">Тұтынушы әрекеттері</span><span class="sxs-lookup"><span data-stu-id="1e36f-103">Customer activities</span></span>

<span data-ttu-id="1e36f-104">Әрекеттерді хронологиялық ретпен көрсететін тұтынушының уақыт кестесін жасау үшін Dynamics 365 Customer Insights жүйесіндегі [түрлі деректер көзінен](data-sources.md) тұтынушы әрекеттерін біріктіріңіз.</span><span class="sxs-lookup"><span data-stu-id="1e36f-104">Combine customer activities from [various data sources](data-sources.md) in Dynamics 365 Customer Insights to create a customer timeline that lists the activities in chronological order.</span></span> <span data-ttu-id="1e36f-105">[Тұтынушы картасының қондырмасы](customer-card-add-in.md) арқылы Dynamics 365 жүйесіндегі тұтынушылармен әрекеттесу бағдарламаларына немесе Power BI бақылау тақтасына уақыт шкаласын қосуға болады.</span><span class="sxs-lookup"><span data-stu-id="1e36f-105">You can include the timeline in customer engagement apps in Dynamics 365 via the [Customer Card add-in](customer-card-add-in.md), or in a Power BI dashboard.</span></span>

## <a name="define-an-activity"></a><span data-ttu-id="1e36f-106">Әрекетті анықтау</span><span class="sxs-lookup"><span data-stu-id="1e36f-106">Define an activity</span></span>

<span data-ttu-id="1e36f-107">Деректер көздерінде бірнеше деректер көздерінен алынған транзакциялық және әрекет деректері бар нысандар бар.</span><span class="sxs-lookup"><span data-stu-id="1e36f-107">Your data sources include entities with transactional and activity data from multiple data sources.</span></span> <span data-ttu-id="1e36f-108">Осы нысандарды анықтап, тұтынушының уақыт шкаласында көргіңіз келетін әрекеттерді таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="1e36f-108">Identify these entities and select the activities you want to view on the customer's timeline.</span></span> <span data-ttu-id="1e36f-109">Мақсатты әрекетті немесе әрекеттерді қамтитын нысанды таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="1e36f-109">Choose the entity that includes your target activity or activities.</span></span>

1. <span data-ttu-id="1e36f-110">Аудитория мәліметтерінде **Деректер** > **Әрекеттер** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="1e36f-110">In audience insights, go to **Data** > **Activities**.</span></span>

1. <span data-ttu-id="1e36f-111">**Әрекетті қосу** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="1e36f-111">Select **Add activity**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="1e36f-112">Нысанда тұтынушының уақыт шкаласына қосылатын **Күн** түріндегі кем дегенде бір атрибут болуы қажет, **Күн** өрісінсіз нысандар қосылмайды.</span><span class="sxs-lookup"><span data-stu-id="1e36f-112">An entity must have at least one attribute of type **Date** to be included in a customer timeline and you can't add entities without **Date** fields.</span></span> <span data-ttu-id="1e36f-113">Егер нысан табылмаса, **Әрекетті қосу** басқару жүйесі өшіріледі.</span><span class="sxs-lookup"><span data-stu-id="1e36f-113">The **Add activity** control is disabled if no such entity is found.</span></span>

1. <span data-ttu-id="1e36f-114">**Әрекетті қосу** панелінде келесі өрістер үшін мәндерді орнатыңыз:</span><span class="sxs-lookup"><span data-stu-id="1e36f-114">In the **Add activity** pane, set the values for the following fields:</span></span>

   - <span data-ttu-id="1e36f-115">**Нысан**: Транзакциялық немесе әрекет деректері бар нысанды таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="1e36f-115">**Entity**: Select an entity that includes transactional or activity data.</span></span>
   - <span data-ttu-id="1e36f-116">**Бастапқы кілт**: Жазбаны айқын анықтайтын өрісті таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="1e36f-116">**Primary key**: Select the field that uniquely identifies a record.</span></span> <span data-ttu-id="1e36f-117">Онда қайталанатын мәндер, бос мәндер немесе жоқ мәндер болмауы керек.</span><span class="sxs-lookup"><span data-stu-id="1e36f-117">It shouldn't contain any duplicate values, empty values, or missing values.</span></span>
   - <span data-ttu-id="1e36f-118">**Уақыт белгісі**  Әрекеттің басталу уақытын көрсететін өрісті таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="1e36f-118">**Timestamp**: Select the field that represents the start time of your activity.</span></span>
   - <span data-ttu-id="1e36f-119">**Оқиға**: Әрекетке арналған оқиға болатын өрісті таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="1e36f-119">**Event**: Select the field that is the event for the activity.</span></span>
   - <span data-ttu-id="1e36f-120">**Веб-мекенжай**: осы тіркелгі туралы қосымша ақпарат беретін URL мекенжайын көрсететін өрісті таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="1e36f-120">**Web address**: Select the field that represents a URL providing additional information about this activity.</span></span> <span data-ttu-id="1e36f-121">Мысалы, осы әрекетке негізделген транзакциялық жүйе.</span><span class="sxs-lookup"><span data-stu-id="1e36f-121">For example, the transactional system that sources this activity.</span></span> <span data-ttu-id="1e36f-122">Бұл URL мекенжайы дереккөз өрісі болуы мүмкін немесе Power Query түрлендіруін пайдаланып жаңа өріс ретінде құрастырылуы мүмкін.</span><span class="sxs-lookup"><span data-stu-id="1e36f-122">This URL can be any field from the data source, or it can be constructed as a new field using a Power Query transformation.</span></span> <span data-ttu-id="1e36f-123">Бұл URL деректері API көрсеткіштерін пайдаланып төменгі ағын пайдаланылуы мүмкін Бірыңғай әрекет нысанында сақталады.</span><span class="sxs-lookup"><span data-stu-id="1e36f-123">This URL data will be stored in the Unified Activity entity, which can be consumed downstream using APIs.</span></span>
   - <span data-ttu-id="1e36f-124">**Мәліметтер**: Қосымша ақпаратқа арналған қосымша өрісті таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="1e36f-124">**Details**: Optionally, select the field that is added for additional details.</span></span>
   - <span data-ttu-id="1e36f-125">**Белгіше**: Қажет болса, осы әрекетті көрсететін белгішені таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="1e36f-125">**Icon**: Optionally, select the icon that represents this activity.</span></span>
   - <span data-ttu-id="1e36f-126">**Әрекет түрі**: әрекеттің семантикалық анықтамасын ең жақсы сипаттайтын Common Data Model үлгісінің әрекет түрі сілтемесін анықтаңыз.</span><span class="sxs-lookup"><span data-stu-id="1e36f-126">**Activity Type**: Define the activity type reference to Common Data Model that best describes the semantic definition of the activity.</span></span>

1. <span data-ttu-id="1e36f-127">**Қарым-қатынасты орнату** бөлімінде әрекет деректерін өзінің сәйкес тұтынушысына қосу үшін мәліметтерді конфигурациялаңыз.</span><span class="sxs-lookup"><span data-stu-id="1e36f-127">In the **Set up relationship** section, configure the details to connect your activity data to its corresponding customer.</span></span>

    - <span data-ttu-id="1e36f-128">**Әрекет нысанының өрісі** : Басқа нысанмен қарым-қатынас құру үшін қолданылатын әрекет нысанында өрісті таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="1e36f-128">**Activity entity field**: Select the field in your activity entity that will be used to establish a relationship with another entity.</span></span>
    - <span data-ttu-id="1e36f-129">**Тұтынушы нысаны** : Әрекет нысаныңыз қарым-қатынаста болатын тұтынушы нысанының сәйкес көзін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="1e36f-129">**Customer entity**: Select the corresponding source customer entity with which your activity entity will be in relationship.</span></span> <span data-ttu-id="1e36f-130">Сіз тек деректерді біріктіру процесінде пайдаланылған бастапқы тұтынушы нысандарына қатыстыра аласыз.</span><span class="sxs-lookup"><span data-stu-id="1e36f-130">You can relate to only those source customer entities that are used in the data unification process.</span></span>
    - <span data-ttu-id="1e36f-131">**Тұтынушы нысанының өрісі** : Бұл өріс салыстыру процесінде таңдалған бастапқы тұтынушы нысанының негізгі кілтін көрсетеді.</span><span class="sxs-lookup"><span data-stu-id="1e36f-131">**Customer entity field**: This field shows the primary key of the source customer entity as selected in the map process.</span></span> <span data-ttu-id="1e36f-132">Тұтынушының бастапқы нысанындағы осы негізгі кілт әрекет нысанымен байланыс орнату үшін пайдаланылады.</span><span class="sxs-lookup"><span data-stu-id="1e36f-132">This primary key field in the source customer entity is used to establish a relationship with the activity entity.</span></span>
    - <span data-ttu-id="1e36f-133">**Атау** : Егер осы әрекет нысаны мен таңдалған бастапқы тұтынушы нысаны арасындағы байланыс бұрыннан бар болса, қатынас атауы тек оқу режимінде болады.</span><span class="sxs-lookup"><span data-stu-id="1e36f-133">**Name**: If a relationship between this activity entity and the selected source customer entity already exists, the relationship name will be in read-only mode.</span></span> <span data-ttu-id="1e36f-134">Егер мұндай байланыс болмаса, онда осында көрсетілген жаңа атаумен қарым-қатынастар жасалады.</span><span class="sxs-lookup"><span data-stu-id="1e36f-134">If there no such relationship exists, a new relationship will be created with the name provided here.</span></span>
   
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="1e36f-135">![Нысандар қатынасын анықтаңыз](media/activities-entities-define.png "Нысан қатынасын анықтаңыз")</span><span class="sxs-lookup"><span data-stu-id="1e36f-135">![Define the entity relationship](media/activities-entities-define.png "Define the entity relationship")</span></span>

1. <span data-ttu-id="1e36f-136">Өзгерістерді қолдану үшін **Сақтау** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="1e36f-136">Select **Save** to apply your changes.</span></span>

1. <span data-ttu-id="1e36f-137">**Әрекеттер** бетінде **Іске қосу** түймесін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="1e36f-137">On the **Activities** page, select **Run**.</span></span>

> [!TIP]
> <span data-ttu-id="1e36f-138">Тапсырмалар/процестерге арналған [күйдің алты түрі](system.md#status-types) бар.</span><span class="sxs-lookup"><span data-stu-id="1e36f-138">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="1e36f-139">Сонымен қатар, көптеген процестер [басқа кезектегі процестерге тәуелді](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="1e36f-139">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="1e36f-140">Бүкіл тапсырманың барысы туралы мәліметтерді көру үшін процестің күйін таңдай аласыз.</span><span class="sxs-lookup"><span data-stu-id="1e36f-140">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="1e36f-141">Бір жұмыс тапсырмаларының бірі үшін **Мәліметтерді көру** параметрін таңдағаннан кейін, қосымша ақпаратты көруге болады: өңдеу уақыты, соңғы өңделген күні және тапсырмаға қатысты барлық қателер мен ескертулер.</span><span class="sxs-lookup"><span data-stu-id="1e36f-141">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="edit-an-activity"></a><span data-ttu-id="1e36f-142">Әрекетті өңдеу</span><span class="sxs-lookup"><span data-stu-id="1e36f-142">Edit an activity</span></span>

1. <span data-ttu-id="1e36f-143">Аудитория мәліметтерінде **Деректер** > **Әрекеттер** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="1e36f-143">In audience insights, go to **Data** > **Activities**.</span></span>

2. <span data-ttu-id="1e36f-144">Өңдеу қажет әрекет нысанын таңдап, **Өңдеу** опциясын басыңыз.</span><span class="sxs-lookup"><span data-stu-id="1e36f-144">Select the activity entity you want to edit and select **Edit**.</span></span> <span data-ttu-id="1e36f-145">Болмаса, меңзерді нысан қатарына апарып, **Өңдеу** белгішесін басыңыз.</span><span class="sxs-lookup"><span data-stu-id="1e36f-145">Or, you can hover over the entity row and select the **Edit** icon.</span></span>

3. <span data-ttu-id="1e36f-146">**Өңдеу** белгішесін басыңыз.</span><span class="sxs-lookup"><span data-stu-id="1e36f-146">Click on the **Edit** icon.</span></span>

4. <span data-ttu-id="1e36f-147">**Әрекетті өңдеу** панелінде мәндерді жаңартып, **Сақтау** түймесін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="1e36f-147">In the **Edit activity** pane, update the values and select **Save**.</span></span>

5. <span data-ttu-id="1e36f-148">**Әрекеттер** бетінде **Іске қосу** түймесін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="1e36f-148">On the **Activities** page, select **Run**.</span></span>

## <a name="delete-an-activity"></a><span data-ttu-id="1e36f-149">Әрекетті жою</span><span class="sxs-lookup"><span data-stu-id="1e36f-149">Delete an activity</span></span>

1. <span data-ttu-id="1e36f-150">Аудитория мәліметтерінде **Деректер** > **Әрекеттер** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="1e36f-150">In audience insights, go to **Data** > **Activities**.</span></span>

2. <span data-ttu-id="1e36f-151">Жою қажет әрекет нысанын таңдап, **Жою** опциясын басыңыз.</span><span class="sxs-lookup"><span data-stu-id="1e36f-151">Select the activity entity you want to remove and select **Delete**.</span></span> <span data-ttu-id="1e36f-152">Болмаса, меңзерді нысан қатарына апарып, **Жою** белгішесін басыңыз.</span><span class="sxs-lookup"><span data-stu-id="1e36f-152">Or, you can hover over the entity row and select the **Delete** icon.</span></span> <span data-ttu-id="1e36f-153">Сонымен қатар, сіз бірден бірнеше жойылатын әрекет нысандарын таңдай аласыз.</span><span class="sxs-lookup"><span data-stu-id="1e36f-153">Additionally, you can select multiple activity entities to be deleted at once.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="1e36f-154">![Нысан қарым-қатынастарын өңдеу немесе жою](media/activities-entities-edit-delete.png "Нысан қарым-қатынастарын өңдеу немесе жою")</span><span class="sxs-lookup"><span data-stu-id="1e36f-154">![Edit or delete the entity relationship](media/activities-entities-edit-delete.png "Edit or delete the entity relationship")</span></span>

3. <span data-ttu-id="1e36f-155">**Жою** белгішесін басыңыз.</span><span class="sxs-lookup"><span data-stu-id="1e36f-155">Select on the **Delete** icon.</span></span>

4. <span data-ttu-id="1e36f-156">Жоюды растаңыз.</span><span class="sxs-lookup"><span data-stu-id="1e36f-156">Confirm your deletion.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]