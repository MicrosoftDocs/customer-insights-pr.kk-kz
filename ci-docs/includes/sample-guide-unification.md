---
ms.openlocfilehash: 1d79987893986148421c316193b27d268cfe0a0b
ms.sourcegitcommit: 4ae316c856b8de0f08a4605f73e75a8c2cf51c4e
ms.translationtype: MT
ms.contentlocale: kk-KZ
ms.lasthandoff: 05/13/2022
ms.locfileid: "8755551"
---
Деректерді қабылдағаннан кейін бірыңғай тұтынушы профилін жасау үшін деректерді біріктіру процесін бастаңыз. Қосымша ақпарат алу үшін [Деректерді біріктіру](../data-unification.md) бөлімін қараңыз.

### <a name="select-source-fields"></a>Бастапқы өрістерді таңдаңыз

1. Деректерді қабылдағаннан кейін, eCommerce және адалдық деректеріндегі контактілерді жалпы деректер түрлерімен салыстырыңыз. Бару **Деректер** > **Біріктіру**.

1. Тұтынушы профилін ұсынатын нысандарды таңдаңыз – **eCommerce контактілері** және **адалдық тұтынушылары**.

   ![ecommerce және адалдық деректер көздерін біріктіру.](../media/unify-ecommerce-loyalty.png)

1. **eCommerce контактілері** үшін негізгі кілт ретінде **Контакт идентификаторы** кілтін, ал **адалдық тұтынушылары** үшін негізгі кілт ретінде **Адалдық идентификаторы** кілтін таңдаңыз.

1. **Келесі** пәрменін таңдаңыз. Қайталанатын жазбаларды өткізіп жіберіп, таңдаңыз **Келесі**.

### <a name="match-conditions"></a>Сәйкестік шарттары

1. Таңдау **eCommerceContacts: eCommerce** негізгі нысан ретінде және барлық жазбаларды қамтиды.

1. Таңдау **loyCustomers: LoyaltyScheme** және барлық жазбаларды қамтиды.

1. Ереже қосыңыз:
   - таңдаңыз **Толық аты** eCommerceContacts және loyCustomers үшін.
   - таңдаңыз **Түр (телефон, аты, мекенжайы, ...)** үшін **Қалыптастыру**.
   - **Дәлдік деңгейі** мәнін орнатыңыз: **Негізгі** және **Мән** : **Жоғары**.
   - Енгізіңіз **Аты-жөні, электрондық поштасы** аты үшін.

1. Электрондық пошта мекенжайына екінші шарт қосыңыз:
   - таңдаңыз **Электрондық пошта** eCommerceContacts және loyCustomers үшін.
   - Нормалдау өрісін бос қалдырыңыз.
   - **Дәлдік деңгейі** мәнін орнатыңыз: **Негізгі** және **Мән** : **Жоғары**.

   ![Атауы мен электрондық поштасы үшін сәйкестік ережесін біріктіру.](../media/unify-match-rule.png)

1. **Дайын** опциясын таңдаңыз.

1. **Келесі** пәрменін таңдаңыз.

### <a name="unify-fields"></a>Өрістерді біріктіру

1. атын өзгерту **ContactId** үшін **loyCustomers** субъектіге **БайланысIdLOYALTY** оны басқа қабылданған идентификаторлардан ажырату үшін.

1. таңдаңыз **Келесі** қарап шығу үшін, содан кейін таңдаңыз **Тұтынушы профильдерін жасаңыз**.