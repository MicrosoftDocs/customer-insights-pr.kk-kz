---
title: Экспорттау мақсаттары
description: Деректерді экспорттап, экспорттау мақсаттарын басқарыңыз.
ms.date: 07/21/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 5557442983f8c48cd46387009e0060beb6e764bb
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596092"
---
# <a name="export-destinations-preview-overview"></a>Экспорттау мақсаттарына (алдын ала қарау нұсқасы) шолу

**Экспорттық межелі орындар** беті деректерді экспорттау үшін орнатылған барлық орындарды көрсетеді. Сонымен қатар жаңа экспорттау межелі орындарын қосуға болады. Сонымен қатар ол экспорттаудың ағымдағы уақытта қолжетімді нұсқаларын көрсетеді. Жылдам шолу, сипаттама алып, нақты кеңейтім опциясымен істеуге болатын істі табыңыз. Бизнесіңізге қатысты қолдау көрсетілетін бағдарламаларға бірыңғай профильдерді, өлшеулерді және сегменттерді экспорттаңыз.

Мына кеңейтім опцияларын табу үшін **Әкімші** > **Экспорт межелі орындары** тармағына өтіңіз:

- [Adobe Campaign Standard](export-adobe-campaign-standard.md)
- [Adobe Experience платформасы](export-adobe-experience-platform.md)
- [AdRoll](export-adroll.md)
- [Autopilot](export-autopilot.md)
- [Azure Blob сақтау орны](export-azure-blob-storage.md)
- [Azure Data Lake Storage Gen2](export-azure-data-lake-storage-gen2.md)
- [Microsoft Teams арналған бот](export-teams-bot.md)
- [Customer Insights API](apis.md)
- [DotDigital](export-dotdigital.md)
- [Dynamics 365 Customer Service (Тұтынушы картасының қондырмасы)](customer-card-add-in.md)
- [Dynamics 365 Marketing](export-dynamics365-marketing.md)
- [Dynamics 365 Sales](export-dynamics365-sales.md)
- [Dynamics 365 сату орталығы (Тұтынушы картасының қондырмасы)](customer-card-add-in.md)
- [Facebook жарнамалары жөніндегі менеджер](export-facebook.md)
- [Google Ads](export-google-ads.md)
- [LiveRamp&reg;](export-liveramp.md)
- [Mailchimp](export-mailchimp.md)
- [Marketo](export-marketo.md)
- [Power Automate](export-power-automate.md)
- [Power Apps](export-power-apps.md)
- [Power BI](export-power-bi.md)
- [SendGrid](export-sendgrid.md)
- [SFTP](export-sftp.md)

## <a name="add-a-new-export-destination"></a>Жаңа экспорттық межелі орынды қосу

Экспорттау мақсаттарын қосу үшін сізде [әкімші рұқсаттары](permissions.md) бар. Microsoft қызметтерін экспорттайтын болсаңыз, екі қызмет те бір ұйымда екендігі болжанады.

1. **Әкімші** > **Экспорттық межелі орындар** тармағына өтіңіз.

1. **Менің экспорттық межелі орындарым** қойыншасына ауысыңыз.

1. Жаңа экспорттық межелі орынды жасау үшін **Межелі орынды қосу** параметрін таңдаңыз.

1. **Межелі орынды қосу** бөлігінде ашылмалы мәзірде экспорттық межелі орын **Түрін** таңдаңыз.

1. Қажетті мәліметтерді енгізіп, экспорттық межелі орынды жасау үшін **Келесі** түймешігін таңдаңыз.

**Анықтау** қойыншасындағы қатардағы **Орнату** параметрін таңдауға болады,

## <a name="view-export-destinations"></a>Межелі орындарды қарау

Экспорттық межелі орындарды жасағаннан кейін оларды **Менің экспорттық межелі орындарым** қойыншасындағы кестеде көресіз. Бұл кестеле үш баған бар:

- **Көрсетілетін атау**: Межелі орынды жасау кезінде сіз енгізген атау.
- **Түрі**: Межелі орынды жасау кезіндегі орнатылған экспорттық межелі орын түрі.
- **Жасалды** : Межелі орынды жасаған күн.

## <a name="edit-an-export-destination"></a>Экспорттық межелі орынды өңдеу

1. Өңдеу қажет экспорттық межелі орынға арналған тік көп нүктені таңдаңыз.

   > [!div class="mx-imgBorder"]
   > ![Тік эллипс](media/export-destinations-page-ellipsis.png "Тік эллипс")

1. Ашылмалы мәзірден **Өңдеу** түймешігін таңдаңыз.

1. Жаңартуды қажет ететін мәндерді өзгертіп, **Сақтау** түймешігін таңдаңыз.

## <a name="export-data-on-demand"></a>Сұрау бойынша деректерді экспорттау

Экспорттық межелі орын қосқышын конфигурациялағаннан кейін экспорттар әрбір [жоспарланған жаңарту](system.md#schedule-tab) сайын іске қосылады.

Деректерді жоспарланған жаңартуды күтпей экспорттау үшін **Әкімші** > **Экспорттық межелі орындар** тармағындағы **Менің экспорттық межелі орындарым** қойыншасына өтіңіз.

> [!div class="mx-imgBorder"]
> ![Тік эллипс](media/export-destinations-page-ellipsis.png "Тік эллипс")

- Экспортты барлық экспорттық межелі орындарға бір уақытта іске қосу үшін тізімнің жоғарғы жағындағы **Экспорттау** опциясын таңдаңыз.
- Тізім элементінен кейінгі көп нүктені (…) таңдап, содан соң бір экспорттық межелі орын үшін экспортты іске қосу үшін **Экспорттау** опциясын таңдаңыз.

## <a name="remove-an-export-destination"></a>«Экспорттау» межелі орнын алып тастау

«Экспорттау» межелі орнын алып тастау үшін басты **Экспортталатын межелі орындар** бетінен бастаңыз.

1. Алып тастау қажет «Экспорттау» межелі орнына арналған тік эллипсті таңдаңыз.

   > [!div class="mx-imgBorder"]
   > ![Тік эллипс](media/export-destinations-page-ellipsis.png "Тік эллипс")

2. Ашылмалы тізімнен **Алып тастау** опциясын таңдаңыз.

3. Растау экранында **Жою** опциясын таңдау арқылы жоюды растаңыз.


[!INCLUDE[footer-include](../includes/footer-banner.md)]