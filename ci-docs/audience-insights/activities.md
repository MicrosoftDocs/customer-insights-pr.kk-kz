---
title: Тұтынушы әрекеттері
description: Тұтынушылар әрекеттерін анықтап, оларды тұтынушылардың уақыт кестесінде қарап шығыңыз.
ms.date: 04/07/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.openlocfilehash: 342aeb33f652d5d60cd25e13969766954bf56370
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304933"
---
# <a name="customer-activities"></a><span data-ttu-id="3bfa3-103">Тұтынушы әрекеттері</span><span class="sxs-lookup"><span data-stu-id="3bfa3-103">Customer activities</span></span>

<span data-ttu-id="3bfa3-104">Әрекеттерді хронологиялық түрде тізімдейтін уақыт шкаласын жасау үшін Dynamics 365 Customer Insights бағдарламасындағы [әртүрлі деректер көздеріндегі](data-sources.md) тұтынушы әрекеттерін біріктіріңіз.</span><span class="sxs-lookup"><span data-stu-id="3bfa3-104">Combine customer activities from [various data sources](data-sources.md) in Dynamics 365 Customer Insights to create a timeline that lists the activities chronologically.</span></span> <span data-ttu-id="3bfa3-105">Dynamics 365 бағдарламаларындағы уақыт шкаласын [Тұтынушы картасының қондырмасы](customer-card-add-in.md) шешіміне немесе Power BI бақылау тақтасына қосыңыз.</span><span class="sxs-lookup"><span data-stu-id="3bfa3-105">Include the timeline in Dynamics 365 apps with the [Customer Card add-in](customer-card-add-in.md) solution, or in a Power BI dashboard.</span></span>

## <a name="define-an-activity"></a><span data-ttu-id="3bfa3-106">Әрекетті анықтау</span><span class="sxs-lookup"><span data-stu-id="3bfa3-106">Define an activity</span></span>

<span data-ttu-id="3bfa3-107">Деректер көздерінде бірнеше деректер көздерінен алынған транзакциялық және әрекет деректері бар нысандар болуы мүмкін.</span><span class="sxs-lookup"><span data-stu-id="3bfa3-107">Your data sources can include entities with transactional and activity data from multiple data sources.</span></span> <span data-ttu-id="3bfa3-108">Осы нысандарды анықтап, тұтынушының уақыт шкаласында көргіңіз келетін әрекеттерді таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="3bfa3-108">Identify these entities and select the activities you want to view on the customer's timeline.</span></span> <span data-ttu-id="3bfa3-109">Мақсатты әрекетті немесе әрекеттерді қамтитын нысанды таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="3bfa3-109">Choose the entity that includes your target activity or activities.</span></span>

> [!NOTE]
> <span data-ttu-id="3bfa3-110">Нысанда тұтынушының уақыт шкаласына қосылатын **Күн** түріндегі кем дегенде бір атрибут болуы қажет, **Күн** өрісінсіз нысандар қосылмайды.</span><span class="sxs-lookup"><span data-stu-id="3bfa3-110">An entity must have at least one attribute of type **Date** to be included in a customer timeline and you can't add entities without **Date** fields.</span></span> <span data-ttu-id="3bfa3-111">Егер нысан табылмаса, **Әрекетті қосу** басқару жүйесі өшіріледі.</span><span class="sxs-lookup"><span data-stu-id="3bfa3-111">The **Add activity** control is disabled if no such entity is found.</span></span>

1. <span data-ttu-id="3bfa3-112">Аудитория мәліметтерінде **Деректер** > **Әрекеттер** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="3bfa3-112">In audience insights, go to **Data** > **Activities**.</span></span>

1. <span data-ttu-id="3bfa3-113">Әрекетті орнату процесінің қадамдық тәжірибесін бастау үшін **Әрекет қосу** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="3bfa3-113">Select **Add activity** to start the guided experience for the activity setup process.</span></span>

1. <span data-ttu-id="3bfa3-114">**Әрекет деректері** қадамында келесі өрістер үшін мәндерді орнатыңыз:</span><span class="sxs-lookup"><span data-stu-id="3bfa3-114">In the **Activity data** step, set the values for the following fields:</span></span>

   - <span data-ttu-id="3bfa3-115">**Әрекет атауы**: әрекет үшін атау таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="3bfa3-115">**Activity name**: Select a name for your activity.</span></span>
   - <span data-ttu-id="3bfa3-116">**Нысан**: Транзакциялық немесе әрекет деректері бар нысанды таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="3bfa3-116">**Entity**: Select an entity that includes transactional or activity data.</span></span>
   - <span data-ttu-id="3bfa3-117">**Бастапқы кілт**: Жазбаны айқын анықтайтын өрісті таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="3bfa3-117">**Primary key**: Select the field that uniquely identifies a record.</span></span> <span data-ttu-id="3bfa3-118">Онда қайталанатын мәндер, бос мәндер немесе жоқ мәндер болмауы керек.</span><span class="sxs-lookup"><span data-stu-id="3bfa3-118">It shouldn't contain any duplicate values, empty values, or missing values.</span></span>

   :::image type="content" source="media/Activity_Wizard1.PNG" alt-text="Әрекет деректерін атауымен, нысанымен және негізгі кілтімен орнатыңыз.":::

1. <span data-ttu-id="3bfa3-120">Келесі қадамға өту үшін **Келесі** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="3bfa3-120">Select **Next** to go to the next step.</span></span>

1. <span data-ttu-id="3bfa3-121">**Қарым-қатынас** қадамында әрекет деректерін тиісті тұтынушыға қосу үшін мәліметтерді конфигурациялаңыз.</span><span class="sxs-lookup"><span data-stu-id="3bfa3-121">In the **Relationship** step, configure the details to connect your activity data to its corresponding customer.</span></span> <span data-ttu-id="3bfa3-122">Бұл қадам нысандар арасындағы байланысты көрсетеді.</span><span class="sxs-lookup"><span data-stu-id="3bfa3-122">This step visualizes the connection between entities.</span></span>  

   - <span data-ttu-id="3bfa3-123">**Бірінші**: басқа нысанмен қарым‑қатынас орнату үшін қолданылатын әрекет нысанындағы сыртқы өріс.</span><span class="sxs-lookup"><span data-stu-id="3bfa3-123">**First**: Foreign field in your activity entity that will be used to establish a relationship with another entity.</span></span>
   - <span data-ttu-id="3bfa3-124">**Екінші**: әрекет нысаны қарым-қатынаста болатын тиісті бастапқы тұтынушы нысаны.</span><span class="sxs-lookup"><span data-stu-id="3bfa3-124">**Second**: Corresponding source customer entity with which your activity entity will be in relationship.</span></span> <span data-ttu-id="3bfa3-125">Сіз тек деректерді біріздендіру процесінде қолданылатын бастапқы тұтынушы нысандарына қатысты бола аласыз.</span><span class="sxs-lookup"><span data-stu-id="3bfa3-125">You can only relate to source customer entities that are used in the data unification process.</span></span>
   - <span data-ttu-id="3bfa3-126">**Үшінші**: егер осы әрекет нысаны мен таңдалған бастапқы тұтынушы нысаны арасындағы байланыс бұрыннан бар болса, қатынас атауы тек оқуға арналған режимде болады.</span><span class="sxs-lookup"><span data-stu-id="3bfa3-126">**Third**: If a relationship between this activity entity and the selected source customer entity already exists, the relationship name will be in read-only mode.</span></span> <span data-ttu-id="3bfa3-127">Егер ондай қатынас болмаса, онда сіз осы өрісте көрсеткен атаумен жаңа қатынас жасалады.</span><span class="sxs-lookup"><span data-stu-id="3bfa3-127">If no such relationship exists, a new relationship will be created with the name you provide in this box.</span></span>

   :::image type="content" source="media/Activity_Wizard2.PNG" alt-text="Нысандар қатынасын анықтаңыз.":::

1. <span data-ttu-id="3bfa3-129">Келесі қадамға өту үшін **Келесі** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="3bfa3-129">Select **Next** to go to the next step.</span></span> 

1. <span data-ttu-id="3bfa3-130">**Әрекетті біріздендіру** қадамында әрекет оқиғасын және әрекеттің басталу уақытын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="3bfa3-130">In the **Activity unification** step, choose the activity event and the start time of your activity.</span></span> 
   - <span data-ttu-id="3bfa3-131">**Талап етілетін өрісте**</span><span class="sxs-lookup"><span data-stu-id="3bfa3-131">**Required fields**</span></span>
      - <span data-ttu-id="3bfa3-132">**Оқиға әрекеті**: осы әрекет үшін оқиға болып табылатын өріс.</span><span class="sxs-lookup"><span data-stu-id="3bfa3-132">**Event activity**: Field that is the event for this activity.</span></span>
      - <span data-ttu-id="3bfa3-133">**Уақыт белгісі**: әрекеттің басталу уақытын білдіретін өріс.</span><span class="sxs-lookup"><span data-stu-id="3bfa3-133">**Timestamp**: Field that represents the start time of your activity.</span></span>

   - <span data-ttu-id="3bfa3-134">**Қосымша өрістер**</span><span class="sxs-lookup"><span data-stu-id="3bfa3-134">**Optional fields**</span></span>
      - <span data-ttu-id="3bfa3-135">**Қосымша мәлімет**: осы әрекетке қатысты ақпараты бар өріс.</span><span class="sxs-lookup"><span data-stu-id="3bfa3-135">**Additional detail**: Field with relevant information for this activity.</span></span>
      - <span data-ttu-id="3bfa3-136">**Белгіше**: осы әрекет түрін жақсы көрсететін белгіше.</span><span class="sxs-lookup"><span data-stu-id="3bfa3-136">**Icon**: Icon that best represents this activity type.</span></span>
      - <span data-ttu-id="3bfa3-137">**Веб-мекен-жайы**: осы әрекет туралы ақпараты бар URL мекенжайы бар өріс.</span><span class="sxs-lookup"><span data-stu-id="3bfa3-137">**Web address**: Field containing a URL with information about this activity.</span></span> <span data-ttu-id="3bfa3-138">Мысалы, осы әрекетке негізделген транзакциялық жүйе.</span><span class="sxs-lookup"><span data-stu-id="3bfa3-138">For example, the transactional system that sources this activity.</span></span> <span data-ttu-id="3bfa3-139">Бұл URL мекенжайы дереккөз өрісі болуы мүмкін немесе Power Query түрлендіруін пайдаланып жаңа өріс ретінде құрастырылуы мүмкін.</span><span class="sxs-lookup"><span data-stu-id="3bfa3-139">This URL can be any field from the data source, or it can be constructed as a new field using a Power Query transformation.</span></span> <span data-ttu-id="3bfa3-140">URL деректері *Бірыңғай әрекет* нысанында сақталады, оны [API](apis.md) көмегімен тұтынуға болады.</span><span class="sxs-lookup"><span data-stu-id="3bfa3-140">The URL data will be stored in the *Unified Activity* entity, which can be consumed downstream using [APIs](apis.md).</span></span>
   
   :::image type="content" source="media/Activity_Wizard3.PNG" alt-text="Бірыңғай әрекет нысанындағы тұтынушы әрекеті деректерін көрсетіңіз.":::

1. <span data-ttu-id="3bfa3-142">Келесі қадамға өту үшін **Келесі** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="3bfa3-142">Select **Next** to move to the next step.</span></span> <span data-ttu-id="3bfa3-143">Әрекетті қазір әрекет түрі **Басқа** күйіне орнатылған күйде сақтау үшін **Аяқтау және қарап шығу** түймешігін таңдауға болады.</span><span class="sxs-lookup"><span data-stu-id="3bfa3-143">You can select **Finish and review** to save the activity now with the activity type set to **Other**.</span></span> 

1. <span data-ttu-id="3bfa3-144">**Әрекет түрі** қадамында әрекет түрін таңдап, Customer Insights бағдарламасының басқа салаларында қолдану үшін кейбір әрекет түрлерін семантикалық түрде салыстыру керек болса, қалауыңыз бойынша таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="3bfa3-144">In the **Activity Type** step, choose the activity type and optionally select if you want to semantically map some of the activity types for use in other areas of Customer Insights.</span></span> <span data-ttu-id="3bfa3-145">Ағымдағы уақытта *Жазылым* және *SalesOrderLine* әрекет түрлерін өрістерді салыстыруға келіскеннен кейін семантикалық түрде салыстыруға болады.</span><span class="sxs-lookup"><span data-stu-id="3bfa3-145">Currently, *Subscription* and *SalesOrderLine* activity types can be semantically mapped after agreeing to map the fields.</span></span> <span data-ttu-id="3bfa3-146">Егер әрекет түрі жаңа әрекетке сәйкес келмесе, *Басқа* түймешігін таңдауға немесе реттелетін әрекет түрі үшін *Жаңасын жасау* түймешігін таңдауға болады.</span><span class="sxs-lookup"><span data-stu-id="3bfa3-146">If an activity type isn't relevant for the new activity, you can choose *Other* or *Create new* for a custom activity type.</span></span>

1. <span data-ttu-id="3bfa3-147">Келесі қадамға өту үшін **Келесі** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="3bfa3-147">Select **Next** to move to the next step.</span></span> 

1. <span data-ttu-id="3bfa3-148">**Қарап шығу** қадамында таңдауларыңызды тексеріңіз.</span><span class="sxs-lookup"><span data-stu-id="3bfa3-148">In the **Review** step, verify your selections.</span></span> <span data-ttu-id="3bfa3-149">Алдыңғы қадамдардың кез келгеніне оралыңыз және қажет болса ақпаратты жаңартыңыз.</span><span class="sxs-lookup"><span data-stu-id="3bfa3-149">Go back to any of the previous steps and update the information if necessary.</span></span>

   :::image type="content" source="media/Activity_Wizard5.PNG" alt-text="Әрекет үшін көрсетілген өрістерді қарап шығыңыз.":::
   
1. <span data-ttu-id="3bfa3-151">Өзгерістерді қолдану үшін **Әрекетті сақтау** түймешігін таңдаңыз және **Деректер** > **Әрекеттер** тармағына оралу үшін **Дайын** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="3bfa3-151">Select **Save activity** to apply your changes and select **Done** to go back to **Data** > **Activities**.</span></span> <span data-ttu-id="3bfa3-152">Мұнда сіз уақыт шкаласында қандай әрекеттер көрсетілетіндігін көресіз.</span><span class="sxs-lookup"><span data-stu-id="3bfa3-152">Here you see which activities are set to show in the timeline.</span></span> 

1. <span data-ttu-id="3bfa3-153">**Әрекеттер** бетінде әрекетті өңдеу үшін **Іске қосу** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="3bfa3-153">On the **Activities** page, select **Run** to process the activity.</span></span> 

> [!TIP]
> <span data-ttu-id="3bfa3-154">Тапсырмалар/процестерге арналған [күйдің алты түрі](system.md#status-types) бар.</span><span class="sxs-lookup"><span data-stu-id="3bfa3-154">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="3bfa3-155">Сонымен қатар, көптеген процестер [басқа кезектегі процестерге тәуелді](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="3bfa3-155">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="3bfa3-156">Бүкіл тапсырманың барысы туралы мәліметтерді көру үшін процестің күйін таңдай аласыз.</span><span class="sxs-lookup"><span data-stu-id="3bfa3-156">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="3bfa3-157">Бір жұмыс тапсырмаларының бірі үшін **Мәліметтерді көру** параметрін таңдағаннан кейін, қосымша ақпаратты көруге болады: өңдеу уақыты, соңғы өңделген күні және тапсырмаға қатысты барлық қателер мен ескертулер.</span><span class="sxs-lookup"><span data-stu-id="3bfa3-157">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>


## <a name="manage-existing-activities"></a><span data-ttu-id="3bfa3-158">Бұрыннан бар әрекеттерді басқару</span><span class="sxs-lookup"><span data-stu-id="3bfa3-158">Manage existing activities</span></span>

<span data-ttu-id="3bfa3-159">**Деректер** > **Әрекеттер** тармағында барлық сақталған әрекеттерді көруге және оларды басқаруға болады.</span><span class="sxs-lookup"><span data-stu-id="3bfa3-159">On **Data** > **Activities**, you can view all your saved activities, and manage them.</span></span> <span data-ttu-id="3bfa3-160">Әрбір әрекет дерек көзі, нысан және әрекет түрі туралы мәліметтерді қамтитын жолмен ұсынылады.</span><span class="sxs-lookup"><span data-stu-id="3bfa3-160">Each activity is represented by a row that also includes details about the source, the entity, and the activity type.</span></span>

<span data-ttu-id="3bfa3-161">Келесі әрекеттер әрекетті таңдаған кезде қолжетімді болады.</span><span class="sxs-lookup"><span data-stu-id="3bfa3-161">The following actions are available when you select an activity.</span></span> 

- <span data-ttu-id="3bfa3-162">**Өңдеу**: қарап шығу қадамындағы әрекетті орнатуды ашады.</span><span class="sxs-lookup"><span data-stu-id="3bfa3-162">**Edit**: Opens the activity setup on the review step.</span></span> <span data-ttu-id="3bfa3-163">Ағымдағы конфигурацияның кез келгенін немесе барлығын осы қадамнан өзгертуге болады.</span><span class="sxs-lookup"><span data-stu-id="3bfa3-163">You can change any or all of the current configuration from this step.</span></span> <span data-ttu-id="3bfa3-164">Конфигурацияны өзгерткеннен кейін **Әрекетті сақтау** түймешігін таңдаңыз, содан кейін өзгерістерді өңдеу үшін **Іске қосу** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="3bfa3-164">After changing the configuration, select **Save activity** and then select **Run** to process the changes.</span></span>

- <span data-ttu-id="3bfa3-165">**Атын өзгерту**: таңдалған әрекет үшін басқа атау енгізуге болатын диалогтік терезені ашады.</span><span class="sxs-lookup"><span data-stu-id="3bfa3-165">**Rename**: Opens a dialog where you can enter a different name for the selected activity.</span></span> <span data-ttu-id="3bfa3-166">Өзгерістерді қолдану үшін **Сақтау** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="3bfa3-166">Select **Save** to apply your changes.</span></span>

- <span data-ttu-id="3bfa3-167">**Жою**: таңдалған әрекеттің жойылуын растайтын диалогтік терезені ашады.</span><span class="sxs-lookup"><span data-stu-id="3bfa3-167">**Delete**: Opens a dialog to confirm the deletion of the selected activity.</span></span> <span data-ttu-id="3bfa3-168">Әрекеттерді таңдап, содан кейін жою белгішесін таңдау арқылы бірден бірнеше әрекетті жоюға болады.</span><span class="sxs-lookup"><span data-stu-id="3bfa3-168">You can also delete more than one activity at once by selecting the activities and then selecting the delete icon.</span></span> <span data-ttu-id="3bfa3-169">Жоюды растау үшін **Жою** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="3bfa3-169">Select **Delete** to confirm the deletion.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
