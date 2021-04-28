---
title: Customer Insights деректерін RollWorks қызметіне экспорттау
description: RollWorks қызметі үшін қосылымды конфигурациялау және экспорттау жолы туралы ақпарат.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 4979f0147dea2270f11342c1bb6b0693f3c24aea
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760573"
---
# <a name="export-segment-lists-to-rollworks-preview"></a>Сегмент тізімдерін RollWorks қызметіне экспорттау (алдын ала қарау нұсқасы)

Тұтынушылардың бірыңғай профильдерінің сегменттерін RollWorks қызметіне экспорттаңыз және оларды жарнама үшін пайдаланыңыз. 

## <a name="prerequisites-for-a-connection"></a>Қосылым алғышарттары

-   Сізде [RollWorks қызметінің тіркелгісі](https://www.rollworks.com/) және тиісті әкімші тіркелгі деректері бар.
-   Аудитория түсініктерінде [конфигурацияланған сегменттер](segments.md) бар.
-   Экспортталған сегменттердегі тұтынушылардың бірыңғай профильдері электрондық пошта мекенжайын көрсететін өрістен тұрады.

## <a name="known-limitations"></a>Белгілі шектеулер

- RollWorks қызметіне бір экспорттаған кезде 250000 профильді экспорттауға болады.
- RollWorks қызметіне 100-ден аз профилі бар сегменттерді экспорттау мүмкін емес. 
- RollWorks қызметіне экспорттау сегменттермен шектеледі.
- RollWorks қызметіне 250000 дейінгі профильді экспорттауды аяқтау 10 минутқа созылуы мүмкін. 
- RollWorks қызметіне экспорттауға болатын профильдер саны RollWorks қызметімен келісімшартқа байланысты және шектеулі.

## <a name="set-up-connection-to-rollworks"></a>RollWorks қызметіне қосылым орнату

1. **Әкімші** > **Қосылымдар** тармағына өтіңіз.

1. **Қосылым қосу** түймешігін таңдаңыз және қосылымды конфигурациялау үшін **RollWorks** параметрін таңдаңыз.

1. **Көрсетілетін аты** өрісінде қосылымға оңай танылатын атау енгізіңіз. Қосылым атауы мен түрі осы қосылымды сипаттайды. Қосылымның мақсатын түсіндіретін атауды таңдауды ұсынамыз.

1. Осы қосылымды кім пайдалана алатынын таңдаңыз. Егер сіз ешқандай әрекет жасамасаңыз, әдепкі бойынша Әкімшілер болады. Қосымша ақпарат алу үшін [Салымшыларға экспорттау үшін қосылымды пайдалануға рұқсат беру](connections.md#allow-contributors-to-use-a-connection-for-exports) бөлімін қараңыз.

1. **Деректер құпиялығы мен сәйкестігін** растау үшін **Мен келісемін** параметрін таңдаңыз.

1. RollWorks қызметіне қосылымды баптандыру үшін **Қосылу** түймешігін таңдаңыз.

1. **RollWorks қызметімен аутентификациялау** опциясын таңдаңыз және RollWorks қызметі үшін әкімші тіркелгі деректерін беріңіз.

1. **Өзіңізді экспорт пайдаланушысы ретінде қосу** пәрменін таңдап, өзіңіздің Customer Insights тіркелгі деректерін ұсыныңыз.

1. Қосылымды аяқтау үшін **Сақтау** түймешігін таңдаңыз.

## <a name="configure-an-export"></a>Экспорттауды конфигурациялау

Егер сіз осы түрдегі қосылымға қатынаса алсаңыз, сіз бұл экспорттауды конфигурациялай аласыз. Қосымша ақпарат алу үшін [Экспорттауды конфигурациялау үшін қажет рұқсаттар](export-destinations.md#set-up-a-new-export) бөлімін қараңыз.

1. **Деректер** > **Экспорттау** тармағына өтіңіз.

1. Жаңа экспорттау жасау үшін **Мақсатты орын қосу** түймешігін таңдаңыз.

1. **Экспорттауға арналған қосылым** өрісінде RollWorks бөлімінен қосылым таңдаңыз. Егер сіз осы бөлімнің атын көрмесеңіз, сізге қолжетімді осы түрдегі қосылым жоқ.

1. **RollWorks жарнама беруші идентификаторын** [RollWorks Advertisable](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles) енгізіңіз.

3. **Деректерді салыстыру** бөліміндегі **Электрондық пошта** өрісінде тұтынушының электрондық пошта мекенжайын көрсететін бірыңғай тұтынушы профиліндегі өрісті таңдаңыз. Бұл RollWorks қызметіне сегменттерді экспорттау үшін қажет.

1. Экспорттау керек сегменттерді таңдаңыз. Кемінде 100 мүшесі бар сегментті таңдаңыз. Кішірек сегменттерді экспорттау мүмкін емес. Сонымен қатар, экспортталатын сегменттің максималды мөлшері әр экспортқа 250000 мүшені құрайды. 

1. **Сақтау** опциясын таңдаңыз.

Экспорттауды сақтау экспорттауды бірден іске қоспайды.

Экспорттау әр [жоспарланған жаңартумен](system.md#schedule-tab) іске қосылады. Сондай-ақ [деректерді сұрау бойынша экспорттауға](export-destinations.md#run-exports-on-demand) болады. 


## <a name="data-privacy-and-compliance"></a>Деректердің құпиялылығы мен сәйкестігі

Деректерді RollWorks қызметіне тасымалдау үшін Dynamics 365 Customer Insights бағдарламасын қосқан кезде жеке деректер сияқты ықтимал құпия деректерді қоса алғанда, деректерді Dynamics 365 Customer Insights бағдарламасының үйлесімділік шегінен тыс тасымалдауға рұқсат бересіз. Microsoft корпорациясы мұндай деректерді сіздің нұсқауыңыз бойынша жібереді, бірақ сіз RollWorks қызметінің кез-келген құпиялылық немесе қауіпсіздік міндеттемелерінің орындалуына кепілдік беретініне жауаптысыз. Қосымша ақпаратты [Microsoft құпиялық туралы мәлімдемесі](https://go.microsoft.com/fwlink/?linkid=396732) бөлімінен қараңыз.

Бұл функцияны тоқтату үшін бұл экспорттау мақсатын кез келген уақытта Dynamics 365 Customer Insights әкімшісі жоя алады.