---
title: LiveRamp коннекторы
description: LiveRamp қызметі үшін қосылымды конфигурациялау және экспорттау жолы туралы ақпарат.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 987457966fe1fc034d9e3cd2a1ce33902c7a84f4
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760334"
---
# <a name="export-segments-to-liverampreg-preview"></a><span data-ttu-id="e45be-103">Сегменттерді LiveRamp&reg; қызметіне экспорттау (алдын ала қарау нұсқасы)</span><span class="sxs-lookup"><span data-stu-id="e45be-103">Export segments to LiveRamp&reg; (preview)</span></span>

<span data-ttu-id="e45be-104">Сандық, әлеуметтік және теледидарлардағы 500-ден астам платформалармен байланыс орнату үшін LiveRamp қызметіндегі деректеріңізді белсендіріңіз.</span><span class="sxs-lookup"><span data-stu-id="e45be-104">Activate your data in LiveRamp to connect with over 500 platforms across digital, social, and TVs.</span></span> <span data-ttu-id="e45be-105">Жарнамалық науқандарды белгілеу, тоқтату және даралау үшін LiveRamp платформасындағы деректермен жұмыс істеңіз.</span><span class="sxs-lookup"><span data-stu-id="e45be-105">Work with your data in LiveRamp to target, suppress, and personalize ad campaigns.</span></span>

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="e45be-106">Қосылым алғышарттары</span><span class="sxs-lookup"><span data-stu-id="e45be-106">Prerequisites for a connection</span></span>

- <span data-ttu-id="e45be-107">Бұл қосқышты пайдалану үшін LiveRamp жазылымы қажет.</span><span class="sxs-lookup"><span data-stu-id="e45be-107">You need a LiveRamp subscription to use this connector.</span></span>
- <span data-ttu-id="e45be-108">Жазылымды алу үшін [LiveRamp платформасына](https://liveramp.com/contact/) байланысыңыз.</span><span class="sxs-lookup"><span data-stu-id="e45be-108">To get a subscription, [contact LiveRamp](https://liveramp.com/contact/) directly.</span></span> <span data-ttu-id="e45be-109">[LiveRamp Onboarding жүйесі жөнінде мәлімет алыңыз](https://liveramp.com/our-platform/data-onboarding/).</span><span class="sxs-lookup"><span data-stu-id="e45be-109">[Learn more about LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).</span></span>

## <a name="set-up-connection-to-liveramp"></a><span data-ttu-id="e45be-110">LiveRamp қызметіне қосылым орнату</span><span class="sxs-lookup"><span data-stu-id="e45be-110">Set up connection to LiveRamp</span></span>

1. <span data-ttu-id="e45be-111">**Әкімші** > **Қосылымдар** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="e45be-111">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="e45be-112">**Қосылым қосу** түймешігін таңдаңыз және қосылымды конфигурациялау үшін **LiveRamp** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="e45be-112">Select **Add connection** and choose **LiveRamp** to configure the connection.</span></span>

1. <span data-ttu-id="e45be-113">**Көрсетілетін аты** өрісінде қосылымға оңай танылатын атау енгізіңіз.</span><span class="sxs-lookup"><span data-stu-id="e45be-113">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="e45be-114">Қосылым атауы мен түрі осы қосылымды сипаттайды.</span><span class="sxs-lookup"><span data-stu-id="e45be-114">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="e45be-115">Қосылымның мақсатын түсіндіретін атауды таңдауды ұсынамыз.</span><span class="sxs-lookup"><span data-stu-id="e45be-115">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="e45be-116">Осы қосылымды кім пайдалана алатынын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="e45be-116">Choose who can use this connection.</span></span> <span data-ttu-id="e45be-117">Егер сіз ешқандай әрекет жасамасаңыз, әдепкі бойынша Әкімшілер болады.</span><span class="sxs-lookup"><span data-stu-id="e45be-117">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="e45be-118">Қосымша ақпарат алу үшін [Салымшыларға экспорттау үшін қосылымды пайдалануға рұқсат беру](connections.md#allow-contributors-to-use-a-connection-for-exports) бөлімін қараңыз.</span><span class="sxs-lookup"><span data-stu-id="e45be-118">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="e45be-119">LiveRamp Secure FTP (SFTP) тіркелгісі үшін **Пайдаланушы аты** мен **Құпиясөзді** енгізіңіз.</span><span class="sxs-lookup"><span data-stu-id="e45be-119">Provide a **Username** and **Password** for your LiveRamp Secure FTP (SFTP) account.</span></span>
<span data-ttu-id="e45be-120">Бұл тіркелгі деректері LiveRamp Onboarding тіркелгі деректерінен өзгеше болуы мүмкін.</span><span class="sxs-lookup"><span data-stu-id="e45be-120">These credentials may be different from your LiveRamp Onboarding credentials.</span></span>

1. <span data-ttu-id="e45be-121">LiveRamp платформасына қосылымды сынау үшін **Тексеру** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="e45be-121">Select **Verify** to test the connection to LiveRamp.</span></span>

1. <span data-ttu-id="e45be-122">Сәтті түрде тексерілгеннен кейін **Мен келісемін** өрісіне құсбелгі қою арқылы **Деректердің құпиялылығы мен сәйкестігі** үшін келісім беріңіз.</span><span class="sxs-lookup"><span data-stu-id="e45be-122">After successful verification, provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span>

1. <span data-ttu-id="e45be-123">Қосылымды аяқтау үшін **Сақтау** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="e45be-123">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="e45be-124">Экспорттауды конфигурациялау</span><span class="sxs-lookup"><span data-stu-id="e45be-124">Configure an export</span></span>

<span data-ttu-id="e45be-125">Егер сіз осы түрдегі қосылымға қатынаса алсаңыз, сіз бұл экспорттауды конфигурациялай аласыз.</span><span class="sxs-lookup"><span data-stu-id="e45be-125">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="e45be-126">Қосымша ақпарат алу үшін [Экспорттауды конфигурациялау үшін қажет рұқсаттар](export-destinations.md#set-up-a-new-export) бөлімін қараңыз.</span><span class="sxs-lookup"><span data-stu-id="e45be-126">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="e45be-127">**Деректер** > **Экспорттау** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="e45be-127">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="e45be-128">Жаңа экспорттау жасау үшін **Мақсатты орын қосу** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="e45be-128">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="e45be-129">**Экспорттауға арналған қосылым** өрісінде LiveRamp бөлімінен қосылым таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="e45be-129">In the **Connection for export** field, choose a connection from the LiveRamp section.</span></span> <span data-ttu-id="e45be-130">Егер сіз осы бөлімнің атын көрмесеңіз, сізге қолжетімді осы түрдегі қосылым жоқ.</span><span class="sxs-lookup"><span data-stu-id="e45be-130">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="e45be-131">**Негізгі идентификаторды таңдау** өрісінде сәйкестік шешімі үшін LiveRamp платформасына жіберу үшін **Электрондық пошта**, **Атауы және мекенжайы** немесе **Телефон** параметрлерін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="e45be-131">In the **Choose your key identifier** field, select **Email**,  **Name and address**, or **Phone** to send to LiveRamp for identity resolution.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e45be-132">![Төлсипаттық салыстыру жүйесі бар LiveRamp қосқышы](media/export-liveramp-segments.png "Төлсипаттық салыстыру жүйесі бар LiveRamp қосқышы")</span><span class="sxs-lookup"><span data-stu-id="e45be-132">![LiveRamp connector with attribute mapping](media/export-liveramp-segments.png "LiveRamp connector with attribute mapping")</span></span>

1. <span data-ttu-id="e45be-133">Таңдалған негізгі идентификаторға арналған бірыңғай тұтынушы нысанының тиісті төлсипаттарын салыстырыңыз.</span><span class="sxs-lookup"><span data-stu-id="e45be-133">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>

1. <span data-ttu-id="e45be-134">LiveRamp қызметіне жіберетін қосымша төлсипаттарды көрсету үшін **Төлсипат қосу** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="e45be-134">Select **Add attribute** to map more attributes to send to LiveRamp.</span></span>

   > [!TIP]
   > <span data-ttu-id="e45be-135">LiveRamp платформасына қосымша негізгі идентификатор төлсипаттарын жіберу жоғары сәйкестендіру жиілігіне алып келеді.</span><span class="sxs-lookup"><span data-stu-id="e45be-135">Sending more key identifier attributes to LiveRamp is likely to get you a higher match rate.</span></span>

1. <span data-ttu-id="e45be-136">LiveRamp платформасына экспорттау қажет сегменттерді таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="e45be-136">Select the segments you want to export to LiveRamp.</span></span>

1. <span data-ttu-id="e45be-137">**Сақтау** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="e45be-137">Select **Save**.</span></span>

<span data-ttu-id="e45be-138">Экспорттауды сақтау экспорттауды бірден іске қоспайды.</span><span class="sxs-lookup"><span data-stu-id="e45be-138">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="e45be-139">Экспорттау әр [жоспарланған жаңартумен](system.md#schedule-tab) іске қосылады.</span><span class="sxs-lookup"><span data-stu-id="e45be-139">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="e45be-140">Сондай-ақ [деректерді сұрау бойынша экспорттауға](export-destinations.md#run-exports-on-demand) болады.</span><span class="sxs-lookup"><span data-stu-id="e45be-140">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="e45be-141">Деректердің құпиялылығы мен сәйкестігі</span><span class="sxs-lookup"><span data-stu-id="e45be-141">Data privacy and compliance</span></span>

<span data-ttu-id="e45be-142">Деректерді Liveramp платформасына жіберу үшін Dynamics 365 Customer Insights бағдарламасын қосқан кезде, Dynamics 365 Customer Insights талаптарына сәйкестік шекарасынан тыс деректерді, соның ішінде жеке деректер сияқты ықтимал құпия деректерді беруге мүмкіндік бересіз.</span><span class="sxs-lookup"><span data-stu-id="e45be-142">When you enable Dynamics 365 Customer Insights to transmit data to Liveramp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="e45be-143">Microsoft мұндай деректерді сіздің нұсқауыңыз бойынша тасымалдайды, бірақ Liveramp платформасының кез келген құпиялылық немесе қауіпсіздік міндеттемелеріне сәйкес келуіне жауап бересіз.</span><span class="sxs-lookup"><span data-stu-id="e45be-143">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Liveramp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="e45be-144">Қосымша ақпаратты [Microsoft құпиялық туралы мәлімдемесі](https://go.microsoft.com/fwlink/?linkid=396732) бөлімінен қараңыз.</span><span class="sxs-lookup"><span data-stu-id="e45be-144">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="e45be-145">Бұл функцияны тоқтату үшін бұл экспорттау мақсатын кез келген уақытта Dynamics 365 Customer Insights әкімшісі жоя алады.</span><span class="sxs-lookup"><span data-stu-id="e45be-145">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
