---
title: Құпияларды басқару үшін жеке Azure Key Vault қызметін пайдалану
description: Жеке Azure Key Vault қызметін пайдалану үшін Customer Insights бағдарламасын конфигурациялау жолы.
ms.date: 10/06/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: brndkfr
ms.author: bkief
manager: shellyha
ms.openlocfilehash: 6f521dfce3e0922238d16beee3be8e1bbcfc63a5
ms.sourcegitcommit: 693458e13e4b4d94b6205093559912f6a4dc4a1c
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 10/06/2021
ms.locfileid: "7606096"
---
# <a name="bring-your-own-azure-key-vault-preview"></a>Жеке Azure Key Vault қызметін пайдалану (алдын ала қарау нұсқасы)

Арнайы [Azure Key Vault](/azure/key-vault/general/basic-concepts) қызметін аудитория түсініктері ортасымен байланыстыру ұйымдарға сәйкестік талаптарын орындауға көмектеседі.
Арнайы кілт қоймасын ұйымның сәйкестік шекарасында құпияларды орнатуға және пайдалануға болады. Аудитория түсініктері Azure Key Vault қызметіндегі құпияларды үшінші тарап жүйелерімен [байланыстар орнату](connections.md) үшін пайдалана алады.

## <a name="link-the-key-vault-to-the-audience-insights-environment"></a>Кілт қоймасын аудитория түсінігінің ортасымен байланыстыру

### <a name="prerequisites"></a>Алғышарттар

Аудитория түсінігіндегі кілт қоймасын конфигурациялау үшін келесі алғышарттар орындалуы керек:

- Сізде белсенді Azure жазылымы болуы қажет.

- Сізде аудитория туралы түсініктерде [Әкімші](permissions.md#administrator) рөлі бар. [Аудитория түсініктеріндегі пайдаланушы рұқсаттары](permissions.md#assign-roles-and-permissions) туралы қосымша ақпарат.

- Сізде кілт қоймасында немесе кілт қоймасы тиесілі ресурстар тобын [Салымшы](/azure/role-based-access-control/built-in-roles#contributor) және [Пайдаланушы қатынасуы әкімшісі](/azure/role-based-access-control/built-in-roles#user-access-administrator) рөлдері бар. Қосымша ақпарат алу үшін [Azure порталын пайдалану арқылы Azure рөлін тағайындауды қосу немесе жою](/azure/role-based-access-control/role-assignments-portal) бөліміне өтіңіз. Егер сізде кілттер қоймасында пайдаланушы қатынасуының әкімшісі рөлі болмаса, Dynamics 365 Customer Insights бағдарламасына арналған Azure субъект-қызметі үшін рөлге негізделген қатынасуды басқару рұқсаттарын орнату қажет. Байланыстырылуы керек кілт қоймасына арналған [Azure субъект-қызметін](connect-service-principal.md) пайдалану үшін қадамдарды орындаңыз.

- Кілт қоймасында Key Vault брандмауэрі **өшірулі** болуы керек.

- Кілт қоймасы аудитория түсініктері ортасы орналасқан бір [Azure орнында](https://azure.microsoft.com/global-infrastructure/geographies/#overview) орналасқан. Аудитория түсініктерінде орта аймағы **Әкімші** > **Жүйе** > **Ақпарат** > **Аймақ** тармағында тізімделген.

### <a name="link-a-key-vault-to-the-environment"></a>Кілт қоймасын ортамен байланыстыру

1. **Әкімші** > **Жүйе** тармағына өтіңіз және содан кейін **Қауіпсіздік** қойыншасын таңдаңыз.
1. **Кілт қоймасы** тақтасында **Орнату** түймешігін таңдаңыз.
1. **Жазылым** түймешігін таңдаңыз.
1. **Key Vault** ашылмалы тізімінен кілт қоймасын таңдаңыз. Егер тым көп кілт қоймасы пайда болса, іздеу нәтижелерін шектеу үшін ресурстар тобын таңдаңыз.
1. **Деректердің құпиялылығы мен сәйкестігі** мәлімдемесін қабылдаңыз.
1. **Сақтау** опциясын таңдаңыз.

:::image type="content" source="media/set-up-azure-key-vault.png" alt-text="Аудитория түсінігінде байланысқан кілт қоймасын орнату қадамдары.":::

**Кілт қоймасы** тақтасы енді байланыстырылған кілт қоймасының атауын, ресурстар тобын және жазылымды көрсетеді. Ол қосылымды орнатуда пайдалануға дайын.
Аудитория түсінігіне кілт қоймасында қандай рұқсаттар берілетіні туралы қосымша ақпарат алу үшін осы мақалада кейін кездесетін [Аудитория түсінігіне кілт қоймасында берілген рұқсаттар](#permissions-granted-on-the-key-vault-to-audience-insights) бөлімін қараңыз.

## <a name="use-the-key-vault-in-the-connection-setup"></a>Қосылым орнату кезінде кілт қоймасын пайдалану

Үшінші тарап жүйелеріне [байланыстар орнату](connections.md) кезінде байланыстырылған Key Vault құпияларын қосылымдарды конфигурациялау үшін пайдалануға болады.

1. **Әкімші** > **Қосылымдар** тармағына өтіңіз.
1. **Қосылым қосу** опциясын таңдаңыз.
1. Қолдау көрсетілетін қосылым түрлері үшін егер сіз кілт қоймасын байланыстырсаңыз **Key Vault қызметін пайдалану** ауыстырып‑қосқышы қолжетімді болады.
1. Құпияны қолмен енгізудің орнына, кілт қоймасындағы құпия мәнді көрсететін құпия атауды таңдауға болады.

:::image type="content" source="media/use-key-vault-secret.png" alt-text="Key Vault құпиясын қолданатын SFTP қосылымы бар қосылым тақтасы.":::

## <a name="supported-connection-types"></a>Қолдау көрсетілетін қосылым түрлері

Келесі [экспорттау](export-destinations.md) қосылымдарына қолдау көрсетіледі:

* [ActiveCampaign](export-active-campaign.md)
* [Autopilot](export-autopilot.md)
* [DotDigital](export-dotdigital.md)
* [Google Ads](export-google-ads.md)
* [Klaviyo](export-klaviyo.md)
* [LiveRamp](export-liveramp.md)
* [Marketo](export-marketo.md)
* [Omnisend](export-omnisend.md)
* [Salesforce Marketing Cloud](export-salesforce.md)
* [Sendgrid](export-sendgrid.md)
* [Sendinblue](export-sendinblue.md)
* [SFTP](export-sftp.md)

## <a name="permissions-granted-on-the-key-vault-to-audience-insights"></a>Кілт қоймасында аудитория түсініктеріне берілетін рұқсаттар

[Key Vault қатынасу саясаты](/azure/key-vault/general/assign-access-policy?tabs=azure-portal) немесе [Azure рөлге негізделген қатынасуды басқару](/azure/key-vault/general/rbac-guide?tabs=azure-cli) опциясы қосулы болса, байланыстырылған кілт қоймасында аудитория түсініктеріне келесі рұқсаттар беріледі.

### <a name="key-vault-access-policy"></a>Key Vault қатынасу саясаты

| Түр        | Рұқсаттар          |
| ----------- | -------------------- |
| Перне         | [Кілттерді алу](/rest/api/keyvault/get-keys), [Кілтті алу](/rest/api/keyvault/get-key)                                 |
| Құпия      | [Құпияларды алу](/rest/api/keyvault/get-secrets), [Құпияны алу](/rest/api/keyvault/get-secret)                     |
| Куәлік | [Сертификаттарды алу](/rest/api/keyvault/get-certificates), [Сертификат алу](/rest/api/keyvault/get-certificate) |

Алдыңғы мәндер орындау кезінде тізімдеу және оқу үшін минимум болып табылады.

### <a name="azure-role-based-access-control"></a>Azure рөлге негізделген қатынасуды басқару элементі

Аудитория түсініктеріне Key Vault оқушысы және Key Vault құпиялалары пайдаланушы рөлдері қосылады. Бұл рөлдер туралы толық ақпарат алу үшін [Key Vault деректер жазықтығы операцияларына арналған Azure кіріктірілген рөлдері](/azure/key-vault/general/rbac-guide?tabs=azure-cli) бөлімін қараңыз.

## <a name="recommendations"></a>Ұсыныстар

- Аудитория түсініктері үшін қажет құпияларды ғана қамтитын жеке немесе арнайы кілт қоймасын пайдаланыңыз. Неліктен [бөлек кілт қоймалары ұсынылғандығы](/azure/key-vault/general/best-practices#why-we-recommend-separate-key-vaults) туралы ақпарат.

- Қатынасуды басқару, резервтік көшірме, тексеру және қалпына келтіру опциялары үшін [Key Vault қызметін қолданудың үздік әдістерін](/azure/key-vault/general/best-practices#turn-on-logging) орындаңыз.

## <a name="frequently-asked-questions"></a>Жиі қойылатын сұрақтар

### <a name="can-audience-insights-write-secrets-or-overwrite-secrets-into-the-key-vault"></a>Аудитория түсініктері кілт қоймасына құпия жазып немесе құпияны қайта жаза алады ма?

Жоқ. Аудитория түсініктеріне осы мақалада бұрын [берілген рұқсаттар](#permissions-granted-on-the-key-vault-to-audience-insights) бөлімінде көрсетілген оқу және тізімдеу рұқсаттары ғана беріледі. Жүйе кілт қоймасында құпияларды қоса алмайды, жоя алмайды немесе қайта жаза алмайды. Сондықтан қосылым Key Vault қызметін қолданғанда тіркелгі деректерін енгізу мүмкін емес болады.

### <a name="can-i-change-a-connection-from-using-key-vault-secrets-to-default-authentication"></a>Қосылымды Key Vault құпияларын пайдаланудан әдепкі аутентификацияға өзгертуге бола ма?

Жоқ. Байланыстырылған кілт қоймасының құпиясын пайдалану арқылы оны конфигурациялағаннан кейін әдепкі қосылымға оралу мүмкін емес. Бөлек қосылым жасаңыз және енді қажет болмаса ескісін жойыңыз.

### <a name="how-can-i-revoke-access-to-a-key-vault-for-audience-insights"></a>Аудитория түсініктері үшін кілт қоймасына қатынасуды қалай жоюға болады?

[Key Vault қатынасу саясаты](/azure/key-vault/general/assign-access-policy?tabs=azure-portal) немесе [Azure рөлге негізделген қатынасуды басқару](/azure/key-vault/general/rbac-guide?tabs=azure-cli) опциясының қосулы болуына байланысты, `Dynamics 365 AI for Customer Insights` атты `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` қызмет‑субъектісі үшін рұқсаттарды жою керек. Кілт қоймасын қолданатын барлық қосылымдар жұмысын тоқтатады.

### <a name="a-secret-thats-used-in-a-connection-got-removed-from-the-key-vault-what-can-i-do"></a>Қосылымда пайдаланылған құпия кілт қоймасынан жойылды. Не істеуге болады?

Кілт қоймасындағы конфигурацияланған құпия енді қолжетімсіз болғанда, аудитория түсінігінде хабарландыру пайда болады. Кездейсоқ жойылған жағдайда құпияны қалпына келтіру үшін кілт қоймасында [жеңіл жою](/azure/key-vault/general/soft-delete-overview) опциясын қосыңыз.

### <a name="a-connection-doesnt-work-but-my-secret-is-in-the-key-vault-what-might-be-the-cause"></a>Қосылым жұмыс істемейді, бірақ менің құпиям кілт қоймасында. Не себеп болуы мүмкін?

Аудитория түсініктері кілт қоймасына қатынаса алмаған кезде хабарландыру пайда болады. Оның себебі келесі болуы мүмкін:

- Аудитория түсініктері қызмет‑субъектісінің рұқсаттары жойылды. Оларды қолмен қалпына келтіру қажет.

- Кілт қоймасындағы брандмауэр қосылған. Кілт қоймасын аудитория түсінігі үшін қайтадан қолжетімді ету үшін брандмауэрді өшіру керек.
