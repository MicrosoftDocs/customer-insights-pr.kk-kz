---
title: Customer Insights деректерін SFTP хосттарына экспорттау
description: SFTP хостымен байланысты теңшеу жолы туралы ақпарат.
ms.date: 01/27/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 9ec14fafa8f99e34b95349371298082e166535d0
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598392"
---
# <a name="connector-for-sftp-preview"></a><span data-ttu-id="41b32-103">SFTP коннекторы (алдын ала қарау)</span><span class="sxs-lookup"><span data-stu-id="41b32-103">Connector for SFTP (preview)</span></span>

<span data-ttu-id="41b32-104">Қауіпсіз файл тасымалдау протоколы (SFTP) хостына үшінші тарап қолданбаларындағы тұтынушы деректерін пайдаланыңыз.</span><span class="sxs-lookup"><span data-stu-id="41b32-104">Use your customer data in third-party applications by exporting them to a Secure File Transfer Protocol (SFTP) host.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="41b32-105">Алғышарттар</span><span class="sxs-lookup"><span data-stu-id="41b32-105">Prerequisites</span></span>

- <span data-ttu-id="41b32-106">SFTP хостының және тиісті тіркелгі деректерінің қолжетімділігі.</span><span class="sxs-lookup"><span data-stu-id="41b32-106">Availability of an SFTP host and corresponding credentials.</span></span>

## <a name="connect-to-sftp"></a><span data-ttu-id="41b32-107">SFTP қосылу</span><span class="sxs-lookup"><span data-stu-id="41b32-107">Connect to SFTP</span></span>

1. <span data-ttu-id="41b32-108">**Әкімші** > **Экспорттық межелі орындар** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="41b32-108">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="41b32-109">**SFTP** астынан **Орнату** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="41b32-109">Under **SFTP**, select **Set up**.</span></span>

1. <span data-ttu-id="41b32-110">**Көрсетілу аты** өрісінде межелі орынға оңай танылатын атау енгізіңіз.</span><span class="sxs-lookup"><span data-stu-id="41b32-110">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="41b32-111">SFTP тіркелгіңіз үшін **Пайдаланушы аты**, **Құпиясөз**, **Хост атауы** және **Экспорттау қалтасы** деректерін енгізіңіз.</span><span class="sxs-lookup"><span data-stu-id="41b32-111">Provide a **Username**, **Password**, **Hostname**, and **Export folder** for your SFTP account.</span></span>

1. <span data-ttu-id="41b32-112">Байланысты сынау үшін **Растау** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="41b32-112">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="41b32-113">Сәтті тексеруден кейін деректеріңізді **Мұрағатталған** немесе **Мұрағаттан шығарылған** деректерді экспорттау қажеттігін таңдап, экспортталған файлдарға арналған **өріс бөлгішін** таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="41b32-113">After successful verification, choose if you want to export your data **Gzipped** or **Unzipped**, and select the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="41b32-114">**Деректер құпиялығы мен сәйкестігін** растау үшін **Мен келісемін** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="41b32-114">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="41b32-115">Экспорттауды теңшеуді бастау үшін **Келесі** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="41b32-115">Select **Next** to start configuring the export.</span></span>

## <a name="configure-the-export"></a><span data-ttu-id="41b32-116">Экспорттауды конфигурациялау</span><span class="sxs-lookup"><span data-stu-id="41b32-116">Configure the export</span></span>

1. <span data-ttu-id="41b32-117">Экспортталатын нысандарды таңдаңыз, мысалы, сегменттер.</span><span class="sxs-lookup"><span data-stu-id="41b32-117">Select the entities, for example segments, you want to export.</span></span>

   > [!NOTE]
   > <span data-ttu-id="41b32-118">Әр таңдалған нысанда экспорттау кезінде беске дейін шығыс файлдары болады.</span><span class="sxs-lookup"><span data-stu-id="41b32-118">Each selected entity will be up to five output files when exported.</span></span> 

1. <span data-ttu-id="41b32-119">**Сақтау** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="41b32-119">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="41b32-120">Деректерді экспорттау</span><span class="sxs-lookup"><span data-stu-id="41b32-120">Export the data</span></span>

<span data-ttu-id="41b32-121">[Сұрау бойынша деректерді экспорттауға](export-destinations.md) болады.</span><span class="sxs-lookup"><span data-stu-id="41b32-121">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="41b32-122">Экспорттау сондай-ақ әрбір [жоспарланған жаңарту](system.md#schedule-tab) сайын іске қосылады.</span><span class="sxs-lookup"><span data-stu-id="41b32-122">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="41b32-123">Белгілі шектеулер</span><span class="sxs-lookup"><span data-stu-id="41b32-123">Known limitations</span></span>

- <span data-ttu-id="41b32-124">Экспорттаудың жұмыс уақыты жүйенің жұмысына байланысты.</span><span class="sxs-lookup"><span data-stu-id="41b32-124">The runtime of an export depends on your system performance.</span></span> <span data-ttu-id="41b32-125">Сервердің минималды конфигурациясы ретінде екі CPU оперативті жады мен 1 Гб жадты ұсынамыз.</span><span class="sxs-lookup"><span data-stu-id="41b32-125">We recommend two CPU cores and 1 Gb of memory as minimal configuration of your server.</span></span> 
- <span data-ttu-id="41b32-126">100 миллионға дейін тұтынушы профильдері бар нысандарды экспорттау процессордың екі оперативті жады мен 1 Гб жадының ұсынылған минималды конфигурациясын пайдалану кезінде 90 минутты алуы мүмкін.</span><span class="sxs-lookup"><span data-stu-id="41b32-126">Exporting entities with up to 100 million customer profiles can take 90 minutes when using the recommended minimal configuration of two CPU cores and 1 Gb of memory.</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="41b32-127">Деректердің құпиялылығы мен сәйкестігі</span><span class="sxs-lookup"><span data-stu-id="41b32-127">Data privacy and compliance</span></span>

<span data-ttu-id="41b32-128">Деректерді SFTP арқылы жіберу үшін Dynamics 365 Customer Insights бағдарламасын қосқан кезде, Dynamics 365 Customer Insights талаптарына сәйкестік шекарасынан тыс деректерді, соның ішінде жеке деректер сияқты ықтимал құпия деректерді беруге мүмкіндік бересіз.</span><span class="sxs-lookup"><span data-stu-id="41b32-128">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="41b32-129">Microsoft мұндай деректерді сіздің нұсқауыңыз бойынша тасымалдайды, бірақ экспортталатын орынның кез келген құпиялылық немесе қауіпсіздік міндеттемелеріне сәйкес келуіне жауап бересіз.</span><span class="sxs-lookup"><span data-stu-id="41b32-129">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="41b32-130">Қосымша ақпаратты [Microsoft құпиялық туралы мәлімдемесі](https://go.microsoft.com/fwlink/?linkid=396732) бөлімінен қараңыз.</span><span class="sxs-lookup"><span data-stu-id="41b32-130">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="41b32-131">Бұл функцияны тоқтату үшін бұл экспорттау мақсатын кез келген уақытта Dynamics 365 Customer Insights әкімшісі жоя алады.</span><span class="sxs-lookup"><span data-stu-id="41b32-131">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]