---
title: Customer Insights деректерін Microsoft Advertising қызметіне экспорттау
description: Microsoft Advertising қызметі үшін қосылымды конфигурациялау және экспорттау жолы туралы ақпарат.
ms.date: 05/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c2ac92de2718cf7f0622b407bf198a7a7e50a37b
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124513"
---
# <a name="export-segments-to-microsoft-advertising-preview"></a><span data-ttu-id="bf887-103">Сегменттерді Microsoft Advertising (алдын ала қарау нұсқасы) қызметіне экспорттау</span><span class="sxs-lookup"><span data-stu-id="bf887-103">Export segments to Microsoft Advertising (preview)</span></span>

<span data-ttu-id="bf887-104">Customer Match аудиториясын жасау үшін Customer Insights сегменттерін Microsoft Advertising қызметіне экспорттаңыз.</span><span class="sxs-lookup"><span data-stu-id="bf887-104">Export Customer Insights segments to Microsoft Advertising to create Customer Match audiences.</span></span> <span data-ttu-id="bf887-105">Осы аудиторияны жарнамалық науқан үшін пайдаланыңыз.</span><span class="sxs-lookup"><span data-stu-id="bf887-105">Use these audiences for your ad campaigns.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="bf887-106">Алғышарттар</span><span class="sxs-lookup"><span data-stu-id="bf887-106">Prerequisites</span></span>

-   <span data-ttu-id="bf887-107">[Microsoft Advertising қызметінің тіркелгісі](https://ads.microsoft.com/) және тиісті әкімші тіркелгі деректері.</span><span class="sxs-lookup"><span data-stu-id="bf887-107">An [Microsoft Advertising account](https://ads.microsoft.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="bf887-108">Customer Match қызметінің пайдалану шарттарын қабылдадыңыз.</span><span class="sxs-lookup"><span data-stu-id="bf887-108">You've accepted the Customer Match terms of use.</span></span> 
-   <span data-ttu-id="bf887-109">Аудитория туралы пайдалы мәліметтердегі [конфигурацияланған сегменттер](segments.md).</span><span class="sxs-lookup"><span data-stu-id="bf887-109">[Configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="bf887-110">Экспортталған сегменттердегі тұтынушылардың бірыңғай профильдері электрондық пошта мекенжайы бар өрісті қамтиды.</span><span class="sxs-lookup"><span data-stu-id="bf887-110">Unified customer profiles in the exported segments contain a field with an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="bf887-111">Белгілі шектеулер</span><span class="sxs-lookup"><span data-stu-id="bf887-111">Known limitations</span></span>

- <span data-ttu-id="bf887-112">Microsoft Advertising қызметіне бір экспорттаған кезде 500000 профильді экспорттауға болады.</span><span class="sxs-lookup"><span data-stu-id="bf887-112">You can export up to 500 K profiles per export to Microsoft Advertising.</span></span>
- <span data-ttu-id="bf887-113">Microsoft Advertising қызметіне экспорттау сегменттермен шектеледі.</span><span class="sxs-lookup"><span data-stu-id="bf887-113">Exporting to Microsoft Advertising is limited to segments.</span></span>
- <span data-ttu-id="bf887-114">Microsoft Advertising қызметіне 500000 дейінгі профильді экспорттауды аяқтау 10 минутқа созылуы мүмкін.</span><span class="sxs-lookup"><span data-stu-id="bf887-114">Exporting up to 500 K profiles to Microsoft Advertising can take up to 10 minutes to complete.</span></span> 


## <a name="set-up-the-connection-to-microsoft-advertising"></a><span data-ttu-id="bf887-115">Microsoft Advertising қызметіне қосылым орнату</span><span class="sxs-lookup"><span data-stu-id="bf887-115">Set up the connection to Microsoft Advertising</span></span>

1. <span data-ttu-id="bf887-116">**Әкімші** > **Қосылымдар** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="bf887-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="bf887-117">**Қосылым қосу** түймешігін таңдаңыз және қосылымды конфигурациялау үшін **Microsoft Advertising** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="bf887-117">Select **Add connection** and choose **Microsoft Advertising** to configure the connection.</span></span>

1. <span data-ttu-id="bf887-118">**Көрсетілетін аты** өрісінде қосылымға оңай танылатын атау енгізіңіз.</span><span class="sxs-lookup"><span data-stu-id="bf887-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="bf887-119">Қосылым атауы мен түрі осы қосылымды сипаттайды.</span><span class="sxs-lookup"><span data-stu-id="bf887-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="bf887-120">Қосылымның мақсатын түсіндіретін атауды таңдауды ұсынамыз.</span><span class="sxs-lookup"><span data-stu-id="bf887-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="bf887-121">Осы қосылымды кім пайдалана алатынын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="bf887-121">Choose who can use this connection.</span></span> <span data-ttu-id="bf887-122">Әдепкі бойынша әкімшілер.</span><span class="sxs-lookup"><span data-stu-id="bf887-122">The default is administrators.</span></span> <span data-ttu-id="bf887-123">Қосымша ақпарат алу үшін [Салымшыларға экспорттау үшін қосылымды пайдалануға рұқсат беру](connections.md#allow-contributors-to-use-a-connection-for-exports) бөлімін қараңыз.</span><span class="sxs-lookup"><span data-stu-id="bf887-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="bf887-124">**Деректер құпиялығы мен сәйкестігін** растау үшін **Мен келісемін** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="bf887-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="bf887-125">Microsoft Advertising қызметіне қосылымды баптандыру үшін **Қосылу** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="bf887-125">Select **Connect** to initialize the connection to Microsoft Advertising.</span></span>

1. <span data-ttu-id="bf887-126">**Microsoft Advertising қызметімен аутентификациялау** опциясын таңдаңыз және Microsoft Advertising қызметі үшін әкімші тіркелгі деректерін беріңіз.</span><span class="sxs-lookup"><span data-stu-id="bf887-126">Select **Authenticate with Microsoft Advertising** and provide your admin credentials for Microsoft Advertising.</span></span>

1. <span data-ttu-id="bf887-127">**Өзіңізді экспорт пайдаланушысы ретінде қосу** пәрменін таңдап, өзіңіздің Customer Insights тіркелгі деректерін ұсыныңыз.</span><span class="sxs-lookup"><span data-stu-id="bf887-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="bf887-128">Қосылымды аяқтау үшін **Сақтау** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="bf887-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="bf887-129">Экспорттауды конфигурациялау</span><span class="sxs-lookup"><span data-stu-id="bf887-129">Configure an export</span></span>

<span data-ttu-id="bf887-130">Егер сіз осы түрдегі қосылымға қатынаса алсаңыз, сіз бұл экспорттауды конфигурациялай аласыз.</span><span class="sxs-lookup"><span data-stu-id="bf887-130">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="bf887-131">Қосымша ақпарат алу үшін [Экспорттауды конфигурациялау үшін қажет рұқсаттар](export-destinations.md#set-up-a-new-export) бөлімін қараңыз.</span><span class="sxs-lookup"><span data-stu-id="bf887-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="bf887-132">**Деректер** > **Экспорттау** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="bf887-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="bf887-133">Жаңа экспорттау жасау үшін **Мақсатты орын қосу** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="bf887-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="bf887-134">**Экспорттауға арналған қосылым** өрісінде Microsoft Advertising бөлімінен қосылым таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="bf887-134">In the **Connection for export** field, choose a connection from the Microsoft Advertising section.</span></span> <span data-ttu-id="bf887-135">Егер сіз осы бөлімнің атын көрмесеңіз, сізге қолжетімді осы түрдегі қосылым жоқ.</span><span class="sxs-lookup"><span data-stu-id="bf887-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="bf887-136">Экспорттайтын сегменттерді таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="bf887-136">Select the segments to export.</span></span> <span data-ttu-id="bf887-137">Microsoft Advertising қызметіндегі Customer Match аудиториялары экспорттау үшін таңдалған сегменттердің атауымен автоматты түрде жасалады.</span><span class="sxs-lookup"><span data-stu-id="bf887-137">The Customer Match audiences in Microsoft Advertising are automatically created with the name of the segments selected for export.</span></span> <span data-ttu-id="bf887-138">Әрбір сегмент бөлек Customer Match аудиториясына әкеледі.</span><span class="sxs-lookup"><span data-stu-id="bf887-138">Each segment will result in a separate Customer Match audience.</span></span> 

1. <span data-ttu-id="bf887-139">**Microsoft Advertising тұтынушы идентификаторы мен тіркелгі идентификаторын** енгізіңіз.</span><span class="sxs-lookup"><span data-stu-id="bf887-139">Enter your **Microsoft Advertising Customer ID and Account ID**.</span></span> <span data-ttu-id="bf887-140">Тұтынушы идентификаторы (`cid`) мен тіркелгі идентификаторын (`aid`) Microsoft Advertising қызметіне кірген кезде URL мекенжайының параметрлерінен табуға болады.</span><span class="sxs-lookup"><span data-stu-id="bf887-140">You can find the Customer ID (`cid`) and Account ID (`aid`) in the parameters of the URL when you're signed in Microsoft Advertising.</span></span>

1. <span data-ttu-id="bf887-141">**Деректерді сәйкестендіру** бөлімінде **Электрондық пошта** өрісінде тұтынушының электрондық пошта мекенжайы бар бірыңғай тұтынушы профиліндегі өрісті таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="bf887-141">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile with a customer's email address.</span></span> <span data-ttu-id="bf887-142">Бұл Microsoft Advertising қызметіне сегменттерді экспорттау үшін қажет.</span><span class="sxs-lookup"><span data-stu-id="bf887-142">It's required to export segments to Microsoft Advertising.</span></span>

1. <span data-ttu-id="bf887-143">**Сақтау** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="bf887-143">Select **Save**.</span></span>

<span data-ttu-id="bf887-144">Экспорттауды сақтау экспорттауды бірден іске қоспайды.</span><span class="sxs-lookup"><span data-stu-id="bf887-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="bf887-145">Экспорттау әр [жоспарланған жаңартумен](system.md#schedule-tab) іске қосылады.</span><span class="sxs-lookup"><span data-stu-id="bf887-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="bf887-146">Сондай-ақ [деректерді сұрау бойынша экспорттауға](export-destinations.md#run-exports-on-demand) болады.</span><span class="sxs-lookup"><span data-stu-id="bf887-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="bf887-147">Деректердің құпиялылығы мен сәйкестігі</span><span class="sxs-lookup"><span data-stu-id="bf887-147">Data privacy and compliance</span></span>

<span data-ttu-id="bf887-148">Деректерді Microsoft Advertising қызметіне тасымалдау үшін Dynamics 365 Customer Insights бағдарламасын қосқан кезде жеке деректер сияқты ықтимал құпия деректерді қоса алғанда, деректерді Dynamics 365 Customer Insights бағдарламасының үйлесімділік шегінен тыс тасымалдауға рұқсат бересіз.</span><span class="sxs-lookup"><span data-stu-id="bf887-148">When you enable Dynamics 365 Customer Insights to transmit data to Microsoft Advertising, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="bf887-149">Microsoft корпорациясы мұндай деректерді сіздің нұсқауыңыз бойынша жібереді, бірақ сіз Microsoft Advertising қызметінің кез келген құпиялылық немесе қауіпсіздік міндеттемелерінің орындалуына кепілдік беретініне жауаптысыз.</span><span class="sxs-lookup"><span data-stu-id="bf887-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Microsoft Advertising meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="bf887-150">Қосымша ақпаратты [Microsoft құпиялық туралы мәлімдемесі](https://go.microsoft.com/fwlink/?linkid=396732) бөлімінен қараңыз.</span><span class="sxs-lookup"><span data-stu-id="bf887-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="bf887-151">Dynamics 365 Customer Insights әкімшісі бұл функцияны тоқтату үшін бұл экспорттау мақсатын кез келген уақытта жоя алады.</span><span class="sxs-lookup"><span data-stu-id="bf887-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to stop use of this functionality.</span></span>
