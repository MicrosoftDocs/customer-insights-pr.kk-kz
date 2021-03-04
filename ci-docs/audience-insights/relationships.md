---
title: Нысандар мен нысан жолдары арасындағы қатынастар
description: Бірнеше деректер көздерінен нысандар арасындағы қарым-қатынастарды жасап, басқарыңыз.
ms.date: 04/14/2020
ms.reviewer: mukeshpo
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 292da986faa7f62d8aa73ed7214075612178e2e1
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269888"
---
# <a name="relationships-between-entities"></a><span data-ttu-id="8831b-103">Нысандар арасындағы қарым-қатынастар</span><span class="sxs-lookup"><span data-stu-id="8831b-103">Relationships between entities</span></span>

<span data-ttu-id="8831b-104">Қарым-қатынастар нысандарды қосуға және нысандар бір нысаннан басқа нысанға сілтеме жасалуы мүмкін жалпы идентификаторды (бөгде кілт) бөліскен кезде деректердің графигін құруға көмектеседі.</span><span class="sxs-lookup"><span data-stu-id="8831b-104">Relationships help you connect entities and generate a graph of your data when entities share a common identifier (foreign key) that can be referenced from one entity to another.</span></span> <span data-ttu-id="8831b-105">Қосылған нысандар бірнеше деректер көзі негізінде сегменттер мен шараларды анықтауға мүмкіндік береді.</span><span class="sxs-lookup"><span data-stu-id="8831b-105">Connected entities enable you to define segments and measures based on multiple data sources.</span></span>

<span data-ttu-id="8831b-106">Қарым-қатынастардың екі түрі бар.</span><span class="sxs-lookup"><span data-stu-id="8831b-106">There are two types of relationships.</span></span> <span data-ttu-id="8831b-107">Автоматты түрде жасалған, өңделмейтін жүйе қарым-қатынастары және пайдаланушылар жасаған әрі теңшеген теңшелетін қарым-қатынастар.</span><span class="sxs-lookup"><span data-stu-id="8831b-107">Non-editable system relationships, which are created automatically, and custom relationships created and configured by users.</span></span>

<span data-ttu-id="8831b-108">Сәйкестендіру және біріктіру процестері барысында зерделі сәйкестендіру негізінде көріністерден бөлек жүйенің қарым-қатынастары жасалады.</span><span class="sxs-lookup"><span data-stu-id="8831b-108">During the match and merge processes, system relationships are created behind the scenes based on intelligent matching.</span></span> <span data-ttu-id="8831b-109">Бұл қарым-қатынастар Тұтынушы профилі жазбаларын басқа тиісті нысандар жазбаларымен байланыстыруға көмектеседі.</span><span class="sxs-lookup"><span data-stu-id="8831b-109">These relationships help relate the Customer Profile records with other corresponding entities' records.</span></span> <span data-ttu-id="8831b-110">Мына диаграммада соңғы Тұтынушы профилінің нысанын шығару үшін тұтынушы нысанын қосымша нысандармен сәйкестендірген кезде үш жүйе қарым-қатынасын жасау көрсетілген.</span><span class="sxs-lookup"><span data-stu-id="8831b-110">The following diagram illustrates the creation of three system relationships when the customer entity is matched with additional entities to produce the final Customer Profile entity.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="8831b-111">![Қарым-қатынас жасау](media/relationships-entities-merge.png "Қарым-қатынас жасау")</span><span class="sxs-lookup"><span data-stu-id="8831b-111">![Relationship creation](media/relationships-entities-merge.png "Relationship creation")</span></span>

- <span data-ttu-id="8831b-112">***CustomerToContact* қарым-қатынасы** Тұтынушы нысаны мен Контакт нысаны арасында жасалды.</span><span class="sxs-lookup"><span data-stu-id="8831b-112">***CustomerToContact* relationship** was created between the Customer entity and the Contact entity.</span></span> <span data-ttu-id="8831b-113">Тұтынушы нысаны Контакт нысанының **contactId** негізгі өрісімен байланыстыру үшін **Contact_contactId** негізгі өрісін алады.</span><span class="sxs-lookup"><span data-stu-id="8831b-113">The Customer entity gets the key field **Contact_contactId** to relate to the Contact entity key field **contactId**.</span></span>
- <span data-ttu-id="8831b-114">***CustomerToAccount* қарым-қатынасы** Тұтынушы нысаны мен Тіркелгі нысаны арасында жасалды.</span><span class="sxs-lookup"><span data-stu-id="8831b-114">***CustomerToAccount* relationship** was created between the Customer entity and the Account entity.</span></span> <span data-ttu-id="8831b-115">Тұтынушы нысаны Тіркелгі нысанының **accountId** негізгі өрісімен байланыстыру үшін **Account_accountId** негізгі өрісін алады.</span><span class="sxs-lookup"><span data-stu-id="8831b-115">The Customer entity gets the key field **Account_accountId** to relate to the Account entity key field **accountId**.</span></span>
- <span data-ttu-id="8831b-116">***CustomerToWebAccount* қарым-қатынасы** Тұтынушы нысаны мен Веб-тіркелгі нысаны арасында жасалды.</span><span class="sxs-lookup"><span data-stu-id="8831b-116">***CustomerToWebAccount* relationship** was created between the Customer entity and the WebAccount entity.</span></span> <span data-ttu-id="8831b-117">Тұтынушы нысаны Веб-тіркелгі нысанының **webaccountId** негізгі өрісімен байланыстыру үшін **WebAccount_webaccountId** негізгі өрісін алады.</span><span class="sxs-lookup"><span data-stu-id="8831b-117">The Customer entity gets the key field **WebAccount_webaccountId** to relate to the WebAccount entity key field **webaccountId**.</span></span>

## <a name="create-a-relationship"></a><span data-ttu-id="8831b-118">Қатынас жасау</span><span class="sxs-lookup"><span data-stu-id="8831b-118">Create a relationship</span></span>

<span data-ttu-id="8831b-119">**Қарым-қатынастар** бетінде теңшелетін қарым-қатынастарды анықтаңыз.</span><span class="sxs-lookup"><span data-stu-id="8831b-119">Define custom relationships on the **Relationships** page.</span></span> <span data-ttu-id="8831b-120">Әрбір қарым-қатынаста Бастапқы нысан (бөгде кілтті ұстайтын нысан) мен Мақсатты нысан (бастапқы нысанның бөгде кілті қаратылған нысан) бар.</span><span class="sxs-lookup"><span data-stu-id="8831b-120">Each relationship consists of a Source entity (the entity that holds the foreign key) and a Target entity (the entity that the source entity's foreign key points to).</span></span>

1. <span data-ttu-id="8831b-121">Аудитория түсініктерінде **Деректер** > **Қарым-қатынастар** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="8831b-121">In audience insights, go to **Data** > **Relationships**.</span></span>

2. <span data-ttu-id="8831b-122">**Жаңа қарым-қатынас** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="8831b-122">Select **New relationship**.</span></span>

3. <span data-ttu-id="8831b-123">**Қарым-қатынас қосу** тақтасында келесі ақпаратты көрсетіңіз:</span><span class="sxs-lookup"><span data-stu-id="8831b-123">In the **Add relationship** pane, provide the following information:</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="8831b-124">![Қарым-қатынас мәліметтерін енгізу](media/relationships-add.png "Қарым-қатынас мәліметтерін енгізу")</span><span class="sxs-lookup"><span data-stu-id="8831b-124">![Enter relationship details](media/relationships-add.png "Enter relationship details")</span></span>

   - <span data-ttu-id="8831b-125">**Қарым-қатынас аты**: қарым-қатынас мақсатына әсер ететін ат (мысалы, **AccountWebLogs**).</span><span class="sxs-lookup"><span data-stu-id="8831b-125">**Relationship name**: Name that reflects the purpose of the relationship (for example, **AccountWebLogs**).</span></span>
   - <span data-ttu-id="8831b-126">**Сипаттама**: қарым-қатынастар рөлінің сипаттамасы.</span><span class="sxs-lookup"><span data-stu-id="8831b-126">**Description**: Description of the relationship.</span></span>
   - <span data-ttu-id="8831b-127">**Бастапқы нысан**: қарым-қатынаста көз ретінде қолданылатын нысанды таңдаңыз (мысалы, веб-журнал).</span><span class="sxs-lookup"><span data-stu-id="8831b-127">**Source entity**: Select the entity that is used as a source in the relationship (for example, WebLog).</span></span>
   - <span data-ttu-id="8831b-128">**Элементтер саны**: бастапқы нысан жазбаларының элементтер санын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="8831b-128">**Cardinality**: Select the cardinality of the source entity records.</span></span> <span data-ttu-id="8831b-129">Мысалы, "көптеген" термині бір веб-тіркелгімен байланысты бірнеше веб-журнал жазбасын білдіреді.</span><span class="sxs-lookup"><span data-stu-id="8831b-129">For example, "many" means that multiple Weblog records are related to one WebAccount.</span></span>
   - <span data-ttu-id="8831b-130">**Бастапқы кілт өрісі**: бұл бастапқы нысанда бөгде кілт өрісін көрсетеді.</span><span class="sxs-lookup"><span data-stu-id="8831b-130">**Source key field**: This represents the foreign key field in the source entity.</span></span> <span data-ttu-id="8831b-131">Мысалы, веб-журналда **accountId** бөгде кілт өрісі бар.</span><span class="sxs-lookup"><span data-stu-id="8831b-131">For example, WebLog has the **accountId** foreign key field.</span></span>
   - <span data-ttu-id="8831b-132">**Мақсатты нысан**: қарым-қатынаста мақсат ретінде қолданылатын нысанды таңдаңыз (мысалы, веб-тіркелгі).</span><span class="sxs-lookup"><span data-stu-id="8831b-132">**Target entity**: Select the entity that is used as a target in the relationship (for example, WebAccount).</span></span>
   - <span data-ttu-id="8831b-133">**Мақсатты элементтер саны**: мақсатты нысан жазбаларының элементтер санын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="8831b-133">**Target cardinality**: Select the cardinality of the target entity records.</span></span> <span data-ttu-id="8831b-134">Мысалы, "бір" термині бір веб-тіркелгімен байланысты бірнеше веб-журнал жазбасын білдіреді.</span><span class="sxs-lookup"><span data-stu-id="8831b-134">For example, "one" means that multiple Weblog records are related to one WebAccount.</span></span>
   - <span data-ttu-id="8831b-135">**Мақсатты негізгі өріс**: бұл өріс мақсатты нысанның негізгі өрісін көрсетті.</span><span class="sxs-lookup"><span data-stu-id="8831b-135">**Target key field**: This field represents the key field of target entity.</span></span> <span data-ttu-id="8831b-136">Мысалы, веб-тіркелгіде **accountId** негізгі өрісі бар.</span><span class="sxs-lookup"><span data-stu-id="8831b-136">For example, WebAccount has the **accountId** key field.</span></span>

> [!NOTE]
> <span data-ttu-id="8831b-137">Тек көптеген-бір және бір-бір қарым-қатынастарына қолдау көрсетіледі.</span><span class="sxs-lookup"><span data-stu-id="8831b-137">Only many-to-one and one-to-one relationships are supported.</span></span> <span data-ttu-id="8831b-138">Екі көптеген-бір қарым-қатынасы және байланыс нысаны (бастапқы нысан мен мақсатты нысанды қосуға қолданылатын нысан) көмегімен көптеген-көптеген қарым-қатынастары жасалуы мүмкін.</span><span class="sxs-lookup"><span data-stu-id="8831b-138">Many-to-many relationships can be created using two many-to-one relationships and a link entity (an entity that is used to connect the source entity and the target entity).</span></span>

## <a name="delete-a-relationship"></a><span data-ttu-id="8831b-139">Қарым-қатынасты жою</span><span class="sxs-lookup"><span data-stu-id="8831b-139">Delete a relationship</span></span>

1. <span data-ttu-id="8831b-140">Аудитория түсініктерінде **Деректер** > **Қарым-қатынастар** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="8831b-140">In audience insights, go to **Data** > **Relationships**.</span></span>

2. <span data-ttu-id="8831b-141">Жою керек қарым-қатынастардың құсбелгілерін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="8831b-141">Select check boxes for the relationships you want to delete.</span></span>

3. <span data-ttu-id="8831b-142">**Қарым-қатынастар** кестесінің үстінен **Жою** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="8831b-142">Select **Delete** at the top of the **Relationships** table.</span></span>

4. <span data-ttu-id="8831b-143">Жоюды растаңыз.</span><span class="sxs-lookup"><span data-stu-id="8831b-143">Confirm your deletion.</span></span>

## <a name="next-step"></a><span data-ttu-id="8831b-144">Келесі қадам</span><span class="sxs-lookup"><span data-stu-id="8831b-144">Next step</span></span>

<span data-ttu-id="8831b-145">Жүйе мен теңшелетін қарым-қатынастар енді оқшауланбаған бірнеше деректер көзі негізінде сегменттерді жасауға қолданылады.</span><span class="sxs-lookup"><span data-stu-id="8831b-145">System and custom relationships are used to create segments based on multiple data sources that are no longer siloed.</span></span> <span data-ttu-id="8831b-146">Қосымша ақпаратты [Сегменттер](segments.md) бөлімінен қараңыз.</span><span class="sxs-lookup"><span data-stu-id="8831b-146">For more information, see [Segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]