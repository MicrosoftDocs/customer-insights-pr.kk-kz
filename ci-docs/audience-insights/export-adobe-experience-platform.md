---
title: Customer Insights деректерін Adobe Experience Platform жүйесіне экспорттау
description: Adobe Experience Platform жүйесінде аудитория мәліметтері сегменттерін пайдалану жолы туралы мәлімет алыңыз.
ms.date: 02/26/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: d1856861562be55c6d1d051050fe965560fa42f8
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596276"
---
# <a name="use-customer-insights-segments-in-adobe-experience-platform-preview"></a><span data-ttu-id="18962-103">Adobe Experience Platform жүйесіндегі Customer Insights сегменттерін пайдалану (алдын ала қарау нұсқасы)</span><span class="sxs-lookup"><span data-stu-id="18962-103">Use Customer Insights segments in Adobe Experience Platform (preview)</span></span>

<span data-ttu-id="18962-104">Dynamics 365 Customer Insights бағдарламасының аудитория туралы түсініктер пайдаланушысы ретінде сіз тиісті аудиторияға назар аудара отырып, маркетингтік науқандарды тиімді ету үшін сегменттер жасауыңыз мүмкін.</span><span class="sxs-lookup"><span data-stu-id="18962-104">As a user of audience insights for Dynamics 365 Customer Insights, you may have created segments to make your marketing campaigns more efficient by targeting relevant audiences.</span></span> <span data-ttu-id="18962-105">Adobe Experience Platform платформасында және Adobe Campaign Standard секілді бағдарламаларда аудитория туралы түсініктерден сегментті пайдалану үшін осы мақалада көрсетілген бірнеше қадамды орындауыңыз қажет.</span><span class="sxs-lookup"><span data-stu-id="18962-105">To use a segment from audience insights in Adobe Experience Platform and applications like Adobe Campaign Standard, you need to follow a few steps outlined in this article.</span></span>

:::image type="content" source="media/AEP-flow.png" alt-text="Осы мақалада көрсетілген қадамдардың процестік диаграммасы.":::

## <a name="prerequisites"></a><span data-ttu-id="18962-107">Алғышарттар</span><span class="sxs-lookup"><span data-stu-id="18962-107">Prerequisites</span></span>

-   <span data-ttu-id="18962-108">Dynamics 365 Customer Insights лицензиясы</span><span class="sxs-lookup"><span data-stu-id="18962-108">Dynamics 365 Customer Insights license</span></span>
-   <span data-ttu-id="18962-109">Adobe Experience Platform лицензиясы</span><span class="sxs-lookup"><span data-stu-id="18962-109">Adobe Experience Platform license</span></span>
-   <span data-ttu-id="18962-110">Adobe Campaign Standard лицензиясы</span><span class="sxs-lookup"><span data-stu-id="18962-110">Adobe Campaign Standard license</span></span>
-   <span data-ttu-id="18962-111">Azure Blob сақтау орны тіркелгісі</span><span class="sxs-lookup"><span data-stu-id="18962-111">Azure Blob Storage account</span></span>

## <a name="campaign-overview"></a><span data-ttu-id="18962-112">Науқанды шолу</span><span class="sxs-lookup"><span data-stu-id="18962-112">Campaign Overview</span></span>

<span data-ttu-id="18962-113">Adobe Experience Platform платформасында аудитория туралы түсініктердегі сегменттерді пайдалану жолы туралы толығырақ түсіну үшін үлгі ретінде берілген науқанды қарастырайық.</span><span class="sxs-lookup"><span data-stu-id="18962-113">To better understand how you can use segments from audience insights in Adobe Experience Platform, let’s look at a fictitious sample campaign.</span></span>

<span data-ttu-id="18962-114">Сіздің компанияңыз АҚШ-тағы тұтынушыларыңызға ай сайынғы жазылымға негізделген қызметті ұсынады делік.</span><span class="sxs-lookup"><span data-stu-id="18962-114">Let’s assume that your company offers a monthly, subscription-based service to your customers in the United States.</span></span> <span data-ttu-id="18962-115">Сізге жазылымы келесі сегіз күнде жаңартылуы керек, бірақ жазылымын әлі ұзартпаған тұтынушыларды анықтау қажет.</span><span class="sxs-lookup"><span data-stu-id="18962-115">You want to identify customers whose subscriptions are due for renewal in the next eight days but haven't yet renewed their subscription.</span></span> <span data-ttu-id="18962-116">Осы тұтынушыларды ұстап тұру үшін Adobe Experience Platform бағдарламасы көмегімен электрондық пошта арқылы оларға жарнамалық акция жіберу қажет болуы мүмкін.</span><span class="sxs-lookup"><span data-stu-id="18962-116">To keep these customers, you want to send them a promotional offer via email, using Adobe Experience Platform.</span></span>

<span data-ttu-id="18962-117">Бұл мысалда біз жарнамалық науқанды бір рет электрондық пошта арқылы жүргізгіміз келеді.</span><span class="sxs-lookup"><span data-stu-id="18962-117">In this example, we want to run the promotional email campaign once.</span></span> <span data-ttu-id="18962-118">Бұл мақалада науқанды бірнеше рет жүргізу жағдайлары қарастырылмаған.</span><span class="sxs-lookup"><span data-stu-id="18962-118">This article doesn’t cover the use-case of running the campaign more than once.</span></span>

## <a name="identify-your-target-audience"></a><span data-ttu-id="18962-119">Мақсатты аудиторияңызды анықтаңыз</span><span class="sxs-lookup"><span data-stu-id="18962-119">Identify your target audience</span></span>

<span data-ttu-id="18962-120">Біздің сценарий бойынша біз тұтынушылардың электрондық пошта мекенжайлары аудитория туралы түсініктерде қолжетімді және сегменттің мүшелерін анықтау үшін олардың жарнамалық артықшылықтары талданды деп болжанады.</span><span class="sxs-lookup"><span data-stu-id="18962-120">In our scenario, we assume that the email addresses of the customers are available in audience insights and their promotional preferences were analyzed to identify members of the segment.</span></span>

<span data-ttu-id="18962-121">[Аудитория туралы түсініктерде анықталған сегмент](segments.md) **ChurnProneCustomers** деп аталады және осы тұтынушыларға электрондық пошта арқылы жарнамалауды жіберуді жоспарлайсыз.</span><span class="sxs-lookup"><span data-stu-id="18962-121">The [segment you defined in audience insights](segments.md) is called **ChurnProneCustomers** and you plan to send these customers the email promotion.</span></span>

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Жасалған ChurnProneCustomers сегменті бар сегменттер бетінің скриншоты.":::

<span data-ttu-id="18962-123">Жіберілетін ұсыныс электрондық хаты аты-жөнін, тегін және тұтынушы жазылымының аяқталу күнін қамтиды.</span><span class="sxs-lookup"><span data-stu-id="18962-123">The offer email that you want to send out will contain the first name, last name, and the subscription end date of the customer.</span></span> <span data-ttu-id="18962-124">Мұнда тұтынушыларға жазылым аяқталғанға дейін оны ұзартқан кезде алатын жеңілдіктер туралы хабарланады.</span><span class="sxs-lookup"><span data-stu-id="18962-124">It informs the customers about the discount they’ll get if they renew their subscription before it ends.</span></span>

## <a name="export-your-target-audience"></a><span data-ttu-id="18962-125">Мақсатты аудиторияңызды экспорттау</span><span class="sxs-lookup"><span data-stu-id="18962-125">Export your target audience</span></span>

<span data-ttu-id="18962-126">Анықталған мақсатты аудитория арқылы аудитория туралы түсініктерден Azure Blob сақтау орны тіркелгісіне экспорттауды конфигурациялаймыз.</span><span class="sxs-lookup"><span data-stu-id="18962-126">With our target audience identified, we can configure the export from audience insights to an Azure Blob Storage account.</span></span>

1. <span data-ttu-id="18962-127">Аудитория мәліметтерінде **Әкімші** > **Экспорттау мақсаттары** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="18962-127">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="18962-128">**Azure Blob сақтау орны** тақтасында **Орнату** пәрменін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="18962-128">In the **Azure Blob Storage** tile, select **Set up**.</span></span>

   :::image type="content" source="media/export-azure-blob-storage-tile.png" alt-text="Azure Blob сақтау орнының конфигурация тақтасы.":::

1. <span data-ttu-id="18962-130">Осы жаңа экспорттау межелі орны үшін **Көрсетілу атауын** ұсынып, содан кейін сегмент экспортталатын Azure Blob сақтау орны тіркелгісінің **Тіркелгі атауы**, **Тіркелгі кілті** және **Контейнер** параметрлерін енгізіңіз.</span><span class="sxs-lookup"><span data-stu-id="18962-130">Provide a **Display name** for this new export destination and then enter the **Account name**, **Account key**, and **Container** of the Azure Blob Storage account where you want to export the segment to.</span></span>  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Сақтау орны тіркелгісі конфигурациясының скриншоты."::: 

   - <span data-ttu-id="18962-132">Azure Blob сақтау тіркелгісінің аты мен тіркелгі кілтін табу жөнінде толығырақ ақпарат алу үшін мына тақырыпты қараңыз: [Azure порталындағы сақтау құралының тіркелгі параметрлерін басқару](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="18962-132">To learn more about how to find the Azure Blob storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

   - <span data-ttu-id="18962-133">Контейнерді жасау жөнінде мағлұмат алу үшін мына тақырыпты қараңыз: [Контейнер жасау](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="18962-133">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="18962-134">**Келесі** пәрменін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="18962-134">Select **Next**.</span></span>

1. <span data-ttu-id="18962-135">Экспорттау қажет сегментті таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="18962-135">Choose the segment that you want to export.</span></span> <span data-ttu-id="18962-136">Бұл мысалда ол **ChurnProneCustomers** болып табылады.</span><span class="sxs-lookup"><span data-stu-id="18962-136">In this example, it’s **ChurnProneCustomers**.</span></span>

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Таңдалған ChurnProneCustomers сегментімен сегмент таңдау бойынша пайдаланушы интерфейсінің скриншоты.":::

1. <span data-ttu-id="18962-138">**Сақтау** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="18962-138">Select **Save**.</span></span>

<span data-ttu-id="18962-139">Экспорттау межелі орнын сақтағаннан кейін оны **Әкімші** > **Экспорттар** > **Менің экспорттау межелі орындарым** тармағы бойынша табуға болады.</span><span class="sxs-lookup"><span data-stu-id="18962-139">After saving the export destination, you find it on **Admin** > **Exports** > **My export destinations**.</span></span>

:::image type="content" source="media/export-destination-azure-blob-storage.png" alt-text="Экспорттаулар тізімі мен бөлектелген сегмент үлгісінің скриншоты.":::

<span data-ttu-id="18962-141">[Сегментті сұраныс бойынша экспорттауға](export-destinations.md#export-data-on-demand) болады.</span><span class="sxs-lookup"><span data-stu-id="18962-141">You can now [export the segment on demand](export-destinations.md#export-data-on-demand).</span></span> <span data-ttu-id="18962-142">Экспорттау сондай-ақ әрбір [жоспарланған жаңарту](system.md) сайын іске қосылады.</span><span class="sxs-lookup"><span data-stu-id="18962-142">The export will also run with every [scheduled refresh](system.md).</span></span>

> [!NOTE]
> <span data-ttu-id="18962-143">Экспортталған сегменттегі жазбалар санының Adobe Campaign Standard лицензиясының рұқсат етілген шегінде болуын тексеріңіз.</span><span class="sxs-lookup"><span data-stu-id="18962-143">Ensure that the number of records in the exported segment are within the allowed limit of your Adobe Campaign Standard license.</span></span>

<span data-ttu-id="18962-144">Экспортталған деректер сіз жоғарыда конфигурациялаған Azure Blob сақтау контейнерінде сақталады.</span><span class="sxs-lookup"><span data-stu-id="18962-144">Exported data is stored in the Azure Blob storage container you configured above.</span></span> <span data-ttu-id="18962-145">Контейнерде келесі қалта жолы автоматты түрде жасалады:</span><span class="sxs-lookup"><span data-stu-id="18962-145">The following folder path is automatically created in your container:</span></span>

<span data-ttu-id="18962-146">*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*</span><span class="sxs-lookup"><span data-stu-id="18962-146">*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*</span></span>

<span data-ttu-id="18962-147">Мысал: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv</span><span class="sxs-lookup"><span data-stu-id="18962-147">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv</span></span>

<span data-ttu-id="18962-148">Экспортталған нысандарға арналған *model.json* пішімі *%ExportDestinationName%* деңгейінде болады.</span><span class="sxs-lookup"><span data-stu-id="18962-148">The *model.json* for the exported entities resides at the *%ExportDestinationName%* level.</span></span>

<span data-ttu-id="18962-149">Мысал: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json</span><span class="sxs-lookup"><span data-stu-id="18962-149">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json</span></span>

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a><span data-ttu-id="18962-150">Adobe Experience Platform бағдарламасындағы Experience Data Model (XDM) үлгісін анықтау</span><span class="sxs-lookup"><span data-stu-id="18962-150">Define Experience Data Model (XDM) in Adobe Experience Platform</span></span>

<span data-ttu-id="18962-151">Аудитория туралы түсініктердегі экспортталған деректер Adobe Experience Platform шегінде пайдаланылғанға дейін Experience Data Model схемасын анықтап, [нақты уақыттағы тұтынушы профиліне арналған деректерді конфигурациялау](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials) қажет.</span><span class="sxs-lookup"><span data-stu-id="18962-151">Before the exported data from audience insights can be used within Adobe Experience Platform, we need to define the Experience Data Model schema and [configure the data for the Real-time Customer Profile](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).</span></span>

<span data-ttu-id="18962-152">[XDM үлгісі дегеніміз не екендігі туралы](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) мәлімет алып, [схема құрамының негіздері туралы](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema) түсінік алыңыз.</span><span class="sxs-lookup"><span data-stu-id="18962-152">Learn [what XDM is](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) and understand the [basics of schema composition](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).</span></span>

## <a name="import-data-into-adobe-experience-platform"></a><span data-ttu-id="18962-153">Деректерді Adobe Experience Platform бағдарламасына импорттау</span><span class="sxs-lookup"><span data-stu-id="18962-153">Import data into Adobe Experience Platform</span></span>

<span data-ttu-id="18962-154">Енді барлығы дайын болған кезде профильдер жасау үшін дайындалған аудитория деректерін аудитория туралы түсініктерден Adobe Experience Platform жүйесіне импорттауымыз қажет.</span><span class="sxs-lookup"><span data-stu-id="18962-154">Now that everything is in place, we need to import the prepared audience data from audience insights into Adobe Experience Platform.</span></span>

<span data-ttu-id="18962-155">Алдымен, [Azure Blob сақтау орнының бастапқы қосылымын жасаңыз](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).</span><span class="sxs-lookup"><span data-stu-id="18962-155">First, [create an Azure Blob Storage source connection](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).</span></span>    

<span data-ttu-id="18962-156">Бастапқы қосылымды анықтағаннан кейін сегмент шығысын аудитория туралы түсініктерден Adobe Experience Platform платформасына импорттау үшін бұлттағы сақтау орнының топтық қосылымына арналған [деректер ағынын](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) конфигурациялаңыз.</span><span class="sxs-lookup"><span data-stu-id="18962-156">After defining the source connection, [configure a dataflow](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) for a cloud storage batch connection to import the segment output from audience insights into Adobe Experience Platform.</span></span>

## <a name="create-an-audience-in-adobe-campaign-standard"></a><span data-ttu-id="18962-157">Adobe Campaign Standard жүйесінде аудиторияны жасау</span><span class="sxs-lookup"><span data-stu-id="18962-157">Create an audience in Adobe Campaign Standard</span></span>

<span data-ttu-id="18962-158">Осы науқанға электрондық пошта хатын жіберу үшін Adobe Campaign Standard бағдарламасын пайдаланамыз.</span><span class="sxs-lookup"><span data-stu-id="18962-158">To send the email for this campaign, we will use Adobe Campaign Standard.</span></span> <span data-ttu-id="18962-159">Деректерді Adobe Experience Platform бағдарламасына импорттағаннан кейін Adobe Experience Platform бағдарламасындағы деректерді пайдаланып Adobe Campaign Standard жүйесінде [аудитория жасау](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) қажет.</span><span class="sxs-lookup"><span data-stu-id="18962-159">After importing the data into Adobe Experience Platform, we need to [create an audience](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) in Adobe Campaign Standard using the data in Adobe Experience Platform.</span></span>

<span data-ttu-id="18962-160">Adobe Experience Platform жүйесіндегі деректер негізінде аудиторияны анықтау үшін Adobe Campaign Standard бағдарламасында [сегментті құрастыру құралын пайдалану](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/working-with-adobe-experience-platform/aep-using-segment-builder.html#building-a-segment) бойынша мәлімет алыңыз.</span><span class="sxs-lookup"><span data-stu-id="18962-160">Learn how to [use segment builder](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/working-with-adobe-experience-platform/aep-using-segment-builder.html#building-a-segment) in Adobe Campaign Standard to define an audience based on the data in Adobe Experience Platform.</span></span>

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a><span data-ttu-id="18962-161">Adobe Campaign Standard көмегімен электрондық пошта хабарын жасау және жіберу</span><span class="sxs-lookup"><span data-stu-id="18962-161">Create and send the email using Adobe Campaign Standard</span></span>

<span data-ttu-id="18962-162">Электрондық пошта мазмұнын жасап, содан кейін электрондық пошта хабарын [тексеріп, жіберіңіз](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages).</span><span class="sxs-lookup"><span data-stu-id="18962-162">Create the email content and then [test and send](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) your email.</span></span>

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Adobe Campaign Standard ұсынған жаңарту ұсынысы бар электрондық пошта хабарының үлгісі.":::