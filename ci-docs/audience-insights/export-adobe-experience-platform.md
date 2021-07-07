---
title: Customer Insights деректерін Adobe Experience Platform жүйесіне экспорттау
description: Adobe Experience Platform қызметіндегі аудитория туралы түсінік сегменттерін пайдалану жолы туралы ақпарат.
ms.date: 03/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: 1045d0e373fd5ea8987684e51bd9a07b7b535ee3
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305531"
---
# <a name="use-customer-insights-segments-in-adobe-experience-platform-preview"></a>Adobe Experience Platform жүйесіндегі Customer Insights сегменттерін пайдалану (алдын ала қарау нұсқасы)

Dynamics 365 Customer Insights бағдарламасындағы аудитория туралы түсініктердің пайдаланушысы ретінде сіз тиісті аудиторияларға бағытталу арқылы маркетинг науқандарын тиімдірек ету үшін сегменттер жасаған болуыңыз мүмкін. Adobe Experience Platform платформасында және Adobe Campaign Standard секілді бағдарламаларда аудитория туралы түсініктерден сегментті пайдалану үшін осы мақалада көрсетілген бірнеше қадамды орындауыңыз қажет.

:::image type="content" source="media/AEP-flow.png" alt-text="Осы мақалада көрсетілген қадамдардың процестік диаграммасы.":::

## <a name="prerequisites"></a>Алғышарттар

-   Dynamics 365 Customer Insights лицензиясы
-   Adobe Experience Platform лицензиясы
-   Adobe Campaign Standard лицензиясы
-   Azure Blob сақтау орны тіркелгісі

## <a name="campaign-overview"></a>Науқанды шолу

Adobe Experience Platform платформасында аудитория туралы түсініктердегі сегменттерді пайдалану жолы туралы толығырақ түсіну үшін үлгі ретінде берілген науқанды қарастырайық.

Сіздің компанияңыз АҚШ-тағы тұтынушыларыңызға ай сайынғы жазылымға негізделген қызметті ұсынады делік. Сізге жазылымы келесі сегіз күнде жаңартылуы керек, бірақ жазылымын әлі ұзартпаған тұтынушыларды анықтау қажет. Осы тұтынушыларды ұстап тұру үшін Adobe Experience Platform бағдарламасы көмегімен электрондық пошта арқылы оларға жарнамалық акция жіберу қажет болуы мүмкін.

Бұл мысалда біз жарнамалық науқанды бір рет электрондық пошта арқылы жүргізгіміз келеді. Бұл мақалада науқанды бірнеше рет жүргізу жағдайлары қарастырылмаған.

## <a name="identify-your-target-audience"></a>Мақсатты аудиторияңызды анықтаңыз

Біздің сценарий бойынша біз тұтынушылардың электрондық пошта мекенжайлары аудитория туралы түсініктерде қолжетімді және сегменттің мүшелерін анықтау үшін олардың жарнамалық артықшылықтары талданды деп болжанады.

[Аудитория туралы түсініктерде анықталған сегмент](segments.md) **ChurnProneCustomers** деп аталады және осы тұтынушыларға электрондық пошта арқылы жарнамалауды жіберуді жоспарлайсыз.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Жасалған ChurnProneCustomers сегменті бар сегменттер бетінің скриншоты.":::

Жіберілетін ұсыныс электрондық хаты аты-жөнін, тегін және тұтынушы жазылымының аяқталу күнін қамтиды. Мұнда тұтынушыларға жазылым аяқталғанға дейін оны ұзартқан кезде алатын жеңілдіктер туралы хабарланады.

## <a name="export-your-target-audience"></a>Мақсатты аудиторияңызды экспорттау

Анықталған мақсатты аудитория арқылы аудитория туралы түсініктерден Azure Blob сақтау орны тіркелгісіне экспорттауды конфигурациялаймыз.

### <a name="configure-a-connection"></a>Қосылымды конфигурациялау

1. **Әкімші** > **Қосылымдар** тармағына өтіңіз.

1. **Қосылым қосу** түймешігін таңдаңыз және қосылымды конфигурациялау үшін **Azure Blob Storage** параметрін таңдаңыз немесе **Azure Blob Storage** тақтасында **Орнату** түймешігін таңдаңыз.

   :::image type="content" source="media/export-azure-blob-storage-tile.png" alt-text="Azure Blob сақтау орнының конфигурация тақтасы."::: 

1. **Көрсетілетін аты** өрісінде қосылымға оңай танылатын атау енгізіңіз. Қосылым атауы мен түрі осы қосылымды сипаттайды. Қосылымның мақсатын түсіндіретін атауды таңдауды ұсынамыз.

1. Осы қосылымды кім пайдалана алатынын таңдаңыз. Егер сіз ешқандай әрекет жасамасаңыз, әдепкі бойынша Әкімшілер болады. Қосымша ақпарат алу үшін [Салымшыларға экспорттау үшін қосылымды пайдалануға рұқсат беру](connections.md#allow-contributors-to-use-a-connection-for-exports) бөлімін қараңыз.

1. Сегментті экспорттау керек Blob сақтау орны тіркелгісі үшін **Тіркелгі атауы**, **Тіркелгі кілті** және **Контейнер** өрістерін енгізіңіз.  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Сақтау орны тіркелгісі конфигурациясының скриншоты."::: 
   
    - Blob сақтау орнының тіркелгі атауын және тіркелгі кілтін табу жолы туралы қосымша ақпарат алу үшін [Azure порталындағы сақтау орны тіркелгісінің параметрлерін басқару](/azure/storage/common/storage-account-manage) бөлімін қараңыз.
    - Контейнерді жасау жөнінде мағлұмат алу үшін мына тақырыпты қараңыз: [Контейнер жасау](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Қосылымды аяқтау үшін **Сақтау** түймешігін таңдаңыз. 

### <a name="configure-an-export"></a>Экспорттауды конфигурациялау

Егер сіз осы түрдегі қосылымға қатынаса алсаңыз, сіз бұл экспорттауды конфигурациялай аласыз. Қосымша ақпарат алу үшін [Экспорттауды конфигурациялау үшін қажет рұқсаттар](export-destinations.md#set-up-a-new-export) бөлімін қараңыз.

1. **Деректер** > **Экспорттау** тармағына өтіңіз.

1. Жаңа экспорттау жасау үшін **Экспорттау қосу** түймешігін таңдаңыз.

1. **Экспорттауға арналған қосылым** өрісінде Azure Blob сақтау орны бөлімінен қосылым таңдаңыз. Егер сіз бұл бөлімнің атауын көрмесеңіз, онда сіз үшін осы түрдегі қосылымдар қолжетімді емес.

1. Экспорттау қажет сегментті таңдаңыз. Бұл мысалда ол **ChurnProneCustomers** болып табылады.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Таңдалған ChurnProneCustomers сегментімен сегмент таңдау бойынша пайдаланушы интерфейсінің скриншоты.":::

1. **Сақтау** опциясын таңдаңыз.

Экспорттау мақсатты орнын сақтағаннан кейін оны **Деректер** > **Экспорттаулар** тармағынан таба аласыз.

[Сегментті сұраныс бойынша экспорттауға](export-destinations.md#run-exports-on-demand) болады. Экспорттау сондай-ақ әрбір [жоспарланған жаңарту](system.md) сайын іске қосылады.

> [!NOTE]
> Экспортталған сегменттегі жазбалар санының Adobe Campaign Standard лицензиясының рұқсат етілген шегінде болуын тексеріңіз.

Экспортталған деректер сіз жоғарыда конфигурациялаған Azure Blob сақтау контейнерінде сақталады. Контейнерде келесі қалта жолы автоматты түрде жасалады:

*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*

Мысал: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv

Экспортталған нысандарға арналған *model.json* пішімі *%ExportDestinationName%* деңгейінде болады.

Мысал: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a>Adobe Experience Platform бағдарламасындағы Experience Data Model (XDM) үлгісін анықтау

Аудитория туралы түсініктердегі экспортталған деректер Adobe Experience Platform шегінде пайдаланылғанға дейін Experience Data Model схемасын анықтап, [нақты уақыттағы тұтынушы профиліне арналған деректерді конфигурациялау](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials) қажет.

[XDM үлгісі дегеніміз не екендігі туралы](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) мәлімет алып, [схема құрамының негіздері туралы](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema) түсінік алыңыз.

## <a name="import-data-into-adobe-experience-platform"></a>Деректерді Adobe Experience Platform бағдарламасына импорттау

Енді барлығы дайын болған кезде профильдер жасау үшін дайындалған аудитория деректерін аудитория туралы түсініктерден Adobe Experience Platform жүйесіне импорттауымыз қажет.

Алдымен, [Azure Blob сақтау орнының бастапқы қосылымын жасаңыз](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).    

Бастапқы қосылымды анықтағаннан кейін сегмент шығысын аудитория туралы түсініктерден Adobe Experience Platform платформасына импорттау үшін бұлттағы сақтау орнының топтық қосылымына арналған [деректер ағынын](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) конфигурациялаңыз.

## <a name="create-an-audience-in-adobe-campaign-standard"></a>Adobe Campaign Standard жүйесінде аудиторияны жасау

Осы науқанға электрондық хабар жіберу үшін біз Adobe Campaign Standard қызметін қолданамыз. Деректерді Adobe Experience Platform бағдарламасына импорттағаннан кейін Adobe Experience Platform бағдарламасындағы деректерді пайдаланып Adobe Campaign Standard жүйесінде [аудитория жасау](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) қажет.


Adobe Experience Platform жүйесіндегі деректер негізінде аудиторияны анықтау үшін Adobe Campaign Standard бағдарламасында [сегментті құрастыру құралын пайдалану](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/audience-destinations/aep-using-segment-builder.html) бойынша мәлімет алыңыз.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Adobe Campaign Standard көмегімен электрондық пошта хабарын жасау және жіберу

Электрондық пошта мазмұнын жасап, содан кейін электрондық пошта хабарын [тексеріп, жіберіңіз](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages).

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Adobe Campaign Standard ұсынған жаңарту ұсынысы бар электрондық пошта хабарының үлгісі.":::
