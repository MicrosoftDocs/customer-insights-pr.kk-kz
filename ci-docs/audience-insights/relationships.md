---
title: Нысандар мен нысан жолдары арасындағы қатынастар
description: Бірнеше деректер көздерінен нысандар арасындағы қарым-қатынастарды жасап, басқарыңыз.
ms.date: 06/01/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.openlocfilehash: d5b9566ec88096fec31d8e164a51598159ec26d4
ms.sourcegitcommit: ece48f80a7b470fb33cd36e3096b4f1e9190433a
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 06/03/2021
ms.locfileid: "6171171"
---
# <a name="relationships-between-entities"></a><span data-ttu-id="b9a99-103">Нысандар арасындағы қарым-қатынастар</span><span class="sxs-lookup"><span data-stu-id="b9a99-103">Relationships between entities</span></span>

<span data-ttu-id="b9a99-104">Қарым-қатынастар нысандарды біріктіреді және нысандар жалпы идентификаторды, сыртқы кілтпен бөліскен кезде сіздің деректеріңіздің диаграммасын анықтайды.</span><span class="sxs-lookup"><span data-stu-id="b9a99-104">Relationships connect entities and define a graph of your data when entities share a common identifier, a foreign key.</span></span> <span data-ttu-id="b9a99-105">Бұл сыртқы кілтке бір нысаннан екінші нысанға сілтеме жасауға болады.</span><span class="sxs-lookup"><span data-stu-id="b9a99-105">This foreign key can be referenced from one entity to another.</span></span> <span data-ttu-id="b9a99-106">Қосылған нысандар бірнеше деректер көзі негізінде сегменттер мен өлшемдер анықтамасын қосады.</span><span class="sxs-lookup"><span data-stu-id="b9a99-106">Connected entities enable the definition of segments and measures based on multiple data sources.</span></span>

<span data-ttu-id="b9a99-107">Қарым-қатынастың үш түрі бар:</span><span class="sxs-lookup"><span data-stu-id="b9a99-107">There are three types of relationships:</span></span> 
- <span data-ttu-id="b9a99-108">Жүйе деректерді біріздендіру процесінің бөлігі ретінде жасаған өңделмейтін жүйелік қатынастар</span><span class="sxs-lookup"><span data-stu-id="b9a99-108">Non-editable system relationships, created by the system as part of the data unification process</span></span>
- <span data-ttu-id="b9a99-109">Қабылдау деректер көздерінен автоматты түрде жасалатын өңделмейтін иеленген қатынастар</span><span class="sxs-lookup"><span data-stu-id="b9a99-109">Non-editable inherited relationships, which are created automatically from ingesting data sources</span></span> 
- <span data-ttu-id="b9a99-110">Пайдаланушылар жасаған және конфигурацияланған өңделмелі реттелетін қатынастар</span><span class="sxs-lookup"><span data-stu-id="b9a99-110">Editable custom relationships, created and configured by users</span></span>

## <a name="non-editable-system-relationships"></a><span data-ttu-id="b9a99-111">Өңделмейтін жүйелік қатынастар</span><span class="sxs-lookup"><span data-stu-id="b9a99-111">Non-editable system relationships</span></span>

<span data-ttu-id="b9a99-112">Деректерді біріздендіру кезінде жүйелік қатынастар автоматты түрде интеллектуалды сәйкестендіру негізінде жасалады.</span><span class="sxs-lookup"><span data-stu-id="b9a99-112">During data unification, system relationships are created automatically based on intelligent matching.</span></span> <span data-ttu-id="b9a99-113">Бұл қарым-қатынастар тұтынушы профилі жазбаларын тиісті жазбалармен байланыстыруға көмектеседі.</span><span class="sxs-lookup"><span data-stu-id="b9a99-113">These relationships help relate the customer profile records with corresponding records.</span></span> <span data-ttu-id="b9a99-114">Төмендегі диаграмма жүйеге негізделген үш қатынастың жасалуын бейнелейді.</span><span class="sxs-lookup"><span data-stu-id="b9a99-114">The following diagram illustrates the creation of three system-based relationships.</span></span> <span data-ttu-id="b9a99-115">Тұтынушы нысаны бірыңғай *Тұтынушы* нысанын жасау үшін басқа нысандармен сәйкестендіріледі.</span><span class="sxs-lookup"><span data-stu-id="b9a99-115">The customer entity is matched with other entities to produce the unified *Customer* entity.</span></span>

:::image type="content" source="media/relationships-entities-merge.png" alt-text="Үш 1-n қатынасы бар тұтынушы нысанына арналған қатынас жолдары бар диаграмма.":::

- <span data-ttu-id="b9a99-117">***CustomerToContact* қатынасы** *Тұтынушы* нысаны мен *Контакт* нысаны арасында жасалды.</span><span class="sxs-lookup"><span data-stu-id="b9a99-117">***CustomerToContact* relationship** was created between the *Customer* entity and the *Contact* entity.</span></span> <span data-ttu-id="b9a99-118">*Тұтынушы* нысаны *Контакт* нысанының **contactID** негізгі өрісімен байланыстыру үшін **Contact_contactID** негізгі өрісін алады.</span><span class="sxs-lookup"><span data-stu-id="b9a99-118">The *Customer* entity gets the key field **Contact_contactID** to relate to the *Contact* entity key field **contactID**.</span></span>
- <span data-ttu-id="b9a99-119">***CustomerToAccount* қатынасы** *Тұтынушы* нысаны мен *Тіркелгі* нысаны арасында жасалды.</span><span class="sxs-lookup"><span data-stu-id="b9a99-119">***CustomerToAccount* relationship** was created between the *Customer* entity and the *Account* entity.</span></span> <span data-ttu-id="b9a99-120">*Тұтынушы* нысаны *Тіркелгі* нысанының **accountID** негізгі өрісімен байланыстыру үшін **Account_accountID** негізгі өрісін алады.</span><span class="sxs-lookup"><span data-stu-id="b9a99-120">The *Customer* entity gets the key field **Account_accountID** to relate to the *Account* entity key field **accountID**.</span></span>
- <span data-ttu-id="b9a99-121">***CustomerToWebAccount* қатынасы** *Тұтынушы* нысаны мен *Веб-тіркелгі* нысаны арасында жасалды.</span><span class="sxs-lookup"><span data-stu-id="b9a99-121">***CustomerToWebAccount* relationship** was created between the *Customer* entity and the *WebAccount* entity.</span></span> <span data-ttu-id="b9a99-122">*Тұтынушы* нысаны *Веб-тіркелгі* нысанының **webaccountID** негізгі өрісімен байланыстыру үшін **WebAccount_webaccountID** негізгі өрісін алады.</span><span class="sxs-lookup"><span data-stu-id="b9a99-122">The *Customer* entity gets the key field **WebAccount_webaccountID** to relate to the *WebAccount* entity key field **webaccountID**.</span></span>

## <a name="non-editable-inherited-relationships"></a><span data-ttu-id="b9a99-123">Өңделмейтін иеленген қатынастар</span><span class="sxs-lookup"><span data-stu-id="b9a99-123">Non-editable inherited relationships</span></span>

<span data-ttu-id="b9a99-124">Деректерді қабылдау процесі кезінде жүйе деректер көздерінде бұрыннан бар қатынастардың бар‑жоғын тексереді.</span><span class="sxs-lookup"><span data-stu-id="b9a99-124">During the data ingestion process, the system checks data sources for existing relationships.</span></span> <span data-ttu-id="b9a99-125">Егер ешқандай қатынас болмаса, жүйе оларды автоматты түрде жасайды.</span><span class="sxs-lookup"><span data-stu-id="b9a99-125">If no relationship exists, the system automatically creates them.</span></span> <span data-ttu-id="b9a99-126">Бұл қатынастар кейінгі әрекет процестерінде де қолданылады.</span><span class="sxs-lookup"><span data-stu-id="b9a99-126">These relationships are also used in downstream processes.</span></span>

## <a name="create-a-custom-relationship"></a><span data-ttu-id="b9a99-127">Реттелетін қатынас жасау</span><span class="sxs-lookup"><span data-stu-id="b9a99-127">Create a custom relationship</span></span>

<span data-ttu-id="b9a99-128">Қатынас сыртқы кілтті қамтитын *бастапқы нысаннан* және бастапқы нысанның сыртқы кілті сілтеме жасайтын *мақсатты нысаннан* тұрады.</span><span class="sxs-lookup"><span data-stu-id="b9a99-128">Relationship consists of a *source entity* containing the foreign key and a *target entity* that the source entity's foreign key points to.</span></span> 

1. <span data-ttu-id="b9a99-129">Аудитория түсініктерінде **Деректер** > **Қарым-қатынастар** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="b9a99-129">In audience insights, go to **Data** > **Relationships**.</span></span>

2. <span data-ttu-id="b9a99-130">**Жаңа қарым-қатынас** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="b9a99-130">Select **New relationship**.</span></span>

3. <span data-ttu-id="b9a99-131">**Жаңа қатынас** тақтасында келесі ақпаратты көрсетіңіз:</span><span class="sxs-lookup"><span data-stu-id="b9a99-131">In the **New relationship** pane, provide the following information:</span></span>

   :::image type="content" source="media/relationship-add.png" alt-text="Бос енгізу өрістері бар жаңа қатынас бүйірлік тақтасы.":::

   - <span data-ttu-id="b9a99-133">**Қарым-қатынас атауы**: қарым-қатынастың мақсатын көрсететін атау.</span><span class="sxs-lookup"><span data-stu-id="b9a99-133">**Relationship name**: Name that reflects the purpose of the relationship.</span></span> <span data-ttu-id="b9a99-134">Мысалы: CustomerToSupportCase.</span><span class="sxs-lookup"><span data-stu-id="b9a99-134">Example: CustomerToSupportCase.</span></span>
   - <span data-ttu-id="b9a99-135">**Сипаттама**: қарым-қатынастар рөлінің сипаттамасы.</span><span class="sxs-lookup"><span data-stu-id="b9a99-135">**Description**: Description of the relationship.</span></span>
   - <span data-ttu-id="b9a99-136">**Бастапқы нысан**: қарым-қатынастың көзі ретінде қолданылатын нысан.</span><span class="sxs-lookup"><span data-stu-id="b9a99-136">**Source entity**: Entity that is used as a source in the relationship.</span></span> <span data-ttu-id="b9a99-137">Мысалы: SupportCase.</span><span class="sxs-lookup"><span data-stu-id="b9a99-137">Example: SupportCase.</span></span>
   - <span data-ttu-id="b9a99-138">**Мақсатты нысан**: қарым-қатынаста мақсат ретінде қолданылатын нысан.</span><span class="sxs-lookup"><span data-stu-id="b9a99-138">**Target entity**: Entity that is used as a target in the relationship.</span></span> <span data-ttu-id="b9a99-139">Мысалы: тұтынушы.</span><span class="sxs-lookup"><span data-stu-id="b9a99-139">Example: Customer.</span></span>
   - <span data-ttu-id="b9a99-140">**Дереккөз элементтер саны**: бастапқы нысанның элементтер санын көрсетіңіз.</span><span class="sxs-lookup"><span data-stu-id="b9a99-140">**Source cardinality**: Specify the cardinality of the source entity.</span></span> <span data-ttu-id="b9a99-141">Элементтер саны жиынтықтағы ықтимал элементтердің санын сипаттайды.</span><span class="sxs-lookup"><span data-stu-id="b9a99-141">Cardinality describes the number of possible elements in a set.</span></span> <span data-ttu-id="b9a99-142">Бұл әрдайым мақсатты элементтер санына қатысты.</span><span class="sxs-lookup"><span data-stu-id="b9a99-142">It always relates to the target cardinality.</span></span> <span data-ttu-id="b9a99-143">**Бір** немесе **Көп** опциясының бірін таңдауға болады.</span><span class="sxs-lookup"><span data-stu-id="b9a99-143">You can choose between **One** and **Many**.</span></span> <span data-ttu-id="b9a99-144">Тек көптеген-бір және бір-бір қарым-қатынастарына қолдау көрсетіледі.</span><span class="sxs-lookup"><span data-stu-id="b9a99-144">Only many-to-one and one-to-one relationships are supported.</span></span>  
     - <span data-ttu-id="b9a99-145">Көптен біреуге: бірнеше бастапқы жазбалар бір мақсатты жазбаға қатысты болуы мүмкін.</span><span class="sxs-lookup"><span data-stu-id="b9a99-145">Many-to-one: Multiple source records can relate to one target record.</span></span> <span data-ttu-id="b9a99-146">Мысалы: бір тұтынушы үшін бірнеше қолдау жағдайлары.</span><span class="sxs-lookup"><span data-stu-id="b9a99-146">Example: Multiple support cases from a single customer.</span></span>
     - <span data-ttu-id="b9a99-147">Бір-біріне: бір бастапқы жазба бір мақсатты жазбаға қатысты.</span><span class="sxs-lookup"><span data-stu-id="b9a99-147">One-to-one: A single source record relates to a one target record.</span></span> <span data-ttu-id="b9a99-148">Мысалы: бір тұтынушы үшін бір сенім идентификаторы.</span><span class="sxs-lookup"><span data-stu-id="b9a99-148">Example: One loyalty ID for a single customer.</span></span>

     > [!NOTE]
     > <span data-ttu-id="b9a99-149">Көптен көпке қатынастарын екі көптен біреуге қатынасын немесе бастапқы нысан мен мақсатты нысанды байланыстыратын байланыстырушы нысан көмегімен жасауға болады.</span><span class="sxs-lookup"><span data-stu-id="b9a99-149">Many-to-many relationships can be created using two many-to-one relationships and a linking entity, which connects the source entity and the target entity.</span></span>

   - <span data-ttu-id="b9a99-150">**Мақсатты элементтер саны**: мақсатты нысан жазбаларының элементтер санын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="b9a99-150">**Target cardinality**: Select the cardinality of the target entity records.</span></span> 
   - <span data-ttu-id="b9a99-151">**Бастапқы негізгі өріс**: бастапқы нысандағы сыртқы негізгі өріс.</span><span class="sxs-lookup"><span data-stu-id="b9a99-151">**Source key field**: The foreign key field in the source entity.</span></span> <span data-ttu-id="b9a99-152">Мысалы: SupportCase нысаны CaseID нысанын сыртқы кілт өрісі ретінде пайдалануы мүмкін.</span><span class="sxs-lookup"><span data-stu-id="b9a99-152">Example: SupportCase could use CaseID as a foreign key field.</span></span>
   - <span data-ttu-id="b9a99-153">**Мақсатты негізгі өріс**: мақсатты нысанның негізгі өрісі.</span><span class="sxs-lookup"><span data-stu-id="b9a99-153">**Target key field**: The key field of the target entity.</span></span> <span data-ttu-id="b9a99-154">Мысалы, тұтынушы **CustomerID** негізгі өрісін пайдалануы мүмкін.</span><span class="sxs-lookup"><span data-stu-id="b9a99-154">Example Customer could use the **CustomerID** key field.</span></span>

4. <span data-ttu-id="b9a99-155">Реттелетін қатынас жасау үшін **Сақтау** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="b9a99-155">Select **Save** to create the custom relationship.</span></span>

## <a name="view-relationships"></a><span data-ttu-id="b9a99-156">Қатынастарды көру</span><span class="sxs-lookup"><span data-stu-id="b9a99-156">View relationships</span></span>

<span data-ttu-id="b9a99-157">Қатынастар бетінде жасалған барлық қатынастар тізімі келтірілген.</span><span class="sxs-lookup"><span data-stu-id="b9a99-157">The Relationships page lists all the relationships that have been created.</span></span> <span data-ttu-id="b9a99-158">Әрбір жол бастапқы нысан, мақсатты нысан және элементтер саны туралы мәліметтерді қамтитын қатынасты білдіреді.</span><span class="sxs-lookup"><span data-stu-id="b9a99-158">Each row represents a relationship, which also includes details about the source entity, the target entity, and the cardinality.</span></span> 

:::image type="content" source="media/relationships-list.png" alt-text="Қатынастар бетінің әрекеттер жолағындағы қатынастар мен опциялар тізімі.":::

<span data-ttu-id="b9a99-160">Бұл бет бұрыннан бар және жаңа қатынастардың бірнеше опцияларын ұсынады:</span><span class="sxs-lookup"><span data-stu-id="b9a99-160">This page offers a set of options for existing and new relationships:</span></span> 
- <span data-ttu-id="b9a99-161">**Жаңа қатынасу**: [Реттелетін қатынас жасау](#create-a-custom-relationship).</span><span class="sxs-lookup"><span data-stu-id="b9a99-161">**New Relationship**: [Create a custom relationship](#create-a-custom-relationship).</span></span>
- <span data-ttu-id="b9a99-162">**Визуализатор**: бұрыннан бар қатынастардың желілік диаграммасын және олардың элементтер санын көру үшін [қатынас визуализаторын зерттеңіз](#explore-the-relationship-visualizer).</span><span class="sxs-lookup"><span data-stu-id="b9a99-162">**Visualizer**: [Explore the relationship visualizer](#explore-the-relationship-visualizer) to see a network diagram of the existing relationships and their cardinality.</span></span>
- <span data-ttu-id="b9a99-163">**Сүзу әдісі**: тізімде көрсетілетін қарым-қатынас түрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="b9a99-163">**Filter by**: Choose the type of relationships to show in the list.</span></span>
- <span data-ttu-id="b9a99-164">**Қатынастарды іздеу**: қатынастардың сипаттары бойынша мәтіндік іздеуді қолданыңыз.</span><span class="sxs-lookup"><span data-stu-id="b9a99-164">**Search relationships**: Use a text-based search on properties of the relationships.</span></span>

### <a name="explore-the-relationship-visualizer"></a><span data-ttu-id="b9a99-165">Қарым-қатынас визуализаторын зерттеу</span><span class="sxs-lookup"><span data-stu-id="b9a99-165">Explore the relationship visualizer</span></span>

<span data-ttu-id="b9a99-166">Қатынас визуализаторы қосылған нысандар мен олардың элементтер саны арасындағы бұрыннан бар қатынастардың желілік диаграммасын көрсетеді.</span><span class="sxs-lookup"><span data-stu-id="b9a99-166">The relationship visualizer shows a network diagram of the existing relationships between connected entities and their cardinality.</span></span>

<span data-ttu-id="b9a99-167">Көріністі теңшеу үшін, өрістерді кенепке сүйреп апару арқылы орнын өзгертуге болады.</span><span class="sxs-lookup"><span data-stu-id="b9a99-167">To customize the view, you can change the position of the boxes by dragging them on the canvas.</span></span>

:::image type="content" source="media/relationship-visualizer.png" alt-text="Қатысты нысандар арасындағы қосылымдары бар қатынас визуализаторы желілік диаграммасының скриншоты.":::

<span data-ttu-id="b9a99-169">Қолжетімді опциялар:</span><span class="sxs-lookup"><span data-stu-id="b9a99-169">Available options:</span></span> 
- <span data-ttu-id="b9a99-170">**Кескін ретінде экспорттау**: ағымдағы көріністі кескін файлы ретінде сақтау.</span><span class="sxs-lookup"><span data-stu-id="b9a99-170">**Export as image**: Save the current view as an image file.</span></span>
- <span data-ttu-id="b9a99-171">**Көлденең/тік орналасуға өзгерту**: нысандар мен қатынастардың туралануын өзгерту.</span><span class="sxs-lookup"><span data-stu-id="b9a99-171">**Change to horizontal/vertical layout**: Change the alignment of the entities and relationships.</span></span>
- <span data-ttu-id="b9a99-172">**Өңдеу**: өңдеу тақтасында реттелетін қатынастардың сипаттарын жаңарту және өзгертулерді сақтау.</span><span class="sxs-lookup"><span data-stu-id="b9a99-172">**Edit**: Update properties of custom relationships in the edit pane and save changes.</span></span>

## <a name="manage-existing-relationships"></a><span data-ttu-id="b9a99-173">Бұрыннан бар қатынастарды басқару</span><span class="sxs-lookup"><span data-stu-id="b9a99-173">Manage existing relationships</span></span> 

<span data-ttu-id="b9a99-174">Қатынастар бетінде әрбір қатынас жолмен ұсынылған.</span><span class="sxs-lookup"><span data-stu-id="b9a99-174">On the Relationships page, each relationship is represented by a row.</span></span> 

<span data-ttu-id="b9a99-175">Қатынасты таңдаңыз және келесі опциялардың бірін таңдаңыз:</span><span class="sxs-lookup"><span data-stu-id="b9a99-175">Select a relationship and choose one of the following options:</span></span> 
 
- <span data-ttu-id="b9a99-176">**Өңдеу**: өңдеу тақтасында реттелетін қатынастардың сипаттарын жаңарту және өзгертулерді сақтау.</span><span class="sxs-lookup"><span data-stu-id="b9a99-176">**Edit**: Update properties of custom relationships in the edit pane and save changes.</span></span>
- <span data-ttu-id="b9a99-177">**Жою**: реттелетін қатынастарды жою.</span><span class="sxs-lookup"><span data-stu-id="b9a99-177">**Delete**: Delete custom relationships.</span></span>
- <span data-ttu-id="b9a99-178">**Көру**: жүйе жасаған және иеленген қатынастарды көру.</span><span class="sxs-lookup"><span data-stu-id="b9a99-178">**View**: View system-created and inherited relationships.</span></span> 

## <a name="next-step"></a><span data-ttu-id="b9a99-179">Келесі қадам</span><span class="sxs-lookup"><span data-stu-id="b9a99-179">Next step</span></span>

<span data-ttu-id="b9a99-180">Жүйе мен реттелетін қарым-қатынастар енді оқшауланбаған бірнеше деректер көзі негізінде [сегменттер жасауға](segments.md) қолданылады.</span><span class="sxs-lookup"><span data-stu-id="b9a99-180">System and custom relationships are used to [create segments](segments.md) based on multiple data sources that are no longer siloed.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
