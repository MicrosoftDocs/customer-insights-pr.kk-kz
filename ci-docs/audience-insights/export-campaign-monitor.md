---
title: Customer Insights деректерін Campaign Monitor қызметіне экспорттау
description: Campaign Monitor қызметі үшін қосылымды конфигурациялау және экспорттау жолы туралы ақпарат.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 7fd6af37b40e21d030a1ace0cd5f8fcc7861c3fa
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760572"
---
# <a name="export-segment-lists-to-campaign-monitor-preview"></a><span data-ttu-id="2b511-103">Сегмент тізімдерін Campaign Monitor қызметіне экспорттау (алдын ала қарау нұсқасы)</span><span class="sxs-lookup"><span data-stu-id="2b511-103">Export segment lists to Campaign Monitor (preview)</span></span>

<span data-ttu-id="2b511-104">Тұтынушылардың бірыңғай профильдерінің сегменттерін Campaign Monitor қызметіне экспорттаңыз және оларды маркетингтік әрекеттер үшін пайдаланыңыз.</span><span class="sxs-lookup"><span data-stu-id="2b511-104">Export segments of unified customer profiles to Campaign Monitor and use them for marketing activities.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="2b511-105">Алғышарттар</span><span class="sxs-lookup"><span data-stu-id="2b511-105">Prerequisites</span></span>

-   <span data-ttu-id="2b511-106">Сізде [Campaign Monitor қызметінің тіркелгісі](https://www.campaignmonitor.com/) және тиісті әкімші тіркелгі деректері бар.</span><span class="sxs-lookup"><span data-stu-id="2b511-106">You have an [Campaign Monitor account](https://www.campaignmonitor.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="2b511-107">Аудитория түсініктерінде [конфигурацияланған сегменттер](segments.md) бар.</span><span class="sxs-lookup"><span data-stu-id="2b511-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="2b511-108">Экспортталған сегменттердегі тұтынушылардың бірыңғай профильдері электрондық пошта мекенжайын көрсететін өрістен тұрады.</span><span class="sxs-lookup"><span data-stu-id="2b511-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="2b511-109">Белгілі шектеулер</span><span class="sxs-lookup"><span data-stu-id="2b511-109">Known limitations</span></span>

- <span data-ttu-id="2b511-110">Campaign Monitor қызметіне бір экспорттаған кезде 1 миллион профильді экспорттауға болады.</span><span class="sxs-lookup"><span data-stu-id="2b511-110">You can export up to 1 million profiles per export to Campaign Monitor.</span></span>
- <span data-ttu-id="2b511-111">Campaign Monitor қызметіне экспорттау сегменттермен шектеледі.</span><span class="sxs-lookup"><span data-stu-id="2b511-111">Exporting to Campaign Monitor is limited to segments.</span></span>
- <span data-ttu-id="2b511-112">Campaign Monitor қызметіне 1 миллионға дейінгі профильді экспорттауды аяқтау 20 минутқа созылуы мүмкін.</span><span class="sxs-lookup"><span data-stu-id="2b511-112">Exporting up to 1 million profiles to Campaign Monitor can take up to 20 minutes to complete.</span></span> 
- <span data-ttu-id="2b511-113">Campaign Monitor қызметіне экспорттауға болатын профильдер саны Campaign Monitor қызметімен келісімшартқа байланысты және шектеулі.</span><span class="sxs-lookup"><span data-stu-id="2b511-113">The number of profiles that you can export to Campaign Monitor is dependent and limited on your contract with Campaign Monitor.</span></span>

## <a name="set-up-connection-to-campaign-monitor"></a><span data-ttu-id="2b511-114">Campaign Monitor қызметіне қосылым орнату</span><span class="sxs-lookup"><span data-stu-id="2b511-114">Set up connection to Campaign Monitor</span></span>

1. <span data-ttu-id="2b511-115">**Әкімші** > **Қосылымдар** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="2b511-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="2b511-116">**Қосылым қосу** түймешігін таңдаңыз және қосылымды конфигурациялау үшін **Campaign Monitor** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="2b511-116">Select **Add connection** and choose **Campaign Monitor** to configure the connection.</span></span>

1. <span data-ttu-id="2b511-117">**Көрсетілетін аты** өрісінде қосылымға оңай танылатын атау енгізіңіз.</span><span class="sxs-lookup"><span data-stu-id="2b511-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="2b511-118">Қосылым атауы мен түрі осы қосылымды сипаттайды.</span><span class="sxs-lookup"><span data-stu-id="2b511-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="2b511-119">Қосылымның мақсатын түсіндіретін атауды таңдауды ұсынамыз.</span><span class="sxs-lookup"><span data-stu-id="2b511-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="2b511-120">Осы қосылымды кім пайдалана алатынын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="2b511-120">Choose who can use this connection.</span></span> <span data-ttu-id="2b511-121">Егер сіз ешқандай әрекет жасамасаңыз, әдепкі бойынша Әкімшілер болады.</span><span class="sxs-lookup"><span data-stu-id="2b511-121">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="2b511-122">Қосымша ақпарат алу үшін [Салымшыларға экспорттау үшін қосылымды пайдалануға рұқсат беру](connections.md#allow-contributors-to-use-a-connection-for-exports) бөлімін қараңыз.</span><span class="sxs-lookup"><span data-stu-id="2b511-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="2b511-123">**Деректер құпиялығы мен сәйкестігін** растау үшін **Мен келісемін** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="2b511-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="2b511-124">Campaign Monitor қызметіне қосылымды баптандыру үшін **Қосылу** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="2b511-124">Select **Connect** to initialize the connection to Campaign Monitor.</span></span>

1. <span data-ttu-id="2b511-125">**Campaign Monitor қызметімен аутентификациялау** опциясын таңдаңыз және Campaign Monitor қызметі үшін әкімші тіркелгі деректерін беріңіз.</span><span class="sxs-lookup"><span data-stu-id="2b511-125">Select **Authenticate with Campaign Monitor** and provide your admin credentials for Campaign Monitor.</span></span>

1. <span data-ttu-id="2b511-126">**Өзіңізді экспорт пайдаланушысы ретінде қосу** пәрменін таңдап, өзіңіздің Customer Insights тіркелгі деректерін ұсыныңыз.</span><span class="sxs-lookup"><span data-stu-id="2b511-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="2b511-127">Қосылымды аяқтау үшін **Сақтау** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="2b511-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="2b511-128">Экспорттауды конфигурациялау</span><span class="sxs-lookup"><span data-stu-id="2b511-128">Configure an export</span></span>

<span data-ttu-id="2b511-129">Егер сіз осы түрдегі қосылымға қатынаса алсаңыз, сіз бұл экспорттауды конфигурациялай аласыз.</span><span class="sxs-lookup"><span data-stu-id="2b511-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="2b511-130">Қосымша ақпарат алу үшін [Экспорттауды конфигурациялау үшін қажет рұқсаттар](export-destinations.md#set-up-a-new-export) бөлімін қараңыз.</span><span class="sxs-lookup"><span data-stu-id="2b511-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="2b511-131">**Деректер** > **Экспорттау** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="2b511-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="2b511-132">Жаңа экспорттау жасау үшін **Мақсатты орын қосу** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="2b511-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="2b511-133">**Экспорттауға арналған қосылым** өрісінде Campaign Monitor бөлімінен қосылым таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="2b511-133">In the **Connection for export** field, choose a connection from the Campaign Monitor section.</span></span> <span data-ttu-id="2b511-134">Егер сіз осы бөлімнің атын көрмесеңіз, сізге қолжетімді осы түрдегі қосылым жоқ.</span><span class="sxs-lookup"><span data-stu-id="2b511-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="2b511-135">[**Campaign Monitor тізімінің идентификаторын**](https://www.campaignmonitor.com/api/getting-started/#your-list-id) енгізіңіз.</span><span class="sxs-lookup"><span data-stu-id="2b511-135">Enter your [**Campaign Monitor List ID**](https://www.campaignmonitor.com/api/getting-started/#your-list-id).</span></span>    
   <span data-ttu-id="2b511-136">API тізімінің идентификаторын көру үшін алдымен Campaign Monitor қызметіндегі **Тіркелгі параметрлері** өрісінен [API кілтін жасаңыз](https://www.campaignmonitor.com/api/getting-started/).</span><span class="sxs-lookup"><span data-stu-id="2b511-136">[Generate the API key](https://www.campaignmonitor.com/api/getting-started/) from **Account Settings** in Campaign Monitor first to view the API list ID.</span></span>  

3. <span data-ttu-id="2b511-137">**Деректерді салыстыру** бөліміндегі **Электрондық пошта** өрісінде тұтынушының электрондық пошта мекенжайын көрсететін бірыңғай тұтынушы профиліндегі өрісті таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="2b511-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="2b511-138">Бұл Campaign Monitor қызметіне сегменттерді экспорттау үшін қажет.</span><span class="sxs-lookup"><span data-stu-id="2b511-138">It's required to export segments to Campaign Monitor.</span></span>

1. <span data-ttu-id="2b511-139">**Сақтау** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="2b511-139">Select **Save**.</span></span>

<span data-ttu-id="2b511-140">Экспорттауды сақтау экспорттауды бірден іске қоспайды.</span><span class="sxs-lookup"><span data-stu-id="2b511-140">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="2b511-141">Экспорттау әр [жоспарланған жаңартумен](system.md#schedule-tab) іске қосылады.</span><span class="sxs-lookup"><span data-stu-id="2b511-141">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="2b511-142">Сондай-ақ [деректерді сұрау бойынша экспорттауға](export-destinations.md#run-exports-on-demand) болады.</span><span class="sxs-lookup"><span data-stu-id="2b511-142">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="2b511-143">Деректердің құпиялылығы мен сәйкестігі</span><span class="sxs-lookup"><span data-stu-id="2b511-143">Data privacy and compliance</span></span>

<span data-ttu-id="2b511-144">Деректерді Campaign Monitor қызметіне тасымалдау үшін Dynamics 365 Customer Insights бағдарламасын қосқан кезде жеке деректер сияқты ықтимал құпия деректерді қоса алғанда, деректерді Dynamics 365 Customer Insights бағдарламасының үйлесімділік шегінен тыс тасымалдауға рұқсат бересіз.</span><span class="sxs-lookup"><span data-stu-id="2b511-144">When you enable Dynamics 365 Customer Insights to transmit data to Campaign Monitor, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="2b511-145">Microsoft корпорациясы мұндай деректерді сіздің нұсқауыңыз бойынша жібереді, бірақ сіз Campaign Monitor қызметінің кез-келген құпиялылық немесе қауіпсіздік міндеттемелерінің орындалуына кепілдік беретініне жауаптысыз.</span><span class="sxs-lookup"><span data-stu-id="2b511-145">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Campaign Monitor meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="2b511-146">Қосымша ақпаратты [Microsoft құпиялық туралы мәлімдемесі](https://go.microsoft.com/fwlink/?linkid=396732) бөлімінен қараңыз.</span><span class="sxs-lookup"><span data-stu-id="2b511-146">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="2b511-147">Бұл функцияны тоқтату үшін бұл экспорттау мақсатын кез келген уақытта Dynamics 365 Customer Insights әкімшісі жоя алады.</span><span class="sxs-lookup"><span data-stu-id="2b511-147">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
