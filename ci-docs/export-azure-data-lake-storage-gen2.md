---
title: Деректерді экспорттау Azure Data Lake Storage Gen2 (алдын ала қарау)
description: Azure Data Lake Storage Gen2 қосылымын конфигурациялау жолы туралы ақпарат.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 55a61e4d9166df7809a64aeb1168a730402aaed6
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: kk-KZ
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196447"
---
# <a name="export-data-to-azure-data-lake-storage-gen2-preview"></a>Деректерді экспорттау Azure Data Lake Storage Gen2 (алдын ала қарау)

Customer Insights деректерін Azure Data Lake Storage Gen2 тіркелгісіне сақтаңыз немесе оны деректерді басқа бағдарламаларға тасымалдау үшін пайдаланыңыз.

## <a name="prerequisites"></a>Алғышарттар

- А [Azure Data Lake Gen2 көмегімен пайдалану үшін сақтау тіркелгісі](/azure/storage/blobs/create-data-lake-storage-account). Сақтау тіркелгісінің атын және кілтін табу үшін қараңыз [Azure порталында сақтау тіркелгісінің параметрлерін басқарыңыз](/azure/storage/common/storage-account-manage).
- Ан [Azure Blob сақтау контейнері](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

## <a name="known-limitations"></a>Белгілі шектеулер

- Үшін Azure Data Lake Storage Gen2, біреуін таңдаңыз [Стандартты өнімділік және Premium өнімділік деңгейі](/azure/storage/blobs/create-data-lake-storage-account). Егер сіз премиум өнімділік деңгейін таңдасаңыз, [тіркелгі түрі ретінде премиум блок екілік нысандарын](/azure/storage/common/storage-account-overview#types-of-storage-accounts) таңдаңыз.

## <a name="set-up-connection-to-azure-data-lake-storage-gen2"></a>Қосылымды орнату Azure Data Lake Storage Gen2

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. **Әкімші** > **Қосылымдар** тармағына өтіңіз.

1. таңдаңыз **Қосылым қосыңыз** және таңдаңыз **Azure Data Lake Gen 2**.

1. **Көрсетілетін аты** өрісінде қосылымға оңай танылатын атау енгізіңіз. Қосылым атауы мен түрі осы қосылымды сипаттайды. Қосылымның мақсатын түсіндіретін атауды таңдауды ұсынамыз.

1. Осы қосылымды кім пайдалана алатынын таңдаңыз. Әдепкі бойынша бұл тек әкімшілер. Қосымша ақпарат алу үшін [Салымшыларға экспорттау үшін қосылымды пайдалануға рұқсат беру](connections.md#allow-contributors-to-use-a-connection-for-exports) бөлімін қараңыз.

1. Azure Data Lake Storage Gen2 арналған **Тіркелгі атауы**, **Тіркелгі кілті** және **Контейнер** элементтерін енгізіңіз.

1. шолу [деректердің құпиялылығы және сәйкестігі](connections.md#data-privacy-and-compliance) және таңдаңыз **Мен келісемін**.

1. Қосылымды аяқтау үшін **Сақтау** түймешігін таңдаңыз.

## <a name="configure-an-export"></a>Экспорттауды конфигурациялау

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. **Деректер** > **Экспорттау** тармағына өтіңіз.

1. таңдаңыз **Экспортты қосыңыз**.

1. Ішінде **Экспортқа арналған қосылым** өрісінде Azure деректер көлі бөлімінен қосылымды таңдаңыз. Егер қосылым болмаса, әкімшіге хабарласыңыз.

1. Экспорттау үшін атау енгізіңіз.

1. үшін қалта атын енгізіңіз Azure Data Lake Storage Gen2 сақтау орны.

1. Осы межелі орынға экспорттағыңыз келетін нысандардың жанына құсбелгіні қойыңыз.

1. **Сақтау** пәрменін таңдаңыз.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

Экспортталған деректер конфигурациялаған Azure Data Lake Gen 2 сақтау орны контейнерінде сақталады.

> [!TIP]
> Деректердің үлкен көлемін қамтитын нысандарды экспорттау әр экспорт үшін бір қалтадағы бірнеше CSV файлдарына әкелуі мүмкін. Экспортты бөлу экспортты аяқтауға кететін уақытты азайту үшін өнімділік себептеріне байланысты орын алады.

[!INCLUDE [footer-include](includes/footer-banner.md)]
