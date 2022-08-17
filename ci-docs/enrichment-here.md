---
title: Тұтынушы профильдерін HERE Technologies көмегімен байытыңыз (алдын ала қарау)
description: HERE Technologies үшінші тарап арттыруы туралы жалпы ақпарат.
ms.date: 08/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 86a070342193dd7afda38823d90f4bd28c8b862e
ms.sourcegitcommit: b1d06fe26934f12f0c5ed13e8ef1d37e52e67cc7
ms.translationtype: MT
ms.contentlocale: kk-KZ
ms.lasthandoff: 08/08/2022
ms.locfileid: "9237865"
---
# <a name="enrich-customer-profiles-with-here-technologies-preview"></a>Тұтынушы профильдерін HERE Technologies көмегімен байытыңыз (алдын ала қарау)

HERE Technologies — орынға бағытталған деректер мен қызметтерді ұсынатын, орынды анықтауға арналған платформа компаниясы. HERE Technologies деректерін байыту қызметтері тұтынушыларыңыз туралы орын ақпаратының дәлдігін жақсартады. Ол мекенжайды қалыпқа келтіруді, ендік пен бойлықты алуды және т.б. қамтамасыз етеді.

## <a name="prerequisites"></a>Алғышарттар

- Белсенді HERE Technologies жазылымы. Жазылым алу үшін, [осында тіркеліңіз](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) немесе [HERE Technologies компаниясына хабарласыңыз](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) тікелей. [HERE Technologies орынды арттыру туралы қосымша ақпарат.](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- А МЫНДА [байланыс](connections.md) болып табылады [конфигурацияланған](#configure-the-connection-for-here-technologies) әкімші арқылы.

## <a name="configure-the-connection-for-here-technologies"></a>HERE Technologies үшін қосылымды конфигурациялау

Сіз болуыңыз керек [әкімші](permissions.md#admin) Customer Insights жүйесінде және белсенді HERE Technologies API кілті бар.

1. таңдаңыз **Қосылым қосыңыз** байытуды конфигурациялағанда немесе өтіңіз **Админ** > **Қосылымдар** және таңдаңыз **Орнату** HERE Technologies тақтасында.

1. Қосылым атауын және жарамды HERE Technologies API кілтін енгізіңіз.

1. шолу [деректердің құпиялылығы және сәйкестігі](connections.md#data-privacy-and-compliance) және таңдаңыз **Мен келісемін**.

1. таңдаңыз **Тексеру** конфигурацияны растау үшін, содан кейін таңдаңыз **Сақтау**.

   :::image type="content" source="media/enrichment-HERE-connection.png" alt-text="HERE Technologies қосылымын конфигурациялау беті.":::

## <a name="configure-the-enrichment"></a>Жақсартуды конфигурациялау

1. **Деректер** > **Арттыру** тармағына өтіп, **Анықтау** қойыншасын таңдаңыз.

1. таңдаңыз **Менің деректерімді байыту** үстінде **Орналасқан жері** HERE Technologies тақтасынан.

   :::image type="content" source="media/HERE-tile.png" alt-text="HERE Technologies тақтасы.":::

1. Шолуды қарап шығыңыз, содан кейін таңдаңыз **Келесі**.

1. Қосылымды таңдаңыз. Егер қосылым болмаса, әкімшіге хабарласыңыз.

1. **Келесі** пәрменін таңдаңыз.

1. таңдаңыз **Тұтынушы деректер жинағы** және HERE Technologies деректерімен байытқыңыз келетін профильді немесе сегментті таңдаңыз. The *Тұтынушы* нысан сіздің барлық тұтынушы профильдеріңізді байытады, ал сегмент сол сегменттегі тұтынушы профильдерін ғана байытады.

1. Біріктірілген профильдердегі өрістердің қай түрін сәйкестендіру үшін пайдаланылатынын анықтаңыз: негізгі және/немесе қосымша мекенжай. Сіз екі мекенжай үшін өріс картасын көрсете аласыз және екі мекенжайдың профильдерін бөлек жақсарта аласыз. Мысалы, үй мекенжайы және бизнес мекенжайы үшін. **Келесі** пәрменін таңдаңыз.

1. Өрістерді HERE Technologies деректерімен салыстырыңыз. **1-көше** және **Пошта индексі** өрістері таңдалған негізгі және/немесе қосымша мекенжай үшін қажет. Жоғарырақ сәйкестік дәлдігі үшін көбірек өрістерді қосыңыз.

1. Өрістерді салыстыруды аяқтау үшін **Келесі** түймешігін таңдаңыз.

1. А қамтамасыз етіңіз **Аты** байыту үшін және **Шығару нысанының атауы**.

1. Таңдауларды қарап шыққаннан кейін **Жақсартуды сақтау** түймешігін таңдаңыз.

1. таңдаңыз **Жүгіру** байыту процесін бастау немесе қайта оралу үшін жақын **Байытулар** бет.

## <a name="view-enrichment-results"></a>Байыту нәтижелерін көру

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

The **Өріс бойынша байытылған тұтынушылар саны** әрбір байытылған өрістің қамтылуын егжей-тегжейлі қарастырады.

## <a name="next-steps"></a>Келесі қадамдар

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
