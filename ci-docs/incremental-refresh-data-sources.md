---
title: үшін қосымша жаңарту Power Query - деректер көздеріне негізделген
description: негізіндегі үлкен деректер көздері үшін жаңа және жаңартылған деректерді жаңарту Power Query.
ms.date: 12/06/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
searchScope:
- ci-system-schedule
- customerInsights
ms.openlocfilehash: 3d21baf9804f300802b066df0183fc8f01abba9a
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: kk-KZ
ms.lasthandoff: 04/27/2022
ms.locfileid: "8643670"
---
# <a name="incremental-refresh-for-data-sources-based-on-power-query"></a>Деректер көздеріне арналған қосымша жаңарту Power Query

Бұл мақала негізінде деректер көздері үшін қосымша жаңартуды теңшеу жолы талқыланады Power Query.

Деректер көздерін біртіндеп жаңарту келесі артықшылықтарға ие:

- **Жылдамырақ жаңартулар** - Тек өзгертілген деректер жаңартылады. Мысалы, тарихи деректер жинағын тек өткен бес күн жаңарта алуыңыз мүмкін.
- **Арттырылған сенімділік** - Кішкентайырақ жаңартулар көмегімен байланыс мәселелері қаупін азайта отырып, тұрақсыз көз жүйелерінің байланыстарын барынша ұзақ сақтау керек болмайды.
- **Қысқартылған ресурс тұтынысы** - Жалпы деректердің қосалқы жинағын ғана жаңарту есептеу ресурстарын тиімдірек пайдалануға әкеледі және орта тұтынысын қысқартады.

## <a name="configure-incremental-refresh"></a>Кезеңдік жаңартуды теңшеу

Customer Insights арқылы импортталған деректер көздері үшін қосымша жаңартуға мүмкіндік береді Power Query бұл қосымша қабылдауды қолдайды. Мысалы, күн мен уақыт өрістері Azure SQL дерекқорларында деректер жазбаларының соңғы жаңартылған уақыты көрсетілген.

1. [негізінде жаңа деректер көзі жасаңыз Power Query](connect-power-query.md).

1. А қамтамасыз етіңіз **Аты** деректер көзі үшін.

1. Қосымша жаңартуды қолдайтын деректер көзі таңдаңыз, мысалы, [Azure SQL дерекқоры](/power-query/connectors/azuresqldatabase).

1. Қабылданатын нысандарды немесе кестелерді таңдаңыз.

1. Тасымалдау қадамдарын аяқтап, **Келесі** параметрін таңдаңыз.

1. **Кезеңдік жаңартуды орнату** диалог терезесінде **Кезеңдік жаңарту параметрлерін** ашу үшін **Орнату** параметрін таңдаңыз. **Өткізіп жіберу** қадамын өткізіп жіберсеңіз, деректер көзі толық деректер жинағын жаңартады.
   > [!TIP]
   > Сонымен қатар бұрыннан бар деректер көзін өңдеу арқылы кезеңдік жаңартуды кейінірек қолдана аласыз.

1. **Кезеңдік жаңарту параметрлерінде** деректер көзін жаңарту кезінде таңдалған барлық нысандарды кезеңдік жаңартуды теңшей аласыз.

   :::image type="content" source="media/incremental-refresh-settings.png" alt-text="Қосымша жаңартуға арналған деректер көзіндегі нысандарды конфигурациялау.":::

1. Нысанды таңдап, мына мәліметтерді қамтамасыз етіңіз:

   - **Негізгі кілтті анықтау**: нысанның немесе кестенің негізгі кілтін таңдаңыз.
   - **"Соңғы жаңартылған" өрісті анықтау**: бұл өрісте тек күн немесе уақыт түріндегі төлсипаттар көрсетіледі. Жазбалар соңғы жаңартылған уақытты көрсететін төлсипатты таңдаңыз. Бұл қосымша жаңартудың уақыт аралығына кіретін жазбаларды анықтау үшін қолданылады.
   - **Әрбір жаңартуды тексеру**: қажетті кезеңдік жаңарту уақыт аралығын көрсетіңіз.

1. Деректер көзін жасауды аяқтау үшін **Сақтау** параметрін таңдаңыз. Бастапқы деректер жаңартуы толық жаңарту болады. Одан кейін деректерді кезеңдік жаңарту алдыңғы қадамда теңшелгендей орындалады.


[!INCLUDE [footer-include](includes/footer-banner.md)]