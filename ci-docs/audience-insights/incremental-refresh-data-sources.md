---
title: Power Query жүйесіне негізделген деректер көздерін қосымша жаңарту
description: Power Query негізделген үлкен деректер көздеріне арналған жаңа және жаңартылған деректерді жаңартыңыз.
ms.date: 09/28/2020
ms.reviewer: adkuppa
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: b7e834f5f2fd1328563139675d7f850008348734
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406241"
---
# <a name="incremental-refresh-for-data-sources-based-on-power-query"></a><span data-ttu-id="9d8a6-103">Power Query негізіндегі деректер көздерін біртіндеп жаңарту</span><span class="sxs-lookup"><span data-stu-id="9d8a6-103">Incremental refresh for data sources based on Power Query</span></span>

<span data-ttu-id="9d8a6-104">Деректер көздерін біртіндеп жаңарту келесі артықшылықтарға ие:</span><span class="sxs-lookup"><span data-stu-id="9d8a6-104">Incremental refresh for data sources provides the following advantages:</span></span>

- <span data-ttu-id="9d8a6-105">**Жылдамырақ жаңартулар** - Тек өзгертілген деректер жаңартылады.</span><span class="sxs-lookup"><span data-stu-id="9d8a6-105">**Faster refreshes** - Only data that has changed gets refreshed.</span></span> <span data-ttu-id="9d8a6-106">Мысалы, тарихи деректер жинағын тек өткен бес күн жаңарта алуыңыз мүмкін.</span><span class="sxs-lookup"><span data-stu-id="9d8a6-106">For example, you might refresh only the past five days of a historical dataset.</span></span>
- <span data-ttu-id="9d8a6-107">**Арттырылған сенімділік** - Кішкентайырақ жаңартулар көмегімен байланыс мәселелері қаупін азайта отырып, тұрақсыз көз жүйелерінің байланыстарын барынша ұзақ сақтау керек болмайды.</span><span class="sxs-lookup"><span data-stu-id="9d8a6-107">**Increased reliability** - With smaller refreshes, you don't need to maintain connections to volatile source systems for as long, reducing the risk of connection issues.</span></span>
- <span data-ttu-id="9d8a6-108">**Қысқартылған ресурс тұтынысы** - Жалпы деректердің қосалқы жинағын ғана жаңарту есептеу ресурстарын тиімдірек пайдалануға әкеледі және орта тұтынысын қысқартады.</span><span class="sxs-lookup"><span data-stu-id="9d8a6-108">**Reduced resource consumption** - Refreshing only a subset of your total data leads to more efficient use of computing resources and decreases the environmental footprint.</span></span>

## <a name="configure-incremental-refresh"></a><span data-ttu-id="9d8a6-109">Біртіндеп жаңартуды конфигурациялау</span><span class="sxs-lookup"><span data-stu-id="9d8a6-109">Configure incremental refresh</span></span>

<span data-ttu-id="9d8a6-110">Аудитория мәліметтері қосымша қабылдауды қолдайтын Power Query арқылы импортталған деректер көздерін қосымша жаңартуға мүмкіндік береді.</span><span class="sxs-lookup"><span data-stu-id="9d8a6-110">Audience insights allows incremental refresh for data sources imported through Power Query that support incremental ingestion.</span></span> <span data-ttu-id="9d8a6-111">Мысалы, күн мен уақыт өрістері Azure SQL дерекқорларында деректер жазбаларының соңғы жаңартылған уақыты көрсетілген.</span><span class="sxs-lookup"><span data-stu-id="9d8a6-111">For example, Azure SQL databases with date and time fields, which indicate when data records were last updated.</span></span>

1. <span data-ttu-id="9d8a6-112">[Power Query негізделген жаңа деректер көзін жасау](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="9d8a6-112">[Create a new data source based on Power Query](connect-power-query.md).</span></span>

1. <span data-ttu-id="9d8a6-113">Деректер көзіне ат беріңіз.</span><span class="sxs-lookup"><span data-stu-id="9d8a6-113">Provide a name for the data source.</span></span>

1. <span data-ttu-id="9d8a6-114">Azure SQL дерекқоры сияқты кезеңдік жаңартуға қолдау көрсетілетін деректер көзін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="9d8a6-114">Select a data source that supports incremental refresh, such as Azure SQL database.</span></span>

1. <span data-ttu-id="9d8a6-115">Қабылданатын нысандарды немесе кестелерді таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="9d8a6-115">Select the entities or tables to ingest.</span></span>

1. <span data-ttu-id="9d8a6-116">Тасымалдау қадамдарын аяқтап, **Келесі** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="9d8a6-116">Complete the transformation steps and select **Next**.</span></span>

1. <span data-ttu-id="9d8a6-117">**Кезеңдік жаңартуды орнату** диалог терезесінде **Кезеңдік жаңарту параметрлерін** ашу үшін **Орнату** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="9d8a6-117">In the **Set up incremental refresh** dialog box, select **Set up** to open the **Incremental refresh settings**.</span></span> <span data-ttu-id="9d8a6-118">**Өткізіп жіберу** қадамын өткізіп жіберсеңіз, деректер көзі толық деректер жинағын жаңартады.</span><span class="sxs-lookup"><span data-stu-id="9d8a6-118">If you select **Skip**, the data source will refresh the entire data set.</span></span>
   > [!TIP]
   > <span data-ttu-id="9d8a6-119">Сонымен қатар бұрыннан бар деректер көзін өңдеу арқылы кезеңдік жаңартуды кейінірек қолдана аласыз.</span><span class="sxs-lookup"><span data-stu-id="9d8a6-119">You can also apply incremental refresh later by editing an existing data source.</span></span>

1. <span data-ttu-id="9d8a6-120">**Кезеңдік жаңарту параметрлерінде** деректер көзін жаңарту кезінде таңдалған барлық нысандарды кезеңдік жаңартуды теңшей аласыз.</span><span class="sxs-lookup"><span data-stu-id="9d8a6-120">On **Incremental refresh settings**, you'll configure the incremental refresh for all entities that you selected when creating the data source.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="9d8a6-121">![Кезеңдік жаңартылатын деректер көзіндегі нысандарды теңшеу](media/incremental-refresh-settings.png "Кезеңдік жаңартылатын деректер көзіндегі нысандарды теңшеу")</span><span class="sxs-lookup"><span data-stu-id="9d8a6-121">![Configure entities in a data source for incremental refresh](media/incremental-refresh-settings.png "Configure entities in a data source for incremental refresh")</span></span>

1. <span data-ttu-id="9d8a6-122">Нысанды таңдап, мына мәліметтерді қамтамасыз етіңіз:</span><span class="sxs-lookup"><span data-stu-id="9d8a6-122">Select an entity, and provide the following details:</span></span>

   - <span data-ttu-id="9d8a6-123">**Негізгі кілтті анықтау**: нысанның немесе кестенің негізгі кілтін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="9d8a6-123">**Define the primary key**: Select a primary key for the entity or table.</span></span>
   - <span data-ttu-id="9d8a6-124">**"Соңғы жаңартылған" өрісті анықтау**: бұл өрісте тек күн немесе уақыт түріндегі төлсипаттар көрсетіледі.</span><span class="sxs-lookup"><span data-stu-id="9d8a6-124">**Define the "last updated" field**: This field will only display attributes of type date or time.</span></span> <span data-ttu-id="9d8a6-125">Жазбалар соңғы жаңартылған уақытты көрсететін төлсипатты таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="9d8a6-125">Select an attribute that indicates when the records were last updated.</span></span> <span data-ttu-id="9d8a6-126">Бұл қосымша жаңартудың уақыт аралығына кіретін жазбаларды анықтау үшін қолданылады.</span><span class="sxs-lookup"><span data-stu-id="9d8a6-126">It will be used to identify the records that fall within the incremental refresh time frame.</span></span>
   - <span data-ttu-id="9d8a6-127">**Әрбір жаңартуды тексеру**: қажетті кезеңдік жаңарту уақыт аралығын көрсетіңіз.</span><span class="sxs-lookup"><span data-stu-id="9d8a6-127">**Check for updates every**: Specify how long you want the incremental refresh time frame to be.</span></span>

1. <span data-ttu-id="9d8a6-128">Деректер көзін жасауды аяқтау үшін **Сақтау** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="9d8a6-128">Select **Save** to complete the creation of the data source.</span></span> <span data-ttu-id="9d8a6-129">Бастапқы деректер жаңартуы толық жаңарту болады.</span><span class="sxs-lookup"><span data-stu-id="9d8a6-129">The initial data refresh will be a full refresh.</span></span> <span data-ttu-id="9d8a6-130">Одан кейін деректерді кезеңдік жаңарту алдыңғы қадамда теңшелгендей орындалады.</span><span class="sxs-lookup"><span data-stu-id="9d8a6-130">Afterwards, the incremental data refresh happens as configured in the previous step.</span></span>
