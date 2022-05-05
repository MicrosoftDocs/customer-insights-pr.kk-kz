---
title: Customer Insights бағдарламасынан деректерді экспорттау
description: Деректерді бөлісу үшін экспорттауы басқарыңыз.
ms.date: 11/01/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: overview
author: pkieffer
ms.author: philk
manager: shellyha
searchScope:
- ci-export
- ci-connections
- customerInsights
ms.openlocfilehash: 9c3b35f1514adcc697672f09cabf593f936e4a82
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: kk-KZ
ms.lasthandoff: 04/27/2022
ms.locfileid: "8643402"
---
# <a name="exports-preview-overview"></a>Экспорттауларға (алдын ала қарау нұсқасы) шолу

**Экспорттаулар** беті барлық конфигурацияланған экспорттарды көрсетеді. Экспорттау белгілі бір деректерді әртүрлі бағдарламалармен бөліседі. Олар тұтынушы профилін, нысандарды, схемаларды және салыстыру мәліметтерін қамтуы мүмкін. Әрбір экспорттау [аутентификация мен кіруді басқару үшін әкімші орнатқан қосылымды](connections.md) қажет етеді.

Экспорттау бетін көру үшін **Деректер** > **Экспорттау** тармағына өтіңіз. Барлық пайдаланушы рөлдері конфигурацияланған экспорттауларды көре алады. Пәрмен жолағындағы іздеу өрісін пайдалану арқылы экспорттауларды олардың атауы, қосылым атауы немесе қосылым түрі бойынша табыңыз.

## <a name="export-types"></a>Экспорттау түрлері

Экспорттаудың екі негізгі түрі бар:  

- **Деректерді экспорттау** Customer Insights жүйесінде қолжетімді нысанның кез келген түрін экспорттауға мүмкіндік береді. Экспорттау үшін таңдаған нысандар барлық деректер өрістерімен, метадеректермен, схемалармен және салыстыру мәліметтерімен экспортталады. 
- **Сегменттік экспорт** Customer Insights жүйесінен сегмент нысандарын экспорттауға мүмкіндік береді. Сегменттер тұтынушы профильдерінің тізімін білдіреді. Экспорттауды конфигурациялау кезінде, сіз деректерді экспорттауды мақсатты жүйеге байланысты енгізілген деректер өрістерін таңдайсыз. 

### <a name="export-segments"></a>Сегменттерді экспорттау

**Бизнес тіркелгілер (бизнес‑бизнес) немесе жеке тұтынушыларға (бизнес‑тұтынушы) арналған орталардағы сегменттерді экспорттау**  
Экспорттау опцияларының көпшілігі ортаның екі түріне де қолдау көрсетеді. Сегменттерді әр түрлі мақсатты жүйелерге экспорттау нақты талаптарға ие. Жалпы алғанда сегмент элементі, тұтынушы профилінде байланыс ақпараты болады. Бұл жеке тұтынушыларға (бизнес‑тұтынушы) негізделген сегменттер үшін әдеттегі жағдай болғанымен, бизнес тіркелгілерге (бизнес‑бизнес) негізделген сегменттер үшін міндетті емес. 

**Бизнес тіркелгілер (бизнес‑бизнес) үшін сегменттерді экспорттау орталары**  
- Бизнес тіркелгілерге арналған орталар мәнмәтініндегі сегменттер *тіркелгі* нысанына негізделген. Тіркелгі сегменттерін сол күйінде экспорттау үшін мақсатты жүйе таза тіркелгі сегменттеріне қолдау көрсетуі керек. Бұл экспорттауды анықтау кезінде **компания** опциясын таңдаған кездегі [LinkedIn](export-linkedin-ads.md) қызметіне қатысты болып табылады.
- Барлық басқа мақсатты жүйелер контакт нысанындағы өрістерді қажет етеді. Тіркелгі сегменттері байланысты контактілерден деректерді шығарып алуын қамтамасыз ету үшін сегменттің анықтамасы контакт нысанының төлсипаттарын жобалауы қажет. [Сегменттер мен жоба төлсипаттарын конфигурациялау](segment-builder.md) туралы қосымша ақпарат.

**Жеке тұтынушыларға (бизнес‑тұтынушы) арналған орталарда сегменттерді экспорттау**  
- Жеке тұтынушыларға арналған орталар мәнмәтініндегі сегменттер *бірыңғай тұтынушы профилі* нысанына негізделген. Мақсатты жүйелердің талаптарына сәйкес келетін әрбір сегмент (мысалы, электрондық пошта мекенжайы) экспортталуы мүмкін.

**Сегментті экспорттауға шектеулер**  
- Үшінші тараптың мақсатты жүйелері экспорттауға болатын тұтынушы профильдерінің санын шектеуі мүмкін. 
- Жеке тұтынушылар үшін сіз экспорттау үшін сегмент таңдаған кезде сегмент элементтерінің нақты санын көресіз. Егер сегмент тым үлкен болса, сізге ескерту келеді. 
- Бизнес тіркелгілер үшін сіз тіркелгілер санын сегментте көресіз; алайда, болжауға болатын контактілер саны көрсетілмейді. Кейбір жағдайларда, бұл мақсатты жүйе қабылдағаннан гөрі көп тұтынушы профилін қамтитын экспортталатын сегментке әкелуі мүмкін. Мақсатты жүйелер нәтижелерінің шегінен асып кету экспорттауды өткізіп жібереді. 

## <a name="set-up-a-new-export"></a>Жаңа экспорттауды орнату  
Экспорттауды орнату немесе өңдеу үшін сізде қолжетімді қосылымдар болуы керек. Қосылымдар сіздің [пайдаланушы рөліңізге](permissions.md) байланысты:
- **Әкімшілер** барлық қосылымдарға қатынаса алады. Сондай-ақ олар экспорттауды орнатқан кезде жаңа қосылымдар жасай алады.
- **Салымшылар** белгілі бір қосылымдарға қатынаса алады. Олар қосылымдарды конфигурациялау және бөлісу үшін әкімшілерге тәуелді. Экспорттау тізімі салымшылардың экспорттауды өңдеп немесе тек **Сіздің рұқсаттарыңыз** бағанында көре алатындығын көрсетеді. Қосымша ақпарат алу үшін [Салымшыларға экспорттау үшін қосылымды пайдалануға рұқсат ету](connections.md#allow-contributors-to-use-a-connection-for-exports) бөліміне өтіңіз.
- **Қараушылар** бұрыннан бар экспорттауды ғана көре алады, бірақ оларды жасай алмайды.

### <a name="define-a-new-export"></a>Жаңа экспорттауды анықтау

1. **Деректер** > **Экспорттау** тармағына өтіңіз.

1. Жаңа экспорттау жасау үшін **Экспорттау қосу** түймешігін таңдаңыз.

1. **Экспортты орнату** тақтасында пайдаланылатын қосылымды таңдаңыз. [Қосылымдар](connections.md) әкімшілер арқылы басқарылады. 

1. Қажетті мәліметтерді енгізіңіз және экспорттауды жасау үшін **Сақтау** түймешігін таңдаңыз.

### <a name="define-a-new-export-based-on-an-existing-export"></a>Бұрыннан бар экспорттау негізінде жаңа экспорттауды анықтау

1. **Деректер** > **Экспорттау** тармағына өтіңіз.

1. Экспорттаулар тізімінде көшірмесін жасау керек экспорттауды таңдаңыз.

1. Таңдалған экспорттаудың мәліметтері бар **Экспорттауды орнату** тақтасын ашу үшін пәрмен жолағынан **Көшірмесін жасау** опциясын таңдаңыз.

1. Экспорттауды қарап шығыңыз және бейімдеңіз және жаңа экспорттауды жасау үшін **Сақтау** түймешігін таңдаңыз.

### <a name="edit-an-export"></a>Экспорттауды өңдеу

1. **Деректер** > **Экспорттау** тармағына өтіңіз.

1. Экспорттаулар тізімінде өңдеу керек экспорттауды таңдаңыз.

1. Пәрмен жолағынан **Өңдеу** түймешігін таңдаңыз.

1. Жаңарту керек мәндерді таңдаңыз және **Сақтау** түймешігін таңдаңыз.

## <a name="view-exports-and-export-details"></a>Экспорттауларды және экспорттау туралы мәліметтерді көру

Экспорттаудың мақсатты орындарын жасағаннан кейін олар **Деректер** > **Экспорттау** тармағында тізімделеді. Барлық пайдаланушылар қандай деректер бөлісілетінін және оның соңғы күйін көре алады.

1. **Деректер** > **Экспорттау** тармағына өтіңіз.

1. Өңдеу рұқсаттары жоқ пайдаланушылар экспорттау мәліметтерін көру үшін **Өңдеу** түймешігінің орнына **Көру** түймешігін таңдайды.

1. Бүйірлік тақта экспорттаудың конфигурациясын көрсетеді. Өңдеу рұқсаттарынсыз мәндерді өзгерту мүмкін емес. Экспорттау бетіне оралу үшін **Жабу** түймешігін таңдаңыз.

## <a name="schedule-and-run-exports"></a>Экспорттауды жоспарлау және іске қосу

Конфигурациялаған әрбір экспорттауда жаңарту кестесі бар. Жаңарту кезінде жүйе экспорттауға қосу үшін жаңа немесе жаңартылған деректерді іздейді. Әдепкі бойынша, экспорттау әр [жоспарланған жүйені жаңарту](system.md#schedule-tab) бөлігі ретінде іске қосылады. Экспорттауды қолмен іске қосу үшін жаңарту кестесін теңшеуге немесе оны өшіруге болады.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

Экспорттау кестесі сіздің ортаңыздың күйіне байланысты. Егер жоспарланған экспорттау басталу керек кезде [тәуелділіктерде](system.md#refresh-processes) жаңартулар орындалып жатса, жүйе алдымен жаңартуларды аяқтайды, содан кейін экспорттауды іске қосады. Экспорттаудың соңғы жаңартылған уақытын **Жаңартылған** бағанынан көре аласыз.

### <a name="schedule-exports"></a>Экспорттауларды жоспарлау

Сіз жеке экспорттауға немесе бірнеше экспорттауға бір уақытта реттелетін жаңарту кестелерін анықтай аласыз. Ағымдағы анықталған кесте экспорттау тізімінің **Кесте** бағанында тізімделген. Кестені өзгертуге арналған рұқсат [экспорттауды өңдеу және анықтаумен](export-destinations.md#set-up-a-new-export) бірдей. 

1. **Деректер** > **Экспорттау** тармағына өтіңіз.

1. Жоспарлау керек экспорттауды таңдаңыз.

1. Пәрмен жолағынан **Жоспарлау** түймешігін таңдаңыз.

1. **Экспорттауды жоспарлау** тақтасында экспорттауды автоматты түрде іске қосу үшін **Жоспарлауды іске қосу** опциясын **Қосулы** күйіне орнатыңыз. Оны қолмен жаңарту үшін **Өшірулі** күйіне орнатыңыз.

1. Автоматты түрде жаңартылған экспорттау үшін **Қайталану** мәнін таңдаңыз және ол үшін мәліметтерді көрсетіңіз. Анықталған уақыт қайталанудың барлық даналарына қолданылады. Бұл экспорттау жаңартуды бастайтын уақыт.

1. **Сақтау** түймешігін таңдау арқылы өзгерістерді қолданыңыз және белсендіріңіз.

Бірнеше экспорттау үшін кестені өңдеген кезде, **Кестелерді сақтау немесе алдын ала анықтау** бөлімінен таңдау жасау керек болады:
- **Жеке кестелерді сақтау**: таңдалған экспорттау үшін алдын ала анықталған кестені сақтаңыз және оларды тек өшіріңіз немесе қосыңыз.
- **Барлық таңдалған экспорттаулар үшін жаңа кесте анықтау**: таңдалған экспорттаудың бұрыннан бар кестелерін алдын ала анықтаңыз,

### <a name="run-exports-on-demand"></a>Экспорттауды сұрау бойынша іске қосу

Жоспарланған жаңартуды күтпестен деректерді экспорттау үшін **Деректер** > **Экспорттау** тармағына өтіңіз.

- Барлық экспорттауларды іске қосу үшін пәрмен жолағында **Барлығын іске қосу** түймешігін таңдаңыз. Бұл әрекет тек белсенді кестесі бар экспорттауды іске қосады.
- Бір рет экспорттауды іске қосу үшін оны тізімнен таңдаңыз және пәрмен жолағынан **Іске қосу** түймешігін таңдаңыз. Осылайша сіз белсенді кестесі жоқ экспорттауды іске қосасыз. 

## <a name="remove-an-export"></a>Экспорттауды алып тастау

1. **Деректер** > **Экспорттау** тармағына өтіңіз.

1. Жою керек экспорттауды таңдаңыз.

1. Пәрмен жолағынан **Жою** пәрменін таңдаңыз.

1. Растау экранында **Жою** опциясын таңдау арқылы жоюды растаңыз.


[!INCLUDE [footer-include](includes/footer-banner.md)]