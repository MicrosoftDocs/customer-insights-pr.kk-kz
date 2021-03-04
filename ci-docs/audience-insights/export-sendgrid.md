---
title: Customer Insights деректерін SendGrid нысанына экспорттау
description: SendGrid қосылымын конфигурациялау жолы туралы ақпарат.
ms.date: 12/08/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: f16d69deb2a0b48270ed04f9b72f03056f20b619
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268739"
---
# <a name="connector-for-sendgrid-preview"></a><span data-ttu-id="dcd40-103">SendGrid қосқышы (алдын ала қарау)</span><span class="sxs-lookup"><span data-stu-id="dcd40-103">Connector for SendGrid (preview)</span></span>

<span data-ttu-id="dcd40-104">Тұтынушылардың бірыңғай профильдерінің сегменттерін Autopilot контактілер тізіміне экспорттап, оларды SendGrid жүйесіндегі науқандар мен электрондық пошта маркетингі үшін пайдаланыңыз.</span><span class="sxs-lookup"><span data-stu-id="dcd40-104">Export segments of unified customer profiles to SendGrid contact lists and use them for campaigns and email marketing in SendGrid.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="dcd40-105">Алғышарттар</span><span class="sxs-lookup"><span data-stu-id="dcd40-105">Prerequisites</span></span>

-   <span data-ttu-id="dcd40-106">Сізде [SendGrid тіркелгісі](https://sendgrid.com/) және тиісті әкімшінің тіркелгі деректері бар.</span><span class="sxs-lookup"><span data-stu-id="dcd40-106">You have a [SendGrid account](https://sendgrid.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="dcd40-107">SendGrid платформасында бұрыннан бар контактілер тізімдері және тиісті идентификаторлар бар.</span><span class="sxs-lookup"><span data-stu-id="dcd40-107">There are existing contact lists in SendGrid and the corresponding IDs.</span></span> <span data-ttu-id="dcd40-108">Қосымша ақпарат алу үшін [SendGrid - Контактілерді басқару](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts) бөлімін қараңыз.</span><span class="sxs-lookup"><span data-stu-id="dcd40-108">For more information, see [SendGrid - Manage contacts](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).</span></span>
-   <span data-ttu-id="dcd40-109">Аудитория түсініктерінде [конфигурацияланған сегменттер](segments.md) бар.</span><span class="sxs-lookup"><span data-stu-id="dcd40-109">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="dcd40-110">Экспортталған сегменттердегі тұтынушылардың бірыңғай профильдері электрондық пошта мекенжайын көрсететін өрістен тұрады.</span><span class="sxs-lookup"><span data-stu-id="dcd40-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-sendgrid"></a><span data-ttu-id="dcd40-111">SendGrid жүйесіне қосылу</span><span class="sxs-lookup"><span data-stu-id="dcd40-111">Connect to SendGrid</span></span>

1. <span data-ttu-id="dcd40-112">**Әкімші** > **Экспорттық межелі орындар** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="dcd40-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="dcd40-113">**SendGrid** бөлімінде **Орнату** пәрменін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="dcd40-113">Under **SendGrid**, select **Set up**.</span></span>

1. <span data-ttu-id="dcd40-114">**Көрсетілетін атауы** өрісінде экспорттық межелі орынға танылатын атау беріңіз.</span><span class="sxs-lookup"><span data-stu-id="dcd40-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/export-sendgrid.PNG" alt-text="SendGrid экспорттауының конфигурациялық тақтасы.":::

1. <span data-ttu-id="dcd40-116">**SendGrid API кілтін** [SendGrid API кілті](https://sendgrid.com/docs/ui/account-and-settings/api-keys/) енгізіңіз.</span><span class="sxs-lookup"><span data-stu-id="dcd40-116">Enter your **SendGrid API key** [SendGrid API key](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).</span></span>

1. <span data-ttu-id="dcd40-117">**[SendGrid тізімінің идентификаторын](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)** енгізіңіз.</span><span class="sxs-lookup"><span data-stu-id="dcd40-117">Enter your **[SendGrid list ID](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.</span></span>

1. <span data-ttu-id="dcd40-118">**Деректер құпиялығы мен сәйкестігін** растау үшін **Мен келісемін** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="dcd40-118">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="dcd40-119">SendGrid қосылымын баптандыру үшін **Қосылу** пәрменін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="dcd40-119">Select **Connect** to initialize the connection to SendGrid.</span></span>

1. <span data-ttu-id="dcd40-120">**Өзіңізді экспорт пайдаланушысы ретінде қосу** пәрменін таңдап, өзіңіздің Customer Insights тіркелгі деректерін ұсыныңыз.</span><span class="sxs-lookup"><span data-stu-id="dcd40-120">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="dcd40-121">Экспорттауды теңшеу үшін **Келесі** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="dcd40-121">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="dcd40-122">Қосқышты конфигурациялау</span><span class="sxs-lookup"><span data-stu-id="dcd40-122">Configure the connector</span></span>

1. <span data-ttu-id="dcd40-123">**Деректерді салыстыру** бөліміндегі **Электрондық пошта** өрісінде тұтынушының электрондық пошта мекенжайын көрсететін бірыңғай тұтынушы профиліндегі өрісті таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="dcd40-123">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="dcd40-124">**Аты**, **Тегі**, **Ел/аймақ**, **Облыс**, **Қала** және **Пошта индексі** секілді басқа қосымша өрістер үшін сол қадамдарды қайталаңыз.</span><span class="sxs-lookup"><span data-stu-id="dcd40-124">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Country/Region**, **State**, **City**, and **Post code**.</span></span>

1. <span data-ttu-id="dcd40-125">Экспорттау керек сегменттерді таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="dcd40-125">Select the segments you want to export.</span></span> <span data-ttu-id="dcd40-126">Біз SendGrid жүйесіне **100000-нан астам тұтынушы профильдерін экспорттамауға кеңес береміз**.</span><span class="sxs-lookup"><span data-stu-id="dcd40-126">We strongly **recommend to not export more than 100'000 customer profiles in total** to SendGrid.</span></span> 

1. <span data-ttu-id="dcd40-127">**Сақтау** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="dcd40-127">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="dcd40-128">Деректерді экспорттау</span><span class="sxs-lookup"><span data-stu-id="dcd40-128">Export the data</span></span>

<span data-ttu-id="dcd40-129">[Сұрау бойынша деректерді экспорттауға](export-destinations.md) болады.</span><span class="sxs-lookup"><span data-stu-id="dcd40-129">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="dcd40-130">Экспорттау сондай-ақ әрбір [жоспарланған жаңарту](system.md#schedule-tab) сайын іске қосылады.</span><span class="sxs-lookup"><span data-stu-id="dcd40-130">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="dcd40-131">Белгілі шектеулер</span><span class="sxs-lookup"><span data-stu-id="dcd40-131">Known limitations</span></span>

- <span data-ttu-id="dcd40-132">SendGrid жүйесінде барлығы 100000 профильге дейін.</span><span class="sxs-lookup"><span data-stu-id="dcd40-132">Up to 100'000 profiles in total to SendGrid.</span></span>
- <span data-ttu-id="dcd40-133">SendGrid нысанына экспорттау тек сегменттермен шектеледі.</span><span class="sxs-lookup"><span data-stu-id="dcd40-133">Exporting to SendGrid is limited to segments.</span></span>
- <span data-ttu-id="dcd40-134">SendGrid жүйесіне 100000 дейін профильді экспорттау бірнеше сағатқа созылуы мүмкін.</span><span class="sxs-lookup"><span data-stu-id="dcd40-134">Exporting up to 100'000 profiles to SendGrid can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="dcd40-135">SendGrid нысанына экспорттауға болатын профильдер саны SendGrid нысанымен жасалған келісімшартқа байланысты және шектеулі.</span><span class="sxs-lookup"><span data-stu-id="dcd40-135">The number of profiles that you can export to SendGrid is dependent and limited on your contract with SendGrid.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="dcd40-136">Деректердің құпиялылығы мен сәйкестігі</span><span class="sxs-lookup"><span data-stu-id="dcd40-136">Data privacy and compliance</span></span>

<span data-ttu-id="dcd40-137">Деректерді SendGrid платформасына жіберу үшін Dynamics 365 Customer Insights бағдарламасын қосқан кезде, Dynamics 365 Customer Insights талаптарына сәйкестік шекарасынан тыс деректерді, соның ішінде жеке деректер сияқты ықтимал құпия деректерді беруге мүмкіндік бересіз.</span><span class="sxs-lookup"><span data-stu-id="dcd40-137">When you enable Dynamics 365 Customer Insights to transmit data to SendGrid, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="dcd40-138">Microsoft мұндай деректерді сіздің нұсқауыңыз бойынша тасымалдайды, бірақ SendGrid кез келген құпиялылық немесе қауіпсіздік міндеттемелеріне сәйкес келуіне жауап бересіз.</span><span class="sxs-lookup"><span data-stu-id="dcd40-138">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that SendGrid meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="dcd40-139">Қосымша ақпаратты [Microsoft құпиялық туралы мәлімдемесі](https://go.microsoft.com/fwlink/?linkid=396732) бөлімінен қараңыз.</span><span class="sxs-lookup"><span data-stu-id="dcd40-139">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="dcd40-140">Бұл функцияны тоқтату үшін бұл экспорттау мақсатын кез келген уақытта Dynamics 365 Customer Insights әкімшісі жоя алады.</span><span class="sxs-lookup"><span data-stu-id="dcd40-140">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]