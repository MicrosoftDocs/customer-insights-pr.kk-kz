---
title: Сегменттерді ActiveCampaign қызметіне экспорттау
description: ActiveCampaign қызметіне қосылымды және экспорттауды конфигурациялау жолы туралы ақпарат.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: e62888a6d618fb1154890e607d8c23d3767d35f7
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: MT
ms.contentlocale: kk-KZ
ms.lasthandoff: 10/27/2022
ms.locfileid: "9725407"
---
# <a name="export-segments-to-activecampaign-preview"></a>Сегменттерді ActiveCampaign қызметіне экспорттау (алдын ала қарау нұсқасы)

Бірыңғай тұтынушы профильдерінің сегменттерін ActiveCampaign қызметіне экспорттаңыз және оларды маркетингтік қызмет үшін пайдаланыңыз.

## <a name="prerequisites"></a>Алғышарттар

- Ан [ActiveCampaign тіркелгісі](https://www.activecampaign.com/) және сәйкес әкімшінің тіркелгі деректері.
- Ан [ActiveCampaign List идентификаторы](https://help.activecampaign.com/hc/articles/360000030559-How-to-create-a-list-in-ActiveCampaign).
- Ан [ActiveCampaign API кілті](https://help.activecampaign.com/hc/articles/207317590-Getting-started-with-the-API#how-to-obtain-your-activecampaign-api-url-and-key) және REST соңғы нүктенің хост атауы.
- [Конфигурацияланған сегменттер](segments.md) Customer Insights ішінде.
- Экспортталған сегменттердегі тұтынушылардың бірыңғай профильдері электрондық пошта мекенжайын көрсететін өрістен тұрады.

## <a name="known-limitations"></a>Белгілі шектеулер

- Өз жадыңызды әкеліңіз (BYOS) тіркесімімен жеке сілтемеге қолдау көрсетілмейді.
- ActiveCampaign бағдарламасына экспорттау үшін 1 миллионға дейін тұтынушы профилі, оны аяқтауға 90 минут кетуі мүмкін. ActiveCampaign қызметіне экспорттауға болатын тұтынушы профильдерінің саны ActiveCampaign қызметімен жасалған келісім-шартқа байланысты.
- Тек сегменттер.

## <a name="set-up-connection-to-activecampaign"></a>ActiveCampaign қызметіне қосылым орнату

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. **Әкімші** > **Қосылымдар** тармағына өтіңіз.

1. таңдаңыз **Қосылым қосыңыз** және таңдаңыз **ActiveCampaign**.

1. **Көрсетілетін аты** өрісінде қосылымға оңай танылатын атау енгізіңіз. Қосылым атауы мен түрі осы қосылымды сипаттайды. Қосылымның мақсатын түсіндіретін атауды таңдауды ұсынамыз.

1. Осы қосылымды кім пайдалана алатынын таңдаңыз. Әдепкі бойынша бұл тек әкімшілер. Қосымша ақпарат алу үшін [Салымшыларға экспорттау үшін қосылымды пайдалануға рұқсат беру](connections.md#allow-contributors-to-use-a-connection-for-exports) бөлімін қараңыз.

1. ActiveCampaign API кілтін және REST соңғы нүктесінің хост атауын енгізіңіз. REST соңғы нүктесінің хост атауы тек хосттың атауы болып табылады, яғни https:// префиксі жоқ.

1. шолу [деректердің құпиялылығы және сәйкестігі](connections.md#data-privacy-and-compliance) және таңдаңыз **Мен келісемін**.

1. таңдаңыз **Қосылу** қосылымды инициализациялау үшін.

1. **Өзіңізді экспорт пайдаланушысы ретінде қосу** пәрменін таңдап, өзіңіздің Customer Insights тіркелгі деректерін ұсыныңыз.

1. Қосылымды аяқтау үшін **Сақтау** түймешігін таңдаңыз.

## <a name="configure-an-export"></a>Экспорттауды конфигурациялау

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. **Деректер** > **Экспорттау** тармағына өтіңіз.

1. таңдаңыз **Экспортты қосыңыз**.

1. **Экспорттауға арналған қосылым** өрісінде ActiveCampaign бөлімінен қосылым таңдаңыз. Егер қосылым болмаса, әкімшіге хабарласыңыз.

1. Экспорттау үшін атау енгізіңіз.

1. Өзіңізді енгізіңіз **ActiveCampaign List идентификаторы**.

1. **Деректерді сәйкестендіру** бөлімінде **Электрондық пошта** өрісінде тұтынушының электрондық пошта мекенжайын көрсететін өрісті таңдаңыз.

1. Қажет болса, экспорттау **аты**, **·**, және **Телефон** жекелендірілген электрондық пошталарды жасау үшін. Осы өрістерді салыстыру үшін **Төлсипат қосу** пәрменін таңдаңыз.

1. Экспорттау керек сегменттерді таңдаңыз.

1. **Сақтау** пәрменін таңдаңыз.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
