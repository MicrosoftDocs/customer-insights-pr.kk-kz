---
title: Power Automate қосқышы | Microsoft Docs
description: Dynamics 365 Customer Insights жүйесінен Microsoft Power Automate ішінде ағындар жасаңыз.
ms.date: 01/20/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
ms.reviewer: philk
manager: shellyha
ms.openlocfilehash: fb1df4e9ab1f78300b8ec1f8dfdfbfbac0e71447
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268831"
---
# <a name="power-automate-connector-preview"></a>Power Automate коннекторы (алдын ала қарау)

Деректер өзгерген жағдайда, автоматты түрде орын алатын белгілі бір оқиғаларды іске қосыңыз және күрделірек ағындарды [Power Automate](https://flow.microsoft.com/) бағдарламасында тікелей басқарыңыз.

## <a name="power-automate-triggers"></a>Power Automate триггерлері

Бұлтты ағындарды құру және хабарландырулар немесе жетілдірілген әрекеттер секілді қайталанатын тапсырмаларды автоматтандыру үшін триггерлерді пайдаланыңыз. 

- Дереккөзді жаңарту сәтсіз болған кезде іске қосыңыз. 
- Дереккөзді жаңарту сәтті болған кезде іске қосыңыз.
- Сегментте шектен асқан кезде іске қосыңыз. Триггер шектен асырмауға шектелген.
- Іскери шарада шектен асқан кезде іске қосыңыз. Триггер шектен асырмау күйіне шектелген.
- Толық жаңарту (деректер көздері, сегменттер, шаралар,...) аяқталған кезде іске қосыңыз.
- Бірегейлендіру процесін жаңарту (карта, сәйкестік, біріктіру) аяқталған кезде іске қосу.

[Power Automate жүйесінде триггерлеріңізді теңшеңіз](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).

## <a name="power-automate-actions"></a>Power Automate әрекеттері
Power Automate коннекторы қолжетімді триггерлерден бөлек басқа әрекеттерді қамтамасыз етеді. Толық ақпарат алу үшін [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/) қараңыз.

## <a name="create-a-power-automate-flow"></a>Power Automate ағынын жасау

1. Аудитория мәліметтерінде **Әкімші** > **Экспорттау мақсаттары** тармағына өтіңіз.

1. **Power Automate** тақтасында **Реттеу** түймешігін таңдаңыз.

1. Power Automate жүйесінде Customer Insights қосқышы (алдын ала қарау) ашылады. Power Automate жүйесіне **кіріңіз**.

1. Қолжетімді триггерлердің бірін таңдап, жаңа ағынға қосымша қадамдар қосыңыз. Қосымша ақпарат алу үшін [Power Automate бағдарламасында бұлттық ағынды жасау](https://docs.microsoft.com/power-automate/get-started-logic-flow) бөлімін қараңыз.

Ағындарды пайдалану мысалдары: 
- Деректер көзін жаңарту орындалмаса, Microsoft Teams арнасына хабар жіберіңіз. 
- Сегменттегі шек қиылыспағанда, деректер иеленушілеріне электрондық хабар жіберіңіз.



[!INCLUDE[footer-include](../includes/footer-banner.md)]