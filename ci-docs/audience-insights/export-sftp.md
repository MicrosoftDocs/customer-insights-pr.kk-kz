---
title: Customer Insights деректерін SFTP хосттарына экспорттау
description: SFTP орны үшін қосылымды конфигурациялау және экспорттау жолы туралы ақпарат.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 96c6026aded315008439740646827ca910cead90
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760426"
---
# <a name="export-segment-lists-and-other-data-to-sftp-preview"></a><span data-ttu-id="02ad8-103">Сегмент тізімдерін және басқа деректерді SFTP қызметіне экспорттау (алдын ала қарау нұсқасы)</span><span class="sxs-lookup"><span data-stu-id="02ad8-103">Export segment lists and other data to SFTP (preview)</span></span>

<span data-ttu-id="02ad8-104">Тұтынушы деректерін үшінші тарап бағдарламаларында оларды файлдарды қауіпсіз тасымалдау протоколының (SFTP) орнына экспорттау арқылы пайдаланыңыз.</span><span class="sxs-lookup"><span data-stu-id="02ad8-104">Use your customer data in third-party applications by exporting them to a Secure File Transfer Protocol (SFTP) location.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="02ad8-105">Қосылым алғышарттары</span><span class="sxs-lookup"><span data-stu-id="02ad8-105">Prerequisites for connection</span></span>

- <span data-ttu-id="02ad8-106">SFTP хостының және тиісті тіркелгі деректерінің қолжетімділігі.</span><span class="sxs-lookup"><span data-stu-id="02ad8-106">Availability of an SFTP host and corresponding credentials.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="02ad8-107">Белгілі шектеулер</span><span class="sxs-lookup"><span data-stu-id="02ad8-107">Known limitations</span></span>

- <span data-ttu-id="02ad8-108">Экспорттаудың жұмыс уақыты жүйенің жұмысына байланысты.</span><span class="sxs-lookup"><span data-stu-id="02ad8-108">The runtime of an export depends on your system performance.</span></span> <span data-ttu-id="02ad8-109">Сервердің минималды конфигурациясы ретінде екі CPU оперативті жады мен 1 Гб жадты ұсынамыз.</span><span class="sxs-lookup"><span data-stu-id="02ad8-109">We recommend two CPU cores and 1 Gb of memory as minimal configuration of your server.</span></span> 
- <span data-ttu-id="02ad8-110">100 миллионға дейін тұтынушы профильдері бар нысандарды экспорттау процессордың екі оперативті жады мен 1 Гб жадының ұсынылған минималды конфигурациясын пайдалану кезінде 90 минутты алуы мүмкін.</span><span class="sxs-lookup"><span data-stu-id="02ad8-110">Exporting entities with up to 100 million customer profiles can take 90 minutes when using the recommended minimal configuration of two CPU cores and 1 Gb of memory.</span></span> 

## <a name="set-up-connection-to-sftp"></a><span data-ttu-id="02ad8-111">SFTP қызметіне қосылым орнату</span><span class="sxs-lookup"><span data-stu-id="02ad8-111">Set up connection to SFTP</span></span>

1. <span data-ttu-id="02ad8-112">**Әкімші** > **Қосылымдар** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="02ad8-112">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="02ad8-113">**Қосылым қосу** түймешігін таңдаңыз және қосылымды конфигурациялау үшін **SFTP** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="02ad8-113">Select **Add connection** and choose **SFTP** to configure the connection.</span></span>

1. <span data-ttu-id="02ad8-114">**Көрсетілетін аты** өрісінде қосылымға оңай танылатын атау енгізіңіз.</span><span class="sxs-lookup"><span data-stu-id="02ad8-114">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="02ad8-115">Қосылым атауы мен түрі осы қосылымды сипаттайды.</span><span class="sxs-lookup"><span data-stu-id="02ad8-115">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="02ad8-116">Қосылымның мақсатын түсіндіретін атауды таңдауды ұсынамыз.</span><span class="sxs-lookup"><span data-stu-id="02ad8-116">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="02ad8-117">Осы қосылымды кім пайдалана алатынын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="02ad8-117">Choose who can use this connection.</span></span> <span data-ttu-id="02ad8-118">Егер сіз ешқандай әрекет жасамасаңыз, әдепкі бойынша Әкімшілер болады.</span><span class="sxs-lookup"><span data-stu-id="02ad8-118">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="02ad8-119">Қосымша ақпарат алу үшін [Салымшыларға экспорттау үшін қосылымды пайдалануға рұқсат беру](connections.md#allow-contributors-to-use-a-connection-for-exports) бөлімін қараңыз.</span><span class="sxs-lookup"><span data-stu-id="02ad8-119">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="02ad8-120">SFTP тіркелгіңіз үшін **Пайдаланушы аты**, **Құпиясөз**, **Хост атауы** және **Экспорттау қалтасы** деректерін енгізіңіз.</span><span class="sxs-lookup"><span data-stu-id="02ad8-120">Provide a **Username**, **Password**, **Hostname**, and **Export folder** for your SFTP account.</span></span>

1. <span data-ttu-id="02ad8-121">Байланысты сынау үшін **Растау** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="02ad8-121">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="02ad8-122">Деректерді **Мұрағатталған** немесе **Мұрағаттан шығарылған** күйде экспорттауды және экспортталған файлдар үшін **өріс бөлгішін** таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="02ad8-122">Choose if you want to export your data **Gzipped** or **Unzipped** and the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="02ad8-123">**Деректер құпиялығы мен сәйкестігін** растау үшін **Мен келісемін** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="02ad8-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="02ad8-124">Қосылымды аяқтау үшін **Сақтау** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="02ad8-124">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="02ad8-125">Экспорттауды конфигурациялау</span><span class="sxs-lookup"><span data-stu-id="02ad8-125">Configure an export</span></span>

<span data-ttu-id="02ad8-126">Егер сіз осы түрдегі қосылымға қатынаса алсаңыз, сіз бұл экспорттауды конфигурациялай аласыз.</span><span class="sxs-lookup"><span data-stu-id="02ad8-126">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="02ad8-127">Қосымша ақпарат алу үшін [Экспорттауды конфигурациялау үшін қажет рұқсаттар](export-destinations.md#set-up-a-new-export) бөлімін қараңыз.</span><span class="sxs-lookup"><span data-stu-id="02ad8-127">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="02ad8-128">**Деректер** > **Экспорттау** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="02ad8-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="02ad8-129">Жаңа экспорттау жасау үшін **Мақсатты орын қосу** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="02ad8-129">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="02ad8-130">**Экспорттауға арналған қосылым** өрісінде SFTP бөлімінен қосылым таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="02ad8-130">In the **Connection for export** field, choose a connection from the SFTP section.</span></span> <span data-ttu-id="02ad8-131">Егер сіз осы бөлімнің атын көрмесеңіз, сізге қолжетімді осы түрдегі қосылым жоқ.</span><span class="sxs-lookup"><span data-stu-id="02ad8-131">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="02ad8-132">Экспортталатын нысандарды таңдаңыз, мысалы, сегменттер.</span><span class="sxs-lookup"><span data-stu-id="02ad8-132">Select the entities, for example segments, you want to export.</span></span>

   > [!NOTE]
   > <span data-ttu-id="02ad8-133">Әрбір таңдалған нысан экспортталған кезде бес шығыс файлға бөлінеді.</span><span class="sxs-lookup"><span data-stu-id="02ad8-133">Each selected entity will be split up into up to five output files when exported.</span></span> 

1. <span data-ttu-id="02ad8-134">**Сақтау** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="02ad8-134">Select **Save**.</span></span>

<span data-ttu-id="02ad8-135">Экспорттауды сақтау экспорттауды бірден іске қоспайды.</span><span class="sxs-lookup"><span data-stu-id="02ad8-135">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="02ad8-136">Экспорттау әр [жоспарланған жаңартумен](system.md#schedule-tab) іске қосылады.</span><span class="sxs-lookup"><span data-stu-id="02ad8-136">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="02ad8-137">Сондай-ақ [деректерді сұрау бойынша экспорттауға](export-destinations.md#run-exports-on-demand) болады.</span><span class="sxs-lookup"><span data-stu-id="02ad8-137">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="02ad8-138">Деректердің құпиялылығы мен сәйкестігі</span><span class="sxs-lookup"><span data-stu-id="02ad8-138">Data privacy and compliance</span></span>

<span data-ttu-id="02ad8-139">Деректерді SFTP арқылы жіберу үшін Dynamics 365 Customer Insights бағдарламасын қосқан кезде, Dynamics 365 Customer Insights талаптарына сәйкестік шекарасынан тыс деректерді, соның ішінде жеке деректер сияқты ықтимал құпия деректерді беруге мүмкіндік бересіз.</span><span class="sxs-lookup"><span data-stu-id="02ad8-139">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="02ad8-140">Microsoft мұндай деректерді сіздің нұсқауыңыз бойынша тасымалдайды, бірақ экспортталатын орынның кез келген құпиялылық немесе қауіпсіздік міндеттемелеріне сәйкес келуіне жауап бересіз.</span><span class="sxs-lookup"><span data-stu-id="02ad8-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="02ad8-141">Қосымша ақпаратты [Microsoft құпиялық туралы мәлімдемесі](https://go.microsoft.com/fwlink/?linkid=396732) бөлімінен қараңыз.</span><span class="sxs-lookup"><span data-stu-id="02ad8-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="02ad8-142">Бұл функцияны тоқтату үшін бұл экспорттау мақсатын кез келген уақытта Dynamics 365 Customer Insights әкімшісі жоя алады.</span><span class="sxs-lookup"><span data-stu-id="02ad8-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
