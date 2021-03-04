---
title: Customer Insights деректерін Dynamics 365 Marketing бағдарламасына экспорттау
description: Dynamics 365 Marketing жүйесіне қосылымды конфигурациялау жолы.
ms.date: 02/01/2021
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: a06920b8ff25d7102ccd14ae68cf42fe91fa1ee6
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269061"
---
# <a name="connector-for-dynamics-365-marketing-preview"></a>Dynamics 365 Marketing қосқышы (алдын ала қарау)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

[Сегменттерді](segments.md) науқандар құру және Dynamics 365 Marketing арқылы тұтынушылардың белгілі бір топтарымен байланысу үшін пайдаланыңыз. Қосымша ақпаратты [Dynamics 365 Marketing бар Dynamics 365 Customer Insights сегменттерін пайдалану](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments) бөлімінен қараңыз

## <a name="prerequisite"></a>Алғышарт

- Сегментті Customer Insights қызметінен маркетингке экспорттау алдында Dynamics 365 Marketing жүйесінде контакт жазбалары болуы тиіс. [Dynamics 365 Marketing жүйесінде Common Data Services](connect-power-query.md) арқылы контактілерді қабылдау жолдары туралы толығырақ оқыңыз.

  > [!NOTE]
  > Сегменттерді аудитория туралы түсініктерден маркетингке экспорттау маркетинг даналарында жаңа контакт жазбаларын жасамайды. Маркетингтегі контакт жазбалары аудитория туралы түсінікке қабылданып, деректер көзі ретінде пайдаланылуы тиіс. Сондай-ақ, оларды сегменттер экспортталмас бұрын тұтынушы идентификаторларын контакт идентификаторларымен салыстыру үшін бірыңғай тұтынушы нысанына қосу қажет.

## <a name="configure-the-connector-for-marketing"></a>Marketing қызметіне арналған қосқышты конфигурациялау

1. Аудитория мәліметтерінде **Әкімші** > **Экспорттау мақсаттары** тармағына өтіңіз.

1. **Dynamics 365 Marketing** бөлімінде **Орнату** опциясын таңдаңыз.

1. **Көрсетілетін атауы** өрісінде экспорттық межелі орынға танылатын атау беріңіз.

1. **Сервер мекенжайы** өрісінде ұйымның Marketing URL мекенжайын енгізіңіз.

1. **Сервер әкімшісі тіркелгісі** бөлімінде **Жүйеге кіру** опциясын таңдап, Dynamics 365 Marketing тіркелгісін таңдаңыз.

1. Тұтынушы идентификаторы өрісін Dynamics 365 контакт идентификаторына салыңыз.

1. **Келесі** пәрменін таңдаңыз.

1. Бір немесе бірнеше сегментті таңдаңыз.

1. **Сақтау** опциясын таңдаңыз.

## <a name="export-the-data"></a>Деректерді экспорттау

[Сұрау бойынша деректерді экспорттауға](export-destinations.md) болады. Экспорттау сондай-ақ әрбір [жоспарланған жаңарту](system.md#schedule-tab) сайын іске қосылады.


[!INCLUDE[footer-include](../includes/footer-banner.md)]