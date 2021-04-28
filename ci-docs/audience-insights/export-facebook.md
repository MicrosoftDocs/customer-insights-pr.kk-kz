---
title: Customer Insights деректерін Facebook жарнама менеджеріне экспорттау
description: Facebook Ads Manager қызметі үшін қосылымды конфигурациялау және экспорттау жолы туралы ақпарат.
ms.date: 04/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ca32906a98bc734639fb369d6f5a92e8888fd850
ms.sourcegitcommit: 6d5dd572f75ba4c0303ec77c3b74e4318d52705c
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 04/16/2021
ms.locfileid: "5906817"
---
# <a name="export-segments-list-to-facebook-ads-manager-preview"></a><span data-ttu-id="df8b0-103">Сегменттер тізімін Facebook Ads Manager қызметіне экспорттау (алдын ала қарау нұсқасы)</span><span class="sxs-lookup"><span data-stu-id="df8b0-103">Export segments list to Facebook Ads Manager (preview)</span></span>

<span data-ttu-id="df8b0-104">Facebook және Instagram желісінде науқандар жасау үшін Facebook жарнамалар менеджеріне біріккен тұтынушы профильдерінің сегменттерін экспорттаңыз.</span><span class="sxs-lookup"><span data-stu-id="df8b0-104">Export segments of unified customer profiles to Facebook Ads Manager to create campaigns on Facebook and Instagram.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="df8b0-105">Қосылым алғышарттары</span><span class="sxs-lookup"><span data-stu-id="df8b0-105">Prerequisites for connection</span></span>

- <span data-ttu-id="df8b0-106">Сізде [**Facebook бизнес тіркелгісін**](https://business.facebook.com/) қамтитын [**Facebook жарнама тіркелгісі**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) болуы керек.</span><span class="sxs-lookup"><span data-stu-id="df8b0-106">You need to have a [**Facebook Ad Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) that includes a [**Facebook Business Account**](https://business.facebook.com/).</span></span>
- <span data-ttu-id="df8b0-107">[**Facebook жарнама тіркелгісінде**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) әкімші болуыңыз керек.</span><span class="sxs-lookup"><span data-stu-id="df8b0-107">You need to be an administrator on the [**Facebook Ad Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="df8b0-108">Белгілі шектеулер</span><span class="sxs-lookup"><span data-stu-id="df8b0-108">Known limitations</span></span>

- <span data-ttu-id="df8b0-109">Facebook Ads Manager қызметінде бір экспорттауда 10 миллионға дейінгі тұтынушы профилі.</span><span class="sxs-lookup"><span data-stu-id="df8b0-109">Up to 10 million customer profile per export to Facebook Ads Manager.</span></span>
- <span data-ttu-id="df8b0-110">Facebook Ads Manager қызметіне экспорттау сегменттермен шектеледі.</span><span class="sxs-lookup"><span data-stu-id="df8b0-110">Export to Facebook Ads Manager is limited to segments.</span></span>
- <span data-ttu-id="df8b0-111">Тек *тұтынушы тізімі* түріндегі Facebook қызметінде аудиториялар жасаңыз немесе реттелетін аудиторияларды жаңартыңыз.</span><span class="sxs-lookup"><span data-stu-id="df8b0-111">Create or update custom audiences in Facebook of type *customer list* only.</span></span>
- <span data-ttu-id="df8b0-112">Жалпы саны 10 миллион профилі бар сегменттерді экспорттауды аяқтау 90 минутқа созылуы мүмкін.</span><span class="sxs-lookup"><span data-stu-id="df8b0-112">Exporting segments with a total of 10 million profiles can take up to 90 minutes to complete.</span></span>

## <a name="set-up-connection-to-facebook-ads-manager"></a><span data-ttu-id="df8b0-113">Facebook Ads Manager қызметіне қосылым орнату</span><span class="sxs-lookup"><span data-stu-id="df8b0-113">Set up connection to Facebook Ads Manager</span></span>

<span data-ttu-id="df8b0-114">Пайдаланушылар экспорттауды жасамас бұрын, әкімші қызметке қосылымды конфигурациялап, салымшыларға қосылымды пайдалануға рұқсат беруі керек.</span><span class="sxs-lookup"><span data-stu-id="df8b0-114">Before users can create an export, an administrator must configure the connection to the service and allow contributors to use the connection.</span></span>

1. <span data-ttu-id="df8b0-115">**Әкімші** > **Қосылымдар** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="df8b0-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="df8b0-116">**Қосылым қосу** түймешігін таңдаңыз және қосылымды конфигурациялау үшін **Facebook Ads Manager** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="df8b0-116">Select **Add connection** and choose **Facebook Ads Manager** to configure the connection.</span></span>

1. <span data-ttu-id="df8b0-117">**Көрсетілетін аты** өрісінде қосылымға оңай танылатын атау енгізіңіз.</span><span class="sxs-lookup"><span data-stu-id="df8b0-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="df8b0-118">Қосылым атауы мен түрі осы қосылымды сипаттайды.</span><span class="sxs-lookup"><span data-stu-id="df8b0-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="df8b0-119">Қосылымның мақсатын түсіндіретін атауды таңдауды ұсынамыз.</span><span class="sxs-lookup"><span data-stu-id="df8b0-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="df8b0-120">Осы қосылымды кім пайдалана алатынын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="df8b0-120">Choose who can use this connection.</span></span> <span data-ttu-id="df8b0-121">Егер сіз ешқандай әрекет жасамасаңыз, әдепкі бойынша **Әкімшілер** болады.</span><span class="sxs-lookup"><span data-stu-id="df8b0-121">If you take no action, the default will be **Administrators**.</span></span> <span data-ttu-id="df8b0-122">Қосымша ақпарат алу үшін [Салымшыларға экспорттау үшін қосылымды пайдалануға рұқсат беру](connections.md#allow-contributors-to-use-a-connection-for-exports) бөлімін қараңыз.</span><span class="sxs-lookup"><span data-stu-id="df8b0-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="df8b0-123">Facebook Ads қызметі арқылы аутентификациялау:</span><span class="sxs-lookup"><span data-stu-id="df8b0-123">Authenticate with Facebook Ads:</span></span> 

   1. <span data-ttu-id="df8b0-124">Facebook жарнама тіркелгісіне кіру үшін **Facebook көмегімен қосылу** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="df8b0-124">Select **Continue with Facebook** to sign in to your Facebook Ad Account.</span></span>

   1. <span data-ttu-id="df8b0-125">Facebook көмегімен аутентификациялағаннан кейін, **ads_management** рұқсатына мүмкіндік беріңіз.</span><span class="sxs-lookup"><span data-stu-id="df8b0-125">Allow the **ads_management** permission after authenticating with Facebook.</span></span>

   1. <span data-ttu-id="df8b0-126">Жұмыс істеу қажет **Facebook жарнамалар тіркелгісі** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="df8b0-126">Select the **Facebook Ads Account** that you want to work with.</span></span>

   1. <span data-ttu-id="df8b0-127">Ашылмалы тізімнен **Бұрыннан бар реттелетін аудитория** параметрін таңдаңыз немесе **Жаңа реттелетін аудитория** жасаңыз.</span><span class="sxs-lookup"><span data-stu-id="df8b0-127">Select an **Existing custom audience** from the drop-down list or create a **New custom audience**.</span></span> <span data-ttu-id="df8b0-128">Қосымша ақпаратты [**Facebook жарнамалар менеджеріндегі аудиториялар**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494) бөлімінен қараңыз.</span><span class="sxs-lookup"><span data-stu-id="df8b0-128">For more information, see [**Audiences in Facebook Ads Manager**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span></span>
      > [!NOTE]
      > <span data-ttu-id="df8b0-129">Осы экспорттаумен тек *тұтынушы тізімі* түріндегі Facebook қызметінде аудиториялар жасап немесе реттелетін аудиторияларды жаңартуға болады.</span><span class="sxs-lookup"><span data-stu-id="df8b0-129">You can only create or update custom audiences on Facebook of the type *customer list* with this export.</span></span> <span data-ttu-id="df8b0-130">Кейбір жағдайларда ашылмалы тізімнен әртүрлі түрдегі реттелетін аудиторияларды көресіз.</span><span class="sxs-lookup"><span data-stu-id="df8b0-130">In some cases, you see custom audiences of different types in the drop-down list.</span></span> <span data-ttu-id="df8b0-131">*Тұтынушы тізімі* түрінен басқа бір түрді таңдау экспорттаудың сәтсіз болуына әкеледі.</span><span class="sxs-lookup"><span data-stu-id="df8b0-131">Selecting a different type than *customer list* will result in a failing export.</span></span> 

1. <span data-ttu-id="df8b0-132">**Деректердің құпиялығы мен сәйкестігі** қарап шығыңыз және **Келісемін** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="df8b0-132">Review the **Data privacy and compliance** and select **I agree**.</span></span>

1. <span data-ttu-id="df8b0-133">Қосылымды аяқтау үшін **Сақтау** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="df8b0-133">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="df8b0-134">Экспорттауды конфигурациялау</span><span class="sxs-lookup"><span data-stu-id="df8b0-134">Configure an export</span></span>

<span data-ttu-id="df8b0-135">Егер сіз осы түрдегі қосылымға қатынаса алсаңыз, сіз бұл экспорттауды конфигурациялай аласыз.</span><span class="sxs-lookup"><span data-stu-id="df8b0-135">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="df8b0-136">Қосымша ақпарат алу үшін [Экспорттауды конфигурациялау үшін қажет рұқсаттар](export-destinations.md#set-up-a-new-export) бөлімін қараңыз.</span><span class="sxs-lookup"><span data-stu-id="df8b0-136">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="df8b0-137">**Деректер** > **Экспорттау** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="df8b0-137">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="df8b0-138">Жаңа экспорттау жасау үшін **Мақсатты орын қосу** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="df8b0-138">To create a new export, select **Add destination**.</span></span> 

1. <span data-ttu-id="df8b0-139">**Экспорттауға арналған қосылым** өрісінде **Facebook Ads Manager** бөлімінен қосылым таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="df8b0-139">In **Connection for export** choose a connection from the **Facebook Ads Manager** section.</span></span> <span data-ttu-id="df8b0-140">Егер сіз осы бөлімнің атын көрмесеңіз, сізге қолжетімді осы түрдегі қосылым жоқ.</span><span class="sxs-lookup"><span data-stu-id="df8b0-140">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="df8b0-141">**Негізгі идентификатор өрісін таңдау** ішінде Facebook жарнамалар менеджеріне жіберу үшін **Электрондық пошта**, **Аты және мекенжай** немесе **Телефон** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="df8b0-141">In the **Choose your key identifier field**, select **Email**, **Name and address**, or **Phone** to send to Facebook Ads Manager.</span></span> 

1. <span data-ttu-id="df8b0-142">**Көрсетілетін аты** өрісінде қосылымға оңай танылатын атау енгізіңіз.</span><span class="sxs-lookup"><span data-stu-id="df8b0-142">Give your connection a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="df8b0-143">Таңдалған негізгі идентификаторға арналған бірыңғай тұтынушы нысанының тиісті төлсипаттарын салыстырыңыз.</span><span class="sxs-lookup"><span data-stu-id="df8b0-143">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>
   > <span data-ttu-id="df8b0-144">[КЕҢЕС] Негізгі идентификатор ретінде **Электрондық пошта** параметрін таңдасаңыз, үздік сәйкестік мүмкіндіктері орын алады.</span><span class="sxs-lookup"><span data-stu-id="df8b0-144">[TIP] The best chances for a match occur if you select **Email** as key identifier.</span></span> <span data-ttu-id="df8b0-145">Қосымша идентификаторларды қосу сәйкестікті жақсартуы мүмкін.</span><span class="sxs-lookup"><span data-stu-id="df8b0-145">Adding additional identifiers may improve the matching.</span></span>

1. <span data-ttu-id="df8b0-146">Facebook Ads Manager қызметіне жіберетін қосымша төлсипаттарды көрсету үшін **Төлсипат қосу** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="df8b0-146">Select **Add attribute** to map more attributes to send to Facebook Ads Manager.</span></span> <span data-ttu-id="df8b0-147">Facebook Ads Manager қызметіндегі төлсипаттар мына пайдаланушыға таныс аттармен салыстырылады: **FN** = **Аты**, **LN** = **Тегі**, **FI** = **Бірінші инициал**, **PHONE** = **Телефон**, **GEN** = **Жынысы**, **DOB** = **Туған күн**, **ST** = **Облыс**, **CT** = **Қала**, **ZIP** = **Пошта индексі**, **COUNTRY** = **Ел/аймақ**</span><span class="sxs-lookup"><span data-stu-id="df8b0-147">Attributes from Facebook Ads Manager are mapping to the following user-friendly names: **FN** = **First Name**, **LN** = **Last Name**, **FI** = **First Initial**, **PHONE** = **Phone**, **GEN** = **Gender**, **DOB** = **Date of birth**, **ST** = **State**, **CT** = **City**, **ZIP** = **Postal code / Zip code**, **COUNTRY** = **Country / Region**</span></span>

1. <span data-ttu-id="df8b0-148">Экспорттау керек сегменттерді таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="df8b0-148">Select the segments you want to export.</span></span>

1. <span data-ttu-id="df8b0-149">**Сақтау** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="df8b0-149">Select **Save**.</span></span>

<span data-ttu-id="df8b0-150">Экспорттауды сақтау экспорттауды бірден іске қоспайды.</span><span class="sxs-lookup"><span data-stu-id="df8b0-150">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="df8b0-151">Экспорттау әр [жоспарланған жаңартумен](system.md#schedule-tab) іске қосылады.</span><span class="sxs-lookup"><span data-stu-id="df8b0-151">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="df8b0-152">Сондай-ақ [деректерді сұрау бойынша экспорттауға](export-destinations.md#run-exports-on-demand) болады.</span><span class="sxs-lookup"><span data-stu-id="df8b0-152">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="df8b0-153">Деректердің құпиялылығы мен сәйкестігі</span><span class="sxs-lookup"><span data-stu-id="df8b0-153">Data privacy and compliance</span></span>

<span data-ttu-id="df8b0-154">Деректерді Facebook жарнама менеджеріне жіберу үшін Dynamics 365 Customer Insights бағдарламасын қосқан кезде, Dynamics 365 Customer Insights талаптарына сәйкестік шекарасынан тыс деректерді, соның ішінде жеке деректер сияқты ықтимал құпия деректерді беруге мүмкіндік бересіз.</span><span class="sxs-lookup"><span data-stu-id="df8b0-154">When you enable Dynamics 365 Customer Insights to transmit data to Facebook Ads Manager, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="df8b0-155">Microsoft мұндай деректерді сіздің нұсқауыңыз бойынша тасымалдайды, бірақ Facebook жарнамаларының кез келген құпиялылық немесе қауіпсіздік міндеттемелеріне сәйкес келуіне жауап бересіз.</span><span class="sxs-lookup"><span data-stu-id="df8b0-155">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Facebook Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="df8b0-156">Қосымша ақпаратты [Microsoft құпиялық туралы мәлімдемесі](https://go.microsoft.com/fwlink/?linkid=396732) бөлімінен қараңыз.</span><span class="sxs-lookup"><span data-stu-id="df8b0-156">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="df8b0-157">Бұл функцияны тоқтату үшін бұл экспорттау мақсатын кез келген уақытта Dynamics 365 Customer Insights әкімшісі жоя алады.</span><span class="sxs-lookup"><span data-stu-id="df8b0-157">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
