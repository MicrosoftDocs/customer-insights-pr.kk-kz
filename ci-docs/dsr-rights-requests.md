---
title: GDPR бойынша деректер нысанының құқықтарына (DSR) қатысты сұраулар | Microsoft Docs
description: Dynamics 365 Customer Insights аудитория мәліметтері мүмкіндіктері үшін деректер субъектілеріне қатысты сұрауға жауап беріңіз.
ms.date: 08/11/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: e095eb4f8e194f314d7d6baf6fa6a7a319319d2a
ms.sourcegitcommit: 1946d7af0bd2ca216885bec3c5c95009996d9a28
ms.translationtype: MT
ms.contentlocale: kk-KZ
ms.lasthandoff: 02/25/2022
ms.locfileid: "8350276"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a>GDPR бойынша деректер субъектілерінің құқықтарына (DSR) қатысты сұраулар

Еуропалық Одақтың Деректерді қорғау бойынша жалпы регламенті (GDPR) 2018 жылдың 25 мамырынан бастап күшіне енді. Бұл жеке тұлғаларда олардың деректеріне қатысты айтарлықтай құқықтар береді. GDPR жеке тұлғалардың құпиялылық құқықтарын қорғауға және қамтамасыз етуге бағытталған. Microsoft корпорациясының қауіпсіздік пен сәйкестікке қатысты міндеттемелері туралы [Microsoft қауіпсіздікті басқару орталығында](https://www.microsoft.com/trust-center) қосымша ақпарат оқи аласыз.

Біз өз тұтынушыларымызға GDPR талаптарын орындауға көмектесуге дайынбыз. Ол пайдаланушы идентификаторы, телефон нөмірлері және электрондық пошта мекенжайлары секілді жеке ақпаратты қамтитын деректерді жою және экспорттау құқығын қамтиды. Әкімшілер пайдаланушылардың жеке деректерді жою немесе экспорттау туралы сұраныстарын жүзеге асыра алады.

## <a name="audience-insights"></a>Аудитория туралы пайдалы мәліметтер

### <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights-audience-insights-capability"></a>Dynamics 365 Customer Insights аудитория мәліметтері мүмкіндіктері үшін GDPR деректер субъектілерін жою сұрауларына жауап беру

Ұйымның тұтынушы деректерінен жеке деректерді "жою құқығы" Деректерді қорғау бойынша жалпы регламенттің (GDPR) негізгі қорғанысы болып табылады. Жеке деректерді жою процесі аудит журналының ақпаратын қоспағанда, барлық жеке деректерді және жүйемен жасалған журналдарды жоюды қамтиды.

#### <a name="manage-data-subject-delete-requests"></a>Деректер нысанын жою сұрауларын басқару

Аудитория мәліметтері белгілі бір тұтынушының немесе пайдаланушының жеке деректерін жою үшін мына өнімдегі тәжірибелерді ұсынады:

- **Тұтынушы деректерінің жою сұрауларын басқару**: Customer Insights ішіндегі тұтынушы деректері бастапқы сыртқы деректер көздерінен Customer Insights жүйесіне қабылданады. Барлық GDPR жою сұраулары бастапқы деректер көзінде орындалуы қажет.
- **Customer Insights пайдаланушы деректерін жою сұрауларын басқару**: Customer Insights жасаған пайдаланушыларға арналған деректер. Барлық GDPR жою сұраулары Customer Insights бағдарламасында орындалуы қажет.

##### <a name="manage-requests-to-delete-customer-data"></a>Тұтынушы деректерін жою сұрауларын басқару

Customer Insights әкімші дереккөзден жойылған тұтынушы деректерін жою үшін осы қадамдарды орындай алады:

1. Dynamics 365 Customer Insights жүйесіне кіріңіз.
2. Аудитория мәліметтерінде **Деректер** > **Деректер көздері** тармағына өтіңіз
3. Жойылған тұтынушы деректерінен тұратын тізімдегі әрбір дереккөз үшін:
   1. (...) параметрін таңдап, одан кейін **Жаңарту** параметрін таңдаңыз.
   2. **Күй** астынан деректер көзі күйін тексеріңіз. Құсбелгі жаңарту сәтті болғанын білдіреді. Ескерту үшбұрышы бірдеңе дұрыс болмағанын білдіреді. Ескерту үшбұрышы көрсетілсе, D365CI@microsoft.com торабына хабарласыңыз.

> [!div class="mx-imgBorder"]
> ![GDPR шешімін қолдану тұтынушы деректерінің сұрауларын жояды.](audience-insights/media/gdpr-data-sources.png "GDPR шешімін қолдану тұтынушы деректерінің сұрауларын жояды")

##### <a name="manage-delete-requests-for-user-data"></a>Пайдаланушы деректерін жою сұрауларын басқару

Customer Insights әкімшісі Customer Insights пайдаланушысы деректерін жою үшін осы қадамдарды орындай алады:

1. Dynamics 365 Customer Insights жүйесіне кіріңіз.
2. Аудитория мәліметтерінде **Әкімші** > **Рұқсаттар** тармағына өтіңіз.
3. Жою керек пайдаланушы құсбелгісін таңдаңыз.
4. **Жою** параметрін таңдаңыз.

### <a name="responding-to-gdpr-data-subject-export-requests"></a>GDPR деректер субъектілерін экспорттау сұрауларына жауап беру

Деректерді қорғау бойынша жалпы регламент (GDPR) бойынша сізбен серіктес құру міндеттемесінің бөлігі ретінде дайындыққа көмектесетін құжатты әзірледік. Бұл құжаттамада аудитория мәліметтерін пайдаланған кезде GDPR сәйкестігіне қолдау көрсету үшін бүгін жасауға болатын қадамдар сипатталған.

#### <a name="manage-export-and-view-requests"></a>Экспорттау және көру сұрауларын басқару

Деректерді тасымалдау құқығы деректер субъектілеріне басқа деректер контроллеріне берілуі мүмкін электрондық пішімдегі ("құрылымдалған, жиі қолданылатын, машинамен оқылатын және өзара жұмыс істейтін пішім" ретінде анықталған) жеке деректердің көшірмесін сұрауға мүмкіндік береді.

##### <a name="export-customer-data-tenant-admin"></a>Тұтынушы деректерін экспорттау (қатысушы әкімшісі)

Қатысушы әкімшісі деректерді экспорттау үшін мына қадамдарды орындай алуы мүмкін:

1. Сұрауда тұтынушының электрондық пошта мекенжайын көрсетіп, D365CI@microsoft.com мекенжайына электрондық хабар жіберіңіз. Customer Insights тобы деректерді экспорттау растауын сұрайтын тіркелген қатысушы әкімшісі электрондық пошта мекенжайына электрондық хабарды жібереді.
2. Сұралған тұтынушыға деректерді экспорттау үшін растауды мақұлдаңыз.
3. Қатысушы әкімшісінің электрондық пошта мекенжайы арқылы экспортталған деректерді алыңыз.

##### <a name="export-user-data-tenant-admin"></a>Пайдаланушы деректерін экспорттау (қатысушы әкімші)

1. Сұрауда пайдаланушының электрондық пошта мекенжайын көрсетіп, D365CI@microsoft.com мекенжайына электрондық хабар жіберіңіз. Customer Insights тобы деректерді экспорттау растауын сұрайтын тіркелген қатысушы әкімшісі электрондық пошта мекенжайына электрондық хабарды жібереді.
2. Сұралған пайдаланушыға деректерді экспорттау үшін растауды мақұлдаңыз.
3. Қатысушы әкімшісінің электрондық пошта мекенжайы арқылы экспортталған деректерді алыңыз.

## <a name="consent-management-preview"></a>Келісімді басқару (алдын ала қарау)

Келісімді басқару мүмкіндігі пайдаланушы деректерін тікелей жинамайды. Ол тек басқа қолданбаларда пайдаланушылар берген келісім деректерін импорттайды және өңдейді.

Арнайы пайдаланушылар туралы келісім деректерін жою үшін оны келісімді басқару мүмкіндігіне енгізілген деректер көздерінен жойыңыз. деректер көзі жаңартқаннан кейін жойылған деректер келісім орталығында да жойылады. Келісім нысанын пайдаланатын қолданбалар а кейін көзде жойылған деректерді де жояды [жаңарту](audience-insights/system.md#refresh-processes). Барлық басқа процестер мен қолданбалардан пайдаланушы деректерін жою үшін деректер субъектісінің сұрауына жауап бергеннен кейін деректер көздерін жылдам жаңартуды ұсынамыз.


<!-- ## Engagement insights (preview)

### Deleting and exporting event data containing end user identifiable information

The following sections describe how to delete and export event data that might contain personal data.

To delete or export data:

1. Tag event properties that contain data with personal information.
2. Delete or export data associated with specific values (for example: a specified user ID).

#### Tag and update event properties

Personal data is tagged on an event property level. First, tag the properties being considered for deletion or export.

To tag an event property as containing personal information, follow these steps:

1. Open the workspace containing the event.

1. Go to **Data** > **Events** to see the list of events in the selected workspace.
  
1. Select the event you want to tag.

1. Select **Edit properties** to open the pane listing all properties of the selected event.
     
1. Select **...** and then choose **Edit** to reach the **Update property** dialog.

   ![Edit event.](engagement-insights/media/edit-event.png "Edit event")

1. In the **Update Property** window, choose **...** in the upper right corner, and then choose the **Contains EUII** box. Choose **Update** to save your changes.

   ![Save your changes.](engagement-insights/media/update-property.png "Save your changes")

   > [!NOTE]
   > Every time the event schema changes or you create a new event, it's recommended that you evaluate the associated event properties and tag or untag them as containing personal data, if necessary.

#### Delete or export tagged event data

If all event properties have been tagged appropriately as described in the previous step, an environment admin can issue a deletion request against the tagged event data.

To manage EUII deletion or export requests

1. Go to **Admin** > **Environment** > **Settings**.

1. In the **Manage end user identifiable information (EUII)** section, select **Manage EUII**.

##### Deletion

For deletion, you can enter a list of comma-separated user IDs in the **Delete end user identifiable information (EUII)** section. These IDs will then be compared with all tagged event properties of all projects in the current environment via exact string matching. 

If a property value matches one of the provided IDs, the associated event will be permanently deleted. Due to the irreversibility of this action, you must confirm the deletion after selecting **Delete**.

##### Export

The export process is identical to the deletion process when it comes to defining event property values in the **Export end user identifiable information (EUII)** section. Additionally, you'll need to provide an **Azure blob storage URL** to specify the export destination. The Azure Blob URL must include a [Shared Access Signature (SAS)](/azure/storage/common/storage-sas-overview).

After selecting **Export**, all events of the current team that contain matching tagged properties will be exported in CSV format to the export destination.

### Good practices

* Try to avoid sending any events that contain personal data.
* If you need to send events containing EUII data, limit the number of events and event properties that contain EUII data. Ideally, limit yourself to one such event.
* Make sure that as few people as possible have access to the sent personal data.
* For events containing personal data, make sure that you set one property to emit a unique identifier that can easily be linked to a specific user (for example, a user ID). This makes it easier to segregate data and to export or delete the right data.
* Only tag one property per event as containing personal data. Ideally one that only contains a unique identifier.
* Do not tag properties containing verbose values (for example, an entire request body). Engagement insights capability uses exact string matching when deciding which events to delete or export. -->

[!INCLUDE[footer-include](includes/footer-banner.md)]