---
title: Power BI коннекторы
description: Power BI ішінде Dynamics 365 Customer Insights коннекторын пайдалану жолы туралы ақпарат.
ms.date: 09/21/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: e43e2f9dbc84ebfbf2154990a752740f973296cb
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596046"
---
# <a name="connector-for-power-bi-preview"></a><span data-ttu-id="db2f2-103">Power BI арналған қосқыш (алдын ала қарау)</span><span class="sxs-lookup"><span data-stu-id="db2f2-103">Connector for Power BI (preview)</span></span>

<span data-ttu-id="db2f2-104">Power BI Desktop көмегімен деректерге арналған көрнекілендірулер жасаңыз.</span><span class="sxs-lookup"><span data-stu-id="db2f2-104">Create visualizations for your data with the Power BI Desktop.</span></span> <span data-ttu-id="db2f2-105">Қосымша түсініктер жасаңыз және бірыңғай тұтынушы деректерімен есептер жасаңыз.</span><span class="sxs-lookup"><span data-stu-id="db2f2-105">Generate additional insights and build reports with your unified customer data.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="db2f2-106">Алғышарттар</span><span class="sxs-lookup"><span data-stu-id="db2f2-106">Prerequisites</span></span>

- <span data-ttu-id="db2f2-107">Сізде тұтынушының бірыңғай профилі бар.</span><span class="sxs-lookup"><span data-stu-id="db2f2-107">You have unified customer profiles.</span></span>
- <span data-ttu-id="db2f2-108">[Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) параметрінің соңғы нұсқасы компьютеріңізде орнатылған.</span><span class="sxs-lookup"><span data-stu-id="db2f2-108">The latest version of [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) is installed on your computer.</span></span> <span data-ttu-id="db2f2-109">[Power BI Desktop туралы қосымша мәлімет](/power-bi/desktop-what-is-desktop).</span><span class="sxs-lookup"><span data-stu-id="db2f2-109">[Learn more about Power BI Desktop](/power-bi/desktop-what-is-desktop).</span></span>

## <a name="configure-the-connector-for-power-bi"></a><span data-ttu-id="db2f2-110">Power BI арналған қосқышты конфигурациялау</span><span class="sxs-lookup"><span data-stu-id="db2f2-110">Configure the connector for Power BI</span></span>

1. <span data-ttu-id="db2f2-111">Power BI Desktop бағдарламасында **Файл** > **Деректер алу** тармағын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="db2f2-111">In Power BI Desktop, select **File** > **Get Data**.</span></span>

1. <span data-ttu-id="db2f2-112">**Қосымша ақпарат** опциясын таңдап, **Dynamics 365 Customer Insights** бағдарламасын іздеңіз</span><span class="sxs-lookup"><span data-stu-id="db2f2-112">Select **See more** and search for **Dynamics 365 Customer Insights**</span></span>

1. <span data-ttu-id="db2f2-113">**Қосылу** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="db2f2-113">Select **Connect**.</span></span>

1. <span data-ttu-id="db2f2-114">Customer Insights бағдарламасы үшін пайдаланатын ұйым тіркелгісімен **кіріңіз** және **Қосу** опциясын басыңыз.</span><span class="sxs-lookup"><span data-stu-id="db2f2-114">**Sign in** with the same organizational account you use for Customer Insights and select **Connect**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="db2f2-115">Бұл қадамда көрсетілген тіркелгі Customer Insights деректерін алу үшін пайдаланылады және Power BI жүйесіне кіргенде бірдей болу қажет емес.</span><span class="sxs-lookup"><span data-stu-id="db2f2-115">The account you indicate in this step is used to fetch data from Customer Insights and doesn't need to be the same you are signed in to Power BI.</span></span> <span data-ttu-id="db2f2-116">Деректер алу үшін пайдаланылатын тіркелгіні қалпына келтіру үшін Power BI бағдарламасын ашып, **Файл** > **Опциялар** > **Параметрлер** > **Деректер көзі параметрлері** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="db2f2-116">To reset the account that is used for data fetching, open Power BI and go to **File** > **Options** > **Settings** > **Data source settings**.</span></span> <span data-ttu-id="db2f2-117">Деректер көздері тізімінде, **Dynamics 365 Customer Insights Кіру** және **Рұқсаттарды өшіру** пәрменін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="db2f2-117">In the list of data sources, select **Dynamics 365 Customer Insights Login** and select **Clear permissions**.</span></span>  

1. <span data-ttu-id="db2f2-118">**Navigator** диалогтық терезесінде.</span><span class="sxs-lookup"><span data-stu-id="db2f2-118">In the **Navigator** dialog box.</span></span> <span data-ttu-id="db2f2-119">қолжетімді барлық орталарды тізімде көресіз.</span><span class="sxs-lookup"><span data-stu-id="db2f2-119">you see the list of all environments you have access to.</span></span> <span data-ttu-id="db2f2-120">Ортаны кеңейтіп, қалталардың кез келгенін ашыңыз (нысандар, өлшемдер, сегменттер, арттырулар).</span><span class="sxs-lookup"><span data-stu-id="db2f2-120">Expand an environment and open any of the folders (entities, measures, segments, enrichments).</span></span> <span data-ttu-id="db2f2-121">Мысалы, импорттауға болатын барлық нысандарды көру үшін **Субъектілер** қалтасын ашыңыз.</span><span class="sxs-lookup"><span data-stu-id="db2f2-121">For example, open the **Entities** folder, to see all entities you can import.</span></span>

   <span data-ttu-id="db2f2-122">![Power BI қосқыш навигаторы](media/power-bi-navigator.png "Power BI қосқыш навигаторы")</span><span class="sxs-lookup"><span data-stu-id="db2f2-122">![Power BI Connector Navigator](media/power-bi-navigator.png "Power BI Connector Navigator")</span></span>

1. <span data-ttu-id="db2f2-123">Қосылатын нысандардың жанына құсбелгі қойып, **Жүктеу** опциясын басыңыз.</span><span class="sxs-lookup"><span data-stu-id="db2f2-123">Select the check boxes next to the entities to include and **Load**.</span></span> <span data-ttu-id="db2f2-124">Бірнеше ортадан бірнеше нысанды таңдай аласыз.</span><span class="sxs-lookup"><span data-stu-id="db2f2-124">You can select multiple entities from multiple environments.</span></span>

1. <span data-ttu-id="db2f2-125">Нысандарды жүктеу кезінде жүктеу диалог терезесін көресіз.</span><span class="sxs-lookup"><span data-stu-id="db2f2-125">You'll see a loading dialog box while your entities are loaded.</span></span> <span data-ttu-id="db2f2-126">Барлық таңдалған нысандар жүктелгеннен кейін, деректерді көзбен көру үшін Power BI мүмкіндіктерін пайдалануға болады.</span><span class="sxs-lookup"><span data-stu-id="db2f2-126">Once all of your selected entities have loaded, you can use the capabilities of Power BI to visualize the data.</span></span>

## <a name="large-data-sets"></a><span data-ttu-id="db2f2-127">Үлкен деректер жиынтықтары</span><span class="sxs-lookup"><span data-stu-id="db2f2-127">Large data sets</span></span>

<span data-ttu-id="db2f2-128">Power BI үшін Customer Insights коннекторы 1 миллионға дейін тұтынушы профильдерін қамтитын деректер жиынтықтары үшін жұмыс істеуге арналған.</span><span class="sxs-lookup"><span data-stu-id="db2f2-128">The Customer Insights connector for Power BI is designed to work for data sets that contain up to 1 million customer profiles.</span></span> <span data-ttu-id="db2f2-129">Үлкенірек деректер жиынтықтарын импорттау нәтиже беруі мүмкін, бірақ бұл көп уақытты алады.</span><span class="sxs-lookup"><span data-stu-id="db2f2-129">Importing larger data sets may work, but it takes a long time.</span></span> <span data-ttu-id="db2f2-130">Бұған қоса, Power BI шектеулеріне байланысты бұл процесті күту уақыты бітуі мүмкін.</span><span class="sxs-lookup"><span data-stu-id="db2f2-130">Additionally, the process could run into a time-out because of Power BI limitations.</span></span> <span data-ttu-id="db2f2-131">Қосымша ақпаратты [Power BI: үлкен деректер жиынтықтары туралы ұсыныстар](/power-bi/admin/service-premium-what-is#large-datasets) бөлімінен қараңыз.</span><span class="sxs-lookup"><span data-stu-id="db2f2-131">For more information, see [Power BI: Recommendations for large data sets](/power-bi/admin/service-premium-what-is#large-datasets).</span></span> 

### <a name="work-with-a-subset-of-data"></a><span data-ttu-id="db2f2-132">Деректер жиынымен жұмыс</span><span class="sxs-lookup"><span data-stu-id="db2f2-132">Work with a subset of data</span></span>

<span data-ttu-id="db2f2-133">Деректердің ішкі жиынымен жұмыс жасауды қарастырыңыз.</span><span class="sxs-lookup"><span data-stu-id="db2f2-133">Consider working with a subset of your data.</span></span> <span data-ttu-id="db2f2-134">Мысалы, барлық тұтынушы жазбаларын Power BI бағдарламасына экспорттаудың орнына [сегменттер](segments.md) жасауға болады.</span><span class="sxs-lookup"><span data-stu-id="db2f2-134">For example, you can create [segments](segments.md) instead of exporting all customer records to Power BI.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="db2f2-135">Ақауларын жою</span><span class="sxs-lookup"><span data-stu-id="db2f2-135">Troubleshooting</span></span>

### <a name="customer-insights-environment-doesnt-show-in-power-bi"></a><span data-ttu-id="db2f2-136">Customer Insights ортасы Power BI ішінде көрсетілмейді</span><span class="sxs-lookup"><span data-stu-id="db2f2-136">Customer Insights environment doesn't show in Power BI</span></span>

<span data-ttu-id="db2f2-137">Аудитория туралы түсініктердегі екі бірдей нысан аралығында анықталған бірнеше [қатынасы](relationships.md) бар орталар Power BI қосқышында қолжетімді болмайды.</span><span class="sxs-lookup"><span data-stu-id="db2f2-137">Environments that have more than one [relationship](relationships.md) defined between two identical entities in audience insights will not be available in the Power BI connector.</span></span>

<span data-ttu-id="db2f2-138">Қайталанатын қатынастарды анықтауға және жоюға болады.</span><span class="sxs-lookup"><span data-stu-id="db2f2-138">You can identify and remove the duplicated relationships.</span></span>

1. <span data-ttu-id="db2f2-139">Аудитория туралы түсініктерде Power BI қызметінде жоқ ортада **Деректер** > **Қатынастар** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="db2f2-139">In audience insights, go to **Data** > **Relationships** on the environment you're missing in Power BI.</span></span>
2. <span data-ttu-id="db2f2-140">Қайталанатын қатынастарды анықтаңыз:</span><span class="sxs-lookup"><span data-stu-id="db2f2-140">Identify duplicated relationships:</span></span>
   - <span data-ttu-id="db2f2-141">Бірдей екі нысан арасында анықталған бірнеше қатынастың бар-жоғын тексеріңіз.</span><span class="sxs-lookup"><span data-stu-id="db2f2-141">Check if there is more than one relationship defined between the same two entities.</span></span>
   - <span data-ttu-id="db2f2-142">Біріктіру процесіне қосылатын екі нысан арасында байланыс бар-жоғын тексеріңіз.</span><span class="sxs-lookup"><span data-stu-id="db2f2-142">Check if there is a relationship created between two entities that are both included in the unification process.</span></span> <span data-ttu-id="db2f2-143">Біріктіру процесіне кіретін барлық нысандар арасында айқын емес қатынас бар.</span><span class="sxs-lookup"><span data-stu-id="db2f2-143">There is an implicit relationship defined between all entities included in the unification process.</span></span>
3. <span data-ttu-id="db2f2-144">Анықталған қайталанатын қатынастарды жойыңыз.</span><span class="sxs-lookup"><span data-stu-id="db2f2-144">Remove any duplicate relationships identified.</span></span>

<span data-ttu-id="db2f2-145">Қайталанатын қатынастарды жойғаннан кейін, Power BI қосқышын қайта конфигурациялап көріңіз.</span><span class="sxs-lookup"><span data-stu-id="db2f2-145">After removal of the duplicated relationships, try to configure the Power BI connector again.</span></span> <span data-ttu-id="db2f2-146">Орта қазір қолжетімді болуы керек.</span><span class="sxs-lookup"><span data-stu-id="db2f2-146">The environment should be available now.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]