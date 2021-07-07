---
title: Customer Insights деректерін ActiveCampaign қызметіне экспорттау
description: ActiveCampaign қызметіне қосылымды және экспорттауды конфигурациялау жолы туралы ақпарат.
ms.date: 06/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6d85fa9836618e27f7f3da6ce17c07b4bc89e187
ms.sourcegitcommit: 057079532e31c12bac36f374857ba3dc847d6ad0
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 06/29/2021
ms.locfileid: "6314638"
---
# <a name="export-segments-to-activecampaign-preview"></a><span data-ttu-id="07c5a-103">Сегменттерді ActiveCampaign қызметіне экспорттау (алдын ала қарау нұсқасы)</span><span class="sxs-lookup"><span data-stu-id="07c5a-103">Export segments to ActiveCampaign (preview)</span></span>

<span data-ttu-id="07c5a-104">Бірыңғай тұтынушы профильдерінің сегменттерін ActiveCampaign қызметіне экспорттаңыз және оларды маркетингтік қызмет үшін пайдаланыңыз.</span><span class="sxs-lookup"><span data-stu-id="07c5a-104">Export segments of unified customer profiles to ActiveCampaign and use them for marketing activities.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="07c5a-105">Алғышарттар</span><span class="sxs-lookup"><span data-stu-id="07c5a-105">Prerequisites</span></span>

-   <span data-ttu-id="07c5a-106">Сізде [ActiveCampaign тіркелгісі](https://www.activecampaign.com/) және тиісті әкімші тіркелгі деректері бар.</span><span class="sxs-lookup"><span data-stu-id="07c5a-106">You have an [ActiveCampaign account](https://www.activecampaign.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="07c5a-107">Аудитория түсініктерінде [конфигурацияланған сегменттер](segments.md) бар.</span><span class="sxs-lookup"><span data-stu-id="07c5a-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="07c5a-108">Экспортталған сегменттердегі тұтынушылардың бірыңғай профильдері электрондық пошта мекенжайы бар өрісті қамтиды.</span><span class="sxs-lookup"><span data-stu-id="07c5a-108">Unified customer profiles in the exported segments contain a field with an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="07c5a-109">Белгілі шектеулер</span><span class="sxs-lookup"><span data-stu-id="07c5a-109">Known limitations</span></span>

- <span data-ttu-id="07c5a-110">ActiveCampaign қызметіне бір экспорттағанда 1 миллион профильді экспорттауға болады және оны аяқтау 90 минутқа созылуы мүмкін.</span><span class="sxs-lookup"><span data-stu-id="07c5a-110">You can export up to 1 million profiles per export to ActiveCampaign and it can take up to 90 minutes to complete.</span></span>
- <span data-ttu-id="07c5a-111">ActiveCampaign қызметіне экспорттау сегменттермен шектеледі.</span><span class="sxs-lookup"><span data-stu-id="07c5a-111">Exporting to ActiveCampaign is limited to segments.</span></span>
- <span data-ttu-id="07c5a-112">ActiveCampaign қызметіне экспорттауға болатын профильдер саны ActiveCampaign қызметімен келісімшартқа байланысты.</span><span class="sxs-lookup"><span data-stu-id="07c5a-112">The number of profiles that you can export to ActiveCampaign depends on your contract with ActiveCampaign.</span></span>

## <a name="set-up-connection-to-activecampaign"></a><span data-ttu-id="07c5a-113">ActiveCampaign қызметіне қосылым орнату</span><span class="sxs-lookup"><span data-stu-id="07c5a-113">Set up connection to ActiveCampaign</span></span>

1. <span data-ttu-id="07c5a-114">**Әкімші** > **Қосылымдар** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="07c5a-114">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="07c5a-115">**Қосылым қосу** түймешігін таңдаңыз және қосылымды конфигурациялау үшін **ActiveCampaign** қызметін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="07c5a-115">Select **Add connection** and choose **ActiveCampaign** to configure the connection.</span></span>

1. <span data-ttu-id="07c5a-116">**Көрсетілетін аты** өрісінде қосылымға оңай танылатын атау енгізіңіз.</span><span class="sxs-lookup"><span data-stu-id="07c5a-116">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="07c5a-117">Қосылым атауы мен түрі осы қосылымды сипаттайды.</span><span class="sxs-lookup"><span data-stu-id="07c5a-117">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="07c5a-118">Қосылымның мақсатын түсіндіретін атауды таңдауды ұсынамыз.</span><span class="sxs-lookup"><span data-stu-id="07c5a-118">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="07c5a-119">Осы қосылымды кім пайдалана алатынын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="07c5a-119">Choose who can use this connection.</span></span> <span data-ttu-id="07c5a-120">Әдепкі бойынша бұл тек әкімшілер.</span><span class="sxs-lookup"><span data-stu-id="07c5a-120">By default, it's only administrators.</span></span> <span data-ttu-id="07c5a-121">Қосымша ақпарат алу үшін [Салымшыларға экспорттау үшін қосылымды пайдалануға рұқсат беру](connections.md#allow-contributors-to-use-a-connection-for-exports) бөлімін қараңыз.</span><span class="sxs-lookup"><span data-stu-id="07c5a-121">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="07c5a-122">[ActiveCampaign API кілтін және REST соңғы нүктесінің хост атауын](https://help.activecampaign.com/hc/articles/207317590-Getting-started-with-the-API#how-to-obtain-your-activecampaign-api-url-and-key) енгізіңіз.</span><span class="sxs-lookup"><span data-stu-id="07c5a-122">Enter your [ActiveCampaign API Key and REST Endpoint Hostname](https://help.activecampaign.com/hc/articles/207317590-Getting-started-with-the-API#how-to-obtain-your-activecampaign-api-url-and-key).</span></span> <span data-ttu-id="07c5a-123">REST соңғы нүктесінің хост атауы тек хосттың атауы болып табылады, яғни https:// префиксі жоқ.</span><span class="sxs-lookup"><span data-stu-id="07c5a-123">The REST Endpoint Hostname is the hostname only, without https://.</span></span> 

1. <span data-ttu-id="07c5a-124">**Деректер құпиялығы мен сәйкестігін** растау үшін **Мен келісемін** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="07c5a-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="07c5a-125">ActiveCampaign қызметіне қосылымды баптандыру үшін **Қосылу** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="07c5a-125">Select **Connect** to initialize the connection to ActiveCampaign.</span></span>

1. <span data-ttu-id="07c5a-126">**Өзіңізді экспорт пайдаланушысы ретінде қосу** пәрменін таңдап, өзіңіздің Customer Insights тіркелгі деректерін ұсыныңыз.</span><span class="sxs-lookup"><span data-stu-id="07c5a-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="07c5a-127">Қосылымды аяқтау үшін **Сақтау** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="07c5a-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="07c5a-128">Экспорттауды конфигурациялау</span><span class="sxs-lookup"><span data-stu-id="07c5a-128">Configure an export</span></span>

<span data-ttu-id="07c5a-129">Егер сіз осы түрдегі қосылымға қатынаса алсаңыз, сіз экспорттауды конфигурациялай аласыз.</span><span class="sxs-lookup"><span data-stu-id="07c5a-129">You can configure an export if you have access to a connection of this type.</span></span> <span data-ttu-id="07c5a-130">Қосымша ақпарат алу үшін [Экспорттауды конфигурациялау үшін қажет рұқсаттар](export-destinations.md#set-up-a-new-export) бөлімін қараңыз.</span><span class="sxs-lookup"><span data-stu-id="07c5a-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="07c5a-131">**Деректер** > **Экспорттау** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="07c5a-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="07c5a-132">Жаңа экспорттау жасау үшін **Мақсатты орын қосу** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="07c5a-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="07c5a-133">**Экспорттауға арналған қосылым** өрісінде ActiveCampaign бөлімінен қосылым таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="07c5a-133">In the **Connection for export** field, choose a connection from the ActiveCampaign section.</span></span> <span data-ttu-id="07c5a-134">Егер сіз осы бөлімнің атын көрмесеңіз, сізге қолжетімді осы түрдегі қосылым жоқ.</span><span class="sxs-lookup"><span data-stu-id="07c5a-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="07c5a-135">[**ActiveCampaign тізім идентификаторын**](https://help.activecampaign.com/hc/articles/360000030559-How-to-create-a-list-in-ActiveCampaign) енгізіңіз.</span><span class="sxs-lookup"><span data-stu-id="07c5a-135">Enter your [**ActiveCampaign List ID**](https://help.activecampaign.com/hc/articles/360000030559-How-to-create-a-list-in-ActiveCampaign).</span></span>    

3. <span data-ttu-id="07c5a-136">**Деректерді салыстыру** бөліміндегі **Электрондық пошта** өрісінде тұтынушының электрондық пошта мекенжайын көрсететін бірыңғай тұтынушы профиліндегі өрісті таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="07c5a-136">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="07c5a-137">Сегменттерді ActiveCampaign қызметіне экспорттау қажет.</span><span class="sxs-lookup"><span data-stu-id="07c5a-137">It's required to export segments to ActiveCampaign.</span></span> <span data-ttu-id="07c5a-138">Таңдау бойынша жеке электронды хаттар жасау үшін аты, тегі және телефон өрістерін экспорттауға болады.</span><span class="sxs-lookup"><span data-stu-id="07c5a-138">Optionally, you can export First name, Last name, and Phone to create more personalized emails.</span></span> <span data-ttu-id="07c5a-139">Осы өрістерді салыстыру үшін Төлсипат қосу пәрменін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="07c5a-139">Select Add attribute to map these fields.</span></span>

1. <span data-ttu-id="07c5a-140">**Сақтау** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="07c5a-140">Select **Save**.</span></span>

<span data-ttu-id="07c5a-141">Экспорттауды сақтау экспорттауды бірден іске қоспайды.</span><span class="sxs-lookup"><span data-stu-id="07c5a-141">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="07c5a-142">Экспорттау әр [жоспарланған жаңартумен](system.md#schedule-tab) іске қосылады.</span><span class="sxs-lookup"><span data-stu-id="07c5a-142">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="07c5a-143">Сондай-ақ [деректерді сұрау бойынша экспорттауға](export-destinations.md#run-exports-on-demand) болады.</span><span class="sxs-lookup"><span data-stu-id="07c5a-143">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="07c5a-144">Деректердің құпиялылығы мен сәйкестігі</span><span class="sxs-lookup"><span data-stu-id="07c5a-144">Data privacy and compliance</span></span>

<span data-ttu-id="07c5a-145">Dynamics 365 Customer Insights бағдарламасын деректерді ActiveCampaign қызметіне тасымалдау үшін қосқан кезде, жеке деректер сияқты ықтимал құпия деректерді қоса алғанда сіз Dynamics 365 Customer Insights бағдарламасы үшін деректерді сәйкестік шекарасынан тыс тасымалдауға рұқсат бересіз.</span><span class="sxs-lookup"><span data-stu-id="07c5a-145">When you enable Dynamics 365 Customer Insights to transmit data to ActiveCampaign, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="07c5a-146">Microsoft мұндай деректерді сіздің нұсқауыңыз бойынша тасымалдайды, бірақ сіз ActiveCampaign қызметінің сізде болуы мүмкін кез келген құпиялылық немесе қауіпсіздік міндеттемелерін орындауын қамтамасыз етуіне жауаптысыз.</span><span class="sxs-lookup"><span data-stu-id="07c5a-146">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that ActiveCampaign meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="07c5a-147">Қосымша ақпаратты [Microsoft құпиялық туралы мәлімдемесі](https://go.microsoft.com/fwlink/?linkid=396732) бөлімінен қараңыз.</span><span class="sxs-lookup"><span data-stu-id="07c5a-147">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="07c5a-148">Бұл функцияны тоқтату үшін бұл экспорттау мақсатын кез келген уақытта Dynamics 365 Customer Insights әкімшісі жоя алады.</span><span class="sxs-lookup"><span data-stu-id="07c5a-148">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
