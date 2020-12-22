---
title: Customer Insights деректерін Google Ads платформасына экспорттау
description: Google Ads платформасына қосылуды конфигурациялау жолы туралы ақпарат.
ms.date: 11/18/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 06aa0b6ff3125d8735adc8c8f9f6dad69087d9f8
ms.sourcegitcommit: ff824bbbd31fd666ab0da682bf48ea31580d242c
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 11/18/2020
ms.locfileid: "4568463"
---
# <a name="connector-for-google-ads-preview"></a>Google Ads қосқышы (алдын ала қарау)

Тұтынушылардың біріңғай профильдерінің сегменттерін Google Ads аудиториясының тізіміне экспорттаңыз және оларды Google Search, Gmail, YouTube және Google көрсету желілерінде жарнамалаңыз. 

## <a name="prerequisites"></a>Алғышарттар

-   Сізде [Google Ads тіркелгісі](https://ads.google.com/) және тиісті әкімшінің тіркелгі деректері бар.
-   Google Ads платформасында қолданыстағы аудиториялар және тиісті идентификаторлар бар. Қосымша ақпарат алу үшін [Google Ads аудиториялары](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.) бөлімін қараңыз.
-   Сізде [конфигурацияланған сегменттер](segments.md) бар
-   Экспортталған сегменттердегі тұтынушылардың бірыңғай профильдері электрондық пошта мекенжайын, аты және тегін көрсететін өрістерден тұрады

## <a name="connect-to-google-ads"></a>Google Ads қолданбасына қосылу

1. **Әкімші** > **Экспорттық межелі орындар** тармағына өтіңіз.

1. **Google Ads** астында **Орнату** пәрменін таңдаңыз.

1. **Көрсетілетін атауы** өрісінде экспорттық межелі орынға танылатын атау беріңіз.

1. **[Google Ads тұтынушы идентификаторын](https://support.google.com/google-ads/answer/1704344)** енгізіңіз.

1. **[Google Ads мақұлдаған әзірлеуші таңбалауышын](https://developers.google.com/google-ads/api/docs/first-call/dev-token)** енгізіңіз.

1. **Деректер құпиялығы мен сәйкестігін** растау үшін **Мен келісемін** параметрін таңдаңыз.

1. Google Ads платформасына қосылуды баптандыру үшін **[Google Ads аудиториясының идентификаторын](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** енгізіп, **Қосылу** пәрменін таңдаңыз.

1. **Google Ads көмегімен аутентификациялау** пәрменін таңдап, Google Ads тіркелгі деректерін ұсыныңыз.

1. **Өзіңізді экспорт пайдаланушысы ретінде қосу** пәрменін таңдап, өзіңіздің Customer Insights тіркелгі деректерін ұсыныңыз.

   :::image type="content" source="media/export-segments-googleads.PNG" alt-text="Google Ads қосылымына арналған скриншотты экспорттау":::

1. Экспорттауды теңшеу үшін **Келесі** параметрін таңдаңыз.

## <a name="configure-the-connector"></a>Қосқышты конфигурациялау

1. **Деректерді салыстыру** бөліміндегі **Электрондық пошта** өрісінде тұтынушының электрондық пошта мекенжайын көрсететін бірыңғай тұтынушы профиліндегі өрісті таңдаңыз. **Аты** және **Тегі** өрістері үшін бірдей қадамдарды қайталаңыз.

1. Экспорттау керек сегменттерді таңдаңыз. Google Ads платформасына жалпы 1 миллионға дейін тұтынушы профилін экспорттай аласыз.

1. **Сақтау** опциясын таңдаңыз.

## <a name="export-the-data"></a>Деректерді экспорттау

[Сұрау бойынша деректерді экспорттауға](export-destinations.md) болады. Экспорттау сондай-ақ әрбір [жоспарланған жаңарту](system.md#schedule-tab) сайын іске қосылады. Google Ads платформасында, өз сегменттеріңізді [Google Ads аудиториялары](https://support.google.com/google-ads/answer/7558048?hl=en/) астынан табуға болады.

## <a name="known-limitations"></a>Белгілі шектеулер

- Google Ads платформасына 1 миллионға дейін профильді экспорттауға болады.
- Google Ads платформасына экспорттау тек сегменттермен шектеледі.
- Жалпы саны 1 миллион профильді экспорттайтын сегменттер провайдер тарапынан шектеулер болғандықтан 5 минутқа созылуы мүмкін. 
- Google Ads платформасында салыстыру 48 сағатқа созылуы мүмкін.

## <a name="data-privacy-and-compliance"></a>Деректердің құпиялылығы мен сәйкестігі

Деректерді Google Ads платформасына жіберу үшін Dynamics 365 Customer Insights бағдарламасын қосқан кезде, Dynamics 365 Customer Insights талаптарына сәйкестік шекарасынан тыс деректерді, соның ішінде жеке деректер сияқты ықтимал құпия деректерді беруге мүмкіндік бересіз. Microsoft мұндай деректерді сіздің нұсқауыңыз бойынша тасымалдайды, бірақ Google Ads кез келген құпиялылық немесе қауіпсіздік міндеттемелеріне сәйкес келуіне жауап бересіз. Қосымша ақпаратты [Microsoft құпиялық туралы мәлімдемесі](https://go.microsoft.com/fwlink/?linkid=396732) бөлімінен қараңыз.
Бұл функцияны тоқтату үшін бұл экспорттау мақсатын кез келген уақытта Dynamics 365 Customer Insights әкімшісі жоя алады.
