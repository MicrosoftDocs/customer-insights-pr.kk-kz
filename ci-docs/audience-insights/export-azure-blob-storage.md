---
title: Customer Insights деректерін Azure Blob сақтау орнына экспорттау
description: Blob сақтау орны үшін қосылымды конфигурациялау және экспорттау жолы туралы ақпарат.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 3c19dc6d4956a33a5bd3cea706f8a154198d487f
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976188"
---
# <a name="export-segment-list-and-other-data-to-azure-blob-storage-preview"></a><span data-ttu-id="e64a3-103">Сегменттер тізімін және басқа деректерді Azure Blob сақтау орнына экспорттау (алдын ала қарау нұсқасы)</span><span class="sxs-lookup"><span data-stu-id="e64a3-103">Export segment list and other data to Azure Blob Storage (preview)</span></span>

<span data-ttu-id="e64a3-104">Customer Insights деректерін Azure Blob сақтау орнында сақтаңыз немесе оны деректерді басқа бағдарламаларға тасымалдау үшін пайдаланыңыз.</span><span class="sxs-lookup"><span data-stu-id="e64a3-104">Store your Customer Insights data in a Blob storage or use it to transfer your data to other applications.</span></span>

## <a name="set-up-the-connection-to-blob-storage"></a><span data-ttu-id="e64a3-105">Blob сақтау орнына қосылым орнату</span><span class="sxs-lookup"><span data-stu-id="e64a3-105">Set up the connection to Blob storage</span></span>

1. <span data-ttu-id="e64a3-106">**Әкімші** > **Қосылымдар** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="e64a3-106">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="e64a3-107">**Қосылым қосу** түймешігін таңдаңыз және қосылымды конфигурациялау үшін **Azure Blob сақтау орны** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="e64a3-107">Select **Add connection** and choose **Azure Blob Storage** to configure the connection.</span></span>

1. <span data-ttu-id="e64a3-108">**Көрсетілетін аты** өрісінде қосылымға оңай танылатын атау енгізіңіз.</span><span class="sxs-lookup"><span data-stu-id="e64a3-108">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="e64a3-109">Қосылым атауы мен түрі осы қосылымды сипаттайды.</span><span class="sxs-lookup"><span data-stu-id="e64a3-109">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="e64a3-110">Қосылымның мақсатын түсіндіретін атауды таңдауды ұсынамыз.</span><span class="sxs-lookup"><span data-stu-id="e64a3-110">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="e64a3-111">Осы қосылымды кім пайдалана алатынын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="e64a3-111">Choose who can use this connection.</span></span> <span data-ttu-id="e64a3-112">Егер сіз ешқандай әрекет жасамасаңыз, әдепкі бойынша Әкімшілер болады.</span><span class="sxs-lookup"><span data-stu-id="e64a3-112">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="e64a3-113">Қосымша ақпарат алу үшін [Салымшыларға экспорттау үшін қосылымды пайдалануға рұқсат беру](connections.md#allow-contributors-to-use-a-connection-for-exports) бөлімін қараңыз.</span><span class="sxs-lookup"><span data-stu-id="e64a3-113">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="e64a3-114">Blob сақтау орны тіркелгісі үшін **Тіркелгі атауы**, **Тіркелгі кілті** және **Контейнер** өрістерін енгізіңіз.</span><span class="sxs-lookup"><span data-stu-id="e64a3-114">Enter **Account name**, **Account key**, and **Container** for your Blob storage account.</span></span>
    - <span data-ttu-id="e64a3-115">Blob сақтау орнының тіркелгі атауын және тіркелгі кілтін табу жолы туралы қосымша ақпарат алу үшін [Azure порталындағы сақтау орны тіркелгісінің параметрлерін басқару](/azure/storage/common/storage-account-manage) бөлімін қараңыз.</span><span class="sxs-lookup"><span data-stu-id="e64a3-115">To learn more about how to find the Blob storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>
    - <span data-ttu-id="e64a3-116">Контейнерді жасау жөнінде мағлұмат алу үшін мына тақырыпты қараңыз: [Контейнер жасау](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="e64a3-116">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="e64a3-117">Қосылымды аяқтау үшін **Сақтау** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="e64a3-117">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="e64a3-118">Экспорттауды конфигурациялау</span><span class="sxs-lookup"><span data-stu-id="e64a3-118">Configure an export</span></span>

<span data-ttu-id="e64a3-119">Егер сіз осы түрдегі қосылымға қатынаса алсаңыз, сіз бұл экспорттауды конфигурациялай аласыз.</span><span class="sxs-lookup"><span data-stu-id="e64a3-119">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="e64a3-120">Қосымша ақпарат алу үшін [Экспорттауды конфигурациялау үшін қажет рұқсаттар](export-destinations.md#set-up-a-new-export) бөлімін қараңыз.</span><span class="sxs-lookup"><span data-stu-id="e64a3-120">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="e64a3-121">**Деректер** > **Экспорттау** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="e64a3-121">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="e64a3-122">Жаңа экспорттау жасау үшін **Мақсатты орын қосу** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="e64a3-122">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="e64a3-123">**Экспорттауға арналған қосылым** өрісінде Azure Blob сақтау орны бөлімінен қосылым таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="e64a3-123">In the **Connection for export** field, choose a connection from the Azure Blob Storage section.</span></span> <span data-ttu-id="e64a3-124">Егер сіз осы бөлімнің атын көрмесеңіз, сізге қолжетімді осы түрдегі қосылым жоқ.</span><span class="sxs-lookup"><span data-stu-id="e64a3-124">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="e64a3-125">Осы межелі орынға экспорттағыңыз келетін нысандардың жанына құсбелгіні қойыңыз.</span><span class="sxs-lookup"><span data-stu-id="e64a3-125">Select the box next to each of the entities you want to export to this destination.</span></span>

1. <span data-ttu-id="e64a3-126">**Сақтау** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="e64a3-126">Select **Save**.</span></span>

<span data-ttu-id="e64a3-127">Экспорттауды сақтау экспорттауды бірден іске қоспайды.</span><span class="sxs-lookup"><span data-stu-id="e64a3-127">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="e64a3-128">Экспорттау әр [жоспарланған жаңартумен](system.md#schedule-tab) іске қосылады.</span><span class="sxs-lookup"><span data-stu-id="e64a3-128">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span>     
<span data-ttu-id="e64a3-129">Сондай-ақ [деректерді сұрау бойынша экспорттауға](export-destinations.md#run-exports-on-demand) болады.</span><span class="sxs-lookup"><span data-stu-id="e64a3-129">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

<span data-ttu-id="e64a3-130">Экспортталған деректер конфигурациялаған Blob сақтау орны контейнерінде сақталады.</span><span class="sxs-lookup"><span data-stu-id="e64a3-130">Exported data is stored in the Blob storage container you configured.</span></span> <span data-ttu-id="e64a3-131">Контейнерде келесі қалта жолдары автоматты түрде жасалады:</span><span class="sxs-lookup"><span data-stu-id="e64a3-131">The following folder paths are automatically created in your container:</span></span>

- <span data-ttu-id="e64a3-132">Бастапқы нысандар және жүйе арқылы жасалған нысандар үшін: `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`</span><span class="sxs-lookup"><span data-stu-id="e64a3-132">For source entities and entities generated by the system: `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`</span></span>
  - <span data-ttu-id="e64a3-133">Мысал: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`</span><span class="sxs-lookup"><span data-stu-id="e64a3-133">Example: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`</span></span>
- <span data-ttu-id="e64a3-134">Экспортталатын нысандарға арналған model.json файлы %ExportDestinationName% деңгейінде болады</span><span class="sxs-lookup"><span data-stu-id="e64a3-134">The model.json for the exported entities will be at the %ExportDestinationName% level</span></span>
  - <span data-ttu-id="e64a3-135">Мысал: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`</span><span class="sxs-lookup"><span data-stu-id="e64a3-135">Example: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
