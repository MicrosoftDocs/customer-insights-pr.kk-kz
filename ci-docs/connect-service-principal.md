---
title: Қызмет негізін пайдалану арқылы Azure Data Lake Storage тіркелгісіне қосылу
description: Жеке деректер көліне қосылу үшін Azure қызмет негізін пайдаланыңыз.
ms.date: 04/26/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-system-security
- customerInsights
ms.openlocfilehash: 1dd99edc327bd41b0442b390f2e4f8664269f553
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: kk-KZ
ms.lasthandoff: 04/27/2022
ms.locfileid: "8643348"
---
# <a name="connect-to-an-azure-data-lake-storage-account-by-using-an-azure-service-principal"></a>Azure қызмет негізін пайдалану арқылы Azure Data Lake Storage тіркелгісіне қосылу

Бұл мақалада қосылу әдісі қарастырылады Dynamics 365 Customer Insights а Azure Data Lake Storage тіркелгіні сақтау тіркелгі кілттерінің орнына Azure қызмет көрсетушісін пайдалану арқылы. 

Azure қызметтерін пайдаланатын автоматтандырылған құралдарда әрдайым шектеулі рұқсаттар болуы тиіс. Бағдарламалардың толық артықшылықты пайдаланушы ретінде кіруінің орнына, Azure субъект-қызметтерін ұсынады. Қауіпсіз болу үшін қызмет жетекшілерін пайдалануға болады [Жалпы деректер үлгісі қалтасын деректер көзі ретінде қосыңыз немесе өңдеңіз](connect-common-data-model.md) немесе [ортаны жасау немесе жаңарту](create-environment.md).

> [!IMPORTANT]
> - Негізгі қызметті пайдаланатын Data Lake Storage тіркелгісі Gen2 болуы және болуы керек [иерархиялық аттар кеңістігі қосылды](/azure/storage/blobs/data-lake-storage-namespace). Azure Data Lake Gen1 сақтау тіркелгілеріне қолдау көрсетілмейді.
> - Қызмет басшысын жасау үшін сізге Azure жазылымына әкімші рұқсаттары қажет.

## <a name="create-an-azure-service-principal-for-customer-insights"></a>Customer Insights үшін Azure қызмет негізін жасау

Customer Insights үшін жаңа қызмет негізін жасамас бұрын, оның ұйымыңызда бұрыннан бар-жоғын тексеріңіз.

### <a name="look-for-an-existing-service-principal"></a>Бар субъект-қызметін іздеңіз

1. [Azure әкімші порталына](https://portal.azure.com) өтіп, ұйымыңызға кіріңіз.

2. **Azure қызметтері** өрісінен **Azure Active Directory** таңдаңыз.

3. **Басқару** тармағында **Кәсіпорын бағдарламалары** опциясын таңдаңыз.

4. Microsoft қолданбасының идентификаторын іздеңіз`0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` атымен `Dynamics 365 AI for Customer Insights`.

5. Егер сәйкес жазбаны тапсаңыз, бұл қызмет негізі бұрыннан бар екенін білдіреді. 
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Қолданыстағы қызмет негізін көрсететін скриншот.":::
   
6. Егер ешбір нәтиже қайтарылмаса, жаңа субъект-қызметін жасаңыз.

### <a name="create-a-new-service-principal"></a>Жаңа субъект-қызметін жасау

1. Azure Active Directory PowerShell for Graph бағдарламасының соңғы нұсқасын орнатыңыз. Қосымша ақпарат алу үшін [Azure Active Directory PowerShell for Graph бағдарламасын орнату](/powershell/azure/active-directory/install-adv2) бөліміне өтіңіз.

   1. Компьютерде пернетақтадағы Windows пернесін таңдап, **Windows PowerShell** іздеп, **Әкімші ретінде іске қосу** опциясын таңдаңыз.
   
   1. Ашылатын PowerShell терезесінде `Install-Module AzureAD` енгізіңіз.

2. Azure AD PowerShell модулімен Customer Insights арналған қызмет негізін жасаңыз.

   1. PowerShell терезесінде `Connect-AzureAD -TenantId "[your Directory ID]" -AzureEnvironmentName Azure` енгізіңіз. Ауыстыру *[каталог идентификаторыңыз]* Azure жазылымының нақты Каталог идентификаторымен қызмет көрсетуші негізгі жасағыңыз келетін жерде. `AzureEnvironmentName` орта атауының параметрі міндетті емес.
  
   1. `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"` енгізіңіз. Бұл пәрмен таңдалған Azure жазылымында Customer Insights үшін қызмет негізін жасайды. 

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a>Сақтау тіркелгісіне қатынасу үшін субъект-қызметіне рұқсаттар беріңіз

Customer Insights бағдарламасында пайдаланғыңыз келетін сақтау тіркелгісі үшін қызмет басшысына рұқсаттар беру үшін Azure порталына өтіңіз.

1. [Azure әкімші порталына](https://portal.azure.com) өтіп, ұйымыңызға кіріңіз.

1. Customer Insights үшін қызмет көрсетушіге қатынасу қажет сақтау тіркелгісін ашыңыз.

1. Сол жақ тақтадан **Кіруді басқару (IAM)**, содан кейін **Қосу** > **Рөл тағайындауды қосу** тармағын таңдаңыз.

   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Рөл тағайындауын қосу кезінде Azure порталын көрсететін скриншот.":::

1. **Рөл тағайындауды қосу** тақтасында келесі сипаттарды орнатыңыз:
   - Рөл: **Blob сақтау құралы деректерін қосушы**
   - Мыналарға қатынасу рұқсатын тағайындаңыз: **Пайдаланушы, топ немесе субъект-қызмет**
   - Мүшелерді таңдаңыз: **Customer Insights үшін Dynamics 365 AI** ([қызмет көрсетуші](#create-a-new-service-principal) Сіз осы процедурада бұрын жасағансыз)

1.  таңдаңыз **Қарау + тағайындау**.

Өзгерістерді үлгілеу 15 минутқа созылуы мүмкін.

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-customer-insights"></a>Azure ресурсының идентификаторын немесе Azure жазылымының мәліметтерін Customer Insights жүйесіне сақтау тіркелгісінің тіркемесінде енгізіңіз.

Customer Insights қолданбасында Data Lake Storage тіркелгісін тіркей аласыз [шығыс деректерін сақтау](manage-environments.md) немесе [оны деректер көзі ретінде пайдаланыңыз](connect-dataverse-managed-lake.md). Бұл опция ресурсқа негізделген немесе жазылымға негізделген тәсілдің бірін таңдауға мүмкіндік береді. Сіз таңдаған тәсілге байланысты келесі бөлімдердің біріндегі процедураны орындаңыз.

### <a name="resource-based-storage-account-connection"></a>Ресурсқа негізделген сақтау тіркелгісінің байланысы

1. [Azure әкімші порталына](https://portal.azure.com) өтіп, жазылымға кіріңіз де, сақтау тіркелгісін ашыңыз.

1. Сол жақ тақтада **Параметрлер** > **Сипаттары** тармағына өтіңіз.

1. Сақтау тіркелгісінің ресурстық идентификаторының мәнін көшіріңіз.

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="Сақтау тіркелгісінің ресурстық идентификаторын көшіріңіз.":::

1. Customer Insights ішінде сақтау тіркелгісінің қосылым экранында көрсетілген ресурс өрісіне ресурс идентификаторын енгізіңіз.

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="Сақтау тіркелгісінің ресурстық идентификаторының ақпаратын енгізіңіз.":::   

1. Жад тіркелгісін тіркеу үшін Customer Insights ішіндегі қалған қадамдарды орындаңыз.

### <a name="subscription-based-storage-account-connection"></a>Жазылымға негізделген сақтау тіркелгісінің байланысы

1. [Azure әкімші порталына](https://portal.azure.com) өтіп, жазылымға кіріңіз де, сақтау тіркелгісін ашыңыз.

1. Сол жақ тақтада **Параметрлер** > **Сипаттары** тармағына өтіңіз.

1. шолу **Жазылым**, **тобы**, және **Аты** Customer Insights бағдарламасында дұрыс мәндерді таңдағаныңызға көз жеткізу үшін сақтау тіркелгісінің.

1. Customer Insights ішінде сақтау тіркелгісін тіркеген кезде сәйкес өрістер үшін мәндерді таңдаңыз.

1. Жад тіркелгісін тіркеу үшін Customer Insights ішіндегі қалған қадамдарды орындаңыз.


[!INCLUDE [footer-include](includes/footer-banner.md)]