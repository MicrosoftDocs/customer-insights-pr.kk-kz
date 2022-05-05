---
title: Деректерді біріктіруде нысандарды біріктіру
description: Тұтынушылардың бірыңғай профильдерін жасау үшін деректерді біріктіріңіз.
ms.date: 01/28/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-match
- ci-merge
- ci-relationships
- customerInsights
ms.openlocfilehash: 978a7c9bc440398fa39e9fa1d366d74e5c7aaea0
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: kk-KZ
ms.lasthandoff: 04/27/2022
ms.locfileid: "8643851"
---
# <a name="merge-entities"></a>Нысандарды біріктіру

Біріктіру кезеңі — деректерді біріктіру процесіндегі соңғы кезең. Оның мақсаты — қайшылықты деректерді қайта салыстыру. Қайшылықты деректер мысалдарына екі деректер жиынынан табылатын, бірақ әрқайсысы өзгеше көрінетін тұтынушы аты ("Грант Маршалл" және "Грант Маршал") немесе пішімі әр түрлі телефон нөмірі (617-803-091X және 617803091X) болуы мүмкін. Осы қайшылықты деректер нүктелерін біріктіру төлсипат-төлсипат негізінде орындалады.

:::image type="content" source="media/merge-fields-page.png" alt-text="Бірыңғай тұтынушы профилін анықтайтын біріктірілген өрістермен кестені көрсететін деректерді біріздендіру процесіндегі бетті біріктіру.":::

[Сәйкестендіру кезеңін](match-entities.md) аяқтаған соң, **Біріктіру** бетінен **Біріктіру** қатарын таңдау арқылы біріктіру кезеңін бастайсыз.

## <a name="review-system-recommendations"></a>Жүйе ұсыныстарын қарап шығу

**Деректер** > **Біріздендіру** > **Біріктіру** тармағында бірыңғай тұтынушы профиліңізде біріктіру үшін төлсипаттарды таңдайсыз және алып тастайсыз. Тұтынушы бірыңғай профилі деректерді біріздендіру процесінің нәтижесі болып табылады. Жүйе кейбір төлсипаттарды автоматты түрде біріктіреді.

Автоматты түрде біріктірілген төлсипаттардың біріне қосылған төлсипаттарды көру үшін, сол біріктірілген төлсипатты кестенің **Тұтынушы өрістері** қойыншасынан таңдаңыз. Сол біріктірілген төлсипаттан тұратын төлсипатта біріктірілген төлсипаттан бөлек екі жаңа жол көрсетіледі.

## <a name="separate-rename-exclude-and-edit-merged-fields"></a>Біріктірілген өрістерді бөлу, атауын өзгерту, шығару және өңдеу

Тұтынушының бірыңғай профилін құру үшін жүйенің біріктірілген төлсипаттарды өңдеу әдісін өзгерте аласыз. **Қосымша көрсету** түймешігін таңдаңыз және өзгерту керек нәрсені таңдаңыз.

:::image type="content" source="media/manage-merged-attributes.png" alt-text="Біріктірілген төлсипаттарды басқаруға арналған Көбірек көрсету ашылмалы мәзіріндегі опциялар.":::

Қосымша ақпарат алу үшін келесі бөлімдерді қараңыз.

## <a name="separate-merged-fields"></a>Біріктірілген өрістерді бөлу

Біріктірілген өрістерді бөлу үшін кестеден төлсипатты табыңыз. Бөлінген өрістер тұтынушы бірыңғай профилінде жеке деректер нүктелері ретінде көрсетіледі. 

1. Біріктірілген өрісті таңдаңыз.
  
1. **Қосымша көрсету** түймешігін таңдаңыз және **Өрістерді бөлу** опциясын таңдаңыз.
 
1. Бөлуді растаңыз.

1. Өзгерістерді өңдеу үшін **Сақтау** және **Іске қосу** түймешіктерін таңдаңыз.

## <a name="rename-merged-fields"></a>Біріктірілген өрістердің атын өзгерту

Біріктірілген төлсипаттардың көрсетілетін атауын өзгертіңіз. Шығыс нысанның атауын өзгерту мүмкін емес.

1. Біріктірілген өрісті таңдаңыз.
  
1. **Қосымша көрсету** түймешігін таңдаңыз және **Атауын өзгерту** опциясын таңдаңыз.

1. Өзгертілген көрсетілетін атауды растаңыз. 

1. Өзгерістерді өңдеу үшін **Сақтау** және **Іске қосу** түймешіктерін таңдаңыз.

## <a name="exclude-merged-fields"></a>Біріктірілген өрістерді шығару

Төлсипатты бірыңғай тұтынушы профилінен алып тастаңыз. Егер өріс басқа процестерде, мысалы сегментте қолданылса, оны тұтынушы профилінен шығармас бұрын оны осы процестерден алып тастаңыз. 

1. Біріктірілген өрісті таңдаңыз.
  
1. **Қосымша көрсету** түймешігін таңдаңыз және **Шығару** опциясын таңдаңыз.

1. Шығаруды растаңыз.

1. Өзгерістерді өңдеу үшін **Сақтау** және **Іске қосу** түймешіктерін таңдаңыз. 

**Біріктіру** бетінде барлық шығарылған өрістердің тізімін көру үшін **Шығарылған өрістер** түймешігін таңдаңыз. Бұл тақта шығарылған өрістерді қайта қосуға мүмкіндік береді.

## <a name="edit-a-merged-field"></a>Біріктірілген өрісті өңдеу

1.  Біріктірілген өрісті таңдаңыз.

1.  **Қосымша көрсету** түймешігін таңдаңыз және **Өңдеу** опциясын таңдаңыз.

1.  Өрістерді үш нұсқаның бірінен қалай біріктіру немесе біріктіру керектігін көрсетіңіз:
    - **Маңыздылығы**: қатысушы өрістер үшін көрсетілген маңыздылық дәрежесі негізінде жеңімпаздың мәнін анықтайды. Бұл әдепкі біріктіру опциясы болып табылады. Маңыздылығы бойынша бағаалауды орнату үшін **Жоғары/төмен жылжыту** опциясын таңдаңыз.
    :::image type="content" source="media/importance-merge-option.png" alt-text="Өрістерді біріктіру диалогтік терезесіндегі маңыздылық параметрі."::: 
    - **Ең соңғы**: ең соңғысы негізінде жеңімпаздың мәнін анықтайды. Жаңалықты анықтау үшін біріктіру өрістерінің аумағына қатысатын әрбір субъект үшін күн немесе сандық өріс қажет.
    :::image type="content" source="media/recency-merge-option.png" alt-text="Өрістерді біріктіру диалогтік терезесіндегі жаңалық параметрі.":::
    - **Бұрынғы**: бұрынғысы негізінде жеңімпаздың мәнін анықтайды. Жаңалықты анықтау үшін біріктіру өрістерінің аумағына қатысатын әрбір субъект үшін күн немесе сандық өріс қажет.

1.  Біріктіру процесіне қатысу үшін қосымша өрістер қосуға болады.

1.  Біріктірілген өрістің атын өзгертуге болады.

1. Өзгертулерді қолдану үшін **Дайын** опциясын таңдаңыз.

1. Өзгерістерді өңдеу үшін **Сақтау** және **Іске қосу** түймешіктерін таңдаңыз. 

## <a name="combine-fields-manually"></a>Өрістерді қолмен біріктіру

Біріктірілген төлсипатты қолмен көрсетіңіз.

1. Үстінде **Біріктіру** бет, таңдаңыз **Біріктіру**.

1. таңдаңыз **Өрістер** опция.

1. **Өрістерді біріктіру** ашылмалы мәзірінде біріктіру жеңімпазының саясатын көрсетіңіз.

1. Қосу керек өрісті таңдаңыз. Қосымша өрістерді біріктіру үшін **Өрістер қосу** түймешігін таңдаңыз.

1. **Атауы** және **Шығыс өріс атауы** өрістерін енгізіңіз.

1. Өзгертулерді қолдану үшін **Дайын** опциясын таңдаңыз.

1. Өзгерістерді өңдеу үшін **Сақтау** және **Іске қосу** түймешіктерін таңдаңыз. 

## <a name="combine-a-group-of-fields"></a>Өрістер тобын біріктіріңіз

Өрістер тобын бір бірлік ретінде қарастырыңыз. Мысалы, егер біздің жазбаларымызда Мекенжай1, Мекенжай2, Қала, штат және Zip өрістері болса. Біз басқа жазбаның 2-мекенжайында біріктіргіміз келмейді, бұл біздің деректерімізді толық етеді деп ойлаймыз

1. Үстінде **Біріктіру** бет, таңдаңыз **Біріктіру**.

1. таңдаңыз **Өрістер тобы** опция.

1. ішінде біріктіру жеңімпазының саясатын көрсетіңіз **Топтарды разрядтау** түсіп қалу.

1. таңдаңыз **қосу** және өрістерге қосымша өрістерді немесе қосымша топтарды қосқыңыз келетінін таңдаңыз.

1. А қамтамасыз етіңіз **Аты** және а **Шығару атауы** әрбір біріктірілген өріс үшін.

1. А қамтамасыз етіңіз **Аты** өрістер тобы үшін. 

1. Өзгертулерді қолдану үшін **Дайын** опциясын таңдаңыз.

1. Өзгерістерді өңдеу үшін **Сақтау** және **Іске қосу** түймешіктерін таңдаңыз.

## <a name="change-the-order-of-fields"></a>Өрістердің ретін өзгерту

Кейбір нысандарда басқаларға қарағанда көбірек мәліметтер бар. Егер нысан өріс туралы соңғы деректерді қамтыса, мәндерді біріктіру кезінде оны басқа ұйымдарға қарағанда бірінші орынға қоюға болады.

1. Біріктірілген өрісті таңдаңыз.
  
1. **Қосымша көрсету** түймешігін таңдаңыз және **Өңдеу** опциясын таңдаңыз.

1. **Өрістерді біріктіру** тақтасында ретті орнату үшін **Жоғары/төмен жылжыту** түймешігін таңдаңыз немесе оларды қажетті орынға сүйреп апарыңыз.

1. Өзгерісті растаңыз.

1. Өзгерістерді өңдеу үшін **Сақтау** және **Іске қосу** түймешіктерін таңдаңыз.

## <a name="configure-customer-id-generation"></a>Тұтынушы идентификаторын жасауды конфигурациялау 

Біріктіру өрістерін конфигурациялағаннан кейін CustomerId мәндерін, тұтынушы профилінің бірегей идентификаторларын қалай жасау керектігін анықтауға болады. Деректерді біріктіру процесіндегі біріктіру қадамы бірегей тұтынушы профилінің идентификаторын жасайды. Идентификатор - бұл деректерді біріктіру процесіне әкелетін *Тұтынушы* нысанындағы тұтынушы идентификаторы. 

Тұтынушы нысанындағы CustomerId нөлдік емес жеңімпаз бастапқы кілттердің бірінші мәнінің хэшіне негізделген. Бұл кілттер сәйкестендіру және біріктіру кезеңінде пайдаланылатын нысандардан келеді және сәйкестік тәртібіне әсер етеді.Осылайша, сәйкестік тапсырысының негізгі нысанында бастапқы кілт мәні өзгерген кезде, құрылған CustomerID өзгеруі мүмкін. Негізгі кілт мәні әрқашан бір тұтынушыны білдірмеуі мүмкін.

Тұрақты тұтынушы идентификаторын конфигурациялау бұл әрекетті болдырмауға мүмкіндік береді.

**Бірегей тұтынушы идентификаторын конфигурациялау**

1. **Бірыңғайландыру** > **Біріктіру** тармағына өтіңіз.

1. **Кілттер** қойыншасын таңдаңыз. 

1. **CustomerId** жолына курсорды апарып, **Конфигурациялау** опциясын таңдаңыз.
   :::image type="content" source="media/customize-stable-id.png" alt-text="Идентификатор жасалуын реттеу үшін басқару.":::

1. Бірегей тұтынушы идентификаторынан тұратын және тұрақты болатын беске дейін өрісті таңдаңыз. Сіздің конфигурацияңызға сәйкес келмейтін жазбалар оның орнына жүйеде конфигурацияланған идентификаторды пайдаланады.  

1. **Дайын** опциясын таңдап, өзгерістерді қолдану үшін біріктіру процесін іске қосыңыз.

## <a name="group-profiles-into-households-or-clusters"></a>Профильдерді үй шаруашылықтарына немесе кластерлерге топтастыру

Тұтынушы профилін құру конфигурациясы процесінің бөлігі ретінде сіз байланысты профильдерді кластерге топтау ережелерін анықтай аласыз. Қазіргі уақытта кластерлердің екі түрі қолжетімді — тұрмыстық және реттелетін кластерлер. Егер *Тұтынушы* нысаны *Person.LastName* және *Location.Address* семантикалық өрістерін қамтитын болса, жүйе алдын ала анықталған ережелері бар тұрмыстық кластерді автоматты түрде таңдайды. Сонымен қатар [сәйкестік ережелері](match-entities.md#define-rules-for-match-pairs) сияқты өз ережелері мен шарттары бар кластер жасауға болады.

**Тұрмыс немесе кластерді анықтау**

1. **Бірыңғайландыру** > **Біріктіру** тармағына өтіңіз.

1. **Біріктіру** қойыншасында **Кеңейтілген** > **Кластер жасау** тармағын таңдаңыз.

   :::image type="content" source="media/create-cluster.png" alt-text="Жаңа кластер жасауға арналған басқару элементі.":::

1. **Тұрмыстық** немесе **Реттелетін** кластер арасынан таңдаңыз. Егер *Person.LastName* және *Location.Address* семантикалық өрістері *Тұтынушы* нысанында болса, тұрмыстық автоматты түрде таңдалады.

1. Кластерге атау беріңіз және **Дайын** түймешігін таңдаңыз.

1. Сіз жасаған кластерді табу үшін **Кластерлер** қойыншасын таңдаңыз.

1. Кластерді анықтау үшін ережелер мен шарттарды көрсетіңіз.

1. Біріктіру процесін іске қосу және кластер жасау үшін **Іске қосу** түймешігін таңдаңыз.

Біріктіру процесі іске қосылғаннан кейін кластер идентификаторлары *Тұтынушы* нысанына жаңа өрістер ретінде қосылады.

## <a name="run-your-merge"></a>Біріктіруді іске қосу

Төлсипаттарды қолмен біріктіруге немесе жүйенің оларды біріктіруіне мүмкіндік беріп, үнемі біріктіруді іске қоса аласыз. Процесті бастау үшін **Біріктіру** бетінен **Іске қосу** параметрін таңдаңыз.

> [!div class="mx-imgBorder"]
> ![Деректерді біріктіру Сақтау және іске қосу.](media/configure-data-merge-save-run.png "Деректерді біріктіру Сақтау және іске қосу")

Егер нәтиженің тек бірыңғай тұтынушы нысанында ғана көрсетілуін қаласаңыз **Тек біріктіруді іске қосу** түймешігін таңдаңыз. Кейінгі процестер [жаңарту кестесінде анықталған](system.md#schedule-tab) ретінде жаңартылатын болады.

Жүйені өзгерістермен жаңарту үшін **Біріктіруді және кейінгі процестерді іске қосу** опциясын таңдаңыз. Барлық процестер, соның ішінде толықтыру, сегменттер және көрсеткіштер автоматты түрде қайта іске қосылады. Барлық кейінгі процестер аяқталғаннан кейін тұтынушы профильдері сіз жасаған барлық өзгерістерді көрсетеді.

Қосымша өзгертулер енгізу және қадамды қайта орындау үшін аяқталмаған біріктіруді болдырмауға болады. **Жаңартылуда ...** мәтінін таңдап, пайда болған бүйірлік тақтадағы **Тапсырмадан бас тарту** опциясын басыңыз.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

:::image type="content" source="media/process-detail-path.png" alt-text="Тапсырма күйінің сілтемесінен толық мәліметтерді өңдеуге арналған зерттеу жолы.":::

## <a name="next-step"></a>Келесі қадам

Тұтынушылар туралы қосымша түсініктер алу үшін [әрекеттер](activities.md), [арттыру](enrichment-hub.md) немесе [қарым-қатынастар](relationships.md) параметрін теңшеңіз.

Егер сіз әрекеттерді, толықтыруды немесе сегменттерді конфигурациялаған болсаңыз, олар тұтынушылардың соңғы деректерін пайдалану үшін автоматты түрде өңделеді.

[!INCLUDE [footer-include](includes/footer-banner.md)]