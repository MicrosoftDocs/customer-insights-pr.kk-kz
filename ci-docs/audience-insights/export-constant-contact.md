---
title: Customer Insights деректерін Constant Contact қызметіне экспорттау
description: Constant Contact қызметі үшін қосылымды конфигурациялау және экспорттау жолы туралы ақпарат.
ms.date: 03/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 29f4320c798db62609283e3c48f0b47a4f0b982f
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124280"
---
# <a name="export-segments-to-constant-contact-preview"></a><span data-ttu-id="b960e-103">Сегменттерді Constant Contact қызметіне экспорттау (алдын ала қарау нұсқасы)</span><span class="sxs-lookup"><span data-stu-id="b960e-103">Export segments to Constant Contact (preview)</span></span>

<span data-ttu-id="b960e-104">Тұтынушылардың бірыңғай профильдерінің сегменттерін Constant Contact қызметіне экспорттаңыз және оларды маркетингтік әрекеттер үшін пайдаланыңыз.</span><span class="sxs-lookup"><span data-stu-id="b960e-104">Export segments of unified customer profiles to Constant Contact and use them for marketing activities.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="b960e-105">Қосылым алғышарттары</span><span class="sxs-lookup"><span data-stu-id="b960e-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="b960e-106">Сізде [Constant Contact қызметінің тіркелгісі](https://www.constantcontact.com/account-home) және тиісті әкімші тіркелгі деректері бар.</span><span class="sxs-lookup"><span data-stu-id="b960e-106">You have an [Constant Contact account](https://www.constantcontact.com/account-home) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="b960e-107">Аудитория түсініктерінде [конфигурацияланған сегменттер](segments.md) бар.</span><span class="sxs-lookup"><span data-stu-id="b960e-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="b960e-108">Экспортталған сегменттердегі тұтынушылардың бірыңғай профильдері электрондық пошта мекенжайын көрсететін өрістен тұрады.</span><span class="sxs-lookup"><span data-stu-id="b960e-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="b960e-109">Белгілі шектеулер</span><span class="sxs-lookup"><span data-stu-id="b960e-109">Known limitations</span></span>

- <span data-ttu-id="b960e-110">Constant Contact қызметіне бір экспорттаған кезде 1 миллион профильді экспорттауға болады.</span><span class="sxs-lookup"><span data-stu-id="b960e-110">You can export up to 1 million profiles per export to Constant Contact.</span></span>
- <span data-ttu-id="b960e-111">Constant Contact қызметіне экспорттау сегменттермен шектеледі.</span><span class="sxs-lookup"><span data-stu-id="b960e-111">Exporting to Constant Contact is limited to segments.</span></span>
- <span data-ttu-id="b960e-112">Constant Contact қызметіне 1 миллионға дейінгі профильді экспорттауды аяқтау 1 сағатқа созылуы мүмкін.</span><span class="sxs-lookup"><span data-stu-id="b960e-112">Exporting up to 1 million profiles to Constant Contact can take up to 1 hour to complete.</span></span> 
- <span data-ttu-id="b960e-113">Constant Contact қызметіне экспорттауға болатын профильдер саны Constant Contact қызметімен келісімшартқа байланысты және шектеулі.</span><span class="sxs-lookup"><span data-stu-id="b960e-113">The number of profiles that you can export to Constant Contact is dependent and limited on your contract with Constant Contact.</span></span>

## <a name="set-up-connection-to-constant-contact"></a><span data-ttu-id="b960e-114">Constant Contact қызметіне қосылым орнату</span><span class="sxs-lookup"><span data-stu-id="b960e-114">Set up connection to Constant Contact</span></span>

1. <span data-ttu-id="b960e-115">**Әкімші** > **Қосылымдар** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="b960e-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="b960e-116">**Қосылым қосу** түймешігін таңдаңыз және қосылымды конфигурациялау үшін **Constant Contact** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="b960e-116">Select **Add connection** and choose **Constant Contact** to configure the connection.</span></span>

1. <span data-ttu-id="b960e-117">**Көрсетілетін аты** өрісінде қосылымға оңай танылатын атау енгізіңіз.</span><span class="sxs-lookup"><span data-stu-id="b960e-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="b960e-118">Қосылым атауы мен түрі осы қосылымды сипаттайды.</span><span class="sxs-lookup"><span data-stu-id="b960e-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="b960e-119">Қосылымның мақсатын түсіндіретін атауды таңдауды ұсынамыз.</span><span class="sxs-lookup"><span data-stu-id="b960e-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="b960e-120">Осы қосылымды кім пайдалана алатынын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="b960e-120">Choose who can use this connection.</span></span> <span data-ttu-id="b960e-121">Егер сіз ешқандай әрекет жасамасаңыз, әдепкі бойынша Әкімшілер болады.</span><span class="sxs-lookup"><span data-stu-id="b960e-121">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="b960e-122">Қосымша ақпарат алу үшін [Салымшыларға экспорттау үшін қосылымды пайдалануға рұқсат беру](connections.md#allow-contributors-to-use-a-connection-for-exports) бөлімін қараңыз.</span><span class="sxs-lookup"><span data-stu-id="b960e-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="b960e-123">**Деректер құпиялығы мен сәйкестігін** растау үшін **Мен келісемін** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="b960e-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="b960e-124">Constant Contact қызметіне қосылымды баптандыру үшін **Қосылу** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="b960e-124">Select **Connect** to initialize the connection to Constant Contact.</span></span>

1. <span data-ttu-id="b960e-125">**AdRoll қызметімен аутентификациялау** опциясын таңдаңыз және Constant Contact қызметі үшін әкімші тіркелгі деректерін беріңіз.</span><span class="sxs-lookup"><span data-stu-id="b960e-125">Select **Authenticate with AdRoll** and provide your admin credentials for Constant Contact.</span></span> 

1. <span data-ttu-id="b960e-126">**Өзіңізді экспорт пайдаланушысы ретінде қосу** пәрменін таңдап, өзіңіздің Customer Insights тіркелгі деректерін ұсыныңыз.</span><span class="sxs-lookup"><span data-stu-id="b960e-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="b960e-127">Қосылымды аяқтау үшін **Сақтау** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="b960e-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="b960e-128">Экспорттауды конфигурациялау</span><span class="sxs-lookup"><span data-stu-id="b960e-128">Configure an export</span></span>

<span data-ttu-id="b960e-129">Егер сіз осы түрдегі қосылымға қатынаса алсаңыз, сіз бұл экспорттауды конфигурациялай аласыз.</span><span class="sxs-lookup"><span data-stu-id="b960e-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="b960e-130">Қосымша ақпарат алу үшін [Экспорттауды конфигурациялау үшін қажет рұқсаттар](export-destinations.md#set-up-a-new-export) бөлімін қараңыз.</span><span class="sxs-lookup"><span data-stu-id="b960e-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="b960e-131">**Деректер** > **Экспорттау** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="b960e-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="b960e-132">Жаңа экспорттау жасау үшін **Мақсатты орын қосу** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="b960e-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="b960e-133">**Экспорттауға арналған қосылым** өрісінде Constant Contact бөлімінен қосылым таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="b960e-133">In the **Connection for export** field, choose a connection from the Constant Contact section.</span></span> <span data-ttu-id="b960e-134">Егер сіз осы бөлімнің атын көрмесеңіз, сізге қолжетімді осы түрдегі қосылым жоқ.</span><span class="sxs-lookup"><span data-stu-id="b960e-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="b960e-135">[**Constant Contact тізімінің идентификаторын**](https://app.constantcontact.com/pages/contacts/ui#lists) енгізіңіз.</span><span class="sxs-lookup"><span data-stu-id="b960e-135">Enter your [**Constant Contact List ID**](https://app.constantcontact.com/pages/contacts/ui#lists).</span></span> <span data-ttu-id="b960e-136">URL мекенжайындағы тізім идентификаторын табу үшін Constant Contact қызметіндегі тізімді ашыңыз.</span><span class="sxs-lookup"><span data-stu-id="b960e-136">Open a list in Constant Contact to find the list ID in the URL.</span></span>

1. <span data-ttu-id="b960e-137">**Деректерді салыстыру** бөліміндегі **Электрондық пошта** өрісінде тұтынушының электрондық пошта мекенжайын көрсететін бірыңғай тұтынушы профиліндегі өрісті таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="b960e-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="b960e-138">Бұл Constant Contact қызметіне сегменттерді экспорттау үшін қажет.</span><span class="sxs-lookup"><span data-stu-id="b960e-138">It's required to export segments to Constant Contact.</span></span>

1. <span data-ttu-id="b960e-139">Сонымен қатар Аты және Тегі өрістерін қосымша жеке электрондық пошталар жасау үшін қосымша өрістер ретінде экспорттауға болады.</span><span class="sxs-lookup"><span data-stu-id="b960e-139">Optionally, you can export First name and Last name as additional fields to create more personalized emails.</span></span> <span data-ttu-id="b960e-140">Осы өрістерді салыстыру үшін **Төлсипат қосу** пәрменін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="b960e-140">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="b960e-141">Экспорттау керек сегменттерді таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="b960e-141">Select the segments you want to export.</span></span>

1. <span data-ttu-id="b960e-142">**Сақтау** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="b960e-142">Select **Save**.</span></span>

<span data-ttu-id="b960e-143">Экспорттауды сақтау экспорттауды бірден іске қоспайды.</span><span class="sxs-lookup"><span data-stu-id="b960e-143">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="b960e-144">Экспорттау әр [жоспарланған жаңартумен](system.md#schedule-tab) іске қосылады.</span><span class="sxs-lookup"><span data-stu-id="b960e-144">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="b960e-145">Сондай-ақ [деректерді сұрау бойынша экспорттауға](export-destinations.md#run-exports-on-demand) болады.</span><span class="sxs-lookup"><span data-stu-id="b960e-145">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="b960e-146">Деректердің құпиялылығы мен сәйкестігі</span><span class="sxs-lookup"><span data-stu-id="b960e-146">Data privacy and compliance</span></span>

<span data-ttu-id="b960e-147">Деректерді Constant Contact қызметіне тасымалдау үшін Dynamics 365 Customer Insights бағдарламасын қосқан кезде жеке деректер сияқты ықтимал құпия деректерді қоса алғанда, деректерді Dynamics 365 Customer Insights бағдарламасының үйлесімділік шегінен тыс тасымалдауға рұқсат бересіз.</span><span class="sxs-lookup"><span data-stu-id="b960e-147">When you enable Dynamics 365 Customer Insights to transmit data to Constant Contact, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="b960e-148">Microsoft корпорациясы мұндай деректерді сіздің нұсқауыңыз бойынша жібереді, бірақ сіз Constant Contact қызметінің кез келген құпиялылық немесе қауіпсіздік міндеттемелерінің орындалуына кепілдік беретініне жауаптысыз.</span><span class="sxs-lookup"><span data-stu-id="b960e-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Constant Contact meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="b960e-149">Қосымша ақпаратты [Microsoft құпиялық туралы мәлімдемесі](https://go.microsoft.com/fwlink/?linkid=396732) бөлімінен қараңыз.</span><span class="sxs-lookup"><span data-stu-id="b960e-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="b960e-150">Бұл функцияны тоқтату үшін бұл экспорттау мақсатын кез келген уақытта Dynamics 365 Customer Insights әкімшісі жоя алады.</span><span class="sxs-lookup"><span data-stu-id="b960e-150">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
