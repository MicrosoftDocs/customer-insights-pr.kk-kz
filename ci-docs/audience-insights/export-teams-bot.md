---
title: Microsoft Teams жұмыс кеңістігіне арналған бот
description: Microsoft Teams жұмыс кеңістігінде боттың көмегімен тұтынушының бірыңғай профильдерін іздеңіз.
ms.date: 04/21/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 03299610fd41a7e142e3c9723fad56ce7f90e083
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267959"
---
# <a name="teams-bot-for-dynamics-365-customer-insights-preview"></a><span data-ttu-id="b6bc8-103">Dynamics 365 Customer Insights үшін Teams боты (алдын ала қарау)</span><span class="sxs-lookup"><span data-stu-id="b6bc8-103">Teams bot for Dynamics 365 Customer Insights (preview)</span></span>

<span data-ttu-id="b6bc8-104">Ботқа Teams арналарынан тұтынушының бірыңғай профилін іздеуге мүмкіндік беру үшін Microsoft Teams жұмыс кеңістігімен қосылыңыз.</span><span class="sxs-lookup"><span data-stu-id="b6bc8-104">Connect with Microsoft Teams to let a bot look up unified customer profiles in Teams channels.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="b6bc8-105">![Teams боты тұтынушы жазбасын көрсетеді](media/teams-bot.png "Teams боты тұтынушы жазбасын көрсетеді")</span><span class="sxs-lookup"><span data-stu-id="b6bc8-105">![Teams bot showing a customer record](media/teams-bot.png "Teams bot showing a customer record")</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b6bc8-106">Алғышарттар</span><span class="sxs-lookup"><span data-stu-id="b6bc8-106">Prerequisites</span></span>

<span data-ttu-id="b6bc8-107">Ботты орнатып, конфигурациялау үшін келесі алғышарттарды орындау қажет:</span><span class="sxs-lookup"><span data-stu-id="b6bc8-107">To set up and configure the bot, the following prerequisites must be met:</span></span>

- <span data-ttu-id="b6bc8-108">[Қосылатын кемінде бір деректер көзі](data-sources.md) бар.</span><span class="sxs-lookup"><span data-stu-id="b6bc8-108">There's at least one [data source added](data-sources.md).</span></span>
- <span data-ttu-id="b6bc8-109">[Бірыңғайландыру процесі](data-unification.md) аяқталған.</span><span class="sxs-lookup"><span data-stu-id="b6bc8-109">The [unification process](data-unification.md) is complete.</span></span>
- <span data-ttu-id="b6bc8-110">Өрістер [іздеу және сүзгілеу индексіне](search-filter-index.md) қосылған.</span><span class="sxs-lookup"><span data-stu-id="b6bc8-110">Fields are added to the [search and filter index](search-filter-index.md).</span></span>
- <span data-ttu-id="b6bc8-111">Customer Insights және Teams жүйелері бір ұйымда.</span><span class="sxs-lookup"><span data-stu-id="b6bc8-111">Customer Insights and Teams are in the same organization.</span></span>

## <a name="configure-the-bot"></a><span data-ttu-id="b6bc8-112">Ботты конфигурациялау</span><span class="sxs-lookup"><span data-stu-id="b6bc8-112">Configure the bot</span></span>

1. <span data-ttu-id="b6bc8-113">Аудитория мәліметтерінде **Әкімші** > **Экспорттау мақсаттары** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="b6bc8-113">In audience insights, go to **Admin** > **Export Destinations**.</span></span>
1. <span data-ttu-id="b6bc8-114">Microsoft Teams қатарында **Орнату** түймесін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="b6bc8-114">On the Microsoft Teams tile, select **Set up**.</span></span>
1. <span data-ttu-id="b6bc8-115">Сіз Teams жүйесінде **Бағдарламалар** аймағына қайта бағытталдыңыз.</span><span class="sxs-lookup"><span data-stu-id="b6bc8-115">You're redirected to the **Apps** area in Teams.</span></span> <span data-ttu-id="b6bc8-116">Сондай-ақ Teams жүйесін ашып, астыңғы сол жақ бұрышта **Бағдарламалар** опциясын таңдауға немесе [оны AppSource](https://go.microsoft.com/fwlink/?linkid=2124104) жүйесінен алуға болады.</span><span class="sxs-lookup"><span data-stu-id="b6bc8-116">You can also open Teams and select **Apps** in the bottom-left corner or [get it from AppSource](https://go.microsoft.com/fwlink/?linkid=2124104) directly.</span></span>
1. <span data-ttu-id="b6bc8-117">**Customer Insights** іздеп, бағдарламаны таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="b6bc8-117">Search for **Customer Insights** and select the app.</span></span>
1. <span data-ttu-id="b6bc8-118">**Қосу** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="b6bc8-118">Select **Add**.</span></span>
1. <span data-ttu-id="b6bc8-119">Teams жүйесіндегі Customer Insights қызметіне кіргеннен кейін сәлемдесу хабарын көріп, іске кірісуге болады.</span><span class="sxs-lookup"><span data-stu-id="b6bc8-119">After signing in to Customer Insights in Teams, you'll see a welcome message and can get started.</span></span>

## <a name="things-you-can-do-with-the-bot"></a><span data-ttu-id="b6bc8-120">Ботпен жасауға болатын әрекеттер</span><span class="sxs-lookup"><span data-stu-id="b6bc8-120">Things you can do with the bot</span></span>

<span data-ttu-id="b6bc8-121">Бот бірыңғай тұтынушы профильдері үшін іздеу мүмкіндіктерін қамтамасыз етеді.</span><span class="sxs-lookup"><span data-stu-id="b6bc8-121">The bot provides lookup capabilities for unified customer profiles.</span></span>

- <span data-ttu-id="b6bc8-122">**Іздеу** өрісінен кейін іздеу және сүзгілеу индексіне қосылған бірыңғай тұтынушы профиліндегі атау, электрондық пошта мекенжайы немесе басқа да өрістерді енгізіңіз.</span><span class="sxs-lookup"><span data-stu-id="b6bc8-122">Enter **search** followed by a name, email address, or any other field on the unified customer profile that is added to the search and filter index.</span></span>

  <span data-ttu-id="b6bc8-123">Нәтижелік тұтынушы профилінен 15-ке дейінгі өрістері бар карта аласыз.</span><span class="sxs-lookup"><span data-stu-id="b6bc8-123">You'll get a card with up to 15 fields from the resulting customer profile.</span></span> <span data-ttu-id="b6bc8-124">Бірнеше сәйкестіктер профильді таңдау аймағында нәтижелер тізімін қайтарады.</span><span class="sxs-lookup"><span data-stu-id="b6bc8-124">Multiple matches return a list of results where you can select a profile.</span></span> <span data-ttu-id="b6bc8-125">Дәл сәйкестік табу үшін іздеу шартына қос тырнақша қосуға болады.</span><span class="sxs-lookup"><span data-stu-id="b6bc8-125">You can add the search term in double quotes to look up an exact match.</span></span>

- <span data-ttu-id="b6bc8-126">Егер сіздің ұйымыңыз бір ұйымда бірнеше Customer Insights орталарын сақтаса, ботты қосқыңыз келетін ортаны таңдау үшін **дананы ауыстыру** ішіне кіре аласыз.</span><span class="sxs-lookup"><span data-stu-id="b6bc8-126">If your organization maintains multiple Customer Insights environments in the same organization, you can enter **switchinstance** to choose which environment you want to connect the bot to.</span></span>

- <span data-ttu-id="b6bc8-127">Бот үшін қолжетімді пәрмендер тізімін көру үшін **анықтаманы** енгізіңіз,</span><span class="sxs-lookup"><span data-stu-id="b6bc8-127">Enter **help** to see a list of available commands for the bot.</span></span>  


[!INCLUDE[footer-include](../includes/footer-banner.md)]