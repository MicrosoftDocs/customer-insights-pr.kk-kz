---
title: LiveRamp коннекторы
description: Деректерді LiveRamp платформасына экспорттау жолы туралы ақпарат.
ms.date: 12/02/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 6ef4388b0e8ba8bc5866807765d8a872d41c9c14
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597564"
---
# <a name="liverampreg-connector-preview"></a><span data-ttu-id="948e9-103">LiveRamp&reg; қосқышы (алдын ала қарау)</span><span class="sxs-lookup"><span data-stu-id="948e9-103">LiveRamp&reg; connector (preview)</span></span>

<span data-ttu-id="948e9-104">Сандық, әлеуметтік және теледидарлық экожүйелерде 500-ден астам платформаларға қосылу үшін LiveRamp платформасындағы деректерді белсендіріңіз.</span><span class="sxs-lookup"><span data-stu-id="948e9-104">Activate your data in LiveRamp to connect with over 500 platforms across digital, social, and TV ecosystems.</span></span> <span data-ttu-id="948e9-105">Жарнамалық науқандарды белгілеу, тоқтату және даралау үшін LiveRamp платформасындағы деректермен жұмыс істеңіз.</span><span class="sxs-lookup"><span data-stu-id="948e9-105">Work with your data in LiveRamp to target, suppress, and personalize ad campaigns.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="948e9-106">Алғышарттар</span><span class="sxs-lookup"><span data-stu-id="948e9-106">Prerequisites</span></span>

- <span data-ttu-id="948e9-107">Бұл қосқышты пайдалану үшін LiveRamp жазылымы қажет.</span><span class="sxs-lookup"><span data-stu-id="948e9-107">You need a LiveRamp subscription to use this connector.</span></span>
- <span data-ttu-id="948e9-108">Жазылымды алу үшін [LiveRamp платформасына](https://liveramp.com/contact/) байланысыңыз.</span><span class="sxs-lookup"><span data-stu-id="948e9-108">To get a subscription, [contact LiveRamp](https://liveramp.com/contact/) directly.</span></span> <span data-ttu-id="948e9-109">[LiveRamp Onboarding жүйесі жөнінде мәлімет алыңыз](https://liveramp.com/our-platform/data-onboarding/).</span><span class="sxs-lookup"><span data-stu-id="948e9-109">[Learn more about LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).</span></span>

## <a name="connect-to-liveramp"></a><span data-ttu-id="948e9-110">LiveRamp платформасына қосылу</span><span class="sxs-lookup"><span data-stu-id="948e9-110">Connect to LiveRamp</span></span>

1. <span data-ttu-id="948e9-111">Аудитория мәліметтерінде **Әкімші** > **Экспорттау мақсаттары** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="948e9-111">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="948e9-112">**LiveRamp** тақтасында **Орнату** пәрменін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="948e9-112">In the **LiveRamp** tile, select **Set up**.</span></span>

1. <span data-ttu-id="948e9-113">**Көрсетілу аты** өрісінде межелі орынға оңай танылатын атау енгізіңіз.</span><span class="sxs-lookup"><span data-stu-id="948e9-113">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="948e9-114">LiveRamp Secure FTP (SFTP) тіркелгісі үшін **Пайдаланушы аты** мен **Құпиясөзді** енгізіңіз.</span><span class="sxs-lookup"><span data-stu-id="948e9-114">Provide a **Username** and **Password** for your LiveRamp Secure FTP (SFTP) account.</span></span>
<span data-ttu-id="948e9-115">Бұл тіркелгі деректері LiveRamp Onboarding тіркелгі деректерінен өзгеше болуы мүмкін.</span><span class="sxs-lookup"><span data-stu-id="948e9-115">These credentials may be different from your LiveRamp Onboarding credentials.</span></span>

1. <span data-ttu-id="948e9-116">LiveRamp платформасына қосылымды сынау үшін **Тексеру** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="948e9-116">Select **Verify** to test the connection to LiveRamp.</span></span>

1. <span data-ttu-id="948e9-117">Сәтті түрде тексерілгеннен кейін **Мен келісемін** өрісіне құсбелгі қою арқылы **Деректердің құпиялылығы мен сәйкестігі** үшін келісім беріңіз.</span><span class="sxs-lookup"><span data-stu-id="948e9-117">After successful verification, provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span>

1. <span data-ttu-id="948e9-118">LiveRamp қосқышын орнату үшін **Келесі** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="948e9-118">Select **Next** to set up the LiveRamp connector.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="948e9-119">Қосқышты конфигурациялау</span><span class="sxs-lookup"><span data-stu-id="948e9-119">Configure the connector</span></span>

1. <span data-ttu-id="948e9-120">**Негізгі идентификаторды таңдау** өрісінде сәйкестік шешімі үшін LiveRamp платформасына жіберу үшін **Электрондық пошта**, **Атауы және мекенжайы** немесе **Телефон** параметрлерін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="948e9-120">In the **Choose your key identifier** field, select **Email**,  **Name and address**, or **Phone** to send to LiveRamp for identity resolution.</span></span>

1. <span data-ttu-id="948e9-121">Таңдалған негізгі идентификаторға арналған бірыңғай тұтынушы нысанының тиісті төлсипаттарын салыстырыңыз.</span><span class="sxs-lookup"><span data-stu-id="948e9-121">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>

1. <span data-ttu-id="948e9-122">LiveRamp платформасына жіберу үшін қосымша төлсипаттарды салыстыру үшін **Төлсипатты қосу** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="948e9-122">Select **Add attribute** to map additional attributes to send to LiveRamp.</span></span>

   > [!TIP]
   > <span data-ttu-id="948e9-123">LiveRamp платформасына қосымша негізгі идентификатор төлсипаттарын жіберу жоғары сәйкестендіру жиілігіне алып келеді.</span><span class="sxs-lookup"><span data-stu-id="948e9-123">Sending more key identifier attributes to LiveRamp is likely to get you a higher match rate.</span></span>

1. <span data-ttu-id="948e9-124">LiveRamp платформасына экспорттау қажет сегменттерді таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="948e9-124">Select the segments you want to export to LiveRamp.</span></span>

1. <span data-ttu-id="948e9-125">**Сақтау** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="948e9-125">Select **Save**.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="948e9-126">![Төлсипаттық салыстыру жүйесі бар LiveRamp қосқышы](media/export-liveramp-segments.png "Төлсипаттық салыстыру жүйесі бар LiveRamp қосқышы")</span><span class="sxs-lookup"><span data-stu-id="948e9-126">![LiveRamp connector with attribute mapping](media/export-liveramp-segments.png "LiveRamp connector with attribute mapping")</span></span>

## <a name="export-the-data"></a><span data-ttu-id="948e9-127">Деректерді экспорттау</span><span class="sxs-lookup"><span data-stu-id="948e9-127">Export the data</span></span>

<span data-ttu-id="948e9-128">Егер экспорттаудың барлық алғышарттары орындалған болса экспорттау жақын арада басталады.</span><span class="sxs-lookup"><span data-stu-id="948e9-128">The export will start shortly if all prerequisites for export have been completed.</span></span> <span data-ttu-id="948e9-129">Экспорттау сондай-ақ әрбір [жоспарланған жаңарту](system.md#schedule-tab) сайын іске қосылады.</span><span class="sxs-lookup"><span data-stu-id="948e9-129">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>
<span data-ttu-id="948e9-130">Экспорттау сәтті аяқталған соң, деректерді белсендіріп, үлестіру үшін LiveRamp Onboarding жүйесіне кіруге болады.</span><span class="sxs-lookup"><span data-stu-id="948e9-130">Once the export is successfully completed, you can sign in to LiveRamp Onboarding to activate and distribute your data.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="948e9-131">Деректердің құпиялылығы мен сәйкестігі</span><span class="sxs-lookup"><span data-stu-id="948e9-131">Data privacy and compliance</span></span>

<span data-ttu-id="948e9-132">Деректерді Liveramp платформасына жіберу үшін Dynamics 365 Customer Insights бағдарламасын қосқан кезде, Dynamics 365 Customer Insights талаптарына сәйкестік шекарасынан тыс деректерді, соның ішінде жеке деректер сияқты ықтимал құпия деректерді беруге мүмкіндік бересіз.</span><span class="sxs-lookup"><span data-stu-id="948e9-132">When you enable Dynamics 365 Customer Insights to transmit data to Liveramp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="948e9-133">Microsoft мұндай деректерді сіздің нұсқауыңыз бойынша тасымалдайды, бірақ Liveramp платформасының кез келген құпиялылық немесе қауіпсіздік міндеттемелеріне сәйкес келуіне жауап бересіз.</span><span class="sxs-lookup"><span data-stu-id="948e9-133">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Liveramp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="948e9-134">Қосымша ақпаратты [Microsoft құпиялық туралы мәлімдемесі](https://go.microsoft.com/fwlink/?linkid=396732) бөлімінен қараңыз.</span><span class="sxs-lookup"><span data-stu-id="948e9-134">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="948e9-135">Бұл функцияны тоқтату үшін бұл экспорттау мақсатын кез келген уақытта Dynamics 365 Customer Insights әкімшісі жоя алады.</span><span class="sxs-lookup"><span data-stu-id="948e9-135">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]