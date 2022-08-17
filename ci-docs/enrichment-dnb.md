---
title: Dun & Bradstreet көмегімен компания профилін байыту (алдын ала қарау)
description: Dun & Bradstreet үшінші тараптың байытылуы туралы жалпы ақпарат.
ms.date: 08/08/2022
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: e89b64774dcb519a071dd3d403473807a50e7f33
ms.sourcegitcommit: b1d06fe26934f12f0c5ed13e8ef1d37e52e67cc7
ms.translationtype: MT
ms.contentlocale: kk-KZ
ms.lasthandoff: 08/08/2022
ms.locfileid: "9237911"
---
# <a name="enrich-company-profiles-with-dun--bradstreet-preview"></a>Dun & Bradstreet көмегімен компания профилін байыту (алдын ала қарау)

Dun & Bradstreet коммерциялық деректер, аналитика және бизнеске арналған түсініктерді ұсынады. Ол компанияларға арналған бірыңғай тұтынушы профильдері бар тұтынушыларға деректерін толықтыруына мүмкіндік береді. Байытуларға DUNS нөмірі, компания өлшемі, орналасқан жері, сала және т.б. сияқты атрибуттар кіреді.

## <a name="prerequisites"></a>Алғышарттар

- Белсенді [Дан және Брэдстрит](https://www.dnb.com/marketing/media/give-your-data-a-boost.html?source=microsoft_audience_insights) лицензия.
- [Бірыңғай тұтынушы профильдері](customer-profiles.md) компаниялар үшін.
- Дан және Брэдстрит [жоба](#set-up-your-dun--bradstreet-project) орнатылған.
- Дан және Брэдстрит [байланыс](connections.md) болып табылады [конфигурацияланған](#configure-a-connection-for-dun--bradstreet) әкімші арқылы.

## <a name="set-up-your-dun--bradstreet-project"></a>Dun & Bradstreet жобасын орнатыңыз

Dun & Bradstreet лицензиясы бар пайдаланушы ретінде жобаны орнатуға болады [Dun & Bradstreet Connect](https://connect.dnb.com?lead_source=microsoft_audienceinsights).

1. кіру [Dun & Bradstreet Connect](https://connect.dnb.com?lead_source=microsoft_audienceinsights). Тіркелгі деректерін алу үшін, [құпия сөзіңізді қалпына келтіріңіз](https://sso.dnb.com/signin/forgot-password?lead_source=microsoft_audienceinsights).

1. Жүктеп алу [біздің csv үлгі файлымыз](https://c360devenrichment.blob.core.windows.net/mapping/DnBCIdatamapping.csv) ол Customer Insights өрістерін сәйкес Dun және Bradstreet өрістеріне салыстыру үшін пайдаланылады.

1. файлды жүктеп салыңыз **Деректерді жүктеп салу** Dun & Bradstreet жобасын жасау тәжірибесінің қадамы.

1. Сәйкес астындағы көлденең нүктелерді таңдаңыз **көзі** қол жетімді опцияларды көру үшін жаңадан жасалған Dun & Bradstreet жобасында.

   :::image type="content" source="media/enrichment-dnb-dots.png" alt-text="Dun & Bradstreet жобасындағы нүктелердің скриншоты.":::

1. Таңдау **S3 мәліметтерін алыңыз**. Бұл ақпаратты қауіпсіз жерде сақтаңыз. Сізге қажет болады [байыту үшін қосылымды орнатыңыз](#configure-a-connection-for-dun--bradstreet) Customer Insights ішінде.

   :::image type="content" source="media/enrichment-dnb-s3info.png" alt-text="Dun & Bradstreet жобасындағы s3 ақпаратын таңдаудың скриншоты.":::

## <a name="configure-a-connection-for-dun--bradstreet"></a>Dun & Bradstreet үшін қосылымды теңшеңіз

Сіз болуыңыз керек [әкімші](permissions.md#admin) Customer Insights жүйесінде және Dun & Bradstreet Connect тіркелгі деректеріне ие болыңыз.

1. таңдаңыз **Қосылым қосыңыз** байытуды конфигурациялағанда немесе өтіңіз **Админ** > **Қосылымдар** және таңдаңыз **Орнату** Dun & Bradstreet тақтайшасында.

1. Қосылым үшін атау енгізіңіз.

1. Жарамды Dun & Bradstreet тіркелгі деректерін және Dun & Bradstreet жобасының мәліметтерін беріңіз *Аймақ, Қалтаны тастау жолы және Қалтаның атауы*. Сіз [бұл ақпаратты алыңыз](#set-up-your-dun--bradstreet-project) Dun & Bradstreet жобасынан.

1. шолу [деректердің құпиялылығы және сәйкестігі](connections.md#data-privacy-and-compliance) және таңдаңыз **Мен келісемін**.

1. таңдаңыз **Тексеру** конфигурацияны растау үшін, содан кейін таңдаңыз **Сақтау**.

   :::image type="content" source="media/enrichment-dnb-connection.png" alt-text="Dun & Bradstreet қосылымының конфигурация беті.":::

## <a name="supported-countries-or-regions"></a>Қолдау көрсетілетін елдер немесе аймақтар

Қазіргі уақытта біз келесі ел/аймақ опцияларын қолдаймыз: Канада (ағылшын тілі) немесе Америка Құрама Штаттары (ағылшын тілі).

## <a name="configure-the-enrichment"></a>Жақсартуды конфигурациялау

1. **Деректер** > **Арттыру** тармағына өтіп, **Анықтау** қойыншасын таңдаңыз.

1. таңдаңыз **Менің деректерімді байыту** үстінде **Компания деректері** Dun & Bradstreet плиткасы үшін.

   :::image type="content" source="media/enrichment-dnb-tile.png" alt-text="Dun & Bradstreet тақтасының скриншоты.":::

1. Шолуды қарап шығыңыз, содан кейін таңдаңыз **Келесі**.

1. Қосылымды таңдап, растаңыз. Егер қосылым болмаса, әкімшіге хабарласыңыз.

1. **Келесі** пәрменін таңдаңыз.

1. таңдаңыз **Тұтынушы деректер жинағы** және Dun & Bradstreet компаниясының деректерімен байытқыңыз келетін профильді немесе сегментті таңдаңыз. The *Тұтынушы* нысан сіздің барлық тұтынушы профильдеріңізді байытады, ал сегмент сол сегменттегі тұтынушы профильдерін ғана байытады.

1. Dun & Bradstreet компаниясының деректерін сәйкестендіру үшін пайдаланылатын бірыңғай профильдердегі өрістердің қай түрін анықтаңыз. **Атауы және мекен-жайы**, **Телефон** немесе **Электрондық пошта** өрістерінің кем дегенде біреуі қажет.

1. **Келесі** опциясын таңдаңыз

1. Өрістерді Dun & Bradstreet компаниясының деректерімен салыстырыңыз. Немесе **DUNS нөмірі** немесе **Компанияның атауы** және **Ел** өрістер қажет.

      :::image type="content" source="media/enrichment-dnb-mapping.png" alt-text="Dun & Bradstreet өрісті салыстыру тақтасы.":::

1. Өрістерді салыстыруды аяқтау үшін **Келесі** түймешігін таңдаңыз.

1. А қамтамасыз етіңіз **Аты** байыту үшін және **Шығару нысанының атауы**.

1. Таңдауларды қарап шыққаннан кейін **Жақсартуды сақтау** түймешігін таңдаңыз.

1. таңдаңыз **Жүгіру** байыту процесін бастау немесе қайта оралу үшін жақын **Байытулар** бет.

## <a name="view-enrichment-results"></a>Байыту нәтижелерін көру

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

## <a name="next-steps"></a>Келесі қадамдар

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE[footer-include](includes/footer-banner.md)]
