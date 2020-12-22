---
title: Power BI коннекторы
description: Power BI ішінде Dynamics 365 Customer Insights коннекторын пайдалану жолы туралы ақпарат.
ms.date: 09/21/2020
ms.reviewer: sthe
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: d497ca779a337c512a7254524f597cff226bcb45
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406211"
---
# <a name="connector-for-power-bi-preview"></a><span data-ttu-id="3c5a2-103">Power BI арналған қосқыш (алдын ала қарау)</span><span class="sxs-lookup"><span data-stu-id="3c5a2-103">Connector for Power BI (preview)</span></span>

<span data-ttu-id="3c5a2-104">Power BI Desktop көмегімен деректерге арналған көрнекілендірулер жасаңыз.</span><span class="sxs-lookup"><span data-stu-id="3c5a2-104">Create visualizations for your data with the Power BI Desktop.</span></span> <span data-ttu-id="3c5a2-105">Қосымша түсініктер жасаңыз және бірыңғай тұтынушы деректерімен есептер жасаңыз.</span><span class="sxs-lookup"><span data-stu-id="3c5a2-105">Generate additional insights and build reports with your unified customer data.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="3c5a2-106">Алғышарттар</span><span class="sxs-lookup"><span data-stu-id="3c5a2-106">Prerequisites</span></span>

- <span data-ttu-id="3c5a2-107">Сізде тұтынушының бірыңғай профилі бар.</span><span class="sxs-lookup"><span data-stu-id="3c5a2-107">You have unified customer profiles.</span></span>
- <span data-ttu-id="3c5a2-108">Компьютерде [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) бағдарламасының соңғы нұсқасы орнатылған.</span><span class="sxs-lookup"><span data-stu-id="3c5a2-108">The latest version of [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) is installed on your computer.</span></span> <span data-ttu-id="3c5a2-109">[Power BI Desktop туралы қосымша мәлімет](https://docs.microsoft.com/power-bi/desktop-what-is-desktop).</span><span class="sxs-lookup"><span data-stu-id="3c5a2-109">[Learn more about Power BI Desktop](https://docs.microsoft.com/power-bi/desktop-what-is-desktop).</span></span>

## <a name="configure-the-connector-for-power-bi"></a><span data-ttu-id="3c5a2-110">Power BI арналған қосқышты конфигурациялау</span><span class="sxs-lookup"><span data-stu-id="3c5a2-110">Configure the connector for Power BI</span></span>

1. <span data-ttu-id="3c5a2-111">Power BI Desktop бағдарламасында **Файл** > **Деректер алу** тармағын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="3c5a2-111">In Power BI Desktop, select **File** > **Get Data**.</span></span>

1. <span data-ttu-id="3c5a2-112">**Қосымша ақпарат** опциясын таңдап, **Dynamics 365 Customer Insights** бағдарламасын іздеңіз</span><span class="sxs-lookup"><span data-stu-id="3c5a2-112">Select **See more** and search for **Dynamics 365 Customer Insights**</span></span>

1. <span data-ttu-id="3c5a2-113">Нәтижені таңдап, **Қосу** опциясын басыңыз.</span><span class="sxs-lookup"><span data-stu-id="3c5a2-113">Select the result and select **Connect**.</span></span>

1. <span data-ttu-id="3c5a2-114">Customer Insights бағдарламасы үшін пайдаланатын ұйым тіркелгісімен **кіріңіз** және **Қосу** опциясын басыңыз.</span><span class="sxs-lookup"><span data-stu-id="3c5a2-114">**Sign in** with the same organizational account you use for Customer Insights and select **Connect**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="3c5a2-115">Бұл қадамда көрсетілген тіркелгі Customer Insights деректерін алу үшін пайдаланылады және Power BI жүйесіне кіргенде бірдей болу қажет емес.</span><span class="sxs-lookup"><span data-stu-id="3c5a2-115">The account you indicate in this step is used to fetch data from Customer Insights and doesn't need to be the same you are signed in to Power BI.</span></span> <span data-ttu-id="3c5a2-116">Деректер алу үшін пайдаланылатын тіркелгіні қалпына келтіру үшін Power BI бағдарламасын ашып, **Файл** > **Опциялар** > **Параметрлер** > **Деректер көзі параметрлері** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="3c5a2-116">To reset the account that is used for data fetching, open Power BI and go to **File** > **Options** > **Settings** > **Data source settings**.</span></span> <span data-ttu-id="3c5a2-117">Деректер көздері тізімінде, **Dynamics 365 Customer Insights Кіру** және **Рұқсаттарды өшіру** пәрменін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="3c5a2-117">In the list of data sources, select **Dynamics 365 Customer Insights Login** and select **Clear permissions**.</span></span>  

1. <span data-ttu-id="3c5a2-118">**Navigator** диалогтық терезесінде.</span><span class="sxs-lookup"><span data-stu-id="3c5a2-118">In the **Navigator** dialog box.</span></span> <span data-ttu-id="3c5a2-119">қолжетімді барлық орталарды тізімде көресіз.</span><span class="sxs-lookup"><span data-stu-id="3c5a2-119">you see the list of all environments you have access to.</span></span> <span data-ttu-id="3c5a2-120">Ортаны кеңейтіп, қалталардың кез келгенін ашыңыз (нысандар, өлшемдер, сегменттер, арттырулар).</span><span class="sxs-lookup"><span data-stu-id="3c5a2-120">Expand an environment and open any of the folders (entities, measures, segments, enrichments).</span></span> <span data-ttu-id="3c5a2-121">Мысалы, импорттауға болатын барлық нысандарды көру үшін **Субъектілер** қалтасын ашыңыз.</span><span class="sxs-lookup"><span data-stu-id="3c5a2-121">For example, open the **Entities** folder, to see all entities you can import.</span></span>

   <span data-ttu-id="3c5a2-122">![Power BI қосқыш навигаторы](media/power-bi-navigator.png "Power BI қосқыш навигаторы")</span><span class="sxs-lookup"><span data-stu-id="3c5a2-122">![Power BI Connector Navigator](media/power-bi-navigator.png "Power BI Connector Navigator")</span></span>

1. <span data-ttu-id="3c5a2-123">Қосылатын нысандардың жанына құсбелгі қойып, **Жүктеу** опциясын басыңыз.</span><span class="sxs-lookup"><span data-stu-id="3c5a2-123">Select the check boxes next to the entities to include and **Load**.</span></span> <span data-ttu-id="3c5a2-124">Бірнеше ортадан бірнеше нысанды таңдай аласыз.</span><span class="sxs-lookup"><span data-stu-id="3c5a2-124">You can select multiple entities from multiple environments.</span></span>

1. <span data-ttu-id="3c5a2-125">Нысандарды жүктеу кезінде жүктеу диалог терезесін көресіз.</span><span class="sxs-lookup"><span data-stu-id="3c5a2-125">You'll see a loading dialog box while your entities are loaded.</span></span> <span data-ttu-id="3c5a2-126">Барлық таңдалған нысандар жүктелгеннен кейін, деректерді көзбен көру үшін Power BI мүмкіндіктерін пайдалануға болады.</span><span class="sxs-lookup"><span data-stu-id="3c5a2-126">Once all of your selected entities have loaded, you can use the capabilities of Power BI to visualize the data.</span></span>

## <a name="large-data-sets"></a><span data-ttu-id="3c5a2-127">Үлкен деректер жиынтықтары</span><span class="sxs-lookup"><span data-stu-id="3c5a2-127">Large data sets</span></span>

<span data-ttu-id="3c5a2-128">Power BI үшін Customer Insights коннекторы 1 миллионға дейін тұтынушы профильдерін қамтитын деректер жиынтықтары үшін жұмыс істеуге арналған.</span><span class="sxs-lookup"><span data-stu-id="3c5a2-128">The Customer Insights connector for Power BI is designed to work for data sets that contain up to 1 million customer profiles.</span></span> <span data-ttu-id="3c5a2-129">Үлкенірек деректер жиынтықтарын импорттау нәтиже беруі мүмкін, бірақ бұл көп уақытты алады.</span><span class="sxs-lookup"><span data-stu-id="3c5a2-129">Importing larger data sets may work, but it takes a long time.</span></span> <span data-ttu-id="3c5a2-130">Бұған қоса, Power BI шектеулеріне байланысты бұл процесті күту уақыты бітуі мүмкін.</span><span class="sxs-lookup"><span data-stu-id="3c5a2-130">Additionally, the process could run into a time-out because of Power BI limitations.</span></span> <span data-ttu-id="3c5a2-131">Қосымша ақпаратты [Power BI: үлкен деректер жиынтықтары туралы ұсыныстар](https://docs.microsoft.com/power-bi/admin/service-premium-what-is#large-datasets) бөлімінен қараңыз.</span><span class="sxs-lookup"><span data-stu-id="3c5a2-131">For more information, see [Power BI: Recommendations for large data sets](https://docs.microsoft.com/power-bi/admin/service-premium-what-is#large-datasets).</span></span> 

### <a name="work-with-a-subset-of-data"></a><span data-ttu-id="3c5a2-132">Деректер жиынымен жұмыс</span><span class="sxs-lookup"><span data-stu-id="3c5a2-132">Work with a subset of data</span></span>

<span data-ttu-id="3c5a2-133">Деректердің ішкі жиынымен жұмыс жасауды қарастырыңыз.</span><span class="sxs-lookup"><span data-stu-id="3c5a2-133">Consider working with a subset of your data.</span></span> <span data-ttu-id="3c5a2-134">Мысалы, барлық тұтынушы жазбаларын Power BI бағдарламасына экспорттаудың орнына [сегменттер](segments.md) жасауға болады.</span><span class="sxs-lookup"><span data-stu-id="3c5a2-134">For example, you can create [segments](segments.md) instead of exporting all customer records to Power BI.</span></span>
