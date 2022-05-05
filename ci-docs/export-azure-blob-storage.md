---
title: Customer Insights деректерін Azure Blob сақтау орнына экспорттау
description: Blob сақтау орны үшін қосылымды конфигурациялау және экспорттау жолы туралы ақпарат.
ms.date: 10/06/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 42095f369c47553e5ddf5fada54e559202c943a9
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: kk-KZ
ms.lasthandoff: 04/27/2022
ms.locfileid: "8643437"
---
# <a name="export-segment-list-and-other-data-to-azure-blob-storage-preview"></a>Сегменттер тізімін және басқа деректерді Azure Blob сақтау орнына экспорттау (алдын ала қарау нұсқасы)

Customer Insights деректерін Azure Blob сақтау орнында сақтаңыз немесе оны деректерді басқа бағдарламаларға тасымалдау үшін пайдаланыңыз.

## <a name="known-limitations"></a>Белгілі шектеулер

1. Azure Blob Storage қызметі үшін [Стандартты өнімділік және премиум өнімділік деңгейін](/azure/storage/blobs/storage-blob-performance-tiers) таңдауға болады. Егер сіз премиум өнімділік деңгейін таңдасаңыз, [тіркелгі түрі ретінде премиум блок екілік нысандарын](/azure/storage/common/storage-account-overview#types-of-storage-accounts) таңдаңыз.

## <a name="set-up-the-connection-to-blob-storage"></a>Blob сақтау орнына қосылым орнату

1. **Әкімші** > **Қосылымдар** тармағына өтіңіз.

1. **Қосылым қосу** түймешігін таңдаңыз және қосылымды конфигурациялау үшін **Azure Blob сақтау орны** параметрін таңдаңыз.

1. **Көрсетілетін аты** өрісінде қосылымға оңай танылатын атау енгізіңіз. Қосылым атауы мен түрі осы қосылымды сипаттайды. Қосылымның мақсатын түсіндіретін атауды таңдауды ұсынамыз.

1. Осы қосылымды кім пайдалана алатынын таңдаңыз. Егер сіз ешқандай әрекет жасамасаңыз, әдепкі бойынша Әкімшілер болады. Қосымша ақпарат алу үшін [Салымшыларға экспорттау үшін қосылымды пайдалануға рұқсат беру](connections.md#allow-contributors-to-use-a-connection-for-exports) бөлімін қараңыз.

1. Blob сақтау орны тіркелгісі үшін **Тіркелгі атауы**, **Тіркелгі кілті** және **Контейнер** өрістерін енгізіңіз.
    - Blob сақтау орнының тіркелгі атауын және тіркелгі кілтін табу жолы туралы қосымша ақпарат алу үшін [Azure порталындағы сақтау орны тіркелгісінің параметрлерін басқару](/azure/storage/common/storage-account-manage) бөлімін қараңыз.
    - Контейнерді жасау жөнінде мағлұмат алу үшін мына тақырыпты қараңыз: [Контейнер жасау](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Қосылымды аяқтау үшін **Сақтау** түймешігін таңдаңыз. 

## <a name="configure-an-export"></a>Экспорттауды конфигурациялау

Егер сіз осы түрдегі қосылымға қатынаса алсаңыз, сіз бұл экспорттауды конфигурациялай аласыз. Қосымша ақпарат алу үшін [Экспорттауды конфигурациялау үшін қажет рұқсаттар](export-destinations.md#set-up-a-new-export) бөлімін қараңыз.

> [!IMPORTANT]
> Егер сіз Azure Blob сақтау орны тіркелгісі үшін жұмсақ жою параметрін қоссаңыз, экспорттау сәтсіз аяқталады. Деректерді BLOB нысандарына экспорттау үшін жұмсақ жоюды өшіріңіз. Қосымша ақпарат алу үшін [Blob жұмсақ жою мүмкіндігін қосу](/azure/storage/blobs/soft-delete-blob-enable.md) тақырыбын қараңыз

1. **Деректер** > **Экспорттау** тармағына өтіңіз.

1. Жаңа экспорттау жасау үшін **Мақсатты орын қосу** түймешігін таңдаңыз.

1. **Экспорттауға арналған қосылым** өрісінде Azure Blob сақтау орны бөлімінен қосылым таңдаңыз. Егер сіз бұл бөлімнің атауын көрмесеңіз, онда сіз үшін осы түрдегі қосылымдар қолжетімді емес.

1. Осы межелі орынға экспорттағыңыз келетін нысандардың жанына құсбелгіні қойыңыз.

1. **Сақтау** опциясын таңдаңыз.

Экспорттауды сақтау экспорттауды бірден іске қоспайды.

Экспорттау әр [жоспарланған жаңартумен](system.md#schedule-tab) іске қосылады.     

Сондай-ақ [деректерді сұрау бойынша экспорттауға](export-destinations.md#run-exports-on-demand) болады. 

Экспортталған деректер конфигурациялаған Blob сақтау орны контейнерінде сақталады. Контейнерде келесі қалта жолдары автоматты түрде жасалады:

- Бастапқы нысандар және жүйе арқылы жасалған нысандар үшін:   
  `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`  
  - Мысал: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`
 
- Экспортталатын нысандарға арналған model.json файлы %ExportDestinationName% деңгейінде болады.  
  - Мысал: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`

[!INCLUDE [footer-include](includes/footer-banner.md)]