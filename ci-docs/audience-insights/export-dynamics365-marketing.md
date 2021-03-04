---
title: Customer Insights деректерін Dynamics 365 Marketing бағдарламасына экспорттау
description: Dynamics 365 Marketing жүйесіне қосылымды конфигурациялау жолы.
ms.date: 02/01/2021
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: a06920b8ff25d7102ccd14ae68cf42fe91fa1ee6
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269061"
---
# <a name="connector-for-dynamics-365-marketing-preview"></a><span data-ttu-id="0044d-103">Dynamics 365 Marketing қосқышы (алдын ала қарау)</span><span class="sxs-lookup"><span data-stu-id="0044d-103">Connector for Dynamics 365 Marketing (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="0044d-104">[Сегменттерді](segments.md) науқандар құру және Dynamics 365 Marketing арқылы тұтынушылардың белгілі бір топтарымен байланысу үшін пайдаланыңыз.</span><span class="sxs-lookup"><span data-stu-id="0044d-104">Use [segments](segments.md) to generate campaigns and contact specific groups of customers with Dynamics 365 Marketing.</span></span> <span data-ttu-id="0044d-105">Қосымша ақпаратты [Dynamics 365 Marketing бар Dynamics 365 Customer Insights сегменттерін пайдалану](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments) бөлімінен қараңыз</span><span class="sxs-lookup"><span data-stu-id="0044d-105">For more information, see [Use segments from Dynamics 365 Customer Insights with Dynamics 365 Marketing](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments)</span></span>

## <a name="prerequisite"></a><span data-ttu-id="0044d-106">Алғышарт</span><span class="sxs-lookup"><span data-stu-id="0044d-106">Prerequisite</span></span>

- <span data-ttu-id="0044d-107">Сегментті Customer Insights қызметінен маркетингке экспорттау алдында Dynamics 365 Marketing жүйесінде контакт жазбалары болуы тиіс.</span><span class="sxs-lookup"><span data-stu-id="0044d-107">Contact records must be present in Dynamics 365 Marketing before you can export a segment from Customer Insights to Marketing.</span></span> <span data-ttu-id="0044d-108">[Dynamics 365 Marketing жүйесінде Common Data Services](connect-power-query.md) арқылы контактілерді қабылдау жолдары туралы толығырақ оқыңыз.</span><span class="sxs-lookup"><span data-stu-id="0044d-108">Read more on how to ingest contacts in [Dynamics 365 Marketing using Common Data Services](connect-power-query.md).</span></span>

  > [!NOTE]
  > <span data-ttu-id="0044d-109">Сегменттерді аудитория туралы түсініктерден маркетингке экспорттау маркетинг даналарында жаңа контакт жазбаларын жасамайды.</span><span class="sxs-lookup"><span data-stu-id="0044d-109">Exporting segments from audience insights to Marketing will not create new contact records in the Marketing instances.</span></span> <span data-ttu-id="0044d-110">Маркетингтегі контакт жазбалары аудитория туралы түсінікке қабылданып, деректер көзі ретінде пайдаланылуы тиіс.</span><span class="sxs-lookup"><span data-stu-id="0044d-110">The contact records from Marketing must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="0044d-111">Сондай-ақ, оларды сегменттер экспортталмас бұрын тұтынушы идентификаторларын контакт идентификаторларымен салыстыру үшін бірыңғай тұтынушы нысанына қосу қажет.</span><span class="sxs-lookup"><span data-stu-id="0044d-111">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="configure-the-connector-for-marketing"></a><span data-ttu-id="0044d-112">Marketing қызметіне арналған қосқышты конфигурациялау</span><span class="sxs-lookup"><span data-stu-id="0044d-112">Configure the connector for Marketing</span></span>

1. <span data-ttu-id="0044d-113">Аудитория мәліметтерінде **Әкімші** > **Экспорттау мақсаттары** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="0044d-113">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="0044d-114">**Dynamics 365 Marketing** бөлімінде **Орнату** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="0044d-114">Under **Dynamics 365 Marketing**, select **Set up**.</span></span>

1. <span data-ttu-id="0044d-115">**Көрсетілетін атауы** өрісінде экспорттық межелі орынға танылатын атау беріңіз.</span><span class="sxs-lookup"><span data-stu-id="0044d-115">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="0044d-116">**Сервер мекенжайы** өрісінде ұйымның Marketing URL мекенжайын енгізіңіз.</span><span class="sxs-lookup"><span data-stu-id="0044d-116">Enter your organization's Marketing URL in the **Server address** field.</span></span>

1. <span data-ttu-id="0044d-117">**Сервер әкімшісі тіркелгісі** бөлімінде **Жүйеге кіру** опциясын таңдап, Dynamics 365 Marketing тіркелгісін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="0044d-117">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Marketing account.</span></span>

1. <span data-ttu-id="0044d-118">Тұтынушы идентификаторы өрісін Dynamics 365 контакт идентификаторына салыңыз.</span><span class="sxs-lookup"><span data-stu-id="0044d-118">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="0044d-119">**Келесі** пәрменін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="0044d-119">Select **Next**.</span></span>

1. <span data-ttu-id="0044d-120">Бір немесе бірнеше сегментті таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="0044d-120">Choose one or more segments.</span></span>

1. <span data-ttu-id="0044d-121">**Сақтау** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="0044d-121">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="0044d-122">Деректерді экспорттау</span><span class="sxs-lookup"><span data-stu-id="0044d-122">Export the data</span></span>

<span data-ttu-id="0044d-123">[Сұрау бойынша деректерді экспорттауға](export-destinations.md) болады.</span><span class="sxs-lookup"><span data-stu-id="0044d-123">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="0044d-124">Экспорттау сондай-ақ әрбір [жоспарланған жаңарту](system.md#schedule-tab) сайын іске қосылады.</span><span class="sxs-lookup"><span data-stu-id="0044d-124">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]