---
title: Customer Insights деректерін Adobe Experience Platform қызметіне экспорттау
description: ішінде Customer Insights сегменттерін пайдалану жолын үйреніңіз Adobe Experience Platform.
ms.date: 03/29/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: 42a4e0c6bce67a63b449a541299620ef2f4a3259
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: kk-KZ
ms.lasthandoff: 04/27/2022
ms.locfileid: "8643731"
---
# <a name="use-customer-insights-segments-in-adobe-experience-platform-preview"></a>Adobe Experience Platform бағдарламасында Customer Insights сегменттерін пайдалану (алдын ала қарау)

пайдаланушысы ретінде Dynamics 365 Customer Insights, сәйкес аудиторияларды бағыттау арқылы маркетингтік науқандарыңызды тиімдірек ету үшін сегменттер жасаған болуыңыз мүмкін. Customer Insights сегментін пайдалану үшін Adobe Experience Platform және сияқты қолданбалар Adobe Науқан стандарты, сіз осы мақалада сипатталған бірнеше қадамдарды орындауыңыз керек.

:::image type="content" source="media/AEP-flow.png" alt-text="Осы мақалада көрсетілген қадамдардың процестік диаграммасы.":::

## <a name="prerequisites"></a>Алғышарттар

-   Dynamics 365 Customer Insights лицензиясы
-   Adobe Experience Platform лицензиясы
-   Adobe Campaign Standard лицензиясы
-   Azure Blob сақтау орны тіркелгісі

## <a name="campaign-overview"></a>Науқанды шолу

Customer Insights сегменттерін қалай пайдалануға болатынын жақсырақ түсіну үшін Adobe Experience Platform, жалған үлгі науқанды қарастырайық.

Сіздің компанияңыз АҚШ-тағы тұтынушыларыңызға ай сайынғы жазылымға негізделген қызметті ұсынады делік. Сізге жазылымы келесі сегіз күнде жаңартылуы керек, бірақ жазылымын әлі ұзартпаған тұтынушыларды анықтау қажет. Бұл тұтынушыларды сақтау үшін оларға Adobe Experience Platform көмегімен электрондық пошта арқылы жарнамалық ұсыныс жіберу қажет.

Бұл мысалда біз жарнамалық науқанды бір рет электрондық пошта арқылы жүргізгіміз келеді. Бұл мақалада науқанды бірнеше рет жүргізу жағдайлары қарастырылмаған.

## <a name="identify-your-target-audience"></a>Мақсатты аудиторияңызды анықтаңыз

Біздің сценарийде тұтынушылардың электрондық пошта мекенжайлары Customer Insights қызметінде қолжетімді және сегмент мүшелерін анықтау үшін олардың жарнамалық таңдаулары талданған деп есептейміз.

The [Customer Insights ішінде сіз анықтаған сегмент](segments.md) аталады **ChurnProneCustomers** және сіз осы тұтынушыларға электрондық пошта жарнамасын жіберуді жоспарлап отырсыз.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Жасалған ChurnProneCustomers сегменті бар сегменттер бетінің скриншоты.":::

Жіберілетін ұсыныс электрондық хаты аты-жөнін, тегін және тұтынушы жазылымының аяқталу күнін қамтиды. Мұнда тұтынушыларға жазылым аяқталғанға дейін оны ұзартқан кезде алатын жеңілдіктер туралы хабарланады.

## <a name="export-your-target-audience"></a>Мақсатты аудиторияңызды экспорттау

Мақсатты аудиторияны анықтау арқылы біз Customer Insights жүйесінен Azure Blob Storage тіркелгісіне экспорттауды теңшей аламыз.

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
> Экспортталатын сегменттегі жазбалар саны Adobe Campaign Standard лицензиясының рұқсат етілген шегінде екеніне көз жеткізіңіз.

Экспортталған деректер сіз жоғарыда конфигурациялаған Azure Blob сақтау контейнерінде сақталады. Контейнерде келесі қалта жолы автоматты түрде жасалады:

*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*

Мысал: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv

Экспортталған нысандарға арналған *model.json* пішімі *%ExportDestinationName%* деңгейінде болады.

Мысал: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a>Adobe Experience Platform қызметінде тәжірибе деректерінің үлгісін (XDM) анықтау

Customer Insights ішінен экспортталған деректерді пайдалану алдында Adobe Experience Platform, біз Experience Data Model схемасын анықтауымыз керек және [Нақты уақыттағы тұтынушы профилі үшін деректерді теңшеңіз](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).

[XDM үлгісі дегеніміз не екендігі туралы](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) мәлімет алып, [схема құрамының негіздері туралы](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema) түсінік алыңыз.

## <a name="import-data-into-adobe-experience-platform"></a>Деректерді Adobe Experience Platform жүйесіне импорттау

Енді бәрі орнында, біз Customer Insights ішінен дайындалған аудитория деректерін импорттауымыз керек Adobe Experience Platform.

Алдымен, [Azure Blob сақтау орнының бастапқы қосылымын жасаңыз](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).    

Бастапқы қосылымды анықтағаннан кейін, [деректер ағынын конфигурациялаңыз](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) сегмент шығысын Customer Insights ішінен импорттау үшін бұлтты сақтау пакеттік қосылымы үшін Adobe Experience Platform.

## <a name="create-an-audience-in-adobe-campaign-standard"></a>Adobe Campaign Standard қызметінде аудитория жасау

Осы науқанға электрондық хабар жіберу үшін біз Adobe Campaign Standard қызметін қолданамыз. Деректерді Adobe Experience Platform жүйесіне импорттағаннан кейін Adobe Campaign Standard жүйесінде Adobe Experience Platform қызметіндегі деректерді пайдаланып, [аудитория жасау](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) қажет.


Adobe Experience Platform қызметіндегі деректер негізінде аудиторияны анықтау үшін Adobe Campaign Standard жүйесінде [сегмент құрастырғышын пайдалану](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/audience-destinations/aep-using-segment-builder.html) жолдары туралы мәлімет алыңыз.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Adobe Campaign Standard көмегімен электрондық пошта хабарын жасау және жіберу

Электрондық пошта мазмұнын жасап, содан кейін электрондық пошта хабарын [тексеріп, жіберіңіз](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages).

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Adobe Campaign Standard жүйесінен жаңарту ұсынысы бар электрондық поштаның үлгісі.":::
