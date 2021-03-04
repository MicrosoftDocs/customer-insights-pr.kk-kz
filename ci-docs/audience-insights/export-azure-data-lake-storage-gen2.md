---
title: Customer Insights деректерін Azure Data Lake Storage Gen2 жүйесіне экспорттау
description: Azure Data Lake Storage Gen2 қосылымын конфигурациялау жолы туралы ақпарат.
ms.date: 02/04/2021
ms.reviewer: sthe
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: b00c3d6178150cbc93fe800779f094809d4dc67b
ms.sourcegitcommit: 0260ed244b97c2fd0be5e9a084c4c489358e8d4f
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 02/18/2021
ms.locfileid: "5477186"
---
# <a name="connector-for-azure-data-lake-storage-gen2-preview"></a><span data-ttu-id="3b093-103">Azure Data Lake Storage Gen2 қосқышы (алдын ала қарау)</span><span class="sxs-lookup"><span data-stu-id="3b093-103">Connector for Azure Data Lake Storage Gen2 (preview)</span></span>

<span data-ttu-id="3b093-104">Customer Insights деректерін Azure Data Lake Storage Gen2 ішінде сақтаңыз немесе оны деректерді басқа бағдарламаларға тасымалдау үшін пайдаланыңыз.</span><span class="sxs-lookup"><span data-stu-id="3b093-104">Store your Customer Insights data in Azure Data Lake Storage Gen2 or use it to transfer your data to other applications.</span></span>

## <a name="configure-the-connector-for-azure-data-lake-storage-gen2"></a><span data-ttu-id="3b093-105">Azure Data Lake Storage Gen2 арналған қосқышты конфигурациялау</span><span class="sxs-lookup"><span data-stu-id="3b093-105">Configure the connector for Azure Data Lake Storage Gen2</span></span>

1. <span data-ttu-id="3b093-106">Аудитория мәліметтерінде **Әкімші** > **Экспорттау мақсаттары** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="3b093-106">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="3b093-107">**Azure Data Lake Storage Gen2** бөлімінде **Реттеу** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="3b093-107">Under **Azure Data Lake Storage Gen2**, select **Set up**.</span></span>

1. <span data-ttu-id="3b093-108">**Көрсетілу аты** өрісінде межелі орынға оңай танылатын атау енгізіңіз.</span><span class="sxs-lookup"><span data-stu-id="3b093-108">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="3b093-109">Azure Data Lake Storage Gen2 арналған **Тіркелгі атауы**, **Тіркелгі кілті** және **Контейнер** элементтерін енгізіңіз.</span><span class="sxs-lookup"><span data-stu-id="3b093-109">Enter **Account name**, **Account key**, and **Container** for your Azure Data Lake Storage Gen2.</span></span>
    - <span data-ttu-id="3b093-110">Azure Data Lake Storage Gen2 жүйесімен пайдалану үшін сақтау орны тіркелгісін жасау жолы туралы мәлімет алу үшін [Сақтау орны тіркелгісін жасау](https://docs.microsoft.com/azure/storage/blobs/create-data-lake-storage-account) бөлімін қараңыз.</span><span class="sxs-lookup"><span data-stu-id="3b093-110">To learn how to create a storage account to use with Azure Data Lake Storage Gen2, see [Create storage account](https://docs.microsoft.com/azure/storage/blobs/create-data-lake-storage-account).</span></span> 
    - <span data-ttu-id="3b093-111">Azure Data Lake Gen2 сақтау орны тіркелгісінің атауы мен тіркелгі кілтін табу жолдары туралы мәлімет алу үшін [Azure порталында сақтау орны тіркелгісінің параметрлерін басқару](https://docs.microsoft.com/azure/storage/common/storage-account-manage) бөлімін қараңыз.</span><span class="sxs-lookup"><span data-stu-id="3b093-111">To learn more about how to find the Azure Data Lake Gen2 storage account name and account key, see [Manage storage account settings in the Azure portal](https://docs.microsoft.com/azure/storage/common/storage-account-manage).</span></span>

1. <span data-ttu-id="3b093-112">**Келесі** пәрменін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="3b093-112">Select **Next**.</span></span>

1. <span data-ttu-id="3b093-113">Осы межелі орынға экспорттағыңыз келетін нысандардың жанына құсбелгіні қойыңыз.</span><span class="sxs-lookup"><span data-stu-id="3b093-113">Select the box next to each of the entities you want to export to this destination.</span></span>

1. <span data-ttu-id="3b093-114">**Сақтау** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="3b093-114">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="3b093-115">Деректерді экспорттау</span><span class="sxs-lookup"><span data-stu-id="3b093-115">Export the data</span></span>

<span data-ttu-id="3b093-116">[Сұрау бойынша деректерді экспорттауға](export-destinations.md#export-data-on-demand) болады.</span><span class="sxs-lookup"><span data-stu-id="3b093-116">You can [export data on demand](export-destinations.md#export-data-on-demand).</span></span> <span data-ttu-id="3b093-117">Экспорттау сондай-ақ әрбір [жоспарланған жаңарту](system.md#schedule-tab) сайын іске қосылады.</span><span class="sxs-lookup"><span data-stu-id="3b093-117">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>
