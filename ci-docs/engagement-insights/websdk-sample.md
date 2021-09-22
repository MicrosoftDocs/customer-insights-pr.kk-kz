---
title: Веб-SDK үлгісін іске қосу
description: SDK веб-үлгісін жекелендіру және іске қосу туралы мәлімет алыңыз.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 10/30/2020
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 97e50a51231bcf05f3e381397f0cf41e49afc10e3c3674d7c709c8f521979e12
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036610"
---
# <a name="run-the-web-sdk-sample-for-dynamics-365-customer-insights-engagement-insights-capability"></a>Dynamics 365 Customer Insights өзара әрекеттестік туралы түсініктер мүмкіндігінің веб-SDK үлгісін іске қосу

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Өзара әрекеттестіктер туралы түсініктер мүмкіндігінің веб-SDK кітапханасы – бұл веб-сайтта пайдалануға болатын үлгі коды бар JavaScript кітапханасы.

## <a name="prerequisites"></a>Алғышарттар

- [Visual Studio кодын](https://code.visualstudio.com/) орнатыңыз.
- Visual Studio кодында [нақты сервер кеңейтімін орнатып](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer), нақты серверді іске қосу жолы туралы мәлімет алыңыз.
- Сізде [қабылдау кілті](instrument-website.md) болуы тиіс.

## <a name="run-sample"></a>Үлгіні іске қосу

1. [SDK веб-үлгісін жүктеп алыңыз](https://download.pi.dynamics.com/sdk/EngagementInsightsSamples/ei_websdk_sample.zip).

1. Қысылған `ei_websdk_sample.zip` файлын мұрағаттан шығарыңыз.

1. Visual Studio кодында мұрағаттан шығарылған қалтаны ашыңыз.

1. `ei_websdk_sample.html` файлында “INGESTION_KEY” жолын өзара әрекеттестік туралы түсініктер мүмкіндігі порталындағы қабылдау кілтімен, ал “АТАУЫ” жолын SDK үлгісін жасау қажет глобалдық атаумен алмастырыңыз. Барлық енгізулерді ауыстырғаныңызға көз жеткізіңіз.

1. Күй жолағынан **Күшіне ендіру** опциясын таңдау арқылы Visual Studio кодында нақты серверді пайдалану арқылы `ei_websdk_sample.html` файлын ашыңыз.

1. Бетті ашқан кезде қарау оқиғасы автоматты түрде жіберілуі тиіс. Беттегі кез келген түймені басу арқылы әрекет оқиғалары жіберіледі. **Оқиғаларды бақылау** түймесі реттелетін оқиғаларды жібереді. Bing веб-сайтына шарлау алдында **Bing браузеріне өті** түймесін таңдау кезінде әрекет оқиғасы жіберіледі.

1. Жұмыс кеңістігіне өткен кезде болатын оқиғаларға қараңыз. Бұл жұмыс кеңістігі 4-қадамда енгізілген қабылдау кілтімен байланысты.


[!INCLUDE[footer-include](../includes/footer-banner.md)]