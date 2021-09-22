---
title: Аудитория туралы пайдалы мәліметтер мен өзара әрекеттестік туралы пайдалы мәліметтер арасындағы байланыс жасау
description: Деректерді екі жақты бөлісуді қамтамасыз ету үшін аудитория мен өзара түсіністік туралы пайдалы мәліметтер арасында белсенді байланыс жасаңыз.
ms.date: 07/22/2021
ms.service: customer-insights
ms.topic: conceptual
author: mkisel
ms.author: mkisel
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 870209a7e19fec464ec41462a02365771bd653bd
ms.sourcegitcommit: 1c396394470df8e68c2fafe3106567536ff87194
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 08/30/2021
ms.locfileid: "7461020"
---
# <a name="create-a-link-between-audience-insights-and-engagement-insights"></a>Аудитория туралы пайдалы мәліметтер мен өзара әрекеттестік туралы пайдалы мәліметтер арасындағы байланыс жасау

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Өзара әрекеттестік және аудитория туралы пайдалы мәліметтер арасындағы интеграция екі мүмкіндіктегі орталарды байланыстырады, сондай-ақ олардың арасында деректерді екі бағытта бөлісуге мүмкіндік береді.

Аудитория мәліметтеріндегі бірыңғай профильдер мен сегменттерді өзара әрекеттестік туралы пайдалы мәліметтердегі қосымша талдау опциялары үшін пайдаланыңыз. Өзара әрекеттестік мәліметтерінен жоғары іскерлік мәні бар экспорттау оқиғалары. Бұл оқиғаларды аудитория мәліметтеріндегі бірыңғай профильдерге деректер қосу үшін пайдаланыңыз.

## <a name="prerequisites"></a>Алғышарттар

- Аудитория мәліметтерінің профильдері сіз иелік ететін Azure Data Lake Storage тіркелгісінде немесе [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro.md)&ndash;басқарылатын деректер көлінде сақталуы тиіс. 

- Сізге өзара әрекеттестік мәліметтері мен аудитория мәліметтері орталарына арналған әкімші рұқсаттары қажет.

- Байланысты орталар бір географиялық аймақта болуы керек.

> [!NOTE]
> - Егер сіздегі аудитория мәліметтерінің жазылымы аудитория мәліметтерінің ішкі басқарылатын деректер көлін пайдаланатын сынақ нұсқа болып табылса, көмек алу үшін [pirequest@microsoft.com](mailto:pirequest@microsoft.com) хабарласыңыз. 
> - Егер деректерді сақтау үшін аудитория мәліметтерінің ортасы сіздің Azure Data Lake Storage пайдаланса, сақтау орны тіркелгісі үшін өзара әрекеттестік мәліметтерінің Azure қызмет негізін қосу қажет. Толық ақпарат алу үшін, [Аудитория мәліметтеріне арналған Azure қызмет негізімен Azure Data Lake Storage тіркелгісіне қосылу](../audience-insights/connect-service-principal.md) бөліміне өтіңіз. Сондай-ақ аудитория мәліметтерінің ортасында байланысты [Dataverse ортасы](../audience-insights/get-started-paid.md) болуы қажет. 

## <a name="create-an-environment-link"></a>Орта сілтемесін жасау

Өзара әрекеттестік мәліметтерінде **Әкімші** > **Орта** параметрлерін жаңарту арқылы орта сілтемесін жасауға болады.

**Аудитория туралы пайдалы мәліметтер мен өзара әрекеттестік туралы пайдалы мәліметтер арасындағы байланыс орнату үшін**

1. **Орта әкімшісі** бетінде **Сілтемелер ортасы** қойыншасын таңдаңыз.

    :::image type="content" source="media/integrate1.png" alt-text="Ортаны орнату.":::

1. Жоғарғы сол жақ бұрышта немесе экранның астында **Орнату параметрлері** опциясын таңдаңыз.

     :::image type="content" source="media/integrate2.png" alt-text="Аудитория туралы пайдалы мәліметтер ортасын таңдау.":::

1. Аудитория туралы мәліметтер ортасын таңдаңыз, содан кейін аяқтау үшін **Келесі** опциясын таңдаңыз. Енді сіз байланыстырылған орталар үшін қосымша мүмкіндіктерді таңдай аласыз.
 
## <a name="enable-audience-insights-unified-profiles-attributes-and-segments"></a>Аудитория туралы пайда мәліметтердің бірыңғай профильдерінің төлсипаттары мен сегменттерін қосу

Орталарды байланыстырғаннан кейін байланыстырылған орталар үшін қосымша мүмкіндіктерді таңдауға болады. Бұл мүмкіндіктер тұтынушылардың деректеріне интерактивті талдау жасау үшін аудитория мәліметтерінен бірыңғай профиль төлсипаттары мен сегменттерін қосады.

**Өзара әрекеттестік мәліметтеріндегі веб-деректерді талдау үшін**

1. **Орта әкімшісі** бетінде **Аудитория мәліметтеріндегі деректерді өзара әрекеттестік мәліметтерімен бөлісу** ауыстырып-қосқышын қосып, содан кейін **Келесі** опциясын таңдаңыз.

    :::image type="content" source="media/integrate4.png" alt-text="Мүмкіндіктерді таңдау.":::

1. Өзара әрекеттестік мәліметтерінде өлшемдерге айналатын бірыңғай профильдердің төлсипаттарын таңдаңыз. (Барлық төлсипаттар пайдалы өлшемдер емес. Мысалы, веб-сайт оқиғаларын талдау үшін төлсипат ретінде **Аты** немесе **Тегі** қажет болмауы мүмкін.)

    :::image type="content" source="media/integrate5.png" alt-text="Өлшемдерді реттеу.":::

   >[!NOTE]
   > Идентификаторларды көрсететін барлық аудитория мәліметтерінің профиль төлсипаттары (мысалы **идентификатор** және **балама идентификатор**) қолжетімді төлсипаттардан сүзгіленеді және өзара әрекеттестік мәліметтерінде өлшемдерге айналады.

1. Төлсипаттарды таңдауды аяқтағаннан кейін **Келесі** опциясын таңдаңыз.
1. Аудитория мәліметтері профилінің өлшемдері мен сегменттерін өзара әрекеттестік мәліметтерінде көре алатын пайдаланушыларды қосыңыз.

    :::image type="content" source="media/integrate6.png" alt-text="Тұтынушы деректеріне қатынасты басқару.":::

   > [!IMPORTANT]
   > Егер сіз бұл қадамда пайдаланушыларды нақты қоспасаңыз, деректер өзара әрекеттестік мәліметтерінде пайдаланушылардан жасырылады.

1. Таңдауды қарап шығыңыз, содан кейін **Аяқтау** опциясын таңдаңыз.

    :::image type="content" source="media/integrate7.png" alt-text="Тұтынушы деректерінің параметрлерін қарап шығыңыз.":::

## <a name="export-refined-events-to-audience-insights"></a>Нақтыланған оқиғаларды аудитория туралы пайдалы мәліметтерге экспорттау

Орталар арасында байланыс орнатқаннан кейін нақтыланған оқиғаларды өзара әрекеттестік мәліметтерінен аудитория мәліметтеріне экспорттауға болады және оларды жаңа деректер көзі ретінде қабылдауға болады. 

Қосымша ақпарат алу үшін [Өзара әрекеттестік мәліметтеріндегі веб-деректерді аудитория мәліметтерімен біріктіру](../audience-insights/integrate-engagement-insights.md) бөліміне өтіңіз.

<!--
## Share engagement insights refined events with audience insights

After you create a link between environments, a new option becomes available for you to share [refined events](refined-events.md) with audience insights.

Consider the following when creating refined events for audience insights: 

- Provide a meaningful name for the refined event. It will be used as an activity name in audience insights.
- Select at least the following properties to create an activity in audience insights: 
    - Signal.Action.Name indicates the activity details.
    - Signal.User.Id maps with the customer ID.
    - Signal.View.Uri is a web address as a basis for segments or measures.
    - Signal.Export.Id is a primary key for events.
    - Signal.Timestamp determines the date and time for the activity.

To share refined events:

1. From the engagement insights menu, select **Data** and then select the **Events** tab.
2. On the **Action** menu, select **Share as activity**.

    :::image type="content" source="media/integrate8.png" alt-text="Data shared events settings.":::

3. You can view and stop actively shared events on the **Export and Sharing** tab.
4. -- per Michael K, we need a mock here (Mukesh needs to update to reflect what happens in AUI once a user shares a refined event (i.e. no longer AUI, data wrangler needs to go discover data in the storage, the shared event is available as a DS and entity, correct?)

### Attach refined events shared as activities to unified profiles in audience insights

You can bring customer web activity data from engagement insights into audience insights. In addition to transactional, demographic, or behavioral data, you can view activities on the web in unified customer profiles. You can then use these profiles to get insights such as segments, measures, and predictions for audience activation.

Follow the steps in [data unification](../audience-insights/data-unification.md) to map, match, and merge website authentication information to unified profiles in audience insights.

You can also share refined events that are now available in audience insights, identified as data sources and entities. 

Next, you can relate event data from engagement insights as unified activities in customer profiles.

### Relate refined event data as an activity of a customer profile

After unifying the data, you can configure the activity for the customer profile. For more information, go to [Customer activities](../audience-insights/activities.md).

:::image type="content" source="media/web-event-activity.png" alt-text="Activities page with expanded Edit activity pane.":::

Next, configure the new activity by using mapping elements: 

- **Primary Key**: Signal.Export.Id, a unique ID that is available for every event record in engagement insights. This property is automatically generated.

- **Timestamp**: Signal.Timestamp in the event property.

- **Event**: Signal.Name, the event name that you want to track.

- **Web address**: Signal.View.Uri that refers to the URI of the page that created the event.

- **Details**: Signal.Action.Name to represent the information to associate with the event. The selected property in this case indicates that the event is for email promotion.

- **Activity type**: In this example, we choose the existing activity type WebLog. This selection is a useful filter option to run prediction models or create segments based on this activity type.

- **Set up relationship**: This important setting ties the activity to existing customer profiles. **Signal.User.Id** is the identifier configured in the SDK to be collected. It relates to the user ID in other data sources that are configured in audience insights. 

This example configures the relationship between Signal.User.Id and RetailCustomers:CustomerRetailId, which is the primary key that was identified in the map step of the data unification process.

After processing the activities, you can review customer records and open a customer card to see activities from engagement insights in the timeline. 

> [!TIP]
> To find a customer ID that has an engagement insights activity, go to **Entities** and preview the data for the UnifiedActivity entity. **ActivityTypeDisplay = WebLog** contains the engagement insights activity configured in the preceding example. Copy the customer ID for one of those records and search<!--note from editor: Edit okay? I couldn't quite follow this.-- > for that ID on the **Customers** page.

--> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
