---
title: Customer Insights деректерін SFTP хосттарына экспорттау
description: SFTP хостымен байланысты теңшеу жолы туралы ақпарат.
ms.date: 06/05/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: c2529744d7a26a06324b79cad6a8001d75903545
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643510"
---
# <a name="connector-for-sftp-preview"></a><span data-ttu-id="56de3-103">SFTP коннекторы (алдын ала қарау)</span><span class="sxs-lookup"><span data-stu-id="56de3-103">Connector for SFTP (preview)</span></span>

<span data-ttu-id="56de3-104">Қауіпсіз файл тасымалдау протоколы (SFTP) хостына үшінші тарап қолданбаларындағы тұтынушы деректерін пайдаланыңыз.</span><span class="sxs-lookup"><span data-stu-id="56de3-104">Use your customer data in third-party applications by exporting them to a Secure File Transfer Protocol(SFTP) host.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="56de3-105">Алғышарттар</span><span class="sxs-lookup"><span data-stu-id="56de3-105">Prerequisites</span></span>

- <span data-ttu-id="56de3-106">SFTP хосты мен тиісті деректемелер қолжетімділігі.</span><span class="sxs-lookup"><span data-stu-id="56de3-106">Availability of a SFTP host and corresponding credentials.</span></span>

## <a name="connect-to-sftp"></a><span data-ttu-id="56de3-107">SFTP қызметіне қосылу</span><span class="sxs-lookup"><span data-stu-id="56de3-107">Connect to SFTP</span></span>

1. <span data-ttu-id="56de3-108">**Әкімші** > **Экспорттық межелі орындар** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="56de3-108">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="56de3-109">**SFTP** астынан **Орнату** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="56de3-109">Under **SFTP**, select **Set up**.</span></span>

1. <span data-ttu-id="56de3-110">**Көрсетілу аты** өрісінде межелі орынға оңай танылатын атау енгізіңіз.</span><span class="sxs-lookup"><span data-stu-id="56de3-110">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="56de3-111">SFTP тіркелгіңіз үшін **Пайдаланушы аты**, **Құпиясөз** және **Хост атауы** деректерін қамтамасыз етіңіз.</span><span class="sxs-lookup"><span data-stu-id="56de3-111">Provide a **Username**, **Password** and **Hostname** for your SFTP account.</span></span> <span data-ttu-id="56de3-112">Мысалы: егер SFTP серверінің түбірлік қалтасы /root/folder болса және деректердің /root/folder/ci_export_destination_folder қалтасына экспортталуын қаласаңыз, хост атауы sftp://<server_address>/ci_export_destination_folder" болуы керек.</span><span class="sxs-lookup"><span data-stu-id="56de3-112">Example: If your SFTP server's root folder is /root/folder, and you would like the data to be exported to /root/folder/ci_export_destination_folder, the the host should be sftp://<server_address>/ci_export_destination_folder".</span></span>

1. <span data-ttu-id="56de3-113">Байланысты сынау үшін **Растау** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="56de3-113">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="56de3-114">Сәтті растағаннан кейін, **Мұрағатталған** немесе **Мұрағаттан шығарылған** деректерді экспорттау керек болса, экспортталған файлдар үшін **өріс бөлгішін** таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="56de3-114">After successful verification, choose if you want to export your data **Zipped** or **Unzipped**, and select the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="56de3-115">**Деректер құпиялығы мен сәйкестігін** растау үшін **Мен келісемін** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="56de3-115">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="56de3-116">Экспорттауды теңшеуді бастау үшін **Келесі** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="56de3-116">Select **Next** to start configuring the export.</span></span>

## <a name="configure-the-connection"></a><span data-ttu-id="56de3-117">Байланысты теңшеу</span><span class="sxs-lookup"><span data-stu-id="56de3-117">Configure the connection</span></span>

1. <span data-ttu-id="56de3-118">Экспорттау қажет **тұтынушы төлсипаттарын** таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="56de3-118">Select the **customer attributes** you want to export.</span></span> <span data-ttu-id="56de3-119">Бір немесе бірнеше төлсипатты экспорттай аласыз.</span><span class="sxs-lookup"><span data-stu-id="56de3-119">You can export one or multiple attributes.</span></span>

1. <span data-ttu-id="56de3-120">**Келесі** пәрменін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="56de3-120">Select **Next**.</span></span>

1. <span data-ttu-id="56de3-121">Экспорттау керек сегменттерді таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="56de3-121">Select the segments you want to export.</span></span>

1. <span data-ttu-id="56de3-122">**Сақтау** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="56de3-122">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="56de3-123">Деректерді экспорттау</span><span class="sxs-lookup"><span data-stu-id="56de3-123">Export the data</span></span>

<span data-ttu-id="56de3-124">[Сұрау бойынша деректерді экспорттауға](export-destinations.md) болады.</span><span class="sxs-lookup"><span data-stu-id="56de3-124">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="56de3-125">Экспорттау сондай-ақ әрбір [жоспарланған жаңарту](system.md#schedule-tab) сайын іске қосылады.</span><span class="sxs-lookup"><span data-stu-id="56de3-125">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="56de3-126">Деректердің құпиялылығы мен сәйкестігі</span><span class="sxs-lookup"><span data-stu-id="56de3-126">Data privacy and compliance</span></span>

<span data-ttu-id="56de3-127">Деректерді SFTP арқылы жіберу үшін Dynamics 365 Customer Insights бағдарламасын қосқан кезде, Dynamics 365 Customer Insights талаптарына сәйкестік шекарасынан тыс деректерді, соның ішінде жеке деректер сияқты ықтимал құпия деректерді беруге мүмкіндік бересіз.</span><span class="sxs-lookup"><span data-stu-id="56de3-127">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="56de3-128">Microsoft мұндай деректерді сіздің нұсқауыңыз бойынша тасымалдайды, бірақ экспортталатын орынның кез келген құпиялылық немесе қауіпсіздік міндеттемелеріне сәйкес келуіне жауап бересіз.</span><span class="sxs-lookup"><span data-stu-id="56de3-128">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="56de3-129">Қосымша ақпаратты [Microsoft құпиялық туралы мәлімдемесі](https://go.microsoft.com/fwlink/?linkid=396732) бөлімінен қараңыз.</span><span class="sxs-lookup"><span data-stu-id="56de3-129">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="56de3-130">Бұл функцияны тоқтату үшін бұл экспорттау мақсатын кез келген уақытта Dynamics 365 Customer Insights әкімшісі жоя алады.</span><span class="sxs-lookup"><span data-stu-id="56de3-130">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
