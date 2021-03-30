---
title: Customer Insights деректерін Dynamics 365 Sales бағдарламасына экспорттау
description: Dynamics 365 Sales жүйесіне қосылымды конфигурациялау жолы.
ms.date: 02/01/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 39ecdf528c6be4d8fb420a52a6ed998317e43bcd
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598116"
---
# <a name="connector-for-dynamics-365-sales-preview"></a><span data-ttu-id="74614-103">Dynamics 365 Sales қосқышы (алдын ала қарау)</span><span class="sxs-lookup"><span data-stu-id="74614-103">Connector for Dynamics 365 Sales (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="74614-104">Тұтынушы деректерін Dynamics 365 Sales көмегімен маркетинг тізімдерін жасау, жұмыс ағындарын қадағалау және жарнамалар жіберу үшін пайдаланыңыз.</span><span class="sxs-lookup"><span data-stu-id="74614-104">Use your customer data to create marketing lists, follow up workflows, and send out promotions with Dynamics 365 Sales.</span></span>

## <a name="prerequisite"></a><span data-ttu-id="74614-105">Алғышарт</span><span class="sxs-lookup"><span data-stu-id="74614-105">Prerequisite</span></span>

1. <span data-ttu-id="74614-106">Сегментті Customer Insights қызметінен сатылымға экспорттау алдында Dynamics 365 Sales жүйесінде контакт жазбалары болуы тиіс.</span><span class="sxs-lookup"><span data-stu-id="74614-106">Contact records must be present in Dynamics 365 Sales before you can export a segment from Customer Insights to Sales.</span></span> <span data-ttu-id="74614-107">[Dynamics 365 Sales жүйесінде Common Data Services](connect-power-query.md) арқылы контактілерді қабылдау жолдары туралы толығырақ оқыңыз.</span><span class="sxs-lookup"><span data-stu-id="74614-107">Read more on how to ingest contacts in [Dynamics 365 Sales using Common Data Services](connect-power-query.md).</span></span>

   > [!NOTE]
   > <span data-ttu-id="74614-108">Сегменттерді аудитория туралы түсініктерден сатылымға экспорттау сатылым даналарында жаңа контакт жазбаларын жасамайды.</span><span class="sxs-lookup"><span data-stu-id="74614-108">Exporting segments from audience insights to Sales will not create new contact records in the Sales instances.</span></span> <span data-ttu-id="74614-109">Сатылымдағы контакт жазбалары аудитория туралы түсінікке қабылданып, деректер көзі ретінде пайдаланылуы тиіс.</span><span class="sxs-lookup"><span data-stu-id="74614-109">The contact records from Sales must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="74614-110">Сондай-ақ, оларды сегменттер экспортталмас бұрын тұтынушы идентификаторларын контакт идентификаторларымен салыстыру үшін бірыңғай тұтынушы нысанына қосу қажет.</span><span class="sxs-lookup"><span data-stu-id="74614-110">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="configure-the-connector-for-sales"></a><span data-ttu-id="74614-111">Sales қызметіне арналған қосқышты конфигурациялау</span><span class="sxs-lookup"><span data-stu-id="74614-111">Configure the connector for Sales</span></span>

1. <span data-ttu-id="74614-112">Аудитория мәліметтерінде **Әкімші** > **Экспорттау мақсаттары** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="74614-112">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="74614-113">**Dynamics 365 Sales** бөлімінде **Орнату** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="74614-113">Under **Dynamics 365 Sales**, select **Set up**.</span></span>

1. <span data-ttu-id="74614-114">**Көрсетілетін атауы** өрісінде экспорттық межелі орынға танылатын атау беріңіз.</span><span class="sxs-lookup"><span data-stu-id="74614-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="74614-115">**Сервер мекенжайы** өрісінде ұйымның Sales URL мекенжайын енгізіңіз.</span><span class="sxs-lookup"><span data-stu-id="74614-115">Enter your organization's Sales URL in the **Server address** field.</span></span>

1. <span data-ttu-id="74614-116">**Сервер әкімшісі тіркелгісі** бөлімінде **Жүйеге кіру** опциясын таңдап, Dynamics 365 Sales тіркелгісін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="74614-116">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Sales account.</span></span>

1. <span data-ttu-id="74614-117">Тұтынушы идентификаторы өрісін Dynamics 365 контакт идентификаторына салыңыз.</span><span class="sxs-lookup"><span data-stu-id="74614-117">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="74614-118">**Келесі** пәрменін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="74614-118">Select **Next**.</span></span>

1. <span data-ttu-id="74614-119">Бір немесе бірнеше сегментті таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="74614-119">Choose one or more segments.</span></span>

1. <span data-ttu-id="74614-120">**Сақтау** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="74614-120">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="74614-121">Деректерді экспорттау</span><span class="sxs-lookup"><span data-stu-id="74614-121">Export the data</span></span>

<span data-ttu-id="74614-122">[Сұрау бойынша деректерді экспорттауға](export-destinations.md) болады.</span><span class="sxs-lookup"><span data-stu-id="74614-122">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="74614-123">Экспорттау сондай-ақ әрбір [жоспарланған жаңарту](system.md#schedule-tab) сайын іске қосылады.</span><span class="sxs-lookup"><span data-stu-id="74614-123">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]