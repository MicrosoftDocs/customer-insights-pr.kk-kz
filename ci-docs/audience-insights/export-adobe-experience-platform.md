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
# <a name="use-customer-insights-segments-in-adobe-experience-platform-preview"></a><span data-ttu-id="23051-103">Adobe Experience Platform жүйесіндегі Customer Insights сегменттерін пайдалану (алдын ала қарау нұсқасы)</span><span class="sxs-lookup"><span data-stu-id="23051-103">Use Customer Insights segments in Adobe Experience Platform (preview)</span></span>

<span data-ttu-id="23051-104">Dynamics 365 Customer Insights бағдарламасындағы аудитория туралы түсініктердің пайдаланушысы ретінде сіз тиісті аудиторияларға бағытталу арқылы маркетинг науқандарын тиімдірек ету үшін сегменттер жасаған болуыңыз мүмкін.</span><span class="sxs-lookup"><span data-stu-id="23051-104">As a user of audience insights in Dynamics 365 Customer Insights, you may have created segments to make your marketing campaigns more efficient by targeting relevant audiences.</span></span> <span data-ttu-id="23051-105">Adobe Experience Platform платформасында және Adobe Campaign Standard секілді бағдарламаларда аудитория туралы түсініктерден сегментті пайдалану үшін осы мақалада көрсетілген бірнеше қадамды орындауыңыз қажет.</span><span class="sxs-lookup"><span data-stu-id="23051-105">To use a segment from audience insights in Adobe Experience Platform and applications like Adobe Campaign Standard, you need to follow a few steps outlined in this article.</span></span>

:::image type="content" source="media/AEP-flow.png" alt-text="Осы мақалада көрсетілген қадамдардың процестік диаграммасы.":::

## <a name="prerequisites"></a><span data-ttu-id="23051-107">Алғышарттар</span><span class="sxs-lookup"><span data-stu-id="23051-107">Prerequisites</span></span>

-   <span data-ttu-id="23051-108">Dynamics 365 Customer Insights лицензиясы</span><span class="sxs-lookup"><span data-stu-id="23051-108">Dynamics 365 Customer Insights license</span></span>
-   <span data-ttu-id="23051-109">Adobe Experience Platform лицензиясы</span><span class="sxs-lookup"><span data-stu-id="23051-109">Adobe Experience Platform license</span></span>
-   <span data-ttu-id="23051-110">Adobe Campaign Standard лицензиясы</span><span class="sxs-lookup"><span data-stu-id="23051-110">Adobe Campaign Standard license</span></span>
-   <span data-ttu-id="23051-111">Azure Blob сақтау орны тіркелгісі</span><span class="sxs-lookup"><span data-stu-id="23051-111">Azure Blob Storage account</span></span>

## <a name="campaign-overview"></a><span data-ttu-id="23051-112">Науқанды шолу</span><span class="sxs-lookup"><span data-stu-id="23051-112">Campaign Overview</span></span>

<span data-ttu-id="23051-113">Adobe Experience Platform платформасында аудитория туралы түсініктердегі сегменттерді пайдалану жолы туралы толығырақ түсіну үшін үлгі ретінде берілген науқанды қарастырайық.</span><span class="sxs-lookup"><span data-stu-id="23051-113">To better understand how you can use segments from audience insights in Adobe Experience Platform, let’s look at a fictitious sample campaign.</span></span>

<span data-ttu-id="23051-114">Сіздің компанияңыз АҚШ-тағы тұтынушыларыңызға ай сайынғы жазылымға негізделген қызметті ұсынады делік.</span><span class="sxs-lookup"><span data-stu-id="23051-114">Let’s assume that your company offers a monthly, subscription-based service to your customers in the United States.</span></span> <span data-ttu-id="23051-115">Сізге жазылымы келесі сегіз күнде жаңартылуы керек, бірақ жазылымын әлі ұзартпаған тұтынушыларды анықтау қажет.</span><span class="sxs-lookup"><span data-stu-id="23051-115">You want to identify customers whose subscriptions are due for renewal in the next eight days but haven't yet renewed their subscription.</span></span> <span data-ttu-id="23051-116">Осы тұтынушыларды ұстап тұру үшін Adobe Experience Platform бағдарламасы көмегімен электрондық пошта арқылы оларға жарнамалық акция жіберу қажет болуы мүмкін.</span><span class="sxs-lookup"><span data-stu-id="23051-116">To keep these customers, you want to send them a promotional offer via email, using Adobe Experience Platform.</span></span>

<span data-ttu-id="23051-117">Бұл мысалда біз жарнамалық науқанды бір рет электрондық пошта арқылы жүргізгіміз келеді.</span><span class="sxs-lookup"><span data-stu-id="23051-117">In this example, we want to run the promotional email campaign once.</span></span> <span data-ttu-id="23051-118">Бұл мақалада науқанды бірнеше рет жүргізу жағдайлары қарастырылмаған.</span><span class="sxs-lookup"><span data-stu-id="23051-118">This article doesn’t cover the use-case of running the campaign more than once.</span></span>

## <a name="identify-your-target-audience"></a><span data-ttu-id="23051-119">Мақсатты аудиторияңызды анықтаңыз</span><span class="sxs-lookup"><span data-stu-id="23051-119">Identify your target audience</span></span>

<span data-ttu-id="23051-120">Біздің сценарий бойынша біз тұтынушылардың электрондық пошта мекенжайлары аудитория туралы түсініктерде қолжетімді және сегменттің мүшелерін анықтау үшін олардың жарнамалық артықшылықтары талданды деп болжанады.</span><span class="sxs-lookup"><span data-stu-id="23051-120">In our scenario, we assume that the email addresses of the customers are available in audience insights and their promotional preferences were analyzed to identify members of the segment.</span></span>

<span data-ttu-id="23051-121">[Аудитория туралы түсініктерде анықталған сегмент](segments.md) **ChurnProneCustomers** деп аталады және осы тұтынушыларға электрондық пошта арқылы жарнамалауды жіберуді жоспарлайсыз.</span><span class="sxs-lookup"><span data-stu-id="23051-121">The [segment you defined in audience insights](segments.md) is called **ChurnProneCustomers** and you plan to send these customers the email promotion.</span></span>

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Жасалған ChurnProneCustomers сегменті бар сегменттер бетінің скриншоты.":::

<span data-ttu-id="23051-123">Жіберілетін ұсыныс электрондық хаты аты-жөнін, тегін және тұтынушы жазылымының аяқталу күнін қамтиды.</span><span class="sxs-lookup"><span data-stu-id="23051-123">The offer email that you want to send out will contain the first name, last name, and the subscription end date of the customer.</span></span> <span data-ttu-id="23051-124">Мұнда тұтынушыларға жазылым аяқталғанға дейін оны ұзартқан кезде алатын жеңілдіктер туралы хабарланады.</span><span class="sxs-lookup"><span data-stu-id="23051-124">It informs the customers about the discount they’ll get if they renew their subscription before it ends.</span></span>

## <a name="export-your-target-audience"></a><span data-ttu-id="23051-125">Мақсатты аудиторияңызды экспорттау</span><span class="sxs-lookup"><span data-stu-id="23051-125">Export your target audience</span></span>

<span data-ttu-id="23051-126">Анықталған мақсатты аудитория арқылы аудитория туралы түсініктерден Azure Blob сақтау орны тіркелгісіне экспорттауды конфигурациялаймыз.</span><span class="sxs-lookup"><span data-stu-id="23051-126">With our target audience identified, we can configure the export from audience insights to an Azure Blob Storage account.</span></span>

### <a name="configure-a-connection"></a><span data-ttu-id="23051-127">Қосылымды конфигурациялау</span><span class="sxs-lookup"><span data-stu-id="23051-127">Configure a connection</span></span>

1. <span data-ttu-id="23051-128">**Әкімші** > **Қосылымдар** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="23051-128">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="23051-129">**Қосылым қосу** түймешігін таңдаңыз және қосылымды конфигурациялау үшін **Azure Blob Storage** параметрін таңдаңыз немесе **Azure Blob Storage** тақтасында **Орнату** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="23051-129">Select **Add connection** and choose **Azure Blob Storage** or select **Set up** in the **Azure Blob Storage** tile to configure the connection.</span></span>

   :::image type="content" source="media/export-azure-blob-storage-tile.png" alt-text="Azure Blob сақтау орнының конфигурация тақтасы."::: 

1. <span data-ttu-id="23051-131">**Көрсетілетін аты** өрісінде қосылымға оңай танылатын атау енгізіңіз.</span><span class="sxs-lookup"><span data-stu-id="23051-131">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="23051-132">Қосылым атауы мен түрі осы қосылымды сипаттайды.</span><span class="sxs-lookup"><span data-stu-id="23051-132">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="23051-133">Қосылымның мақсатын түсіндіретін атауды таңдауды ұсынамыз.</span><span class="sxs-lookup"><span data-stu-id="23051-133">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="23051-134">Осы қосылымды кім пайдалана алатынын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="23051-134">Choose who can use this connection.</span></span> <span data-ttu-id="23051-135">Егер сіз ешқандай әрекет жасамасаңыз, әдепкі бойынша Әкімшілер болады.</span><span class="sxs-lookup"><span data-stu-id="23051-135">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="23051-136">Қосымша ақпарат алу үшін [Салымшыларға экспорттау үшін қосылымды пайдалануға рұқсат беру](connections.md#allow-contributors-to-use-a-connection-for-exports) бөлімін қараңыз.</span><span class="sxs-lookup"><span data-stu-id="23051-136">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="23051-137">Сегментті экспорттау керек Blob сақтау орны тіркелгісі үшін **Тіркелгі атауы**, **Тіркелгі кілті** және **Контейнер** өрістерін енгізіңіз.</span><span class="sxs-lookup"><span data-stu-id="23051-137">Enter **Account name**, **Account key**, and **Container** for your Blob Storage account where you want to export the segment to.</span></span>  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Сақтау орны тіркелгісі конфигурациясының скриншоты."::: 
   
    - <span data-ttu-id="23051-139">Blob сақтау орнының тіркелгі атауын және тіркелгі кілтін табу жолы туралы қосымша ақпарат алу үшін [Azure порталындағы сақтау орны тіркелгісінің параметрлерін басқару](/azure/storage/common/storage-account-manage) бөлімін қараңыз.</span><span class="sxs-lookup"><span data-stu-id="23051-139">To learn more about how to find the Blob Storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>
    - <span data-ttu-id="23051-140">Контейнерді жасау жөнінде мағлұмат алу үшін мына тақырыпты қараңыз: [Контейнер жасау](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="23051-140">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="23051-141">Қосылымды аяқтау үшін **Сақтау** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="23051-141">Select **Save** to complete the connection.</span></span> 

### <a name="configure-an-export"></a><span data-ttu-id="23051-142">Экспорттауды конфигурациялау</span><span class="sxs-lookup"><span data-stu-id="23051-142">Configure an export</span></span>

<span data-ttu-id="23051-143">Егер сіз осы түрдегі қосылымға қатынаса алсаңыз, сіз бұл экспорттауды конфигурациялай аласыз.</span><span class="sxs-lookup"><span data-stu-id="23051-143">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="23051-144">Қосымша ақпарат алу үшін [Экспорттауды конфигурациялау үшін қажет рұқсаттар](export-destinations.md#set-up-a-new-export) бөлімін қараңыз.</span><span class="sxs-lookup"><span data-stu-id="23051-144">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="23051-145">**Деректер** > **Экспорттау** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="23051-145">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="23051-146">Жаңа экспорттау жасау үшін **Экспорттау қосу** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="23051-146">To create a new export, select **Add export**.</span></span>

1. <span data-ttu-id="23051-147">**Экспорттауға арналған қосылым** өрісінде Azure Blob сақтау орны бөлімінен қосылым таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="23051-147">In the **Connection for export** field, choose a connection from the Azure Blob Storage section.</span></span> <span data-ttu-id="23051-148">Егер сіз бұл бөлімнің атауын көрмесеңіз, онда сіз үшін осы түрдегі қосылымдар қолжетімді емес.</span><span class="sxs-lookup"><span data-stu-id="23051-148">If you don't see this section name, then no connections of this type are available to you.</span></span>

1. <span data-ttu-id="23051-149">Экспорттау қажет сегментті таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="23051-149">Choose the segment that you want to export.</span></span> <span data-ttu-id="23051-150">Бұл мысалда ол **ChurnProneCustomers** болып табылады.</span><span class="sxs-lookup"><span data-stu-id="23051-150">In this example, it’s **ChurnProneCustomers**.</span></span>

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Таңдалған ChurnProneCustomers сегментімен сегмент таңдау бойынша пайдаланушы интерфейсінің скриншоты.":::

1. <span data-ttu-id="23051-152">**Сақтау** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="23051-152">Select **Save**.</span></span>

<span data-ttu-id="23051-153">Экспорттау мақсатты орнын сақтағаннан кейін оны **Деректер** > **Экспорттаулар** тармағынан таба аласыз.</span><span class="sxs-lookup"><span data-stu-id="23051-153">After saving the export destination, you find it on **Data** > **Exports**.</span></span>

<span data-ttu-id="23051-154">[Сегментті сұраныс бойынша экспорттауға](export-destinations.md#run-exports-on-demand) болады.</span><span class="sxs-lookup"><span data-stu-id="23051-154">You can now [export the segment on demand](export-destinations.md#run-exports-on-demand).</span></span> <span data-ttu-id="23051-155">Экспорттау сондай-ақ әрбір [жоспарланған жаңарту](system.md) сайын іске қосылады.</span><span class="sxs-lookup"><span data-stu-id="23051-155">The export will also run with every [scheduled refresh](system.md).</span></span>

> [!NOTE]
> <span data-ttu-id="23051-156">Экспортталған сегменттегі жазбалар санының Adobe Campaign Standard лицензиясының рұқсат етілген шегінде болуын тексеріңіз.</span><span class="sxs-lookup"><span data-stu-id="23051-156">Ensure that the number of records in the exported segment are within the allowed limit of your Adobe Campaign Standard license.</span></span>

<span data-ttu-id="23051-157">Экспортталған деректер сіз жоғарыда конфигурациялаған Azure Blob сақтау контейнерінде сақталады.</span><span class="sxs-lookup"><span data-stu-id="23051-157">Exported data is stored in the Azure Blob Storage container you configured above.</span></span> <span data-ttu-id="23051-158">Контейнерде келесі қалта жолы автоматты түрде жасалады:</span><span class="sxs-lookup"><span data-stu-id="23051-158">The following folder path is automatically created in your container:</span></span>

<span data-ttu-id="23051-159">*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*</span><span class="sxs-lookup"><span data-stu-id="23051-159">*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*</span></span>

<span data-ttu-id="23051-160">Мысал: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv</span><span class="sxs-lookup"><span data-stu-id="23051-160">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv</span></span>

<span data-ttu-id="23051-161">Экспортталған нысандарға арналған *model.json* пішімі *%ExportDestinationName%* деңгейінде болады.</span><span class="sxs-lookup"><span data-stu-id="23051-161">The *model.json* for the exported entities resides at the *%ExportDestinationName%* level.</span></span>

<span data-ttu-id="23051-162">Мысал: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json</span><span class="sxs-lookup"><span data-stu-id="23051-162">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json</span></span>

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a><span data-ttu-id="23051-163">Adobe Experience Platform бағдарламасындағы Experience Data Model (XDM) үлгісін анықтау</span><span class="sxs-lookup"><span data-stu-id="23051-163">Define Experience Data Model (XDM) in Adobe Experience Platform</span></span>

<span data-ttu-id="23051-164">Аудитория туралы түсініктердегі экспортталған деректер Adobe Experience Platform шегінде пайдаланылғанға дейін Experience Data Model схемасын анықтап, [нақты уақыттағы тұтынушы профиліне арналған деректерді конфигурациялау](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials) қажет.</span><span class="sxs-lookup"><span data-stu-id="23051-164">Before the exported data from audience insights can be used within Adobe Experience Platform, we need to define the Experience Data Model schema and [configure the data for the Real-time Customer Profile](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).</span></span>

<span data-ttu-id="23051-165">[XDM үлгісі дегеніміз не екендігі туралы](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) мәлімет алып, [схема құрамының негіздері туралы](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema) түсінік алыңыз.</span><span class="sxs-lookup"><span data-stu-id="23051-165">Learn [what XDM is](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) and understand the [basics of schema composition](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).</span></span>

## <a name="import-data-into-adobe-experience-platform"></a><span data-ttu-id="23051-166">Деректерді Adobe Experience Platform бағдарламасына импорттау</span><span class="sxs-lookup"><span data-stu-id="23051-166">Import data into Adobe Experience Platform</span></span>

<span data-ttu-id="23051-167">Енді барлығы дайын болған кезде профильдер жасау үшін дайындалған аудитория деректерін аудитория туралы түсініктерден Adobe Experience Platform жүйесіне импорттауымыз қажет.</span><span class="sxs-lookup"><span data-stu-id="23051-167">Now that everything is in place, we need to import the prepared audience data from audience insights into Adobe Experience Platform.</span></span>

<span data-ttu-id="23051-168">Алдымен, [Azure Blob сақтау орнының бастапқы қосылымын жасаңыз](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).</span><span class="sxs-lookup"><span data-stu-id="23051-168">First, [create an Azure Blob Storage source connection](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).</span></span>    

<span data-ttu-id="23051-169">Бастапқы қосылымды анықтағаннан кейін сегмент шығысын аудитория туралы түсініктерден Adobe Experience Platform платформасына импорттау үшін бұлттағы сақтау орнының топтық қосылымына арналған [деректер ағынын](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) конфигурациялаңыз.</span><span class="sxs-lookup"><span data-stu-id="23051-169">After defining the source connection, [configure a dataflow](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) for a cloud storage batch connection to import the segment output from audience insights into Adobe Experience Platform.</span></span>

## <a name="create-an-audience-in-adobe-campaign-standard"></a><span data-ttu-id="23051-170">Adobe Campaign Standard жүйесінде аудиторияны жасау</span><span class="sxs-lookup"><span data-stu-id="23051-170">Create an audience in Adobe Campaign Standard</span></span>

<span data-ttu-id="23051-171">Осы науқанға электрондық хабар жіберу үшін біз Adobe Campaign Standard қызметін қолданамыз.</span><span class="sxs-lookup"><span data-stu-id="23051-171">To send the email for this campaign, we'll use Adobe Campaign Standard.</span></span> <span data-ttu-id="23051-172">Деректерді Adobe Experience Platform бағдарламасына импорттағаннан кейін Adobe Experience Platform бағдарламасындағы деректерді пайдаланып Adobe Campaign Standard жүйесінде [аудитория жасау](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) қажет.</span><span class="sxs-lookup"><span data-stu-id="23051-172">After importing the data into Adobe Experience Platform, we need to [create an audience](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) in Adobe Campaign Standard using the data in Adobe Experience Platform.</span></span>


<span data-ttu-id="23051-173">Adobe Experience Platform жүйесіндегі деректер негізінде аудиторияны анықтау үшін Adobe Campaign Standard бағдарламасында [сегментті құрастыру құралын пайдалану](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/audience-destinations/aep-using-segment-builder.html) бойынша мәлімет алыңыз.</span><span class="sxs-lookup"><span data-stu-id="23051-173">Learn how to [use segment builder](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/audience-destinations/aep-using-segment-builder.html) in Adobe Campaign Standard to define an audience based on the data in Adobe Experience Platform.</span></span>

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a><span data-ttu-id="23051-174">Adobe Campaign Standard көмегімен электрондық пошта хабарын жасау және жіберу</span><span class="sxs-lookup"><span data-stu-id="23051-174">Create and send the email using Adobe Campaign Standard</span></span>

<span data-ttu-id="23051-175">Электрондық пошта мазмұнын жасап, содан кейін электрондық пошта хабарын [тексеріп, жіберіңіз](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages).</span><span class="sxs-lookup"><span data-stu-id="23051-175">Create the email content and then [test and send](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) your email.</span></span>

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Adobe Campaign Standard ұсынған жаңарту ұсынысы бар электрондық пошта хабарының үлгісі.":::
