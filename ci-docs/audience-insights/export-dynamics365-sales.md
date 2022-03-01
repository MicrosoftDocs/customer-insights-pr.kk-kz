---
title: Customer Insights деректерін Dynamics 365 Sales бағдарламасына экспорттау
description: Dynamics 365 Sales жүйесіне қосылымды конфигурациялау жолы.
ms.date: 08/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: af0824e69dfdf620a0ac756e32a9bd3dd85e5151
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643825"
---
# <a name="connector-for-dynamics-365-sales-preview"></a>Dynamics 365 Sales қосқышы (алдын ала қарау)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Тұтынушы деректерін Dynamics 365 Sales көмегімен маркетинг тізімдерін жасау, жұмыс ағындарын қадағалау және жарнамалар жіберу үшін пайдаланыңыз.

## <a name="prerequisite"></a>Алғышарт

[Common Data Service көмегімен қабылданған Dynamics 365 Sales бағдарламасынан алынған](connect-power-query.md) байланыс жазбалары.

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
