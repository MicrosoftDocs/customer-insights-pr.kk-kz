---
title: Қауіпсіздік параметрлерін конфигурациялаңыз
description: Қауіпсіздік параметрлері туралы мына жерден біліңіз Dynamics 365 Customer Insights.
ms.date: 08/02/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: ea21163d7dd05370de28ca8340ae9583846adb26
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: MT
ms.contentlocale: kk-KZ
ms.lasthandoff: 08/10/2022
ms.locfileid: "9246069"
---
# <a name="configure-security-settings"></a>Қауіпсіздік параметрлерін конфигурациялаңыз

API кілттерін басқарыңыз, тұтынушы деректеріне қол жеткізіңіз және Azure Private Link орнатыңыз.

## <a name="manage-api-keys"></a>API кілттерін басқару

пайдалану үшін пернелерді қараңыз және басқарыңыз [Customer Insights API интерфейстері](apis.md) ортаңыздағы деректермен.

1. Бару **Жүйе** > **Қауіпсіздік** және таңдаңыз **API интерфейстері** қойындысы.

1. Ортаға API қатынасы орнатылмаған болса, таңдаңыз **Қосу**. Немесе ортаға API қатынасын блоктау үшін таңдаңыз **Өшіру** және растаңыз.

1. Негізгі және қосымша API кілттерін басқару:

   1. Негізгі немесе қосымша API кілтін көрсету үшін таңдаңыз **Көрсету** символы.

   1. Негізгі немесе қосымша API кілтін көшіру үшін таңдаңыз **Көшіру** символы.

   1. Жаңа негізгі немесе қосымша API кілттерін жасау үшін таңдаңыз **Бастапқы қалпына келтіру** немесе **Екінші ретті қалпына келтіру**.

## <a name="securely-access-customer-data-with-customer-lockbox-preview"></a>Customer Lockbox көмегімен тұтынушы деректеріне қауіпсіз қол жеткізіңіз (Алдын ала қарау)

Customer Insights пайдаланады Power Platform Customer Lockbox мүмкіндігі. Customer Lockbox деректерге қол жеткізу сұрауларын қарау және мақұлдау (немесе қабылдамау) үшін интерфейсті қамтамасыз етеді. Бұл сұраулар қолдау ісін шешу үшін тұтынушы деректеріне деректерге қол жеткізу қажет болғанда орын алады. Бұл мүмкіндікті пайдалану үшін Customer Insights қолданбасында бұрыннан бар қосылым болуы керек Microsoft Dataverse сіздің жалға алушыңыздағы орта.

Customer Lockbox туралы қосымша ақпаратты мына жерден қараңыз [түйіндеме](/power-platform/admin/about-lockbox#summary) ның Power Platform Customer Lockbox. Мақалада сонымен қатар сипатталған [жұмыс процесі](/power-platform/admin/about-lockbox#workflow) және талап етілетін [орнату](/power-platform/admin/about-lockbox#enable-the-lockbox-policy) Customer Lockbox қосу үшін.

> [!IMPORTANT]
> үшін ғаламдық әкімшілер Power Platform немесе Power Platform әкімшілер Customer Insights үшін берілген Customer Lockbox сұрауларын мақұлдай алады.

## <a name="set-up-an-azure-private-link"></a>Azure жеке сілтемесін орнатыңыз

[Azure жеке сілтемесі](/azure/private-link/private-link-overview) Customer Insights сіздің компьютеріңізге қосылсын Azure Data Lake Storage виртуалды желіңіздегі жеке соңғы нүкте арқылы тіркелгіні жасаңыз. Жалпыға ортақ интернетке қосылмаған сақтау тіркелгісіндегі деректер үшін Private Link сол шектелген желіге қосылуды қосады.

> [!IMPORTANT]
> Жеке сілтеме қосылымын орнату үшін ең аз рөл талабы:
>
> - Тұтынушы түсініктері: Әкімші
> - Azure кірістірілген рөлі: [Сақтау есептік жазбасының салымшысы](/azure/role-based-access-control/built-in-roles#storage-account-contributor)
> - Теңшелетін Azure рөліне рұқсаттар: [Microsoft.Storage/storageAccounts/read және Microsoft.Storage/storageAccounts/PrivateEndpointConnectionsApproval/action](/azure/role-based-access-control/resource-provider-operations#microsoftstorage)

1. Customer Insights бөліміне өтіңіз **Админ** > **Қауіпсіздік** және таңдаңыз **Жеке сілтемелер** қойындысы.

1. таңдаңыз **Жеке сілтеме қосыңыз**.

   The **Жеке сілтеме қосыңыз** панельде көру рұқсаттары бар жалға берушінің сақтау тіркелгілері тізімі берілген.

1. Жазылымды, ресурс тобын және сақтау тіркелгісін таңдаңыз.

1. шолу [деректердің құпиялылығы және сәйкестігі](connections.md#data-privacy-and-compliance) және таңдаңыз **Мен келісемін**.

1. **Сақтау** пәрменін таңдаңыз.

1. Data Lake Storage тіркелгісіне өтіп, экранда көрсетілген сілтемені ашыңыз.

1. Жеке сілтемені мақұлдаңыз.


[!INCLUDE [footer-include](includes/footer-banner.md)]
