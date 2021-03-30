---
title: Customer Insights деректерін Adobe Campaign Standard бағдарламасына экспорттау
description: Adobe Campaign Standard бағдарламасында аудитория мәліметтері сегменттерін пайдалану жолы туралы мәлімет алыңыз.
ms.date: 02/26/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: a5d0154c3d7c473dcba03fac0847bafcf97de2f2
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596322"
---
# <a name="use-customer-insights-segments-in-adobe-campaign-standard-preview"></a><span data-ttu-id="14831-103">Adobe Campaign Standard бағдарламасында Customer Insights сегменттерін пайдалану (алдын ала қарау нұсқасы)</span><span class="sxs-lookup"><span data-stu-id="14831-103">Use Customer Insights segments in Adobe Campaign Standard (preview)</span></span>

<span data-ttu-id="14831-104">Dynamics 365 Customer Insights бағдарламасының аудитория туралы түсініктер пайдаланушысы ретінде сіз тиісті аудиторияға назар аудара отырып, маркетингтік науқандарды тиімді ету үшін сегменттер жасауыңыз мүмкін.</span><span class="sxs-lookup"><span data-stu-id="14831-104">As a user of audience insights for Dynamics 365 Customer Insights, you may have created segments to make your marketing campaigns more efficient by targeting relevant audiences.</span></span> <span data-ttu-id="14831-105">Adobe Experience Platform платформасында және Adobe Campaign Standard секілді бағдарламаларда аудитория туралы түсініктерден сегментті пайдалану үшін осы мақалада көрсетілген бірнеше қадамды орындауыңыз қажет.</span><span class="sxs-lookup"><span data-stu-id="14831-105">To use a segment from audience insights in Adobe Experience Platform and applications like Adobe Campaign Standard, you need to follow a few steps outlined in this article.</span></span>

:::image type="content" source="media/ACS-flow.png" alt-text="Осы мақалада көрсетілген қадамдардың процестік диаграммасы.":::

## <a name="prerequisites"></a><span data-ttu-id="14831-107">Алғышарттар</span><span class="sxs-lookup"><span data-stu-id="14831-107">Prerequisites</span></span>

-   <span data-ttu-id="14831-108">Dynamics 365 Customer Insights лицензиясы</span><span class="sxs-lookup"><span data-stu-id="14831-108">Dynamics 365 Customer Insights license</span></span>
-   <span data-ttu-id="14831-109">Adobe Campaign Standard лицензиясы</span><span class="sxs-lookup"><span data-stu-id="14831-109">Adobe Campaign Standard license</span></span>
-   <span data-ttu-id="14831-110">Azure Blob сақтау орны тіркелгісі</span><span class="sxs-lookup"><span data-stu-id="14831-110">Azure Blob Storage account</span></span>

## <a name="campaign-overview"></a><span data-ttu-id="14831-111">Науқанды шолу</span><span class="sxs-lookup"><span data-stu-id="14831-111">Campaign Overview</span></span>

<span data-ttu-id="14831-112">Adobe Experience Platform платформасында аудитория туралы түсініктердегі сегменттерді пайдалану жолы туралы толығырақ түсіну үшін үлгі ретінде берілген науқанды қарастырайық.</span><span class="sxs-lookup"><span data-stu-id="14831-112">To better understand how you can use segments from audience insights in Adobe Experience Platform, let’s look at a fictitious sample campaign.</span></span>

<span data-ttu-id="14831-113">Сіздің компанияңыз АҚШ-тағы тұтынушыларыңызға ай сайынғы жазылымға негізделген қызметті ұсынады делік.</span><span class="sxs-lookup"><span data-stu-id="14831-113">Let’s assume that your company offers a monthly, subscription-based service to your customers in the United States.</span></span> <span data-ttu-id="14831-114">Сізге жазылымы келесі сегіз күнде жаңартылуы керек, бірақ жазылымын әлі ұзартпаған тұтынушыларды анықтау қажет.</span><span class="sxs-lookup"><span data-stu-id="14831-114">You want to identify customers whose subscriptions are due for renewal in the next eight days but haven't yet renewed their subscription.</span></span> <span data-ttu-id="14831-115">Осы тұтынушыларды ұстап тұру үшін Adobe Campaign Standard бағдарламасы көмегімен электрондық пошта арқылы оларға жарнамалық акция жіберу қажет болуы мүмкін.</span><span class="sxs-lookup"><span data-stu-id="14831-115">To keep these customers, you want to send them a promotional offer via email, using Adobe Campaign Standard.</span></span>

<span data-ttu-id="14831-116">Бұл мысалда біз жарнамалық науқанды бір рет электрондық пошта арқылы жүргізгіміз келеді.</span><span class="sxs-lookup"><span data-stu-id="14831-116">In this example, we want to run the promotional email campaign once.</span></span> <span data-ttu-id="14831-117">Бұл мақалада науқанды бірнеше рет жүргізу жағдайлары қарастырылмаған.</span><span class="sxs-lookup"><span data-stu-id="14831-117">This article doesn’t cover the use-case of running the campaign more than once.</span></span> <span data-ttu-id="14831-118">Дегенмен, аудитория мәліметтері мен Adobe Campaign Standard бағдарламасы қайталанатын науқандық сценарий үшін жұмыс істеуге конфигурациялануы мүмкін.</span><span class="sxs-lookup"><span data-stu-id="14831-118">However, audience insights and Adobe Campaign Standard can be configured to work for a recurring campaign scenario too.</span></span>

## <a name="identify-your-target-audience"></a><span data-ttu-id="14831-119">Мақсатты аудиторияңызды анықтаңыз</span><span class="sxs-lookup"><span data-stu-id="14831-119">Identify your target audience</span></span>

<span data-ttu-id="14831-120">Біздің сценарий бойынша біз тұтынушылардың электрондық пошта мекенжайлары аудитория туралы түсініктерде қолжетімді және сегменттің мүшелерін анықтау үшін олардың жарнамалық артықшылықтары талданды деп болжанады.</span><span class="sxs-lookup"><span data-stu-id="14831-120">In our scenario, we assume that the email addresses of the customers are available in audience insights and their promotional preferences were analyzed to identify members of the segment.</span></span>

<span data-ttu-id="14831-121">[Аудитория туралы түсініктерде анықталған сегмент](segments.md) **ChurnProneCustomers** деп аталады және осы тұтынушыларға электрондық пошта арқылы жарнамалауды жіберуді жоспарлайсыз.</span><span class="sxs-lookup"><span data-stu-id="14831-121">The [segment you defined in audience insights](segments.md) is called **ChurnProneCustomers** and you plan to send these customers the email promotion.</span></span>

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Жасалған ChurnProneCustomers сегменті бар сегменттер бетінің скриншоты.":::

<span data-ttu-id="14831-123">Жіберілетін ұсыныс электрондық хаты аты-жөнін, тегін және тұтынушы жазылымының аяқталу күнін қамтиды.</span><span class="sxs-lookup"><span data-stu-id="14831-123">The offer email that you want to send out will contain the first name, last name, and the subscription end date of the customer.</span></span> <span data-ttu-id="14831-124">Мұнда тұтынушыларға жазылым аяқталғанға дейін оны ұзартқан кезде алатын жеңілдіктер туралы хабарланады.</span><span class="sxs-lookup"><span data-stu-id="14831-124">It informs the customers about the discount they’ll get if they renew their subscription before it ends.</span></span>

## <a name="export-your-target-audience"></a><span data-ttu-id="14831-125">Мақсатты аудиторияңызды экспорттау</span><span class="sxs-lookup"><span data-stu-id="14831-125">Export your target audience</span></span>

<span data-ttu-id="14831-126">Анықталған мақсатты аудитория арқылы аудитория туралы түсініктерден Azure Blob сақтау орны тіркелгісіне экспорттауды конфигурациялаймыз.</span><span class="sxs-lookup"><span data-stu-id="14831-126">With our target audience identified, we can configure the export from audience insights to an Azure Blob Storage account.</span></span>

1. <span data-ttu-id="14831-127">Аудитория мәліметтерінде **Әкімші** > **Экспорттау мақсаттары** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="14831-127">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="14831-128">**Adobe Campaign** тақтасында **Орнату** пәрменін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="14831-128">In the **Adobe Campaign** tile, select **Set up**.</span></span>

   :::image type="content" source="media/adobe-campaign-standard-tile.png" alt-text="Adobe Campaign Standard бағдарламасының конфигурация тақтасы.":::

1. <span data-ttu-id="14831-130">Осы жаңа экспорттау межелі орны үшін **Көрсетілу атауын** ұсынып, содан кейін сегмент экспортталатын Azure Blob сақтау орны тіркелгісінің **Тіркелгі атауы**, **Тіркелгі кілті** және **Контейнер** параметрлерін енгізіңіз.</span><span class="sxs-lookup"><span data-stu-id="14831-130">Provide a **Display name** for this new export destination and then enter the **Account name**, **Account key**, and **Container** of the Azure Blob Storage account where you want to export the segment to.</span></span>  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Сақтау орны тіркелгісі конфигурациясының скриншоты."::: 

   - <span data-ttu-id="14831-132">Azure Blob сақтау тіркелгісінің аты мен тіркелгі кілтін табу жөнінде толығырақ ақпарат алу үшін мына тақырыпты қараңыз: [Azure порталындағы сақтау құралының тіркелгі параметрлерін басқару](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="14831-132">To learn more about how to find the Azure Blob storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

   - <span data-ttu-id="14831-133">Контейнерді жасау жөнінде мағлұмат алу үшін мына тақырыпты қараңыз: [Контейнер жасау](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="14831-133">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="14831-134">**Келесі** пәрменін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="14831-134">Select **Next**.</span></span>

1. <span data-ttu-id="14831-135">Экспорттау қажет сегментті таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="14831-135">Choose the segment that you want to export.</span></span> <span data-ttu-id="14831-136">Бұл мысалда ол **ChurnProneCustomers** болып табылады.</span><span class="sxs-lookup"><span data-stu-id="14831-136">In this example, it’s **ChurnProneCustomers**.</span></span>

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Таңдалған ChurnProneCustomers сегментімен сегмент таңдау бойынша пайдаланушы интерфейсінің скриншоты.":::

1. <span data-ttu-id="14831-138">**Келесі** пәрменін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="14831-138">Select **Next**.</span></span>

1. <span data-ttu-id="14831-139">Енді біз аудитория мәліметтері сегментіндегі **Дереккөз** өрістерін Adobe Campaign Standard профилінің схемасындағы **Мақсат** өріс атауларымен салыстырамыз.</span><span class="sxs-lookup"><span data-stu-id="14831-139">Now we map the **Source** fields from the audience insights segment to the **Target** field names in the Adobe Campaign Standard profile schema.</span></span>

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="Adobe Campaign Standard қосқышына арналған өрістерді салыстыру.":::

   <span data-ttu-id="14831-141">Егер қосымша төлсипаттар қосу қажет болса, **Төлсипат қосу** пәрменін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="14831-141">If you want to add more attributes, select **Add attribute**.</span></span> <span data-ttu-id="14831-142">Мақсатты атау бастапқы өріс атауынан өзгеше болуы мүмкін, егер өрістердің екі жүйедегі атауы бірдей болмаса, аудитория мәліметтеріндегі сегмент шығысын Adobe Campaign Standard жүйесімен салыстыруға болады.</span><span class="sxs-lookup"><span data-stu-id="14831-142">The target name can be different from the source field name so you can still map segment output from audience insights to Adobe Campaign Standard if the fields don’t have the same name in the two systems.</span></span>

   > [!NOTE]
   > <span data-ttu-id="14831-143">Электрондық пошта мекенжайы жеке куәлік өрісі ретінде пайдаланылады, бірақ Adobe Campaign Standard жүйесіне деректерді салыстыру үшін аудитория мәліметтерінің тұтынушы профилінен кез келген басқа идентификаторды пайдалана аласыз.</span><span class="sxs-lookup"><span data-stu-id="14831-143">Email address is used as an identity field but you can use any other identifier from your audience insights customer profile to map data to Adobe Campaign Standard.</span></span>

1. <span data-ttu-id="14831-144">**Сақтау** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="14831-144">Select **Save**.</span></span>

<span data-ttu-id="14831-145">Экспорттау межелі орнын сақтағаннан кейін оны **Әкімші** > **Экспорттар** > **Менің экспорттау межелі орындарым** тармағы бойынша табуға болады.</span><span class="sxs-lookup"><span data-stu-id="14831-145">After saving the export destination, you find it on **Admin** > **Exports** > **My export destinations**.</span></span>

:::image type="content" source="media/export-destination-adobe-campaign-standard.png" alt-text="Экспорттаулар тізімі мен бөлектелген сегмент үлгісінің скриншоты.":::

<span data-ttu-id="14831-147">[Сегментті сұраныс бойынша экспорттауға](export-destinations.md#export-data-on-demand) болады.</span><span class="sxs-lookup"><span data-stu-id="14831-147">You can now [export the segment on demand](export-destinations.md#export-data-on-demand).</span></span> <span data-ttu-id="14831-148">Экспорттау сондай-ақ әрбір [жоспарланған жаңарту](system.md) сайын іске қосылады.</span><span class="sxs-lookup"><span data-stu-id="14831-148">The export will also run with every [scheduled refresh](system.md).</span></span>

> [!NOTE]
> <span data-ttu-id="14831-149">Экспортталған сегменттегі жазбалар санының Adobe Campaign Standard лицензиясының рұқсат етілген шегінде болуын тексеріңіз.</span><span class="sxs-lookup"><span data-stu-id="14831-149">Ensure that the number of records in the exported segment are within the allowed limit of your Adobe Campaign Standard license.</span></span>

<span data-ttu-id="14831-150">Экспортталған деректер сіз жоғарыда конфигурациялаған Azure Blob сақтау контейнерінде сақталады.</span><span class="sxs-lookup"><span data-stu-id="14831-150">Exported data is stored in the Azure Blob storage container you configured above.</span></span> <span data-ttu-id="14831-151">Контейнерде келесі қалта жолы автоматты түрде жасалады:</span><span class="sxs-lookup"><span data-stu-id="14831-151">The following folder path is automatically created in your container:</span></span>

<span data-ttu-id="14831-152">*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*</span><span class="sxs-lookup"><span data-stu-id="14831-152">*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*</span></span>

<span data-ttu-id="14831-153">Мысал: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv</span><span class="sxs-lookup"><span data-stu-id="14831-153">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv</span></span>

## <a name="configure-adobe-campaign-standard"></a><span data-ttu-id="14831-154">Adobe Campaign Standard жүйесін конфигурациялау</span><span class="sxs-lookup"><span data-stu-id="14831-154">Configure Adobe Campaign Standard</span></span>

<span data-ttu-id="14831-155">Аудитория мәліметтерінен алынған сегмент экспортталған кезде, алдыңғы қадамда экспорттауды анықтаған кезде сіз таңдаған бағандарды қамтиды.</span><span class="sxs-lookup"><span data-stu-id="14831-155">When a segment from audience insights is exported, it contains the columns you selected while defining the export destination in the previous step.</span></span> <span data-ttu-id="14831-156">Бұл деректерді [Adobe Campaign Standard жүйесінде профильдер жасау](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles) үшін пайдалануға болады.</span><span class="sxs-lookup"><span data-stu-id="14831-156">This data can be used to [create profiles in Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).</span></span>

<span data-ttu-id="14831-157">Adobe Campaign Standard жүйесінде сегментті пайдалану үшін Adobe Campaign Standard жүйесінде профиль схемасын екі қосымша өрісті қосу үшін кеңейту қажет.</span><span class="sxs-lookup"><span data-stu-id="14831-157">To use the segment in Adobe Campaign Standard, we need to extend the profile schema in Adobe Campaign Standard to include two additional fields.</span></span> <span data-ttu-id="14831-158">[Профиль ресурсын](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) Adobe Campaign Standard жүйесінде жаңа өрістермен кеңейту жолдары туралы мәлімет алыңыз.</span><span class="sxs-lookup"><span data-stu-id="14831-158">Learn how to [extend the profile resource](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) with new fields in Adobe Campaign Standard.</span></span>

<span data-ttu-id="14831-159">Біздің мысалда бұл өрістер *Сегмент атауы және сегмент күні (міндетті емес)* болып табылады.</span><span class="sxs-lookup"><span data-stu-id="14831-159">In our example, these fields are *Segment Name and Segment Date (optional).*</span></span>

<span data-ttu-id="14831-160">Біз осы өрістерді Adobe Campaign Standard қызметінде осы науқанға бағыттағымыз келетін профильдерді анықтау үшін пайдаланамыз.</span><span class="sxs-lookup"><span data-stu-id="14831-160">We will use these fields to identify the profiles in Adobe Campaign Standard we want to target for this campaign.</span></span>

<span data-ttu-id="14831-161">Егер Adobe Campaign Standard қызметінде импортталатын жазбалардан басқа жазбалар болмаса, бұл қадамды өткізіп жіберуге болады.</span><span class="sxs-lookup"><span data-stu-id="14831-161">If there are no other records in Adobe Campaign Standard, other than what you are going to import, you can skip this step.</span></span>

## <a name="import-data-into-adobe-campaign-standard"></a><span data-ttu-id="14831-162">Деректерді Adobe Campaign Standard жүйесіне импорттау</span><span class="sxs-lookup"><span data-stu-id="14831-162">Import data into Adobe Campaign Standard</span></span>

<span data-ttu-id="14831-163">Енді барлығы дайын болған кезде профильдер жасау үшін дайындалған аудитория деректерін аудитория туралы түсініктерден Adobe Campaign Standard жүйесіне импорттауымыз қажет.</span><span class="sxs-lookup"><span data-stu-id="14831-163">Now that everything is in place, we need to import the prepared audience data from audience insights into Adobe Campaign Standard to create profiles.</span></span> <span data-ttu-id="14831-164">Жұмыс ағынын пайдаланып [Adobe Campaign Standard жүйесінде профильдерді импорттау туралы](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) мәлімет алыңыз.</span><span class="sxs-lookup"><span data-stu-id="14831-164">Learn [how to import profiles in Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) using a workflow.</span></span>

<span data-ttu-id="14831-165">Төмендегі кескіндегі импорттық жұмыс ағыны әр 8 сағат сайын орындалатындай етіп конфигурацияланған және экспортталған аудитория түсініктерін (Azure Blob сақтау орнындағы .csv файлы) іздейді.</span><span class="sxs-lookup"><span data-stu-id="14831-165">The import workflow in the image below has been configured to run every 8 hours and looks for exported audience insights segments (.csv file in Azure Blob Storage).</span></span> <span data-ttu-id="14831-166">Жұмыс ағыны .csv файл мазмұнын көрсетілген баған ретімен шығарады.</span><span class="sxs-lookup"><span data-stu-id="14831-166">The workflow extracts the .csv file content in a specified column order.</span></span> <span data-ttu-id="14831-167">Бұл жұмыс ағыны негізгі қателермен жұмыс істеуді жүзеге асыру және Adobe Campaign Standard жүйесінде деректерді сутектендірмес бұрын әр жазбада электрондық пошта мекенжайы болуын қамтамасыз ету үшін жасалған.</span><span class="sxs-lookup"><span data-stu-id="14831-167">This workflow has been built to perform basic error handling and ensure that each record has an email address before hydrating the data in Adobe Campaign Standard.</span></span> <span data-ttu-id="14831-168">Сондай-ақ, жұмыс ағыны ACS профилі деректерін қалпына келтірмес бұрын файл атауынан сегменттің атауын шығарады.</span><span class="sxs-lookup"><span data-stu-id="14831-168">The workflow also extracts the segment name from the filename before upserting into ACS Profile data.</span></span>

:::image type="content" source="media/ACS-import-workflow.png" alt-text="Adobe Campaign Standard пайдаланушы интерфейсіндегі импорттық жұмыс ағынының скриншоты.":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a><span data-ttu-id="14831-170">Adobe Campaign Standard жүйесінде аудиторияны алу</span><span class="sxs-lookup"><span data-stu-id="14831-170">Retrieve the audience in Adobe Campaign Standard</span></span>

<span data-ttu-id="14831-171">Деректер Adobe Campaign Standard жүйесіне импортталғаннан кейін біздің үлгі науқанымыз үшін анықталған профильдерді таңдау үшін [жұмыс ағынын жасауға](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) және *Сегмент атауы* мен *Сегмент күні* параметрлеріне негізделген тұтынушыларды [сұрауға](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) болады.</span><span class="sxs-lookup"><span data-stu-id="14831-171">Once the data is imported into Adobe Campaign Standard, you [can create a workflow](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) and [query](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) the customers based on the *Segment Name* and *Segment Date* to select profiles that were identified for our sample campaign.</span></span>

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a><span data-ttu-id="14831-172">Adobe Campaign Standard көмегімен электрондық пошта хабарын жасау және жіберу</span><span class="sxs-lookup"><span data-stu-id="14831-172">Create and send the email using Adobe Campaign Standard</span></span>

<span data-ttu-id="14831-173">Электрондық пошта мазмұнын жасап, содан кейін электрондық пошта хабарын [тексеріп, жіберіңіз](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages).</span><span class="sxs-lookup"><span data-stu-id="14831-173">Create the email content and then [test and send](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) your email.</span></span>

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Adobe Campaign Standard ұсынған жаңарту ұсынысы бар электрондық пошта хабарының үлгісі.":::