---
title: Субъект-қызметімен Azure Data Lake Storage Gen2 тіркелгісіне қосылу
description: Аудитория мәліметтеріне тіркеу кезінде өз деректер көліңізге қосу үшін аудитория мәліметтеріне арналған Azure субъект-қызметін пайдаланыңыз.
ms.date: 11/24/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: c2fae278d34fa02b9168ac70dfa8dd351653245e
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 11/25/2020
ms.locfileid: "4644095"
---
# <a name="connect-to-an-azure-data-lake-storage-gen2-account-with-an-azure-service-principal-for-audience-insights"></a><span data-ttu-id="96512-103">Аудитория мәліметтері бойынша Azure субъект-қызметімен Azure Data Lake Storage Gen2 тіркелгісіне қосылыңыз</span><span class="sxs-lookup"><span data-stu-id="96512-103">Connect to an Azure Data Lake Storage Gen2 account with an Azure service principal for audience insights</span></span>

<span data-ttu-id="96512-104">Azure қызметтерін пайдаланатын автоматтандырылған құралдарда әрдайым шектеулі рұқсаттар болуы тиіс.</span><span class="sxs-lookup"><span data-stu-id="96512-104">Automated tools that use Azure services should always have restricted permissions.</span></span> <span data-ttu-id="96512-105">Бағдарламалардың толық артықшылықты пайдаланушы ретінде кіруінің орнына, Azure субъект-қызметтерін ұсынады.</span><span class="sxs-lookup"><span data-stu-id="96512-105">Instead of having applications sign in as a fully privileged user, Azure offers service principals.</span></span> <span data-ttu-id="96512-106">Сақтау тіркелгісі кілттерінің орнына Azure субхект-қызметін пайдаланып Azure Data Lake Storage Gen2 тіркелгісімен аудитория мәліметтерін қосу жолдары туралы оқыңыз.</span><span class="sxs-lookup"><span data-stu-id="96512-106">Read on to learn how to connect audience insights with an Azure Data Lake Storage Gen2 account using an Azure service principal instead of storage account keys.</span></span> 

<span data-ttu-id="96512-107">[Common Data Model қалтасын деректер көзі ретінде қауіпсіз түрде қосу](connect-common-data-model.md) немесе [жаңасын жасау немесе бұрыннан бар ортаны жаңарту үшін](manage-environments.md#create-an-environment-in-an-existing-organization) субъект-қызметін пайдалануға болады.</span><span class="sxs-lookup"><span data-stu-id="96512-107">You can use the service principal to securely [add or edit a Common Data Model folder as a data source](connect-common-data-model.md) or [create a new or update an existing environment](manage-environments.md#create-an-environment-in-an-existing-organization).</span></span>

<span data-ttu-id="96512-108">Субъект-қызметін жасау үшін Azure жазылымына арналған әкімші рұқсаттары қажет.</span><span class="sxs-lookup"><span data-stu-id="96512-108">You need admin permissions for your Azure subscription to create the service principal.</span></span>

## <a name="create-azure-service-principal-for-audience-insights"></a><span data-ttu-id="96512-109">Аудитория мәліметтеріне арналған Azure субъект-қызметін жасаңыз</span><span class="sxs-lookup"><span data-stu-id="96512-109">Create Azure service principal for audience insights</span></span>

<span data-ttu-id="96512-110">Аудитория мәліметтеріне арналған жаңа субъект-қызметін жасау алдында ұйымда бұрыннан болуын тексеріңіз.</span><span class="sxs-lookup"><span data-stu-id="96512-110">Before creating a new service principal for audience insights, check if it already exists in your organization.</span></span>

### <a name="look-for-an-existing-service-principal"></a><span data-ttu-id="96512-111">Бар субъект-қызметін іздеңіз</span><span class="sxs-lookup"><span data-stu-id="96512-111">Look for an existing service principal</span></span>

1. <span data-ttu-id="96512-112">[Azure әкімші порталына](https://portal.azure.com) өтіп, ұйымыңызға кіріңіз.</span><span class="sxs-lookup"><span data-stu-id="96512-112">Go to the [Azure admin portal](https://portal.azure.com) and sign in to your organization.</span></span>

2. <span data-ttu-id="96512-113">Azure қызметтерінен **Azure Active Directory** таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="96512-113">Select **Azure Active Directory** from the Azure services.</span></span>

3. <span data-ttu-id="96512-114">**Басқару** тармағында **Кәсіпорын бағдарламалары** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="96512-114">Under **Manage**, select **Enterprise Applications**.</span></span>

4. <span data-ttu-id="96512-115">Аудитория мәліметтерінің бірінші тараптағы бағдарлама идентификаторын `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` немесе `Dynamics 365 AI for Customer Insights` атауын іздеңіз.</span><span class="sxs-lookup"><span data-stu-id="96512-115">Search for the audience insights first party application ID `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` or the name `Dynamics 365 AI for Customer Insights`.</span></span>

5. <span data-ttu-id="96512-116">Егер сәйкес жазбаны тапсаңыз, бұл аудитория мәліметтеріне арналған субъект-қызметі бар дегенді білдіреді.</span><span class="sxs-lookup"><span data-stu-id="96512-116">If you find a matching record, it means that the service principal for audience insights exists.</span></span> <span data-ttu-id="96512-117">Оны қайта жасаудың қажеті жоқ.</span><span class="sxs-lookup"><span data-stu-id="96512-117">You don't need to create it again.</span></span>
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Қолданыстағы субъект-қызметін көрсететін скриншот.":::
   
6. <span data-ttu-id="96512-119">Егер ешбір нәтиже қайтарылмаса, жаңа субъект-қызметін жасаңыз.</span><span class="sxs-lookup"><span data-stu-id="96512-119">If no results are returned, create a new service principal.</span></span>

### <a name="create-a-new-service-principal"></a><span data-ttu-id="96512-120">Жаңа субъект-қызметін жасау</span><span class="sxs-lookup"><span data-stu-id="96512-120">Create a new service principal</span></span>

1. <span data-ttu-id="96512-121">**Графикке арналған Azure Active Directory PowerShell** соңғы нұсқасын орнатыңыз.</span><span class="sxs-lookup"><span data-stu-id="96512-121">Install the latest version of the **Azure Active Directory PowerShell for Graph**.</span></span> <span data-ttu-id="96512-122">Қосымша ақпарат алу үшін [Графикке арналған Azure Active Directory PowerShell](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) бөлімін қараңыз.</span><span class="sxs-lookup"><span data-stu-id="96512-122">For more information, see [Install Azure Active Directory PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2).</span></span>
   - <span data-ttu-id="96512-123">Дербес компьютерде пернетақтада Windows кілтін таңдап, **Windows PowerShell** және **Әкімші ретінде іске қосу** параметрлерін іздеңіз.</span><span class="sxs-lookup"><span data-stu-id="96512-123">On your PC, select the Windows key on your keyboard and search for **Windows PowerShell** and **Run as Administrator**.</span></span>
   
   - <span data-ttu-id="96512-124">Ашылатын PowerShell терезесінде `Install-Module AzureAD` енгізіңіз.</span><span class="sxs-lookup"><span data-stu-id="96512-124">In the PowerShell window that opens, enter `Install-Module AzureAD`.</span></span>

2. <span data-ttu-id="96512-125">Azure AD PowerShell модулімен аудитория мәліметтері бойынша субъект-қызмет жасаңыз.</span><span class="sxs-lookup"><span data-stu-id="96512-125">Create the  service principal for audience insights with the Azure AD PowerShell Module.</span></span>
   - <span data-ttu-id="96512-126">PowerShell терезесінде `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure` енгізіңіз.</span><span class="sxs-lookup"><span data-stu-id="96512-126">In the PowerShell window, enter `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`.</span></span> <span data-ttu-id="96512-127">«Қатысушы идентификаторын» субъект-қызмет жасау қажет қатысушының нақты идентификаторымен ауыстырыңыз.</span><span class="sxs-lookup"><span data-stu-id="96512-127">Replace “your tenant ID” with the actual ID of your tenant where you want to create the service principal.</span></span> <span data-ttu-id="96512-128">Орта атауының `AzureEnvironmentName` параметрі міндетті емес,</span><span class="sxs-lookup"><span data-stu-id="96512-128">The environment name parameter `AzureEnvironmentName` is optional.</span></span>
  
   - <span data-ttu-id="96512-129">`New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"` енгізіңіз.</span><span class="sxs-lookup"><span data-stu-id="96512-129">Enter `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`.</span></span> <span data-ttu-id="96512-130">Бұл пәрмен таңдалған қатысушыда аудитория мәліметтері бойынша субъект-қызметін жасайды.</span><span class="sxs-lookup"><span data-stu-id="96512-130">This command creates the service principal for audience insights on the selected tenant.</span></span>  

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a><span data-ttu-id="96512-131">Сақтау тіркелгісіне қатынасу үшін субъект-қызметіне рұқсаттар беріңіз</span><span class="sxs-lookup"><span data-stu-id="96512-131">Grant permissions to the service principal to access the storage account</span></span>

<span data-ttu-id="96512-132">Аудитория мәліметтерінде пайдаланылатын сақтау тіркелгісі бойынша субъект-қызметке рұқсаттар беру үшін Azure порталына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="96512-132">Go to the Azure portal to grant permissions to the service principal for the storage account you want to use in audience insights.</span></span>

1. <span data-ttu-id="96512-133">[Azure әкімші порталына](https://portal.azure.com) өтіп, ұйымыңызға кіріңіз.</span><span class="sxs-lookup"><span data-stu-id="96512-133">Go to the [Azure admin portal](https://portal.azure.com) and sign in to your organization.</span></span>

1. <span data-ttu-id="96512-134">Аудитория мәліметтері бойынша субъект-қызмет қатынаса алатын сақтау тіркелгісін ашыңыз.</span><span class="sxs-lookup"><span data-stu-id="96512-134">Open the storage account you want the service principal for audience insights to have access to.</span></span>

1. <span data-ttu-id="96512-135">Навигация тақтасынан **Қатынасты басқару (IAM)** таңдап, **Қосу** > **Рөл тағайындауын қосу** тармағын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="96512-135">Select **Access control (IAM)** from the navigation pane and select **Add** > **Add role assignment**.</span></span>
   
   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Рөл тағайындауды қосу кезінде Azure порталын көрсететін скриншот.":::
   
1. <span data-ttu-id="96512-137">**Рөл тағайындауды қосу** тақтасында келесі сипаттарды орнатыңыз:</span><span class="sxs-lookup"><span data-stu-id="96512-137">In the **Add role assignment** pane, set the following properties:</span></span>
   - <span data-ttu-id="96512-138">Рөл: *Blob сақтау құралы деректерін қосушы*</span><span class="sxs-lookup"><span data-stu-id="96512-138">Role: *Storage Blob Data Contributor*</span></span>
   - <span data-ttu-id="96512-139">Мыналарға қатынасу рұқсатын тағайындаңыз: *Пайдаланушы, топ немесе субъект-қызмет*</span><span class="sxs-lookup"><span data-stu-id="96512-139">Assign access to: *User, group, or service principal*</span></span>
   - <span data-ttu-id="96512-140">Таңдаңыз: *Customer Insights жүйесіне арналған Dynamics 365 AI* ([сіз жасаған субъект-қызмет](#create-a-new-service-principal))</span><span class="sxs-lookup"><span data-stu-id="96512-140">Select: *Dynamics 365 AI for Customer Insights* (the [service principal you created](#create-a-new-service-principal))</span></span>

1.  <span data-ttu-id="96512-141">**Сақтау** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="96512-141">Select **Save**.</span></span>

<span data-ttu-id="96512-142">Өзгерістерді үлгілеу 15 минутқа созылуы мүмкін.</span><span class="sxs-lookup"><span data-stu-id="96512-142">It can take up to 15 minutes to propagate the changes.</span></span>

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-audience-insights"></a><span data-ttu-id="96512-143">Аудитория мәліметтеріне сақтау тіркелгісін тіркеуде Azure ресурс идентификаторын немесе Azure жазылымы мәліметтерін енгізіңіз.</span><span class="sxs-lookup"><span data-stu-id="96512-143">Enter the Azure Resource ID or the Azure Subscription details in the storage account attachment to Audience Insights.</span></span>

<span data-ttu-id="96512-144">[Нәтиже деректерін сақтау](manage-environments.md) үшін немесе [оны деректер көзі ретінде пайдалану](connect-common-data-service-lake.md) үшін аудитория мәліметтерінде Azure Data Lake сақтау тіркелгісін тіркеңіз.</span><span class="sxs-lookup"><span data-stu-id="96512-144">Attach an Azure Data Lake storage account in audience insights to [store output data](manage-environments.md) or [use it as a data source](connect-common-data-service-lake.md).</span></span> <span data-ttu-id="96512-145">Azure Data Lake опциясын таңдау ресурстарға негізделген немесе жазылымға негізделген тәсілдерді таңдауға мүмкіндік береді.</span><span class="sxs-lookup"><span data-stu-id="96512-145">Choosing the Azure Data Lake option lets you choose between a resource-based or a subscription-based based approach.</span></span>

<span data-ttu-id="96512-146">Таңдалған тәсіл туралы қажетті ақпаратты беру үшін төмендегі қадамдарды орындаңыз.</span><span class="sxs-lookup"><span data-stu-id="96512-146">Follow the below steps to provide the required information on the selected approach.</span></span>

### <a name="resounce-based-storage-account-connection"></a><span data-ttu-id="96512-147">Ресурсқа негізделген сақтау тіркелгісінің байланысы</span><span class="sxs-lookup"><span data-stu-id="96512-147">Resounce-based storage account connection</span></span>

1. <span data-ttu-id="96512-148">[Azure әкімші порталына](https://portal.azure.com) өтіп, жазылымға кіріңіз де, сақтау тіркелгісін ашыңыз.</span><span class="sxs-lookup"><span data-stu-id="96512-148">Go to the [Azure admin portal](https://portal.azure.com), sign in to your subscription and open the storage account.</span></span>

1. <span data-ttu-id="96512-149">Навигация тақтасында **Параметрлер** > **Сипаттар** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="96512-149">Go to **Settings** > **Properties** on navigation pane.</span></span>

1. <span data-ttu-id="96512-150">Сақтау тіркелгісінің ресурстық идентификаторының мәнін көшіріңіз.</span><span class="sxs-lookup"><span data-stu-id="96512-150">Copy the storage account resource ID value.</span></span>

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="Сақтау тіркелгісінің ресурстық идентификаторын көшіріңіз.":::

1. <span data-ttu-id="96512-152">Аудитория мәліметтерінде ресурс идентификаторын сақтау тіркелгісінің қосылу экранында көрсетілетін ресурстар өрісіне енгізіңіз.</span><span class="sxs-lookup"><span data-stu-id="96512-152">In audience insights, insert the resource ID in the resource field displayed in the storage account connection screen.</span></span>

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="Сақтау тіркелгісінің ресурстық идентификаторының ақпаратын енгізіңіз.":::   
   
1. <span data-ttu-id="96512-154">Сақтау тіркелгісін тіркеу үшін аудитория мәліметтеріндегі қалған қадамдарды жалғастырыңыз.</span><span class="sxs-lookup"><span data-stu-id="96512-154">Continue with the remaining steps in audience insights to attach the storage account.</span></span>

### <a name="subscription-based-storage-account-connection"></a><span data-ttu-id="96512-155">Жазылымға негізделген сақтау тіркелгісінің байланысы</span><span class="sxs-lookup"><span data-stu-id="96512-155">Subscription-based storage account connection</span></span>

1. <span data-ttu-id="96512-156">[Azure әкімші порталына](https://portal.azure.com) өтіп, жазылымға кіріңіз де, сақтау тіркелгісін ашыңыз.</span><span class="sxs-lookup"><span data-stu-id="96512-156">Go to the [Azure admin portal](https://portal.azure.com), sign in to your subscription and open the storage account.</span></span>

1. <span data-ttu-id="96512-157">Навигация тақтасында **Параметрлер** > **Сипаттар** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="96512-157">Go to **Settings** > **Properties** on navigation pane.</span></span>

1. <span data-ttu-id="96512-158">Аудитория мәліметтерінде дұрыс мәндерді таңдау үшін сақтау тіркелгісінің **Жазылым**, **Ресурс тобы** және **Атауы** элементтерін қарап шығыңыз.</span><span class="sxs-lookup"><span data-stu-id="96512-158">Review the **Subscription**, **Resource group**, and the **Name** of the storage account to make sure you select the right values in audience insights.</span></span>

1. <span data-ttu-id="96512-159">Аудитория мәліметтерінде сақтау тіркелгісін тіркеу кезінде мәндерді немесе сәйкес өрістерді таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="96512-159">In audience insights, choose the values or for the corresponding fields when attaching the storage account.</span></span>

   :::image type="content" source="media/ADLS-SP-SubscriptionConnection.png" alt-text="Сақтау тіркелгісінің ресурстық идентификаторының ақпаратын енгізіңіз.":::
   
1. <span data-ttu-id="96512-161">Сақтау тіркелгісін тіркеу үшін аудитория мәліметтеріндегі қалған қадамдарды жалғастырыңыз.</span><span class="sxs-lookup"><span data-stu-id="96512-161">Continue with the remaining steps in audience insights to attach the storage account.</span></span>
