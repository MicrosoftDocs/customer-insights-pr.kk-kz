---
title: Субъект-қызметімен Azure Data Lake Storage Gen2 тіркелгісіне қосылу
description: Аудитория мәліметтеріне тіркеу кезінде өз деректер көліңізге қосу үшін аудитория мәліметтеріне арналған Azure субъект-қызметін пайдаланыңыз.
ms.date: 02/10/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: eebbac1370a847869d98beaf70db49b809d762e7
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267729"
---
# <a name="connect-to-an-azure-data-lake-storage-gen2-account-with-an-azure-service-principal-for-audience-insights"></a><span data-ttu-id="6075e-103">Аудитория мәліметтері бойынша Azure субъект-қызметімен Azure Data Lake Storage Gen2 тіркелгісіне қосылыңыз</span><span class="sxs-lookup"><span data-stu-id="6075e-103">Connect to an Azure Data Lake Storage Gen2 account with an Azure service principal for audience insights</span></span>

<span data-ttu-id="6075e-104">Azure қызметтерін пайдаланатын автоматтандырылған құралдарда әрдайым шектеулі рұқсаттар болуы тиіс.</span><span class="sxs-lookup"><span data-stu-id="6075e-104">Automated tools that use Azure services should always have restricted permissions.</span></span> <span data-ttu-id="6075e-105">Бағдарламалардың толық артықшылықты пайдаланушы ретінде кіруінің орнына, Azure субъект-қызметтерін ұсынады.</span><span class="sxs-lookup"><span data-stu-id="6075e-105">Instead of having applications sign in as a fully privileged user, Azure offers service principals.</span></span> <span data-ttu-id="6075e-106">Сақтау тіркелгісі кілттерінің орнына Azure субхект-қызметін пайдаланып Azure Data Lake Storage Gen2 тіркелгісімен аудитория мәліметтерін қосу жолдары туралы оқыңыз.</span><span class="sxs-lookup"><span data-stu-id="6075e-106">Read on to learn how to connect audience insights with an Azure Data Lake Storage Gen2 account using an Azure service principal instead of storage account keys.</span></span> 

<span data-ttu-id="6075e-107">[Common Data Model қалтасын деректер көзі ретінде қауіпсіз түрде қосу](connect-common-data-model.md) немесе [жаңасын жасау немесе бұрыннан бар ортаны жаңарту үшін](manage-environments.md#create-an-environment-in-an-existing-organization) субъект-қызметін пайдалануға болады.</span><span class="sxs-lookup"><span data-stu-id="6075e-107">You can use the service principal to securely [add or edit a Common Data Model folder as a data source](connect-common-data-model.md) or [create a new or update an existing environment](manage-environments.md#create-an-environment-in-an-existing-organization).</span></span>

> [!IMPORTANT]
> - <span data-ttu-id="6075e-108">Субъект-қызметін пайдалануға арналған Azure Data Lake Gen2 сақтау орны тіркелгісінде [Иерархиялық аттар кеңістігі (HNS) қосулы](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-namespace) болуы тиіс.</span><span class="sxs-lookup"><span data-stu-id="6075e-108">The Azure Data Lake Gen2 storage account that intends to use the service principal must have [Hierarchical Name Space (HNS) enabled](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-namespace).</span></span>
> - <span data-ttu-id="6075e-109">Субъект-қызметін жасау үшін Azure жазылымына арналған әкімші рұқсаттары қажет.</span><span class="sxs-lookup"><span data-stu-id="6075e-109">You need admin permissions for your Azure subscription to create the service principal.</span></span>

## <a name="create-azure-service-principal-for-audience-insights"></a><span data-ttu-id="6075e-110">Аудитория мәліметтеріне арналған Azure субъект-қызметін жасаңыз</span><span class="sxs-lookup"><span data-stu-id="6075e-110">Create Azure service principal for audience insights</span></span>

<span data-ttu-id="6075e-111">Аудитория мәліметтеріне арналған жаңа субъект-қызметін жасау алдында ұйымда бұрыннан болуын тексеріңіз.</span><span class="sxs-lookup"><span data-stu-id="6075e-111">Before creating a new service principal for audience insights, check if it already exists in your organization.</span></span>

### <a name="look-for-an-existing-service-principal"></a><span data-ttu-id="6075e-112">Бар субъект-қызметін іздеңіз</span><span class="sxs-lookup"><span data-stu-id="6075e-112">Look for an existing service principal</span></span>

1. <span data-ttu-id="6075e-113">[Azure әкімші порталына](https://portal.azure.com) өтіп, ұйымыңызға кіріңіз.</span><span class="sxs-lookup"><span data-stu-id="6075e-113">Go to the [Azure admin portal](https://portal.azure.com) and sign in to your organization.</span></span>

2. <span data-ttu-id="6075e-114">Azure қызметтерінен **Azure Active Directory** таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="6075e-114">Select **Azure Active Directory** from the Azure services.</span></span>

3. <span data-ttu-id="6075e-115">**Басқару** тармағында **Кәсіпорын бағдарламалары** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="6075e-115">Under **Manage**, select **Enterprise Applications**.</span></span>

4. <span data-ttu-id="6075e-116">Аудитория мәліметтерінің бірінші тараптағы бағдарлама идентификаторын `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` немесе `Dynamics 365 AI for Customer Insights` атауын іздеңіз.</span><span class="sxs-lookup"><span data-stu-id="6075e-116">Search for the audience insights first party application ID `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` or the name `Dynamics 365 AI for Customer Insights`.</span></span>

5. <span data-ttu-id="6075e-117">Егер сәйкес жазбаны тапсаңыз, бұл аудитория мәліметтеріне арналған субъект-қызметі бар дегенді білдіреді.</span><span class="sxs-lookup"><span data-stu-id="6075e-117">If you find a matching record, it means that the service principal for audience insights exists.</span></span> <span data-ttu-id="6075e-118">Оны қайта жасаудың қажеті жоқ.</span><span class="sxs-lookup"><span data-stu-id="6075e-118">You don't need to create it again.</span></span>
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Қолданыстағы субъект-қызметін көрсететін скриншот.":::
   
6. <span data-ttu-id="6075e-120">Егер ешбір нәтиже қайтарылмаса, жаңа субъект-қызметін жасаңыз.</span><span class="sxs-lookup"><span data-stu-id="6075e-120">If no results are returned, create a new service principal.</span></span>

### <a name="create-a-new-service-principal"></a><span data-ttu-id="6075e-121">Жаңа субъект-қызметін жасау</span><span class="sxs-lookup"><span data-stu-id="6075e-121">Create a new service principal</span></span>

1. <span data-ttu-id="6075e-122">**Графикке арналған Azure Active Directory PowerShell** соңғы нұсқасын орнатыңыз.</span><span class="sxs-lookup"><span data-stu-id="6075e-122">Install the latest version of the **Azure Active Directory PowerShell for Graph**.</span></span> <span data-ttu-id="6075e-123">Қосымша ақпарат алу үшін [Графикке арналған Azure Active Directory PowerShell](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) бөлімін қараңыз.</span><span class="sxs-lookup"><span data-stu-id="6075e-123">For more information, see [Install Azure Active Directory PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2).</span></span>
   - <span data-ttu-id="6075e-124">Дербес компьютерде пернетақтада Windows кілтін таңдап, **Windows PowerShell** және **Әкімші ретінде іске қосу** параметрлерін іздеңіз.</span><span class="sxs-lookup"><span data-stu-id="6075e-124">On your PC, select the Windows key on your keyboard and search for **Windows PowerShell** and **Run as Administrator**.</span></span>
   
   - <span data-ttu-id="6075e-125">Ашылатын PowerShell терезесінде `Install-Module AzureAD` енгізіңіз.</span><span class="sxs-lookup"><span data-stu-id="6075e-125">In the PowerShell window that opens, enter `Install-Module AzureAD`.</span></span>

2. <span data-ttu-id="6075e-126">Azure AD PowerShell модулімен аудитория мәліметтері бойынша субъект-қызмет жасаңыз.</span><span class="sxs-lookup"><span data-stu-id="6075e-126">Create the  service principal for audience insights with the Azure AD PowerShell Module.</span></span>
   - <span data-ttu-id="6075e-127">PowerShell терезесінде `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure` енгізіңіз.</span><span class="sxs-lookup"><span data-stu-id="6075e-127">In the PowerShell window, enter `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`.</span></span> <span data-ttu-id="6075e-128">«Қатысушы идентификаторын» субъект-қызмет жасау қажет қатысушының нақты идентификаторымен ауыстырыңыз.</span><span class="sxs-lookup"><span data-stu-id="6075e-128">Replace “your tenant ID” with the actual ID of your tenant where you want to create the service principal.</span></span> <span data-ttu-id="6075e-129">Орта атауының `AzureEnvironmentName` параметрі міндетті емес,</span><span class="sxs-lookup"><span data-stu-id="6075e-129">The environment name parameter `AzureEnvironmentName` is optional.</span></span>
  
   - <span data-ttu-id="6075e-130">`New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"` енгізіңіз.</span><span class="sxs-lookup"><span data-stu-id="6075e-130">Enter `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`.</span></span> <span data-ttu-id="6075e-131">Бұл пәрмен таңдалған қатысушыда аудитория мәліметтері бойынша субъект-қызметін жасайды.</span><span class="sxs-lookup"><span data-stu-id="6075e-131">This command creates the service principal for audience insights on the selected tenant.</span></span>  

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a><span data-ttu-id="6075e-132">Сақтау тіркелгісіне қатынасу үшін субъект-қызметіне рұқсаттар беріңіз</span><span class="sxs-lookup"><span data-stu-id="6075e-132">Grant permissions to the service principal to access the storage account</span></span>

<span data-ttu-id="6075e-133">Аудитория мәліметтерінде пайдаланылатын сақтау тіркелгісі бойынша субъект-қызметке рұқсаттар беру үшін Azure порталына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="6075e-133">Go to the Azure portal to grant permissions to the service principal for the storage account you want to use in audience insights.</span></span>

1. <span data-ttu-id="6075e-134">[Azure әкімші порталына](https://portal.azure.com) өтіп, ұйымыңызға кіріңіз.</span><span class="sxs-lookup"><span data-stu-id="6075e-134">Go to the [Azure admin portal](https://portal.azure.com) and sign in to your organization.</span></span>

1. <span data-ttu-id="6075e-135">Аудитория мәліметтері бойынша субъект-қызмет қатынаса алатын сақтау тіркелгісін ашыңыз.</span><span class="sxs-lookup"><span data-stu-id="6075e-135">Open the storage account you want the service principal for audience insights to have access to.</span></span>

1. <span data-ttu-id="6075e-136">Навигация тақтасынан **Қатынасты басқару (IAM)** таңдап, **Қосу** > **Рөл тағайындауын қосу** тармағын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="6075e-136">Select **Access control (IAM)** from the navigation pane and select **Add** > **Add role assignment**.</span></span>
   
   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Рөл тағайындауды қосу кезінде Azure порталын көрсететін скриншот.":::
   
1. <span data-ttu-id="6075e-138">**Рөл тағайындауды қосу** тақтасында келесі сипаттарды орнатыңыз:</span><span class="sxs-lookup"><span data-stu-id="6075e-138">In the **Add role assignment** pane, set the following properties:</span></span>
   - <span data-ttu-id="6075e-139">Рөл: *Blob сақтау құралы деректерін қосушы*</span><span class="sxs-lookup"><span data-stu-id="6075e-139">Role: *Storage Blob Data Contributor*</span></span>
   - <span data-ttu-id="6075e-140">Мыналарға қатынасу рұқсатын тағайындаңыз: *Пайдаланушы, топ немесе субъект-қызмет*</span><span class="sxs-lookup"><span data-stu-id="6075e-140">Assign access to: *User, group, or service principal*</span></span>
   - <span data-ttu-id="6075e-141">Таңдаңыз: *Customer Insights жүйесіне арналған Dynamics 365 AI* ([сіз жасаған субъект-қызмет](#create-a-new-service-principal))</span><span class="sxs-lookup"><span data-stu-id="6075e-141">Select: *Dynamics 365 AI for Customer Insights* (the [service principal you created](#create-a-new-service-principal))</span></span>

1.  <span data-ttu-id="6075e-142">**Сақтау** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="6075e-142">Select **Save**.</span></span>

<span data-ttu-id="6075e-143">Өзгерістерді үлгілеу 15 минутқа созылуы мүмкін.</span><span class="sxs-lookup"><span data-stu-id="6075e-143">It can take up to 15 minutes to propagate the changes.</span></span>

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-audience-insights"></a><span data-ttu-id="6075e-144">Аудитория мәліметтеріне сақтау тіркелгісін тіркеуде Azure ресурс идентификаторын немесе Azure жазылымы мәліметтерін енгізіңіз.</span><span class="sxs-lookup"><span data-stu-id="6075e-144">Enter the Azure Resource ID or the Azure Subscription details in the storage account attachment to Audience Insights.</span></span>

<span data-ttu-id="6075e-145">[Нәтиже деректерін сақтау](manage-environments.md) үшін немесе [оны деректер көзі ретінде пайдалану](connect-common-data-service-lake.md) үшін аудитория мәліметтерінде Azure Data Lake сақтау тіркелгісін тіркеңіз.</span><span class="sxs-lookup"><span data-stu-id="6075e-145">Attach an Azure Data Lake storage account in audience insights to [store output data](manage-environments.md) or [use it as a data source](connect-common-data-service-lake.md).</span></span> <span data-ttu-id="6075e-146">Azure Data Lake опциясын таңдау ресурстарға негізделген немесе жазылымға негізделген тәсілдерді таңдауға мүмкіндік береді.</span><span class="sxs-lookup"><span data-stu-id="6075e-146">Choosing the Azure Data Lake option lets you choose between a resource-based or a subscription-based based approach.</span></span>

<span data-ttu-id="6075e-147">Таңдалған тәсіл туралы қажетті ақпаратты беру үшін төмендегі қадамдарды орындаңыз.</span><span class="sxs-lookup"><span data-stu-id="6075e-147">Follow the below steps to provide the required information on the selected approach.</span></span>

### <a name="resource-based-storage-account-connection"></a><span data-ttu-id="6075e-148">Ресурсқа негізделген сақтау тіркелгісінің байланысы</span><span class="sxs-lookup"><span data-stu-id="6075e-148">Resource-based storage account connection</span></span>

1. <span data-ttu-id="6075e-149">[Azure әкімші порталына](https://portal.azure.com) өтіп, жазылымға кіріңіз де, сақтау тіркелгісін ашыңыз.</span><span class="sxs-lookup"><span data-stu-id="6075e-149">Go to the [Azure admin portal](https://portal.azure.com), sign in to your subscription and open the storage account.</span></span>

1. <span data-ttu-id="6075e-150">Навигация тақтасында **Параметрлер** > **Сипаттар** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="6075e-150">Go to **Settings** > **Properties** on navigation pane.</span></span>

1. <span data-ttu-id="6075e-151">Сақтау тіркелгісінің ресурстық идентификаторының мәнін көшіріңіз.</span><span class="sxs-lookup"><span data-stu-id="6075e-151">Copy the storage account resource ID value.</span></span>

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="Сақтау тіркелгісінің ресурстық идентификаторын көшіріңіз.":::

1. <span data-ttu-id="6075e-153">Аудитория мәліметтерінде ресурс идентификаторын сақтау тіркелгісінің қосылу экранында көрсетілетін ресурстар өрісіне енгізіңіз.</span><span class="sxs-lookup"><span data-stu-id="6075e-153">In audience insights, insert the resource ID in the resource field displayed in the storage account connection screen.</span></span>

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="Сақтау тіркелгісінің ресурстық идентификаторының ақпаратын енгізіңіз.":::   
   
1. <span data-ttu-id="6075e-155">Сақтау тіркелгісін тіркеу үшін аудитория мәліметтеріндегі қалған қадамдарды жалғастырыңыз.</span><span class="sxs-lookup"><span data-stu-id="6075e-155">Continue with the remaining steps in audience insights to attach the storage account.</span></span>

### <a name="subscription-based-storage-account-connection"></a><span data-ttu-id="6075e-156">Жазылымға негізделген сақтау тіркелгісінің байланысы</span><span class="sxs-lookup"><span data-stu-id="6075e-156">Subscription-based storage account connection</span></span>

1. <span data-ttu-id="6075e-157">[Azure әкімші порталына](https://portal.azure.com) өтіп, жазылымға кіріңіз де, сақтау тіркелгісін ашыңыз.</span><span class="sxs-lookup"><span data-stu-id="6075e-157">Go to the [Azure admin portal](https://portal.azure.com), sign in to your subscription and open the storage account.</span></span>

1. <span data-ttu-id="6075e-158">Навигация тақтасында **Параметрлер** > **Сипаттар** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="6075e-158">Go to **Settings** > **Properties** on navigation pane.</span></span>

1. <span data-ttu-id="6075e-159">Аудитория мәліметтерінде дұрыс мәндерді таңдау үшін сақтау тіркелгісінің **Жазылым**, **Ресурс тобы** және **Атауы** элементтерін қарап шығыңыз.</span><span class="sxs-lookup"><span data-stu-id="6075e-159">Review the **Subscription**, **Resource group**, and the **Name** of the storage account to make sure you select the right values in audience insights.</span></span>

1. <span data-ttu-id="6075e-160">Аудитория мәліметтерінде сақтау тіркелгісін тіркеу кезінде мәндерді немесе сәйкес өрістерді таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="6075e-160">In audience insights, choose the values or for the corresponding fields when attaching the storage account.</span></span>
   
1. <span data-ttu-id="6075e-161">Сақтау тіркелгісін тіркеу үшін аудитория мәліметтеріндегі қалған қадамдарды жалғастырыңыз.</span><span class="sxs-lookup"><span data-stu-id="6075e-161">Continue with the remaining steps in audience insights to attach the storage account.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]