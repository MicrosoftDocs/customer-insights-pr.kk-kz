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
ms.openlocfilehash: 10c338b89a6f9971912d05986c105cba1221b01b
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896012"
---
# <a name="enrichment-for-customer-profiles-preview"></a><span data-ttu-id="13f0d-103">Тұтынушы профильдерін арттыру (алдын ала қарау)</span><span class="sxs-lookup"><span data-stu-id="13f0d-103">Enrichment for customer profiles (preview)</span></span>

<span data-ttu-id="13f0d-104">Тұтынушы деректерін арттыру үшін Microsoft және басқа серіктестер сияқты көздердің деректерін пайдаланыңыз.</span><span class="sxs-lookup"><span data-stu-id="13f0d-104">Use data from sources like Microsoft and other partners to enrich your customer data.</span></span>

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Арттыру орталығының беті":::

<span data-ttu-id="13f0d-106">Аудитория түсініктерінде арттыру нұсқаларымен жұмыс істеу үшін **Деректер** > **Арттыру** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="13f0d-106">In audience insights, go to **Data** > **Enrichment** to work with enrichment options.</span></span>    
<span data-ttu-id="13f0d-107">Арттыруларды жасау немесе өңдеу үшін сізге үлескер немесе әкімші рұқсаттары қажет.</span><span class="sxs-lookup"><span data-stu-id="13f0d-107">You need to have Contributor or Administrator permissions to create or edit enrichments.</span></span> <span data-ttu-id="13f0d-108">Қосымша ақпаратты [Рұқсаттар](permissions.md) бөлімінен қараңыз.</span><span class="sxs-lookup"><span data-stu-id="13f0d-108">For more information, see [Permissions](permissions.md).</span></span>

<span data-ttu-id="13f0d-109">**Табу** қойыншасынан мына арттыруларды табасыз:</span><span class="sxs-lookup"><span data-stu-id="13f0d-109">On the **Discover** tab, you'll find the following enrichments:</span></span>

- <span data-ttu-id="13f0d-110">Microsoft корпорациясы ұсынатын [брендтер](enrichment-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="13f0d-110">[Brands](enrichment-microsoft.md) provided by Microsoft</span></span>
- <span data-ttu-id="13f0d-111">Microsoft корпорациясы ұсынатын [қызығушылықтар](enrichment-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="13f0d-111">[Interests](enrichment-microsoft.md) provided by Microsoft</span></span>
- <span data-ttu-id="13f0d-112">Leadspace қамтамасыз еткен [компания деректері](enrichment-leadspace.md)</span><span class="sxs-lookup"><span data-stu-id="13f0d-112">[Company data](enrichment-leadspace.md) provided by Leadspace</span></span>
- <span data-ttu-id="13f0d-113">Experian қамтамасыз еткен [демография](enrichment-experian.md)</span><span class="sxs-lookup"><span data-stu-id="13f0d-113">[Demographics](enrichment-experian.md) provided by Experian</span></span>
- <span data-ttu-id="13f0d-114">HERE Technologies қамтамасыз еткен [орын деректері](enrichment-here.md)</span><span class="sxs-lookup"><span data-stu-id="13f0d-114">[Location data](enrichment-here.md) provided by HERE Technologies</span></span>
- <span data-ttu-id="13f0d-115">Қауіпсіз файл тасымалдау протоколы (SFTP) арқылы алынған [реттелетін деректер](enrichment-SFTP-custom-import.md)</span><span class="sxs-lookup"><span data-stu-id="13f0d-115">[Custom data](enrichment-SFTP-custom-import.md) through Secure File Transfer Protocol (SFTP)</span></span>

<span data-ttu-id="13f0d-116">**Менің арттыруларым** қойыншасында сіз теңшеген арттыруларды көруге және сипаттарын өңдеуге болады.</span><span class="sxs-lookup"><span data-stu-id="13f0d-116">On the **My enrichments** tab, you can see the enrichments you've configured and edit their properties.</span></span>

## <a name="manage-existing-enrichments"></a><span data-ttu-id="13f0d-117">Бар арттыруларды басқару</span><span class="sxs-lookup"><span data-stu-id="13f0d-117">Manage existing enrichments</span></span>

<span data-ttu-id="13f0d-118">Барлық конфигурацияланған арттыруларды көру үшін **Менің арттыруларым** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="13f0d-118">Go to the **My enrichments** to see all configured enrichments.</span></span> <span data-ttu-id="13f0d-119">Әрбір арттыру сол арттыру туралы қосымша ақпаратты қамтитын жол түрінде көрсетіледі.</span><span class="sxs-lookup"><span data-stu-id="13f0d-119">Each enrichment is represented as a row that includes additional information about the enrichment.</span></span>

<span data-ttu-id="13f0d-120">Қолжетімді опцияларды көру үшін арттыруды таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="13f0d-120">Select an enrichment to see the available options.</span></span> <span data-ttu-id="13f0d-121">Опцияларды көру үшін тізім элементінен көп нүктені (...) таңдауға болады.</span><span class="sxs-lookup"><span data-stu-id="13f0d-121">You can also select the ellipsis (...) on a list item to see the options.</span></span>

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Арттырулар тізіміндегі арттыруды басқару параметрлері":::

- <span data-ttu-id="13f0d-123">Арттырылған тұтынушы профильдерінің саны бар арттыру туралы мәліметтерді **Көру**.</span><span class="sxs-lookup"><span data-stu-id="13f0d-123">**View** enrichment details with the number of enriched customer profiles.</span></span>
- <span data-ttu-id="13f0d-124">Арттыру конфигурациясын **Өңдеу**.</span><span class="sxs-lookup"><span data-stu-id="13f0d-124">**Edit** the enrichment configuration.</span></span>
- <span data-ttu-id="13f0d-125">Тұтынушы профильдерін соңғы деректермен жаңарту үшін арттыру функциясын **іске қосыңыз**.</span><span class="sxs-lookup"><span data-stu-id="13f0d-125">**Run** the enrichment to update customer profiles with the latest data.</span></span>
- <span data-ttu-id="13f0d-126">Әр жоспарланған жаңартуда автоматты түрде жаңартылуын тоқтату үшін бар арттыруды **Өшіру**.</span><span class="sxs-lookup"><span data-stu-id="13f0d-126">**Deactivate** an existing enrichment to stop it from refreshing automatically with every scheduled refresh.</span></span> <span data-ttu-id="13f0d-127">Соңғы сәтті жаңартудың деректері қолжетімді бола береді.</span><span class="sxs-lookup"><span data-stu-id="13f0d-127">Data from the last successful refresh will continue to be available.</span></span> <span data-ttu-id="13f0d-128">Әр жоспарланған жаңартуда автоматты жаңартуды қайта бастау үшін белсенді емес арттыруды **Белсендіру**.</span><span class="sxs-lookup"><span data-stu-id="13f0d-128">**Activate** an inactive enrichment to restart automatic refreshing with every scheduled refresh.</span></span>
- <span data-ttu-id="13f0d-129">Арттыруды **жойыңыз**.</span><span class="sxs-lookup"><span data-stu-id="13f0d-129">**Delete** an enrichment.</span></span>

<span data-ttu-id="13f0d-130">Бірнеше арттыру функцияларын тізімнен таңдау арқылы бірден іске қосуға немесе өшіруге болады.</span><span class="sxs-lookup"><span data-stu-id="13f0d-130">You can run or deactivate multiple enrichments at once by selecting them in the list.</span></span> <span data-ttu-id="13f0d-131">Көру және өңдеу параметрлері жаппай әрекет ретінде қолжетімді емес және бір уақытта тек бір арттыру үшін жұмыс істейді.</span><span class="sxs-lookup"><span data-stu-id="13f0d-131">View and edit options aren't available as bulk action and only work for one enrichment at a time.</span></span>

## <a name="enrichments-and-connections"></a><span data-ttu-id="13f0d-132">Жақсартулар мен қосылымдар</span><span class="sxs-lookup"><span data-stu-id="13f0d-132">Enrichments and connections</span></span>

<span data-ttu-id="13f0d-133">Үшінші тарап жақсартулары [қосылымдарды](connections.md) пайдалану арқылы конфигурацияланады, оны әкімші тіркелгі деректерімен орнатады және деректерді тасымалдауға келісім береді.</span><span class="sxs-lookup"><span data-stu-id="13f0d-133">Third-party enrichments are configured using [connections](connections.md), which an administrator sets up with credentials and provides consent for data transfers.</span></span> <span data-ttu-id="13f0d-134">Әкімшілер мен салымшылар қосылымды жақсартуларды конфигурациялау үшін пайдалана алады.</span><span class="sxs-lookup"><span data-stu-id="13f0d-134">The connection can be used by administrators and contributors to configure enrichments.</span></span>  

## <a name="multiple-enrichments-of-the-same-type"></a><span data-ttu-id="13f0d-135">Бір түрдегі бірнеше жақсарту</span><span class="sxs-lookup"><span data-stu-id="13f0d-135">Multiple enrichments of the same type</span></span>

<span data-ttu-id="13f0d-136">Жақсартылатын нысан жақсарту конфигурациясы кезінде көрсетіледі, бұл сіздің профильдеріңіздің тек ішкі жиынтығын жақсартуға мүмкіндік береді.</span><span class="sxs-lookup"><span data-stu-id="13f0d-136">The entity to be enriched is specified during the enrichment configuration, which allows you to enrich only a subset of your profiles.</span></span> <span data-ttu-id="13f0d-137">Мысалы, деректерді тек белгілі бір сегмент үшін жақсартыңыз.</span><span class="sxs-lookup"><span data-stu-id="13f0d-137">For exmaple, enrich data only for a specific segment.</span></span> <span data-ttu-id="13f0d-138">Бір түрдегі бірнеше жақсартуды конфигурациялауға және бір қосылымды қайта пайдалануға болады.</span><span class="sxs-lookup"><span data-stu-id="13f0d-138">You can configure several enrichments of the same type and reuse the same connection.</span></span> <span data-ttu-id="13f0d-139">Кейбір жақсартуларда жасалуы мүмкін бірдей түрдегі жақсарту санының шегі болады.</span><span class="sxs-lookup"><span data-stu-id="13f0d-139">Some enrichments will have limits to the number of enrichments of the same type that can be created.</span></span> <span data-ttu-id="13f0d-140">Шектеулер мен ағымдағы пайдалануды **Жақсарту** бетінде көруге болады.</span><span class="sxs-lookup"><span data-stu-id="13f0d-140">The limits and current use can be seen on the **Enrichment** page.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
