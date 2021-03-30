---
title: Customer Insights деректерін DotDigital платформасына экспорттау
description: DotDigital қосылымын конфигурациялау жолы туралы ақпарат.
ms.date: 11/14/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 51a28bdf0de34f0555d8ad7e3d13b2ef8911d417
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598024"
---
# <a name="connector-for-dotdigital-preview"></a><span data-ttu-id="a2c22-103">DotDigital қосқышы (алдын ала қарау)</span><span class="sxs-lookup"><span data-stu-id="a2c22-103">Connector for DotDigital (preview)</span></span>

<span data-ttu-id="a2c22-104">Бірыңғай тұтынушы профильдерінің сегменттерін DotDigital мекенжай кітаптарына экспорттаңыз және оларды науқандар, электрондық пошта маркетингі және dotdigital көмегімен тұтынушы сегменттерін құру үшін пайдаланыңыз.</span><span class="sxs-lookup"><span data-stu-id="a2c22-104">Export segments of unified customer profiles to DotDigital address books and use them for campaigns, email marketing, and to build customer segments with DotDigital.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="a2c22-105">Алғышарттар</span><span class="sxs-lookup"><span data-stu-id="a2c22-105">Prerequisites</span></span>

-   <span data-ttu-id="a2c22-106">Сізде [DotDigital тіркелгісі](https://dotdigital.com/) және тиісті әкімшінің тіркелгі деректері бар.</span><span class="sxs-lookup"><span data-stu-id="a2c22-106">You have a [DotDigital account](https://dotdigital.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="a2c22-107">DotDigital платформасына қолданыстағы мекенжай кітаптары және тиісті идентификаторлар бар.</span><span class="sxs-lookup"><span data-stu-id="a2c22-107">There are existing address books in DotDigital and the corresponding IDs.</span></span> <span data-ttu-id="a2c22-108">Идентификаторды мекенжай кітабын таңдап, ашқан кезде URL мекенжайынан табуға болады.</span><span class="sxs-lookup"><span data-stu-id="a2c22-108">The ID can be found in the URL when you select and open an address book.</span></span> <span data-ttu-id="a2c22-109">Қосымша ақпарат алу үшін [DotDigital мекенжай кітаптарын](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book) қараңыз.</span><span class="sxs-lookup"><span data-stu-id="a2c22-109">For more information, see [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>
-   <span data-ttu-id="a2c22-110">Аудитория түсініктерінде [конфигурацияланған сегменттер](segments.md) бар.</span><span class="sxs-lookup"><span data-stu-id="a2c22-110">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="a2c22-111">Экспортталған сегменттердегі тұтынушылардың бірыңғай профильдері электрондық пошта мекенжайын көрсететін өрістен тұрады.</span><span class="sxs-lookup"><span data-stu-id="a2c22-111">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-dotdigital"></a><span data-ttu-id="a2c22-112">DotDigital бағдарламасына қосу</span><span class="sxs-lookup"><span data-stu-id="a2c22-112">Connect to DotDigital</span></span>

1. <span data-ttu-id="a2c22-113">**Әкімші** > **Экспорттық межелі орындар** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="a2c22-113">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="a2c22-114">**DotDigital** астындағы **Орнату** пәрменін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="a2c22-114">Under **DotDigital**, select **Set up**.</span></span>

1. <span data-ttu-id="a2c22-115">**Көрсетілетін атауы** өрісінде экспорттық межелі орынға танылатын атау беріңіз.</span><span class="sxs-lookup"><span data-stu-id="a2c22-115">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/DotDigital_config.PNG" alt-text="DotDigital экспортына арналған конфигурациялау тақтасы.":::

1. <span data-ttu-id="a2c22-117">**DotDigital пайдаланушы аты мен құпиясөзін** енгізіңіз.</span><span class="sxs-lookup"><span data-stu-id="a2c22-117">Enter your **DotDigital username and password**.</span></span>

1. <span data-ttu-id="a2c22-118">**[DotDigital мекенжай кітабының идентификаторын](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)** енгізіңіз.</span><span class="sxs-lookup"><span data-stu-id="a2c22-118">Enter your **[DotDigital address book ID](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.</span></span>

1. <span data-ttu-id="a2c22-119">**Деректер құпиялығы мен сәйкестігін** растау үшін **Мен келісемін** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="a2c22-119">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="a2c22-120">DotDigital қосылымын баптандыру үшін **Қосылу** пәрменін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="a2c22-120">Select **Connect** to initialize the connection to DotDigital.</span></span>

1. <span data-ttu-id="a2c22-121">**Өзіңізді экспорт пайдаланушысы ретінде қосу** пәрменін таңдап, өзіңіздің Customer Insights тіркелгі деректерін ұсыныңыз.</span><span class="sxs-lookup"><span data-stu-id="a2c22-121">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="a2c22-122">Экспорттауды теңшеу үшін **Келесі** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="a2c22-122">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="a2c22-123">Қосқышты конфигурациялау</span><span class="sxs-lookup"><span data-stu-id="a2c22-123">Configure the connector</span></span>

1. <span data-ttu-id="a2c22-124">**Деректерді салыстыру** бөліміндегі **Электрондық пошта** өрісінде тұтынушының электрондық пошта мекенжайын көрсететін бірыңғай тұтынушы профиліндегі өрісті таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="a2c22-124">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="a2c22-125">**Аты**, **Тегі**, **Толық аты-жөні**, **Жынысы** және **Пошта индексі** сияқты басқа қосымша өрістер үшін сол қадамдарды қайталаңыз.</span><span class="sxs-lookup"><span data-stu-id="a2c22-125">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Full name**, **Gender**, and **Post code**.</span></span>

1. <span data-ttu-id="a2c22-126">Экспорттау керек сегменттерді таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="a2c22-126">Select the segments you want to export.</span></span> <span data-ttu-id="a2c22-127">DotDigital платформасына жалпы 1 миллионға дейін тұтынушы профилін экспорттай аласыз.</span><span class="sxs-lookup"><span data-stu-id="a2c22-127">You can export up to 1 million customer profiles in total to DotDigital.</span></span>

1. <span data-ttu-id="a2c22-128">**Сақтау** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="a2c22-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="a2c22-129">Деректерді экспорттау</span><span class="sxs-lookup"><span data-stu-id="a2c22-129">Export the data</span></span>

<span data-ttu-id="a2c22-130">[Сұрау бойынша деректерді экспорттауға](export-destinations.md) болады.</span><span class="sxs-lookup"><span data-stu-id="a2c22-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="a2c22-131">Экспорттау сондай-ақ әрбір [жоспарланған жаңарту](system.md#schedule-tab) сайын іске қосылады.</span><span class="sxs-lookup"><span data-stu-id="a2c22-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="a2c22-132">DotDigital платформасында [DotDigital мекенжай кітаптарындағы](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book) сегменттерді табуға болады.</span><span class="sxs-lookup"><span data-stu-id="a2c22-132">In DotDigital, you can now find your segments in [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="a2c22-133">Белгілі шектеулер</span><span class="sxs-lookup"><span data-stu-id="a2c22-133">Known limitations</span></span>

- <span data-ttu-id="a2c22-134">DotDigital нысанына 1 миллионға дейін профильді экспорттауға болады.</span><span class="sxs-lookup"><span data-stu-id="a2c22-134">Up to 1 million profiles per export to DotDigital.</span></span>
- <span data-ttu-id="a2c22-135">DotDigital нысанына экспорттау тек сегменттермен шектеледі.</span><span class="sxs-lookup"><span data-stu-id="a2c22-135">Exporting to DotDigital is limited to segments.</span></span>
- <span data-ttu-id="a2c22-136">Жалпы саны 1 миллион профильді экспорттайтын сегменттер провайдер тарапынан шектеулер болғандықтан 3 сағатқа созылуы мүмкін.</span><span class="sxs-lookup"><span data-stu-id="a2c22-136">Exporting segments with a total of 1 million profiles can take up to 3 hours because of limitations on the provider side.</span></span> 
- <span data-ttu-id="a2c22-137">DotDigital платформасына экспорттауға болатын профильдер саны DotDigital платформасымен жасалған келісім-шартқа байланысты және шектеулі.</span><span class="sxs-lookup"><span data-stu-id="a2c22-137">The number of profiles that you can export to DotDigital is dependent and limited on your contract with DotDigital.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="a2c22-138">Деректердің құпиялылығы мен сәйкестігі</span><span class="sxs-lookup"><span data-stu-id="a2c22-138">Data privacy and compliance</span></span>

<span data-ttu-id="a2c22-139">Деректерді DotDigital платформасына жіберу үшін Dynamics 365 Customer Insights бағдарламасын қосқан кезде, Dynamics 365 Customer Insights талаптарына сәйкестік шекарасынан тыс деректерді, соның ішінде жеке деректер сияқты ықтимал құпия деректерді беруге мүмкіндік бересіз.</span><span class="sxs-lookup"><span data-stu-id="a2c22-139">When you enable Dynamics 365 Customer Insights to transmit data to DotDigital, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="a2c22-140">Microsoft мұндай деректерді сіздің нұсқауыңыз бойынша тасымалдайды, бірақ DotDigital кез келген құпиялылық немесе қауіпсіздік міндеттемелеріне сәйкес келуіне жауап бересіз.</span><span class="sxs-lookup"><span data-stu-id="a2c22-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that DotDigital meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="a2c22-141">Қосымша ақпаратты [Microsoft құпиялық туралы мәлімдемесі](https://go.microsoft.com/fwlink/?linkid=396732) бөлімінен қараңыз.</span><span class="sxs-lookup"><span data-stu-id="a2c22-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="a2c22-142">Бұл функцияны тоқтату үшін бұл экспорттау мақсатын кез келген уақытта Dynamics 365 Customer Insights әкімшісі жоя алады.</span><span class="sxs-lookup"><span data-stu-id="a2c22-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]