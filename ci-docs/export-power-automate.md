---
title: Power Automate қосқышы | Microsoft Docs
description: Microsoft Power Automate бағдарламасында Dynamics 365 Customer Insights бағдарламасынан ағындар жасау.
ms.date: 06/24/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: d22c4c785695b23a257a89f1ffa519fdc18b443e
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: MT
ms.contentlocale: kk-KZ
ms.lasthandoff: 05/11/2022
ms.locfileid: "8741186"
---
# <a name="power-automate-connector-preview"></a>Power Automate коннекторы (алдын ала қарау)

Деректер өзгерген жағдайда, автоматты түрде орын алатын белгілі бір оқиғаларды іске қосыңыз және күрделірек ағындарды [Power Automate](https://flow.microsoft.com/) бағдарламасында тікелей басқарыңыз.

## <a name="known-limitations"></a>Белгілі шектеулер

- Сіз 60 секундта ең көбі 100 қоңырау шала аласыз. $skip параметрін пайдалану арқылы API соңғы нүктесіне бірнеше рет қоңырау шалуға болады. [$skip параметрі туралы көбірек біліңіз](/connectors/customerinsights/#get-items-from-an-entity).

## <a name="power-automate-triggers"></a>Power Automate триггерлері

Бұлтты ағындарды құру және хабарландырулар немесе жетілдірілген әрекеттер секілді қайталанатын тапсырмаларды автоматтандыру үшін триггерлерді пайдаланыңыз.

- Дереккөзді жаңарту сәтсіз болған кезде іске қосыңыз.
- Дереккөзді жаңарту сәтті болған кезде іске қосыңыз.
- Сегментте шектен асқан кезде іске қосыңыз. Триггер шектен асырмауға шектелген.
- Іскери шарада шектен асқан кезде іске қосыңыз. Тек өлшемсіз бизнес көрсеткіштеріне қолдау көрсетіледі. Триггер шектен асырмауға шектелген.
- Толық жаңарту (деректер көздері, сегменттер, шаралар, ...) аяқталған кезде іске қосыңыз.
- Біріктіру процесін жаңарту аяқталған кезде іске қосыңыз.

[Power Automate бағдарламасындағы триггерлерді конфигурациялаңыз.](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/)

## <a name="power-automate-actions"></a>Power Automate әрекеттері

Power Automate коннекторы қолжетімді триггерлерден бөлек басқа әрекеттерді қамтамасыз етеді. Толық ақпарат алу үшін [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/) қараңыз.

## <a name="create-a-power-automate-flow"></a>Power Automate ағынын жасау

1. **Әкімші** > **Экспорттық межелі орындар** тармағына өтіңіз.

1. **Power Automate** тақтасында **Реттеу** түймешігін таңдаңыз.

1. Power Automate жүйесінде Customer Insights қосқышы (алдын ала қарау) ашылады. Power Automate жүйесіне **кіріңіз**.

1. Қолжетімді триггерлердің бірін таңдап, жаңа ағынға қосымша қадамдар қосыңыз. Қосымша ақпарат алу үшін [Power Automate бағдарламасында бұлттық ағынды жасау](/power-automate/get-started-logic-flow) бөлімін қараңыз.

Ағындарды пайдалану мысалдары: 
- Деректер көзін жаңарту орындалмаса, Microsoft Teams арнасына хабар жіберіңіз. 
- Сегменттегі шек қиылыспағанда, деректер иеленушілеріне электрондық хабар жіберіңіз.



[!INCLUDE [footer-include](includes/footer-banner.md)]
