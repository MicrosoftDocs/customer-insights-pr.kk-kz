---
title: Customer Insights деректерін Google Ads платформасына экспорттау
description: Google Ads платформасына қосылуды конфигурациялау жолы туралы ақпарат.
ms.date: 11/18/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 06aa0b6ff3125d8735adc8c8f9f6dad69087d9f8
ms.sourcegitcommit: ff824bbbd31fd666ab0da682bf48ea31580d242c
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 11/18/2020
ms.locfileid: "4568463"
---
# <a name="connector-for-google-ads-preview"></a><span data-ttu-id="8df30-103">Google Ads қосқышы (алдын ала қарау)</span><span class="sxs-lookup"><span data-stu-id="8df30-103">Connector for Google Ads (preview)</span></span>

<span data-ttu-id="8df30-104">Тұтынушылардың біріңғай профильдерінің сегменттерін Google Ads аудиториясының тізіміне экспорттаңыз және оларды Google Search, Gmail, YouTube және Google көрсету желілерінде жарнамалаңыз.</span><span class="sxs-lookup"><span data-stu-id="8df30-104">Export segments of unified customer profiles to Google Ads audience list and use them to advertise on Google Search, Gmail, YouTube, and Google Display Network.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="8df30-105">Алғышарттар</span><span class="sxs-lookup"><span data-stu-id="8df30-105">Prerequisites</span></span>

-   <span data-ttu-id="8df30-106">Сізде [Google Ads тіркелгісі](https://ads.google.com/) және тиісті әкімшінің тіркелгі деректері бар.</span><span class="sxs-lookup"><span data-stu-id="8df30-106">You have a [Google Ads account](https://ads.google.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="8df30-107">Google Ads платформасында қолданыстағы аудиториялар және тиісті идентификаторлар бар.</span><span class="sxs-lookup"><span data-stu-id="8df30-107">There are existing audiences in Google Ads and the corresponding IDs.</span></span> <span data-ttu-id="8df30-108">Қосымша ақпарат алу үшін [Google Ads аудиториялары](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.) бөлімін қараңыз.</span><span class="sxs-lookup"><span data-stu-id="8df30-108">For more information, see [Google Ads audiences](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).</span></span>
-   <span data-ttu-id="8df30-109">Сізде [конфигурацияланған сегменттер](segments.md) бар</span><span class="sxs-lookup"><span data-stu-id="8df30-109">You have [configured segments](segments.md)</span></span>
-   <span data-ttu-id="8df30-110">Экспортталған сегменттердегі тұтынушылардың бірыңғай профильдері электрондық пошта мекенжайын, аты және тегін көрсететін өрістерден тұрады</span><span class="sxs-lookup"><span data-stu-id="8df30-110">Unified customer profiles in the exported segments contain fields representing an email address, first name, and last name</span></span>

## <a name="connect-to-google-ads"></a><span data-ttu-id="8df30-111">Google Ads қолданбасына қосылу</span><span class="sxs-lookup"><span data-stu-id="8df30-111">Connect to Google Ads</span></span>

1. <span data-ttu-id="8df30-112">**Әкімші** > **Экспорттық межелі орындар** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="8df30-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="8df30-113">**Google Ads** астында **Орнату** пәрменін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="8df30-113">Under **Google Ads**, select **Set up**.</span></span>

1. <span data-ttu-id="8df30-114">**Көрсетілетін атауы** өрісінде экспорттық межелі орынға танылатын атау беріңіз.</span><span class="sxs-lookup"><span data-stu-id="8df30-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="8df30-115">**[Google Ads тұтынушы идентификаторын](https://support.google.com/google-ads/answer/1704344)** енгізіңіз.</span><span class="sxs-lookup"><span data-stu-id="8df30-115">Enter your **[Google Ads customer ID](https://support.google.com/google-ads/answer/1704344)**.</span></span>

1. <span data-ttu-id="8df30-116">**[Google Ads мақұлдаған әзірлеуші таңбалауышын](https://developers.google.com/google-ads/api/docs/first-call/dev-token)** енгізіңіз.</span><span class="sxs-lookup"><span data-stu-id="8df30-116">Enter your **[Google Ads approved developer token](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.</span></span>

1. <span data-ttu-id="8df30-117">**Деректер құпиялығы мен сәйкестігін** растау үшін **Мен келісемін** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="8df30-117">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="8df30-118">Google Ads платформасына қосылуды баптандыру үшін **[Google Ads аудиториясының идентификаторын](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** енгізіп, **Қосылу** пәрменін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="8df30-118">Enter your **[Google Ads audience ID](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** and select **Connect** to initialize the connection to Google Ads.</span></span>

1. <span data-ttu-id="8df30-119">**Google Ads көмегімен аутентификациялау** пәрменін таңдап, Google Ads тіркелгі деректерін ұсыныңыз.</span><span class="sxs-lookup"><span data-stu-id="8df30-119">Select **Authenticate with Google Ads** and provide your Google Ads credentials.</span></span>

1. <span data-ttu-id="8df30-120">**Өзіңізді экспорт пайдаланушысы ретінде қосу** пәрменін таңдап, өзіңіздің Customer Insights тіркелгі деректерін ұсыныңыз.</span><span class="sxs-lookup"><span data-stu-id="8df30-120">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

   :::image type="content" source="media/export-segments-googleads.PNG" alt-text="Google Ads қосылымына арналған скриншотты экспорттау":::

1. <span data-ttu-id="8df30-122">Экспорттауды теңшеу үшін **Келесі** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="8df30-122">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="8df30-123">Қосқышты конфигурациялау</span><span class="sxs-lookup"><span data-stu-id="8df30-123">Configure the connector</span></span>

1. <span data-ttu-id="8df30-124">**Деректерді салыстыру** бөліміндегі **Электрондық пошта** өрісінде тұтынушының электрондық пошта мекенжайын көрсететін бірыңғай тұтынушы профиліндегі өрісті таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="8df30-124">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="8df30-125">**Аты** және **Тегі** өрістері үшін бірдей қадамдарды қайталаңыз.</span><span class="sxs-lookup"><span data-stu-id="8df30-125">Repeat the same steps for \*\*First name" and **Last name** fields.</span></span>

1. <span data-ttu-id="8df30-126">Экспорттау керек сегменттерді таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="8df30-126">Select the segments you want to export.</span></span> <span data-ttu-id="8df30-127">Google Ads платформасына жалпы 1 миллионға дейін тұтынушы профилін экспорттай аласыз.</span><span class="sxs-lookup"><span data-stu-id="8df30-127">You can export up to 1 million customer profiles in total to Google Ads.</span></span>

1. <span data-ttu-id="8df30-128">**Сақтау** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="8df30-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="8df30-129">Деректерді экспорттау</span><span class="sxs-lookup"><span data-stu-id="8df30-129">Export the data</span></span>

<span data-ttu-id="8df30-130">[Сұрау бойынша деректерді экспорттауға](export-destinations.md) болады.</span><span class="sxs-lookup"><span data-stu-id="8df30-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="8df30-131">Экспорттау сондай-ақ әрбір [жоспарланған жаңарту](system.md#schedule-tab) сайын іске қосылады.</span><span class="sxs-lookup"><span data-stu-id="8df30-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="8df30-132">Google Ads платформасында, өз сегменттеріңізді [Google Ads аудиториялары](https://support.google.com/google-ads/answer/7558048?hl=en/) астынан табуға болады.</span><span class="sxs-lookup"><span data-stu-id="8df30-132">In Google Ads, you can now find your segments under [Google Ads audiences](https://support.google.com/google-ads/answer/7558048?hl=en/).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="8df30-133">Белгілі шектеулер</span><span class="sxs-lookup"><span data-stu-id="8df30-133">Known limitations</span></span>

- <span data-ttu-id="8df30-134">Google Ads платформасына 1 миллионға дейін профильді экспорттауға болады.</span><span class="sxs-lookup"><span data-stu-id="8df30-134">Up to 1 million profiles per export to Google Ads.</span></span>
- <span data-ttu-id="8df30-135">Google Ads платформасына экспорттау тек сегменттермен шектеледі.</span><span class="sxs-lookup"><span data-stu-id="8df30-135">Exporting to Google Ads is limited to segments.</span></span>
- <span data-ttu-id="8df30-136">Жалпы саны 1 миллион профильді экспорттайтын сегменттер провайдер тарапынан шектеулер болғандықтан 5 минутқа созылуы мүмкін.</span><span class="sxs-lookup"><span data-stu-id="8df30-136">Exporting segments with a total of 1 million profiles can take up to 5 minutes because of limitations on the provider side.</span></span> 
- <span data-ttu-id="8df30-137">Google Ads платформасында салыстыру 48 сағатқа созылуы мүмкін.</span><span class="sxs-lookup"><span data-stu-id="8df30-137">The matching in Google Ads can take up to 48 hours.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="8df30-138">Деректердің құпиялылығы мен сәйкестігі</span><span class="sxs-lookup"><span data-stu-id="8df30-138">Data privacy and compliance</span></span>

<span data-ttu-id="8df30-139">Деректерді Google Ads платформасына жіберу үшін Dynamics 365 Customer Insights бағдарламасын қосқан кезде, Dynamics 365 Customer Insights талаптарына сәйкестік шекарасынан тыс деректерді, соның ішінде жеке деректер сияқты ықтимал құпия деректерді беруге мүмкіндік бересіз.</span><span class="sxs-lookup"><span data-stu-id="8df30-139">When you enable Dynamics 365 Customer Insights to transmit data to Google Ads, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="8df30-140">Microsoft мұндай деректерді сіздің нұсқауыңыз бойынша тасымалдайды, бірақ Google Ads кез келген құпиялылық немесе қауіпсіздік міндеттемелеріне сәйкес келуіне жауап бересіз.</span><span class="sxs-lookup"><span data-stu-id="8df30-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Google Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="8df30-141">Қосымша ақпаратты [Microsoft құпиялық туралы мәлімдемесі](https://go.microsoft.com/fwlink/?linkid=396732) бөлімінен қараңыз.</span><span class="sxs-lookup"><span data-stu-id="8df30-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="8df30-142">Бұл функцияны тоқтату үшін бұл экспорттау мақсатын кез келген уақытта Dynamics 365 Customer Insights әкімшісі жоя алады.</span><span class="sxs-lookup"><span data-stu-id="8df30-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
