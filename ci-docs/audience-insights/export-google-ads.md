---
title: Customer Insights деректерін Google Ads платформасына экспорттау
description: Google Ads қызметі үшін қосылымды конфигурациялау және экспорттау жолы туралы ақпарат.
ms.date: 03/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 73f3257a3ae6e8423f45410546535df5e3b400ce
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976325"
---
# <a name="export-segments-to-google-ads-preview"></a><span data-ttu-id="14935-103">Сегменттерді Google Ads қызметіне экспорттау (алдын ала қарау нұсқасы)</span><span class="sxs-lookup"><span data-stu-id="14935-103">Export segments to Google Ads (preview)</span></span>

<span data-ttu-id="14935-104">Тұтынушылардың біріңғай профильдерінің сегменттерін Google Ads аудиториясының тізіміне экспорттаңыз және оларды Google Search, Gmail, YouTube және Google көрсету желілерінде жарнамалаңыз.</span><span class="sxs-lookup"><span data-stu-id="14935-104">Export segments of unified customer profiles to Google Ads audience list and use them to advertise on Google Search, Gmail, YouTube, and Google Display Network.</span></span> 

## <a name="prerequisites-for-connection"></a><span data-ttu-id="14935-105">Қосылым алғышарттары</span><span class="sxs-lookup"><span data-stu-id="14935-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="14935-106">Сізде [Google Ads тіркелгісі](https://ads.google.com/) және тиісті әкімшінің тіркелгі деректері бар.</span><span class="sxs-lookup"><span data-stu-id="14935-106">You have a [Google Ads account](https://ads.google.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="14935-107">Сізде [бекітілген Google Ads әзірлеуші таңбалауышы](https://developers.google.com/google-ads/api/docs/first-call/dev-token) бар</span><span class="sxs-lookup"><span data-stu-id="14935-107">You have an [approved Google Ads Developer token](https://developers.google.com/google-ads/api/docs/first-call/dev-token)</span></span> 
-   <span data-ttu-id="14935-108">Сіз [тұтынушы сәйкестігі саясатының](https://support.google.com/adspolicy/answer/6299717) талаптарына сәйкес келесіз</span><span class="sxs-lookup"><span data-stu-id="14935-108">You fulfill the requirements of the [Customer Match Policy](https://support.google.com/adspolicy/answer/6299717)</span></span>
-   <span data-ttu-id="14935-109">Сіз [ремаркетинг тізімі өлшемдерінің](https://support.google.com/google-ads/answer/7558048) талаптарына сәйкес келесіз</span><span class="sxs-lookup"><span data-stu-id="14935-109">You fulfill the requirements of the [remarketing list sizes](https://support.google.com/google-ads/answer/7558048)</span></span> 

-   <span data-ttu-id="14935-110">Google Ads платформасында қолданыстағы аудиториялар және тиісті идентификаторлар бар.</span><span class="sxs-lookup"><span data-stu-id="14935-110">There are existing audiences in Google Ads and the corresponding IDs.</span></span> <span data-ttu-id="14935-111">Қосымша ақпарат алу үшін [Google Ads аудиториялары](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.) бөлімін қараңыз.</span><span class="sxs-lookup"><span data-stu-id="14935-111">For more information, see [Google Ads audiences](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).</span></span>
-   <span data-ttu-id="14935-112">Сізде [конфигурацияланған сегменттер](segments.md) бар</span><span class="sxs-lookup"><span data-stu-id="14935-112">You have [configured segments](segments.md)</span></span>
-   <span data-ttu-id="14935-113">Экспортталған сегменттердегі тұтынушылардың бірыңғай профильдері электрондық пошта мекенжайын, аты және тегін көрсететін өрістерден тұрады</span><span class="sxs-lookup"><span data-stu-id="14935-113">Unified customer profiles in the exported segments contain fields representing an email address, first name, and last name</span></span>

## <a name="known-limitations"></a><span data-ttu-id="14935-114">Белгілі шектеулер</span><span class="sxs-lookup"><span data-stu-id="14935-114">Known limitations</span></span>

- <span data-ttu-id="14935-115">Google Ads платформасына 1 миллионға дейін профильді экспорттауға болады.</span><span class="sxs-lookup"><span data-stu-id="14935-115">Up to 1 million profiles per export to Google Ads.</span></span>
- <span data-ttu-id="14935-116">Google Ads платформасына экспорттау тек сегменттермен шектеледі.</span><span class="sxs-lookup"><span data-stu-id="14935-116">Exporting to Google Ads is limited to segments.</span></span>
- <span data-ttu-id="14935-117">Жалпы саны 1 миллион профильді экспорттайтын сегменттер провайдер тарапынан шектеулер болғандықтан 5 минутқа созылуы мүмкін.</span><span class="sxs-lookup"><span data-stu-id="14935-117">Exporting segments with a total of 1 million profiles can take up to 5 minutes because of limitations on the provider side.</span></span> 
- <span data-ttu-id="14935-118">Google Ads платформасында салыстыру 48 сағатқа созылуы мүмкін.</span><span class="sxs-lookup"><span data-stu-id="14935-118">The matching in Google Ads can take up to 48 hours.</span></span>

## <a name="set-up-connection-to-google-ads"></a><span data-ttu-id="14935-119">Google Ads қызметіне қосылым орнату</span><span class="sxs-lookup"><span data-stu-id="14935-119">Set up connection to Google Ads</span></span>

1. <span data-ttu-id="14935-120">**Әкімші** > **Қосылымдар** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="14935-120">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="14935-121">**Қосылым қосу** түймешігін таңдаңыз және қосылымды конфигурациялау үшін **Google Ads** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="14935-121">Select **Add connection** and choose **Google Ads** to configure the connection.</span></span>

1. <span data-ttu-id="14935-122">**Көрсетілетін аты** өрісінде қосылымға оңай танылатын атау енгізіңіз.</span><span class="sxs-lookup"><span data-stu-id="14935-122">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="14935-123">Қосылым атауы мен түрі осы қосылымды сипаттайды.</span><span class="sxs-lookup"><span data-stu-id="14935-123">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="14935-124">Қосылымның мақсатын түсіндіретін атауды таңдауды ұсынамыз.</span><span class="sxs-lookup"><span data-stu-id="14935-124">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="14935-125">Осы қосылымды кім пайдалана алатынын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="14935-125">Choose who can use this connection.</span></span> <span data-ttu-id="14935-126">Егер сіз ешқандай әрекет жасамасаңыз, әдепкі бойынша Әкімшілер болады.</span><span class="sxs-lookup"><span data-stu-id="14935-126">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="14935-127">Қосымша ақпарат алу үшін [Салымшыларға экспорттау үшін қосылымды пайдалануға рұқсат беру](connections.md#allow-contributors-to-use-a-connection-for-exports) бөлімін қараңыз.</span><span class="sxs-lookup"><span data-stu-id="14935-127">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="14935-128">**[Google Ads тұтынушы идентификаторын](https://support.google.com/google-ads/answer/1704344)** енгізіңіз.</span><span class="sxs-lookup"><span data-stu-id="14935-128">Enter your **[Google Ads customer ID](https://support.google.com/google-ads/answer/1704344)**.</span></span>

1. <span data-ttu-id="14935-129">**[Google Ads мақұлдаған әзірлеуші таңбалауышын](https://developers.google.com/google-ads/api/docs/first-call/dev-token)** енгізіңіз.</span><span class="sxs-lookup"><span data-stu-id="14935-129">Enter your **[Google Ads approved developer token](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.</span></span>

1. <span data-ttu-id="14935-130">**Деректер құпиялығы мен сәйкестігін** растау үшін **Мен келісемін** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="14935-130">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="14935-131">**Google Ads көмегімен аутентификациялау** пәрменін таңдап, Google Ads тіркелгі деректерін ұсыныңыз.</span><span class="sxs-lookup"><span data-stu-id="14935-131">Select **Authenticate with Google Ads** and provide your Google Ads credentials.</span></span>

1. <span data-ttu-id="14935-132">**Өзіңізді экспорт пайдаланушысы ретінде қосу** пәрменін таңдап, өзіңіздің Customer Insights тіркелгі деректерін ұсыныңыз.</span><span class="sxs-lookup"><span data-stu-id="14935-132">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="14935-133">Қосылымды аяқтау үшін **Сақтау** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="14935-133">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="14935-134">Экспорттауды конфигурациялау</span><span class="sxs-lookup"><span data-stu-id="14935-134">Configure an export</span></span>

<span data-ttu-id="14935-135">Егер сіз осы түрдегі қосылымға қатынаса алсаңыз, сіз бұл экспорттауды конфигурациялай аласыз.</span><span class="sxs-lookup"><span data-stu-id="14935-135">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="14935-136">Қосымша ақпарат алу үшін [Экспорттауды конфигурациялау үшін қажет рұқсаттар](export-destinations.md#set-up-a-new-export) бөлімін қараңыз.</span><span class="sxs-lookup"><span data-stu-id="14935-136">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="14935-137">**Деректер** > **Экспорттау** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="14935-137">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="14935-138">Жаңа экспорттау жасау үшін **Мақсатты орын қосу** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="14935-138">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="14935-139">**Экспорттауға арналған қосылым** өрісінде Google Ads бөлімінен қосылым таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="14935-139">In the **Connection for export** field, choose a connection from the Google Ads section.</span></span> <span data-ttu-id="14935-140">Егер сіз осы бөлімнің атын көрмесеңіз, сізге қолжетімді осы түрдегі қосылым жоқ.</span><span class="sxs-lookup"><span data-stu-id="14935-140">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="14935-141">Google Ads платформасына қосылуды баптандыру үшін **[Google Ads аудиториясының идентификаторын](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** енгізіп, **Қосылу** пәрменін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="14935-141">Enter your **[Google Ads audience ID](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** and select **Connect** to initialize the connection to Google Ads.</span></span>

1. <span data-ttu-id="14935-142">**Деректерді салыстыру** бөліміндегі **Электрондық пошта** өрісінде тұтынушының электрондық пошта мекенжайын көрсететін бірыңғай тұтынушы профиліндегі өрісті таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="14935-142">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="14935-143">**Аты** және **Тегі** өрістері үшін бірдей қадамдарды қайталаңыз.</span><span class="sxs-lookup"><span data-stu-id="14935-143">Repeat the same steps for \*\*First name" and **Last name** fields.</span></span>

1. <span data-ttu-id="14935-144">Экспорттау керек сегменттерді таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="14935-144">Select the segments you want to export.</span></span> <span data-ttu-id="14935-145">Google Ads платформасына жалпы 1 миллионға дейін тұтынушы профилін экспорттай аласыз.</span><span class="sxs-lookup"><span data-stu-id="14935-145">You can export up to 1 million customer profiles in total to Google Ads.</span></span>

<span data-ttu-id="14935-146">Экспорттауды сақтау экспорттауды бірден іске қоспайды.</span><span class="sxs-lookup"><span data-stu-id="14935-146">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="14935-147">Экспорттау әр [жоспарланған жаңартумен](system.md#schedule-tab) іске қосылады.</span><span class="sxs-lookup"><span data-stu-id="14935-147">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="14935-148">Сондай-ақ [деректерді сұрау бойынша экспорттауға](export-destinations.md#run-exports-on-demand) болады.</span><span class="sxs-lookup"><span data-stu-id="14935-148">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="14935-149">Деректердің құпиялылығы мен сәйкестігі</span><span class="sxs-lookup"><span data-stu-id="14935-149">Data privacy and compliance</span></span>

<span data-ttu-id="14935-150">Деректерді Google Ads платформасына жіберу үшін Dynamics 365 Customer Insights бағдарламасын қосқан кезде, Dynamics 365 Customer Insights талаптарына сәйкестік шекарасынан тыс деректерді, соның ішінде жеке деректер сияқты ықтимал құпия деректерді беруге мүмкіндік бересіз.</span><span class="sxs-lookup"><span data-stu-id="14935-150">When you enable Dynamics 365 Customer Insights to transmit data to Google Ads, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="14935-151">Microsoft мұндай деректерді сіздің нұсқауыңыз бойынша тасымалдайды, бірақ Google Ads кез келген құпиялылық немесе қауіпсіздік міндеттемелеріне сәйкес келуіне жауап бересіз.</span><span class="sxs-lookup"><span data-stu-id="14935-151">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Google Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="14935-152">Қосымша ақпаратты [Microsoft құпиялық туралы мәлімдемесі](https://go.microsoft.com/fwlink/?linkid=396732) бөлімінен қараңыз.</span><span class="sxs-lookup"><span data-stu-id="14935-152">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="14935-153">Бұл функцияны тоқтату үшін бұл экспорттау мақсатын кез келген уақытта Dynamics 365 Customer Insights әкімшісі жоя алады.</span><span class="sxs-lookup"><span data-stu-id="14935-153">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
