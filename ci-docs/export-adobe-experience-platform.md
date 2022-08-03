---
title: Сегменттерді келесіге экспорттау Adobe Experience Platform (алдын ала қарау)
description: ішінде Customer Insights сегменттерін пайдалану жолын үйреніңіз Adobe Experience Platform.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: fcb43e0956c6d1f0ef36b222dd2b718906364244
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: kk-KZ
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195297"
---
# <a name="export-segments-to-adobe-experience-platform-preview"></a>Сегменттерді келесіге экспорттау Adobe Experience Platform (алдын ала қарау)

Тиісті аудиторияларға бағытталған сегменттерді экспорттау Adobe Experience Platform.

:::image type="content" source="media/AEP-flow.png" alt-text="Осы мақалада көрсетілген қадамдардың процестік диаграммасы.":::

## <a name="prerequisites"></a>Алғышарттар

- Ан Adobe Experience Platform лицензия.
- Ан Adobe Campaign Standard лицензиясы.
- Ан [Azure Blob сақтау тіркелгісі](/azure/storage/blobs/create-data-lake-storage-account) аты және тіркелгі кілті. Аты мен кілтін табу үшін қараңыз [Azure порталында сақтау тіркелгісінің параметрлерін басқарыңыз](/azure/storage/common/storage-account-manage).
- Ан [Azure Blob сақтау контейнері](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

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

Біз Customer Insights жүйесінен Azure Blob сақтау тіркелгісіне экспорттауды конфигурациялаймыз.

### <a name="set-up-connection-to-azure-blob-storage"></a>Azure Blob қоймасына қосылымды орнатыңыз

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. **Әкімші** > **Қосылымдар** тармағына өтіңіз.

1. таңдаңыз **Қосылым қосыңыз** және таңдаңыз **Azure Blob сақтау орны**.

1. **Көрсетілетін аты** өрісінде қосылымға оңай танылатын атау енгізіңіз. Қосылым атауы мен түрі осы қосылымды сипаттайды. Қосылымның мақсатын түсіндіретін атауды таңдауды ұсынамыз.

1. Осы қосылымды кім пайдалана алатынын таңдаңыз. Әдепкі бойынша бұл тек әкімшілер. Қосымша ақпарат алу үшін [Салымшыларға экспорттау үшін қосылымды пайдалануға рұқсат беру](connections.md#allow-contributors-to-use-a-connection-for-exports) бөлімін қараңыз.

1. Сегментті экспорттау керек Blob сақтау орны тіркелгісі үшін **Тіркелгі атауы**, **Тіркелгі кілті** және **Контейнер** өрістерін енгізіңіз.  

   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Сақтау орны тіркелгісі конфигурациясының скриншоты.":::

1. шолу [деректердің құпиялылығы және сәйкестігі](connections.md#data-privacy-and-compliance) және таңдаңыз **Мен келісемін**.

1. Қосылымды аяқтау үшін **Сақтау** түймешігін таңдаңыз.

### <a name="configure-an-export"></a>Экспорттауды конфигурациялау

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. **Деректер** > **Экспорттау** тармағына өтіңіз.

1. таңдаңыз **Экспортты қосыңыз**.

1. **Экспорттауға арналған қосылым** өрісінде Azure Blob сақтау орны бөлімінен қосылым таңдаңыз. Егер қосылым болмаса, әкімшіге хабарласыңыз.

1. Экспорттау үшін атау енгізіңіз.

1. Экспорттау қажет сегментті таңдаңыз. Бұл мысалда ол **ChurnProneCustomers** болып табылады.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Таңдалған ChurnProneCustomers сегментімен сегмент таңдау бойынша пайдаланушы интерфейсінің скриншоты.":::

1. **Сақтау** пәрменін таңдаңыз.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

> [!NOTE]
> Экспортталатын сегменттегі жазбалар саны Adobe Campaign Standard лицензиясының рұқсат етілген шегінде екеніне көз жеткізіңіз.

Экспортталған деректер сіз конфигурациялаған Azure Blob сақтау контейнерінде сақталады. Контейнерде келесі қалта жолдары автоматты түрде жасалады:

- Бастапқы нысандар және жүйе арқылы жасалған нысандар үшін:  

  *%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*

  Мысал: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv

- Экспортталған нысандарға арналған *model.json* пішімі *%ExportDestinationName%* деңгейінде болады.

  Мысал: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a>Adobe Experience Platform қызметінде тәжірибе деректерінің үлгісін (XDM) анықтау

Customer Insights ішінен экспортталған деректерді пайдалану алдында Adobe Experience Platform, Тәжірибе деректер үлгісінің схемасын анықтаңыз және [нақты уақыттағы тұтынушы профилі үшін деректерді теңшеңіз](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).

[XDM үлгісі дегеніміз не екендігі туралы](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) мәлімет алып, [схема құрамының негіздері туралы](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema) түсінік алыңыз.

## <a name="import-data-into-adobe-experience-platform"></a>Деректерді Adobe Experience Platform жүйесіне импорттау

Customer Insights ішінен дайындалған аудитория деректерін импорттаңыз Adobe Experience Platform.

1. [Azure Blob сақтау көзі қосылымын жасаңыз](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).

1. [Деректер ағынын конфигурациялаңыз](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) Customer Insights ішінен сегмент шығысын импорттау үшін бұлтты сақтау пакеттік қосылымы үшін Adobe Experience Platform.

## <a name="create-an-audience-in-adobe-campaign-standard"></a>Adobe Campaign Standard қызметінде аудитория жасау

Осы науқанға электрондық хабар жіберу үшін біз Adobe Campaign Standard қызметін қолданамыз.

1. [Аудиторияны құру](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) жылы Adobe Науқан стандарты ішіндегі деректерді пайдалана отырып Adobe Experience Platform.

1. [Сегмент құрастырушысын пайдаланыңыз](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/audience-destinations/aep-using-segment-builder.html) жылы Adobe ішіндегі деректер негізінде аудиторияны анықтауға арналған науқан стандарты Adobe Experience Platform.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Adobe Campaign Standard көмегімен электрондық пошта хабарын жасау және жіберу

Электрондық пошта мазмұнын жасап, содан кейін электрондық пошта хабарын [тексеріп, жіберіңіз](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages).

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Adobe Campaign Standard жүйесінен жаңарту ұсынысы бар электрондық поштаның үлгісі.":::

[!INCLUDE [footer-include](includes/footer-banner.md)]
