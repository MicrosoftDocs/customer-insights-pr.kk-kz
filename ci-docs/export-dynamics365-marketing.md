---
title: Dynamics 365 Marketing жүйесіне сегменттерді экспорттау (алдын ала қарау)
description: Dynamics 365 Marketing жүйесі үшін қосылымды конфигурациялау және экспорттау жолы туралы ақпарат.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
searchScope:
- ci-export
- customerInsights
ms.openlocfilehash: 123b565421a7d096e7341a8f600f91e59aefe8d0
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: kk-KZ
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196631"
---
# <a name="export-segments-to-dynamics-365-marketing-preview"></a>Dynamics 365 Marketing жүйесіне сегменттерді экспорттау (алдын ала қарау)

Қолдану [сегменттер](segments.md) науқандарды құру және тұтынушылардың белгілі топтарымен байланысу [Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments).

Dataverse ұйымында нақты уақыттағы тұтынушымен өзара қатынас топтамасын басқару үшін Dynamics 365 Marketing жаңа мүмкіндіктерін пайдаланатын болсаңыз, Dynamics 365 Marketing бағдарламасын стандартты экспортты жасау қажет емес. Customer Insights контактілері мен сегменттері Marketing және Customer Insights қосылғаннан кейін тікелей Dynamics 365 Marketing жүйесінде қолжетімді. Бар экспорттарды жою алдында құжаттаманы қараңыз [Customer Insights және Dynamics 365 Marketing тұтынушымен өзара қатынас топтамасы оркестрін қосу жолы](/dynamics365/marketing/real-time-marketing-ci-profile).

## <a name="prerequisite"></a>Алғышарт

Сегментті Customer Insights қызметінен маркетингке экспорттау алдында Dynamics 365 Marketing жүйесінде контакт жазбалары болуы тиіс. [Dynamics 365 Marketing жүйесінде Microsoft Dataverse](connect-dataverse-managed-lake.md) арқылы контактілерді қабылдау жолдары туралы толығырақ оқыңыз.

> [!NOTE]
> Customer Insights-тен маркетингке сегменттерді экспорттау Маркетинг даналарында жаңа контакт жазбаларын жасамайды. Маркетингтен контакт жазбалары Customer Insights жүйесіне енгізіліп, деректер көзі ретінде пайдаланылуы керек. Сондай-ақ оларды сегменттер экспортталмас бұрын тұтынушы идентификаторларын контакт идентификаторларымен салыстыру үшін бірыңғай тұтынушы нысанына қосу қажет.

## <a name="set-up-connection-to-marketing"></a>Маркетинг қызметіне қосылым орнату

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. **Әкімші** > **Қосылымдар** тармағына өтіңіз.

1. таңдаңыз **Қосылым қосыңыз** және таңдаңыз **Dynamics 365 Marketing**.

1. **Көрсетілетін аты** өрісінде қосылымға оңай танылатын атау енгізіңіз. Қосылым атауы мен түрі осы қосылымды сипаттайды. Қосылымның мақсатын түсіндіретін атауды таңдауды ұсынамыз.

1. Осы қосылымды кім пайдалана алатынын таңдаңыз. Әдепкі бойынша бұл тек әкімшілер. Қосымша ақпарат алу үшін [Салымшыларға экспорттау үшін қосылымды пайдалануға рұқсат беру](connections.md#allow-contributors-to-use-a-connection-for-exports) бөлімін қараңыз.

1. **Сервер мекенжайы** өрісінде ұйымның Marketing URL мекенжайын енгізіңіз.

1. **Сервер әкімшісі тіркелгісі** бөлімінде **Жүйеге кіру** опциясын таңдап, Dynamics 365 Marketing тіркелгісін таңдаңыз.

1. Тұтынушы нысанындағы Контакт идентификаторы өрісін Dynamics 365 контакт идентификаторымен салыстырыңыз.

1. шолу [деректердің құпиялылығы және сәйкестігі](connections.md#data-privacy-and-compliance) және таңдаңыз **Мен келісемін**.

1. Қосылымды аяқтау үшін **Сақтау** түймешігін таңдаңыз.

## <a name="configure-an-export"></a>Экспорттауды конфигурациялау

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. **Деректер** > **Экспорттау** тармағына өтіңіз.

1. таңдаңыз **Экспортты қосыңыз**.

1. **Экспорттауға арналған қосылым** өрісінде Dynamics 365 Marketing бөлімінен қосылым таңдаңыз. Егер қосылым болмаса, әкімшіге хабарласыңыз.

1. Экспорттау үшін атау енгізіңіз.

1. Dynamics 365 контакт идентификаторына сәйкес келетін Тұтынушы нысанындағы Контакт идентификаторы өрісін таңдаңыз.

1. Экспорттау керек сегменттерді таңдаңыз.

1. **Сақтау** пәрменін таңдаңыз.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
