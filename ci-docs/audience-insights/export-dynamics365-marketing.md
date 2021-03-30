---
title: Customer Insights деректерін Dynamics 365 Marketing бағдарламасына экспорттау
description: Dynamics 365 Marketing жүйесіне қосылымды конфигурациялау жолы.
ms.date: 02/01/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 892aff643872f11307a2c43e5670edab657d7848
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597610"
---
# <a name="connector-for-dynamics-365-marketing-preview"></a><span data-ttu-id="d1f86-103">Dynamics 365 Marketing қосқышы (алдын ала қарау)</span><span class="sxs-lookup"><span data-stu-id="d1f86-103">Connector for Dynamics 365 Marketing (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="d1f86-104">[Сегменттерді](segments.md) науқандар құру және Dynamics 365 Marketing арқылы тұтынушылардың белгілі бір топтарымен байланысу үшін пайдаланыңыз.</span><span class="sxs-lookup"><span data-stu-id="d1f86-104">Use [segments](segments.md) to generate campaigns and contact specific groups of customers with Dynamics 365 Marketing.</span></span> <span data-ttu-id="d1f86-105">Қосымша ақпаратты [Dynamics 365 Marketing бар Dynamics 365 Customer Insights сегменттерін пайдалану](/dynamics365/marketing/customer-insights-segments) бөлімінен қараңыз</span><span class="sxs-lookup"><span data-stu-id="d1f86-105">For more information, see [Use segments from Dynamics 365 Customer Insights with Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)</span></span>

## <a name="prerequisite"></a><span data-ttu-id="d1f86-106">Алғышарт</span><span class="sxs-lookup"><span data-stu-id="d1f86-106">Prerequisite</span></span>

- <span data-ttu-id="d1f86-107">Сегментті Customer Insights қызметінен маркетингке экспорттау алдында Dynamics 365 Marketing жүйесінде контакт жазбалары болуы тиіс.</span><span class="sxs-lookup"><span data-stu-id="d1f86-107">Contact records must be present in Dynamics 365 Marketing before you can export a segment from Customer Insights to Marketing.</span></span> <span data-ttu-id="d1f86-108">[Dynamics 365 Marketing жүйесінде Common Data Services](connect-power-query.md) арқылы контактілерді қабылдау жолдары туралы толығырақ оқыңыз.</span><span class="sxs-lookup"><span data-stu-id="d1f86-108">Read more on how to ingest contacts in [Dynamics 365 Marketing using Common Data Services](connect-power-query.md).</span></span>

  > [!NOTE]
  > <span data-ttu-id="d1f86-109">Сегменттерді аудитория туралы түсініктерден маркетингке экспорттау маркетинг даналарында жаңа контакт жазбаларын жасамайды.</span><span class="sxs-lookup"><span data-stu-id="d1f86-109">Exporting segments from audience insights to Marketing will not create new contact records in the Marketing instances.</span></span> <span data-ttu-id="d1f86-110">Маркетингтегі контакт жазбалары аудитория туралы түсінікке қабылданып, деректер көзі ретінде пайдаланылуы тиіс.</span><span class="sxs-lookup"><span data-stu-id="d1f86-110">The contact records from Marketing must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="d1f86-111">Сондай-ақ, оларды сегменттер экспортталмас бұрын тұтынушы идентификаторларын контакт идентификаторларымен салыстыру үшін бірыңғай тұтынушы нысанына қосу қажет.</span><span class="sxs-lookup"><span data-stu-id="d1f86-111">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="configure-the-connector-for-marketing"></a><span data-ttu-id="d1f86-112">Marketing қызметіне арналған қосқышты конфигурациялау</span><span class="sxs-lookup"><span data-stu-id="d1f86-112">Configure the connector for Marketing</span></span>

1. <span data-ttu-id="d1f86-113">Аудитория мәліметтерінде **Әкімші** > **Экспорттау мақсаттары** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="d1f86-113">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="d1f86-114">**Dynamics 365 Marketing** бөлімінде **Орнату** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="d1f86-114">Under **Dynamics 365 Marketing**, select **Set up**.</span></span>

1. <span data-ttu-id="d1f86-115">**Көрсетілетін атауы** өрісінде экспорттық межелі орынға танылатын атау беріңіз.</span><span class="sxs-lookup"><span data-stu-id="d1f86-115">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="d1f86-116">**Сервер мекенжайы** өрісінде ұйымның Marketing URL мекенжайын енгізіңіз.</span><span class="sxs-lookup"><span data-stu-id="d1f86-116">Enter your organization's Marketing URL in the **Server address** field.</span></span>

1. <span data-ttu-id="d1f86-117">**Сервер әкімшісі тіркелгісі** бөлімінде **Жүйеге кіру** опциясын таңдап, Dynamics 365 Marketing тіркелгісін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="d1f86-117">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Marketing account.</span></span>

1. <span data-ttu-id="d1f86-118">Тұтынушы идентификаторы өрісін Dynamics 365 контакт идентификаторына салыңыз.</span><span class="sxs-lookup"><span data-stu-id="d1f86-118">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="d1f86-119">**Келесі** пәрменін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="d1f86-119">Select **Next**.</span></span>

1. <span data-ttu-id="d1f86-120">Бір немесе бірнеше сегментті таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="d1f86-120">Choose one or more segments.</span></span>

1. <span data-ttu-id="d1f86-121">**Сақтау** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="d1f86-121">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="d1f86-122">Деректерді экспорттау</span><span class="sxs-lookup"><span data-stu-id="d1f86-122">Export the data</span></span>

<span data-ttu-id="d1f86-123">[Сұрау бойынша деректерді экспорттауға](export-destinations.md) болады.</span><span class="sxs-lookup"><span data-stu-id="d1f86-123">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="d1f86-124">Экспорттау сондай-ақ әрбір [жоспарланған жаңарту](system.md#schedule-tab) сайын іске қосылады.</span><span class="sxs-lookup"><span data-stu-id="d1f86-124">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]