---
title: Customer Insights деректерін InMobi қызметіне экспорттау
description: Қосылымды конфигурациялауды және InMobi қызметіне экспорттауды үйреніңіз.
ms.date: 06/27/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8261c8adfe231792e70fc85432237cf73d5cd5a7
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: kk-KZ
ms.lasthandoff: 06/29/2022
ms.locfileid: "9059612"
---
# <a name="export-segment-list-and-other-data-to-inmobi-preview"></a>Сегмент тізімін және басқа деректерді InMobi қызметіне экспорттау (алдын ала қарау)

Customer Insights данасынан сегмент тізімдерін немесе басқа деректерді экспорттаңыз [InMobi](https://www.inmobi.com/).

## <a name="prerequisites"></a>Алғышарттар

1. Сізде бар [InMobi тіркелгісі](https://www.inmobi.com/) және әкімші тіркелгі деректері.
1. Сізде Azure Blob сақтау тіркелгісінің аты және сәйкес тіркелгі кілті бар. Қосымша ақпаратты қараңыз [Azure порталында сақтау тіркелгісінің параметрлерін басқарыңыз](/azure/storage/common/storage-account-manage). Сақтау тіркелгісінде inMobi деректерін экспорттауға арналған контейнер бар. Қосымша ақпарат алу үшін қараңыз [Контейнер жасаңыз](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).
1. InMobi сіздің Blob қоймасына тікелей қосылым жасайды және деректеріңіздің InMobi-ге автоматты импортын конфигурациялайды. Процесті бастау үшін InMobi өкіліне хабарласыңыз.

## <a name="known-limitations"></a>Белгілі шектеулер

1. Azure Blob Storage үшін арасында таңдауға болады [Стандартты өнімділік және Premium өнімділік деңгейі](/azure/storage/blobs/storage-blob-performance-tiers). Егер сіз премиум өнімділік деңгейін таңдасаңыз, [тіркелгі түрі ретінде премиум блок екілік нысандарын](/azure/storage/common/storage-account-overview#types-of-storage-accounts) таңдаңыз.

## <a name="set-up-the-connection-to-azure-blob-storage-and-configure-an-export"></a>Azure Blob қоймасына қосылымды орнатыңыз және экспортты теңшеңіз

1. үшін нұсқауларды орындаңыз [Azure Blob қоймасына қосылымды орнатыңыз](export-azure-blob-storage.md).
2. үшін нұсқауларды орындаңыз [экспорттауды конфигурациялаңыз](export-azure-blob-storage.md#configure-an-export).

[!INCLUDE [footer-include](includes/footer-banner.md)]
