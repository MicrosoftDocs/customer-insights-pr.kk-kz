---
title: Customer Insights деректерін Adobe Campaign Standard қызметіне экспорттау
description: Customer Insights сегменттерін пайдалану жолын біліңіз Adobe Науқан стандарты.
ms.date: 03/29/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: 2a62d2f889f199222eeb8cc969fce62fa89fa6f0
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: kk-KZ
ms.lasthandoff: 04/27/2022
ms.locfileid: "8643455"
---
# <a name="use-customer-insights-segments-in-adobe-campaign-standard-preview"></a>Adobe Campaign Standard бағдарламасында Customer Insights сегменттерін пайдалану (алдын ала қарау)

Пайдаланушы ретінде Dynamics 365 Customer Insights, сәйкес аудиторияларды бағыттау арқылы маркетингтік науқандарыңызды тиімдірек ету үшін сегменттер жасаған болуыңыз мүмкін. Customer Insights сегментін пайдалану үшін Adobe Experience Platform және сияқты қолданбалар Adobe Науқан стандарты, сіз осы мақалада сипатталған бірнеше қадамдарды орындауыңыз керек.

:::image type="content" source="media/ACS-flow.png" alt-text="Осы мақалада көрсетілген қадамдардың процестік диаграммасы.":::

## <a name="prerequisites"></a>Алғышарттар

-   Dynamics 365 Customer Insights лицензиясы
-   Adobe Campaign Standard лицензиясы
-   Azure Blob сақтау орны тіркелгісі

## <a name="campaign-overview"></a>Науқанға шолу

Customer Insights сегменттерін қалай пайдалануға болатынын жақсырақ түсіну үшін Adobe Experience Platform, жалған үлгі науқанды қарастырайық.

Сіздің компанияңыз АҚШ-тағы тұтынушыларыңызға ай сайынғы жазылымға негізделген қызметті ұсынады делік. Сізге жазылымы келесі сегіз күнде жаңартылуы керек, бірақ жазылымын әлі ұзартпаған тұтынушыларды анықтау қажет. Бұл тұтынушыларды сақтау үшін оларға Adobe Campaign Standard көмегімен электрондық пошта арқылы жарнамалық ұсыныс жіберу қажет.

Бұл мысалда біз жарнамалық науқанды бір рет электрондық пошта арқылы жүргізгіміз келеді. Бұл мақалада науқанды бірнеше рет жүргізу жағдайлары қарастырылмаған. Дегенмен, Customer Insights және Adobe Науқан стандартын қайталанатын науқан сценарийі үшін де жұмыс істеуге конфигурациялауға болады.

## <a name="identify-your-target-audience"></a>Мақсатты аудиторияңызды анықтаңыз

Біздің сценарийде тұтынушылардың электрондық пошта мекенжайлары қол жетімді және сегмент мүшелерін анықтау үшін олардың жарнамалық қалаулары талданған деп есептейміз.

The [Customer Insights ішінде сіз анықтаған сегмент](segments.md) аталады **ChurnProneCustomers** және сіз осы тұтынушыларға электрондық пошта жарнамасын жіберуді жоспарлап отырсыз.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Жасалған ChurnProneCustomers сегменті бар сегменттер бетінің скриншоты.":::

Жіберілетін ұсыныс электрондық хаты аты-жөнін, тегін және тұтынушы жазылымының аяқталу күнін қамтиды. Мұнда тұтынушыларға жазылым аяқталғанға дейін оны ұзартқан кезде алатын жеңілдіктер туралы хабарланады.

## <a name="export-your-target-audience"></a>Мақсатты аудиторияңызды экспорттау

### <a name="configure-a-connection"></a>Қосылымды конфигурациялау

Мақсатты аудиторияны анықтау арқылы экспортты Azure Blob сақтау тіркелгісіне теңшей аламыз.

1. Customer Insights бөліміне өтіңіз **Админ** > **Қосылымдар**.

1. Қосылымды конфигурациялау үшін **Қосылымды қосу** опциясын таңдап, **Adobe Campaign** опциясын таңдаңыз немесе **Adobe Campaign** тақтасында **Орнату** опциясын таңдаңыз.

   :::image type="content" source="media/adobe-campaign-standard-tile.png" alt-text="Adobe Campaign Standard жүйесіне арналған конфигурация тақтасы.":::

1. **Көрсетілетін аты** өрісінде қосылымға оңай танылатын атау енгізіңіз. Қосылым атауы мен түрі осы қосылымды сипаттайды. Қосылымның мақсатын түсіндіретін атауды таңдауды ұсынамыз.

1. Осы қосылымды кім пайдалана алатынын таңдаңыз. Егер сіз ешқандай әрекет жасамасаңыз, әдепкі бойынша Әкімшілер болады. Қосымша ақпарат алу үшін [Экспорттауды конфигурациялау үшін қажет рұқсаттар](export-destinations.md#set-up-a-new-export) бөлімін қараңыз.

1. Сегментті экспорттау керек Azure Blob сақтау тіркелгісінің **Тіркелгі атауы**, **Тіркелгі кілті** және **Контейнер** өрістерін енгізіңіз.  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Сақтау орны тіркелгісі конфигурациясының скриншоты."::: 

   - Azure екілік нысан сақтау тіркелгісінің аты мен тіркелгі кілтін табу жөнінде қосымша ақпарат алу үшін [Azure порталындағы сақтау орны тіркелгі параметрлерін басқару](/azure/storage/common/storage-account-manage) бөлімін қараңыз.

   - Контейнерді жасау жөнінде мағлұмат алу үшін мына тақырыпты қараңыз: [Контейнер жасау](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Қосылымды аяқтау үшін **Сақтау** түймешігін таңдаңыз.

### <a name="configure-an-export"></a>Экспорттауды конфигурациялау

Егер сіз осы түрдегі қосылымға қатынаса алсаңыз, сіз бұл экспорттауды конфигурациялай аласыз. Қосымша ақпарат алу үшін [Экспорттауды конфигурациялау үшін қажет рұқсаттар](export-destinations.md#set-up-a-new-export) бөлімін қараңыз.

1. **Деректер** > **Экспорттау** тармағына өтіңіз.

1. Жаңа экспорттау жасау үшін **Экспорттау қосу** түймешігін таңдаңыз.

1. **Экспорттауға арналған қосылым** өрісінде Adobe Campaign бөлімінен қосылым таңдаңыз. Егер сіз бұл бөлімнің атауын көрмесеңіз, онда сіз үшін осы түрдегі қосылымдар қолжетімді емес.

1. Экспорттау қажет сегментті таңдаңыз. Бұл мысалда ол **ChurnProneCustomers** болып табылады.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Таңдалған ChurnProneCustomers сегментімен сегмент таңдау бойынша пайдаланушы интерфейсінің скриншоты.":::

1. **Келесі** пәрменін таңдаңыз.

1. Енді біз картаға түсіреміз **Дереккөз** Customer Insights сегментінен келесіге дейінгі өрістер **Мақсат** өріс атаулары Adobe Науқанның стандартты профиль схемасы.

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="Adobe Campaign Standard қосқышына арналған өрісті салыстыру.":::

   Егер қосымша төлсипаттар қосу қажет болса, **Төлсипат қосу** пәрменін таңдаңыз. Мақсатты атау бастапқы өріс атынан басқаша болуы мүмкін, осылайша сіз әлі де Customer Insights жүйесінен сегмент шығысын салыстыра аласыз Adobe Екі жүйеде өрістердің аты бірдей болмаса, науқан стандарты.

   > [!NOTE]
   > Электрондық пошта мекенжайы сәйкестендіру өрісі ретінде пайдаланылады, бірақ деректерді салыстыру үшін тұтынушы профиліндегі кез келген басқа идентификаторды пайдалануға болады.Adobe Науқан стандарты.

1. **Сақтау** пәрменін таңдаңыз.

Экспорттау мақсатты орнын сақтағаннан кейін оны **Деректер** > **Экспорттаулар** тармағынан таба аласыз.

[Сегментті сұраныс бойынша экспорттауға](export-destinations.md#run-exports-on-demand) болады. Экспорттау сондай-ақ әрбір [жоспарланған жаңарту](system.md) сайын іске қосылады.

> [!NOTE]
> Экспортталатын сегменттегі жазбалар саны Adobe Campaign Standard лицензиясының рұқсат етілген шегінде екеніне көз жеткізіңіз.

Экспортталған деректер сіз жоғарыда конфигурациялаған Azure Blob сақтау контейнерінде сақталады. Контейнерде келесі қалта жолы автоматты түрде жасалады:

*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*

Мысал: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv

## <a name="configure-adobe-campaign-standard"></a>Adobe Campaign Standard жүйесін конфигурациялау

Экспортталған сегменттер алдыңғы қадамда экспорттау орнын анықтау кезінде таңдалған бағандарды қамтиды. Бұл деректерді [Adobe Campaign Standard жүйесіндегі профильдерді жасау](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles) үшін пайдалануға болады.

Adobe Campaign Standard жүйесінде сегментті пайдалану үшін екі қосымша өріс қосу үшін Adobe Campaign Standard бағдарламасында профиль схемасын кеңейту қажет. Adobe Campaign Standard жүйесіндегі жаңа өрістермен [профиль ресурсын кеңейту](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) жолы туралы мәлімет алыңыз.

Біздің мысалда бұл өрістер *Сегмент атауы және сегмент күні (міндетті емес)* болып табылады.

Бұл өрістерді осы науқан үшін назар аударғымыз келетін Adobe Campaign Standard бағдарламасында профильдерді анықтау үші пайдаланамыз.

Егер Adobe Campaign Standard бағдарламасында импортталатыннан басқа жазбалар болмаса, бұл қадамды өткізіп жіберуге болады.

## <a name="import-data-into-adobe-campaign-standard"></a>Деректерді Adobe Campaign Standard жүйесіне импорттау

Енді бәрі орнында, біз Customer Insights-тен дайындалған аудитория деректерін импорттауымыз керек Adobe Профильдер жасау үшін науқан стандарты. Жұмыс ағынын пайдалану арқылы [Adobe Campaign Standard жүйесінде профильдерді импорттау жолдары туралы](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) мәлімет алыңыз.

Төмендегі суреттегі импорттау жұмыс процесі әрбір сегіз сағат сайын іске қосылатын және экспортталған Customer Insights сегменттерін (Azure Blob қоймасындағы .csv файлы) іздеу үшін конфигурацияланған. Жұмыс ағыны .csv файл мазмұнын көрсетілген баған ретімен шығарады. Бұл жұмыс ағыны негізгі қателерді өңдеуді орындау және Adobe Campaign Standard бағдарламасындағы деректерді жоймас бұрын әр жазбада электрондық пошта мекенжайы болуын қамтамасыз ету үшін жасалды. Жұмыс ағыны Adobe Campaign Standard профиль деректеріне жүктемес бұрын файл атауынан сегмент атауын алады.

:::image type="content" source="media/ACS-import-workflow.png" alt-text="Adobe Campaign Standard пайдаланушы интерфейсіндегі импорттау жұмыс ағынының скриншоты.":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a>Adobe Campaign Standard қызметінде аудитория алу

Деректер Adobe Campaign Standard жүйесіне импортталғаннан кейін үлгі науқаны үшін анықталған профильдерді таңдау үшін тұтынушылар *Сегмент атауы* және *Сегмент күні* параметрлеріне негізделген [жұмыс ағыны](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) мен [сұрауды](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) жасауға болады.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Adobe Campaign Standard көмегімен электрондық пошта хабарын жасау және жіберу

Электрондық пошта мазмұнын жасап, содан кейін электрондық пошта хабарын [тексеріп, жіберіңіз](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages).

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Adobe Campaign Standard жүйесінен жаңарту ұсынысы бар электрондық поштаның үлгісі.":::
