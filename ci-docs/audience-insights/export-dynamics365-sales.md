---
title: Customer Insights деректерін Dynamics 365 Sales бағдарламасына экспорттау
description: Dynamics 365 Sales жүйесіне қосылымды конфигурациялау жолы.
ms.date: 08/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: af0824e69dfdf620a0ac756e32a9bd3dd85e5151
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643825"
---
# <a name="connector-for-dynamics-365-sales-preview"></a><span data-ttu-id="7e2dc-103">Dynamics 365 Sales қосқышы (алдын ала қарау)</span><span class="sxs-lookup"><span data-stu-id="7e2dc-103">Connector for Dynamics 365 Sales (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="7e2dc-104">Тұтынушы деректерін Dynamics 365 Sales көмегімен маркетинг тізімдерін жасау, жұмыс ағындарын қадағалау және жарнамалар жіберу үшін пайдаланыңыз.</span><span class="sxs-lookup"><span data-stu-id="7e2dc-104">Use your customer data to create marketing lists, follow up workflows, and send out promotions with Dynamics 365 Sales.</span></span>

## <a name="prerequisite"></a><span data-ttu-id="7e2dc-105">Алғышарт</span><span class="sxs-lookup"><span data-stu-id="7e2dc-105">Prerequisite</span></span>

<span data-ttu-id="7e2dc-106">[Common Data Service көмегімен қабылданған Dynamics 365 Sales бағдарламасынан алынған](connect-power-query.md) байланыс жазбалары.</span><span class="sxs-lookup"><span data-stu-id="7e2dc-106">Contact records [from Dynamics 365 Sales ingested using Common Data Service](connect-power-query.md).</span></span>

## <a name="configure-the-connector-for-sales"></a><span data-ttu-id="7e2dc-107">Sales қызметіне арналған қосқышты конфигурациялау</span><span class="sxs-lookup"><span data-stu-id="7e2dc-107">Configure the connector for Sales</span></span>

1. <span data-ttu-id="7e2dc-108">Аудитория мәліметтерінде **Әкімші** > **Экспорттау мақсаттары** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="7e2dc-108">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="7e2dc-109">**Dynamics 365 Sales** бөлімінде **Орнату** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="7e2dc-109">Under **Dynamics 365 Sales**, select **Set up**.</span></span>

1. <span data-ttu-id="7e2dc-110">**Көрсетілетін атауы** өрісінде экспорттық межелі орынға танылатын атау беріңіз.</span><span class="sxs-lookup"><span data-stu-id="7e2dc-110">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="7e2dc-111">**Сервер мекенжайы** өрісінде ұйымның Sales URL мекенжайын енгізіңіз.</span><span class="sxs-lookup"><span data-stu-id="7e2dc-111">Enter your organization's Sales URL in the **Server address** field.</span></span>

1. <span data-ttu-id="7e2dc-112">**Сервер әкімшісі тіркелгісі** бөлімінде **Жүйеге кіру** опциясын таңдап, Dynamics 365 Sales тіркелгісін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="7e2dc-112">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Sales account.</span></span>

1. <span data-ttu-id="7e2dc-113">Тұтынушы идентификаторы өрісін Dynamics 365 контакт идентификаторына салыңыз.</span><span class="sxs-lookup"><span data-stu-id="7e2dc-113">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="7e2dc-114">**Келесі** пәрменін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="7e2dc-114">Select **Next**.</span></span>

1. <span data-ttu-id="7e2dc-115">Бір немесе бірнеше сегментті таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="7e2dc-115">Choose one or more segments.</span></span>

1. <span data-ttu-id="7e2dc-116">**Сақтау** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="7e2dc-116">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="7e2dc-117">Деректерді экспорттау</span><span class="sxs-lookup"><span data-stu-id="7e2dc-117">Export the data</span></span>

<span data-ttu-id="7e2dc-118">[Сұрау бойынша деректерді экспорттауға](export-destinations.md) болады.</span><span class="sxs-lookup"><span data-stu-id="7e2dc-118">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="7e2dc-119">Экспорттау сондай-ақ әрбір [жоспарланған жаңарту](system.md#schedule-tab) сайын іске қосылады.</span><span class="sxs-lookup"><span data-stu-id="7e2dc-119">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>
