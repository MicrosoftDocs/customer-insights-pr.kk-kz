---
title: Тұтынушының бірыңғай профильдерін арттыру
description: Тұтынушының деректерін арттыру үшін мүмкіндіктерді пайдаланыңыз.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: c35e73b366fcd5db2ba5a757295ddda6db30efa0
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305255"
---
# <a name="enrichment-for-customer-profiles-preview"></a><span data-ttu-id="6ace2-103">Тұтынушы профильдерін арттыру (алдын ала қарау)</span><span class="sxs-lookup"><span data-stu-id="6ace2-103">Enrichment for customer profiles (preview)</span></span>

<span data-ttu-id="6ace2-104">Тұтынушы деректерін арттыру үшін Microsoft және басқа серіктестер сияқты көздердің деректерін пайдаланыңыз.</span><span class="sxs-lookup"><span data-stu-id="6ace2-104">Use data from sources like Microsoft and other partners to enrich your customer data.</span></span>

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Арттыру орталығының беті":::

<span data-ttu-id="6ace2-106">Аудитория түсініктерінде арттыру нұсқаларымен жұмыс істеу үшін **Деректер** > **Арттыру** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="6ace2-106">In audience insights, go to **Data** > **Enrichment** to work with enrichment options.</span></span>  

<span data-ttu-id="6ace2-107">Арттыруларды жасау немесе өңдеу үшін сізге үлескер немесе әкімші рұқсаттары қажет.</span><span class="sxs-lookup"><span data-stu-id="6ace2-107">You need to have Contributor or Administrator permissions to create or edit enrichments.</span></span> <span data-ttu-id="6ace2-108">Қосымша ақпаратты [Рұқсаттар](permissions.md) бөлімінен қараңыз.</span><span class="sxs-lookup"><span data-stu-id="6ace2-108">For more information, see [Permissions](permissions.md).</span></span>

<span data-ttu-id="6ace2-109">**Табу** қойыншасынан мына арттыруларды табасыз:</span><span class="sxs-lookup"><span data-stu-id="6ace2-109">On the **Discover** tab, you'll find the following enrichments:</span></span>

- <span data-ttu-id="6ace2-110">Microsoft корпорациясы ұсынатын [брендтер](enrichment-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="6ace2-110">[Brands](enrichment-microsoft.md) provided by Microsoft</span></span>
- <span data-ttu-id="6ace2-111">Microsoft корпорациясы ұсынатын [қызығушылықтар](enrichment-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="6ace2-111">[Interests](enrichment-microsoft.md) provided by Microsoft</span></span>
- <span data-ttu-id="6ace2-112">Microsoft ұсынған [нақтыланған мекенжайлар](enrichment-enhanced-addresses.md)</span><span class="sxs-lookup"><span data-stu-id="6ace2-112">[Enhanced addresses](enrichment-enhanced-addresses.md) provided by Microsoft</span></span>
- <span data-ttu-id="6ace2-113">Leadspace қамтамасыз еткен [компания деректері](enrichment-leadspace.md)</span><span class="sxs-lookup"><span data-stu-id="6ace2-113">[Company data](enrichment-leadspace.md) provided by Leadspace</span></span>
- <span data-ttu-id="6ace2-114">Experian компаниясы ұсынған [демографиялық деректер](enrichment-experian.md)</span><span class="sxs-lookup"><span data-stu-id="6ace2-114">[Demographics](enrichment-experian.md) provided by Experian</span></span>
- <span data-ttu-id="6ace2-115">HERE Technologies қамтамасыз еткен [орын деректері](enrichment-here.md)</span><span class="sxs-lookup"><span data-stu-id="6ace2-115">[Location data](enrichment-here.md) provided by HERE Technologies</span></span>
- <span data-ttu-id="6ace2-116">Қауіпсіз файл тасымалдау протоколы (SFTP) арқылы алынған [реттелетін деректер](enrichment-SFTP-custom-import.md)</span><span class="sxs-lookup"><span data-stu-id="6ace2-116">[Custom data](enrichment-SFTP-custom-import.md) through Secure File Transfer Protocol (SFTP)</span></span>

<span data-ttu-id="6ace2-117">**Менің арттыруларым** қойыншасында сіз теңшеген арттыруларды көруге және сипаттарын өңдеуге болады.</span><span class="sxs-lookup"><span data-stu-id="6ace2-117">On the **My enrichments** tab, you can see the enrichments you've configured and edit their properties.</span></span>

## <a name="manage-existing-enrichments"></a><span data-ttu-id="6ace2-118">Бар арттыруларды басқару</span><span class="sxs-lookup"><span data-stu-id="6ace2-118">Manage existing enrichments</span></span>

<span data-ttu-id="6ace2-119">Барлық конфигурацияланған толықтыруларды көру үшін **Менің толықтыруларым** қойыншасына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="6ace2-119">Go to the **My enrichments** tab to see all configured enrichments.</span></span> <span data-ttu-id="6ace2-120">Әрбір арттыру сол арттыру туралы қосымша ақпаратты қамтитын жол түрінде көрсетіледі.</span><span class="sxs-lookup"><span data-stu-id="6ace2-120">Each enrichment is represented as a row that includes additional information about the enrichment.</span></span>

<span data-ttu-id="6ace2-121">Қолжетімді опцияларды көру үшін арттыруды таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="6ace2-121">Select an enrichment to see the available options.</span></span> <span data-ttu-id="6ace2-122">Опцияларды көру үшін тізім элементінен көп нүктені (...) таңдауға болады.</span><span class="sxs-lookup"><span data-stu-id="6ace2-122">You can also select the ellipsis (...) on a list item to see the options.</span></span>

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Арттырулар тізіміндегі арттыруды басқару параметрлері":::

- <span data-ttu-id="6ace2-124">Арттырылған тұтынушы профильдерінің саны бар арттыру туралы мәліметтерді **Көру**.</span><span class="sxs-lookup"><span data-stu-id="6ace2-124">**View** enrichment details with the number of enriched customer profiles.</span></span>
- <span data-ttu-id="6ace2-125">Арттыру конфигурациясын **Өңдеу**.</span><span class="sxs-lookup"><span data-stu-id="6ace2-125">**Edit** the enrichment configuration.</span></span>
- <span data-ttu-id="6ace2-126">Тұтынушы профильдерін соңғы деректермен жаңарту үшін арттыру функциясын **іске қосыңыз**.</span><span class="sxs-lookup"><span data-stu-id="6ace2-126">**Run** the enrichment to update customer profiles with the latest data.</span></span>
- <span data-ttu-id="6ace2-127">Әр жоспарланған жаңартуда автоматты түрде жаңартылуын тоқтату үшін бар арттыруды **Өшіру**.</span><span class="sxs-lookup"><span data-stu-id="6ace2-127">**Deactivate** an existing enrichment to stop it from refreshing automatically with every scheduled refresh.</span></span> <span data-ttu-id="6ace2-128">Соңғы сәтті жаңартудың деректері қолжетімді бола береді.</span><span class="sxs-lookup"><span data-stu-id="6ace2-128">Data from the last successful refresh will continue to be available.</span></span> <span data-ttu-id="6ace2-129">Әр жоспарланған жаңартуда автоматты жаңартуды қайта бастау үшін белсенді емес арттыруды **Белсендіру**.</span><span class="sxs-lookup"><span data-stu-id="6ace2-129">**Activate** an inactive enrichment to restart automatic refreshing with every scheduled refresh.</span></span>
- <span data-ttu-id="6ace2-130">Арттыруды **жойыңыз**.</span><span class="sxs-lookup"><span data-stu-id="6ace2-130">**Delete** an enrichment.</span></span>

<span data-ttu-id="6ace2-131">Бірнеше арттыру функцияларын тізімнен таңдау арқылы бірден іске қосуға немесе өшіруге болады.</span><span class="sxs-lookup"><span data-stu-id="6ace2-131">You can run or deactivate multiple enrichments at once by selecting them in the list.</span></span> <span data-ttu-id="6ace2-132">Көру және өңдеу параметрлері жаппай әрекет ретінде қолжетімді емес және бір уақытта тек бір арттыру үшін жұмыс істейді.</span><span class="sxs-lookup"><span data-stu-id="6ace2-132">View and edit options aren't available as bulk action and only work for one enrichment at a time.</span></span>

## <a name="enrichments-and-connections"></a><span data-ttu-id="6ace2-133">Жақсартулар мен қосылымдар</span><span class="sxs-lookup"><span data-stu-id="6ace2-133">Enrichments and connections</span></span>

<span data-ttu-id="6ace2-134">Үшінші тарап жақсартулары [қосылымдарды](connections.md) пайдалану арқылы конфигурацияланады, оны әкімші тіркелгі деректерімен орнатады және деректерді тасымалдауға келісім береді.</span><span class="sxs-lookup"><span data-stu-id="6ace2-134">Third-party enrichments are configured using [connections](connections.md), which an administrator sets up with credentials and provides consent for data transfers.</span></span> <span data-ttu-id="6ace2-135">Әкімшілер мен салымшылар қосылымды жақсартуларды конфигурациялау үшін пайдалана алады.</span><span class="sxs-lookup"><span data-stu-id="6ace2-135">The connection can be used by administrators and contributors to configure enrichments.</span></span>  

## <a name="multiple-enrichments-of-the-same-type"></a><span data-ttu-id="6ace2-136">Бір түрдегі бірнеше жақсарту</span><span class="sxs-lookup"><span data-stu-id="6ace2-136">Multiple enrichments of the same type</span></span>

<span data-ttu-id="6ace2-137">Жақсартылатын нысан жақсарту конфигурациясы кезінде көрсетіледі, бұл сіздің профильдеріңіздің тек ішкі жиынтығын жақсартуға мүмкіндік береді.</span><span class="sxs-lookup"><span data-stu-id="6ace2-137">The entity to be enriched is specified during the enrichment configuration, which allows you to enrich only a subset of your profiles.</span></span> <span data-ttu-id="6ace2-138">Мысалы, белгілі бір сегмент үшін ғана деректерді толықтыру.</span><span class="sxs-lookup"><span data-stu-id="6ace2-138">For example, enrich data only for a specific segment.</span></span> <span data-ttu-id="6ace2-139">Бір түрдегі бірнеше жақсартуды конфигурациялауға және бір қосылымды қайта пайдалануға болады.</span><span class="sxs-lookup"><span data-stu-id="6ace2-139">You can configure several enrichments of the same type and reuse the same connection.</span></span> <span data-ttu-id="6ace2-140">Кейбір жақсартуларда жасалуы мүмкін бірдей түрдегі жақсарту санының шегі болады.</span><span class="sxs-lookup"><span data-stu-id="6ace2-140">Some enrichments will have limits to the number of enrichments of the same type that can be created.</span></span> <span data-ttu-id="6ace2-141">Шектеулер мен ағымдағы пайдалануды **Жақсарту** бетінде көруге болады.</span><span class="sxs-lookup"><span data-stu-id="6ace2-141">The limits and current use can be seen on the **Enrichment** page.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
