---
title: Customer Insights деректерін Azure Synapse Analytics қызметіне экспорттау
description: Azure Synapse Analytics қызметі үшін қосылымды конфигурациялау жолы туралы ақпарат.
ms.date: 04/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 822082d661863e737ea3d3a749a6c878db766967
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 05/04/2021
ms.locfileid: "5977384"
---
# <a name="export-data-to-azure-synapse-analytics-preview"></a><span data-ttu-id="15f14-103">Деректерді Azure Synapse Analytics (алдын ала қарау нұсқасы) қызметіне экспорттау</span><span class="sxs-lookup"><span data-stu-id="15f14-103">Export data to Azure Synapse Analytics (Preview)</span></span>

<span data-ttu-id="15f14-104">Azure Synapse — бұл деректер қоймалары мен үлкен деректер жүйелері бойынша талдау уақытын жеделдететін аналитикалық қызмет.</span><span class="sxs-lookup"><span data-stu-id="15f14-104">Azure Synapse is an analytics service that accelerates time to insight across data warehouses and big data systems.</span></span> <span data-ttu-id="15f14-105">Customer Insights деректерін [Azure Synapse](/azure/synapse-analytics/overview-what-is) қызметінен алуға және пайдалануға болады.</span><span class="sxs-lookup"><span data-stu-id="15f14-105">You can ingest and use your Customer Insights data in [Azure Synapse](/azure/synapse-analytics/overview-what-is).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="15f14-106">Алғышарттар</span><span class="sxs-lookup"><span data-stu-id="15f14-106">Prerequisites</span></span>

<span data-ttu-id="15f14-107">Customer Insights қосылымын Azure Synapse қызметінде конфигурациялау үшін келесі алғышарттар орындалуы керек.</span><span class="sxs-lookup"><span data-stu-id="15f14-107">The following prerequisites must be met to configure the connection from Customer Insights to Azure Synapse.</span></span>

> [!NOTE]
> <span data-ttu-id="15f14-108">Барлық **рөл тағайындауларын** сипатталғандай орнатқаныңызға көз жеткізіңіз.</span><span class="sxs-lookup"><span data-stu-id="15f14-108">Make sure to set all **role assignments** as described.</span></span>  

## <a name="prerequisites-in-customer-insights"></a><span data-ttu-id="15f14-109">Customer Insights қызметіндегі алғышарттар</span><span class="sxs-lookup"><span data-stu-id="15f14-109">Prerequisites in Customer Insights</span></span>

* <span data-ttu-id="15f14-110">Сізде аудитория туралы түсініктерде **Әкімші** рөлі бар.</span><span class="sxs-lookup"><span data-stu-id="15f14-110">You have an **Administrator** role in audience insights.</span></span> <span data-ttu-id="15f14-111">[Аудитория туралы түсініктерде пайдалану рұқсаттарын орнату](permissions.md#assign-roles-and-permissions) туралы қосымша ақпарат</span><span class="sxs-lookup"><span data-stu-id="15f14-111">Learn more about [setting user permissions in audience insights](permissions.md#assign-roles-and-permissions)</span></span>

<span data-ttu-id="15f14-112">Azure қызметінде:</span><span class="sxs-lookup"><span data-stu-id="15f14-112">In Azure:</span></span> 

- <span data-ttu-id="15f14-113">Белсенді Azure жазылымы.</span><span class="sxs-lookup"><span data-stu-id="15f14-113">An active Azure subscription.</span></span>

- <span data-ttu-id="15f14-114">Егер жаңа Azure Data Lake Storage Gen2 тіркелгісін пайдалансаңыз, the *аудитория туралы түсініктерге арналған қызмет негізі* **Сақтау екілік нысанының деректер салымшысы** рұқсаттарын қажет етеді.</span><span class="sxs-lookup"><span data-stu-id="15f14-114">If using a new Azure Data Lake Storage Gen2 account, the *service principal for audience insights* needs **Storage Blob Data Contributor** permissions.</span></span> <span data-ttu-id="15f14-115">[Azure Data Lake Storage Gen2 тіркелгісін аудитория туралы түсініктерге арналған Azure қызмет негізімен қосу](connect-service-principal.md) туралы қосымша ақпарат.</span><span class="sxs-lookup"><span data-stu-id="15f14-115">Learn more on [connecting to an Azure Data Lake Storage Gen2 account with Azure service principal for audience insights](connect-service-principal.md).</span></span> <span data-ttu-id="15f14-116">Data Lake Storage Gen2 **қызметінде** [иерархиялық атаулар кеңістігі](/azure/storage/blobs/data-lake-storage-namespace) қосулы болуы керек.</span><span class="sxs-lookup"><span data-stu-id="15f14-116">The Data Lake Storage Gen2 **must have** [hierarchical namespace](/azure/storage/blobs/data-lake-storage-namespace) enabled.</span></span>

- <span data-ttu-id="15f14-117">Ресурс тобында Azure Synapse жұмыс кеңістігі орналасқан, *қызмет негізі* және *аудитория туралы түсініктерге арналған пайдаланушыға* кем дегенде **Оқушы** рұқсаттары тағайындалуы керек.</span><span class="sxs-lookup"><span data-stu-id="15f14-117">On the resource group the Azure Synapse workspace is located, the *service principal* and the *user for audience insights* needs to be assigned at least **Reader** permissions.</span></span> <span data-ttu-id="15f14-118">Қосымша ақпарат алу үшін [Azure порталын пайдалану арқылы Azure рөлдерін тағайындау](/azure/role-based-access-control/role-assignments-portal) бөлімін қараңыз.</span><span class="sxs-lookup"><span data-stu-id="15f14-118">For more information, see [Assign Azure roles using the Azure portal](/azure/role-based-access-control/role-assignments-portal).</span></span>

- <span data-ttu-id="15f14-119">*Пайдаланушы* деректер орналасқан және Azure Synapse жұмыс кеңістігімен байланыстырылған Azure Data Lake Storage Gen2 тіркелгісінде **Сақтау екілік нысанының деректер салымшысы** рұқсаттарын қажет етеді.</span><span class="sxs-lookup"><span data-stu-id="15f14-119">The *user* needs **Storage Blob Data Contributor** permissions on the Azure Data Lake Storage Gen2 account where the data is located and linked to the Azure Synapse workspace.</span></span> <span data-ttu-id="15f14-120">[Azure порталын екілік нысан және кезек тізімі деректеріне қатынасуға арналған Azure рөлін тағайындау үшін пайдалану](/azure/storage/common/storage-auth-aad-rbac-portal) және [Сақтау екілік нысанының деректер салымшысы рұқсаттары](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor) туралы қосымша ақпарат.</span><span class="sxs-lookup"><span data-stu-id="15f14-120">Learn more about [using the Azure portal to assign an Azure role for access to blob and queue data](/azure/storage/common/storage-auth-aad-rbac-portal) and [Storage Blob Data Contributor permissions](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).</span></span>

- <span data-ttu-id="15f14-121">*[Azure Synapse жұмыс кеңістігінің басқарылатын идентификациясы](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* деректер орналасқан және Azure Synapse жұмыс кеңістігімен байланыстырылған Azure Data Lake Storage Gen2 тіркелгісінде **Сақтау екілік нысанының деректер салымшысы** рұқсаттарын қажет етеді.</span><span class="sxs-lookup"><span data-stu-id="15f14-121">The *[Azure Synapse workspace managed identity](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* needs **Storage Blob Data Contributor** permissions on the Azure Data Lake Storage Gen2 account where the data is located and linked to the Azure Synapse workspace.</span></span> <span data-ttu-id="15f14-122">[Azure порталын екілік нысан және кезек тізімі деректеріне қатынасуға арналған Azure рөлін тағайындау үшін пайдалану](/azure/storage/common/storage-auth-aad-rbac-portal) және [Сақтау екілік нысанының деректер салымшысы рұқсаттары](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor) туралы қосымша ақпарат алыңыз.</span><span class="sxs-lookup"><span data-stu-id="15f14-122">Learn more on [using the Azure portal to assign an Azure role for access to blob and queue data](/azure/storage/common/storage-auth-aad-rbac-portal) and [Storage Blob Data Contributor permissions](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).</span></span>

- <span data-ttu-id="15f14-123">Azure Synapse жұмыс кеңістігінде *аудитория туралы түсініктерге арналған қызмет негізі* **Synapse әкімшісі** рөлінің тағайындалуын қажет етеді.</span><span class="sxs-lookup"><span data-stu-id="15f14-123">On the Azure Synapse workspace, the *service principal for audience insights* needs **Synapse Administrator** role assigned.</span></span> <span data-ttu-id="15f14-124">Қосымша ақпарат алу үшін [Synapse жұмыс кеңістігі үшін қатынасуды басқару элементін орнату жолы](/azure/synapse-analytics/security/how-to-set-up-access-control) бөлімін қараңыз.</span><span class="sxs-lookup"><span data-stu-id="15f14-124">For more information, see [How to set up access control for your Synapse workspace](/azure/synapse-analytics/security/how-to-set-up-access-control).</span></span>

## <a name="set-up-the-connection-and-export-to-azure-synapse"></a><span data-ttu-id="15f14-125">Қосылым орнату және Azure Synapse қызметіне экспорттау</span><span class="sxs-lookup"><span data-stu-id="15f14-125">Set up the connection and export to Azure Synapse</span></span>

### <a name="configure-a-connection"></a><span data-ttu-id="15f14-126">Қосылымды конфигурациялау</span><span class="sxs-lookup"><span data-stu-id="15f14-126">Configure a connection</span></span>

1. <span data-ttu-id="15f14-127">**Әкімші** > **Қосылымдар** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="15f14-127">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="15f14-128">**Қосылым қосу** түймешігін таңдаңыз және қосылымды конфигурациялау үшін **Azure Synapse Analytics** немесе **Орнату** опциясын **Azure Synapse Analytics** тақтасынан таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="15f14-128">Select **Add connection** and choose **Azure Synapse Analytics** or select the **Set up** on the **Azure Synapse Analytics** tile to configure the connection.</span></span>

1. <span data-ttu-id="15f14-129">Көрсетілетін аты өрісінде қосылымға оңай танылатын атау енгізіңіз.</span><span class="sxs-lookup"><span data-stu-id="15f14-129">Give your connection a recognizable name in the Display name field.</span></span> <span data-ttu-id="15f14-130">Қосылым атауы мен түрі осы қосылымды сипаттайды.</span><span class="sxs-lookup"><span data-stu-id="15f14-130">The name and the type of the connection describes this connection.</span></span> <span data-ttu-id="15f14-131">Қосылымның мақсатын түсіндіретін атауды таңдауды ұсынамыз.</span><span class="sxs-lookup"><span data-stu-id="15f14-131">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="15f14-132">Осы қосылымды кім пайдалана алатынын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="15f14-132">Choose who can use this connection.</span></span> <span data-ttu-id="15f14-133">Егер сіз ешқандай әрекет жасамасаңыз, әдепкі бойынша Әкімшілер болады.</span><span class="sxs-lookup"><span data-stu-id="15f14-133">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="15f14-134">Қосымша ақпарат алу үшін [Салымшыларға экспорттау үшін қосылымды пайдалануға рұқсат беру](connections.md#allow-contributors-to-use-a-connection-for-exports) бөлімін қараңыз.</span><span class="sxs-lookup"><span data-stu-id="15f14-134">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="15f14-135">Customer Insights деректерін пайдалану керек жазылымды таңдаңыз немесе іздеңіз.</span><span class="sxs-lookup"><span data-stu-id="15f14-135">Select or search for the subscription you want to use the Customer Insights data in.</span></span> <span data-ttu-id="15f14-136">Жазылымды таңдағаннан кейін **Жұмыс кеңістігі**, **Сақтау тіркелгісі** және **Контейнер** параметрлерін таңдауға болады.</span><span class="sxs-lookup"><span data-stu-id="15f14-136">As soon as a subscription is selected, you can also select **Workspace**, **Storage account**, and **Container**.</span></span>

1. <span data-ttu-id="15f14-137">Қосылымды сақтау үшін **Сақтау** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="15f14-137">Select **Save** to save the connection.</span></span>

### <a name="configure-an-export"></a><span data-ttu-id="15f14-138">Экспорттауды конфигурациялау</span><span class="sxs-lookup"><span data-stu-id="15f14-138">Configure an export</span></span>

<span data-ttu-id="15f14-139">Егер сіз осы түрдегі қосылымға қатынаса алсаңыз, сіз бұл экспорттауды конфигурациялай аласыз.</span><span class="sxs-lookup"><span data-stu-id="15f14-139">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="15f14-140">Қосымша ақпарат алу үшін [Экспорттауды конфигурациялау үшін қажет рұқсаттар](export-destinations.md#set-up-a-new-export) бөлімін қараңыз.</span><span class="sxs-lookup"><span data-stu-id="15f14-140">For more information, see [permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="15f14-141">**Деректер** > **Экспорттау** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="15f14-141">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="15f14-142">Жаңа экспорттау жасау үшін **Экспорттау қосу** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="15f14-142">To create a new export, select **Add export**.</span></span>

1. <span data-ttu-id="15f14-143">**Экспорттауға арналған қосылым** өрісінде **Azure Synapse Analytics** бөлімінен қосылымды таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="15f14-143">In the **Connection for export** field, choose a connection from the **Azure Synapse Analytics** section.</span></span> <span data-ttu-id="15f14-144">Егер сіз осы бөлімнің атауын көрмесеңіз, сізге қолжетімді осы түрдегі [қосылымдар](connections.md) жоқ.</span><span class="sxs-lookup"><span data-stu-id="15f14-144">If you don't see this section name, there are no [connections](connections.md) of this type available to you.</span></span>

1. <span data-ttu-id="15f14-145">Экспорттау және **Дерекқор атауы** үшін танылатын **Көрсетілетін атау** беріңіз.</span><span class="sxs-lookup"><span data-stu-id="15f14-145">Provide a recognizable **Display name** for your export and a **Database name**.</span></span>

1. <span data-ttu-id="15f14-146">Azure Synapse Analytics қызметіне экспорттау керек нысандарды таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="15f14-146">Select which entities you want to export to Azure Synapse Analytics.</span></span>

1. <span data-ttu-id="15f14-147">**Сақтау** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="15f14-147">Select **Save**.</span></span>

<span data-ttu-id="15f14-148">Экспорттауды сақтау экспорттауды бірден іске қоспайды.</span><span class="sxs-lookup"><span data-stu-id="15f14-148">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="15f14-149">Экспорттау әр [жоспарланған жаңартумен](system.md#schedule-tab) іске қосылады.</span><span class="sxs-lookup"><span data-stu-id="15f14-149">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="15f14-150">Сондай-ақ [деректерді сұрау бойынша экспорттауға](export-destinations.md#run-exports-on-demand) болады.</span><span class="sxs-lookup"><span data-stu-id="15f14-150">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span>

### <a name="update-an-export"></a><span data-ttu-id="15f14-151">Экспорттауды жаңарту</span><span class="sxs-lookup"><span data-stu-id="15f14-151">Update an export</span></span>

1. <span data-ttu-id="15f14-152">**Деректер** > **Экспорттау** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="15f14-152">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="15f14-153">Жаңарту керек экспорттауда **Өңдеу** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="15f14-153">Select **Edit** on the export you want to update.</span></span>

   - <span data-ttu-id="15f14-154">Таңдаудан нысандарды **қосыңыз** немесе **жойыңыз**.</span><span class="sxs-lookup"><span data-stu-id="15f14-154">**Add** or **Remove** entities from the selection.</span></span> <span data-ttu-id="15f14-155">Егер нысандар таңдаудан алынып тасталса, олар Synapse Analytics дерекқорынан жойылмайды.</span><span class="sxs-lookup"><span data-stu-id="15f14-155">If entities are removed from the selection, they aren't deleted from the Synapse Analytics database.</span></span> <span data-ttu-id="15f14-156">Алайда болашақ деректерді жаңарту сол дерекқордағы жойылған нысандарды жаңартпайды.</span><span class="sxs-lookup"><span data-stu-id="15f14-156">However, future data refreshes won't update the removed entities in that database.</span></span>

   - <span data-ttu-id="15f14-157">**Дерекқордың атауын өзгерту** опциясы жаңа Synapse Analytics дерекқорын жасайды.</span><span class="sxs-lookup"><span data-stu-id="15f14-157">**Changing the Database Name** creates a new Synapse Analytics database.</span></span> <span data-ttu-id="15f14-158">Бұрын конфигурацияланған атауы бар дерекқор болашақта жаңартулар алмайды.</span><span class="sxs-lookup"><span data-stu-id="15f14-158">The database with the name that was configured before won't receive any updates in future refreshes.</span></span>
