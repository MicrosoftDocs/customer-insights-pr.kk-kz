---
title: Dynamics 365 Marketing жүйесінде біріктірілген профильдерді пайдаланыңыз
description: Бірыңғай профильдер мен сегменттерді Dynamics 365 Marketing бағдарламасымен біріктіруді үйреніңіз.
ms.date: 04/20/2022
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 45c59465771e4ad25ed36d5da1568e67b94cf994
ms.sourcegitcommit: cf74b8c20d88eb96e1ac86e18cd44fe27aad5ab9
ms.translationtype: MT
ms.contentlocale: kk-KZ
ms.lasthandoff: 04/28/2022
ms.locfileid: "8653818"
---
# <a name="work-with-unified-customer-profiles-in-dynamics-365-marketing"></a>Dynamics 365 Marketing жүйесінде бірыңғай тұтынушы профильдерімен жұмыс жасаңыз

[Dynamics 365 Marketing](/dynamics365/marketing/overview) қарым-қатынастарды нығайту және адалдыққа ие болу үшін барлық байланыс нүктелері бойынша жеке саяхаттарды ұйымдастыруға мүмкіндік беретін тұтынушылар тәжірибесін арттырады. Dynamics 365 Marketing қолданбасы Dynamics 365 Sales жүйесімен үздіксіз жұмыс істейді,Dynamics 365 Customer Insights,Microsoft Teams, және басқа өнімдер және деректер мен AI қуатын пайдаланып жылдамырақ және жақсырақ шешім қабылдауға мүмкіндік береді.

Customer Insights деректерін маркетингпен байланыстыру арқылы сіз:

- Бірыңғай тұтынушы профильдері мен сегменттеріне мақсат қойыңыз. Бұл тұтынушы деректерінің орналасқан жеріне қарамастан әрбір тұтынушыны тартуға мүмкіндік береді.
- Электрондық хаттардағы, SMS пен push хабарландыруларындағы динамикалық мазмұнды (мысалы, жекелендірілген белгілер) адалдық күйі, жазылымды жаңарту күні, бас ұйым немесе біртұтас Customer Insights профилінде түсірген кез келген басқа өлшем сияқты өлшемдерге негіздеңіз.
- Маркетингтен деректерді Customer Insights ішіне жүктеп, оны басқа көздерден тұтынушы деректерімен біріктіріңіз.
- Customer Insights деректерін тазалау, байыту және анық емес сәйкестік құралдарын қолданыңыз.


## <a name="use-rich-customer-profiles-in-real-time-marketing"></a>Нақты уақыттағы маркетингте бай тұтынушы профильдерін пайдаланыңыз

Нақты уақыттағы маркетинг құруға мүмкіндік береді [теңшелетін триггерлер](/dynamics365/marketing/real-time-marketing-custom-triggers) кез келген тұтынушы әрекетіне негізделген тұтынушы саяхатын бастайды. Деректеріңіз неғұрлым жекелендірілген болса, сапарларыңыз соғұрлым өзекті және жекелендірілген болады. Бұл маркетинг пен Customer Insights біріктіруді соншалықты күшті етеді. Сен істе аласың [деректерді біріктіру](data-unification.md) кез келген көзден, содан кейін оны гипер-жекелендірілген тұтынушы саяхатын жағу үшін пайдаланыңыз.

Көбірек білу үшін: [Нақты уақыттағы маркетингте Customer Insights профильдері мен сегменттерін пайдаланыңыз](/dynamics365/marketing/real-time-marketing-ci-profile)

## <a name="use-unified-segments-with-outbound-customer-journeys"></a>Клиенттердің шығыс сапарлары бар біріктірілген сегменттерді пайдаланыңыз

Customer Insights көптеген көздерден алынған деректерді нақтылауға және оларды біріктірілген тұтынушы сегменттеріне біріктіруге мүмкіндік береді. Авторы [Customer Insights шығыс маркетингімен байланыстыру](export-dynamics365-marketing.md), бұл сегменттер автоматты түрде пайда болады *және* тұтынушымен өзара қатынас топтамасы дизайнерінде автоматты түрде жаңартыңыз.

Көбірек білу үшін: [сегменттерін пайдаланыңыз Dynamics 365 Customer Insights Dynamics 365 Marketing бағдарламасымен](/dynamics365/marketing/customer-insights-segments)

## <a name="pull-data-from-your-own-azure-data-lake-storage"></a>Деректерді өзіңізден алыңыз Azure Data Lake Storage

Customer Insights деректерін маркетингпен бірге пайдаланғыңыз келсе, сіз бұлтты сақтаумен шектелмейсіз. Егер сізде бұрыннан бар болса Azure Data Lake Storage орнатқанда, Customer Insights бағдарламасымен қосыла аласыз, содан кейін деректерді бұлтқа негізделген орнатудағыдай Маркетинг қолданбасымен бөлісе аласыз.

Көбірек білу үшін: [Деректерді ортақ пайдалануды қосыңыз Dataverse өзіңнен Azure Data Lake Storage](manage-environments.md#enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview)