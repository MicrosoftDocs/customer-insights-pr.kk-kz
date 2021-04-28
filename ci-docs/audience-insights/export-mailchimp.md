---
title: Customer Insights деректерін Mailchimp нысанына экспорттау
description: Mailchimp қызметі үшін қосылымды конфигурациялау және экспорттау жолы туралы ақпарат.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: b94a8e8b6bb867ca04a64007d592b22fbd700618
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759885"
---
# <a name="export-segment-lists-to-mailchimp-preview"></a><span data-ttu-id="c8c42-103">Сегмент тізімдерін Mailchimp қызметіне экспорттау (алдын ала қарау нұсқасы)</span><span class="sxs-lookup"><span data-stu-id="c8c42-103">Export segment lists to Mailchimp (preview)</span></span>

<span data-ttu-id="c8c42-104">Ақпараттық хаттар мен электрондық пошта науқандарын құру үшін Mailchimp платформасына бірыңғай тұтынушы профильдерінің сегменттерін экспорттаңыз.</span><span class="sxs-lookup"><span data-stu-id="c8c42-104">Export segments of unified customer profiles to Mailchimp to create newsletters and email campaigns.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="c8c42-105">Қосылым алғышарттары</span><span class="sxs-lookup"><span data-stu-id="c8c42-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="c8c42-106">Сізде [Mailchimp тіркелгісі](https://mailchimp.com/) және тиісті әкімшінің тіркелгі деректері бар.</span><span class="sxs-lookup"><span data-stu-id="c8c42-106">You have a [Mailchimp account](https://mailchimp.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="c8c42-107">Mailchimp платформасында қолданыстағы аудиториялар және тиісті идентификаторлар бар.</span><span class="sxs-lookup"><span data-stu-id="c8c42-107">There are existing audiences in Mailchimp and the corresponding IDs.</span></span> <span data-ttu-id="c8c42-108">Қосымша ақпарат алу үшін [Mailchimp аудиториялары](https://mailchimp.com/help/create-audience/) бөлімін қараңыз.</span><span class="sxs-lookup"><span data-stu-id="c8c42-108">For more information, see [Mailchimp audiences](https://mailchimp.com/help/create-audience/).</span></span>
-   <span data-ttu-id="c8c42-109">Сізде [конфигурацияланған сегменттер](segments.md) бар</span><span class="sxs-lookup"><span data-stu-id="c8c42-109">You have [configured segments](segments.md)</span></span>
-   <span data-ttu-id="c8c42-110">Экспортталған сегменттердегі тұтынушылардың бірыңғай профильдері электрондық пошта мекенжайын көрсететін өрістен тұрады.</span><span class="sxs-lookup"><span data-stu-id="c8c42-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="c8c42-111">Белгілі шектеулер</span><span class="sxs-lookup"><span data-stu-id="c8c42-111">Known limitations</span></span>

- <span data-ttu-id="c8c42-112">Mailchimp нысанына 1 миллионға дейін профильді экспорттауға болады.</span><span class="sxs-lookup"><span data-stu-id="c8c42-112">Up to 1 million profiles per export to Mailchimp.</span></span>
- <span data-ttu-id="c8c42-113">Mailchimp нысанына экспорттау тек сегменттермен шектеледі.</span><span class="sxs-lookup"><span data-stu-id="c8c42-113">Exporting to Mailchimp is limited to segments.</span></span>
- <span data-ttu-id="c8c42-114">1 миллион профилі бар сегменттерді экспорттау үш сағатқа созылуы мүмкін.</span><span class="sxs-lookup"><span data-stu-id="c8c42-114">Exporting segments with 1 million profiles can take up to three hours.</span></span> 
- <span data-ttu-id="c8c42-115">Mailchimp нысанына экспорттауға болатын профильдер саны Mailchimp нысанымен жасалған келісім-шартқа байланысты және шектеулі.</span><span class="sxs-lookup"><span data-stu-id="c8c42-115">The number of profiles that you can export to Mailchimp is dependent and limited on your contract with Mailchimp.</span></span>

## <a name="set-up-connection-to-mailchimp"></a><span data-ttu-id="c8c42-116">Mailchimp қызметіне қосылым орнату</span><span class="sxs-lookup"><span data-stu-id="c8c42-116">Set up connection to Mailchimp</span></span>

1. <span data-ttu-id="c8c42-117">**Әкімші** > **Қосылымдар** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="c8c42-117">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="c8c42-118">**Қосылым қосу** түймешігін таңдаңыз және қосылымды конфигурациялау үшін **Autopilot** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="c8c42-118">Select **Add connection** and choose **Autopilot** to configure the connection.</span></span>

1. <span data-ttu-id="c8c42-119">**Көрсетілетін аты** өрісінде қосылымға оңай танылатын атау енгізіңіз.</span><span class="sxs-lookup"><span data-stu-id="c8c42-119">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="c8c42-120">Қосылым атауы мен түрі осы қосылымды сипаттайды.</span><span class="sxs-lookup"><span data-stu-id="c8c42-120">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="c8c42-121">Қосылымның мақсатын түсіндіретін атауды таңдауды ұсынамыз.</span><span class="sxs-lookup"><span data-stu-id="c8c42-121">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="c8c42-122">Осы қосылымды кім пайдалана алатынын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="c8c42-122">Choose who can use this connection.</span></span> <span data-ttu-id="c8c42-123">Егер сіз ешқандай әрекет жасамасаңыз, әдепкі бойынша Әкімшілер болады.</span><span class="sxs-lookup"><span data-stu-id="c8c42-123">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="c8c42-124">Қосымша ақпарат алу үшін [Салымшыларға экспорттау үшін қосылымды пайдалануға рұқсат беру](connections.md#allow-contributors-to-use-a-connection-for-exports) бөлімін қараңыз.</span><span class="sxs-lookup"><span data-stu-id="c8c42-124">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="c8c42-125">**Деректер құпиялығы мен сәйкестігін** растау үшін **Мен келісемін** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="c8c42-125">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="c8c42-126">Mailchimp қызметіне қосылымды баптандыру үшін **Қосылу** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="c8c42-126">Select **Connect** to initialize the connection to Mailchimp.</span></span>

1. <span data-ttu-id="c8c42-127">**Mailchimp көмегімен аутентификациялау** пәрменін таңдап, Mailchimp тіркелгі деректерін ұсыныңыз.</span><span class="sxs-lookup"><span data-stu-id="c8c42-127">Select **Authenticate with Mailchimp** and provide your Mailchimp credentials.</span></span>

1. <span data-ttu-id="c8c42-128">**Өзіңізді экспорт пайдаланушысы ретінде қосу** пәрменін таңдап, өзіңіздің Customer Insights тіркелгі деректерін ұсыныңыз.</span><span class="sxs-lookup"><span data-stu-id="c8c42-128">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="c8c42-129">Қосылымды аяқтау үшін **Сақтау** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="c8c42-129">Select **Save** to complete the connection.</span></span> 

## <a name="configure-the-connector"></a><span data-ttu-id="c8c42-130">Қосқышты конфигурациялау</span><span class="sxs-lookup"><span data-stu-id="c8c42-130">Configure the connector</span></span>

<span data-ttu-id="c8c42-131">Егер сіз осы түрдегі қосылымға қатынаса алсаңыз, сіз бұл экспорттауды конфигурациялай аласыз.</span><span class="sxs-lookup"><span data-stu-id="c8c42-131">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="c8c42-132">Қосымша ақпарат алу үшін [Экспорттауды конфигурациялау үшін қажет рұқсаттар](export-destinations.md#set-up-a-new-export) бөлімін қараңыз.</span><span class="sxs-lookup"><span data-stu-id="c8c42-132">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="c8c42-133">**Деректер**> **Экспорттау** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="c8c42-133">Go to **Data**> **Exports**.</span></span>

1. <span data-ttu-id="c8c42-134">Жаңа экспорттау жасау үшін **Мақсатты орын қосу** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="c8c42-134">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="c8c42-135">**Экспорттауға арналған қосылым** өрісінде Mailchimp бөлімінен қосылым таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="c8c42-135">In the **Connection for export** field, choose a connection from the Mailchimp section.</span></span> <span data-ttu-id="c8c42-136">Егер сіз осы бөлімнің атын көрмесеңіз, сізге қолжетімді осы түрдегі қосылым жоқ.</span><span class="sxs-lookup"><span data-stu-id="c8c42-136">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="c8c42-137">**[Mailchimp аудитория идентификаторын](https://mailchimp.com/help/find-audience-id/)** енгізіңіз</span><span class="sxs-lookup"><span data-stu-id="c8c42-137">Enter your **[Mailchimp audience ID](https://mailchimp.com/help/find-audience-id/)**</span></span>

3. <span data-ttu-id="c8c42-138">**Деректерді салыстыру** бөліміндегі **Электрондық пошта** өрісінде тұтынушының электрондық пошта мекенжайын көрсететін бірыңғай тұтынушы профиліндегі өрісті таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="c8c42-138">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="c8c42-139">Қажет болса, жеке электрондық пошта хабарларын жасау үшін **Аты** және **Тегі** өрістерін конфигурациялауға болады.</span><span class="sxs-lookup"><span data-stu-id="c8c42-139">Optionally, you can export **First name** and **Last name** to create more personalized emails.</span></span> <span data-ttu-id="c8c42-140">Осы өрістерді салыстыру үшін **Төлсипат қосу** пәрменін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="c8c42-140">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="c8c42-141">Экспорттау керек сегменттерді таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="c8c42-141">Select the segments you want to export.</span></span> <span data-ttu-id="c8c42-142">Mailchimp платформасына жалпы 1 миллионға дейін тұтынушы профилін экспорттай аласыз.</span><span class="sxs-lookup"><span data-stu-id="c8c42-142">You can export up to 1 million customer profiles in total to Mailchimp.</span></span>

1. <span data-ttu-id="c8c42-143">**Сақтау** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="c8c42-143">Select **Save**.</span></span>

<span data-ttu-id="c8c42-144">Экспорттауды сақтау экспорттауды бірден іске қоспайды.</span><span class="sxs-lookup"><span data-stu-id="c8c42-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="c8c42-145">Экспорттау әр [жоспарланған жаңартумен](system.md#schedule-tab) іске қосылады.</span><span class="sxs-lookup"><span data-stu-id="c8c42-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="c8c42-146">Сондай-ақ [деректерді сұрау бойынша экспорттауға](export-destinations.md#run-exports-on-demand) болады.</span><span class="sxs-lookup"><span data-stu-id="c8c42-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="c8c42-147">Деректердің құпиялылығы мен сәйкестігі</span><span class="sxs-lookup"><span data-stu-id="c8c42-147">Data privacy and compliance</span></span>

<span data-ttu-id="c8c42-148">Деректерді Mailchimp платформасына жіберу үшін Dynamics 365 Customer Insights бағдарламасын қосқан кезде, Dynamics 365 Customer Insights талаптарына сәйкестік шекарасынан тыс деректерді, соның ішінде жеке деректер сияқты ықтимал құпия деректерді беруге мүмкіндік бересіз.</span><span class="sxs-lookup"><span data-stu-id="c8c42-148">When you enable Dynamics 365 Customer Insights to transmit data to Mailchimp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="c8c42-149">Microsoft мұндай деректерді сіздің нұсқауыңыз бойынша тасымалдайды, бірақ Mailchimp платформасының кез келген құпиялылық немесе қауіпсіздік міндеттемелеріне сәйкес келуіне жауап бересіз.</span><span class="sxs-lookup"><span data-stu-id="c8c42-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Mailchimp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="c8c42-150">Қосымша ақпаратты [Microsoft құпиялық туралы мәлімдемесі](https://go.microsoft.com/fwlink/?linkid=396732) бөлімінен қараңыз.</span><span class="sxs-lookup"><span data-stu-id="c8c42-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="c8c42-151">Бұл функцияны тоқтату үшін бұл экспорттау мақсатын кез келген уақытта Dynamics 365 Customer Insights әкімшісі жоя алады.</span><span class="sxs-lookup"><span data-stu-id="c8c42-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
