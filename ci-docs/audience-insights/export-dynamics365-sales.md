---
title: Customer Insights деректерін Dynamics 365 Sales бағдарламасына экспорттау
description: Dynamics 365 Sales жүйесіне қосылымды конфигурациялау жолы.
ms.date: 02/01/2021
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 0013c4e6a96401d6cdbea55ed38f85f5e10dcc56
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269015"
---
# <a name="connector-for-dynamics-365-sales-preview"></a>Dynamics 365 Sales қосқышы (алдын ала қарау)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Тұтынушы деректерін Dynamics 365 Sales көмегімен маркетинг тізімдерін жасау, жұмыс ағындарын қадағалау және жарнамалар жіберу үшін пайдаланыңыз.

## <a name="prerequisite"></a>Алғышарт

1. Сегментті Customer Insights қызметінен сатылымға экспорттау алдында Dynamics 365 Sales жүйесінде контакт жазбалары болуы тиіс. [Dynamics 365 Sales жүйесінде Common Data Services](connect-power-query.md) арқылы контактілерді қабылдау жолдары туралы толығырақ оқыңыз.

   > [!NOTE]
   > Сегменттерді аудитория туралы түсініктерден сатылымға экспорттау сатылым даналарында жаңа контакт жазбаларын жасамайды. Сатылымдағы контакт жазбалары аудитория туралы түсінікке қабылданып, деректер көзі ретінде пайдаланылуы тиіс. Сондай-ақ, оларды сегменттер экспортталмас бұрын тұтынушы идентификаторларын контакт идентификаторларымен салыстыру үшін бірыңғай тұтынушы нысанына қосу қажет.

## <a name="configure-the-connector-for-sales"></a>Sales қызметіне арналған қосқышты конфигурациялау

1. Аудитория мәліметтерінде **Әкімші** > **Экспорттау мақсаттары** тармағына өтіңіз.

1. **Dynamics 365 Sales** бөлімінде **Орнату** опциясын таңдаңыз.

1. **Көрсетілетін атауы** өрісінде экспорттық межелі орынға танылатын атау беріңіз.

1. **Сервер мекенжайы** өрісінде ұйымның Sales URL мекенжайын енгізіңіз.

1. **Сервер әкімшісі тіркелгісі** бөлімінде **Жүйеге кіру** опциясын таңдап, Dynamics 365 Sales тіркелгісін таңдаңыз.

1. Тұтынушы идентификаторы өрісін Dynamics 365 контакт идентификаторына салыңыз.

1. **Келесі** пәрменін таңдаңыз.

1. Бір немесе бірнеше сегментті таңдаңыз.

1. **Сақтау** опциясын таңдаңыз.

## <a name="export-the-data"></a>Деректерді экспорттау

[Сұрау бойынша деректерді экспорттауға](export-destinations.md) болады. Экспорттау сондай-ақ әрбір [жоспарланған жаңарту](system.md#schedule-tab) сайын іске қосылады.


[!INCLUDE[footer-include](../includes/footer-banner.md)]