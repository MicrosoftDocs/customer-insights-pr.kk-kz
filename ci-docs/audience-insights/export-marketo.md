---
title: Customer Insights деректерін Marketo платформасына экспорттау
description: Marketo қызметі үшін қосылымды конфигурациялау және экспорттау жолы туралы ақпарат.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: b5a644e286bd44d4ebf7d1837255326c005b48d6
ms.sourcegitcommit: 74cd4fa9cbb784d9dff174c0eec7b4dcb408d66b
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 05/18/2021
ms.locfileid: "6059323"
---
# <a name="export-segments-to-marketo-preview"></a><span data-ttu-id="9615f-103">Сегменттерді Marketo қызметіне экспорттау (алдын ала қарау нұсқасы)</span><span class="sxs-lookup"><span data-stu-id="9615f-103">Export segments to Marketo (preview)</span></span>

<span data-ttu-id="9615f-104">Науқандар жасау үшін тұтынушының біріңғай профильдерінің сегменттерін экспорттап, маркетинг бөліміне хат жіберіңіз және Marketo арқылы тұтынушылардың арнайы топтарын пайдаланыңыз.</span><span class="sxs-lookup"><span data-stu-id="9615f-104">Export segments of unified customer profiles to generate campaigns, provide email marketing and use specific groups of customers with Marketo.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="9615f-105">Қосылым алғышарттары</span><span class="sxs-lookup"><span data-stu-id="9615f-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="9615f-106">Сізде [Marketo тіркелгісі](https://login.marketo.com/) және тиісті әкімшінің тіркелгі деректері бар.</span><span class="sxs-lookup"><span data-stu-id="9615f-106">You have a [Marketo account](https://login.marketo.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="9615f-107">Marketo платформасында бұрыннан бар тізімдер және тиісті идентификаторлар бар.</span><span class="sxs-lookup"><span data-stu-id="9615f-107">There are existing lists in Marketo and the corresponding IDs.</span></span> <span data-ttu-id="9615f-108">Толық ақпарат алу үшін [Marketo тізімдерін](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists) қараңыз.</span><span class="sxs-lookup"><span data-stu-id="9615f-108">For more information, see [Marketo lists](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>
-   <span data-ttu-id="9615f-109">Сізде [конфигурацияланған сегменттер](segments.md) бар.</span><span class="sxs-lookup"><span data-stu-id="9615f-109">You have [configured segments](segments.md).</span></span>
-   <span data-ttu-id="9615f-110">Экспортталған сегменттердегі тұтынушылардың бірыңғай профильдері электрондық пошта мекенжайын көрсететін өрістен тұрады.</span><span class="sxs-lookup"><span data-stu-id="9615f-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="9615f-111">Белгілі шектеулер</span><span class="sxs-lookup"><span data-stu-id="9615f-111">Known limitations</span></span>

- <span data-ttu-id="9615f-112">Marketo нысанына 1 миллионға дейін профильді экспорттауға болады.</span><span class="sxs-lookup"><span data-stu-id="9615f-112">Up to 1 million profiles per export to Marketo.</span></span>
- <span data-ttu-id="9615f-113">Marketo нысанына экспорттау тек сегменттермен шектеледі.</span><span class="sxs-lookup"><span data-stu-id="9615f-113">Exporting to Marketo is limited to segments.</span></span>
- <span data-ttu-id="9615f-114">Жалпы саны 1 миллион профилі бар сегменттерді экспорттау 3 сағатқа созылуы мүмкін.</span><span class="sxs-lookup"><span data-stu-id="9615f-114">Exporting segments with a total of 1 million profiles can take up to 3 hours.</span></span> 
- <span data-ttu-id="9615f-115">Marketo платформасына экспорттауға болатын профильдер саны Marketo платформасымен жасалған келісім-шартқа байланысты және шектеулі.</span><span class="sxs-lookup"><span data-stu-id="9615f-115">The number of profiles that you can export to Marketo is dependent and limited on your contract with Marketo.</span></span>

## <a name="set-up-connection-to-marketo"></a><span data-ttu-id="9615f-116">Marketo қызметіне қосылым орнату</span><span class="sxs-lookup"><span data-stu-id="9615f-116">Set up connection to Marketo</span></span>

1. <span data-ttu-id="9615f-117">**Әкімші** > **Қосылымдар** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="9615f-117">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="9615f-118">**Қосылым қосу** түймешігін таңдаңыз және қосылымды конфигурациялау үшін **Marketo** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="9615f-118">Select **Add connection** and choose **Marketo** to configure the connection.</span></span>

1. <span data-ttu-id="9615f-119">**Көрсетілетін аты** өрісінде қосылымға оңай танылатын атау енгізіңіз.</span><span class="sxs-lookup"><span data-stu-id="9615f-119">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="9615f-120">Қосылым атауы мен түрі осы қосылымды сипаттайды.</span><span class="sxs-lookup"><span data-stu-id="9615f-120">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="9615f-121">Қосылымның мақсатын түсіндіретін атауды таңдауды ұсынамыз.</span><span class="sxs-lookup"><span data-stu-id="9615f-121">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="9615f-122">Осы қосылымды кім пайдалана алатынын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="9615f-122">Choose who can use this connection.</span></span> <span data-ttu-id="9615f-123">Егер сіз ешқандай әрекет жасамасаңыз, әдепкі бойынша Әкімшілер болады.</span><span class="sxs-lookup"><span data-stu-id="9615f-123">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="9615f-124">Қосымша ақпарат алу үшін [Салымшыларға экспорттау үшін қосылымды пайдалануға рұқсат беру](connections.md#allow-contributors-to-use-a-connection-for-exports) бөлімін қараңыз.</span><span class="sxs-lookup"><span data-stu-id="9615f-124">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="9615f-125">**[Marketo клиент идентификаторы, клиент құпиясы және REST соңғы хост атауын](https://developers.marketo.com/rest-api/authentication/)** енгізіңіз.</span><span class="sxs-lookup"><span data-stu-id="9615f-125">Enter your **[Marketo client ID, Client secret, and REST Endpoint Hostname](https://developers.marketo.com/rest-api/authentication/)**.</span></span> <span data-ttu-id="9615f-126">REST соңғы нүктесінің хост атауы тек хосттың атауы болып табылады, яғни `https://` префиксі жоқ.</span><span class="sxs-lookup"><span data-stu-id="9615f-126">The REST Endpoint Hostname is the hostname only, without `https://`.</span></span> <span data-ttu-id="9615f-127">Мысал:`xyz-abc-123.mktorest.com`.</span><span class="sxs-lookup"><span data-stu-id="9615f-127">Example: `xyz-abc-123.mktorest.com`.</span></span> 

1. <span data-ttu-id="9615f-128">**Деректер құпиялығы және сәйкестігін** растау үшін **Мен келісемін** пәрменін таңдаңыз және Marketo платформасына қосылуды баптандыру үшін **Қосылу** пәрменін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="9615f-128">Select **I agree** to confirm the **Data privacy and compliance** and select **Connect** to initialize the connection to Marketo.</span></span>

1. <span data-ttu-id="9615f-129">**Өзіңізді экспорт пайдаланушысы ретінде қосу** пәрменін таңдап, өзіңіздің Customer Insights тіркелгі деректерін ұсыныңыз.</span><span class="sxs-lookup"><span data-stu-id="9615f-129">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="9615f-130">Қосылымды аяқтау үшін **Сақтау** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="9615f-130">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="9615f-131">Экспорттауды конфигурациялау</span><span class="sxs-lookup"><span data-stu-id="9615f-131">Configure an export</span></span>

<span data-ttu-id="9615f-132">Егер сіз осы түрдегі қосылымға қатынаса алсаңыз, сіз бұл экспорттауды конфигурациялай аласыз.</span><span class="sxs-lookup"><span data-stu-id="9615f-132">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="9615f-133">Қосымша ақпарат алу үшін [Экспорттауды конфигурациялау үшін қажет рұқсаттар](export-destinations.md#set-up-a-new-export) бөлімін қараңыз.</span><span class="sxs-lookup"><span data-stu-id="9615f-133">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="9615f-134">**Деректер** > **Экспорттау** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="9615f-134">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="9615f-135">Жаңа экспорттау жасау үшін **Мақсатты орын қосу** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="9615f-135">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="9615f-136">**Экспорттауға арналған қосылым** өрісінде Marketo бөлімінен қосылым таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="9615f-136">In the **Connection for export** field, choose a connection from the Marketo section.</span></span> <span data-ttu-id="9615f-137">Егер сіз осы бөлімнің атын көрмесеңіз, сізге қолжетімді осы түрдегі қосылым жоқ.</span><span class="sxs-lookup"><span data-stu-id="9615f-137">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="9615f-138">**[Marketo тізімінің идентификаторын](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)** енгізіңіз.</span><span class="sxs-lookup"><span data-stu-id="9615f-138">Enter your **[Marketo list ID](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**.</span></span> <span data-ttu-id="9615f-139">Тізім идентификаторы — бұл тек сандық мән.</span><span class="sxs-lookup"><span data-stu-id="9615f-139">The list ID is a purely numerical value.</span></span> <span data-ttu-id="9615f-140">Мысалы, егер сіздің Marketo тізімінің идентификаторы ST12345A7 болса, сандарға дейінгі және кейінгі таңбаны алып тастаңыз және `12345` мәнін енгізіңіз.</span><span class="sxs-lookup"><span data-stu-id="9615f-140">For example, if your Marketo list ID is ST12345A7, remove the character before and after the numerals and enter `12345`.</span></span> 

1. <span data-ttu-id="9615f-141">**Деректерді салыстыру** бөліміндегі **Электрондық пошта** өрісінде тұтынушының электрондық пошта мекенжайын көрсететін бірыңғай тұтынушы профиліндегі өрісті таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="9615f-141">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="9615f-142">Қажет болса, жеке электрондық пошта хабарларын жасау үшін **Аты**, **Тегі**, **Қала**, **Штат** және **Ел/аймақ** өрістерін конфигурациялауға болады.</span><span class="sxs-lookup"><span data-stu-id="9615f-142">Optionally, you can export **First name**, **Last name**, **City**, **State**, and **Country/Region**  to create more personalized emails.</span></span> <span data-ttu-id="9615f-143">Осы өрістерді салыстыру үшін **Төлсипат қосу** пәрменін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="9615f-143">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="9615f-144">Экспорттау керек сегменттерді таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="9615f-144">Select the segments you want to export.</span></span> <span data-ttu-id="9615f-145">Marketo платформасына жалпы 1 миллионға дейін тұтынушы профилін экспорттай аласыз.</span><span class="sxs-lookup"><span data-stu-id="9615f-145">You can export up to 1 million customer profiles in total to Marketo.</span></span>

1. <span data-ttu-id="9615f-146">**Сақтау** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="9615f-146">Select **Save**.</span></span>

<span data-ttu-id="9615f-147">Экспорттауды сақтау экспорттауды бірден іске қоспайды.</span><span class="sxs-lookup"><span data-stu-id="9615f-147">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="9615f-148">Экспорттау әр [жоспарланған жаңартумен](system.md#schedule-tab) іске қосылады.</span><span class="sxs-lookup"><span data-stu-id="9615f-148">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="9615f-149">Сондай-ақ [деректерді сұрау бойынша экспорттауға](export-destinations.md#run-exports-on-demand) болады.</span><span class="sxs-lookup"><span data-stu-id="9615f-149">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> <span data-ttu-id="9615f-150">Marketo платформасында, өз сегменттеріңізді [Marketo аудиториялары](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists) астынан табуға болады.</span><span class="sxs-lookup"><span data-stu-id="9615f-150">In Marketo, you can now find your segments under [Marketo lists](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="9615f-151">Деректердің құпиялылығы мен сәйкестігі</span><span class="sxs-lookup"><span data-stu-id="9615f-151">Data privacy and compliance</span></span>

<span data-ttu-id="9615f-152">Деректерді Marketo платформасына жіберу үшін Dynamics 365 Customer Insights бағдарламасын қосқан кезде, Dynamics 365 Customer Insights талаптарына сәйкестік шекарасынан тыс деректерді, соның ішінде жеке деректер сияқты ықтимал құпия деректерді беруге мүмкіндік бересіз.</span><span class="sxs-lookup"><span data-stu-id="9615f-152">When you enable Dynamics 365 Customer Insights to transmit data to Marketo, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="9615f-153">Microsoft мұндай деректерді сіздің нұсқауыңыз бойынша тасымалдайды, бірақ Marketo платформасының кез келген құпиялылық немесе қауіпсіздік міндеттемелеріне сәйкес келуіне жауап бересіз.</span><span class="sxs-lookup"><span data-stu-id="9615f-153">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Marketo meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="9615f-154">Қосымша ақпаратты [Microsoft құпиялық туралы мәлімдемесі](https://go.microsoft.com/fwlink/?linkid=396732) бөлімінен қараңыз.</span><span class="sxs-lookup"><span data-stu-id="9615f-154">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="9615f-155">Бұл функцияны тоқтату үшін бұл экспорттау мақсатын кез келген уақытта Dynamics 365 Customer Insights әкімшісі жоя алады.</span><span class="sxs-lookup"><span data-stu-id="9615f-155">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
