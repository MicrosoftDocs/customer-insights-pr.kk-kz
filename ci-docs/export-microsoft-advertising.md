---
title: Сегменттерді Microsoft Advertising (алдын ала қарау нұсқасы) қызметіне экспорттау
description: Microsoft Advertising қызметі үшін қосылымды конфигурациялау және экспорттау жолы туралы ақпарат.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 44217e7823ffbe14d232b3e33de1b4ea6ed69dcf
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: kk-KZ
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196539"
---
# <a name="export-segments-to-microsoft-advertising-preview"></a>Сегменттерді Microsoft Advertising (алдын ала қарау нұсқасы) қызметіне экспорттау

Customer Match аудиториясын жасау үшін Customer Insights сегменттерін Microsoft Advertising қызметіне экспорттаңыз. Осы аудиторияны жарнамалық науқан үшін пайдаланыңыз.

## <a name="prerequisites"></a>Алғышарттар

- А [Microsoft Advertising тіркелгісі](https://ads.microsoft.com/) және сәйкес әкімшінің тіркелгі деректері.
- Microsoft Advertising тұтынушы идентификаторы және тіркелгі идентификаторы. Тұтынушы идентификаторын табыңыз (`cid`) және тіркелгі идентификаторы (`aid`) Microsoft Advertising жүйесіне кірген кезде URL мекенжайының параметрлерінде.
- Customer Match пайдалану шарттары қабылданады.
- [Конфигурацияланған сегменттер](segments.md) Customer Insights ішінде.
- Экспортталған сегменттердегі тұтынушылардың бірыңғай профильдері электрондық пошта мекенжайын көрсететін өрістен тұрады.

## <a name="known-limitations"></a>Белгілі шектеулер

- Microsoft Advertising бағдарламасына экспорттау үшін 500 000 тұтынушы профиліне дейін, бұл 10 минутқа дейін созылуы мүмкін.
- Тек сегменттер.

## <a name="set-up-connection-to-microsoft-advertising"></a>Microsoft Advertising қосылымын орнатыңыз

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. **Әкімші** > **Қосылымдар** тармағына өтіңіз.

1. таңдаңыз **Қосылым қосыңыз** және таңдаңыз **Microsoft Advertising**.

1. **Көрсетілетін аты** өрісінде қосылымға оңай танылатын атау енгізіңіз. Қосылым атауы мен түрі осы қосылымды сипаттайды. Қосылымның мақсатын түсіндіретін атауды таңдауды ұсынамыз.

1. Осы қосылымды кім пайдалана алатынын таңдаңыз. Әдепкі бойынша әкімшілер. Қосымша ақпарат алу үшін [Салымшыларға экспорттау үшін қосылымды пайдалануға рұқсат беру](connections.md#allow-contributors-to-use-a-connection-for-exports) бөлімін қараңыз.

1. енгізіңіз **Microsoft Advertising тұтынушы идентификаторы**.

1. шолу [деректердің құпиялылығы және сәйкестігі](connections.md#data-privacy-and-compliance) және таңдаңыз **Мен келісемін**.

1. таңдаңыз **Қосылу** қосылымды инициализациялау үшін.

1. **Microsoft Advertising қызметімен аутентификациялау** опциясын таңдаңыз және Microsoft Advertising қызметі үшін әкімші тіркелгі деректерін беріңіз.

1. **Өзіңізді экспорт пайдаланушысы ретінде қосу** пәрменін таңдап, өзіңіздің Customer Insights тіркелгі деректерін ұсыныңыз.

1. Қосылымды аяқтау үшін **Сақтау** түймешігін таңдаңыз.

## <a name="configure-an-export"></a>Экспорттауды конфигурациялау

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. **Деректер** > **Экспорттау** тармағына өтіңіз.

1. таңдаңыз **Экспортты қосыңыз**.

1. **Экспорттауға арналған қосылым** өрісінде Microsoft Advertising бөлімінен қосылым таңдаңыз. Егер қосылым болмаса, әкімшіге хабарласыңыз.

1. Экспорттау үшін атау енгізіңіз.

1. Экспорттайтын сегменттерді таңдаңыз. Microsoft Advertising қызметіндегі Customer Match аудиториялары экспорттау үшін таңдалған сегменттердің атауымен автоматты түрде жасалады. Әрбір сегмент бөлек Customer Match аудиториясына әкеледі.

1. **Microsoft Advertising тұтынушы идентификаторы мен тіркелгі идентификаторын** енгізіңіз.

1. **Деректерді сәйкестендіру** бөлімінде **Электрондық пошта** өрісінде тұтынушының электрондық пошта мекенжайы бар өрісті таңдаңыз.

1. **Сақтау** пәрменін таңдаңыз.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
