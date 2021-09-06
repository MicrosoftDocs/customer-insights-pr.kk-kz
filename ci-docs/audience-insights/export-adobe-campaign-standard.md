---
title: Customer Insights деректерін Adobe Campaign Standard қызметіне экспорттау
description: Adobe Campaign Standard қызметіндегі аудитория туралы түсінік сегменттерін пайдалану жолы туралы ақпарат.
ms.date: 03/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: d301b4f0cb875303fb3d373b77177acd1c1f5219cd6f23c2a1d29ce67a222eab
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 08/10/2021
ms.locfileid: "7032170"
---
# <a name="use-customer-insights-segments-in-adobe-campaign-standard-preview"></a>Adobe Campaign Standard бағдарламасында Customer Insights сегменттерін пайдалану (алдын ала қарау)

Dynamics 365 Customer Insights бағдарламасындағы аудитория туралы түсініктердің пайдаланушысы ретінде сіз тиісті аудиторияларға бағытталу арқылы маркетинг науқандарын тиімдірек ету үшін сегменттер жасаған болуыңыз мүмкін. Adobe Experience Platform қызметінде және Adobe Campaign Standard секілді бағдарламаларда аудитория туралы пайдалы мәліметтер сегментін пайдалану үшін осы мақалада көрсетілген кейбір қадамдарды орындау қажет.

:::image type="content" source="media/ACS-flow.png" alt-text="Осы мақалада көрсетілген қадамдардың процестік диаграммасы.":::

## <a name="prerequisites"></a>Алғышарттар

-   Dynamics 365 Customer Insights лицензиясы
-   Adobe Campaign Standard лицензиясы
-   Azure Blob сақтау орны тіркелгісі

## <a name="campaign-overview"></a>Науқанға шолу

Adobe Experience Platform қызметінде аудитория туралы пайдалы мәліметтердегі сегменттерді пайдалану жолын жақсырақ түсіну үшін жасанды үлгі науқанын қарастырайық.

Сіздің компанияңыз АҚШ-тағы тұтынушыларыңызға ай сайынғы жазылымға негізделген қызметті ұсынады делік. Сізге жазылымы келесі сегіз күнде жаңартылуы керек, бірақ жазылымын әлі ұзартпаған тұтынушыларды анықтау қажет. Бұл тұтынушыларды сақтау үшін оларға Adobe Campaign Standard көмегімен электрондық пошта арқылы жарнамалық ұсыныс жіберу қажет.

Бұл мысалда біз жарнамалық науқанды бір рет электрондық пошта арқылы жүргізгіміз келеді. Бұл мақалада науқанды бірнеше рет жүргізу жағдайлары қарастырылмаған. Дегенмен, аудитория туралы пайдалы мәліметтер мен Adobe Campaign Standard бағдарламасын қайталанатын науқан сценарийімен жұмыс істеу үшін конфигурациялауға болады.

## <a name="identify-your-target-audience"></a>Мақсатты аудиторияңызды анықтаңыз

Біздің сценарий бойынша біз тұтынушылардың электрондық пошта мекенжайлары аудитория туралы түсініктерде қолжетімді және сегменттің мүшелерін анықтау үшін олардың жарнамалық артықшылықтары талданды деп болжанады.

[Аудитория туралы түсініктерде анықталған сегмент](segments.md) **ChurnProneCustomers** деп аталады және осы тұтынушыларға электрондық пошта арқылы жарнамалауды жіберуді жоспарлайсыз.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Жасалған ChurnProneCustomers сегменті бар сегменттер бетінің скриншоты.":::

Жіберілетін ұсыныс электрондық хаты аты-жөнін, тегін және тұтынушы жазылымының аяқталу күнін қамтиды. Мұнда тұтынушыларға жазылым аяқталғанға дейін оны ұзартқан кезде алатын жеңілдіктер туралы хабарланады.

## <a name="export-your-target-audience"></a>Мақсатты аудиторияңызды экспорттау

### <a name="configure-a-connection"></a>Қосылымды конфигурациялау

Анықталған мақсатты аудитория арқылы аудитория туралы түсініктерден Azure Blob сақтау орны тіркелгісіне экспорттауды конфигурациялаймыз.

1. Audience insights бағдарламасында **Әкімші** > **Қосылымдар** тармағына өтіңіз.

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

1. Аудитория туралы пайдалы мәліметтер сегментіндегі **Бастапқы** өрістерін Adobe Campaign Standard профилінің схемасындағы **Мақсатты** өріске салыстырамыз.

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="Adobe Campaign Standard қосқышына арналған өрісті салыстыру.":::

   Егер қосымша төлсипаттар қосу қажет болса, **Төлсипат қосу** пәрменін таңдаңыз. Мақсатты өрістің атауы бастапқы өрістің атауынан өзгеше болуы мүмкін, сондықтан екі жүйеде бірдей аттар болмаса, аудитория туралы пайдалы мәліметтердегі сегмент шығысын Adobe Campaign Standard жүйесіне экспорттауға болады.

   > [!NOTE]
   > Электрондық пошта мекенжайын идентификациялық өріс ретінде пайдалануға болады, бірақ деректерді Adobe Campaign Standard жүйесіне салыстыру үшін аудитория туралы пайдалы мәліметтер тұтынушы профиліндегі басқа идентификацияны пайдалануға болады.

1. **Сақтау** опциясын таңдаңыз.

Экспорттау мақсатты орнын сақтағаннан кейін оны **Деректер** > **Экспорттаулар** тармағынан таба аласыз.

[Сегментті сұраныс бойынша экспорттауға](export-destinations.md#run-exports-on-demand) болады. Экспорттау сондай-ақ әрбір [жоспарланған жаңарту](system.md) сайын іске қосылады.

> [!NOTE]
> Экспортталатын сегменттегі жазбалар саны Adobe Campaign Standard лицензиясының рұқсат етілген шегінде екеніне көз жеткізіңіз.

Экспортталған деректер сіз жоғарыда конфигурациялаған Azure Blob сақтау контейнерінде сақталады. Контейнерде келесі қалта жолы автоматты түрде жасалады:

*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*

Мысал: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv

## <a name="configure-adobe-campaign-standard"></a>Adobe Campaign Standard жүйесін конфигурациялау

Аудитория мәліметтерінен алынған сегмент экспортталған кезде, алдыңғы қадамда экспорттауды анықтаған кезде сіз таңдаған бағандарды қамтиды. Бұл деректерді [Adobe Campaign Standard жүйесіндегі профильдерді жасау](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles) үшін пайдалануға болады.

Adobe Campaign Standard жүйесінде сегментті пайдалану үшін екі қосымша өріс қосу үшін Adobe Campaign Standard бағдарламасында профиль схемасын кеңейту қажет. Adobe Campaign Standard жүйесіндегі жаңа өрістермен [профиль ресурсын кеңейту](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) жолы туралы мәлімет алыңыз.

Біздің мысалда бұл өрістер *Сегмент атауы және сегмент күні (міндетті емес)* болып табылады.

Бұл өрістерді осы науқан үшін назар аударғымыз келетін Adobe Campaign Standard бағдарламасында профильдерді анықтау үші пайдаланамыз.

Егер Adobe Campaign Standard бағдарламасында импортталатыннан басқа жазбалар болмаса, бұл қадамды өткізіп жіберуге болады.

## <a name="import-data-into-adobe-campaign-standard"></a>Деректерді Adobe Campaign Standard жүйесіне импорттау

Енді барлығы өз орнында, профильдер жасау үшін аудитория туралы пайдалы мәліметтердегі дайындалған аудитория деректерін Adobe Campaign Standard қызметіне импорттау қажет. Жұмыс ағынын пайдалану арқылы [Adobe Campaign Standard жүйесінде профильдерді импорттау жолдары туралы](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) мәлімет алыңыз.

Төмендегі кескіндегі импорттау жұмыс ағыны әр сегіз сағат сайын іске қосылатындай етіп және экспортталған аудитория түсініктерін іздейтін етіп (Azure екілік нысан сақтау орнындағы .csv файлы) конфигурацияланған. Жұмыс ағыны .csv файл мазмұнын көрсетілген баған ретімен шығарады. Бұл жұмыс ағыны негізгі қателерді өңдеуді орындау және Adobe Campaign Standard бағдарламасындағы деректерді жоймас бұрын әр жазбада электрондық пошта мекенжайы болуын қамтамасыз ету үшін жасалды. Жұмыс ағыны Adobe Campaign Standard профиль деректеріне жүктемес бұрын файл атауынан сегмент атауын алады.

:::image type="content" source="media/ACS-import-workflow.png" alt-text="Adobe Campaign Standard пайдаланушы интерфейсіндегі импорттау жұмыс ағынының скриншоты.":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a>Adobe Campaign Standard қызметінде аудитория алу

Деректер Adobe Campaign Standard жүйесіне импортталғаннан кейін үлгі науқаны үшін анықталған профильдерді таңдау үшін тұтынушылар *Сегмент атауы* және *Сегмент күні* параметрлеріне негізделген [жұмыс ағыны](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) мен [сұрауды](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) жасауға болады.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Adobe Campaign Standard көмегімен электрондық пошта хабарын жасау және жіберу

Электрондық пошта мазмұнын жасап, содан кейін электрондық пошта хабарын [тексеріп, жіберіңіз](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages).

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Adobe Campaign Standard жүйесінен жаңарту ұсынысы бар электрондық поштаның үлгісі.":::
