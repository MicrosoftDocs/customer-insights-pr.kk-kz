---
title: Customer Insights деректерін Dynamics 365 Marketing бағдарламасына экспорттау
description: Dynamics 365 Marketing жүйесіне қосылымды конфигурациялау жолы.
ms.date: 08/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 163387779b64bd78ef08e2d96a5f1c9615062f28
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643780"
---
# <a name="connector-for-dynamics-365-marketing-preview"></a><span data-ttu-id="65de9-103">Dynamics 365 Marketing қосқышы (алдын ала қарау)</span><span class="sxs-lookup"><span data-stu-id="65de9-103">Connector for Dynamics 365 Marketing (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="65de9-104">[Сегменттерді](segments.md) науқандар құру және Dynamics 365 Marketing арқылы тұтынушылардың белгілі бір топтарымен байланысу үшін пайдаланыңыз.</span><span class="sxs-lookup"><span data-stu-id="65de9-104">Use [segments](segments.md) to generate campaigns and contact specific groups of customers with Dynamics 365 Marketing.</span></span> <span data-ttu-id="65de9-105">Қосымша ақпаратты [Dynamics 365 Marketing бар Dynamics 365 Customer Insights сегменттерін пайдалану](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments) бөлімінен қараңыз</span><span class="sxs-lookup"><span data-stu-id="65de9-105">For more information, see [Use segments from Dynamics 365 Customer Insights with Dynamics 365 Marketing](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments)</span></span>

## <a name="prerequisite"></a><span data-ttu-id="65de9-106">Алғышарт</span><span class="sxs-lookup"><span data-stu-id="65de9-106">Prerequisite</span></span>

<span data-ttu-id="65de9-107">[Common Data Service көмегімен қабылданған Dynamics 365 Marketing бағдарламасынан алынған](connect-power-query.md) байланыс жазбалары.</span><span class="sxs-lookup"><span data-stu-id="65de9-107">Contact records [from Dynamics 365 Marketing ingested Common Data Service](connect-power-query.md).</span></span>

## <a name="configure-the-connector-for-marketing"></a><span data-ttu-id="65de9-108">Marketing қызметіне арналған қосқышты конфигурациялау</span><span class="sxs-lookup"><span data-stu-id="65de9-108">Configure the connector for Marketing</span></span>

1. <span data-ttu-id="65de9-109">Аудитория мәліметтерінде **Әкімші** > **Экспорттау мақсаттары** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="65de9-109">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="65de9-110">**Dynamics 365 Marketing** бөлімінде **Орнату** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="65de9-110">Under **Dynamics 365 Marketing**, select **Set up**.</span></span>

1. <span data-ttu-id="65de9-111">**Көрсетілетін атауы** өрісінде экспорттық межелі орынға танылатын атау беріңіз.</span><span class="sxs-lookup"><span data-stu-id="65de9-111">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="65de9-112">**Сервер мекенжайы** өрісінде ұйымның Marketing URL мекенжайын енгізіңіз.</span><span class="sxs-lookup"><span data-stu-id="65de9-112">Enter your organization's Marketing URL in the **Server address** field.</span></span>

1. <span data-ttu-id="65de9-113">**Сервер әкімшісі тіркелгісі** бөлімінде **Жүйеге кіру** опциясын таңдап, Dynamics 365 Marketing тіркелгісін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="65de9-113">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Marketing account.</span></span>

1. <span data-ttu-id="65de9-114">Тұтынушы идентификаторы өрісін Dynamics 365 контакт идентификаторына салыңыз.</span><span class="sxs-lookup"><span data-stu-id="65de9-114">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="65de9-115">**Келесі** пәрменін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="65de9-115">Select **Next**.</span></span>

1. <span data-ttu-id="65de9-116">Бір немесе бірнеше сегментті таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="65de9-116">Choose one or more segments.</span></span>

1. <span data-ttu-id="65de9-117">**Сақтау** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="65de9-117">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="65de9-118">Деректерді экспорттау</span><span class="sxs-lookup"><span data-stu-id="65de9-118">Export the data</span></span>

<span data-ttu-id="65de9-119">[Сұрау бойынша деректерді экспорттауға](export-destinations.md) болады.</span><span class="sxs-lookup"><span data-stu-id="65de9-119">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="65de9-120">Экспорттау сондай-ақ әрбір [жоспарланған жаңарту](system.md#schedule-tab) сайын іске қосылады.</span><span class="sxs-lookup"><span data-stu-id="65de9-120">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>
