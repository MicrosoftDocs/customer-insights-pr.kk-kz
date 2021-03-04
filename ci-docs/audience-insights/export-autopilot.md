---
title: Customer Insights деректерін Autopilot нысанына экспорттау
description: Autopilot қосылымын конфигурациялау жолы туралы ақпарат.
ms.date: 12/08/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 33a8cd1ae4a77ce2248bc2805d25687c9a2c2732
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269245"
---
# <a name="connector-for-autopilot-preview"></a><span data-ttu-id="729ac-103">Autopilot қосқышы (алдын ала қарау)</span><span class="sxs-lookup"><span data-stu-id="729ac-103">Connector for Autopilot (preview)</span></span>

<span data-ttu-id="729ac-104">Тұтынушылардың бірыңғай профильдерінің сегменттерін Autopilot жүйесіне экспорттап, оларды Autopilot жүйесіндегі электрондық пошта маркетингі үшін пайдаланыңыз.</span><span class="sxs-lookup"><span data-stu-id="729ac-104">Export segments of unified customer profiles to Autopilot and use them for email marketing in Autopilot.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="729ac-105">Алғышарттар</span><span class="sxs-lookup"><span data-stu-id="729ac-105">Prerequisites</span></span>

-   <span data-ttu-id="729ac-106">Сізде [Autopilot тіркелгісі](https://www.autopilothq.com/) және тиісті әкімшінің тіркелгі деректері бар.</span><span class="sxs-lookup"><span data-stu-id="729ac-106">You have an [Autopilot account](https://www.autopilothq.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="729ac-107">Аудитория түсініктерінде [конфигурацияланған сегменттер](segments.md) бар.</span><span class="sxs-lookup"><span data-stu-id="729ac-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="729ac-108">Экспортталған сегменттердегі тұтынушылардың бірыңғай профильдері электрондық пошта мекенжайын көрсететін өрістен тұрады.</span><span class="sxs-lookup"><span data-stu-id="729ac-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-autopilot"></a><span data-ttu-id="729ac-109">AutoPilot жүйесіне қосылу</span><span class="sxs-lookup"><span data-stu-id="729ac-109">Connect to Autopilot</span></span>

1. <span data-ttu-id="729ac-110">**Әкімші** > **Экспорттық межелі орындар** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="729ac-110">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="729ac-111">**Autopilot** бөлімінде **Орнату** пәрменін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="729ac-111">Under **Autopilot**, select **Set up**.</span></span>

1. <span data-ttu-id="729ac-112">**Көрсетілетін атауы** өрісінде экспорттық межелі орынға танылатын атау беріңіз.</span><span class="sxs-lookup"><span data-stu-id="729ac-112">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/export-autopilot.PNG" alt-text="Autopilot қосылымына арналған конфигурация тақтасы.":::

1. <span data-ttu-id="729ac-114">**Autopilot API кілті** [Autopilot API кілтің](https://autopilot.docs.apiary.io/#) енгізіңіз.</span><span class="sxs-lookup"><span data-stu-id="729ac-114">Enter your **Autopilot API key** [Autopilot API key](https://autopilot.docs.apiary.io/#).</span></span>

1. <span data-ttu-id="729ac-115">**Деректер құпиялығы мен сәйкестігін** растау үшін **Мен келісемін** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="729ac-115">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="729ac-116">Autopilot қосылымын баптандыру үшін **Қосылу** пәрменін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="729ac-116">Select **Connect** to initialize the connection to Autopilot.</span></span>

1. <span data-ttu-id="729ac-117">**Өзіңізді экспорт пайдаланушысы ретінде қосу** пәрменін таңдап, өзіңіздің Customer Insights тіркелгі деректерін ұсыныңыз.</span><span class="sxs-lookup"><span data-stu-id="729ac-117">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="729ac-118">Экспорттауды теңшеу үшін **Келесі** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="729ac-118">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="729ac-119">Қосқышты конфигурациялау</span><span class="sxs-lookup"><span data-stu-id="729ac-119">Configure the connector</span></span>

1. <span data-ttu-id="729ac-120">**Деректерді салыстыру** бөліміндегі **Электрондық пошта** өрісінде тұтынушының электрондық пошта мекенжайын көрсететін бірыңғай тұтынушы профиліндегі өрісті таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="729ac-120">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="729ac-121">**Аты**, **Тегі** секілді басқа қосымша өрістер үшін сол қадамдарды қайталаңыз.</span><span class="sxs-lookup"><span data-stu-id="729ac-121">Repeat the same steps for other optional fields such as **First name**, **Last name**.</span></span>

1. <span data-ttu-id="729ac-122">Экспорттау керек сегменттерді таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="729ac-122">Select the segments you want to export.</span></span> <span data-ttu-id="729ac-123">Біз Autopilot жүйесіне **100000-нан астам тұтынушы профильдерін экспорттамауға кеңес береміз**.</span><span class="sxs-lookup"><span data-stu-id="729ac-123">We strongly **recommend to not export more than 100'000 customer profiles in total** to Autopilot.</span></span> 

1. <span data-ttu-id="729ac-124">**Сақтау** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="729ac-124">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="729ac-125">Деректерді экспорттау</span><span class="sxs-lookup"><span data-stu-id="729ac-125">Export the data</span></span>

<span data-ttu-id="729ac-126">[Сұрау бойынша деректерді экспорттауға](export-destinations.md) болады.</span><span class="sxs-lookup"><span data-stu-id="729ac-126">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="729ac-127">Экспорттау сондай-ақ әрбір [жоспарланған жаңарту](system.md#schedule-tab) сайын іске қосылады.</span><span class="sxs-lookup"><span data-stu-id="729ac-127">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="729ac-128">Белгілі шектеулер</span><span class="sxs-lookup"><span data-stu-id="729ac-128">Known limitations</span></span>

- <span data-ttu-id="729ac-129">Autopilot платформасына жалпы 100000-ға дейін профильді экспорттай аласыз.</span><span class="sxs-lookup"><span data-stu-id="729ac-129">You can export up to 100'000 profiles in total to Autopilot.</span></span>
- <span data-ttu-id="729ac-130">Autopilot нысанына экспорттау тек сегменттермен шектеледі.</span><span class="sxs-lookup"><span data-stu-id="729ac-130">Exporting to Autopilot is limited to segments.</span></span>
- <span data-ttu-id="729ac-131">Autopilot жүйесіне 100000 дейін профильді экспорттау бірнеше сағатқа созылуы мүмкін.</span><span class="sxs-lookup"><span data-stu-id="729ac-131">Exporting up to 100'000 profiles to Autopilot can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="729ac-132">Autopilot нысанына экспорттауға болатын профильдер саны Autopilot нысанымен жасалған келісімшартқа байланысты және шектеулі.</span><span class="sxs-lookup"><span data-stu-id="729ac-132">The number of profiles that you can export to Autopilot is dependent and limited on your contract with Autopilot.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="729ac-133">Деректердің құпиялылығы мен сәйкестігі</span><span class="sxs-lookup"><span data-stu-id="729ac-133">Data privacy and compliance</span></span>

<span data-ttu-id="729ac-134">Деректерді Autopilot платформасына жіберу үшін Dynamics 365 Customer Insights бағдарламасын қосқан кезде, Dynamics 365 Customer Insights талаптарына сәйкестік шекарасынан тыс деректерді, соның ішінде жеке деректер сияқты ықтимал құпия деректерді беруге мүмкіндік бересіз.</span><span class="sxs-lookup"><span data-stu-id="729ac-134">When you enable Dynamics 365 Customer Insights to transmit data to Autopilot, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="729ac-135">Microsoft мұндай деректерді сіздің нұсқауыңыз бойынша тасымалдайды, бірақ Autopilot кез келген құпиялылық немесе қауіпсіздік міндеттемелеріне сәйкес келуіне жауап бересіз.</span><span class="sxs-lookup"><span data-stu-id="729ac-135">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Autopilot meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="729ac-136">Қосымша ақпаратты [Microsoft құпиялық туралы мәлімдемесі](https://go.microsoft.com/fwlink/?linkid=396732) бөлімінен қараңыз.</span><span class="sxs-lookup"><span data-stu-id="729ac-136">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="729ac-137">Бұл функцияны тоқтату үшін бұл экспорттау мақсатын кез келген уақытта Dynamics 365 Customer Insights әкімшісі жоя алады.</span><span class="sxs-lookup"><span data-stu-id="729ac-137">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]