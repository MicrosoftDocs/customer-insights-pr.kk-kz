---
title: Үшінші тараптың арттыру HERE Technologies платформасымен арттыру
description: HERE Technologies үшінші тарап арттыруы туралы жалпы ақпарат.
ms.date: 12/10/2020
ms.reviewer: jodahl
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 258e37de9d9685d9ebc30b3c6b8d238d583431b4
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269521"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a>Тұтынушы профильдерін HERE Technologies көмегімен арттыру (алдын ала қарау)

HERE Technologies — орынға бағытталған деректер мен қызметтерді ұсынатын, орынды анықтауға арналған платформа компаниясы. HERE Technologies деректерді арттыру қызметтерінің көмегімен өз мекенжайыңызды қалыпқа келтіру, ендік пен бойлықты алу және тағы басқалар арқылы тұтынушыларыңыздың орналасуын дәлірек анықтай аласыз.

## <a name="prerequisites"></a>Алғышарттар

HERE Technologies арттыруларын конфигурациялау үшін келесі алғышарттар орындалуы керек:

- Сізде белсенді HERE Technologies жазылымы болуы қажет. Жазылым алу үшін [осы жерде тіркелуге](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) немесе тікелей [HERE Technologies компаниясына хабарласуға](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) болады. [HERE Technologies орынды арттыру туралы қосымша ақпарат.](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- Сізде HERE Technologies API кілті бар.

- Сізде [әкімші](permissions.md#administrator) рұқсаттары бар.

## <a name="configuration"></a>Теңшелім

1. **Деректер** > **Толықтыру** тармағына өтіңіз.

1. HERE Technologies тақтасында **Менің деректерімді арттыру** пәрменін таңдаңыз.

   > [!div class="mx-imgBorder"]
   > ![HERE Technologies тақтасы](media/HERE-tile.png "HERE Technologies тақтасы")

1. Белсенді **HERE Technologies API кілтін** енгізіңіз. **Келісемін** құсбелгісін таңдау арқылы **Деректер құпиялығы мен сәйкестігі** келісімін қарап шығыңыз және қамтамасыз етіңіз. 

1. **HERE платформасына қосылу** таңдау арқылы екі кірісті де растаңыз.

1.  **Деректерді қосу** опциясын таңдап, HERE Technologies жүйесіндегі орын деректерімен арттыру қажет **Тұтынушы деректерінің жиынтығын** таңдаңыз. Барлық тұтынушы профильдерін арттыру үшін **Тұтынушы** нысанын таңдауға болады немесе сол сегменттегі тек тұтынушы профильдерін арттыру үшін сегмент нысанын таңдауға болады.

    :::image type="content" source="media/enrichment-HERE-configuration-customer-data-set.png" alt-text="Тұтынушының деректер жиынтығын таңдау кезіндегі скриншот.":::

1. Өрістерді негізгі және/немесе қосымша мекенжаймен салыстырғыңыз келетінін таңдаңыз. Екі мекенжай үшін өріс салыстырмасын көрсетуге (мысалы, үй және бизнес мекенжайы) және екі мекенжайдың профильдерін бөлек арттыруға аласыз. **Келесі** пәрменін таңдаңыз.

1. HERE Technologies платформасынан тиісті орын деректерін іздеу үшін бірыңғай профильдердің қай өрістерін пайдалану керектігін анықтаңыз. **1-көше** және **Пошта индексі** өрістері таңдалған негізгі және/немесе қосымша мекенжай үшін қажет. Сәйкестіктің жоғары дәлдігі үшін қосымша өрістер қосуға болады.

   > [!div class="mx-imgBorder"]
   > ![HERE Technologies арттыру конфигурациясының беті](media/enrichment-HERE-configuration.png "HERE Technologies арттыру конфигурациясының беті")

1. Өрісті салыстыруды аяқтау үшін **Қолдану** пәрменін таңдаңыз.

## <a name="enrichment-results"></a>Толықтыру нәтижелері

Арттыру процесін бастау үшін пәрмендер жолағынан **Іске қосу** пәрменін таңдаңыз. Сондай-ақ, жүйеге [жоспарланған жаңарту](system.md#schedule-tab) бөлігі ретінде арттыруды автоматты түрде іске қосуына мүмкіндік беруге болады. Өңдеу уақыты тұтынушы деректерінің көлеміне және HERE Technologies платформасындағы API жауап беру уақытына байланысты болады.

Арттыру процесі аяқталғаннан кейін, жаңа арттырылған тұтынушы профильдерінің деректерін **Менің арттыруларым** астынан қарап шығуға болады. Сонымен қатар, соңғы жаңартудың уақыты мен арттырылған профильдер санын таба аласыз.

**Толықтырылған деректерді көру** параметрін таңдау арқылы әрбір толықтырылған профильдің толық көрінісіне қатынаса аласыз.

## <a name="next-steps"></a>Келесі қадамдар

Толықтырылған тұтынушы деректерінің негізінде жасаңыз. Тұтынушыларға жекелендірілген тәжірибелерді жеткізу үшін [сегменттер](segments.md), [шаралар](measures.md) жасаңыз және [деректерді экспорттаңыз](export-destinations.md).

## <a name="data-privacy-and-compliance"></a>Деректердің құпиялылығы мен сәйкестігі

Деректерді HERE Technologies платформасына жіберу үшін Dynamics 365 Customer Insights бағдарламасын қосқан кезде, Dynamics 365 Customer Insights талаптарына сәйкестік шекарасынан тыс деректерді, соның ішінде жеке деректер сияқты ықтимал құпия деректерді беруге мүмкіндік бересіз. Microsoft мұндай деректерді сіздің нұсқауыңыз бойынша тасымалдайды, бірақ HERE Technologies платформасының кез келген құпиялылық немесе қауіпсіздік міндеттемелеріне сәйкес келуіне жауап бересіз. Қосымша ақпаратты [Microsoft құпиялық туралы мәлімдемесі](https://go.microsoft.com/fwlink/?linkid=396732) бөлімінен қараңыз.
Бұл функцияны тоқтату үшін бұл арттыруды кез келген уақытта Dynamics 365 Customer Insights әкімшісі жоя алады.


[!INCLUDE[footer-include](../includes/footer-banner.md)]