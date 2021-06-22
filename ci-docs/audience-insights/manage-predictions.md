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
ms.openlocfilehash: b935be08199f20e83bceb3317985b0e1dc120016
ms.sourcegitcommit: 6b07c9c3102761be162e4842f3c9fbc19f948a9b
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 05/25/2021
ms.locfileid: "6095726"
---
# <a name="manage-predictions"></a><span data-ttu-id="e9cca-103">Болжамдарды басқару</span><span class="sxs-lookup"><span data-stu-id="e9cca-103">Manage predictions</span></span>

<span data-ttu-id="e9cca-104">Бұл мақалада болжам сценарийлерінің көпшілігі бөлісетін кейбір тапсырмалар талқыланады.</span><span class="sxs-lookup"><span data-stu-id="e9cca-104">This article discusses some tasks that most prediction scenarios share.</span></span>

## <a name="troubleshoot-a-failed-prediction"></a><span data-ttu-id="e9cca-105">Сәтсіз аяқталған болжам ақаулықтарын жою</span><span class="sxs-lookup"><span data-stu-id="e9cca-105">Troubleshoot a failed prediction</span></span>

1. <span data-ttu-id="e9cca-106">**Сараптау** > **Болжамдар** тарауына өтіп, **Менің болжамдарым** қойындысын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="e9cca-106">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="e9cca-107">Қате туралы журналдарды көру үшін болжам жанындағы тік эллипстерді таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="e9cca-107">Select the vertical ellipses next to the prediction you want to view error logs for.</span></span>

1. <span data-ttu-id="e9cca-108">**Журналдар** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="e9cca-108">Select **Logs**.</span></span>

1. <span data-ttu-id="e9cca-109">Барлық қателерді қарап шығыңыз.</span><span class="sxs-lookup"><span data-stu-id="e9cca-109">Review all the errors.</span></span> <span data-ttu-id="e9cca-110">Орын алуы мүмкін бірнеше қате түрі бар әрі олар қатеге себеп болған шартты сипаттайды.</span><span class="sxs-lookup"><span data-stu-id="e9cca-110">There are several types of errors that can occur, and they describe what condition caused the error.</span></span> <span data-ttu-id="e9cca-111">Мысалы, Customer Insights бағдарламасына қосымша деректерді жүктеу арқылы дәлірек болжауға жеткілікті деректер болмау қатесі әдепкі жолмен шешіледі.</span><span class="sxs-lookup"><span data-stu-id="e9cca-111">For example, an error that there's not enough data to accurately predict is typically resolved by loading additional data into Customer Insights.</span></span>

## <a name="input-data-usability-report"></a><span data-ttu-id="e9cca-112">Кіріс деректердің пайдалану ыңғайлылығы туралы есеп</span><span class="sxs-lookup"><span data-stu-id="e9cca-112">Input data usability report</span></span>

<span data-ttu-id="e9cca-113">Кіріс деректерді пайдалану туралы есеп дайын болжамдар жасауы мүмкін қателер мен ескертулердің біріккен көрінісін ұсынады.</span><span class="sxs-lookup"><span data-stu-id="e9cca-113">The input data usability report provides a consolidated view of the errors and warnings that your out-of-box predictions may be generating.</span></span> <span data-ttu-id="e9cca-114">Сондай-ақ ол модель өнімділігін жақсарту бойынша ұсыныстар береді.</span><span class="sxs-lookup"><span data-stu-id="e9cca-114">It also gives recommendations how to improve the model performance.</span></span>

<span data-ttu-id="e9cca-115">Есеп модель оқыту процесін аяқтағаннан кейін қолжетімді болады.</span><span class="sxs-lookup"><span data-stu-id="e9cca-115">The report is available after a model has completed its training process.</span></span> <span data-ttu-id="e9cca-116">Ол сәтті аяқталғанына немесе аяқталмағанына қарамастан, әр модель үшін бөлек жасалады.</span><span class="sxs-lookup"><span data-stu-id="e9cca-116">It's created for each model separately, regardless if it completed successfully or not.</span></span>

> [!NOTE]
> <span data-ttu-id="e9cca-117">Қазіргі уақытта бұл функция тек транзакциялық жылыстау моделі үшін жұмыс істейді.</span><span class="sxs-lookup"><span data-stu-id="e9cca-117">Currently, this feature only works for the Transaction Churn model.</span></span>

### <a name="view-the-input-data-usability-report"></a><span data-ttu-id="e9cca-118">Кіріс деректерді пайдалану туралы есепті көру</span><span class="sxs-lookup"><span data-stu-id="e9cca-118">View the input data usability report</span></span>

<span data-ttu-id="e9cca-119">Дайын модель оқыту қадамын аяқтағаннан кейін, есепті қараңыз:</span><span class="sxs-lookup"><span data-stu-id="e9cca-119">After an out-of-box model has completed its training step, view the report:</span></span>
- <span data-ttu-id="e9cca-120">Модель атауының жанындағы көп нүктені таңдаңыз және **Кіріс деректерді пайдалану туралы есеп** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="e9cca-120">Select the ellipses next to the model name and choose **Input data usability report**.</span></span>
- <span data-ttu-id="e9cca-121">Модель күйін таңдау үшін бүйірлік тақтада **Кіріс деректерді пайдалану туралы есепті қарау** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="e9cca-121">Select the status of a model select **See Input data usability report** in the side pane.</span></span>
- <span data-ttu-id="e9cca-122">Тізімдегі модельдердің бірін таңдап, пәрмен жолағында **Кіріс деректерді пайдалану туралы есеп** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="e9cca-122">Selecting one of the models in the list and select **Input data usability report** in the command bar.</span></span>
- <span data-ttu-id="e9cca-123">Модель нәтижелері бетін ашыңыз және пәрмен жолағында **Кіріс деректерді пайдалану туралы есеп** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="e9cca-123">Open the model results page and select **Input data usability report** in the command bar.</span></span>

### <a name="information-in-the-input-data-usability-report"></a><span data-ttu-id="e9cca-124">Кіріс деректерді пайдалану туралы есептегі ақпарат</span><span class="sxs-lookup"><span data-stu-id="e9cca-124">Information in the input data usability report</span></span>

<span data-ttu-id="e9cca-125">Есептегі келесі бағандар модельге арналған деректерді жақсартуға арналған пайдалы ақпаратты қамтиды.</span><span class="sxs-lookup"><span data-stu-id="e9cca-125">The following columns in the report contain helpful information to improve the data for the model.</span></span>

:::image type="content" source="media/input-data-usability-report.png" alt-text="Қателері, ескертулері мен ұсыныстары бар кестені көрсететін кіріс деректерді пайдалану туралы есептің мысалы.":::

- <span data-ttu-id="e9cca-127">Атауы: қатенің, ескерту немесе ұсыныстың сипаттамалық атауы.</span><span class="sxs-lookup"><span data-stu-id="e9cca-127">Name: Descriptive name of the error, warning, or recommendation.</span></span>
- <span data-ttu-id="e9cca-128">Қадам: ақпарат сілтеме жасайтын модель кезең, оқыту немесе ұпай.</span><span class="sxs-lookup"><span data-stu-id="e9cca-128">Step: Model phase, train or score, the information refers to.</span></span>
- <span data-ttu-id="e9cca-129">Күйі: ақпараттың маңыздылығы (қате, ескерту, ұсыныс).</span><span class="sxs-lookup"><span data-stu-id="e9cca-129">State: Severity of the information (error, warning, recommendation).</span></span>
- <span data-ttu-id="e9cca-130">Баған атауы: модель өнімділігін жақсарту үшін өзгерту керек нысандағы баған.</span><span class="sxs-lookup"><span data-stu-id="e9cca-130">Column name: Column in an entity that needs to be modified to improve the model performance.</span></span>
- <span data-ttu-id="e9cca-131">Нысан атауы: модель өнімділігін жақсарту үшін өзгерту керек нысан атауы.</span><span class="sxs-lookup"><span data-stu-id="e9cca-131">Entity name: Name of the entity that needs to be modified to improve the model performance.</span></span>
- <span data-ttu-id="e9cca-132">Мәліметтер: қате, ескерту немесе ұсыныс туралы мәліметтер.</span><span class="sxs-lookup"><span data-stu-id="e9cca-132">Details: Details about the error, warning, or recommendation.</span></span>

## <a name="refresh-a-prediction"></a><span data-ttu-id="e9cca-133">Болжамды жаңарту</span><span class="sxs-lookup"><span data-stu-id="e9cca-133">Refresh a prediction</span></span>

<span data-ttu-id="e9cca-134">Болжамдар параметрлерде теңшелген бір [деректер жаңартылатын кестеде](system.md#schedule-tab) автоматты жаңартылады.</span><span class="sxs-lookup"><span data-stu-id="e9cca-134">Predictions will automatically refresh on the same [schedule your data refreshes](system.md#schedule-tab) as configured in settings.</span></span> <span data-ttu-id="e9cca-135">Сіз оларды қолмен де жаңарта аласыз.</span><span class="sxs-lookup"><span data-stu-id="e9cca-135">You can refresh them manually too.</span></span>

1. <span data-ttu-id="e9cca-136">**Сараптау** > **Болжамдар** тарауына өтіп, **Менің болжамдарым** қойындысын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="e9cca-136">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="e9cca-137">Жаңарту керек болжамнан кейінгі тік көп нүктені таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="e9cca-137">Select the vertical ellipses next to the prediction you want to refresh.</span></span>

1. <span data-ttu-id="e9cca-138">**Жаңарту** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="e9cca-138">Select **Refresh**.</span></span>

## <a name="delete-a-prediction"></a><span data-ttu-id="e9cca-139">Болжамды жою</span><span class="sxs-lookup"><span data-stu-id="e9cca-139">Delete a prediction</span></span>

<span data-ttu-id="e9cca-140">Болжамды жою оның шығыс нысанын да жояды.</span><span class="sxs-lookup"><span data-stu-id="e9cca-140">Deleting a prediction also removes its output entity.</span></span>

1. <span data-ttu-id="e9cca-141">**Сараптау** > **Болжамдар** тарауына өтіп, **Менің болжамдарым** қойындысын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="e9cca-141">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="e9cca-142">Жою керек болжамнан кейінгі тік көп нүктені таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="e9cca-142">Select the vertical ellipses next to the prediction you want to delete.</span></span>

1. <span data-ttu-id="e9cca-143">**Жою** пәрменін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="e9cca-143">Select **Delete**.</span></span>
