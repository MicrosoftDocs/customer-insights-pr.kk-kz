---
title: Customer Insights деректерін Azure Data Lake Storage Gen2 жүйесіне экспорттау
description: Azure Data Lake Storage Gen2 қосылымын конфигурациялау жолы туралы ақпарат.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: f431b707e1d65ffe47f8b3aa1c52abaa964e871a
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760058"
---
# <a name="set-up-the-connection-to-azure-data-lake-storage-gen2-preview"></a><span data-ttu-id="015f1-103">Azure Data Lake Storage Gen2 (алдын ала қарау нұсқасы) бағдарламасына қосылым орнату</span><span class="sxs-lookup"><span data-stu-id="015f1-103">Set up the connection to Azure Data Lake Storage Gen2 (preview)</span></span>

1. <span data-ttu-id="015f1-104">**Әкімші** > **Қосылымдар** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="015f1-104">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="015f1-105">**Қосылым қосу** түймешігін таңдаңыз және қосылымды конфигурациялау үшін **Azure Data Lake Gen 2** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="015f1-105">Select **Add connection** and choose **Azure Data Lake Gen 2** to configure the connection.</span></span>

1. <span data-ttu-id="015f1-106">**Көрсетілетін аты** өрісінде қосылымға оңай танылатын атау енгізіңіз.</span><span class="sxs-lookup"><span data-stu-id="015f1-106">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="015f1-107">Қосылым атауы мен түрі осы қосылымды сипаттайды.</span><span class="sxs-lookup"><span data-stu-id="015f1-107">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="015f1-108">Қосылымның мақсатын түсіндіретін атауды таңдауды ұсынамыз.</span><span class="sxs-lookup"><span data-stu-id="015f1-108">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="015f1-109">Осы қосылымды кім пайдалана алатынын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="015f1-109">Choose who can use this connection.</span></span> <span data-ttu-id="015f1-110">Егер сіз ешқандай әрекет жасамасаңыз, әдепкі бойынша Әкімшілер болады.</span><span class="sxs-lookup"><span data-stu-id="015f1-110">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="015f1-111">Қосымша ақпарат алу үшін [Салымшыларға экспорттау үшін қосылымды пайдалануға рұқсат беру](connections.md#allow-contributors-to-use-a-connection-for-exports) бөлімін қараңыз.</span><span class="sxs-lookup"><span data-stu-id="015f1-111">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="015f1-112">Azure Data Lake Storage Gen2 арналған **Тіркелгі атауы**, **Тіркелгі кілті** және **Контейнер** элементтерін енгізіңіз.</span><span class="sxs-lookup"><span data-stu-id="015f1-112">Enter **Account name**, **Account key**, and **Container** for your Azure Data Lake Storage Gen2.</span></span>
    - <span data-ttu-id="015f1-113">Azure Data Lake Storage Gen2 жүйесімен пайдалану үшін сақтау орны тіркелгісін жасау жолы туралы мәлімет алу үшін [Сақтау орны тіркелгісін жасау](/azure/storage/blobs/create-data-lake-storage-account) бөлімін қараңыз.</span><span class="sxs-lookup"><span data-stu-id="015f1-113">To learn how to create a storage account to use with Azure Data Lake Storage Gen2, see [Create storage account](/azure/storage/blobs/create-data-lake-storage-account).</span></span> 
    - <span data-ttu-id="015f1-114">Azure Data Lake Gen2 сақтау орнының тіркелгі атауын және тіркелгі кілтін табу жолы туралы қосымша ақпарат алу үшін [Azure порталындағы сақтау орны тіркелгісінің параметрлерін басқару](/azure/storage/common/storage-account-manage) бөлімін қараңыз.</span><span class="sxs-lookup"><span data-stu-id="015f1-114">To learn more about Azure Data Lake Gen2 storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

1. <span data-ttu-id="015f1-115">Қосылымды аяқтау үшін **Сақтау** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="015f1-115">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="015f1-116">Экспорттауды конфигурациялау</span><span class="sxs-lookup"><span data-stu-id="015f1-116">Configure an export</span></span>

<span data-ttu-id="015f1-117">Егер сіз осы түрдегі қосылымға қатынаса алсаңыз, сіз бұл экспорттауды конфигурациялай аласыз.</span><span class="sxs-lookup"><span data-stu-id="015f1-117">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="015f1-118">Қосымша ақпарат алу үшін [Экспорттауды конфигурациялау үшін қажет рұқсаттар](export-destinations.md#set-up-a-new-export) бөлімін қараңыз.</span><span class="sxs-lookup"><span data-stu-id="015f1-118">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="015f1-119">**Деректер** > **Экспорттау** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="015f1-119">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="015f1-120">Жаңа экспорттау жасау үшін **Экспорттау қосу** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="015f1-120">To create a new export, select **Add export**.</span></span>

1. <span data-ttu-id="015f1-121">**Экспорттауға арналған қосылым** өрісінде **Azure Data Lake** бөлімінен қосылым таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="015f1-121">In the **Connection for export** field, choose a connection from the **Azure Data Lake** section.</span></span> <span data-ttu-id="015f1-122">Егер сіз осы бөлімнің атын көрмесеңіз, сізге қолжетімді осы түрдегі қосылым жоқ.</span><span class="sxs-lookup"><span data-stu-id="015f1-122">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="015f1-123">Осы межелі орынға экспорттағыңыз келетін нысандардың жанына құсбелгіні қойыңыз.</span><span class="sxs-lookup"><span data-stu-id="015f1-123">Select the box next to each of the entities you want to export to this destination.</span></span>

1. <span data-ttu-id="015f1-124">**Сақтау** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="015f1-124">Select **Save**.</span></span>

<span data-ttu-id="015f1-125">Экспорттауды сақтау экспорттауды бірден іске қоспайды.</span><span class="sxs-lookup"><span data-stu-id="015f1-125">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="015f1-126">Экспорттау әр [жоспарланған жаңартумен](system.md#schedule-tab) іске қосылады.</span><span class="sxs-lookup"><span data-stu-id="015f1-126">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="015f1-127">Сондай-ақ [деректерді сұрау бойынша экспорттауға](export-destinations.md#run-exports-on-demand) болады.</span><span class="sxs-lookup"><span data-stu-id="015f1-127">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

<span data-ttu-id="015f1-128">Экспортталған деректер конфигурациялаған Azure Data Lake Gen 2 сақтау орны контейнерінде сақталады.</span><span class="sxs-lookup"><span data-stu-id="015f1-128">Exported data is stored in the Azure Data Lake Gen 2 storage container you configured.</span></span> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
