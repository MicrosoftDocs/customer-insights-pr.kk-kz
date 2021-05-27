---
title: Customer Insights деректерін Dynamics 365 Marketing бағдарламасына экспорттау
description: Dynamics 365 Marketing жүйесі үшін қосылымды конфигурациялау және экспорттау жолы туралы ақпарат.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 195bee789dc043057b47c12c8d93e6d53edb59cd
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976807"
---
# <a name="use-segments-in-dynamics-365-marketing-preview"></a><span data-ttu-id="f382e-103">Dynamics 365 Marketing жүйесіндегі сегменттерді пайдалану (алдын ала қарау нұсқасы)</span><span class="sxs-lookup"><span data-stu-id="f382e-103">Use segments in Dynamics 365 Marketing (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="f382e-104">[Сегменттерді](segments.md) науқандар құру және Dynamics 365 Marketing арқылы тұтынушылардың белгілі бір топтарымен байланысу үшін пайдаланыңыз.</span><span class="sxs-lookup"><span data-stu-id="f382e-104">Use [segments](segments.md) to generate campaigns and contact specific groups of customers with Dynamics 365 Marketing.</span></span> <span data-ttu-id="f382e-105">Қосымша ақпаратты [Dynamics 365 Marketing бар Dynamics 365 Customer Insights сегменттерін пайдалану](/dynamics365/marketing/customer-insights-segments) бөлімінен қараңыз</span><span class="sxs-lookup"><span data-stu-id="f382e-105">For more information, see [Use segments from Dynamics 365 Customer Insights with Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)</span></span>

## <a name="prerequisite-for-a-connection"></a><span data-ttu-id="f382e-106">Қосылым алғышарты</span><span class="sxs-lookup"><span data-stu-id="f382e-106">Prerequisite for a connection</span></span>

- <span data-ttu-id="f382e-107">Сегментті Customer Insights қызметінен маркетингке экспорттау алдында Dynamics 365 Marketing жүйесінде контакт жазбалары болуы тиіс.</span><span class="sxs-lookup"><span data-stu-id="f382e-107">Contact records must be present in Dynamics 365 Marketing before you can export a segment from Customer Insights to Marketing.</span></span> <span data-ttu-id="f382e-108">[Dynamics 365 Marketing жүйесінде Common Data Services](connect-power-query.md) арқылы контактілерді қабылдау жолдары туралы толығырақ оқыңыз.</span><span class="sxs-lookup"><span data-stu-id="f382e-108">Read more on how to ingest contacts in [Dynamics 365 Marketing using Common Data Services](connect-power-query.md).</span></span>

  > [!NOTE]
  > <span data-ttu-id="f382e-109">Сегменттерді аудитория туралы түсініктерден маркетингке экспорттау маркетинг даналарында жаңа контакт жазбаларын жасамайды.</span><span class="sxs-lookup"><span data-stu-id="f382e-109">Exporting segments from audience insights to Marketing will not create new contact records in the Marketing instances.</span></span> <span data-ttu-id="f382e-110">Маркетингтегі контакт жазбалары аудитория туралы түсінікке қабылданып, деректер көзі ретінде пайдаланылуы тиіс.</span><span class="sxs-lookup"><span data-stu-id="f382e-110">The contact records from Marketing must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="f382e-111">Сондай-ақ оларды сегменттер экспортталмас бұрын тұтынушы идентификаторларын контакт идентификаторларымен салыстыру үшін бірыңғай тұтынушы нысанына қосу қажет.</span><span class="sxs-lookup"><span data-stu-id="f382e-111">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="set-up-connection-to-marketing"></a><span data-ttu-id="f382e-112">Маркетинг қызметіне қосылым орнату</span><span class="sxs-lookup"><span data-stu-id="f382e-112">Set up connection to Marketing</span></span>

1. <span data-ttu-id="f382e-113">**Әкімші** > **Қосылымдар** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="f382e-113">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="f382e-114">**Қосылым қосу** түймешігін таңдаңыз және қосылымды конфигурациялау үшін **Dynamics 365 Marketing** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="f382e-114">Select **Add connection** and choose **Dynamics 365 Marketing** to configure the connection.</span></span>

1. <span data-ttu-id="f382e-115">**Көрсетілетін аты** өрісінде қосылымға оңай танылатын атау енгізіңіз.</span><span class="sxs-lookup"><span data-stu-id="f382e-115">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="f382e-116">Қосылым атауы мен түрі осы қосылымды сипаттайды.</span><span class="sxs-lookup"><span data-stu-id="f382e-116">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="f382e-117">Қосылымның мақсатын түсіндіретін атауды таңдауды ұсынамыз.</span><span class="sxs-lookup"><span data-stu-id="f382e-117">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="f382e-118">Осы қосылымды кім пайдалана алатынын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="f382e-118">Choose who can use this connection.</span></span> <span data-ttu-id="f382e-119">Егер сіз ешқандай әрекет жасамасаңыз, әдепкі бойынша Әкімшілер болады.</span><span class="sxs-lookup"><span data-stu-id="f382e-119">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="f382e-120">Қосымша ақпарат алу үшін [Салымшыларға экспорттау үшін қосылымды пайдалануға рұқсат беру](connections.md#allow-contributors-to-use-a-connection-for-exports) бөлімін қараңыз.</span><span class="sxs-lookup"><span data-stu-id="f382e-120">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="f382e-121">**Сервер мекенжайы** өрісінде ұйымның Marketing URL мекенжайын енгізіңіз.</span><span class="sxs-lookup"><span data-stu-id="f382e-121">Enter your organization's Marketing URL in the **Server address** field.</span></span>

1. <span data-ttu-id="f382e-122">**Сервер әкімшісі тіркелгісі** бөлімінде **Жүйеге кіру** опциясын таңдап, Dynamics 365 Marketing тіркелгісін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="f382e-122">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Marketing account.</span></span>

1. <span data-ttu-id="f382e-123">Тұтынушы идентификаторы өрісін Dynamics 365 контакт идентификаторына салыңыз.</span><span class="sxs-lookup"><span data-stu-id="f382e-123">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="f382e-124">Қосылымды аяқтау үшін **Сақтау** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="f382e-124">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="f382e-125">Экспорттауды конфигурациялау</span><span class="sxs-lookup"><span data-stu-id="f382e-125">Configure an export</span></span>

<span data-ttu-id="f382e-126">Егер сіз осы түрдегі қосылымға қатынаса алсаңыз, сіз бұл экспорттауды конфигурациялай аласыз.</span><span class="sxs-lookup"><span data-stu-id="f382e-126">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="f382e-127">Қосымша ақпарат алу үшін [Экспорттауды конфигурациялау үшін қажет рұқсаттар](export-destinations.md#set-up-a-new-export) бөлімін қараңыз.</span><span class="sxs-lookup"><span data-stu-id="f382e-127">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="f382e-128">**Деректер** > **Экспорттау** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="f382e-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="f382e-129">Жаңа экспорттау жасау үшін **Мақсатты орын қосу** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="f382e-129">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="f382e-130">**Экспорттауға арналған қосылым** өрісінде Dynamics 365 Marketing бөлімінен қосылым таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="f382e-130">In the **Connection for export** field, choose a connection from the Dynamics 365 Marketing section.</span></span> <span data-ttu-id="f382e-131">Егер сіз осы бөлімнің атын көрмесеңіз, сізге қолжетімді осы түрдегі қосылым жоқ.</span><span class="sxs-lookup"><span data-stu-id="f382e-131">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="f382e-132">Бір немесе бірнеше сегментті таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="f382e-132">Choose one or more segments.</span></span>

1. <span data-ttu-id="f382e-133">**Сақтау** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="f382e-133">Select **Save**.</span></span>

<span data-ttu-id="f382e-134">Экспорттауды сақтау экспорттауды бірден іске қоспайды.</span><span class="sxs-lookup"><span data-stu-id="f382e-134">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="f382e-135">Экспорттау әр [жоспарланған жаңартумен](system.md#schedule-tab) іске қосылады.</span><span class="sxs-lookup"><span data-stu-id="f382e-135">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="f382e-136">Сондай-ақ [деректерді сұрау бойынша экспорттауға](export-destinations.md#run-exports-on-demand) болады.</span><span class="sxs-lookup"><span data-stu-id="f382e-136">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
