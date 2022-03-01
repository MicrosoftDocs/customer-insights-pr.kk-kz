---
title: Power Automate қосқышы | Microsoft Docs
description: Dynamics 365 Customer Insights жүйесінен Microsoft Power Automate ішінде ағындар жасаңыз.
ms.date: 08/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: philk
manager: shellyha
ms.openlocfilehash: ffe92414365b0b777691a4a2d585100e4fbea591
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406206"
---
# <a name="power-automate-connector-preview"></a>Power Automate коннекторы (алдын ала қарау)

Деректер өзгерген жағдайда, автоматты түрде орын алатын белгілі бір оқиғаларды іске қосыңыз және күрделірек ағындарды [Power Automate](https://flow.microsoft.com/) бағдарламасында тікелей басқарыңыз.

## <a name="power-automate-triggers"></a>Power Automate триггерлері

Хабарландырулар немесе қосымша кеңейтілген әрекеттер сияқты қайталанатын тапсырмаларды автоматтандыру үшін ағындарды жасауға мүмкіндік беретін әртүрлі триггерлерді пайдалана аласыз. 

- Дереккөзді жаңарту сәтсіз болған кезде іске қосыңыз. 
- Дереккөзді жаңарту сәтті болған кезде іске қосыңыз.
- Сегментте шектен асқан кезде іске қосыңыз. Триггер шектен асырмауға шектелген.
- Іскери шарада шектен асқан кезде іске қосыңыз. Триггер шектен асырмау күйіне шектелген.
- Толық жаңарту (деректер көздері, сегменттер, шаралар,...) аяқталған кезде іске қосыңыз.
- Бірегейлендіру процесін жаңарту (карта, сәйкестік, біріктіру) аяқталған кезде іске қосу.

[Power Automate жүйесінде триггерлеріңізді теңшеңіз](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).

## <a name="power-automate-actions"></a>Power Automate әрекеттері
Power Automate коннекторы қолжетімді триггерлерден бөлек басқа әрекеттерді қамтамасыз етеді. Толық ақпарат алу үшін [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/) қараңыз.

## <a name="create-a-power-automate-flow-in-audience-insights"></a>Аудитория түсініктерінде Power Automate ағынын жасау

1. Аудитория түсініктерінде **Әкімші** > **Жүйе** тармағына өтіңіз.

1. **Жүйе** бетінен **Күй** қойыншасын таңдаңыз.

1. **Деректер көздері** бөлімінде **Ағындар** параметріне және ашылмалы тізімнен **Ағын жасау** опциясын таңдаңыз.
   > [!div class="mx-imgBorder"]
   > ![Power Automate коннекторы Ағынды жасау әрекетін көрсетеді](media/power-automate-connector-create-flow.png "Power Automate коннекторы Ағынды жасау әрекетін көрсетеді")

1. Power Automate бағдарламасында қажетті ағынды жасау үшін қолжетімді триггерлердің біреуін таңдаңыз. Алғашқы ағынды жасап жатсаңыз, алдымен Power Automate коннекторы көмегімен түпнұсқалығын растауыңыз керек болады.
