---
title: Customer Insights деректерін Salesforce Marketing Cloud қызметіне экспорттау
description: Salesforce Marketing Cloud қызметіне қосылымды және экспорттауды конфигурациялау жолы туралы ақпарат.
ms.date: 06/24/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 123f8b2dbb6140785dec6c1b4164d2f513f66a53
ms.sourcegitcommit: 057079532e31c12bac36f374857ba3dc847d6ad0
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 06/29/2021
ms.locfileid: "6314636"
---
# <a name="export-segments-and-other-data-to-salesforce-marketing-cloud-preview"></a><span data-ttu-id="7a900-103">Salesforce Marketing Cloud қызметіне сегменттерді және басқа деректерді экспорттау (алдын ала қарау нұсқасы)</span><span class="sxs-lookup"><span data-stu-id="7a900-103">Export segments and other data to Salesforce Marketing Cloud (preview)</span></span>

<span data-ttu-id="7a900-104">Тұтынушылар туралы деректерді Salesforce Marketing Cloud қызметінде қауіпсіз файл тасымалдау протоколымен (SFTP) экспорттау арқылы пайдаланыңыз.</span><span class="sxs-lookup"><span data-stu-id="7a900-104">Use your customer data in Salesforce Marketing Cloud by exporting them through a Secure File Transfer Protocol (SFTP) location.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="7a900-105">Қосылым алғышарттары</span><span class="sxs-lookup"><span data-stu-id="7a900-105">Prerequisites for connection</span></span>

- <span data-ttu-id="7a900-106">SFTP хостының және тиісті әкімші деректерінің қолжетімділігі.</span><span class="sxs-lookup"><span data-stu-id="7a900-106">Availability of an SFTP host and corresponding admin credentials.</span></span> [<span data-ttu-id="7a900-107">Salesforce Marketing Cloud қызметі үшін SFTP орындарын орнату жолы</span><span class="sxs-lookup"><span data-stu-id="7a900-107">How to setup SFTP locations for Salesforce Marketing Cloud</span></span>](https://help.salesforce.com/articleView?id=sf.mc_es_configure_enhanced_ftp.htm&type=5) 

## <a name="known-limitations"></a><span data-ttu-id="7a900-108">Белгілі шектеулер</span><span class="sxs-lookup"><span data-stu-id="7a900-108">Known limitations</span></span>

- <span data-ttu-id="7a900-109">Экспорттаудың жұмыс уақыты жүйенің жұмысына байланысты.</span><span class="sxs-lookup"><span data-stu-id="7a900-109">The runtime of an export depends on your system performance.</span></span> <span data-ttu-id="7a900-110">Сервердің минималды конфигурациясы ретінде екі CPU оперативті жады мен 1 Гб жадты ұсынамыз.</span><span class="sxs-lookup"><span data-stu-id="7a900-110">We recommend two CPU cores and 1 Gb of memory as minimal configuration of your server.</span></span> 
- <span data-ttu-id="7a900-111">100 миллион тұтынушы профилі бар нысандарды экспорттау ұсынылған минималды конфигурацияны пайдаланған кезде 90 минут алуы мүмкін.</span><span class="sxs-lookup"><span data-stu-id="7a900-111">Exporting entities with up to 100 million customer profiles can take 90 minutes when using the recommended minimal configuration.</span></span> 

## <a name="set-up-the-connection-to-salesforce-marketing-cloud"></a><span data-ttu-id="7a900-112">Salesforce Marketing Cloud қызметіне қосылым орнату</span><span class="sxs-lookup"><span data-stu-id="7a900-112">Set up the connection to Salesforce Marketing Cloud</span></span>

1. <span data-ttu-id="7a900-113">**Әкімші** > **Қосылымдар** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="7a900-113">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="7a900-114">**Қосылым қосу** түймешігін таңдаңыз және қосылымды конфигурациялау үшін **Salesforce Marketing Cloud** қызметін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="7a900-114">Select **Add connection** and choose **Salesforce Marketing Cloud** to configure the connection.</span></span>

1. <span data-ttu-id="7a900-115">**Көрсетілетін аты** өрісінде қосылымға оңай танылатын атау енгізіңіз.</span><span class="sxs-lookup"><span data-stu-id="7a900-115">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="7a900-116">Қосылым атауы мен түрі осы қосылымды сипаттайды.</span><span class="sxs-lookup"><span data-stu-id="7a900-116">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="7a900-117">Қосылымның мақсатын түсіндіретін атауды таңдауды ұсынамыз.</span><span class="sxs-lookup"><span data-stu-id="7a900-117">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="7a900-118">Осы қосылымды кім пайдалана алатынын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="7a900-118">Choose who can use this connection.</span></span> <span data-ttu-id="7a900-119">Егер сіз ешқандай әрекет жасамасаңыз, әдепкі бойынша Әкімшілер болады.</span><span class="sxs-lookup"><span data-stu-id="7a900-119">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="7a900-120">Қосымша ақпарат алу үшін [Салымшыларға экспорттау үшін қосылымды пайдалануға рұқсат беру](connections.md#allow-contributors-to-use-a-connection-for-exports) бөлімін қараңыз.</span><span class="sxs-lookup"><span data-stu-id="7a900-120">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="7a900-121">SFTP тіркелгіңіз үшін **Пайдаланушы аты**, **Құпиясөз**, **Хост атауы** және **Экспорттау қалтасы** деректерін енгізіңіз.</span><span class="sxs-lookup"><span data-stu-id="7a900-121">Provide a **Username**, **Password**, **Hostname**, and **Export folder** for your SFTP account.</span></span>

1. <span data-ttu-id="7a900-122">Байланысты сынау үшін **Растау** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="7a900-122">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="7a900-123">**Деректер құпиялығы мен сәйкестігін** растау үшін **Мен келісемін** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="7a900-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="7a900-124">Қосылымды аяқтау үшін **Сақтау** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="7a900-124">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="7a900-125">Экспорттауды конфигурациялау</span><span class="sxs-lookup"><span data-stu-id="7a900-125">Configure an export</span></span>

<span data-ttu-id="7a900-126">Егер сіз осы түрдегі қосылымға қатынаса алсаңыз, сіз бұл экспорттауды конфигурациялай аласыз.</span><span class="sxs-lookup"><span data-stu-id="7a900-126">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="7a900-127">Қосымша ақпарат алу үшін [Экспорттауды конфигурациялау үшін қажет рұқсаттар](export-destinations.md#set-up-a-new-export) бөлімін қараңыз.</span><span class="sxs-lookup"><span data-stu-id="7a900-127">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="7a900-128">**Деректер** > **Экспорттау** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="7a900-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="7a900-129">Жаңа экспорттау жасау үшін **Мақсатты орын қосу** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="7a900-129">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="7a900-130">**Экспорттауға арналған қосылым** өрісінде SFTP бөлімінен қосылым таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="7a900-130">In the **Connection for export** field, choose a connection from the SFTP section.</span></span> <span data-ttu-id="7a900-131">Егер сіз осы бөлімнің атын көрмесеңіз, сізге қолжетімді осы түрдегі қосылым жоқ.</span><span class="sxs-lookup"><span data-stu-id="7a900-131">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="7a900-132">Деректерді **Мұрағатталған** немесе **Мұрағаттан шығарылған** күйде экспорттауды және экспортталған файлдар үшін **өріс бөлгішін** таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="7a900-132">Choose if you want to export your data **Gzipped** or **Unzipped** and the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="7a900-133">Экспортталатын нысандарды таңдаңыз, мысалы, сегменттер.</span><span class="sxs-lookup"><span data-stu-id="7a900-133">Select the entities, for example segments, you want to export.</span></span>

   > [!NOTE]
   > <span data-ttu-id="7a900-134">Әрбір таңдалған нысан экспортталған кезде бес шығыс файлға бөлінеді.</span><span class="sxs-lookup"><span data-stu-id="7a900-134">Each selected entity will be split up into up to five output files when exported.</span></span> 

1. <span data-ttu-id="7a900-135">**Сақтау** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="7a900-135">Select **Save**.</span></span>

<span data-ttu-id="7a900-136">Экспорттауды сақтау экспорттауды бірден іске қоспайды.</span><span class="sxs-lookup"><span data-stu-id="7a900-136">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="7a900-137">Экспорттау әр [жоспарланған жаңартумен](system.md#schedule-tab) іске қосылады.</span><span class="sxs-lookup"><span data-stu-id="7a900-137">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="7a900-138">Сондай-ақ [деректерді сұрау бойынша экспорттауға](export-destinations.md#run-exports-on-demand) болады.</span><span class="sxs-lookup"><span data-stu-id="7a900-138">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="import-customer-insights-data-from-sftp-location-to-salesforce-marketing-cloud"></a><span data-ttu-id="7a900-139">SFTP орнындағы Customer Insights деректерін Salesforce Marketing Cloud қызметіне импорттау</span><span class="sxs-lookup"><span data-stu-id="7a900-139">Import Customer Insights data from SFTP location to Salesforce Marketing Cloud</span></span>

1. <span data-ttu-id="7a900-140">Customer Insights деректер файлын SFTP орнынан импорттау үшін [Salesforce Marketing Cloud қызметінде деректер кеңейтімдерін](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5) жасаңыз.</span><span class="sxs-lookup"><span data-stu-id="7a900-140">Create [data extensions in Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5) to import the Customer Insights data file from the SFTP location.</span></span>

2. <span data-ttu-id="7a900-141">[SFTP орнындағы деректерді](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5) Salesforce Marketing Cloud деректер кеңейтіміне импорттаңыз.</span><span class="sxs-lookup"><span data-stu-id="7a900-141">[Import the data from the SFTP location](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5) into the Salesforce Marketing Cloud data extension.</span></span> 

3. <span data-ttu-id="7a900-142">Деректерді деректер кеңейтіміне импорттау үшін автоматтандыруды орнатыңыз.</span><span class="sxs-lookup"><span data-stu-id="7a900-142">Set up the automation to import the data into the data extensions.</span></span> <span data-ttu-id="7a900-143">[Файлды сүйреуді автоматтандырулар мен жоспарланған автоматтандырулар](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5) туралы қосымша ақпарат.</span><span class="sxs-lookup"><span data-stu-id="7a900-143">Learn more about [file drop automations and scheduled automations](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5).</span></span>

   <span data-ttu-id="7a900-144">[Файлды сүйреуді автоматтандыруды](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5) немесе  [жоспарланған автоматтандыруды](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5) анықтаңыз.</span><span class="sxs-lookup"><span data-stu-id="7a900-144">Define a [file drop automation](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5) or a  [scheduled automation](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5).</span></span> 

<span data-ttu-id="7a900-145">Мына жерде [SFTP протоколымен автоматтандыру](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5) мысалы келтірілген.</span><span class="sxs-lookup"><span data-stu-id="7a900-145">Here's an example of [an automation with SFTP](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5).</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="7a900-146">Деректердің құпиялылығы мен сәйкестігі</span><span class="sxs-lookup"><span data-stu-id="7a900-146">Data privacy and compliance</span></span>

<span data-ttu-id="7a900-147">Деректерді SFTP арқылы жіберу үшін Dynamics 365 Customer Insights бағдарламасын қосқан кезде, Dynamics 365 Customer Insights талаптарына сәйкестік шекарасынан тыс деректерді, соның ішінде жеке деректер сияқты ықтимал құпия деректерді беруге мүмкіндік бересіз.</span><span class="sxs-lookup"><span data-stu-id="7a900-147">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="7a900-148">Microsoft мұндай деректерді сіздің нұсқауыңыз бойынша тасымалдайды, бірақ экспортталатын орынның кез келген құпиялылық немесе қауіпсіздік міндеттемелеріне сәйкес келуіне жауап бересіз.</span><span class="sxs-lookup"><span data-stu-id="7a900-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="7a900-149">Қосымша ақпаратты [Microsoft құпиялық туралы мәлімдемесі](https://go.microsoft.com/fwlink/?linkid=396732) бөлімінен қараңыз.</span><span class="sxs-lookup"><span data-stu-id="7a900-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="7a900-150">Бұл функцияны тоқтату үшін бұл экспорттау мақсатын кез келген уақытта Dynamics 365 Customer Insights әкімшісі жоя алады.</span><span class="sxs-lookup"><span data-stu-id="7a900-150">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
