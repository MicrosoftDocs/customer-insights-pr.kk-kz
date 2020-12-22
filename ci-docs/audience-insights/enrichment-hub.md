---
title: Тұтынушының бірыңғай профильдерін арттыру
description: Тұтынушының деректерін арттыру үшін мүмкіндіктерді пайдаланыңыз.
ms.date: 11/02/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: c25cfbf3808fc1534b54d2d834f1c63ff4c9fe0a
ms.sourcegitcommit: 334633cbd58f5659d20b4f87252c1a10cc7130db
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 12/03/2020
ms.locfileid: "4667101"
---
# <a name="enrichment-for-customer-profiles-preview"></a><span data-ttu-id="7c32b-103">Тұтынушы профильдерін арттыру (алдын ала қарау)</span><span class="sxs-lookup"><span data-stu-id="7c32b-103">Enrichment for customer profiles (preview)</span></span>

<span data-ttu-id="7c32b-104">Тұтынушы деректерін арттыру үшін Microsoft және басқа серіктестер сияқты көздердің деректерін пайдаланыңыз.</span><span class="sxs-lookup"><span data-stu-id="7c32b-104">Use data from sources like Microsoft and other partners to enrich your customer data.</span></span>

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Арттыру орталығының беті":::

<span data-ttu-id="7c32b-106">Аудитория түсініктерінде арттыру нұсқаларымен жұмыс істеу үшін **Деректер** > **Арттыру** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="7c32b-106">In audience insights, go to **Data** > **Enrichment** to work with enrichment options.</span></span>    
<span data-ttu-id="7c32b-107">Арттыруларды жасау немесе өңдеу үшін сізге үлескер немесе әкімші рұқсаттары қажет.</span><span class="sxs-lookup"><span data-stu-id="7c32b-107">You need to have Contributor or Administrator permissions to create or edit enrichments.</span></span> <span data-ttu-id="7c32b-108">Қосымша ақпаратты [Рұқсаттар](permissions.md) бөлімінен қараңыз.</span><span class="sxs-lookup"><span data-stu-id="7c32b-108">For more information, see [Permissions](permissions.md).</span></span>

<span data-ttu-id="7c32b-109">**Табу** қойыншасынан мына арттыруларды табасыз:</span><span class="sxs-lookup"><span data-stu-id="7c32b-109">On the **Discover** tab, you'll find the following enrichments:</span></span>

- <span data-ttu-id="7c32b-110">Microsoft Graph қамтамасыз еткен [брендтер](enrichment-microsoft-graph.md)</span><span class="sxs-lookup"><span data-stu-id="7c32b-110">[Brands](enrichment-microsoft-graph.md) provided by Microsoft Graph</span></span>
- <span data-ttu-id="7c32b-111">Microsoft Graph қамтамасыз еткен [қызығушылықтар](enrichment-microsoft-graph.md)</span><span class="sxs-lookup"><span data-stu-id="7c32b-111">[Interests](enrichment-microsoft-graph.md) provided by Microsoft Graph</span></span>
- <span data-ttu-id="7c32b-112">Leadspace қамтамасыз еткен [компания деректері](enrichment-leadspace.md)</span><span class="sxs-lookup"><span data-stu-id="7c32b-112">[Company data](enrichment-leadspace.md) provided by Leadspace</span></span>
- <span data-ttu-id="7c32b-113">Experian қамтамасыз еткен [демография](enrichment-experian.md)</span><span class="sxs-lookup"><span data-stu-id="7c32b-113">[Demographics](enrichment-experian.md) provided by Experian</span></span>
- <span data-ttu-id="7c32b-114">HERE Technologies қамтамасыз еткен [орын деректері](enrichment-here.md)</span><span class="sxs-lookup"><span data-stu-id="7c32b-114">[Location data](enrichment-here.md) provided by HERE Technologies</span></span>
- <span data-ttu-id="7c32b-115">Қауіпсіз файл тасымалдау протоколы (SFTP) арқылы алынған [реттелетін деректер](enrichment-SFTP-custom-import.md)</span><span class="sxs-lookup"><span data-stu-id="7c32b-115">[Custom data](enrichment-SFTP-custom-import.md) through Secure File Transfer Protocol (SFTP)</span></span>

<span data-ttu-id="7c32b-116">**Менің арттыруларым** қойыншасында сіз теңшеген арттыруларды көруге және сипаттарын өңдеуге болады.</span><span class="sxs-lookup"><span data-stu-id="7c32b-116">On the **My enrichments** tab, you can see the enrichments you've configured and edit their properties.</span></span>

## <a name="manage-existing-enrichments"></a><span data-ttu-id="7c32b-117">Бар арттыруларды басқару</span><span class="sxs-lookup"><span data-stu-id="7c32b-117">Manage existing enrichments</span></span>

<span data-ttu-id="7c32b-118">Барлық конфигурацияланған арттыруларды көру үшін **Менің арттыруларым** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="7c32b-118">Go to the **My enrichments** to see all configured enrichments.</span></span> <span data-ttu-id="7c32b-119">Әрбір арттыру сол арттыру туралы қосымша ақпаратты қамтитын жол түрінде көрсетіледі.</span><span class="sxs-lookup"><span data-stu-id="7c32b-119">Each enrichment is represented as a row that includes additional information about the enrichment.</span></span>

<span data-ttu-id="7c32b-120">Қолжетімді опцияларды көру үшін арттыруды таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="7c32b-120">Select an enrichment to see the available options.</span></span> <span data-ttu-id="7c32b-121">Я болмаса, опцияларды көру үшін тізім элементінде көп нүктені (...) таңдауға болады.</span><span class="sxs-lookup"><span data-stu-id="7c32b-121">Alternatively, you can select the ellipsis (...) on a list item to see the options.</span></span>

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Арттырулар тізіміндегі арттыруды басқару параметрлері":::

- <span data-ttu-id="7c32b-123">Арттырылған тұтынушы профильдерінің саны бар арттыру туралы мәліметтерді **Көру**.</span><span class="sxs-lookup"><span data-stu-id="7c32b-123">**View** enrichment details with the number of enriched customer profiles.</span></span>
- <span data-ttu-id="7c32b-124">Арттыру конфигурациясын **Өңдеу**.</span><span class="sxs-lookup"><span data-stu-id="7c32b-124">**Edit** the enrichment configuration.</span></span>
- <span data-ttu-id="7c32b-125">Тұтынушы профильдерін соңғы деректермен жаңарту үшін арттыру функциясын **іске қосыңыз**.</span><span class="sxs-lookup"><span data-stu-id="7c32b-125">**Run** the enrichment to update customer profiles with the latest data.</span></span>
- <span data-ttu-id="7c32b-126">Әр жоспарланған жаңартуда автоматты түрде жаңартылуын тоқтату үшін бар арттыруды **Өшіру**.</span><span class="sxs-lookup"><span data-stu-id="7c32b-126">**Deactivate** an existing enrichment to stop it from refreshing automatically with every scheduled refresh.</span></span> <span data-ttu-id="7c32b-127">Соңғы сәтті жаңартудың деректері қолжетімді бола береді.</span><span class="sxs-lookup"><span data-stu-id="7c32b-127">Data from the last successful refresh will continue to be available.</span></span> <span data-ttu-id="7c32b-128">Әр жоспарланған жаңартуда автоматты жаңартуды қайта бастау үшін белсенді емес арттыруды **Белсендіру**.</span><span class="sxs-lookup"><span data-stu-id="7c32b-128">**Activate** an inactive enrichment to restart automatic refreshing with every scheduled refresh.</span></span>
- <span data-ttu-id="7c32b-129">Арттыруды **жойыңыз**.</span><span class="sxs-lookup"><span data-stu-id="7c32b-129">**Delete** an enrichment.</span></span>

<span data-ttu-id="7c32b-130">Бірнеше арттыру функцияларын тізімнен таңдау арқылы бірден іске қосуға немесе өшіруге болады.</span><span class="sxs-lookup"><span data-stu-id="7c32b-130">You can run or deactivate multiple enrichments at once by selecting them in the list.</span></span> <span data-ttu-id="7c32b-131">Көру және өңдеу параметрлері жаппай әрекет ретінде қолжетімді емес және бір уақытта тек бір арттыру үшін жұмыс істейді.</span><span class="sxs-lookup"><span data-stu-id="7c32b-131">View and edit options aren't available as bulk action and only work for one enrichment at a time.</span></span>
