---
title: Қызмет негізін пайдалану арқылы Azure Data Lake Storage тіркелгісіне қосылу
description: Жеке деректер көліне қосылу үшін Azure қызмет негізін пайдаланыңыз.
ms.date: 12/06/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 1af01e5579f85d7c8bc8976a003f53ef2dd280d1
ms.sourcegitcommit: b7189b8621e66ee738e4164d4b3ce2af0def3f51
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 02/03/2022
ms.locfileid: "8088154"
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

4. Microsoft бағдарламасы идентификаторын іздеу:
   - Аудитория туралы пайдалы мәліметтер: `Dynamics 365 AI for Customer Insights` атауымен `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff`
   - Өзара әрекеттестік туралы пайдалы мәліметтер: `Dynamics 365 AI for Customer Insights engagement insights` атауымен `ffa7d2fe-fc04-4599-9f6d-7ca06dd0c4fd`

5. Егер сәйкес жазбаны тапсаңыз, бұл қызмет негізі бұрыннан бар екенін білдіреді. 
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Қолданыстағы қызмет негізін көрсететін скриншот.":::
   
6. Егер ешбір нәтиже қайтарылмаса, жаңа субъект-қызметін жасаңыз.

>[!NOTE]
>Dynamics 365 Customer Insights толық қуатын пайдалану үшін қызмет негізіне екі бағдарламаны да қосу ұсынылады.

### <a name="create-a-new-service-principal"></a>Жаңа субъект-қызметін жасау

1. Azure Active Directory PowerShell for Graph бағдарламасының соңғы нұсқасын орнатыңыз. Қосымша ақпарат алу үшін [Azure Active Directory PowerShell for Graph бағдарламасын орнату](/powershell/azure/active-directory/install-adv2) бөліміне өтіңіз.

   1. Компьютерде пернетақтадағы Windows пернесін таңдап, **Windows PowerShell** іздеп, **Әкімші ретінде іске қосу** опциясын таңдаңыз.
   
   1. Ашылатын PowerShell терезесінде `Install-Module AzureAD` енгізіңіз.

2. Azure AD PowerShell модулімен Customer Insights арналған қызмет негізін жасаңыз.

   1. PowerShell терезесінде `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure` енгізіңіз. *[Қатысушы идентификаторын]* қызмет негізін жасау қажет қатысушының нақты идентификаторымен ауыстырыңыз. `AzureEnvironmentName` орта атауының параметрі міндетті емес.
  
   1. `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"` енгізіңіз. Бұл пәрмен таңдалған қатысушыда аудитория мәліметтері бойынша субъект-қызметін жасайды. 

   1. `New-AzureADServicePrincipal -AppId "ffa7d2fe-fc04-4599-9f6d-7ca06dd0c4fd" -DisplayName "Dynamics 365 AI for Customer Insights engagement insights"` енгізіңіз. Бұл пәрмен өзара әрекеттестік туралы пайдалы мәліметтер үшін таңдалған қатысушыда қызмет негізін жасайды.

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

[Шығыс деректерін сақтау](manage-environments.md) немесе [оны деректер көзі ретінде пайдалану](connect-common-data-service-lake.md) үшін аудитория мәліметтерінде Data Lake Storage тіркелгісін тіркеуге болады. Бұл опция ресурсқа негізделген немесе жазылымға негізделген тәсілдің бірін таңдауға мүмкіндік береді. Сіз таңдаған тәсілге байланысты келесі бөлімдердің біріндегі процедураны орындаңыз.

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
