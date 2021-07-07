---
title: Customer Insights деректерін Adobe Campaign Standard бағдарламасына экспорттау
description: Adobe Campaign Standard бағдарламасында аудитория мәліметтері сегменттерін пайдалану жолы туралы мәлімет алыңыз.
ms.date: 03/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: 917ab9559416f3ee0ffd66e471e590e8da3faffc
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305393"
---
# <a name="use-customer-insights-segments-in-adobe-campaign-standard-preview"></a><span data-ttu-id="cd241-103">Adobe Campaign Standard бағдарламасында Customer Insights сегменттерін пайдалану (алдын ала қарау нұсқасы)</span><span class="sxs-lookup"><span data-stu-id="cd241-103">Use Customer Insights segments in Adobe Campaign Standard (preview)</span></span>

<span data-ttu-id="cd241-104">Dynamics 365 Customer Insights бағдарламасындағы аудитория туралы түсініктердің пайдаланушысы ретінде сіз тиісті аудиторияларға бағытталу арқылы маркетинг науқандарын тиімдірек ету үшін сегменттер жасаған болуыңыз мүмкін.</span><span class="sxs-lookup"><span data-stu-id="cd241-104">As a user of audience insights in Dynamics 365 Customer Insights, you may have created segments to make your marketing campaigns more efficient by targeting relevant audiences.</span></span> <span data-ttu-id="cd241-105">Adobe Experience Platform платформасында және Adobe Campaign Standard секілді бағдарламаларда аудитория туралы түсініктерден сегментті пайдалану үшін осы мақалада көрсетілген бірнеше қадамды орындауыңыз қажет.</span><span class="sxs-lookup"><span data-stu-id="cd241-105">To use a segment from audience insights in Adobe Experience Platform and applications like Adobe Campaign Standard, you need to follow a few steps outlined in this article.</span></span>

:::image type="content" source="media/ACS-flow.png" alt-text="Осы мақалада көрсетілген қадамдардың процестік диаграммасы.":::

## <a name="prerequisites"></a><span data-ttu-id="cd241-107">Алғышарттар</span><span class="sxs-lookup"><span data-stu-id="cd241-107">Prerequisites</span></span>

-   <span data-ttu-id="cd241-108">Dynamics 365 Customer Insights лицензиясы</span><span class="sxs-lookup"><span data-stu-id="cd241-108">Dynamics 365 Customer Insights license</span></span>
-   <span data-ttu-id="cd241-109">Adobe Campaign Standard лицензиясы</span><span class="sxs-lookup"><span data-stu-id="cd241-109">Adobe Campaign Standard license</span></span>
-   <span data-ttu-id="cd241-110">Azure Blob сақтау орны тіркелгісі</span><span class="sxs-lookup"><span data-stu-id="cd241-110">Azure Blob Storage account</span></span>

## <a name="campaign-overview"></a><span data-ttu-id="cd241-111">Науқанға шолу</span><span class="sxs-lookup"><span data-stu-id="cd241-111">Campaign overview</span></span>

<span data-ttu-id="cd241-112">Adobe Experience Platform платформасында аудитория туралы түсініктердегі сегменттерді пайдалану жолы туралы толығырақ түсіну үшін үлгі ретінде берілген науқанды қарастырайық.</span><span class="sxs-lookup"><span data-stu-id="cd241-112">To better understand how you can use segments from audience insights in Adobe Experience Platform, let’s look at a fictitious sample campaign.</span></span>

<span data-ttu-id="cd241-113">Сіздің компанияңыз АҚШ-тағы тұтынушыларыңызға ай сайынғы жазылымға негізделген қызметті ұсынады делік.</span><span class="sxs-lookup"><span data-stu-id="cd241-113">Let’s assume that your company offers a monthly, subscription-based service to your customers in the United States.</span></span> <span data-ttu-id="cd241-114">Сізге жазылымы келесі сегіз күнде жаңартылуы керек, бірақ жазылымын әлі ұзартпаған тұтынушыларды анықтау қажет.</span><span class="sxs-lookup"><span data-stu-id="cd241-114">You want to identify customers whose subscriptions are due for renewal in the next eight days but haven't yet renewed their subscription.</span></span> <span data-ttu-id="cd241-115">Осы тұтынушыларды ұстап тұру үшін Adobe Campaign Standard бағдарламасы көмегімен электрондық пошта арқылы оларға жарнамалық акция жіберу қажет болуы мүмкін.</span><span class="sxs-lookup"><span data-stu-id="cd241-115">To keep these customers, you want to send them a promotional offer via email, using Adobe Campaign Standard.</span></span>

<span data-ttu-id="cd241-116">Бұл мысалда біз жарнамалық науқанды бір рет электрондық пошта арқылы жүргізгіміз келеді.</span><span class="sxs-lookup"><span data-stu-id="cd241-116">In this example, we want to run the promotional email campaign once.</span></span> <span data-ttu-id="cd241-117">Бұл мақалада науқанды бірнеше рет жүргізу жағдайлары қарастырылмаған.</span><span class="sxs-lookup"><span data-stu-id="cd241-117">This article doesn’t cover the use-case of running the campaign more than once.</span></span> <span data-ttu-id="cd241-118">Дегенмен, аудитория мәліметтері мен Adobe Campaign Standard бағдарламасы қайталанатын науқандық сценарий үшін жұмыс істеуге конфигурациялануы мүмкін.</span><span class="sxs-lookup"><span data-stu-id="cd241-118">However, audience insights and Adobe Campaign Standard can be configured to work for a recurring campaign scenario too.</span></span>

## <a name="identify-your-target-audience"></a><span data-ttu-id="cd241-119">Мақсатты аудиторияңызды анықтаңыз</span><span class="sxs-lookup"><span data-stu-id="cd241-119">Identify your target audience</span></span>

<span data-ttu-id="cd241-120">Біздің сценарий бойынша біз тұтынушылардың электрондық пошта мекенжайлары аудитория туралы түсініктерде қолжетімді және сегменттің мүшелерін анықтау үшін олардың жарнамалық артықшылықтары талданды деп болжанады.</span><span class="sxs-lookup"><span data-stu-id="cd241-120">In our scenario, we assume that the email addresses of the customers are available in audience insights and their promotional preferences were analyzed to identify members of the segment.</span></span>

<span data-ttu-id="cd241-121">[Аудитория туралы түсініктерде анықталған сегмент](segments.md) **ChurnProneCustomers** деп аталады және осы тұтынушыларға электрондық пошта арқылы жарнамалауды жіберуді жоспарлайсыз.</span><span class="sxs-lookup"><span data-stu-id="cd241-121">The [segment you defined in audience insights](segments.md) is called **ChurnProneCustomers** and you plan to send these customers the email promotion.</span></span>

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Жасалған ChurnProneCustomers сегменті бар сегменттер бетінің скриншоты.":::

<span data-ttu-id="cd241-123">Жіберілетін ұсыныс электрондық хаты аты-жөнін, тегін және тұтынушы жазылымының аяқталу күнін қамтиды.</span><span class="sxs-lookup"><span data-stu-id="cd241-123">The offer email that you want to send out will contain the first name, last name, and the subscription end date of the customer.</span></span> <span data-ttu-id="cd241-124">Мұнда тұтынушыларға жазылым аяқталғанға дейін оны ұзартқан кезде алатын жеңілдіктер туралы хабарланады.</span><span class="sxs-lookup"><span data-stu-id="cd241-124">It informs the customers about the discount they’ll get if they renew their subscription before it ends.</span></span>

## <a name="export-your-target-audience"></a><span data-ttu-id="cd241-125">Мақсатты аудиторияңызды экспорттау</span><span class="sxs-lookup"><span data-stu-id="cd241-125">Export your target audience</span></span>

### <a name="configure-a-connection"></a><span data-ttu-id="cd241-126">Қосылымды конфигурациялау</span><span class="sxs-lookup"><span data-stu-id="cd241-126">Configure a connection</span></span>

<span data-ttu-id="cd241-127">Анықталған мақсатты аудитория арқылы аудитория туралы түсініктерден Azure Blob сақтау орны тіркелгісіне экспорттауды конфигурациялаймыз.</span><span class="sxs-lookup"><span data-stu-id="cd241-127">With our target audience identified, we can configure the export from audience insights to an Azure Blob Storage account.</span></span>

1. <span data-ttu-id="cd241-128">Audience insights бағдарламасында **Әкімші** > **Қосылымдар** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="cd241-128">In audience insights, go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="cd241-129">**Қосылым қосу** түймешігін таңдаңыз және қосылымды конфигурациялау үшін **Adobe Campaign** параметрін таңдаңыз немесе **Adobe Campaign** тақтасында **Орнату** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="cd241-129">Select **Add connection** and choose **Adobe Campaign** to configure the connection or select **Set up** in the **Adobe Campaign** tile.</span></span>

   :::image type="content" source="media/adobe-campaign-standard-tile.png" alt-text="Adobe Campaign Standard бағдарламасының конфигурация тақтасы.":::

1. <span data-ttu-id="cd241-131">**Көрсетілетін аты** өрісінде қосылымға оңай танылатын атау енгізіңіз.</span><span class="sxs-lookup"><span data-stu-id="cd241-131">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="cd241-132">Қосылым атауы мен түрі осы қосылымды сипаттайды.</span><span class="sxs-lookup"><span data-stu-id="cd241-132">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="cd241-133">Қосылымның мақсатын түсіндіретін атауды таңдауды ұсынамыз.</span><span class="sxs-lookup"><span data-stu-id="cd241-133">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="cd241-134">Осы қосылымды кім пайдалана алатынын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="cd241-134">Choose who can use this connection.</span></span> <span data-ttu-id="cd241-135">Егер сіз ешқандай әрекет жасамасаңыз, әдепкі бойынша Әкімшілер болады.</span><span class="sxs-lookup"><span data-stu-id="cd241-135">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="cd241-136">Қосымша ақпарат алу үшін [Экспорттауды конфигурациялау үшін қажет рұқсаттар](export-destinations.md#set-up-a-new-export) бөлімін қараңыз.</span><span class="sxs-lookup"><span data-stu-id="cd241-136">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="cd241-137">Сегментті экспорттау керек Azure Blob сақтау тіркелгісінің **Тіркелгі атауы**, **Тіркелгі кілті** және **Контейнер** өрістерін енгізіңіз.</span><span class="sxs-lookup"><span data-stu-id="cd241-137">Enter the **Account name**, **Account key**, and **Container** of the Azure Blob Storage account where you want to export the segment to.</span></span>  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Сақтау орны тіркелгісі конфигурациясының скриншоты."::: 

   - <span data-ttu-id="cd241-139">Azure екілік нысан сақтау тіркелгісінің аты мен тіркелгі кілтін табу жөнінде қосымша ақпарат алу үшін [Azure порталындағы сақтау орны тіркелгі параметрлерін басқару](/azure/storage/common/storage-account-manage) бөлімін қараңыз.</span><span class="sxs-lookup"><span data-stu-id="cd241-139">To learn more about how to find the Azure Blob Storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

   - <span data-ttu-id="cd241-140">Контейнерді жасау жөнінде мағлұмат алу үшін мына тақырыпты қараңыз: [Контейнер жасау](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="cd241-140">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="cd241-141">Қосылымды аяқтау үшін **Сақтау** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="cd241-141">Select **Save** to complete the connection.</span></span>

### <a name="configure-an-export"></a><span data-ttu-id="cd241-142">Экспорттауды конфигурациялау</span><span class="sxs-lookup"><span data-stu-id="cd241-142">Configure an export</span></span>

<span data-ttu-id="cd241-143">Егер сіз осы түрдегі қосылымға қатынаса алсаңыз, сіз бұл экспорттауды конфигурациялай аласыз.</span><span class="sxs-lookup"><span data-stu-id="cd241-143">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="cd241-144">Қосымша ақпарат алу үшін [Экспорттауды конфигурациялау үшін қажет рұқсаттар](export-destinations.md#set-up-a-new-export) бөлімін қараңыз.</span><span class="sxs-lookup"><span data-stu-id="cd241-144">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="cd241-145">**Деректер** > **Экспорттау** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="cd241-145">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="cd241-146">Жаңа экспорттау жасау үшін **Экспорттау қосу** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="cd241-146">To create a new export, select **Add export**.</span></span>

1. <span data-ttu-id="cd241-147">**Экспорттауға арналған қосылым** өрісінде Adobe Campaign бөлімінен қосылым таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="cd241-147">In the **Connection for export** field, choose a connection from the Adobe Campaign section.</span></span> <span data-ttu-id="cd241-148">Егер сіз бұл бөлімнің атауын көрмесеңіз, онда сіз үшін осы түрдегі қосылымдар қолжетімді емес.</span><span class="sxs-lookup"><span data-stu-id="cd241-148">If you don't see this section name, then no connections of this type are available to you.</span></span>

1. <span data-ttu-id="cd241-149">Экспорттау қажет сегментті таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="cd241-149">Choose the segment that you want to export.</span></span> <span data-ttu-id="cd241-150">Бұл мысалда ол **ChurnProneCustomers** болып табылады.</span><span class="sxs-lookup"><span data-stu-id="cd241-150">In this example, it’s **ChurnProneCustomers**.</span></span>

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Таңдалған ChurnProneCustomers сегментімен сегмент таңдау бойынша пайдаланушы интерфейсінің скриншоты.":::

1. <span data-ttu-id="cd241-152">**Келесі** пәрменін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="cd241-152">Select **Next**.</span></span>

1. <span data-ttu-id="cd241-153">Енді біз аудитория мәліметтері сегментіндегі **Дереккөз** өрістерін Adobe Campaign Standard профилінің схемасындағы **Мақсат** өріс атауларымен салыстырамыз.</span><span class="sxs-lookup"><span data-stu-id="cd241-153">Now we map the **Source** fields from the audience insights segment to the **Target** field names in the Adobe Campaign Standard profile schema.</span></span>

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="Adobe Campaign Standard қосқышына арналған өрістерді салыстыру.":::

   <span data-ttu-id="cd241-155">Егер қосымша төлсипаттар қосу қажет болса, **Төлсипат қосу** пәрменін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="cd241-155">If you want to add more attributes, select **Add attribute**.</span></span> <span data-ttu-id="cd241-156">Мақсатты атау бастапқы өріс атауынан өзгеше болуы мүмкін, егер өрістердің екі жүйедегі атауы бірдей болмаса, аудитория мәліметтеріндегі сегмент шығысын Adobe Campaign Standard жүйесімен салыстыруға болады.</span><span class="sxs-lookup"><span data-stu-id="cd241-156">The target name can be different from the source field name so you can still map segment output from audience insights to Adobe Campaign Standard if the fields don’t have the same name in the two systems.</span></span>

   > [!NOTE]
   > <span data-ttu-id="cd241-157">Электрондық пошта мекенжайы жеке куәлік өрісі ретінде пайдаланылады, бірақ Adobe Campaign Standard жүйесіне деректерді салыстыру үшін аудитория мәліметтерінің тұтынушы профилінен кез келген басқа идентификаторды пайдалана аласыз.</span><span class="sxs-lookup"><span data-stu-id="cd241-157">Email address is used as an identity field but you can use any other identifier from your audience insights customer profile to map data to Adobe Campaign Standard.</span></span>

1. <span data-ttu-id="cd241-158">**Сақтау** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="cd241-158">Select **Save**.</span></span>

<span data-ttu-id="cd241-159">Экспорттау мақсатты орнын сақтағаннан кейін оны **Деректер** > **Экспорттаулар** тармағынан таба аласыз.</span><span class="sxs-lookup"><span data-stu-id="cd241-159">After saving the export destination, you find it on **Data** > **Exports**.</span></span>

<span data-ttu-id="cd241-160">[Сегментті сұраныс бойынша экспорттауға](export-destinations.md#run-exports-on-demand) болады.</span><span class="sxs-lookup"><span data-stu-id="cd241-160">You can now [export the segment on demand](export-destinations.md#run-exports-on-demand).</span></span> <span data-ttu-id="cd241-161">Экспорттау сондай-ақ әрбір [жоспарланған жаңарту](system.md) сайын іске қосылады.</span><span class="sxs-lookup"><span data-stu-id="cd241-161">The export will also run with every [scheduled refresh](system.md).</span></span>

> [!NOTE]
> <span data-ttu-id="cd241-162">Экспортталған сегменттегі жазбалар санының Adobe Campaign Standard лицензиясының рұқсат етілген шегінде болуын тексеріңіз.</span><span class="sxs-lookup"><span data-stu-id="cd241-162">Ensure that the number of records in the exported segment are within the allowed limit of your Adobe Campaign Standard license.</span></span>

<span data-ttu-id="cd241-163">Экспортталған деректер сіз жоғарыда конфигурациялаған Azure Blob сақтау контейнерінде сақталады.</span><span class="sxs-lookup"><span data-stu-id="cd241-163">Exported data is stored in the Azure Blob Storage container you configured above.</span></span> <span data-ttu-id="cd241-164">Контейнерде келесі қалта жолы автоматты түрде жасалады:</span><span class="sxs-lookup"><span data-stu-id="cd241-164">The following folder path is automatically created in your container:</span></span>

<span data-ttu-id="cd241-165">*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*</span><span class="sxs-lookup"><span data-stu-id="cd241-165">*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*</span></span>

<span data-ttu-id="cd241-166">Мысал: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv</span><span class="sxs-lookup"><span data-stu-id="cd241-166">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv</span></span>

## <a name="configure-adobe-campaign-standard"></a><span data-ttu-id="cd241-167">Adobe Campaign Standard жүйесін конфигурациялау</span><span class="sxs-lookup"><span data-stu-id="cd241-167">Configure Adobe Campaign Standard</span></span>

<span data-ttu-id="cd241-168">Аудитория мәліметтерінен алынған сегмент экспортталған кезде, алдыңғы қадамда экспорттауды анықтаған кезде сіз таңдаған бағандарды қамтиды.</span><span class="sxs-lookup"><span data-stu-id="cd241-168">When a segment from audience insights is exported, it contains the columns you selected while defining the export destination in the previous step.</span></span> <span data-ttu-id="cd241-169">Бұл деректерді [Adobe Campaign Standard жүйесінде профильдер жасау](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles) үшін пайдалануға болады.</span><span class="sxs-lookup"><span data-stu-id="cd241-169">This data can be used to [create profiles in Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).</span></span>

<span data-ttu-id="cd241-170">Adobe Campaign Standard жүйесінде сегментті пайдалану үшін Adobe Campaign Standard жүйесінде профиль схемасын екі қосымша өрісті қосу үшін кеңейту қажет.</span><span class="sxs-lookup"><span data-stu-id="cd241-170">To use the segment in Adobe Campaign Standard, we need to extend the profile schema in Adobe Campaign Standard to include two additional fields.</span></span> <span data-ttu-id="cd241-171">[Профиль ресурсын](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) Adobe Campaign Standard жүйесінде жаңа өрістермен кеңейту жолдары туралы мәлімет алыңыз.</span><span class="sxs-lookup"><span data-stu-id="cd241-171">Learn how to [extend the profile resource](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) with new fields in Adobe Campaign Standard.</span></span>

<span data-ttu-id="cd241-172">Біздің мысалда бұл өрістер *Сегмент атауы және сегмент күні (міндетті емес)* болып табылады.</span><span class="sxs-lookup"><span data-stu-id="cd241-172">In our example, these fields are *Segment Name and Segment Date (optional)*.</span></span>

<span data-ttu-id="cd241-173">Біз осы өрістерді Adobe Campaign Standard қызметінде осы науқанға бағыттағымыз келетін профильдерді анықтау үшін пайдаланамыз.</span><span class="sxs-lookup"><span data-stu-id="cd241-173">We will use these fields to identify the profiles in Adobe Campaign Standard we want to target for this campaign.</span></span>

<span data-ttu-id="cd241-174">Егер Adobe Campaign Standard қызметінде импортталатын жазбалардан басқа жазбалар болмаса, бұл қадамды өткізіп жіберуге болады.</span><span class="sxs-lookup"><span data-stu-id="cd241-174">If there are no other records in Adobe Campaign Standard, other than what you are going to import, you can skip this step.</span></span>

## <a name="import-data-into-adobe-campaign-standard"></a><span data-ttu-id="cd241-175">Деректерді Adobe Campaign Standard жүйесіне импорттау</span><span class="sxs-lookup"><span data-stu-id="cd241-175">Import data into Adobe Campaign Standard</span></span>

<span data-ttu-id="cd241-176">Енді барлығы дайын болған кезде профильдер жасау үшін дайындалған аудитория деректерін аудитория туралы түсініктерден Adobe Campaign Standard жүйесіне импорттауымыз қажет.</span><span class="sxs-lookup"><span data-stu-id="cd241-176">Now that everything is in place, we need to import the prepared audience data from audience insights into Adobe Campaign Standard to create profiles.</span></span> <span data-ttu-id="cd241-177">Жұмыс ағынын пайдаланып [Adobe Campaign Standard жүйесінде профильдерді импорттау туралы](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) мәлімет алыңыз.</span><span class="sxs-lookup"><span data-stu-id="cd241-177">Learn [how to import profiles in Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) using a workflow.</span></span>

<span data-ttu-id="cd241-178">Төмендегі кескіндегі импорттау жұмыс ағыны әр сегіз сағат сайын іске қосылатындай етіп және экспортталған аудитория түсініктерін іздейтін етіп (Azure екілік нысан сақтау орнындағы .csv файлы) конфигурацияланған.</span><span class="sxs-lookup"><span data-stu-id="cd241-178">The import workflow in the image below has been configured to run every eight hours and look for exported audience insights segments (.csv file in Azure Blob Storage).</span></span> <span data-ttu-id="cd241-179">Жұмыс ағыны .csv файл мазмұнын көрсетілген баған ретімен шығарады.</span><span class="sxs-lookup"><span data-stu-id="cd241-179">The workflow extracts the .csv file content in a specified column order.</span></span> <span data-ttu-id="cd241-180">Бұл жұмыс ағыны негізгі қателермен жұмыс істеуді жүзеге асыру және Adobe Campaign Standard жүйесінде деректерді сутектендірмес бұрын әр жазбада электрондық пошта мекенжайы болуын қамтамасыз ету үшін жасалған.</span><span class="sxs-lookup"><span data-stu-id="cd241-180">This workflow has been built to perform basic error handling and ensure that each record has an email address before hydrating the data in Adobe Campaign Standard.</span></span> <span data-ttu-id="cd241-181">Жұмыс ағыны Adobe Campaign Standard профилінің деректерін енгізбес бұрын файл атауынан сегменттің атауын шығарады.</span><span class="sxs-lookup"><span data-stu-id="cd241-181">The workflow also extracts the segment name from the filename before upserting into Adobe Campaign Standard profile data.</span></span>

:::image type="content" source="media/ACS-import-workflow.png" alt-text="Adobe Campaign Standard пайдаланушы интерфейсіндегі импорттық жұмыс ағынының скриншоты.":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a><span data-ttu-id="cd241-183">Adobe Campaign Standard жүйесінде аудиторияны алу</span><span class="sxs-lookup"><span data-stu-id="cd241-183">Retrieve the audience in Adobe Campaign Standard</span></span>

<span data-ttu-id="cd241-184">Деректер Adobe Campaign Standard жүйесіне импортталғаннан кейін біздің үлгі науқанымыз үшін анықталған профильдерді таңдау үшін [жұмыс ағынын жасауға](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) және *Сегмент атауы* мен *Сегмент күні* параметрлеріне негізделген тұтынушыларды [сұрауға](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) болады.</span><span class="sxs-lookup"><span data-stu-id="cd241-184">Once the data is imported into Adobe Campaign Standard, you [can create a workflow](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) and [query](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) the customers based on the *Segment Name* and *Segment Date* to select profiles that were identified for our sample campaign.</span></span>

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a><span data-ttu-id="cd241-185">Adobe Campaign Standard көмегімен электрондық пошта хабарын жасау және жіберу</span><span class="sxs-lookup"><span data-stu-id="cd241-185">Create and send the email using Adobe Campaign Standard</span></span>

<span data-ttu-id="cd241-186">Электрондық пошта мазмұнын жасап, содан кейін электрондық пошта хабарын [тексеріп, жіберіңіз](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages).</span><span class="sxs-lookup"><span data-stu-id="cd241-186">Create the email content and then [test and send](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) your email.</span></span>

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Adobe Campaign Standard ұсынған жаңарту ұсынысы бар электрондық пошта хабарының үлгісі.":::
