---
title: Salesforce Marketing Cloud қызметіне деректерді экспорттау (алдын ала қарау)
description: Salesforce Marketing Cloud қызметіне қосылымды және экспорттауды конфигурациялау жолы туралы ақпарат.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 58e76e51c18c25177f9b4551b70b25b41248b142
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: kk-KZ
ms.lasthandoff: 07/27/2022
ms.locfileid: "9197045"
---
# <a name="export-data-to-salesforce-marketing-cloud-preview"></a>Salesforce Marketing Cloud қызметіне деректерді экспорттау (алдын ала қарау)

Тұтынушылар туралы деректерді Salesforce Marketing Cloud қызметінде қауіпсіз файл тасымалдау протоколымен (SFTP) экспорттау арқылы пайдаланыңыз.

## <a name="prerequisites"></a>Алғышарттар

- Ан [Salesforce Marketing Cloud үшін SFTP хосты](https://help.salesforce.com/articleView?id=sf.mc_es_configure_enhanced_ftp.htm&type=5) және сәйкес әкімші тіркелгі деректері.

## <a name="set-up-connection-to-salesforce-marketing-cloud"></a>Salesforce Marketing Cloud қосылымын орнатыңыз

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. **Әкімші** > **Қосылымдар** тармағына өтіңіз.

1. таңдаңыз **Қосылым қосыңыз** және таңдаңыз **Salesforce маркетинг бұлты**.

1. **Көрсетілетін аты** өрісінде қосылымға оңай танылатын атау енгізіңіз. Қосылым атауы мен түрі осы қосылымды сипаттайды. Қосылымның мақсатын түсіндіретін атауды таңдауды ұсынамыз.

1. Осы қосылымды кім пайдалана алатынын таңдаңыз. Әдепкі бойынша бұл тек әкімшілер. Қосымша ақпарат алу үшін [Салымшыларға экспорттау үшін қосылымды пайдалануға рұқсат беру](connections.md#allow-contributors-to-use-a-connection-for-exports) бөлімін қараңыз.

1. SFTP тіркелгіңіз үшін **Пайдаланушы аты**, **Құпиясөз**, **Хост атауы** және **Экспорттау қалтасы** деректерін енгізіңіз.

1. Байланысты сынау үшін **Растау** параметрін таңдаңыз.

1. шолу [деректердің құпиялылығы және сәйкестігі](connections.md#data-privacy-and-compliance) және таңдаңыз **Мен келісемін**.

1. Қосылымды аяқтау үшін **Сақтау** түймешігін таңдаңыз.

## <a name="configure-an-export"></a>Экспорттауды конфигурациялау

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. **Деректер** > **Экспорттау** тармағына өтіңіз.

1. таңдаңыз **Экспортты қосыңыз**.

1. **Экспорттауға арналған қосылым** өрісінде SFTP бөлімінен қосылым таңдаңыз. Егер қосылым болмаса, әкімшіге хабарласыңыз.

1. Экспорттау үшін атау енгізіңіз.

1. Деректерді **Мұрағатталған** немесе **Мұрағаттан шығарылған** күйде экспорттауды және экспортталған файлдар үшін **өріс бөлгішін** таңдаңыз.

1. Экспорттағыңыз келетін нысандарды, мысалы сегменттерді таңдаңыз.

   > [!NOTE]
   > Әрбір таңдалған нысан экспортталған кезде ең көбі бес шығыс файлына бөлінеді.

1. **Сақтау** пәрменін таңдаңыз.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

## <a name="import-customer-insights-data-from-sftp-location-to-salesforce-marketing-cloud"></a>SFTP орнындағы Customer Insights деректерін Salesforce Marketing Cloud қызметіне импорттау

1. Customer Insights деректер файлын SFTP орнынан импорттау үшін [Salesforce Marketing Cloud қызметінде деректер кеңейтімдерін](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5) жасаңыз.

2. [SFTP орнындағы деректерді](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5) Salesforce Marketing Cloud деректер кеңейтіміне импорттаңыз.

3. Деректерді деректер кеңейтіміне импорттау үшін автоматтандыруды орнатыңыз. [Файлды сүйреуді автоматтандырулар мен жоспарланған автоматтандырулар](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5) туралы қосымша ақпарат.

   [Файлды сүйреуді автоматтандыруды](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5) немесе  [жоспарланған автоматтандыруды](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5) анықтаңыз.

Мына жерде [SFTP протоколымен автоматтандыру](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5) мысалы келтірілген.

[!INCLUDE [footer-include](includes/footer-banner.md)]
