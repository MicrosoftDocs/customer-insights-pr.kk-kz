---
title: LiveRamp коннекторы
description: LiveRamp қызметі үшін қосылымды конфигурациялау және экспорттау жолы туралы ақпарат.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 973f69c94c625fe4ec543ca5fb57289c4102ea97
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: kk-KZ
ms.lasthandoff: 04/27/2022
ms.locfileid: "8643890"
---
# <a name="export-segments-to-liverampreg-preview"></a>Сегменттерді LiveRamp&reg; қызметіне экспорттау (алдын ала қарау нұсқасы)

Сандық, әлеуметтік және теледидарлардағы 500-ден астам платформалармен байланыс орнату үшін LiveRamp қызметіндегі деректеріңізді белсендіріңіз. Жарнамалық науқандарды белгілеу, тоқтату және даралау үшін LiveRamp платформасындағы деректермен жұмыс істеңіз.

## <a name="prerequisites-for-a-connection"></a>Қосылым алғышарттары

- Бұл қосқышты пайдалану үшін LiveRamp жазылымы қажет.
- Жазылымды алу үшін [LiveRamp платформасына](https://liveramp.com/contact/) байланысыңыз. [LiveRamp Onboarding жүйесі жөнінде мәлімет алыңыз](https://liveramp.com/our-platform/data-onboarding/).

## <a name="set-up-connection-to-liveramp"></a>LiveRamp қызметіне қосылым орнату

1. **Әкімші** > **Қосылымдар** тармағына өтіңіз.

1. **Қосылым қосу** түймешігін таңдаңыз және қосылымды конфигурациялау үшін **LiveRamp** параметрін таңдаңыз.

1. **Көрсетілетін аты** өрісінде қосылымға оңай танылатын атау енгізіңіз. Қосылым атауы мен түрі осы қосылымды сипаттайды. Қосылымның мақсатын түсіндіретін атауды таңдауды ұсынамыз.

1. Осы қосылымды кім пайдалана алатынын таңдаңыз. Егер сіз ешқандай әрекет жасамасаңыз, әдепкі бойынша Әкімшілер болады. Қосымша ақпарат алу үшін [Салымшыларға экспорттау үшін қосылымды пайдалануға рұқсат беру](connections.md#allow-contributors-to-use-a-connection-for-exports) бөлімін қараңыз.

1. LiveRamp Secure FTP (SFTP) тіркелгісі үшін **Пайдаланушы аты** мен **Құпиясөзді** енгізіңіз.
Бұл тіркелгі деректері LiveRamp Onboarding тіркелгі деректерінен өзгеше болуы мүмкін.

1. LiveRamp платформасына қосылымды сынау үшін **Тексеру** опциясын таңдаңыз.

1. Сәтті түрде тексерілгеннен кейін **Мен келісемін** өрісіне құсбелгі қою арқылы **Деректердің құпиялылығы мен сәйкестігі** үшін келісім беріңіз.

1. Қосылымды аяқтау үшін **Сақтау** түймешігін таңдаңыз.

## <a name="configure-an-export"></a>Экспорттауды конфигурациялау

Егер сіз осы түрдегі қосылымға қатынаса алсаңыз, сіз бұл экспорттауды конфигурациялай аласыз. Қосымша ақпарат алу үшін [Экспорттауды конфигурациялау үшін қажет рұқсаттар](export-destinations.md#set-up-a-new-export) бөлімін қараңыз.

1. **Деректер** > **Экспорттау** тармағына өтіңіз.

1. Жаңа экспорттау жасау үшін **Мақсатты орын қосу** түймешігін таңдаңыз.

1. **Экспорттауға арналған қосылым** өрісінде LiveRamp бөлімінен қосылым таңдаңыз. Егер сіз осы бөлімнің атын көрмесеңіз, сізге қолжетімді осы түрдегі қосылым жоқ.

1. **Негізгі идентификаторды таңдау** өрісінде сәйкестік шешімі үшін LiveRamp платформасына жіберу үшін **Электрондық пошта**, **Атауы және мекенжайы** немесе **Телефон** параметрлерін таңдаңыз.
   > [!div class="mx-imgBorder"]
   > ![Төлсипаттық салыстыру жүйесі бар LiveRamp қосқышы.](media/export-liveramp-segments.png "Төлсипаттық салыстыру жүйесі бар LiveRamp қосқышы")

1. *Тұтынушы* нысанындағы тиісті төлсипаттарды таңдалған кілт идентификаторы үшін салыстырыңыз.

1. LiveRamp қызметіне жіберетін қосымша төлсипаттарды көрсету үшін **Төлсипат қосу** түймешігін таңдаңыз.

   > [!TIP]
   > LiveRamp платформасына қосымша негізгі идентификатор төлсипаттарын жіберу жоғары сәйкестендіру жиілігіне алып келеді.

1. LiveRamp платформасына экспорттау қажет сегменттерді таңдаңыз.

1. **Сақтау** опциясын таңдаңыз.

Экспорттауды сақтау экспорттауды бірден іске қоспайды.

Экспорттау әр [жоспарланған жаңартумен](system.md#schedule-tab) іске қосылады. Сондай-ақ [деректерді сұрау бойынша экспорттауға](export-destinations.md#run-exports-on-demand) болады. 


## <a name="data-privacy-and-compliance"></a>Деректердің құпиялылығы мен сәйкестігі

Деректерді Liveramp платформасына жіберу үшін Dynamics 365 Customer Insights бағдарламасын қосқан кезде, Dynamics 365 Customer Insights талаптарына сәйкестік шекарасынан тыс деректерді, соның ішінде жеке деректер сияқты ықтимал құпия деректерді беруге мүмкіндік бересіз. Microsoft мұндай деректерді сіздің нұсқауыңыз бойынша тасымалдайды, бірақ Liveramp платформасының кез келген құпиялылық немесе қауіпсіздік міндеттемелеріне сәйкес келуіне жауап бересіз. Қосымша ақпаратты [Microsoft құпиялық туралы мәлімдемесі](https://go.microsoft.com/fwlink/?linkid=396732) бөлімінен қараңыз.
Бұл функцияны тоқтату үшін бұл экспорттау мақсатын кез келген уақытта Dynamics 365 Customer Insights әкімшісі жоя алады.

[!INCLUDE [footer-include](includes/footer-banner.md)]