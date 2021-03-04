---
title: Customer Insights деректерін Azure Blob сақтау орнына экспорттау
description: Azure Blob сақтау орнына қосылымды конфигурациялау жолы.
ms.date: 09/18/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: ecacf20365e78ced8859dfa54b1b16cb923c00eb
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269199"
---
# <a name="connector-for-azure-blob-storage-preview"></a>Azure Blob сақтау орнына арналған қосқыш (алдын ала қарау)

Customer Insights деректерін Azure Blob сақтау орнында сақтаңыз немесе оны деректерді басқа бағдарламаларға тасымалдау үшін пайдаланыңыз.

## <a name="configure-the-connector-for-azure-blob-storage"></a>Azure Blob сақтау орнына арналған қосқышты конфигурациялау

1. Аудитория мәліметтерінде **Әкімші** > **Экспорттау мақсаттары** тармағына өтіңіз.

1. **Azure Blob сақтау орны** бөлімінде **Орнату** опциясын таңдаңыз.

1. Azure Blob сақтау орнының тіркелгісіне арналған **Тіркелгі атауын**, **Тіркелгі кілтін**, сондай-ақ **Контейнерді** енгізіңіз.
    - Azure Blob сақтау тіркелгісінің аты мен тіркелгі кілтін табу жөнінде толығырақ ақпарат алу үшін мына тақырыпты қараңыз: [Azure порталындағы сақтау құралының тіркелгі параметрлерін басқару](https://docs.microsoft.com/azure/storage/common/storage-account-manage).
    - Контейнерді жасау жөнінде мағлұмат алу үшін мына тақырыпты қараңыз: [Контейнер жасау](https://docs.microsoft.com/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. **Көрсетілу аты** өрісінде межелі орынға оңай танылатын атау енгізіңіз.

1. **Келесі** пәрменін таңдаңыз.

1. Осы межелі орынға экспорттағыңыз келетін нысандардың жанына құсбелгіні қойыңыз.

1. **Сақтау** опциясын таңдаңыз.

Экспортталған деректер сіз конфигурациялаған Azure Blob сақтау орны контейнерінде сақталады. Контейнерде келесі қалта жолдары автоматты түрде жасалады:

- Бастапқы нысандар және жүйе арқылы жасалған нысандар үшін: `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`
  - Мысал: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`
- Экспортталған нысандарға арналған model.json% ExportDestinationName% деңгейінде болады
  - Мысал: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`

## <a name="export-the-data"></a>Деректерді экспорттау

[Сұрау бойынша деректерді экспорттауға](export-destinations.md#export-data-on-demand) болады. Экспорттау сондай-ақ әрбір [жоспарланған жаңарту](system.md#schedule-tab) сайын іске қосылады.


[!INCLUDE[footer-include](../includes/footer-banner.md)]