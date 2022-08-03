---
title: Customer Insights сегменттерін келесіге экспорттаңыз Adobe Науқан стандарты (алдын ала қарау)
description: Customer Insights сегменттерін пайдалану жолын біліңіз Adobe Науқан стандарты.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: 834880cac9c5023157983081ff2513d9b051491f
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: kk-KZ
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195527"
---
# <a name="export-customer-insights-segments-to-adobe-campaign-standard-preview"></a>Customer Insights сегменттерін келесіге экспорттаңыз Adobe Науқан стандарты (алдын ала қарау)

Тиісті аудиторияларға бағытталған сегменттерді экспорттау Adobe Науқан стандарты.

:::image type="content" source="media/ACS-flow.png" alt-text="Осы мақалада көрсетілген қадамдардың процестік диаграммасы.":::

## <a name="prerequisites"></a>Алғышарттар

- Ан Adobe Campaign Standard лицензиясы.
- Ан [Azure Blob сақтау тіркелгісі](/azure/storage/blobs/create-data-lake-storage-account) аты және тіркелгі кілті. Аты мен кілтін табу үшін қараңыз [Azure порталында сақтау тіркелгісінің параметрлерін басқарыңыз](/azure/storage/common/storage-account-manage).
- Ан [Azure Blob сақтау контейнері](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

## <a name="campaign-overview"></a>Науқанға шолу

Customer Insights сегменттерін қалай пайдалануға болатынын жақсырақ түсіну үшін Adobe Experience Platform, жалған үлгі науқанды қарастырайық.

Сіздің компанияңыз АҚШ-тағы тұтынушыларыңызға ай сайынғы жазылымға негізделген қызметті ұсынады делік. Сізге жазылымы келесі сегіз күнде жаңартылуы керек, бірақ жазылымын әлі ұзартпаған тұтынушыларды анықтау қажет. Бұл тұтынушыларды сақтау үшін оларға Adobe Campaign Standard көмегімен электрондық пошта арқылы жарнамалық ұсыныс жіберу қажет.

Бұл мысалда біз жарнамалық науқанды бір рет электрондық пошта арқылы жүргізгіміз келеді. Бұл мақалада науқанды бірнеше рет жүргізу жағдайлары қарастырылмаған. Дегенмен, Customer Insights және Adobe Науқан стандартын қайталанатын науқан сценарийі үшін де жұмыс істеуге конфигурациялауға болады.

## <a name="identify-your-target-audience"></a>Мақсатты аудиторияңызды анықтаңыз

Біздің сценарийде тұтынушылардың электрондық пошта мекенжайлары Customer Insights қызметінде қолжетімді және сегмент мүшелерін анықтау үшін олардың жарнамалық таңдаулары талданған деп есептейміз.

The [Customer Insights ішінде сіз анықтаған сегмент](segments.md) аталады **ChurnProneCustomers** және сіз осы тұтынушыларға электрондық пошта жарнамасын жіберуді жоспарлап отырсыз.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Жасалған ChurnProneCustomers сегменті бар сегменттер бетінің скриншоты.":::

Жіберілетін ұсыныс электрондық хаты аты-жөнін, тегін және тұтынушы жазылымының аяқталу күнін қамтиды. Мұнда тұтынушыларға жазылым аяқталғанға дейін оны ұзартқан кезде алатын жеңілдіктер туралы хабарланады.

## <a name="export-your-target-audience"></a>Мақсатты аудиторияңызды экспорттау

### <a name="set-up-connection-to-adobe-campaign"></a>Қосылымды орнату Adobe Науқан

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. **Әкімші** > **Қосылымдар** тармағына өтіңіз.

1. таңдаңыз **Қосылым қосыңыз** және таңдаңыз **Adobe Науқан**.

1. **Көрсетілетін аты** өрісінде қосылымға оңай танылатын атау енгізіңіз. Қосылым атауы мен түрі осы қосылымды сипаттайды. Қосылымның мақсатын түсіндіретін атауды таңдауды ұсынамыз.

1. Осы қосылымды кім пайдалана алатынын таңдаңыз. Әдепкі бойынша бұл тек әкімшілер. Қосымша ақпарат алу үшін [Салымшыларға экспорттау үшін қосылымды пайдалануға рұқсат беру](connections.md#allow-contributors-to-use-a-connection-for-exports) бөлімін қараңыз.

1. енгізіңіз **Төлем алушы**, **жазба кілті**, және **Контейнер** Blob сақтау тіркелгісіне арналған.  

   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Сақтау орны тіркелгісі конфигурациясының скриншоты.":::

1. шолу [деректердің құпиялылығы және сәйкестігі](connections.md#data-privacy-and-compliance) және таңдаңыз **Мен келісемін**.

1. Қосылымды аяқтау үшін **Сақтау** түймешігін таңдаңыз.

### <a name="configure-an-export"></a>Экспорттауды конфигурациялау

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. **Деректер** > **Экспорттау** тармағына өтіңіз.

1. таңдаңыз **Экспортты қосыңыз**.

1. **Экспорттауға арналған қосылым** өрісінде Adobe Campaign бөлімінен қосылым таңдаңыз. Егер қосылым болмаса, әкімшіге хабарласыңыз.

1. Экспорттау үшін атау енгізіңіз.

1. Экспорттау қажет сегментті таңдаңыз. Бұл мысалда ол **ChurnProneCustomers** болып табылады.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Таңдалған ChurnProneCustomers сегментімен сегмент таңдау бойынша пайдаланушы интерфейсінің скриншоты.":::

1. **Келесі** пәрменін таңдаңыз.

1. картасы **Дереккөз** Customer Insights сегментінен келесіге дейінгі өрістер **Мақсат** өріс атаулары Adobe Науқанның стандартты профиль схемасы.

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="Adobe Campaign Standard қосқышына арналған өрісті салыстыру.":::

   Егер қосымша төлсипаттар қосу қажет болса, **Төлсипат қосу** пәрменін таңдаңыз. Мақсатты атау бастапқы өріс атауынан басқаша болуы мүмкін, осылайша сіз әлі де Customer Insights жүйесінен сегмент шығысын салыстыра аласыз Adobe Екі жүйеде өрістердің аты бірдей болмаса, науқан стандарты.

   > [!NOTE]
   > Электрондық пошта мекенжайы сәйкестендіру өрісі ретінде пайдаланылады, бірақ деректерді салыстыру үшін тұтынушы профиліндегі кез келген басқа идентификаторды пайдалануға болады.Adobe Науқан стандарты.

1. **Сақтау** пәрменін таңдаңыз.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

> [!NOTE]
> Экспортталатын сегменттегі жазбалар саны Adobe Campaign Standard лицензиясының рұқсат етілген шегінде екеніне көз жеткізіңіз.

Экспортталған деректер сіз жоғарыда конфигурациялаған Azure Blob сақтау контейнерінде сақталады. Келесі қалта жолы контейнерде автоматты түрде жасалады: *%ContainerName% /CustomerInsights_%instanceID% /% экспорттау орны-атауы%_%segmentname%_%timestamp% .csv*

Мысал: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv

## <a name="configure-adobe-campaign-standard"></a>Adobe Campaign Standard жүйесін конфигурациялау

Экспортталған сегменттерде экспортты конфигурациялау кезінде таңдалған бағандар бар. Бұл деректерді [Adobe Campaign Standard жүйесіндегі профильдерді жасау](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles) үшін пайдалануға болады.

сегментті пайдалану үшін Adobe Науқан стандарты, [профиль схемасын кеңейту](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) жылы Adobe Екі қосымша өрісті қамтитын науқан стандарты.

Біздің мысалда бұл өрістер сегмент атауы және сегмент күні болып табылады. Бұл өрістерді осы науқан үшін назар аударғымыз келетін Adobe Campaign Standard бағдарламасында профильдерді анықтау үші пайдаланамыз.

Басқа жазбалар болмаса Adobe Импортталатындардан басқа Campaign Standard, бұл қадамды өткізіп жіберіңіз.

## <a name="import-data-into-adobe-campaign-standard"></a>Деректерді Adobe Campaign Standard жүйесіне импорттау

Customer Insights ішінен дайындалған аудитория деректерін импорттаңыз Adobe Науқан стандарты [жұмыс процесін пайдаланып профильдер жасау](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences).

Төмендегі суреттегі импорттау жұмыс процесі әрбір сегіз сағат сайын іске қосылатын және экспортталған Customer Insights сегменттерін (Azure Blob қоймасындағы .csv файлы) іздеу үшін конфигурацияланған. Жұмыс ағыны .csv файл мазмұнын көрсетілген баған ретімен шығарады. Бұл жұмыс ағыны негізгі қателерді өңдеуді орындау және Adobe Campaign Standard бағдарламасындағы деректерді жоймас бұрын әр жазбада электрондық пошта мекенжайы болуын қамтамасыз ету үшін жасалды. Жұмыс ағыны Adobe Campaign Standard профиль деректеріне жүктемес бұрын файл атауынан сегмент атауын алады.

:::image type="content" source="media/ACS-import-workflow.png" alt-text="Adobe Campaign Standard пайдаланушы интерфейсіндегі импорттау жұмыс ағынының скриншоты.":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a>Adobe Campaign Standard қызметінде аудитория алу

Деректер импортталғаннан кейін Adobe Науқан стандарты, [жұмыс процесін құру](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) және [сұрау](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) біздің үлгі науқанымыз үшін анықталған профильдерді таңдау үшін сегмент атауы мен сегмент күні негізінде тұтынушылар.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Adobe Campaign Standard көмегімен электрондық пошта хабарын жасау және жіберу

Электрондық пошта мазмұнын жасап, содан кейін электрондық пошта хабарын [тексеріп, жіберіңіз](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages).

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Adobe Campaign Standard жүйесінен жаңарту ұсынысы бар электрондық поштаның үлгісі.":::

[!INCLUDE [footer-include](includes/footer-banner.md)]
