---
title: Customer Insights ішіндегі қауіпсіздік параметрлері
description: Қауіпсіздік параметрлері туралы мына жерден біліңіз Dynamics 365 Customer Insights.
ms.date: 06/08/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 163deb9bed4f82d742c46cace27dd128f0aca18b
ms.sourcegitcommit: 8e9f0a9693fd8d91ad0227735ff03688fef5406f
ms.translationtype: MT
ms.contentlocale: kk-KZ
ms.lasthandoff: 06/10/2022
ms.locfileid: "8947422"
---
# <a name="security-settings-in-customer-insights"></a>Customer Insights ішіндегі қауіпсіздік параметрлері

The **Қауіпсіздік** бетте пайдаланушы рұқсаттары мен жасауға көмектесетін мүмкіндіктерді конфигурациялауға арналған опциялар тізімі берілген Dynamics 365 Customer Insights қауіпсізірек. Бұл бетке тек әкімшілер кіре алады.

Бару **Админ** > **Қауіпсіздік** параметрлерді конфигурациялау үшін.

The **Қауіпсіздік** бетте келесі қойындылар бар:

- [Пайдаланушылар](#users-tab)
- [API көрсеткіштері](#apis-tab)
- [Жеке сілтемелер](#private-links-tab)
- [Key Vault](#key-vault-tab)
- [Customer Lockbox көмегімен тұтынушы деректеріне қауіпсіз қол жеткізіңіз (алдын ала қарау)](#securely-access-customer-data-with-customer-lockbox-preview)

## <a name="users-tab"></a>Пайдаланушылар қойындысы

Customer Insights қолданбасына әкімші қосқан ұйымыңыздағы пайдаланушылармен шектелген. The **Пайдаланушылар** қойындысы пайдаланушы қатынасын және олардың рұқсаттарын басқаруға мүмкіндік береді. Қосымша ақпаратты қараңыз [Пайдаланушы рұқсаттары](permissions.md).

## <a name="apis-tab"></a>API қойындысы

пайдалану үшін пернелерді қараңыз және басқарыңыз [Customer Insights API интерфейстері](apis.md) ортаңыздың деректерімен.

Жаңа негізгі және қосымша кілттерді таңдау арқылы жасауға болады **Бастапқы қалпына келтіру** немесе **Екінші ретті қалпына келтіру**. 

Қоршаған ортаға API қатынасын блоктау үшін таңдаңыз **Өшіру**. API интерфейстері өшірілген болса, таңдауға болады **Қосу** қайта рұқсат беру үшін.

## <a name="private-links-tab"></a>Жеке сілтемелер қойындысы

[Azure жеке сілтемесі](/azure/private-link/private-link-overview) Customer Insights қолданбаңызға қосылсын Azure Data Lake Storage виртуалды желіңіздегі жеке соңғы нүкте арқылы тіркелгі. Жалпыға қолжетімді интернетке қосылмаған сақтау тіркелгісіндегі деректер үшін Private Link сол шектелген желіге қосылуды қосады.

> [!IMPORTANT]
> Жеке сілтеме қосылымын орнату үшін ең аз рөл талабы:
>
> - Тұтынушы түсініктері: Әкімші
> - Azure кірістірілген рөлі: [Сақтау есептік жазбасының салымшысы](/azure/role-based-access-control/built-in-roles#storage-account-contributor)
> - Теңшелетін Azure рөліне рұқсаттар: [Microsoft.Storage/storageAccounts/read және Microsoft.Storage/storageAccounts/PrivateEndpointConnectionsApproval/action](/azure/role-based-access-control/resource-provider-operations#microsoftstorage)
>

Customer Insights жүйесінде жеке сілтемені орнату екі қадамды процесс. Біріншіден, сіз жеке сілтеме жасауды бастауға кірісесіз **Админ** > **Қауіпсіздік** > **Жеке сілтемелер** Customer Insights ішінде. The **Жеке сілтеме қосыңыз** панель көру рұқсаттары бар жалға берушінің сақтау тіркелгілерінің тізімін береді. Сақтау тіркелгісін таңдап, Жеке сілтеме жасауға келісім беріңіз.

Әрі қарай, Data Lake Storage тіркелгі жағындағы Жеке сілтемені бекіту керек. Жаңа Жеке сілтемені бекіту үшін экранда көрсетілген сілтемені ашыңыз.

## <a name="key-vault-tab"></a>Key Vault қойындысы

The **Кілттер қоймасы** қойындысы өзіңізді байланыстыруға және басқаруға мүмкіндік береді [Azure кілттер қоймасы](/azure/key-vault/general/basic-concepts) қоршаған ортаға.
Арнайы кілт қоймасын ұйымның сәйкестік шекарасында құпияларды орнатуға және пайдалануға болады. Customer Insights бағдарламасы Azure Key Vault ішіндегі құпияларды пайдалана алады [қосылымдарды орнату](connections.md) үшінші тарап жүйелеріне.

Қосымша ақпарат алу үшін [Жеке Azure Key Vault қызметін жүзеге асыру](use-azure-key-vault.md) бөлімін қараңыз.

## <a name="securely-access-customer-data-with-customer-lockbox-preview"></a>Customer Lockbox көмегімен тұтынушы деректеріне қауіпсіз қол жеткізіңіз (Алдын ала қарау)

Customer Insights пайдаланады Power Platform Customer Lockbox мүмкіндігі. Customer Lockbox деректерге қол жеткізу сұрауларын қарау және мақұлдау (немесе қабылдамау) үшін интерфейсті қамтамасыз етеді. Бұл сұраулар қолдау ісін шешу үшін тұтынушы деректеріне деректерге қол жеткізу қажет болғанда орын алады. Бұл мүмкіндікті пайдалану үшін Customer Insights қолданбасында бұрыннан бар қосылым болуы керек Microsoft Dataverse сіздің жалға алушыңыздағы орта.

Customer Lockbox туралы қосымша ақпаратты мына жерден қараңыз [түйіндеме](/power-platform/admin/about-lockbox#summary) бойынша Power Platform Customer Lockbox. Мақалада сонымен қатар сипатталған [жұмыс процесі](/power-platform/admin/about-lockbox#workflow) және талап етілетін [орнату](/power-platform/admin/about-lockbox#enable-the-lockbox-policy) Customer Lockbox қосу үшін.

> [!IMPORTANT]
> үшін ғаламдық әкімшілер Power Platform немесе Power Platform әкімшілер Customer Insights үшін берілген Customer Lockbox сұрауларын мақұлдай алады.

[!INCLUDE [footer-include](includes/footer-banner.md)]
