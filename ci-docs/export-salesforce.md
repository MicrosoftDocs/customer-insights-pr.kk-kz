---
title: Salesforce Marketing Cloud қызметіне деректерді экспорттау (алдын ала қарау)
description: Salesforce Marketing Cloud қызметіне қосылымды және экспорттауды конфигурациялау жолы туралы ақпарат.
ms.date: 07/23/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c3a6a40d9b9f08c8ebca8cb4a9196a1a79f03afa
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: kk-KZ
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082619"
---
# <a name="export-data-to-salesforce-marketing-cloud-preview"></a>Salesforce Marketing Cloud қызметіне деректерді экспорттау (алдын ала қарау)

Тұтынушылар туралы деректерді Salesforce Marketing Cloud қызметінде қауіпсіз файл тасымалдау протоколымен (SFTP) экспорттау арқылы пайдаланыңыз.

## <a name="prerequisites-for-connection"></a>Қосылым алғышарттары

- SFTP хостының және тиісті әкімші деректерінің қолжетімділігі. [Salesforce Marketing Cloud қызметі үшін SFTP орындарын орнату жолы](https://help.salesforce.com/articleView?id=sf.mc_es_configure_enhanced_ftp.htm&type=5) 

## <a name="set-up-the-connection-to-salesforce-marketing-cloud"></a>Salesforce Marketing Cloud қызметіне қосылым орнату

1. **Әкімші** > **Қосылымдар** тармағына өтіңіз.

1. **Қосылым қосу** түймешігін таңдаңыз және қосылымды конфигурациялау үшін **Salesforce Marketing Cloud** қызметін таңдаңыз.

1. **Көрсетілетін аты** өрісінде қосылымға оңай танылатын атау енгізіңіз. Қосылым атауы мен түрі осы қосылымды сипаттайды. Қосылымның мақсатын түсіндіретін атауды таңдауды ұсынамыз.

1. Осы қосылымды кім пайдалана алатынын таңдаңыз. Егер сіз ешқандай әрекет жасамасаңыз, әдепкі бойынша Әкімшілер болады. Қосымша ақпарат алу үшін [Салымшыларға экспорттау үшін қосылымды пайдалануға рұқсат беру](connections.md#allow-contributors-to-use-a-connection-for-exports) бөлімін қараңыз.

1. SFTP тіркелгіңіз үшін **Пайдаланушы аты**, **Құпиясөз**, **Хост атауы** және **Экспорттау қалтасы** деректерін енгізіңіз.

1. Байланысты сынау үшін **Растау** параметрін таңдаңыз.

1. **Деректер құпиялығы мен сәйкестігін** растау үшін **Мен келісемін** параметрін таңдаңыз.

1. Қосылымды аяқтау үшін **Сақтау** түймешігін таңдаңыз.

## <a name="configure-an-export"></a>Экспорттауды конфигурациялау

Егер сіз осы түрдегі қосылымға қатынаса алсаңыз, сіз бұл экспорттауды конфигурациялай аласыз. Қосымша ақпарат алу үшін [Экспорттауды конфигурациялау үшін қажет рұқсаттар](export-destinations.md#set-up-a-new-export) бөлімін қараңыз.

1. **Деректер** > **Экспорттау** тармағына өтіңіз.

1. Жаңа экспорттау жасау үшін **Мақсатты орын қосу** түймешігін таңдаңыз.

1. **Экспорттауға арналған қосылым** өрісінде SFTP бөлімінен қосылым таңдаңыз. Егер сіз осы бөлімнің атын көрмесеңіз, сізге қолжетімді осы түрдегі қосылым жоқ.

1. Деректерді **Мұрағатталған** немесе **Мұрағаттан шығарылған** күйде экспорттауды және экспортталған файлдар үшін **өріс бөлгішін** таңдаңыз.

1. Экспортталатын нысандарды таңдаңыз, мысалы, сегменттер.

   > [!NOTE]
   > Әрбір таңдалған нысан экспортталған кезде бес шығыс файлға бөлінеді. 

1. **Сақтау** опциясын таңдаңыз.

Экспорттауды сақтау экспорттауды бірден іске қоспайды.

Экспорттау әр [жоспарланған жаңартумен](system.md#schedule-tab) іске қосылады. Сондай-ақ [деректерді сұрау бойынша экспорттауға](export-destinations.md#run-exports-on-demand) болады. 

## <a name="import-customer-insights-data-from-sftp-location-to-salesforce-marketing-cloud"></a>SFTP орнындағы Customer Insights деректерін Salesforce Marketing Cloud қызметіне импорттау

1. Customer Insights деректер файлын SFTP орнынан импорттау үшін [Salesforce Marketing Cloud қызметінде деректер кеңейтімдерін](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5) жасаңыз.

2. [SFTP орнындағы деректерді](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5) Salesforce Marketing Cloud деректер кеңейтіміне импорттаңыз. 

3. Деректерді деректер кеңейтіміне импорттау үшін автоматтандыруды орнатыңыз. [Файлды сүйреуді автоматтандырулар мен жоспарланған автоматтандырулар](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5) туралы қосымша ақпарат.

   [Файлды сүйреуді автоматтандыруды](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5) немесе  [жоспарланған автоматтандыруды](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5) анықтаңыз. 

Мына жерде [SFTP протоколымен автоматтандыру](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5) мысалы келтірілген.

## <a name="data-privacy-and-compliance"></a>Деректердің құпиялылығы мен сәйкестігі

Деректерді SFTP арқылы жіберу үшін Dynamics 365 Customer Insights бағдарламасын қосқан кезде, Dynamics 365 Customer Insights талаптарына сәйкестік шекарасынан тыс деректерді, соның ішінде жеке деректер сияқты ықтимал құпия деректерді беруге мүмкіндік бересіз. Microsoft мұндай деректерді сіздің нұсқауыңыз бойынша тасымалдайды, бірақ экспортталатын орынның кез келген құпиялылық немесе қауіпсіздік міндеттемелеріне сәйкес келуіне жауап бересіз. Қосымша ақпаратты [Microsoft құпиялық туралы мәлімдемесі](https://go.microsoft.com/fwlink/?linkid=396732) бөлімінен қараңыз.
Бұл функцияны тоқтату үшін бұл экспорттау мақсатын кез келген уақытта Dynamics 365 Customer Insights әкімшісі жоя алады.

[!INCLUDE [footer-include](includes/footer-banner.md)]
