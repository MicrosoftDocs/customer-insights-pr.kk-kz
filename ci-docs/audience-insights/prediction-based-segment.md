---
title: Болжам нәтижесіне негізделген сегменттер
description: Болжам үлгісінің шығыс нысаны негізінде сегменттер жасаңыз.
ms.date: 03/24/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 488db1af865ce600ec012716327d053bee33aff8
ms.sourcegitcommit: a95c82f46c23f625cb34fceba021ccc70d4b1df6
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 03/30/2021
ms.locfileid: "5741436"
---
# <a name="create-a-segment-based-on-a-prediction-model-preview"></a><span data-ttu-id="b42c9-103">Болжам үлгісі негізінде сегмент жасау (алдын ала қарау нұсқасы)</span><span class="sxs-lookup"><span data-stu-id="b42c9-103">Create a segment based on a prediction model (preview)</span></span>

<span data-ttu-id="b42c9-104">Болжамдардың нәтижелері кейде сіздің тұтынушыларыңыздың ішкі жиынтығына ғана қолданылады.</span><span class="sxs-lookup"><span data-stu-id="b42c9-104">The results of predictions sometimes only apply to a subset of your customers.</span></span> <span data-ttu-id="b42c9-105">Болжам үлгілерінің нәтижелерінен сегменттер жасау арқылы ұсыныстарды жекелендіруді арттырыңыз.</span><span class="sxs-lookup"><span data-stu-id="b42c9-105">Increase the personalization of recommendations by creating segments from results of prediction models.</span></span> <span data-ttu-id="b42c9-106">Мысалы, сіз белгілі бір қызмет түрін қалайтын тұтынушыларға нақты ұсыныстар бергіңіз келуі мүмкін.</span><span class="sxs-lookup"><span data-stu-id="b42c9-106">For example, you may want to give specific recommendations to customers that prefer a certain type of service.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="b42c9-107">Алғышарттар</span><span class="sxs-lookup"><span data-stu-id="b42c9-107">Prerequisites</span></span>

- <span data-ttu-id="b42c9-108">Customer Insights бағдарламасында кемінде [Салымшы рұқсаттары](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="b42c9-108">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>

- <span data-ttu-id="b42c9-109">Customer Insights бағдарламасында конфигурацияланған өнім ұсынысы, транзакциялық жылыстау, жазылым жылыстауы немесе тұтынушының өмір бойғы құндылығы мәні.</span><span class="sxs-lookup"><span data-stu-id="b42c9-109">A product recommendation, transactional churn, subscription churn, or customer lifetime value model configured in Customer Insights.</span></span> <span data-ttu-id="b42c9-110">Әртүрлі үлгілерді орнатуға қойылатын талаптарды қарап шығыңыз:</span><span class="sxs-lookup"><span data-stu-id="b42c9-110">Review the requirements to set up the different models:</span></span>

  - [<span data-ttu-id="b42c9-111">Өнім ұсыныстарының моделі</span><span class="sxs-lookup"><span data-stu-id="b42c9-111">Product recommendation model</span></span>](predict-product-recommendation.md)
  - [<span data-ttu-id="b42c9-112">Жазылым жылыстауы үлгісі</span><span class="sxs-lookup"><span data-stu-id="b42c9-112">Subscription churn model</span></span>](predict-subscription-churn.md)
  - [<span data-ttu-id="b42c9-113">Транзакциялық жылыстау үлгісі</span><span class="sxs-lookup"><span data-stu-id="b42c9-113">Transactional churn model</span></span>](predict-transactional-churn.md)
  - [<span data-ttu-id="b42c9-114">Тұтынушының өмір бойғы құндылығы үлгісі</span><span class="sxs-lookup"><span data-stu-id="b42c9-114">Customer lifetime value model</span></span>](predict-customer-lifetime-value.md)

## <a name="create-a-customer-segment-based-on-predictions"></a><span data-ttu-id="b42c9-115">Болжамдар негізінде тұтынушы сегментін жасау</span><span class="sxs-lookup"><span data-stu-id="b42c9-115">Create a customer segment based on predictions</span></span>

1. <span data-ttu-id="b42c9-116">**Сараптау** > **Болжамдар** тарауына өтіп, **Менің болжамдарым** қойындысын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="b42c9-116">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="b42c9-117">Қарап шығу керек үлгінің жанындағы тік көп нүктелерді таңдаңыз және **Көру** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="b42c9-117">Select the vertical ellipses next to the model you want to review and select **View**.</span></span>

1. <span data-ttu-id="b42c9-118">Нәтижелер бетінде **Сегмент жасау** түймешігін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="b42c9-118">On the results page, select **Create segment**.</span></span> <span data-ttu-id="b42c9-119">Нәтижелер беті туралы қосымша ақпарат алу үшін үлгі туралы мақаланы қарап шығыңыз.</span><span class="sxs-lookup"><span data-stu-id="b42c9-119">For more information about the results page, review the article about the model.</span></span>

   :::image type="content" source="media/prediction-create-segment.png" alt-text="Сегмент әрекетін жасау опциясы бөлектелген болжам нәтижелері бетінің скриншоты.":::

1. <span data-ttu-id="b42c9-121">Таңдалған үлгінің шығыс нысаны негізінде жаңа сегмент жасаңыз.</span><span class="sxs-lookup"><span data-stu-id="b42c9-121">Create a new segment based on the output entity of the selected model.</span></span> <span data-ttu-id="b42c9-122">Қосымша ақпаратты [Сегменттерді жасау және басқару](segments.md) бөлімінен қараңыз.</span><span class="sxs-lookup"><span data-stu-id="b42c9-122">For more information, see [Create and manage segments](segments.md).</span></span>