---
title: Құпияларды басқару үшін жеке Azure Key Vault қызметін пайдалану
description: Жеке Azure Key Vault қызметін пайдалану үшін Customer Insights бағдарламасын конфигурациялау жолы.
ms.date: 10/06/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: brndkfr
ms.author: bkief
manager: shellyha
searchScope:
- ci-system-security
- customerInsights
ms.openlocfilehash: d4f2d5ebc828053c40e22065f4915c4d0f84153f
ms.sourcegitcommit: 6ec4626a185892dfb781d3c7af4384f9c13f3723
ms.translationtype: MT
ms.contentlocale: kk-KZ
ms.lasthandoff: 05/17/2022
ms.locfileid: "8763586"
---
# <a name="bring-your-own-azure-key-vault-preview"></a>Жеке Azure Key Vault қызметін пайдалану (алдын ала қарау нұсқасы)

Арнайы байланыстыру [Azure кілттер қоймасы](/azure/key-vault/general/basic-concepts) Customer Insights ортасы ұйымдарға сәйкестік талаптарын орындауға көмектеседі.
Арнайы кілт қоймасын ұйымның сәйкестік шекарасында құпияларды орнатуға және пайдалануға болады. Customer Insights бағдарламасы Azure Key Vault ішіндегі құпияларды пайдалана алады [қосылымдарды орнату](connections.md) үшінші тарап жүйелеріне.

## <a name="link-the-key-vault-to-the-customer-insights-environment"></a>Кілттер қоймасын Customer Insights ортасымен байланыстырыңыз

### <a name="prerequisites"></a>Алғышарттар

Customer Insights жүйесінде кілт қоймасын конфигурациялау үшін келесі алғышарттар орындалуы керек:

- Сізде белсенді Azure жазылымы болуы қажет.

- Сізде бар [Әкімші](permissions.md#admin) Customer Insights жүйесіндегі рөл. туралы көбірек біліңіз [Customer Insights ішіндегі пайдаланушы рұқсаттары](permissions.md#assign-roles-and-permissions).

- Сізде кілт қоймасында немесе кілт қоймасы тиесілі ресурстар тобын [Салымшы](/azure/role-based-access-control/built-in-roles#contributor) және [Пайдаланушы қатынасуы әкімшісі](/azure/role-based-access-control/built-in-roles#user-access-administrator) рөлдері бар. Қосымша ақпарат алу үшін [Azure порталын пайдалану арқылы Azure рөлін тағайындауды қосу немесе жою](/azure/role-based-access-control/role-assignments-portal) бөліміне өтіңіз. Егер сізде кілттер қоймасында пайдаланушы қатынасуының әкімшісі рөлі болмаса, Dynamics 365 Customer Insights бағдарламасына арналған Azure субъект-қызметі үшін рөлге негізделген қатынасуды басқару рұқсаттарын орнату қажет. Байланыстырылуы керек кілт қоймасына арналған [Azure субъект-қызметін](connect-service-principal.md) пайдалану үшін қадамдарды орындаңыз.

- Кілт қоймасында Key Vault брандмауэрі **өшірулі** болуы керек.

- Кілттер қоймасы бірдей [Azure орны](https://azure.microsoft.com/global-infrastructure/geographies/#overview) Customer Insights ортасы ретінде. Customer Insights ішіндегі ортаның аймағы төменде берілген **Админ** > **Жүйе** > **туралы** > **Аймақ**.

### <a name="link-a-key-vault-to-the-environment"></a>Кілт қоймасын ортамен байланыстыру

1. Бару **Админ** > **Қауіпсіздік**, содан кейін белгішесін таңдаңыз **Кілттер қоймасы** қойындысы.
1. **Кілт қоймасы** тақтасында **Орнату** түймешігін таңдаңыз.
1. **Жазылым** түймешігін таңдаңыз.
1. **Key Vault** ашылмалы тізімінен кілт қоймасын таңдаңыз. Егер тым көп кілт қоймасы пайда болса, іздеу нәтижелерін шектеу үшін ресурстар тобын таңдаңыз.
1. **Деректердің құпиялылығы мен сәйкестігі** мәлімдемесін қабылдаңыз.
1. **Сақтау** пәрменін таңдаңыз.

:::image type="content" source="media/set-up-azure-key-vault.png" alt-text="Customer Insights жүйесінде байланыстырылған кілт қоймасын орнату қадамдары.":::

**Кілт қоймасы** тақтасы енді байланыстырылған кілт қоймасының атауын, ресурстар тобын және жазылымды көрсетеді. Ол қосылымды орнатуда пайдалануға дайын.
Кілт қоймасындағы қандай рұқсаттар Customer Insights бағдарламасына берілгені туралы мәліметтер алу үшін өтіңіз [Кілт қоймасында берілген рұқсаттар](#permissions-granted-on-the-key-vault), осы мақалада кейінірек.

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

## <a name="permissions-granted-on-the-key-vault"></a>Кілт қоймасында берілген рұқсаттар

Келесі рұқсаттар Customer Insights бағдарламасына байланыстырылған кілт қоймасында беріледі, егер бар болса [Key Vault қатынасу саясаты](/azure/key-vault/general/assign-access-policy?tabs=azure-portal) немесе [Azure рөлге негізделген қатынасты басқару](/azure/key-vault/general/rbac-guide?tabs=azure-cli) қосылған.

### <a name="key-vault-access-policy"></a>Key Vault қатынасу саясаты

| Түр        | Рұқсаттар          |
| ----------- | -------------------- |
| Перне         | [Кілттерді алу](/rest/api/keyvault/keys/get-keys/get-keys), [Кілтті алу](/rest/api/keyvault/keys/get-key/get-key)                                 |
| Құпия      | [Құпияларды алу](/rest/api/keyvault/secrets/get-secrets/get-secrets), [Құпияны алу](/rest/api/keyvault/secrets/get-secret/get-secret)                     |
| Куәлік | [Сертификаттарды алу](/rest/api/keyvault/certificates/get-certificates/get-certificates), [Сертификат алу](/rest/api/keyvault/certificates/get-certificate/get-certificate) |

Алдыңғы мәндер орындау кезінде тізімдеу және оқу үшін минимум болып табылады.

### <a name="azure-role-based-access-control"></a>Azure рөлге негізделген қатынасуды басқару элементі

Key Vault Reader және Key Vault құпиялары пайдаланушы рөлдері Customer Insights үшін қосылады. Бұл рөлдер туралы толық ақпарат алу үшін [Key Vault деректер жазықтығы операцияларына арналған Azure кіріктірілген рөлдері](/azure/key-vault/general/rbac-guide?tabs=azure-cli) бөлімін қараңыз.

## <a name="recommendations"></a>Ұсыныстар

- Customer Insights үшін қажетті құпияларды ғана қамтитын бөлек немесе арнайы кілт қоймасын пайдаланыңыз. Неліктен [бөлек кілт қоймалары ұсынылғандығы](/azure/key-vault/general/best-practices#why-we-recommend-separate-key-vaults) туралы ақпарат.

- Қатынасуды басқару, резервтік көшірме, тексеру және қалпына келтіру опциялары үшін [Key Vault қызметін қолданудың үздік әдістерін](/azure/key-vault/general/best-practices#turn-on-logging) орындаңыз.

## <a name="frequently-asked-questions"></a>Жиі қойылатын сұрақтар

### <a name="can-customer-insights-write-secrets-or-overwrite-secrets-into-the-key-vault"></a>Customer Insights құпияларды жаза алады немесе кілт қоймасына құпияларды қайта жаза алады ма?

Жоқ. Тек бөлімде көрсетілген оқу және тізім рұқсаттары [рұқсаттар берілді](#permissions-granted-on-the-key-vault) Осы мақаланың алдыңғы бөлімі Customer Insights үшін берілген. Жүйе кілт қоймасында құпияларды қоса алмайды, жоя алмайды немесе қайта жаза алмайды. Сондықтан қосылым Key Vault қызметін қолданғанда тіркелгі деректерін енгізу мүмкін емес болады.

### <a name="can-i-change-a-connection-from-using-key-vault-secrets-to-default-authentication"></a>Қосылымды Key Vault құпияларын пайдаланудан әдепкі аутентификацияға өзгертуге бола ма?

Жоқ. Байланыстырылған кілт қоймасының құпиясын пайдалану арқылы оны конфигурациялағаннан кейін әдепкі қосылымға оралу мүмкін емес. Бөлек қосылым жасаңыз және енді қажет болмаса ескісін жойыңыз.

### <a name="how-can-i-revoke-access-to-a-key-vault-for-customer-insights"></a>Customer Insights үшін негізгі қоймаға кіру рұқсатын қалай жоюға болады?

[Key Vault қатынасу саясаты](/azure/key-vault/general/assign-access-policy?tabs=azure-portal) немесе [Azure рөлге негізделген қатынасуды басқару](/azure/key-vault/general/rbac-guide?tabs=azure-cli) опциясының қосулы болуына байланысты, `Dynamics 365 AI for Customer Insights` атты `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` қызмет‑субъектісі үшін рұқсаттарды жою керек. Кілт қоймасын қолданатын барлық қосылымдар жұмысын тоқтатады.

### <a name="a-secret-thats-used-in-a-connection-got-removed-from-the-key-vault-what-can-i-do"></a>Қосылымда пайдаланылған құпия кілт қоймасынан жойылды. Не істеуге болады?

Кілттер қоймасынан конфигурацияланған құпияға енді қол жеткізу мүмкін болмаған кезде хабарландыру Customer Insights ішінде пайда болады. Кездейсоқ жойылған жағдайда құпияны қалпына келтіру үшін кілт қоймасында [жеңіл жою](/azure/key-vault/general/soft-delete-overview) опциясын қосыңыз.

### <a name="a-connection-doesnt-work-but-my-secret-is-in-the-key-vault-what-might-be-the-cause"></a>Қосылым жұмыс істемейді, бірақ менің құпиям кілт қоймасында. Не себеп болуы мүмкін?

Кілттер қоймасына қол жеткізе алмаған кезде хабарландыру Customer Insights ішінде пайда болады. Оның себебі келесі болуы мүмкін:

- Customer Insights қызметінің негізгі рұқсаттары жойылды. Оларды қолмен қалпына келтіру қажет.

- Кілт қоймасындағы брандмауэр қосылған. Кілт қоймасын Customer Insights үшін қайтадан қолжетімді ету үшін брандмауэр өшірілген болуы керек.
