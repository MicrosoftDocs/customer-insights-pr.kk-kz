---
title: Деректерді Azure Blob қоймасына экспорттау (алдын ала қарау)
description: Blob сақтау орны үшін қосылымды конфигурациялау және экспорттау жолы туралы ақпарат.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 22593ed05f403a40fe494e30f807b57658594f01
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: kk-KZ
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195711"
---
# <a name="export-data-to-an-azure-blob-storage-preview"></a>Деректерді Azure Blob қоймасына экспорттау (алдын ала қарау)

Customer Insights деректерін Azure Blob сақтау орнында сақтаңыз немесе оны деректерді басқа бағдарламаларға тасымалдау үшін пайдаланыңыз.

## <a name="prerequisites"></a>Алғышарттар

- Ан [Azure Blob сақтау тіркелгісі](/azure/storage/blobs/create-data-lake-storage-account) аты және тіркелгі кілті. Аты мен кілтін табу үшін қараңыз [Azure порталында сақтау тіркелгісінің параметрлерін басқарыңыз](/azure/storage/common/storage-account-manage).
- Ан [Azure Blob сақтау контейнері](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

## <a name="known-limitations"></a>Белгілі шектеулер

- Azure Blob сақтау орны үшін біреуін таңдаңыз [Стандартты өнімділік және Premium өнімділік деңгейі](/azure/storage/blobs/storage-blob-performance-tiers). Егер сіз премиум өнімділік деңгейін таңдасаңыз, [тіркелгі түрі ретінде премиум блок екілік нысандарын](/azure/storage/common/storage-account-overview#types-of-storage-accounts) таңдаңыз.

## <a name="set-up-connection-to-blob-storage"></a>Blob қоймасына қосылымды орнатыңыз

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. **Әкімші** > **Қосылымдар** тармағына өтіңіз.

1. таңдаңыз **Қосылым қосыңыз** және таңдаңыз **Azure Blob сақтау орны**.

1. **Көрсетілетін аты** өрісінде қосылымға оңай танылатын атау енгізіңіз. Қосылым атауы мен түрі осы қосылымды сипаттайды. Қосылымның мақсатын түсіндіретін атауды таңдауды ұсынамыз.

1. Осы қосылымды кім пайдалана алатынын таңдаңыз. Әдепкі бойынша бұл тек әкімшілер. Қосымша ақпарат алу үшін [Салымшыларға экспорттау үшін қосылымды пайдалануға рұқсат беру](connections.md#allow-contributors-to-use-a-connection-for-exports) бөлімін қараңыз.

1. Blob сақтау орны тіркелгісі үшін **Тіркелгі атауы**, **Тіркелгі кілті** және **Контейнер** өрістерін енгізіңіз.

1. шолу [деректердің құпиялылығы және сәйкестігі](connections.md#data-privacy-and-compliance) және таңдаңыз **Мен келісемін**.

1. Қосылымды аяқтау үшін **Сақтау** түймешігін таңдаңыз.

## <a name="configure-an-export"></a>Экспорттауды конфигурациялау

Бұл экспортты конфигурациялау үшін сізде болуы керек [рұқсат](export-destinations.md#set-up-a-new-export) осы қосылым түрі үшін.

> [!IMPORTANT]
> Егер сіз қоссаңыз [жұмсақ жою параметрі](/azure/storage/blobs/soft-delete-blob-enable) Azure Blob сақтау тіркелгісі үшін экспорттар сәтсіз болады. Деректерді BLOB нысандарына экспорттау үшін жұмсақ жоюды өшіріңіз.

1. **Деректер** > **Экспорттау** тармағына өтіңіз.

1. таңдаңыз **Экспортты қосыңыз**.

1. **Экспорттауға арналған қосылым** өрісінде Azure Blob сақтау орны бөлімінен қосылым таңдаңыз. Егер қосылым болмаса, әкімшіге хабарласыңыз.

1. Экспорттау үшін атау енгізіңіз.

1. Blob сақтау орны үшін қалта атын енгізіңіз.

1. Осы межелі орынға экспорттағыңыз келетін нысандардың жанына құсбелгіні қойыңыз.

1. **Сақтау** пәрменін таңдаңыз.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

Экспортталған деректер конфигурациялаған Blob сақтау орны контейнерінде сақталады. Контейнерде келесі қалта жолдары автоматты түрде жасалады:

- Бастапқы нысандар және жүйе арқылы жасалған нысандар үшін:   
  *%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*  

  Мысал: Dynamics365CustomerInsights/CustomerInsights_ abcd1234-4312-11f4-93dc-24f72f43e7d5 /BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv
  
  > [!TIP]
  > Деректердің үлкен көлемін қамтитын нысандарды экспорттау әр экспорт үшін бір қалтадағы бірнеше CSV файлдарына әкелуі мүмкін. Экспортты бөлу экспортты аяқтауға кететін уақытты азайту үшін өнімділік себептеріне байланысты орын алады.

- Экспортталған нысандарға арналған model.json мына жерде орналасқан *%ExportDestinationName%* деңгейі.  
  
  Мысал: Dynamics365CustomerInsights/CustomerInsights_ abcd1234-4312-11f4-93dc-24f72f43e7d5 /BlobExport/model.json

[!INCLUDE [footer-include](includes/footer-banner.md)]
