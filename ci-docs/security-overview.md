---
title: Қауіпсіздік параметрлері Dynamics 365 Customer Insights
description: Қауіпсіздік параметрлері туралы мына жерден біліңіз Dynamics 365 Customer Insights.
ms.date: 04/28/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 5d73bacccadc9193d76d8dfafd0365dabc911e00
ms.sourcegitcommit: cf74b8c20d88eb96e1ac86e18cd44fe27aad5ab9
ms.translationtype: MT
ms.contentlocale: kk-KZ
ms.lasthandoff: 04/28/2022
ms.locfileid: "8653817"
---
# <a name="security-overview-page"></a>Қауіпсіздікті шолу беті

The **Қауіпсіздік** бетте пайдаланушы рұқсаттары мен жасауға көмектесетін мүмкіндіктерді конфигурациялауға арналған опциялар тізімі берілген Dynamics 365 Customer Insights қауіпсізірек. Бұл бетке тек әкімшілер кіре алады. 

Бару **Админ** > **Қауіпсіздік** параметрлерді конфигурациялау үшін.

The **Қауіпсіздік** бетте келесі қойындылар бар:
- [Пайдаланушылар](#users-tab)
- [API көрсеткіштері](#apis-tab)
- [Key Vault](#key-vault-tab)

## <a name="users-tab"></a>Пайдаланушылар қойындысы

Customer Insights қолданбасына әкімші қосқан ұйымыңыздағы пайдаланушылармен шектелген. The **Пайдаланушылар** қойындысы пайдаланушы қатынасын және олардың рұқсаттарын басқаруға мүмкіндік береді. Қосымша ақпаратты қараңыз [Пайдаланушы рұқсаттары](permissions.md).

## <a name="apis-tab"></a>API қойындысы

пайдалану үшін пернелерді қараңыз және басқарыңыз [Customer Insights API интерфейстері](apis.md) ортаңыздың деректерімен.

Жаңа негізгі және қосымша кілттерді таңдау арқылы жасауға болады **Бастапқы қалпына келтіру** немесе **Екінші ретті қалпына келтіру**. 

Қоршаған ортаға API қатынасын блоктау үшін таңдаңыз **Өшіру**. API интерфейстері өшірілген болса, таңдауға болады **Қосу** қайта рұқсат беру үшін.

## <a name="key-vault-tab"></a>Key Vault қойындысы

The **Кілттер қоймасы** қойындысы өзіңізді байланыстыруға және басқаруға мүмкіндік береді [Azure кілттер қоймасы](/azure/key-vault/general/basic-concepts) қоршаған ортаға.
Арнайы кілт қоймасын ұйымның сәйкестік шекарасында құпияларды орнатуға және пайдалануға болады. Customer Insights бағдарламасы Azure Key Vault ішіндегі құпияларды пайдалана алады [қосылымдарды орнату](connections.md) үшінші тарап жүйелеріне.

Қосымша ақпарат алу үшін [Жеке Azure Key Vault қызметін жүзеге асыру](use-azure-key-vault.md) бөлімін қараңыз.


[!INCLUDE [footer-include](includes/footer-banner.md)]
