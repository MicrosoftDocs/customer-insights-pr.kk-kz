---
title: Customer Insights деректерін Mailchimp нысанына экспорттау
description: Mailchimp қосылымын конфигурациялау жолы туралы ақпарат.
ms.date: 10/26/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 9f86616731c3cc3d26370727103ea9c5d4288c8d
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598208"
---
# <a name="connector-for-mailchimp-preview"></a><span data-ttu-id="8b1a2-103">Mailchimp қосқышы (алдын ала қарау)</span><span class="sxs-lookup"><span data-stu-id="8b1a2-103">Connector for Mailchimp (preview)</span></span>

<span data-ttu-id="8b1a2-104">Ақпараттық хаттар мен электрондық пошта науқандарын құру үшін Mailchimp платформасына бірыңғай тұтынушы профильдерінің сегменттерін экспорттаңыз.</span><span class="sxs-lookup"><span data-stu-id="8b1a2-104">Export segments of unified customer profiles to Mailchimp to create newsletters and email campaigns.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="8b1a2-105">Алғышарттар</span><span class="sxs-lookup"><span data-stu-id="8b1a2-105">Prerequisites</span></span>

-   <span data-ttu-id="8b1a2-106">Сізде [Mailchimp тіркелгісі](https://mailchimp.com/) және тиісті әкімшінің тіркелгі деректері бар.</span><span class="sxs-lookup"><span data-stu-id="8b1a2-106">You have a [Mailchimp account](https://mailchimp.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="8b1a2-107">Mailchimp платформасында қолданыстағы аудиториялар және тиісті идентификаторлар бар.</span><span class="sxs-lookup"><span data-stu-id="8b1a2-107">There are existing audiences in Mailchimp and the corresponding IDs.</span></span> <span data-ttu-id="8b1a2-108">Қосымша ақпарат алу үшін [Mailchimp аудиториялары](https://mailchimp.com/help/create-audience/) бөлімін қараңыз.</span><span class="sxs-lookup"><span data-stu-id="8b1a2-108">For more information, see [Mailchimp audiences](https://mailchimp.com/help/create-audience/).</span></span>
-   <span data-ttu-id="8b1a2-109">Сізде [конфигурацияланған сегменттер](segments.md) бар</span><span class="sxs-lookup"><span data-stu-id="8b1a2-109">You have [configured segments](segments.md)</span></span>
-   <span data-ttu-id="8b1a2-110">Экспортталған сегменттердегі тұтынушылардың бірыңғай профильдері электрондық пошта мекенжайын көрсететін өрістен тұрады.</span><span class="sxs-lookup"><span data-stu-id="8b1a2-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-mailchimp"></a><span data-ttu-id="8b1a2-111">Mailchimp қызметіне қосылу</span><span class="sxs-lookup"><span data-stu-id="8b1a2-111">Connect to Mailchimp</span></span>

1. <span data-ttu-id="8b1a2-112">**Әкімші** > **Экспорттық межелі орындар** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="8b1a2-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="8b1a2-113">**Mailchimp** астындағы **Орнату** пәрменін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="8b1a2-113">Under **Mailchimp**, select **Set up**.</span></span>

1. <span data-ttu-id="8b1a2-114">**Көрсетілетін атауы** өрісінде экспорттық межелі орынға танылатын атау беріңіз.</span><span class="sxs-lookup"><span data-stu-id="8b1a2-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="8b1a2-115">**Деректер құпиялығы мен сәйкестігін** растау үшін **Мен келісемін** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="8b1a2-115">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="8b1a2-116">Mailchimp платформасына қосылуды баптандыру үшін **[Mailchimp аудиториясының идентификаторын](https://mailchimp.com/help/find-audience-id/)** енгізіп, **Қосылу** пәрменін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="8b1a2-116">Enter your **[Mailchimp audience ID](https://mailchimp.com/help/find-audience-id/)** and select **Connect** to initialize the connection to Mailchimp.</span></span>

1. <span data-ttu-id="8b1a2-117">**Mailchimp көмегімен аутентификациялау** пәрменін таңдап, Mailchimp тіркелгі деректерін ұсыныңыз.</span><span class="sxs-lookup"><span data-stu-id="8b1a2-117">Select **Authenticate with Mailchimp** and provide your Mailchimp credentials.</span></span>

1. <span data-ttu-id="8b1a2-118">**Өзіңізді экспорт пайдаланушысы ретінде қосу** пәрменін таңдап, өзіңіздің Customer Insights тіркелгі деректерін ұсыныңыз.</span><span class="sxs-lookup"><span data-stu-id="8b1a2-118">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

   :::image type="content" source="media/export-connect-mailchimp.png" alt-text="Mailchimp қосылымына арналған скриншотты экспорттау":::

1. <span data-ttu-id="8b1a2-120">Экспорттауды теңшеу үшін **Келесі** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="8b1a2-120">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="8b1a2-121">Қосқышты конфигурациялау</span><span class="sxs-lookup"><span data-stu-id="8b1a2-121">Configure the connector</span></span>

1. <span data-ttu-id="8b1a2-122">**Деректерді салыстыру** бөліміндегі **Электрондық пошта** өрісінде тұтынушының электрондық пошта мекенжайын көрсететін бірыңғай тұтынушы профиліндегі өрісті таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="8b1a2-122">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="8b1a2-123">Сонымен қатар **Аты** және **Тегі** өрістерін қосымша жеке электрондық пошталар жасау үшін қосымша өрістер ретінде экспорттауға болады.</span><span class="sxs-lookup"><span data-stu-id="8b1a2-123">Optionally, you can export **First name** and **Last name** as additional fields to create more personalized emails.</span></span> <span data-ttu-id="8b1a2-124">Осы өрістерді салыстыру үшін **Төлсипат қосу** пәрменін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="8b1a2-124">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="8b1a2-125">Экспорттау керек сегменттерді таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="8b1a2-125">Select the segments you want to export.</span></span> <span data-ttu-id="8b1a2-126">Mailchimp платформасына жалпы 1 миллионға дейін тұтынушы профилін экспорттай аласыз.</span><span class="sxs-lookup"><span data-stu-id="8b1a2-126">You can export up to 1 million customer profiles in total to Mailchimp.</span></span>

   :::image type="content" source="media/export-segments-mailchimp.png" alt-text="Mailchimp платформасына экспорттау үшін өрістер мен сегменттерді таңдау":::

1. <span data-ttu-id="8b1a2-128">**Сақтау** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="8b1a2-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="8b1a2-129">Деректерді экспорттау</span><span class="sxs-lookup"><span data-stu-id="8b1a2-129">Export the data</span></span>

<span data-ttu-id="8b1a2-130">[Сұрау бойынша деректерді экспорттауға](export-destinations.md) болады.</span><span class="sxs-lookup"><span data-stu-id="8b1a2-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="8b1a2-131">Экспорттау сондай-ақ әрбір [жоспарланған жаңарту](system.md#schedule-tab) сайын іске қосылады.</span><span class="sxs-lookup"><span data-stu-id="8b1a2-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="8b1a2-132">Mailchimp платформасында, өз сегменттеріңізді [Mailchimp аудиториялары](https://mailchimp.com/help/create-audience/) астынан табуға болады.</span><span class="sxs-lookup"><span data-stu-id="8b1a2-132">In Mailchimp, you can now find your segments under [Mailchimp audiences](https://mailchimp.com/help/create-audience/).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="8b1a2-133">Белгілі шектеулер</span><span class="sxs-lookup"><span data-stu-id="8b1a2-133">Known limitations</span></span>

- <span data-ttu-id="8b1a2-134">Mailchimp нысанына 1 миллионға дейін профильді экспорттауға болады.</span><span class="sxs-lookup"><span data-stu-id="8b1a2-134">Up to 1 million profiles per export to Mailchimp.</span></span>
- <span data-ttu-id="8b1a2-135">Mailchimp нысанына экспорттау тек сегменттермен шектеледі.</span><span class="sxs-lookup"><span data-stu-id="8b1a2-135">Exporting to Mailchimp is limited to segments.</span></span>
- <span data-ttu-id="8b1a2-136">Жалпы саны 1 миллион профильді экспорттайтын сегменттер провайдер тарапынан шектеулер болуына байланысты үш сағатқа созылуы мүмкін.</span><span class="sxs-lookup"><span data-stu-id="8b1a2-136">Exporting segments with a total of 1 million profiles can take up to three hours due to limitations on the provider side.</span></span> 
- <span data-ttu-id="8b1a2-137">Mailchimp нысанына экспорттауға болатын профильдер саны Mailchimp нысанымен жасалған келісім-шартқа байланысты және шектеулі.</span><span class="sxs-lookup"><span data-stu-id="8b1a2-137">The number of profiles that you can export to Mailchimp is dependent and limited on your contract with Mailchimp.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="8b1a2-138">Деректердің құпиялылығы мен сәйкестігі</span><span class="sxs-lookup"><span data-stu-id="8b1a2-138">Data privacy and compliance</span></span>

<span data-ttu-id="8b1a2-139">Деректерді Mailchimp платформасына жіберу үшін Dynamics 365 Customer Insights бағдарламасын қосқан кезде, Dynamics 365 Customer Insights талаптарына сәйкестік шекарасынан тыс деректерді, соның ішінде жеке деректер сияқты ықтимал құпия деректерді беруге мүмкіндік бересіз.</span><span class="sxs-lookup"><span data-stu-id="8b1a2-139">When you enable Dynamics 365 Customer Insights to transmit data to Mailchimp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="8b1a2-140">Microsoft мұндай деректерді сіздің нұсқауыңыз бойынша тасымалдайды, бірақ Mailchimp платформасының кез келген құпиялылық немесе қауіпсіздік міндеттемелеріне сәйкес келуіне жауап бересіз.</span><span class="sxs-lookup"><span data-stu-id="8b1a2-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Mailchimp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="8b1a2-141">Қосымша ақпаратты [Microsoft құпиялық туралы мәлімдемесі](https://go.microsoft.com/fwlink/?linkid=396732) бөлімінен қараңыз.</span><span class="sxs-lookup"><span data-stu-id="8b1a2-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="8b1a2-142">Бұл функцияны тоқтату үшін бұл экспорттау мақсатын кез келген уақытта Dynamics 365 Customer Insights әкімшісі жоя алады.</span><span class="sxs-lookup"><span data-stu-id="8b1a2-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]