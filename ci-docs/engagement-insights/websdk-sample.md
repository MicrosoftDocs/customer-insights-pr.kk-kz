---
title: Веб-SDK үлгісін іске қосу
description: SDK веб-үлгісін жекелендіру және іске қосу туралы мәлімет алыңыз.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 10/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 545f4a7e9660e339dee1070ad727d5d398eb6254
ms.sourcegitcommit: 693458e13e4b4d94b6205093559912f6a4dc4a1c
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 10/06/2021
ms.locfileid: "7606234"
---
# <a name="run-the-web-sdk-sample-for-dynamics-365-customer-insights-engagement-insights-capability"></a>Dynamics 365 Customer Insights өзара әрекеттестік туралы түсініктер мүмкіндігінің веб-SDK үлгісін іске қосу

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Өзара әрекеттестіктер туралы түсініктер мүмкіндігінің веб-SDK кітапханасы – бұл веб-сайтта пайдалануға болатын үлгі коды бар JavaScript кітапханасы.

## <a name="prerequisites"></a>Алғышарттар

- [Visual Studio кодын](https://code.visualstudio.com/) орнатыңыз.
- Visual Studio кодында [нақты сервер кеңейтімін орнатып](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer), нақты серверді іске қосу жолы туралы мәлімет алыңыз.
- Сізде [өзара әрекеттесу түсініктерінің жұмыс кеңістігі](create-workspace.md) болуы керек.

## <a name="run-sample"></a>Үлгіні іске қосу

1. [SDK веб-үлгісін жүктеп алыңыз](https://download.pi.dynamics.com/sdk/EngagementInsightsSamples/ei_websdk_sample.zip).

1. Қысылған `ei_websdk_sample.zip` файлын мұрағаттан шығарыңыз.

1. Visual Studio кодында мұрағаттан шығарылған қалтаны ашыңыз.

1. Жұмыс кеңістігіне арналған өзара әрекеттесу түсініктері порталына өтіңіз. **Әкімші** > **Жұмыс кеңістігі**  тармағына өтіңіз және содан кейін **Орнату бойынша нұсқаулық** құжатын таңдаңыз. Бірінші опцияны орындаңыз және JavaScript код үзіндісін көшіру үшін **Кодты көшіру** опциясын таңдаңыз.

1. `ei_websdk_sample.html` файлында мына жолдың астына көшірген код үзіндісін қойыңыз:

   - <-- ӨЗАРА ӘРЕКЕТТЕСУ ТҮСІНІКТЕРІ ПОРТАЛЫНДАҒЫ JAVASCRIPT КОД ҮЗІНДІСІН ОСЫ ЖОЛДЫҢ ТӨМЕНГІ ЖАҒЫНА ҚОЙЫҢЫЗ -->

1. Күй жолағынан **Күшіне ендіру** опциясын таңдау арқылы Visual Studio кодында нақты серверді пайдалану арқылы `ei_websdk_sample.html` файлын ашыңыз.

1. Бетті ашқан кезде қарау оқиғасы автоматты түрде жіберілуі тиіс. Беттегі кез келген түймені басу арқылы әрекет оқиғалары жіберіледі. **Оқиғаларды бақылау** түймесі реттелетін оқиғаларды жібереді. Bing веб-сайтына шарлау алдында **Bing браузеріне өті** түймесін таңдау кезінде әрекет оқиғасы жіберіледі.

1. Жұмыс кеңістігіне өткен кезде болатын оқиғаларға қараңыз. Бұл жұмыс кеңістігі 4-қадамда енгізілген қабылдау кілтімен байланысты.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
