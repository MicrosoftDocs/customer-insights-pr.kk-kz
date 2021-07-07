---
title: Болжам сценарийлеріне арналған ортақ тапсырмалар
description: Болжамдарды басқару, ақаулықтарды жою және нақтылау жолы туралы ақпарат.
ms.date: 05/17/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: dccb8dcca8f65f64973e46fed9d83034d58282e2
ms.sourcegitcommit: bcc47d15d4f0eacf008e4dbc09baac7f062b3ca8
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 06/29/2021
ms.locfileid: "6315885"
---
# <a name="manage-predictions"></a><span data-ttu-id="87213-103">Болжамдарды басқару</span><span class="sxs-lookup"><span data-stu-id="87213-103">Manage predictions</span></span>

<span data-ttu-id="87213-104">Бұл мақалада болжам сценарийлерінің көпшілігі бөлісетін кейбір тапсырмалар талқыланады.</span><span class="sxs-lookup"><span data-stu-id="87213-104">This article discusses some tasks that most prediction scenarios share.</span></span>

## <a name="troubleshoot-a-failed-prediction"></a><span data-ttu-id="87213-105">Сәтсіз аяқталған болжам ақаулықтарын жою</span><span class="sxs-lookup"><span data-stu-id="87213-105">Troubleshoot a failed prediction</span></span>

1. <span data-ttu-id="87213-106">**Сараптау** > **Болжамдар** тарауына өтіп, **Менің болжамдарым** қойындысын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="87213-106">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="87213-107">Қате туралы журналдарды көру үшін болжам жанындағы тік эллипстерді таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="87213-107">Select the vertical ellipses next to the prediction you want to view error logs for.</span></span>

1. <span data-ttu-id="87213-108">**Журналдар** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="87213-108">Select **Logs**.</span></span>

1. <span data-ttu-id="87213-109">Барлық қателерді қарап шығыңыз.</span><span class="sxs-lookup"><span data-stu-id="87213-109">Review all the errors.</span></span> <span data-ttu-id="87213-110">Орын алуы мүмкін бірнеше қате түрі бар әрі олар қатеге себеп болған шартты сипаттайды.</span><span class="sxs-lookup"><span data-stu-id="87213-110">There are several types of errors that can occur, and they describe what condition caused the error.</span></span> <span data-ttu-id="87213-111">Мысалы, Customer Insights бағдарламасына қосымша деректерді жүктеу арқылы дәлірек болжауға жеткілікті деректер болмау қатесі әдепкі жолмен шешіледі.</span><span class="sxs-lookup"><span data-stu-id="87213-111">For example, an error that there's not enough data to accurately predict is typically resolved by loading additional data into Customer Insights.</span></span>

## <a name="input-data-usability-report"></a><span data-ttu-id="87213-112">Кіріс деректердің пайдалану ыңғайлылығы туралы есеп</span><span class="sxs-lookup"><span data-stu-id="87213-112">Input data usability report</span></span>

<span data-ttu-id="87213-113">Кіріс деректерді пайдалану туралы есеп дайын болжамдар жасауы мүмкін қателер мен ескертулердің біріккен көрінісін ұсынады.</span><span class="sxs-lookup"><span data-stu-id="87213-113">The input data usability report provides a consolidated view of the errors and warnings that your out-of-box predictions may be generating.</span></span> <span data-ttu-id="87213-114">Сондай-ақ ол модель өнімділігін жақсарту бойынша ұсыныстар береді.</span><span class="sxs-lookup"><span data-stu-id="87213-114">It also gives recommendations how to improve the model performance.</span></span>

<span data-ttu-id="87213-115">Есеп модель оқыту процесін аяқтағаннан кейін қолжетімді болады.</span><span class="sxs-lookup"><span data-stu-id="87213-115">The report is available after a model has completed its training process.</span></span> <span data-ttu-id="87213-116">Ол сәтті аяқталғанына немесе аяқталмағанына қарамастан, әр модель үшін бөлек жасалады.</span><span class="sxs-lookup"><span data-stu-id="87213-116">It's created for each model separately, regardless if it completed successfully or not.</span></span>

### <a name="view-the-input-data-usability-report"></a><span data-ttu-id="87213-117">Кіріс деректерді пайдалану туралы есепті көру</span><span class="sxs-lookup"><span data-stu-id="87213-117">View the input data usability report</span></span>

<span data-ttu-id="87213-118">Дайын модель оқыту қадамын аяқтағаннан кейін, есепті қараңыз:</span><span class="sxs-lookup"><span data-stu-id="87213-118">After an out-of-box model has completed its training step, view the report:</span></span>
- <span data-ttu-id="87213-119">Модель атауының жанындағы көп нүктені таңдаңыз және **Кіріс деректерді пайдалану туралы есеп** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="87213-119">Select the ellipses next to the model name and choose **Input data usability report**.</span></span>
- <span data-ttu-id="87213-120">Модель күйін таңдау үшін бүйірлік тақтада **Кіріс деректерді пайдалану туралы есепті қарау** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="87213-120">Select the status of a model select **See Input data usability report** in the side pane.</span></span>
- <span data-ttu-id="87213-121">Тізімдегі модельдердің бірін таңдап, пәрмен жолағында **Кіріс деректерді пайдалану туралы есеп** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="87213-121">Selecting one of the models in the list and select **Input data usability report** in the command bar.</span></span>
- <span data-ttu-id="87213-122">Модель нәтижелері бетін ашыңыз және пәрмен жолағында **Кіріс деректерді пайдалану туралы есеп** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="87213-122">Open the model results page and select **Input data usability report** in the command bar.</span></span>

### <a name="information-in-the-input-data-usability-report"></a><span data-ttu-id="87213-123">Кіріс деректерді пайдалану туралы есептегі ақпарат</span><span class="sxs-lookup"><span data-stu-id="87213-123">Information in the input data usability report</span></span>

<span data-ttu-id="87213-124">Есептегі келесі бағандар модельге арналған деректерді жақсартуға арналған пайдалы ақпаратты қамтиды.</span><span class="sxs-lookup"><span data-stu-id="87213-124">The following columns in the report contain helpful information to improve the data for the model.</span></span>

:::image type="content" source="media/input-data-usability-report.png" alt-text="Қателері, ескертулері мен ұсыныстары бар кестені көрсететін кіріс деректерді пайдалану туралы есептің мысалы.":::

- <span data-ttu-id="87213-126">Атауы: қатенің, ескерту немесе ұсыныстың сипаттамалық атауы.</span><span class="sxs-lookup"><span data-stu-id="87213-126">Name: Descriptive name of the error, warning, or recommendation.</span></span>
- <span data-ttu-id="87213-127">Қадам: ақпарат сілтеме жасайтын модель кезең, оқыту немесе ұпай.</span><span class="sxs-lookup"><span data-stu-id="87213-127">Step: Model phase, train or score, the information refers to.</span></span>
- <span data-ttu-id="87213-128">Күйі: ақпараттың маңыздылығы (қате, ескерту, ұсыныс).</span><span class="sxs-lookup"><span data-stu-id="87213-128">State: Severity of the information (error, warning, recommendation).</span></span>
- <span data-ttu-id="87213-129">Баған атауы: модель өнімділігін жақсарту үшін өзгерту керек нысандағы баған.</span><span class="sxs-lookup"><span data-stu-id="87213-129">Column name: Column in an entity that needs to be modified to improve the model performance.</span></span>
- <span data-ttu-id="87213-130">Нысан атауы: модель өнімділігін жақсарту үшін өзгерту керек нысан атауы.</span><span class="sxs-lookup"><span data-stu-id="87213-130">Entity name: Name of the entity that needs to be modified to improve the model performance.</span></span>
- <span data-ttu-id="87213-131">Мәліметтер: қате, ескерту немесе ұсыныс туралы мәліметтер.</span><span class="sxs-lookup"><span data-stu-id="87213-131">Details: Details about the error, warning, or recommendation.</span></span>

## <a name="refresh-a-prediction"></a><span data-ttu-id="87213-132">Болжамды жаңарту</span><span class="sxs-lookup"><span data-stu-id="87213-132">Refresh a prediction</span></span>

<span data-ttu-id="87213-133">Болжамдар параметрлерде теңшелген бір [деректер жаңартылатын кестеде](system.md#schedule-tab) автоматты жаңартылады.</span><span class="sxs-lookup"><span data-stu-id="87213-133">Predictions will automatically refresh on the same [schedule your data refreshes](system.md#schedule-tab) as configured in settings.</span></span> <span data-ttu-id="87213-134">Сіз оларды қолмен де жаңарта аласыз.</span><span class="sxs-lookup"><span data-stu-id="87213-134">You can refresh them manually too.</span></span>

1. <span data-ttu-id="87213-135">**Сараптау** > **Болжамдар** тарауына өтіп, **Менің болжамдарым** қойындысын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="87213-135">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="87213-136">Жаңарту керек болжамнан кейінгі тік көп нүктені таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="87213-136">Select the vertical ellipses next to the prediction you want to refresh.</span></span>

1. <span data-ttu-id="87213-137">**Жаңарту** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="87213-137">Select **Refresh**.</span></span>

## <a name="delete-a-prediction"></a><span data-ttu-id="87213-138">Болжамды жою</span><span class="sxs-lookup"><span data-stu-id="87213-138">Delete a prediction</span></span>

<span data-ttu-id="87213-139">Болжамды жою оның шығыс нысанын да жояды.</span><span class="sxs-lookup"><span data-stu-id="87213-139">Deleting a prediction also removes its output entity.</span></span>

1. <span data-ttu-id="87213-140">**Сараптау** > **Болжамдар** тарауына өтіп, **Менің болжамдарым** қойындысын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="87213-140">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="87213-141">Жою керек болжамнан кейінгі тік көп нүктені таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="87213-141">Select the vertical ellipses next to the prediction you want to delete.</span></span>

1. <span data-ttu-id="87213-142">**Жою** пәрменін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="87213-142">Select **Delete**.</span></span>
