---
title: Customer Insights деректерін InMobi қызметіне экспорттау
description: Қосылымды конфигурациялауды және InMobi қызметіне экспорттауды үйреніңіз.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ef486ad6786ef01be977f3d6bda69ce8a2b081c7
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: kk-KZ
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195895"
---
# <a name="export-customer-insights-data-to-inmobi-preview"></a>Customer Insights деректерін InMobi қызметіне экспорттау (алдын ала қарау)

Customer Insights данасынан сегмент тізімдерін немесе басқа деректерді экспорттаңыз [InMobi](https://www.inmobi.com/).

## <a name="prerequisites"></a>Алғышарттар

- Ан [InMobi тіркелгісі](https://www.inmobi.com/) және әкімші тіркелгі деректері.
- Ан [Azure Blob сақтау тіркелгісі](/azure/storage/blobs/create-data-lake-storage-account) аты және тіркелгі кілті. Аты мен кілтін табу үшін қараңыз [Azure порталында сақтау тіркелгісінің параметрлерін басқарыңыз](/azure/storage/common/storage-account-manage).
- Ан [Azure Blob сақтау контейнері](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container) InMobi деректерін экспорттау үшін.
- InMobi сіздің Blob қоймасына тікелей қосылым жасайды және деректеріңіздің InMobi-ге автоматты импортын конфигурациялайды. Процесті бастау үшін InMobi өкіліне хабарласыңыз.

## <a name="known-limitations"></a>Белгілі шектеулер

- Azure Blob сақтау орны үшін біреуін таңдаңыз [Стандартты өнімділік және Premium өнімділік деңгейі](/azure/storage/blobs/storage-blob-performance-tiers). Егер сіз премиум өнімділік деңгейін таңдасаңыз, [тіркелгі түрі ретінде премиум блок екілік нысандарын](/azure/storage/common/storage-account-overview#types-of-storage-accounts) таңдаңыз.

## <a name="set-up-connection-to-azure-blob-storage"></a>Azure Blob қоймасына қосылымды орнатыңыз

[Azure Blob қоймасына қосылымды орнатыңыз](export-azure-blob-storage.md).

## <a name="configure-an-export"></a>Экспорттауды конфигурациялау

[Экспортты конфигурациялаңыз](export-azure-blob-storage.md#configure-an-export).

[!INCLUDE [footer-include](includes/footer-banner.md)]
