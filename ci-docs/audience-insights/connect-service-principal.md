---
title: Қызмет негізін пайдалану арқылы Azure Data Lake Storage тіркелгісіне қосылу
description: Жеке деректер көліне қосылу үшін Azure қызмет негізін пайдаланыңыз.
ms.date: 07/23/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 845d1f55eb99f2adf9b437124addec4f6d016fec
ms.sourcegitcommit: 1c396394470df8e68c2fafe3106567536ff87194
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 08/30/2021
ms.locfileid: "7461155"
---
# <a name="connect-to-an-azure-data-lake-storage-account-by-using-an-azure-service-principal"></a>Azure қызмет негізін пайдалану арқылы Azure Data Lake Storage тіркелгісіне қосылу
<!--note from editor: The Cloud Style Guide would have us just use "Azure Data Lake Storage" to mean the current version, unless the old version (Gen1) is mentioned. I've followed this guidance, even though it seems that our docs and Azure docs are all over the map on this.-->
Azure қызметтерін пайдаланатын автоматтандырылған құралдарда әрдайым шектеулі рұқсаттар болуы тиіс. Бағдарламалардың толық артықшылықты пайдаланушы ретінде кіруінің орнына, Azure субъект-қызметтерін ұсынады. Сақтау орнының тіркелгі кілттерінің орнына Azure қызмет негізін пайдалану арқылы Dynamics 365 Customer Insights қызметін Azure Data Lake Storage тіркелгісімен байланыстыру жолы туралы мәлімет алу үшін оқыңыз. 

Қызмет негізін [Common Data Model қалтасын деректер көзі ретінде қауіпсіз түрде қосу және өңдеу](connect-common-data-model.md) немесе [ортаны жасау және жаңарту](get-started-paid.md) үшін пайдалануға болады.<!--note from editor: Suggested. Or it could be ", or create a new environment or update an existing one". I think "new" is implied with "create". The comma is necessary.-->

> [!IMPORTANT]
> - Пайдаланылатын Data Lake Storage тіркелгісі<!--note from editor: Suggested. Or perhaps it could be "The Data Lake Storage account to which you want to give access to the service principal..."--> қызмет негізінде [қосылған иерархиялық атаулар кеңістігі](/azure/storage/blobs/data-lake-storage-namespace) болуы тиіс.
> - Субъект-қызметін жасау үшін Azure жазылымына арналған әкімші рұқсаттары қажет.

## <a name="create-an-azure-service-principal-for-customer-insights"></a>Customer Insights үшін Azure қызмет негізін жасау

Аудитория туралы пайдалы мәліметтер немесе өзара әрекеттестік туралы пайдалы мәліметтер үшін жаңа қызмет негізін жасамас бұрын оның ұйымда бар екендігін тексеріңіз.

### <a name="look-for-an-existing-service-principal"></a>Бар субъект-қызметін іздеңіз

1. [Azure әкімші порталына](https://portal.azure.com) өтіп, ұйымыңызға кіріңіз.

2. **Azure қызметтері** өрісінен **Azure Active Directory** таңдаңыз.

3. **Басқару** тармағында **Кәсіпорын бағдарламалары** опциясын таңдаңыз.

4. Microsoft жүйесін іздеу<!--note from editor: Via Microsoft Writing Style Guide.--> бағдарлама идентификаторы:
   - Аудитория туралы пайдалы мәліметтер: `Dynamics 365 AI for Customer Insights` атауымен `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff`
   - Өзара әрекеттестік туралы пайдалы мәліметтер: `Dynamics 365 AI for Customer Insights engagement insights` атауымен `ffa7d2fe-fc04-4599-9f6d-7ca06dd0c4fd`

5. Егер сәйкес жазбаны тапсаңыз, бұл қызмет негізі бұрыннан бар екенін білдіреді. 
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Қолданыстағы қызмет негізін көрсететін скриншот.":::
   
6. Егер ешбір нәтиже қайтарылмаса, жаңа субъект-қызметін жасаңыз.

>[!NOTE]
>Dynamics 365 Customer Insights толық қуатын пайдалану үшін қызмет негізіне екі бағдарламаны да қосу ұсынылады.<!--note from editor: Using the note format is suggested, just so this doesn't get lost by being tucked up in the step.-->

### <a name="create-a-new-service-principal"></a>Жаңа субъект-қызметін жасау
<!--note from editor: Some general formatting notes: The MWSG wants bold for text the user enters (in addition to UI strings and the settings users select), but there's plenty of precedent for using code format for entering text in PowerShell so I didn't change that. Note that italic should be used for placeholders, but not much else.-->
1. Azure Active Directory PowerShell for Graph бағдарламасының соңғы нұсқасын орнатыңыз. Қосымша ақпарат алу үшін [Azure Active Directory PowerShell for Graph бағдарламасын орнату](/powershell/azure/active-directory/install-adv2) бөліміне өтіңіз.

   1. Компьютерде пернетақтадағы Windows пернесін таңдап, **Windows PowerShell** іздеп, **Әкімші ретінде іске қосу** опциясын таңдаңыз.<!--note from editor: Or should this be something like "search for **Windows PowerShell** and, if asked, select **Run as administrator**."?-->
   
   1. Ашылатын PowerShell терезесінде `Install-Module AzureAD` енгізіңіз.

2. Azure AD PowerShell модулімен Customer Insights арналған қызмет негізін жасаңыз.

   1. PowerShell терезесінде `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure` енгізіңіз. *"[қатысушы идентификаторын]"* ауыстыру<!--note from editor: Edit okay? Or should the quotation marks stay in the command line, in which case it would be "Replace *[your tenant ID]* --> қызмет негізін жасағыңыз келетін қатысушының нақты идентификаторы. `AzureEnvironmentName` орта атауының параметрі міндетті емес.
  
   1. `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"` енгізіңіз. Бұл пәрмен таңдалған қатысушыда аудитория мәліметтері бойынша субъект-қызметін жасайды. 

   1. `New-AzureADServicePrincipal -AppId "ffa7d2fe-fc04-4599-9f6d-7ca06dd0c4fd" -DisplayName "Dynamics 365 AI for Customer Insights engagement insights"` енгізіңіз. Бұл пәрмен өзара әрекеттестік туралы пайдалы мәліметтер үшін қызмет негізін жасайды<!--note from editor: Edit okay?--> таңдалған қатысушыда.

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a>Сақтау тіркелгісіне қатынасу үшін субъект-қызметіне рұқсаттар беріңіз

Аудитория мәліметтерінде пайдаланылатын сақтау тіркелгісі бойынша субъект-қызметке рұқсаттар беру үшін Azure порталына өтіңіз.

1. [Azure әкімші порталына](https://portal.azure.com) өтіп, ұйымыңызға кіріңіз.

1. Аудитория мәліметтері бойынша субъект-қызмет қатынаса алатын сақтау тіркелгісін ашыңыз.

1. Сол жақ тақтадан **Кіруді басқару (IAM)**, содан кейін **Қосу** > **Рөл тағайындауды қосу** тармағын таңдаңыз.

   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Рөл тағайындауын қосу кезінде Azure порталын көрсететін скриншот.":::

1. **Рөл тағайындауды қосу** тақтасында келесі сипаттарды орнатыңыз:
   - Рөл: **Blob сақтау құралы деректерін қосушы**
   - Мыналарға қатынасу рұқсатын тағайындаңыз: **Пайдаланушы, топ немесе субъект-қызмет**
   - Таңдаңыз: **Customer Insights арналған Dynamics 365 AI** және **Customer Insights өзара әрекеттестік туралы пайдалы мәліметтерге арналған Dynamics 365 AI** (осы процедурада ертерек жасалған [қызмет негізі](#create-a-new-service-principal))

1.  **Сақтау** опциясын таңдаңыз.

Өзгерістерді үлгілеу 15 минутқа созылуы мүмкін.

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-audience-insights"></a>Аудитория мәліметтеріне сақтау тіркелгісін тіркеуде Azure ресурс идентификаторын немесе Azure жазылымы мәліметтерін енгізіңіз

Төмендегілерді орындауға болады<!--note from editor: Edit suggested only if this section is optional.--> [шығыс деректерін сақтау](manage-environments.md) немесе [оны деректер көзі ретінде пайдалану](connect-common-data-service-lake.md) үшін аудитория мәліметтерінде Data Lake Storage тіркелгісін тіркеу. Бұл опция ресурсқа негізделген немесе жазылымға негізделген тәсілдің бірін таңдауға мүмкіндік береді. Сіз таңдаған тәсілге байланысты келесі бөлімдердің біріндегі процедураны орындаңыз.<!--note from editor: Suggested.-->

### <a name="resource-based-storage-account-connection"></a>Ресурсқа негізделген сақтау тіркелгісінің байланысы

1. [Azure әкімші порталына](https://portal.azure.com) өтіп, жазылымға кіріңіз де, сақтау тіркелгісін ашыңыз.

1. Сол жақ тақтада **Параметрлер** > **Сипаттары** тармағына өтіңіз.

1. Сақтау тіркелгісінің ресурстық идентификаторының мәнін көшіріңіз.

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="Сақтау тіркелгісінің ресурстық идентификаторын көшіріңіз.":::

1. Аудитория мәліметтерінде ресурс идентификаторын сақтау тіркелгісінің қосылу экранында көрсетілетін ресурс өрісіне енгізіңіз.

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="Сақтау тіркелгісінің ресурстық идентификаторының ақпаратын енгізіңіз.":::   

1. Сақтау тіркелгісін тіркеу үшін аудитория мәліметтеріндегі қалған қадамдарды жалғастырыңыз.

### <a name="subscription-based-storage-account-connection"></a>Жазылымға негізделген сақтау тіркелгісінің байланысы

1. [Azure әкімші порталына](https://portal.azure.com) өтіп, жазылымға кіріңіз де, сақтау тіркелгісін ашыңыз.

1. Сол жақ тақтада **Параметрлер** > **Сипаттары** тармағына өтіңіз.

1. Аудитория мәліметтерінде дұрыс мәндерді таңдау үшін сақтау тіркелгісінің **Жазылым**, **Ресурс тобы** және **Атауы** элементтерін қарап шығыңыз.

1. Аудитория туралы пайдалы мәліметтерде сақтау тіркелгісін тіркеген кезде сәйкес өрістердің мәндерін таңдаңыз.

1. Сақтау тіркелгісін тіркеу үшін аудитория мәліметтеріндегі қалған қадамдарды жалғастырыңыз.


[!INCLUDE[footer-include](../includes/footer-banner.md)]