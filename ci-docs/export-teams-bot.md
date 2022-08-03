---
title: Dynamics 365 Customer Insights үшін Teams боты (алдын ала қарау)
description: Microsoft Teams жұмыс кеңістігінде боттың көмегімен тұтынушының бірыңғай профильдерін іздеңіз.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: d140ae72578b48091a41005c4acafe03bac540da
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: kk-KZ
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195849"
---
# <a name="teams-bot-for-dynamics-365-customer-insights-preview"></a>Dynamics 365 Customer Insights үшін Teams боты (алдын ала қарау)

Ботқа Teams арналарынан тұтынушының бірыңғай профилін іздеуге мүмкіндік беру үшін Microsoft Teams жұмыс кеңістігімен қосылыңыз.

:::image type="content" source="media/teams-bot.png" alt-text="Teams боты тұтынушы жазбасын көрсетеді":::

## <a name="prerequisites"></a>Алғышарттар

- Кем дегенде біреуі [деректер көзі қосылды](data-sources.md).
- [Бірыңғайландыру процесі](data-unification.md) аяқталған.
- Өрістерге қосылады [іздеу және сүзгі индексі](search-filter-index.md).
- Customer Insights және Teams жүйелері бір ұйымда.
- Сіздің ортаңызда жеке тұтынушыларға арналған негізгі мақсатты аудитория бар. Бизнес тіркелгілерге қолдау көрсетілмейді.


> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWRElj]

## <a name="configure-the-bot"></a>Ботты конфигурациялау

1. **Әкімші** > **Қосылымдар** тармағына өтіңіз.
1. Microsoft Teams қатарында **Орнату** түймесін таңдаңыз.
1. Сіз Teams жүйесінде **Бағдарламалар** аймағына қайта бағытталдыңыз. Сондай-ақ Teams жүйесін ашып, астыңғы сол жақ бұрышта **Бағдарламалар** опциясын таңдауға немесе [оны AppSource](https://go.microsoft.com/fwlink/?linkid=2124104) жүйесінен алуға болады.
1. **Customer Insights** іздеп, бағдарламаны таңдаңыз.
1. **Қосу** параметрін таңдаңыз.
1. Teams ішіндегі Customer Insights жүйесіне кіріңіз. Сәлемдесу хабары көрсетіледі.

## <a name="things-you-can-do-with-the-bot"></a>Ботпен жасауға болатын әрекеттер

Бот бірыңғай тұтынушы профильдері үшін іздеу мүмкіндіктерін қамтамасыз етеді.

- Енгізіңіз **іздеу** содан кейін іздеу және сүзгі индексіне қосылған бірыңғай тұтынушы профиліндегі атау, электрондық пошта мекенжайы немесе кез келген басқа өріс.

  Нәтижелік тұтынушы профилінен 15-ке дейінгі өрістері бар карта аласыз. Бірнеше сәйкестіктер профильді таңдау аймағында нәтижелер тізімін қайтарады. Дәл сәйкестікті іздеу үшін іздеу сөзін қос тырнақшаға қосыңыз.

- Ұйымыңыз бір ұйымда бірнеше Customer Insights ортасын қолдаса, енгізіңіз **коммутатор** ботқа қосылатын ортаны таңдау үшін.

- Бот үшін қолжетімді пәрмендер тізімін көру үшін **анықтаманы** енгізіңіз,  

[!INCLUDE [footer-include](includes/footer-banner.md)]