---
title: Customer Insights деректерін Azure Blob сақтау орнына экспорттау
description: Azure Blob сақтау орнына қосылымды конфигурациялау жолы.
ms.date: 09/18/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 925b53260e7c633e17d7f172d2dd2d581e982e10
ms.sourcegitcommit: 334633cbd58f5659d20b4f87252c1a10cc7130db
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 12/03/2020
ms.locfileid: "4667146"
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

[Сұрау бойынша деректерді экспорттауға](/export-destinations.md#export-data-on-demand) болады. Экспорттау сондай-ақ әрбір [жоспарланған жаңарту](system.md#schedule-tab) сайын іске қосылады.