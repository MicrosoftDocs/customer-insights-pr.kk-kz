---
title: Customer Insights бағдарламасындағы басқа қызметтерге қосылымдар.
description: Деректерді басқа қызметтермен бөлісіңіз.
ms.date: 04/09/2021
ms.reviewer: nikeller
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 17e04b243e9b3d4375c86f5a890a18be35956835
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304979"
---
# <a name="connections-preview-overview"></a><span data-ttu-id="9b6d8-103">Қосылымдарға (алдын ала қарау нұсқасы) шолу</span><span class="sxs-lookup"><span data-stu-id="9b6d8-103">Connections (preview) overview</span></span>

<span data-ttu-id="9b6d8-104">Қосылымдар — бұл Customer Insights бағдарламасымен және бағдарламасынан деректерді бөлісуге мүмкіндік беретін кілт.</span><span class="sxs-lookup"><span data-stu-id="9b6d8-104">Connections are the key to enable data sharing to and from Customer Insights.</span></span> <span data-ttu-id="9b6d8-105">Әрбір қосылым белгілі бір қызметпен деректер алмасуды орнатады.</span><span class="sxs-lookup"><span data-stu-id="9b6d8-105">Each connection establishes data sharing with a specific service.</span></span> <span data-ttu-id="9b6d8-106">Қосылымдар — бұл [үшінші тарап жақсартуларын конфигурациялау](enrichment-hub.md) және [экспорттауды конфигурациялаудың](export-destinations.md) негізі.</span><span class="sxs-lookup"><span data-stu-id="9b6d8-106">Connections are the foundation to [configure third-party enrichments](enrichment-hub.md) and [configure exports](export-destinations.md).</span></span> <span data-ttu-id="9b6d8-107">Бір қосылымды бірнеше рет қолдануға болады.</span><span class="sxs-lookup"><span data-stu-id="9b6d8-107">The same connection can be used multiple times.</span></span> <span data-ttu-id="9b6d8-108">Мысалы, Dynamics 365 Marketing бағдарламасына бір қосылым бірнеше маман үшін жұмыс істейді және бір Leadspace қосылымын бірнеше жақсарту үшін қолдануға болады.</span><span class="sxs-lookup"><span data-stu-id="9b6d8-108">For example, one connection to Dynamics 365 Marketing works for multiple exports and one Leadspace connection can be used for several enrichments.</span></span>

<span data-ttu-id="9b6d8-109">Жаңа қосылымдар жасау үшін **Әкімші** > **Қосылымдар** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="9b6d8-109">Go to **Admin** > **Connections** to create and view connections.</span></span>

<span data-ttu-id="9b6d8-110">**Қосылымдар** қойыншасы барлық белсенді қосылымдарды көрсетеді.</span><span class="sxs-lookup"><span data-stu-id="9b6d8-110">The **Connections** tab shows you all active connections.</span></span> <span data-ttu-id="9b6d8-111">Тізімде әр қосылым үшін жол көрсетілген.</span><span class="sxs-lookup"><span data-stu-id="9b6d8-111">The list shows a row for each connection.</span></span> 

<span data-ttu-id="9b6d8-112">Жылдам шолуды, сипаттаманы алыңыз және **Анықтау** қойыншасындағы әр кеңейтімділік опциясымен не істей алатыныңызды біліңіз.</span><span class="sxs-lookup"><span data-stu-id="9b6d8-112">Get a quick overview, description, and find out what you can do with each extensibility option on the **Discover** tab.</span></span>

### <a name="exports"></a><span data-ttu-id="9b6d8-113">Экспорттаулар</span><span class="sxs-lookup"><span data-stu-id="9b6d8-113">Exports</span></span>

<span data-ttu-id="9b6d8-114">Жаңа қосылымдарды тек әкімшілер конфигурациялай алады, бірақ олар салымшыларға бұрыннан бар қосылымдарды пайдалануға рұқсат бере алады.</span><span class="sxs-lookup"><span data-stu-id="9b6d8-114">Only administrators can configure new connections but they can grant access to contributors to use existing connections.</span></span> <span data-ttu-id="9b6d8-115">Әкімшілер деректердің қайда кететінін басқарады, салымшылар өздерінің қажеттіліктеріне сәйкес пайдалы жүктеме мен жиілікті анықтайды.</span><span class="sxs-lookup"><span data-stu-id="9b6d8-115">Administrators control where data can go, contributors define the payload and frequency fitting their needs.</span></span> <span data-ttu-id="9b6d8-116">Қосымша ақпарат алу үшін [Салымшыларға экспорттау үшін қосылымды пайдалануға рұқсат беру](#allow-contributors-to-use-a-connection-for-exports) бөлімін қараңыз.</span><span class="sxs-lookup"><span data-stu-id="9b6d8-116">For more information, see [Allow contributors to use a connection for exports](#allow-contributors-to-use-a-connection-for-exports).</span></span>

### <a name="enrichments"></a><span data-ttu-id="9b6d8-117">Арттырулар</span><span class="sxs-lookup"><span data-stu-id="9b6d8-117">Enrichments</span></span>

<span data-ttu-id="9b6d8-118">Жаңа қосылымдарды тек әкімшілер ғана конфигурациялай алады, бірақ жасалған қосылымдар әкімшілерге де, салымшыларға да әрқашан қолжетімді.</span><span class="sxs-lookup"><span data-stu-id="9b6d8-118">Only administrators can configure new connections but the created connections are always available to both administrators and contributors.</span></span> <span data-ttu-id="9b6d8-119">Әкімшілер тіркелгі деректерін басқарады және деректерді тасымалдауға келісім береді.</span><span class="sxs-lookup"><span data-stu-id="9b6d8-119">Administrators manage credentials and give consent to data transfers.</span></span> <span data-ttu-id="9b6d8-120">Содан кейін әкімшілер де, салымшылар да қосылымдарды жақсарту үшін қолдана алады.</span><span class="sxs-lookup"><span data-stu-id="9b6d8-120">The connections can then be used for enrichments by both administrators and contributors.</span></span>

## <a name="add-a-new-connection"></a><span data-ttu-id="9b6d8-121">Жаңа қосылым қосу</span><span class="sxs-lookup"><span data-stu-id="9b6d8-121">Add a new connection</span></span>

<span data-ttu-id="9b6d8-122">Қосылымдарды қосу үшін сізде [әкімші рұқсаттары](permissions.md) болуы керек.</span><span class="sxs-lookup"><span data-stu-id="9b6d8-122">To add connections, you need to have [administrator permissions](permissions.md).</span></span> <span data-ttu-id="9b6d8-123">Егер сіз басқа Microsoft қызметтеріне қосылсаңыз, екі қызмет те бір ұйымда болады деп ойлаймыз.</span><span class="sxs-lookup"><span data-stu-id="9b6d8-123">If you connect to other Microsoft services, we assume both services are in the same organization.</span></span>

1. <span data-ttu-id="9b6d8-124">**Әкімші** > **Қосылымдар (алдын ала қарау нұсқасы)** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="9b6d8-124">Go to **Admin** > **Connections (preview)**.</span></span>

1. <span data-ttu-id="9b6d8-125">**Қосылымдар** қойыншасына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="9b6d8-125">Go to the **Connections** tab.</span></span>

1. <span data-ttu-id="9b6d8-126">Жаңа қосылым жасау үшін **Жаңа қосылым** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="9b6d8-126">Select **Add connection** to create a new connection.</span></span> <span data-ttu-id="9b6d8-127">Ашылмалы мәзірден қандай қосылым түрін жасағыңыз келетінін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="9b6d8-127">Choose from the dropdown menu what type of connection you want to create.</span></span>

1. <span data-ttu-id="9b6d8-128">**Қосылымды орнату** тақтасында қажетті мәліметтерді көрсетіңіз.</span><span class="sxs-lookup"><span data-stu-id="9b6d8-128">In the **Set up connection** pane, provide the required details.</span></span> 
   1. <span data-ttu-id="9b6d8-129">**Көрсетілетін атау** және қосылым түрі қосылымды сипаттайды.</span><span class="sxs-lookup"><span data-stu-id="9b6d8-129">The **Display name** and the type of the connection describe a connection.</span></span> <span data-ttu-id="9b6d8-130">Осы қосылымның мақсатын түсіндіретін атауды таңдауды ұсынамыз.</span><span class="sxs-lookup"><span data-stu-id="9b6d8-130">We recommend choosing a name that explains the purpose and target of this connection.</span></span>
   1. <span data-ttu-id="9b6d8-131">Нақты өрістер сіз қандай қызметке қосылатындығыңызға байланысты.</span><span class="sxs-lookup"><span data-stu-id="9b6d8-131">The exact fields depend on what service you are connecting to.</span></span> <span data-ttu-id="9b6d8-132">Белгілі бір қосылым түрі туралы мәліметтерді мақсатты қызмет туралы мақаладан білуге болады.</span><span class="sxs-lookup"><span data-stu-id="9b6d8-132">You can learn about details of a specific connection type in the article about the target service.</span></span>

1. <span data-ttu-id="9b6d8-133">Қосылым жасау үшін **Сақтау** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="9b6d8-133">To create the connection, select **Save**.</span></span>

<span data-ttu-id="9b6d8-134">**Анықтау** қойыншасындағы қатардағы **Орнату** параметрін таңдауға болады,</span><span class="sxs-lookup"><span data-stu-id="9b6d8-134">You can also select **Set up** on a tile on the **Discover** tab.</span></span>

### <a name="allow-contributors-to-use-a-connection-for-exports"></a><span data-ttu-id="9b6d8-135">Салымшыларға экспорттау үшін қосылымды пайдалануға рұқсат беру</span><span class="sxs-lookup"><span data-stu-id="9b6d8-135">Allow contributors to use a connection for exports</span></span>

<span data-ttu-id="9b6d8-136">Экспорттау қосылымын орнату немесе өңдеу кезінде сіз [экспорттауды](export-destinations.md) анықтауға арналған осы арнайы қосылымды пайдалану қай пайдаланушыларға рұқсат етілетінін таңдайсыз.</span><span class="sxs-lookup"><span data-stu-id="9b6d8-136">When setting up or editing an export connection, you choose which users are allowed to use this specific connection to define [exports](export-destinations.md).</span></span> <span data-ttu-id="9b6d8-137">Әдепкі бойынша, қосылым әкімші рөлі бар пайдаланушылар үшін қолжетімді.</span><span class="sxs-lookup"><span data-stu-id="9b6d8-137">By default a connection is available to users with an administrator role.</span></span> <span data-ttu-id="9b6d8-138">Бұл параметрді **Бұл қосылымды кім қолдана алатынын таңдау** бөлімінде өзгертуге болады және салымшы рөлі бар пайдаланушыларға осы қосылымды пайдалануға мүмкіндік береді.</span><span class="sxs-lookup"><span data-stu-id="9b6d8-138">You can change this setting under **Choose who can use this connection** and allow users with contributor role to use this connection.</span></span>

- <span data-ttu-id="9b6d8-139">Салымшылар қосылымды көріп немесе өңдей алмайды.</span><span class="sxs-lookup"><span data-stu-id="9b6d8-139">Contributors won't be able to view or edit the connection.</span></span> <span data-ttu-id="9b6d8-140">Олар экспорттау жасау кезінде тек көрсетілетін атауын және оның түрін көреді.</span><span class="sxs-lookup"><span data-stu-id="9b6d8-140">They will only see the display name and its type when creating an export.</span></span>
- <span data-ttu-id="9b6d8-141">Қосылымды бөлісу арқылы сіз салымшыларға қосылымды пайдалануға рұқсат бересіз.</span><span class="sxs-lookup"><span data-stu-id="9b6d8-141">By sharing a connection, you allow contributors to use a connection.</span></span> <span data-ttu-id="9b6d8-142">Салымшылар экспорттауды орнатқан кезде бөлісілген қосылымдарды көреді.</span><span class="sxs-lookup"><span data-stu-id="9b6d8-142">Contributors will see shared connections when they set up exports.</span></span> <span data-ttu-id="9b6d8-143">Олар осы қосылымды қолданатын кез келген экспорттауды басқара алады.</span><span class="sxs-lookup"><span data-stu-id="9b6d8-143">They can manage every export that uses this specific connection.</span></span>
- <span data-ttu-id="9b6d8-144">Сіз бұл параметрді салымшылар анықтаған экспорттауды сақтай отырып өзгерте аласыз.</span><span class="sxs-lookup"><span data-stu-id="9b6d8-144">You can change this setting while keeping the exports that have already been defined by contributors.</span></span>

## <a name="edit-a-connection"></a><span data-ttu-id="9b6d8-145">Қосылымды өңдеу</span><span class="sxs-lookup"><span data-stu-id="9b6d8-145">Edit a connection</span></span>

1. <span data-ttu-id="9b6d8-146">**Әкімші** > **Қосылымдар (алдын ала қарау нұсқасы)** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="9b6d8-146">Go to **Admin** > **Connections (preview)**.</span></span>

1. <span data-ttu-id="9b6d8-147">**Қосылымдар** қойыншасына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="9b6d8-147">Go to the **Connections** tab.</span></span>

1. <span data-ttu-id="9b6d8-148">Өңдеу керек қосылым үшін тік көп нүктені таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="9b6d8-148">Select the vertical ellipsis for the connection you want to edit.</span></span>

1. <span data-ttu-id="9b6d8-149">**Өңдеу** пәрменін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="9b6d8-149">Select **Edit**.</span></span>

1. <span data-ttu-id="9b6d8-150">Жаңарту керек мәндерді таңдаңыз және **Сақтау** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="9b6d8-150">Change the values you want to update and select **Save**.</span></span>

## <a name="remove-a-connection"></a><span data-ttu-id="9b6d8-151">Қосылымды жою</span><span class="sxs-lookup"><span data-stu-id="9b6d8-151">Remove a connection</span></span>

<span data-ttu-id="9b6d8-152">Егер сіз жоятын қосылым жақсарту немесе экспорттауда пайдаланылса, алдымен оларды ажырату немесе жою қажет.</span><span class="sxs-lookup"><span data-stu-id="9b6d8-152">If the connection you are removing is used by enrichments or exports, you first need to detach or remove them.</span></span> <span data-ttu-id="9b6d8-153">Жою диалогтік терезесі сізді тиісті жақсарту немесе экспорттауға бағыттайды.</span><span class="sxs-lookup"><span data-stu-id="9b6d8-153">The remove dialog will guide you to the relevant enrichments or exports.</span></span> 

<span data-ttu-id="9b6d8-154">Ажыратылған жақсарту және экспорттау белсенді емес болады.</span><span class="sxs-lookup"><span data-stu-id="9b6d8-154">Detached enrichments and exports become inactive.</span></span> <span data-ttu-id="9b6d8-155">Оларды [Жақсартулар](enrichment-hub.md) немесе [Экспорттаулар](export-destinations.md) бетінде оларға басқа қосылым қосу арқылы қайта белсендіруге болады.</span><span class="sxs-lookup"><span data-stu-id="9b6d8-155">You reactivate them by adding another connection to them on the [Enrichments](enrichment-hub.md) or [Exports](export-destinations.md) page.</span></span>

1. <span data-ttu-id="9b6d8-156">**Әкімші** > **Қосылымдар (алдын ала қарау нұсқасы)** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="9b6d8-156">Go to **Admin** > **Connections (preview)**.</span></span>

1. <span data-ttu-id="9b6d8-157">**Қосылымдар** қойыншасына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="9b6d8-157">Go to the **Connections** tab.</span></span>

1. <span data-ttu-id="9b6d8-158">Жою керек қосылым үшін тік көп нүктені таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="9b6d8-158">Select the vertical ellipsis for the connection you want to remove.</span></span>

1. <span data-ttu-id="9b6d8-159">Ашылмалы тізімнен **Алып тастау** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="9b6d8-159">Select **Remove** from the dropdown menu.</span></span> <span data-ttu-id="9b6d8-160">Растау диалогтік терезесі пайда болады.</span><span class="sxs-lookup"><span data-stu-id="9b6d8-160">A confirmation dialog appears.</span></span>

   1. <span data-ttu-id="9b6d8-161">Егер осы қосылымды қолданатын жақсарту немесе экспорттау болса, қосылымның не қолданып жатқанын көру үшін түймешікті таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="9b6d8-161">If there are enrichments or exports using this connection, select the button to see what's using the connection.</span></span>
      - <span data-ttu-id="9b6d8-162">**Экспорттаулар:** қосылымды жою үшін экспорттауды не алып тастауды, не ажыратуды таңдауға болады.</span><span class="sxs-lookup"><span data-stu-id="9b6d8-162">**Exports:** You can choose to either remove or disconnect the exports to be able to remove the connection.</span></span> <span data-ttu-id="9b6d8-163">Экспорттауды ажырату үшін әкімшілер **Ажырату** әрекетін пайдалана алады.</span><span class="sxs-lookup"><span data-stu-id="9b6d8-163">To disconnect an export, administrators can use the **Disconnect** action.</span></span> <span data-ttu-id="9b6d8-164">Бұл әрекет жеке және бірнеше таңдалған экспорттау үшін қолжетімді.</span><span class="sxs-lookup"><span data-stu-id="9b6d8-164">This action is available for individual and multiple selected exports.</span></span> <span data-ttu-id="9b6d8-165">Ажырату арқылы сіз экспорттау конфигурациясын сақтайсыз, бірақ оған басқа қосылым қосылмайынша ол іске қосылмайды.</span><span class="sxs-lookup"><span data-stu-id="9b6d8-165">By disconnecting you keep the export config, but it won't be run until another connection is added to it.</span></span>
      - <span data-ttu-id="9b6d8-166">**Жақсартулар:** қосылымды жою үшін жақсартуларды не алып тастауды, не ажыратуды таңдауға болады.</span><span class="sxs-lookup"><span data-stu-id="9b6d8-166">**Enrichments:** You can choose to either remove or deactivate the enrichments to be able to remove the connection.</span></span> 
   1. <span data-ttu-id="9b6d8-167">Қосылымда ешқандай тәуелділік қалмаған кезде **Әкімші** > **Қосылымдар** тармағына оралыңыз және қосылымды қайтадан алып тастап көріңіз.</span><span class="sxs-lookup"><span data-stu-id="9b6d8-167">Once the connection has no more dependencies, go back to **Admin** > **Connections** and try removing the connection again.</span></span>

1. <span data-ttu-id="9b6d8-168">Жоюды растау үшін **Жою** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="9b6d8-168">To confirm the deletion, select **Remove**.</span></span>

