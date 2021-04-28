---
title: Customer Insights деректерін Dynamics 365 Sales бағдарламасына экспорттау
description: Dynamics 365 Sales жүйесі үшін қосылымды конфигурациялау және экспорттау жолы туралы ақпарат.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: fc1a05ba4d21d96aa1a9724d158687bbb86949b6
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759611"
---
# <a name="use-segments-in-dynamics-365-sales-preview"></a><span data-ttu-id="368d2-103">Dynamics 365 Sales жүйесіндегі сегменттерді пайдалану (алдын ала қарау нұсқасы)</span><span class="sxs-lookup"><span data-stu-id="368d2-103">Use segments in Dynamics 365 Sales (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="368d2-104">Тұтынушы деректерін Dynamics 365 Sales көмегімен маркетинг тізімдерін жасау, жұмыс ағындарын қадағалау және жарнамалар жіберу үшін пайдаланыңыз.</span><span class="sxs-lookup"><span data-stu-id="368d2-104">Use your customer data to create marketing lists, follow up workflows, and send out promotions with Dynamics 365 Sales.</span></span>

## <a name="prerequisite-for-connection"></a><span data-ttu-id="368d2-105">Қосылым алғышарты</span><span class="sxs-lookup"><span data-stu-id="368d2-105">Prerequisite for connection</span></span>

1. <span data-ttu-id="368d2-106">Сегментті Customer Insights қызметінен сатылымға экспорттау алдында Dynamics 365 Sales жүйесінде контакт жазбалары болуы тиіс.</span><span class="sxs-lookup"><span data-stu-id="368d2-106">Contact records must be present in Dynamics 365 Sales before you can export a segment from Customer Insights to Sales.</span></span> <span data-ttu-id="368d2-107">[Dynamics 365 Sales жүйесінде Common Data Services](connect-power-query.md) арқылы контактілерді қабылдау жолдары туралы толығырақ оқыңыз.</span><span class="sxs-lookup"><span data-stu-id="368d2-107">Read more on how to ingest contacts in [Dynamics 365 Sales using Common Data Services](connect-power-query.md).</span></span>

   > [!NOTE]
   > <span data-ttu-id="368d2-108">Сегменттерді аудитория туралы түсініктерден сатылымға экспорттау сатылым даналарында жаңа контакт жазбаларын жасамайды.</span><span class="sxs-lookup"><span data-stu-id="368d2-108">Exporting segments from audience insights to Sales will not create new contact records in the Sales instances.</span></span> <span data-ttu-id="368d2-109">Сатылымдағы контакт жазбалары аудитория туралы түсінікке қабылданып, деректер көзі ретінде пайдаланылуы тиіс.</span><span class="sxs-lookup"><span data-stu-id="368d2-109">The contact records from Sales must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="368d2-110">Сондай-ақ, оларды сегменттер экспортталмас бұрын тұтынушы идентификаторларын контакт идентификаторларымен салыстыру үшін бірыңғай тұтынушы нысанына қосу қажет.</span><span class="sxs-lookup"><span data-stu-id="368d2-110">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="set-up-the-connection-to-sales"></a><span data-ttu-id="368d2-111">Sales қызметіне қосылым орнату</span><span class="sxs-lookup"><span data-stu-id="368d2-111">Set up the connection to Sales</span></span>

1. <span data-ttu-id="368d2-112">**Әкімші** > **Қосылымдар** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="368d2-112">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="368d2-113">**Қосылым қосу** түймешігін таңдаңыз және қосылымды конфигурациялау үшін **Dynamics 365 Sales** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="368d2-113">Select **Add connection** and choose **Dynamics 365 Sales** to configure the connection.</span></span>

1. <span data-ttu-id="368d2-114">**Көрсетілетін аты** өрісінде қосылымға оңай танылатын атау енгізіңіз.</span><span class="sxs-lookup"><span data-stu-id="368d2-114">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="368d2-115">Қосылым атауы мен түрі осы қосылымды сипаттайды.</span><span class="sxs-lookup"><span data-stu-id="368d2-115">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="368d2-116">Қосылымның мақсатын түсіндіретін атауды таңдауды ұсынамыз.</span><span class="sxs-lookup"><span data-stu-id="368d2-116">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="368d2-117">Осы қосылымды кім пайдалана алатынын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="368d2-117">Choose who can use this connection.</span></span> <span data-ttu-id="368d2-118">Егер сіз ешқандай әрекет жасамасаңыз, әдепкі бойынша Әкімшілер болады.</span><span class="sxs-lookup"><span data-stu-id="368d2-118">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="368d2-119">Қосымша ақпарат алу үшін [Салымшыларға экспорттау үшін қосылымды пайдалануға рұқсат беру](connections.md#allow-contributors-to-use-a-connection-for-exports) бөлімін қараңыз.</span><span class="sxs-lookup"><span data-stu-id="368d2-119">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="368d2-120">**Сервер мекенжайы** өрісінде ұйымның Sales URL мекенжайын енгізіңіз.</span><span class="sxs-lookup"><span data-stu-id="368d2-120">Enter your organization's Sales URL in the **Server address** field.</span></span>

1. <span data-ttu-id="368d2-121">**Сервер әкімшісі тіркелгісі** бөлімінде **Жүйеге кіру** опциясын таңдап, Dynamics 365 Sales тіркелгісін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="368d2-121">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Sales account.</span></span>

1. <span data-ttu-id="368d2-122">Тұтынушы идентификаторы өрісін Dynamics 365 контакт идентификаторына салыңыз.</span><span class="sxs-lookup"><span data-stu-id="368d2-122">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="368d2-123">Қосылымды аяқтау үшін **Сақтау** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="368d2-123">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="368d2-124">Экспорттауды конфигурациялау</span><span class="sxs-lookup"><span data-stu-id="368d2-124">Configure an export</span></span>

<span data-ttu-id="368d2-125">Егер сіз осы түрдегі қосылымға қатынаса алсаңыз, сіз бұл экспорттауды конфигурациялай аласыз.</span><span class="sxs-lookup"><span data-stu-id="368d2-125">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="368d2-126">Қосымша ақпарат алу үшін [Экспорттауды конфигурациялау үшін қажет рұқсаттар](export-destinations.md#set-up-a-new-export) бөлімін қараңыз.</span><span class="sxs-lookup"><span data-stu-id="368d2-126">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="368d2-127">**Деректер** > **Экспорттау** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="368d2-127">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="368d2-128">Жаңа экспорттау жасау үшін **Мақсатты орын қосу** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="368d2-128">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="368d2-129">**Экспорттауға арналған қосылым** өрісінде Dynamics 365 Sales бөлімінен қосылым таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="368d2-129">In the **Connection for export** field, choose a connection from the Dynamics 365 Sales section.</span></span> <span data-ttu-id="368d2-130">Егер сіз осы бөлімнің атын көрмесеңіз, сізге қолжетімді осы түрдегі қосылым жоқ.</span><span class="sxs-lookup"><span data-stu-id="368d2-130">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="368d2-131">Бір немесе бірнеше сегментті таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="368d2-131">Choose one or more segments.</span></span>

1. <span data-ttu-id="368d2-132">**Сақтау** түймешігін таңдау</span><span class="sxs-lookup"><span data-stu-id="368d2-132">Select **Save**</span></span>

<span data-ttu-id="368d2-133">Экспорттауды сақтау экспорттауды бірден іске қоспайды.</span><span class="sxs-lookup"><span data-stu-id="368d2-133">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="368d2-134">Экспорттау әр [жоспарланған жаңартумен](system.md#schedule-tab) іске қосылады.</span><span class="sxs-lookup"><span data-stu-id="368d2-134">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="368d2-135">Сондай-ақ [деректерді сұрау бойынша экспорттауға](export-destinations.md#run-exports-on-demand) болады.</span><span class="sxs-lookup"><span data-stu-id="368d2-135">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
