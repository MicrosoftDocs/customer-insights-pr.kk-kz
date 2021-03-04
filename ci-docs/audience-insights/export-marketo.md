---
title: Customer Insights деректерін Marketo платформасына экспорттау
description: Marketo қосылымын конфигурациялау жолы туралы ақпарат.
ms.date: 11/12/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: e0245f2d01aabc86f43532822c056965ff7ae67a
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267088"
---
# <a name="connector-for-marketo-preview"></a><span data-ttu-id="e44d9-103">Marketo қосқышы (алдын ала қарау)</span><span class="sxs-lookup"><span data-stu-id="e44d9-103">Connector for Marketo (preview)</span></span>

<span data-ttu-id="e44d9-104">Науқандар жасау үшін тұтынушының біріңғай профильдерінің сегменттерін экспорттап, маркетинг бөліміне хат жіберіңіз және Marketo арқылы тұтынушылардың арнайы топтарын пайдаланыңыз.</span><span class="sxs-lookup"><span data-stu-id="e44d9-104">Export segments of unified customer profiles to generate campaigns, provide email marketing and use specific groups of customers with Marketo.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="e44d9-105">Алғышарттар</span><span class="sxs-lookup"><span data-stu-id="e44d9-105">Prerequisites</span></span>

-   <span data-ttu-id="e44d9-106">Сізде [Marketo тіркелгісі](https://login.marketo.com/) және тиісті әкімшінің тіркелгі деректері бар.</span><span class="sxs-lookup"><span data-stu-id="e44d9-106">You have a [Marketo account](https://login.marketo.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="e44d9-107">Marketo платформасында бұрыннан бар тізімдер және тиісті идентификаторлар бар.</span><span class="sxs-lookup"><span data-stu-id="e44d9-107">There are existing lists in Marketo and the corresponding IDs.</span></span> <span data-ttu-id="e44d9-108">Толық ақпарат алу үшін [Marketo тізімдерін](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists) қараңыз.</span><span class="sxs-lookup"><span data-stu-id="e44d9-108">For more information, see [Marketo lists](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>
-   <span data-ttu-id="e44d9-109">Сізде [конфигурацияланған сегменттер](segments.md) бар.</span><span class="sxs-lookup"><span data-stu-id="e44d9-109">You have [configured segments](segments.md).</span></span>
-   <span data-ttu-id="e44d9-110">Экспортталған сегменттердегі тұтынушылардың бірыңғай профильдері электрондық пошта мекенжайын көрсететін өрістен тұрады.</span><span class="sxs-lookup"><span data-stu-id="e44d9-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-marketo"></a><span data-ttu-id="e44d9-111">Marketo платформасына қосылу</span><span class="sxs-lookup"><span data-stu-id="e44d9-111">Connect to Marketo</span></span>

1. <span data-ttu-id="e44d9-112">**Әкімші** > **Экспорттық межелі орындар** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="e44d9-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="e44d9-113">**Marketo** астындағы **Орнату** пәрменін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="e44d9-113">Under **Marketo**, select **Set up**.</span></span>

1. <span data-ttu-id="e44d9-114">**Көрсетілетін атауы** өрісінде экспорттық межелі орынға танылатын атау беріңіз.</span><span class="sxs-lookup"><span data-stu-id="e44d9-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="e44d9-115">**[Marketo клиент идентификаторы, клиент құпиясы және REST соңғы хост атауын](https://developers.marketo.com/rest-api/authentication/)** енгізіңіз.</span><span class="sxs-lookup"><span data-stu-id="e44d9-115">Enter your **[Marketo client ID, Client secret and REST Endpoint Hostname](https://developers.marketo.com/rest-api/authentication/)**.</span></span>

1. <span data-ttu-id="e44d9-116">**[Marketo тізімінің идентификаторын](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)** енгізіңіз</span><span class="sxs-lookup"><span data-stu-id="e44d9-116">Enter your **[Marketo list ID](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**</span></span> 

1. <span data-ttu-id="e44d9-117">**Деректер құпиялығы және сәйкестігін** растау үшін **Мен келісемін** пәрменін таңдаңыз және Marketo платформасына қосылуды баптандыру үшін **Қосылу** пәрменін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="e44d9-117">Select **I agree** to confirm the **Data privacy and compliance** and select **Connect** to initialize the connection to Marketo.</span></span>

1. <span data-ttu-id="e44d9-118">**Өзіңізді экспорт пайдаланушысы ретінде қосу** пәрменін таңдап, өзіңіздің Customer Insights тіркелгі деректерін ұсыныңыз.</span><span class="sxs-lookup"><span data-stu-id="e44d9-118">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

   :::image type="content" source="media/export-connect-marketo.png" alt-text="Marketo қосылымына арналған скриншотты экспорттау":::

1. <span data-ttu-id="e44d9-120">Экспорттауды теңшеу үшін **Келесі** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="e44d9-120">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="e44d9-121">Қосқышты конфигурациялау</span><span class="sxs-lookup"><span data-stu-id="e44d9-121">Configure the connector</span></span>

1. <span data-ttu-id="e44d9-122">**Деректерді салыстыру** бөліміндегі **Электрондық пошта** өрісінде тұтынушының электрондық пошта мекенжайын көрсететін бірыңғай тұтынушы профиліндегі өрісті таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="e44d9-122">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="e44d9-123">Сонымен қатар **Аты**, **Тегі**, **Қала**, **Облыс** және **Мемлекет/Аймақ** өрістерін қосымша жеке электрондық пошталар жасау үшін қосымша өрістер ретінде экспорттауға болады.</span><span class="sxs-lookup"><span data-stu-id="e44d9-123">Optionally, you can export **First name**, **Last name**, **City**, **State**, and **Country/Region**  as additional fields to create more personalized emails.</span></span> <span data-ttu-id="e44d9-124">Осы өрістерді салыстыру үшін **Төлсипат қосу** пәрменін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="e44d9-124">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="e44d9-125">Экспорттау керек сегменттерді таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="e44d9-125">Select the segments you want to export.</span></span> <span data-ttu-id="e44d9-126">Marketo платформасына жалпы 1 миллионға дейін тұтынушы профилін экспорттай аласыз.</span><span class="sxs-lookup"><span data-stu-id="e44d9-126">You can export up to 1 million customer profiles in total to Marketo.</span></span>

   :::image type="content" source="media/export-segment-marketo.png" alt-text="Marketo платформасына экспорттау үшін өрістер мен сегменттерді таңдау":::

1. <span data-ttu-id="e44d9-128">**Сақтау** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="e44d9-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="e44d9-129">Деректерді экспорттау</span><span class="sxs-lookup"><span data-stu-id="e44d9-129">Export the data</span></span>

<span data-ttu-id="e44d9-130">[Сұрау бойынша деректерді экспорттауға](export-destinations.md) болады.</span><span class="sxs-lookup"><span data-stu-id="e44d9-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="e44d9-131">Экспорттау сондай-ақ әрбір [жоспарланған жаңарту](system.md#schedule-tab) сайын іске қосылады.</span><span class="sxs-lookup"><span data-stu-id="e44d9-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="e44d9-132">Marketo платформасында, өз сегменттеріңізді [Marketo аудиториялары](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists) астынан табуға болады.</span><span class="sxs-lookup"><span data-stu-id="e44d9-132">In Marketo, you can now find your segments under [Marketo lists](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="e44d9-133">Белгілі шектеулер</span><span class="sxs-lookup"><span data-stu-id="e44d9-133">Known limitations</span></span>

- <span data-ttu-id="e44d9-134">Marketo нысанына 1 миллионға дейін профильді экспорттауға болады.</span><span class="sxs-lookup"><span data-stu-id="e44d9-134">Up to 1 million profiles per export to Marketo.</span></span>
- <span data-ttu-id="e44d9-135">Marketo нысанына экспорттау тек сегменттермен шектеледі.</span><span class="sxs-lookup"><span data-stu-id="e44d9-135">Exporting to Marketo is limited to segments.</span></span>
- <span data-ttu-id="e44d9-136">Жалпы саны 1 миллион профилі бар сегменттерді экспорттау 3 сағатқа созылуы мүмкін.</span><span class="sxs-lookup"><span data-stu-id="e44d9-136">Exporting segments with a total of 1 million profiles can take up to 3 hours.</span></span> 
- <span data-ttu-id="e44d9-137">Marketo платформасына экспорттауға болатын профильдер саны Marketo платформасымен жасалған келісім-шартқа байланысты және шектеулі.</span><span class="sxs-lookup"><span data-stu-id="e44d9-137">The number of profiles that you can export to Marketo is dependent and limited on your contract with Marketo.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="e44d9-138">Деректердің құпиялылығы мен сәйкестігі</span><span class="sxs-lookup"><span data-stu-id="e44d9-138">Data privacy and compliance</span></span>

<span data-ttu-id="e44d9-139">Деректерді Marketo платформасына жіберу үшін Dynamics 365 Customer Insights бағдарламасын қосқан кезде, Dynamics 365 Customer Insights талаптарына сәйкестік шекарасынан тыс деректерді, соның ішінде жеке деректер сияқты ықтимал құпия деректерді беруге мүмкіндік бересіз.</span><span class="sxs-lookup"><span data-stu-id="e44d9-139">When you enable Dynamics 365 Customer Insights to transmit data to Marketo, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="e44d9-140">Microsoft мұндай деректерді сіздің нұсқауыңыз бойынша тасымалдайды, бірақ Marketo платформасының кез келген құпиялылық немесе қауіпсіздік міндеттемелеріне сәйкес келуіне жауап бересіз.</span><span class="sxs-lookup"><span data-stu-id="e44d9-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Marketo meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="e44d9-141">Қосымша ақпаратты [Microsoft құпиялық туралы мәлімдемесі](https://go.microsoft.com/fwlink/?linkid=396732) бөлімінен қараңыз.</span><span class="sxs-lookup"><span data-stu-id="e44d9-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="e44d9-142">Бұл функцияны тоқтату үшін бұл экспорттау мақсатын кез келген уақытта Dynamics 365 Customer Insights әкімшісі жоя алады.</span><span class="sxs-lookup"><span data-stu-id="e44d9-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]