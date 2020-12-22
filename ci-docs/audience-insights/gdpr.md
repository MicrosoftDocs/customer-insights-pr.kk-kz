---
title: GDPR бойынша деректер нысанының құқықтарына (DSR) қатысты сұраулар | Microsoft Docs
description: Dynamics 365 Customer Insights аудитория мәліметтері мүмкіндіктері үшін деректер субъектілеріне қатысты сұрауға жауап беріңіз.
ms.date: 05/14/2020
ms.reviewer: wimohabb
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: f276a73feca52023391ad92fbc84359921b85328
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406237"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a><span data-ttu-id="2d6f4-103">GDPR бойынша деректер субъектілерінің құқықтарына (DSR) қатысты сұраулар</span><span class="sxs-lookup"><span data-stu-id="2d6f4-103">Data Subject Rights (DSR) requests under GDPR</span></span>

## <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights-audience-insights-capability"></a><span data-ttu-id="2d6f4-104">Dynamics 365 Customer Insights аудитория мәліметтері мүмкіндіктері үшін GDPR деректер субъектілерін жою сұрауларына жауап беру</span><span class="sxs-lookup"><span data-stu-id="2d6f4-104">Responding to GDPR data subject delete requests for Dynamics 365 Customer Insights audience insights capability</span></span>

<span data-ttu-id="2d6f4-105">Ұйымның тұтынушы деректерінен жеке деректерді "жою құқығы" Деректерді қорғау бойынша жалпы регламенттің (GDPR) негізгі қорғанысы болып табылады.</span><span class="sxs-lookup"><span data-stu-id="2d6f4-105">The “right to erasure” by the removal of personal data from an organization’s customer data is a key protection in the General Data Protection Regulation (GDPR).</span></span> <span data-ttu-id="2d6f4-106">Жеке деректерді жою процесі аудит журналының ақпаратын қоспағанда, барлық жеке деректерді және жүйемен жасалған журналдарды жоюды қамтиды.</span><span class="sxs-lookup"><span data-stu-id="2d6f4-106">Removing personal data includes removing all personal data and system-generated logs, except audit log information.</span></span>

### <a name="manage-data-subject-delete-requests"></a><span data-ttu-id="2d6f4-107">Деректер нысанын жою сұрауларын басқару</span><span class="sxs-lookup"><span data-stu-id="2d6f4-107">Manage data subject delete requests</span></span>

<span data-ttu-id="2d6f4-108">Аудитория мәліметтері белгілі бір тұтынушының немесе пайдаланушының жеке деректерін жою үшін мына өнімдегі тәжірибелерді ұсынады:</span><span class="sxs-lookup"><span data-stu-id="2d6f4-108">Audience insights offers the following in-product experiences to delete personal data for a specific customer or user:</span></span>

- <span data-ttu-id="2d6f4-109">**Тұтынушы деректерінің жою сұрауларын басқару**: Customer Insights ішіндегі тұтынушы деректері бастапқы сыртқы деректер көздерінен Customer Insights жүйесіне қабылданады.</span><span class="sxs-lookup"><span data-stu-id="2d6f4-109">**Manage delete requests for customer data**: Customer data in Customer Insights is ingested from original data sources external to Customer Insights.</span></span> <span data-ttu-id="2d6f4-110">Барлық GDPR жою сұраулары бастапқы деректер көзінде орындалуы қажет.</span><span class="sxs-lookup"><span data-stu-id="2d6f4-110">All GDPR delete requests must be performed in the original data source.</span></span>
- <span data-ttu-id="2d6f4-111">**Customer Insights пайдаланушы деректерін жою сұрауларын басқару**: Customer Insights жасаған пайдаланушыларға арналған деректер.</span><span class="sxs-lookup"><span data-stu-id="2d6f4-111">**Manage delete requests for Customer Insights user data**: Data for users is created by Customer Insights.</span></span> <span data-ttu-id="2d6f4-112">Барлық GDPR жою сұраулары Customer Insights бағдарламасында орындалуы қажет.</span><span class="sxs-lookup"><span data-stu-id="2d6f4-112">All GDPR delete requests must be performed in Customer Insights.</span></span>

#### <a name="manage-delete-requests-for-customer-data"></a><span data-ttu-id="2d6f4-113">Тұтынушы деректерін жою сұрауларын басқару</span><span class="sxs-lookup"><span data-stu-id="2d6f4-113">Manage delete requests for customer data</span></span>

<span data-ttu-id="2d6f4-114">Customer Insights әкімші дереккөзден жойылған тұтынушы деректерін жою үшін осы қадамдарды орындай алады:</span><span class="sxs-lookup"><span data-stu-id="2d6f4-114">A Customer Insights admin can follow these steps to remove customer data that was deleted in the data source:</span></span>

1. <span data-ttu-id="2d6f4-115">Dynamics 365 Customer Insights жүйесіне кіріңіз.</span><span class="sxs-lookup"><span data-stu-id="2d6f4-115">Sign in to Dynamics 365 Customer Insights.</span></span>
2. <span data-ttu-id="2d6f4-116">Аудитория мәліметтерінде **Деректер** > **Деректер көздері** тармағына өтіңіз</span><span class="sxs-lookup"><span data-stu-id="2d6f4-116">In audience insights, go to **Data** > **Data sources**</span></span>
3. <span data-ttu-id="2d6f4-117">Жойылған тұтынушы деректерінен тұратын тізімдегі әрбір дереккөз үшін:</span><span class="sxs-lookup"><span data-stu-id="2d6f4-117">For each data source in the list that contains deleted customer data:</span></span>
   1. <span data-ttu-id="2d6f4-118">(...) параметрін таңдап, одан кейін **Жаңарту** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="2d6f4-118">Select (...) and then select **Refresh**.</span></span>
   2. <span data-ttu-id="2d6f4-119">**Күй** астынан деректер көзі күйін тексеріңіз.</span><span class="sxs-lookup"><span data-stu-id="2d6f4-119">Check the status of the data source under **Status**.</span></span> <span data-ttu-id="2d6f4-120">Құсбелгі жаңарту сәтті болғанын білдіреді.</span><span class="sxs-lookup"><span data-stu-id="2d6f4-120">A check mark means the refresh was successful.</span></span> <span data-ttu-id="2d6f4-121">Ескерту үшбұрышы бірдеңе дұрыс болмағанын білдіреді.</span><span class="sxs-lookup"><span data-stu-id="2d6f4-121">A warning triangle means something went wrong.</span></span> <span data-ttu-id="2d6f4-122">Ескерту үшбұрышы көрсетілсе, D365CI@microsoft.com торабына хабарласыңыз.</span><span class="sxs-lookup"><span data-stu-id="2d6f4-122">If a warning triangle is displayed, contact D365CI@microsoft.com.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="2d6f4-123">![GDPR шешімін қолдану тұтынушы деректерінің сұрауларын жояды](media/gdpr-data-sources.png "GDPR шешімін қолдану тұтынушы деректерінің сұрауларын жояды")</span><span class="sxs-lookup"><span data-stu-id="2d6f4-123">![Handling GDPR delete requests for customer data](media/gdpr-data-sources.png "Handling GDPR delete requests for customer data")</span></span>

#### <a name="manage-delete-requests-for-user-data"></a><span data-ttu-id="2d6f4-124">Пайдаланушы деректерін жою сұрауларын басқару</span><span class="sxs-lookup"><span data-stu-id="2d6f4-124">Manage delete requests for user data</span></span>

<span data-ttu-id="2d6f4-125">Customer Insights әкімшісі Customer Insights пайдаланушысы деректерін жою үшін осы қадамдарды орындай алады:</span><span class="sxs-lookup"><span data-stu-id="2d6f4-125">A Customer Insights admin can follow these steps to delete Customer Insights user data:</span></span>

1. <span data-ttu-id="2d6f4-126">Dynamics 365 Customer Insights жүйесіне кіріңіз.</span><span class="sxs-lookup"><span data-stu-id="2d6f4-126">Sign in to Dynamics 365 Customer Insights.</span></span>
2. <span data-ttu-id="2d6f4-127">Аудитория мәліметтерінде **Әкімші** > **Рұқсаттар** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="2d6f4-127">In audience insights, go to **Admin** > **Permissions**.</span></span>
3. <span data-ttu-id="2d6f4-128">Жою керек пайдаланушы құсбелгісін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="2d6f4-128">Select the check box for the user you want to delete.</span></span>
4. <span data-ttu-id="2d6f4-129">**Жою** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="2d6f4-129">Select **Remove**.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="2d6f4-130">![Пайдаланушы деректері үшін GDPR жою сұрауларын басқару](media/gdpr-permissions.png "Пайдаланушы деректері үшін GDPR жою сұрауларын басқару")</span><span class="sxs-lookup"><span data-stu-id="2d6f4-130">![Handling GDPR delete requests foruser data](media/gdpr-permissions.png "Handling GDPR delete requests for user data")</span></span>

## <a name="responding-to-gdpr-data-subject-export-requests"></a><span data-ttu-id="2d6f4-131">GDPR деректер субъектілерін экспорттау сұрауларына жауап беру</span><span class="sxs-lookup"><span data-stu-id="2d6f4-131">Responding to GDPR data subject export requests</span></span>

<span data-ttu-id="2d6f4-132">Деректерді қорғау бойынша жалпы регламент (GDPR) бойынша сізбен серіктес құру міндеттемесінің бөлігі ретінде дайындыққа көмектесетін құжатты әзірледік.</span><span class="sxs-lookup"><span data-stu-id="2d6f4-132">As part of our commitment to partner with you on your journey to the General Data Protection Regulation (GDPR), we’ve developed documentation to help you prepare.</span></span> <span data-ttu-id="2d6f4-133">Бұл құжаттамада аудитория мәліметтерін пайдаланған кезде GDPR сәйкестігіне қолдау көрсету үшін бүгін жасауға болатын қадамдар сипатталған.</span><span class="sxs-lookup"><span data-stu-id="2d6f4-133">This documentation describes steps you can take today to support GDPR compliance when using audience insights.</span></span>

### <a name="manage-export-and-view-requests"></a><span data-ttu-id="2d6f4-134">Экспорттау және көру сұрауларын басқару</span><span class="sxs-lookup"><span data-stu-id="2d6f4-134">Manage export and view requests</span></span>

<span data-ttu-id="2d6f4-135">Деректерді тасымалдау құқығы деректер субъектілеріне басқа деректер контроллеріне берілуі мүмкін электрондық пішімдегі ("құрылымдалған, жиі қолданылатын, машинамен оқылатын және өзара жұмыс істейтін пішім" ретінде анықталған) жеке деректердің көшірмесін сұрауға мүмкіндік береді.</span><span class="sxs-lookup"><span data-stu-id="2d6f4-135">The right of data portability allows data subjects to request a copy of their personal data in an electronic format (a “structured, commonly used, machine readable, and interoperable format”) that can be transmitted to another data controller.</span></span>

#### <a name="export-customer-data-tenant-admin"></a><span data-ttu-id="2d6f4-136">Тұтынушы деректерін экспорттау (қатысушы әкімшісі)</span><span class="sxs-lookup"><span data-stu-id="2d6f4-136">Export customer data (tenant admin)</span></span>

<span data-ttu-id="2d6f4-137">Қатысушы әкімшісі деректерді экспорттау үшін мына қадамдарды орындай алуы мүмкін:</span><span class="sxs-lookup"><span data-stu-id="2d6f4-137">A tenant administrator can follow these steps to export data:</span></span>

1. <span data-ttu-id="2d6f4-138">Сұрауда тұтынушының электрондық пошта мекенжайын көрсетіп, D365CI@microsoft.com мекенжайына электрондық хабар жіберіңіз.</span><span class="sxs-lookup"><span data-stu-id="2d6f4-138">Send an email to D365CI@microsoft.com specifying the customer’s email address in the request.</span></span> <span data-ttu-id="2d6f4-139">Customer Insights тобы деректерді экспорттау растауын сұрайтын тіркелген қатысушы әкімшісі электрондық пошта мекенжайына электрондық хабарды жібереді.</span><span class="sxs-lookup"><span data-stu-id="2d6f4-139">The Customer Insights team will send an email to the registered tenant admin email address, asking for confirmation to export data.</span></span>
2. <span data-ttu-id="2d6f4-140">Сұралған тұтынушыға деректерді экспорттау үшін растауды мақұлдаңыз.</span><span class="sxs-lookup"><span data-stu-id="2d6f4-140">Acknowledge the confirmation to export the data for the requested customer.</span></span>
3. <span data-ttu-id="2d6f4-141">Қатысушы әкімшісінің электрондық пошта мекенжайы арқылы экспортталған деректерді алыңыз.</span><span class="sxs-lookup"><span data-stu-id="2d6f4-141">Receive the exported data through the tenant admin email address.</span></span>

#### <a name="export-user-data-tenant-admin"></a><span data-ttu-id="2d6f4-142">Пайдаланушы деректерін экспорттау (қатысушы әкімші)</span><span class="sxs-lookup"><span data-stu-id="2d6f4-142">Export user data (tenant admin)</span></span>

1. <span data-ttu-id="2d6f4-143">Сұрауда пайдаланушының электрондық пошта мекенжайын көрсетіп, D365CI@microsoft.com мекенжайына электрондық хабар жіберіңіз.</span><span class="sxs-lookup"><span data-stu-id="2d6f4-143">Send an email to D365CI@microsoft.com specifying the user’s email address in the request.</span></span> <span data-ttu-id="2d6f4-144">Customer Insights тобы деректерді экспорттау растауын сұрайтын тіркелген қатысушы әкімшісі электрондық пошта мекенжайына электрондық хабарды жібереді.</span><span class="sxs-lookup"><span data-stu-id="2d6f4-144">The Customer Insights team will send an email to the registered tenant admin email address, asking for confirmation to export data.</span></span>
2. <span data-ttu-id="2d6f4-145">Сұралған пайдаланушыға деректерді экспорттау үшін растауды мақұлдаңыз.</span><span class="sxs-lookup"><span data-stu-id="2d6f4-145">Acknowledge the confirmation to export the data for the requested user.</span></span>
3. <span data-ttu-id="2d6f4-146">Қатысушы әкімшісінің электрондық пошта мекенжайы арқылы экспортталған деректерді алыңыз.</span><span class="sxs-lookup"><span data-stu-id="2d6f4-146">Receive the exported data through the tenant admin email address.</span></span>
