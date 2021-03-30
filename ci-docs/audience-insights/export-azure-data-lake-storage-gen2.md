---
title: Customer Insights деректерін Azure Data Lake Storage Gen2 жүйесіне экспорттау
description: Azure Data Lake Storage Gen2 қосылымын конфигурациялау жолы туралы ақпарат.
ms.date: 02/04/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 7c0eef575f745efa6312d7141a6dd96607f9797e
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596644"
---
# <a name="connector-for-azure-data-lake-storage-gen2-preview"></a>Azure Data Lake Storage Gen2 қосқышы (алдын ала қарау)

Customer Insights деректерін Azure Data Lake Storage Gen2 ішінде сақтаңыз немесе оны деректерді басқа бағдарламаларға тасымалдау үшін пайдаланыңыз.

## <a name="configure-the-connector-for-azure-data-lake-storage-gen2"></a>Azure Data Lake Storage Gen2 арналған қосқышты конфигурациялау

1. Аудитория мәліметтерінде **Әкімші** > **Экспорттау мақсаттары** тармағына өтіңіз.

1. **Azure Data Lake Storage Gen2** бөлімінде **Реттеу** опциясын таңдаңыз.

1. **Көрсетілу аты** өрісінде межелі орынға оңай танылатын атау енгізіңіз.

1. Azure Data Lake Storage Gen2 арналған **Тіркелгі атауы**, **Тіркелгі кілті** және **Контейнер** элементтерін енгізіңіз.
    - Azure Data Lake Storage Gen2 жүйесімен пайдалану үшін сақтау орны тіркелгісін жасау жолы туралы мәлімет алу үшін [Сақтау орны тіркелгісін жасау](/azure/storage/blobs/create-data-lake-storage-account) бөлімін қараңыз. 
    - Azure Data Lake Gen2 сақтау орны тіркелгісінің атауы мен тіркелгі кілтін табу жолдары туралы мәлімет алу үшін [Azure порталында сақтау орны тіркелгісінің параметрлерін басқару](/azure/storage/common/storage-account-manage) бөлімін қараңыз.

1. **Келесі** пәрменін таңдаңыз.

1. Осы межелі орынға экспорттағыңыз келетін нысандардың жанына құсбелгіні қойыңыз.

1. **Сақтау** опциясын таңдаңыз.

## <a name="export-the-data"></a>Деректерді экспорттау

[Сұрау бойынша деректерді экспорттауға](export-destinations.md#export-data-on-demand) болады. Экспорттау сондай-ақ әрбір [жоспарланған жаңарту](system.md#schedule-tab) сайын іске қосылады.