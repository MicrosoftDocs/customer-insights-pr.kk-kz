---
title: Деректерді бірыңғайландыру
description: Қабылданған деректерді біріктіру туралы ақпарат.
ms.date: 04/16/2020
ms.reviewer: adkuppa
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 24321e9e11f9fd4e800526673726e5146ed33674
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406214"
---
# <a name="data-unification"></a><span data-ttu-id="2e5c8-103">Деректерді бірыңғайландыру</span><span class="sxs-lookup"><span data-stu-id="2e5c8-103">Data unification</span></span>

<span data-ttu-id="2e5c8-104">[Деректер көздерін орнатқаннан](data-sources.md) кейін, деректерді біріктіруге болады.</span><span class="sxs-lookup"><span data-stu-id="2e5c8-104">After [setting up the data sources](data-sources.md), you can unify the data.</span></span> <span data-ttu-id="2e5c8-105">Деректерді біріктірудің үш қадамы бар: **Салыстыру**, **Сәйкестендіру** және **Біріктіру**.</span><span class="sxs-lookup"><span data-stu-id="2e5c8-105">Data unification includes three steps: **Map**, **Match**, and **Merge**.</span></span>

<span data-ttu-id="2e5c8-106">Деректерді біріктіру процесі үйлесімсіз деректер көздерін тұтынушылардың біріккен көрінісін қамтамасыз ететін жалғыз негізгі деректер жинағына біріктіруге мүмкіндік береді.</span><span class="sxs-lookup"><span data-stu-id="2e5c8-106">The data unification process lets you unify once-disparate data sources into a single master dataset that provides a unified view of your customers.</span></span> <span data-ttu-id="2e5c8-107">Біріктіру кезеңдері міндетті және мына ретпен орындалады:</span><span class="sxs-lookup"><span data-stu-id="2e5c8-107">Unification stages are mandatory, and performed in the following order:</span></span>

1. [<span data-ttu-id="2e5c8-108">Салыстыру</span><span class="sxs-lookup"><span data-stu-id="2e5c8-108">Map</span></span>](map-entities.md)
2. [<span data-ttu-id="2e5c8-109">Match</span><span class="sxs-lookup"><span data-stu-id="2e5c8-109">Match</span></span>](match-entities.md)
3. [<span data-ttu-id="2e5c8-110">Біріктіру</span><span class="sxs-lookup"><span data-stu-id="2e5c8-110">Merge</span></span>](merge-entities.md)

<span data-ttu-id="2e5c8-111">Деректерді біріктіріп болған соң мына әрекеттерді орындай аласыз:</span><span class="sxs-lookup"><span data-stu-id="2e5c8-111">After completing the data unification, you can optionally</span></span>

- <span data-ttu-id="2e5c8-112">шоғырланған сегменттерді жасау үшін [нысандар арасында қарым-қатынастарды орнату](relationships.md)</span><span class="sxs-lookup"><span data-stu-id="2e5c8-112">[set up relationships between entities](relationships.md) to create sophisticated segments</span></span>
- <span data-ttu-id="2e5c8-113">тұтынушылар туралы түсініктердің кеңірек ауқымын алу үшін [деректеріңізді арттыру](enrichment-hub.md)</span><span class="sxs-lookup"><span data-stu-id="2e5c8-113">[enrich your data](enrichment-hub.md) to get a wider range of insights about your customers</span></span>
- <span data-ttu-id="2e5c8-114">қабылданған төлсипаттардың кейбіріндегі [әрекеттерді анықтау](activities.md)</span><span class="sxs-lookup"><span data-stu-id="2e5c8-114">[define activities](activities.md) from some of the ingested attributes</span></span>
