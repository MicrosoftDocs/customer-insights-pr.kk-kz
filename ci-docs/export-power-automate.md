---
title: Power Automate қосқыш (алдын ала қарау) | Microsoft құжаттары
description: Microsoft Power Automate бағдарламасында Dynamics 365 Customer Insights бағдарламасынан ағындар жасау.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: f87bd6db7143294a264813f6c5c7d7963f303628
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: kk-KZ
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196125"
---
# <a name="power-automate-connector-preview"></a>Power Automate коннекторы (алдын ала қарау)

Деректер өзгерген жағдайда, автоматты түрде орын алатын белгілі бір оқиғаларды іске қосыңыз және күрделірек ағындарды [Microsoft Power Automate](https://flow.microsoft.com/) бағдарламасында тікелей басқарыңыз.

## <a name="known-limitations"></a>Белгілі шектеулер

- 60 секундта ең көбі 100 қоңырау. пайдаланыңыз [$skip параметрі](/connectors/customerinsights/#get-items-from-an-entity) API соңғы нүктесін бірнеше рет шақыру.

## <a name="power-automate-triggers"></a>Power Automate триггерлері

Бұлтты ағындарды құру және хабарландырулар немесе жетілдірілген әрекеттер секілді қайталанатын тапсырмаларды автоматтандыру үшін триггерлерді пайдаланыңыз. Триггерлерді келесі жағдайларда пайдаланыңыз:

- деректер көзі жаңарту сәтсіз аяқталды.
- деректер көзі жаңартуы сәтті аяқталды.
- Сегментте шектен асқан. Триггер шектен асырмауға шектелген.
- Іскерлік өлшем бойынша табалдырық атталады. Тек өлшемсіз бизнес көрсеткіштеріне қолдау көрсетіледі. Триггер шектен асырмауға шектелген.
- Толық жоспарланған жаңарту аяқталды. Бұл триггер қолмен басталған жаңартулар үшін жұмыс істемейді.
- Біріктіру процесін жаңарту аяқталды.

[Power Automate бағдарламасындағы триггерлерді конфигурациялаңыз.](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/)

## <a name="power-automate-actions"></a>Power Automate әрекеттері

Power Automate коннекторы қолжетімді триггерлерден бөлек басқа әрекеттерді қамтамасыз етеді. Толық ақпарат алу үшін [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/) қараңыз.

## <a name="create-a-power-automate-flow"></a>Power Automate ағынын жасау

1. **Әкімші** > **Қосылымдар** тармағына өтіңіз.

1. **Power Automate** тақтасында **Реттеу** түймешігін таңдаңыз.

1. Power Automate жүйесінде Customer Insights қосқышы (алдын ала қарау) ашылады. Power Automate жүйесіне **кіріңіз**.

1. Қолжетімді триггерлердің бірін таңдап, жаңа ағынға қосымша қадамдар қосыңыз. Қосымша ақпарат алу үшін [Power Automate бағдарламасында бұлттық ағынды жасау](/power-automate/get-started-logic-flow) бөлімін қараңыз.

Ағындарды пайдалану мысалдары: 
- Деректер көзін жаңарту орындалмаса, Microsoft Teams арнасына хабар жіберіңіз. 
- Сегменттегі шек қиылыспағанда, деректер иеленушілеріне электрондық хабар жіберіңіз.

[!INCLUDE [footer-include](includes/footer-banner.md)]
