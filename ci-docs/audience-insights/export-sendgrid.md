---
title: Customer Insights деректерін SendGrid нысанына экспорттау
description: SendGrid қызметі үшін қосылымды конфигурациялау және экспорттау жолы туралы ақпарат.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 5d3d61d2b5b68079c7717e41dee5a2f698f2b62c
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976923"
---
# <a name="export-segments-to-sendgrid-preview"></a><span data-ttu-id="00ad8-103">Сегменттерді SendGrid қызметіне экспорттау (алдын ала қарау нұсқасы)</span><span class="sxs-lookup"><span data-stu-id="00ad8-103">Export segments to SendGrid (preview)</span></span>

<span data-ttu-id="00ad8-104">Тұтынушылардың бірыңғай профильдерінің сегменттерін Autopilot контактілер тізіміне экспорттап, оларды SendGrid жүйесіндегі науқандар мен электрондық пошта маркетингі үшін пайдаланыңыз.</span><span class="sxs-lookup"><span data-stu-id="00ad8-104">Export segments of unified customer profiles to SendGrid contact lists and use them for campaigns and email marketing in SendGrid.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="00ad8-105">Қосылым алғышарттары</span><span class="sxs-lookup"><span data-stu-id="00ad8-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="00ad8-106">Сізде [SendGrid тіркелгісі](https://sendgrid.com/) және тиісті әкімшінің тіркелгі деректері бар.</span><span class="sxs-lookup"><span data-stu-id="00ad8-106">You have a [SendGrid account](https://sendgrid.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="00ad8-107">SendGrid платформасында бұрыннан бар контактілер тізімдері және тиісті идентификаторлар бар.</span><span class="sxs-lookup"><span data-stu-id="00ad8-107">There are existing contact lists in SendGrid and the corresponding IDs.</span></span> <span data-ttu-id="00ad8-108">Қосымша ақпарат алу үшін [SendGrid - Контактілерді басқару](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts) бөлімін қараңыз.</span><span class="sxs-lookup"><span data-stu-id="00ad8-108">For more information, see [SendGrid - Manage contacts](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).</span></span>
-   <span data-ttu-id="00ad8-109">Аудитория түсініктерінде [конфигурацияланған сегменттер](segments.md) бар.</span><span class="sxs-lookup"><span data-stu-id="00ad8-109">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="00ad8-110">Экспортталған сегменттердегі тұтынушылардың бірыңғай профильдері электрондық пошта мекенжайын көрсететін өрістен тұрады.</span><span class="sxs-lookup"><span data-stu-id="00ad8-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="00ad8-111">Белгілі шектеулер</span><span class="sxs-lookup"><span data-stu-id="00ad8-111">Known limitations</span></span>

- <span data-ttu-id="00ad8-112">SendGrid жүйесінде барлығы 100000 профильге дейін.</span><span class="sxs-lookup"><span data-stu-id="00ad8-112">Up to 100'000 profiles in total to SendGrid.</span></span>
- <span data-ttu-id="00ad8-113">SendGrid нысанына экспорттау тек сегменттермен шектеледі.</span><span class="sxs-lookup"><span data-stu-id="00ad8-113">Exporting to SendGrid is limited to segments.</span></span>
- <span data-ttu-id="00ad8-114">SendGrid жүйесіне 100000 дейін профильді экспорттау бірнеше сағатқа созылуы мүмкін.</span><span class="sxs-lookup"><span data-stu-id="00ad8-114">Exporting up to 100'000 profiles to SendGrid can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="00ad8-115">SendGrid нысанына экспорттауға болатын профильдер саны SendGrid нысанымен жасалған келісімшартқа байланысты және шектеулі.</span><span class="sxs-lookup"><span data-stu-id="00ad8-115">The number of profiles that you can export to SendGrid is dependent and limited on your contract with SendGrid.</span></span>

## <a name="set-up-connection-to-sendgrid"></a><span data-ttu-id="00ad8-116">SendGrid қызметіне қосылым орнату</span><span class="sxs-lookup"><span data-stu-id="00ad8-116">Set up connection to SendGrid</span></span>

1. <span data-ttu-id="00ad8-117">**Әкімші** > **Қосылымдар** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="00ad8-117">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="00ad8-118">**Қосылым қосу** түймешігін таңдаңыз және қосылымды конфигурациялау үшін **SendGrid** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="00ad8-118">Select **Add connection** and choose **SendGrid** to configure the connection.</span></span>

1. <span data-ttu-id="00ad8-119">**Көрсетілетін аты** өрісінде қосылымға оңай танылатын атау енгізіңіз.</span><span class="sxs-lookup"><span data-stu-id="00ad8-119">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="00ad8-120">Қосылым атауы мен түрі осы қосылымды сипаттайды.</span><span class="sxs-lookup"><span data-stu-id="00ad8-120">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="00ad8-121">Қосылымның мақсатын түсіндіретін атауды таңдауды ұсынамыз.</span><span class="sxs-lookup"><span data-stu-id="00ad8-121">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="00ad8-122">Осы қосылымды кім пайдалана алатынын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="00ad8-122">Choose who can use this connection.</span></span> <span data-ttu-id="00ad8-123">Егер сіз ешқандай әрекет жасамасаңыз, әдепкі бойынша Әкімшілер болады.</span><span class="sxs-lookup"><span data-stu-id="00ad8-123">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="00ad8-124">Қосымша ақпарат алу үшін [Салымшыларға экспорттау үшін қосылымды пайдалануға рұқсат беру](connections.md#allow-contributors-to-use-a-connection-for-exports) бөлімін қараңыз.</span><span class="sxs-lookup"><span data-stu-id="00ad8-124">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="00ad8-125">**SendGrid API кілтін** [SendGrid API кілті](https://sendgrid.com/docs/ui/account-and-settings/api-keys/) енгізіңіз.</span><span class="sxs-lookup"><span data-stu-id="00ad8-125">Enter your **SendGrid API key** [SendGrid API key](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).</span></span>

1. <span data-ttu-id="00ad8-126">**Деректер құпиялығы мен сәйкестігін** растау үшін **Мен келісемін** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="00ad8-126">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="00ad8-127">SendGrid қосылымын баптандыру үшін **Қосылу** пәрменін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="00ad8-127">Select **Connect** to initialize the connection to SendGrid.</span></span>

1. <span data-ttu-id="00ad8-128">**Өзіңізді экспорт пайдаланушысы ретінде қосу** пәрменін таңдап, өзіңіздің Customer Insights тіркелгі деректерін ұсыныңыз.</span><span class="sxs-lookup"><span data-stu-id="00ad8-128">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="00ad8-129">Қосылымды аяқтау үшін **Сақтау** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="00ad8-129">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="00ad8-130">Экспорттауды конфигурациялау</span><span class="sxs-lookup"><span data-stu-id="00ad8-130">Configure an export</span></span>

<span data-ttu-id="00ad8-131">Егер сіз осы түрдегі қосылымға қатынаса алсаңыз, сіз бұл экспорттауды конфигурациялай аласыз.</span><span class="sxs-lookup"><span data-stu-id="00ad8-131">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="00ad8-132">Қосымша ақпарат алу үшін [Экспорттауды конфигурациялау үшін қажет рұқсаттар](export-destinations.md#set-up-a-new-export) бөлімін қараңыз.</span><span class="sxs-lookup"><span data-stu-id="00ad8-132">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="00ad8-133">**Деректер** > **Экспорттау** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="00ad8-133">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="00ad8-134">Жаңа экспорттау жасау үшін **Мақсатты орын қосу** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="00ad8-134">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="00ad8-135">**Экспорттауға арналған қосылым** өрісінде SendGrid бөлімінен қосылым таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="00ad8-135">In the **Connection for export** field, choose a connection from the SendGrid section.</span></span> <span data-ttu-id="00ad8-136">Егер сіз осы бөлімнің атын көрмесеңіз, сізге қолжетімді осы түрдегі қосылым жоқ.</span><span class="sxs-lookup"><span data-stu-id="00ad8-136">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="00ad8-137">**[SendGrid тізімінің идентификаторын](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)** енгізіңіз.</span><span class="sxs-lookup"><span data-stu-id="00ad8-137">Enter your **[SendGrid list ID](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.</span></span>

1. <span data-ttu-id="00ad8-138">**Деректерді салыстыру** бөліміндегі **Электрондық пошта** өрісінде тұтынушының электрондық пошта мекенжайын көрсететін бірыңғай тұтынушы профиліндегі өрісті таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="00ad8-138">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="00ad8-139">**Аты**, **Тегі**, **Ел/аймақ**, **Облыс**, **Қала** және **Пошта индексі** секілді басқа қосымша өрістер үшін сол қадамдарды қайталаңыз.</span><span class="sxs-lookup"><span data-stu-id="00ad8-139">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Country/Region**, **State**, **City**, and **Post code**.</span></span>

1. <span data-ttu-id="00ad8-140">Экспорттау керек сегменттерді таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="00ad8-140">Select the segments you want to export.</span></span> <span data-ttu-id="00ad8-141">Біз SendGrid жүйесіне **100000-нан астам тұтынушы профильдерін экспорттамауға кеңес береміз**.</span><span class="sxs-lookup"><span data-stu-id="00ad8-141">We strongly **recommend to not export more than 100'000 customer profiles in total** to SendGrid.</span></span> 

1. <span data-ttu-id="00ad8-142">**Сақтау** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="00ad8-142">Select **Save**.</span></span>

<span data-ttu-id="00ad8-143">Экспорттауды сақтау экспорттауды бірден іске қоспайды.</span><span class="sxs-lookup"><span data-stu-id="00ad8-143">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="00ad8-144">Экспорттау әр [жоспарланған жаңартумен](system.md#schedule-tab) іске қосылады.</span><span class="sxs-lookup"><span data-stu-id="00ad8-144">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="00ad8-145">Сондай-ақ [деректерді сұрау бойынша экспорттауға](export-destinations.md#run-exports-on-demand) болады.</span><span class="sxs-lookup"><span data-stu-id="00ad8-145">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="00ad8-146">Деректердің құпиялылығы мен сәйкестігі</span><span class="sxs-lookup"><span data-stu-id="00ad8-146">Data privacy and compliance</span></span>

<span data-ttu-id="00ad8-147">Деректерді SendGrid платформасына жіберу үшін Dynamics 365 Customer Insights бағдарламасын қосқан кезде, Dynamics 365 Customer Insights талаптарына сәйкестік шекарасынан тыс деректерді, соның ішінде жеке деректер сияқты ықтимал құпия деректерді беруге мүмкіндік бересіз.</span><span class="sxs-lookup"><span data-stu-id="00ad8-147">When you enable Dynamics 365 Customer Insights to transmit data to SendGrid, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="00ad8-148">Microsoft мұндай деректерді сіздің нұсқауыңыз бойынша тасымалдайды, бірақ SendGrid кез келген құпиялылық немесе қауіпсіздік міндеттемелеріне сәйкес келуіне жауап бересіз.</span><span class="sxs-lookup"><span data-stu-id="00ad8-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that SendGrid meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="00ad8-149">Қосымша ақпаратты [Microsoft құпиялық туралы мәлімдемесі](https://go.microsoft.com/fwlink/?linkid=396732) бөлімінен қараңыз.</span><span class="sxs-lookup"><span data-stu-id="00ad8-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="00ad8-150">Бұл функцияны тоқтату үшін бұл экспорттау мақсатын кез келген уақытта Dynamics 365 Customer Insights әкімшісі жоя алады.</span><span class="sxs-lookup"><span data-stu-id="00ad8-150">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]