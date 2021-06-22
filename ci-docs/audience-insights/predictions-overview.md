---
title: Қолдау көрсетілетін болжам сценарийлері туралы шолу
description: Dynamics 365 Customer Insights бағдарламасында қамтылған болжам сценарийлері мен опциялары.
ms.date: 05/18/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: get-started
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 69ae945b22819521db217508c6fc232876346747
ms.sourcegitcommit: 6b07c9c3102761be162e4842f3c9fbc19f948a9b
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 05/25/2021
ms.locfileid: "6095725"
---
# <a name="predictions-overview"></a><span data-ttu-id="9cdf1-103">Болжамдарға шолу</span><span class="sxs-lookup"><span data-stu-id="9cdf1-103">Predictions overview</span></span>

<span data-ttu-id="9cdf1-104">Dynamics 365 Customer Insights бағдарламасы деректерді болжау үшін AI мен компьютерлік оқыту функциясын қолданатын түрлі опцияларымен бірге келеді.</span><span class="sxs-lookup"><span data-stu-id="9cdf1-104">Dynamics 365 Customer Insights comes with a variety of options that leverage AI and machine learning to predict data.</span></span> 

## <a name="out-of-box-models"></a><span data-ttu-id="9cdf1-105">Дайын модельдер</span><span class="sxs-lookup"><span data-stu-id="9cdf1-105">Out-of-box models</span></span>

<span data-ttu-id="9cdf1-106">Деректерді болжауды бастаудың ең оңай жолы алдын ала анықталған модельдер болып табылады, оларды көбінесе дайын модельдер деп атайды.</span><span class="sxs-lookup"><span data-stu-id="9cdf1-106">The easiest way to start with predicting data are predefined models, often referred to as out-of-box models.</span></span> <span data-ttu-id="9cdf1-107">Олар жылдам түсініктер қалыптастыру үшін белгілі бір деректер мен құрылымды қажет етеді.</span><span class="sxs-lookup"><span data-stu-id="9cdf1-107">They only require certain data and structure to generate insights quickly.</span></span> <span data-ttu-id="9cdf1-108">Қазіргі уақытта келесі модельдер қолжетімді:</span><span class="sxs-lookup"><span data-stu-id="9cdf1-108">Currently, the following models are available:</span></span> 
- <span data-ttu-id="9cdf1-109">[Тұтынушының өмір бойғы құндылығы](predict-customer-lifetime-value.md): тұтынушының барлық бизнеспен өзара әрекеттесуі кезінде ықтимал кірісін болжайды.</span><span class="sxs-lookup"><span data-stu-id="9cdf1-109">[Customer lifetime value](predict-customer-lifetime-value.md): Predicts the potential revenue of a customer throughout the entire interaction with a business.</span></span> 
- <span data-ttu-id="9cdf1-110">[Өнімге ұсыныс](predict-product-recommendation.md): сатып алу әрекеті мен сатып алудың ұқсас үлгілері бар тұтынушыларға негізделген болжамды өнім ұсыныстарының жиынтығын ұсынады.</span><span class="sxs-lookup"><span data-stu-id="9cdf1-110">[Product recommendation](predict-product-recommendation.md): Suggests sets of predictive product recommendations based on purchase behavior and customers with similar purchase patterns.</span></span>
- <span data-ttu-id="9cdf1-111">[Жазылымдардан тұтынушылардың кетуі](predict-subscription-churn.md): тұтынушының сіздің компанияңыздың жазылым өнімдері мен қызметтерін бұдан әрі пайдаланбау қаупі бар-жоғын болжайды.</span><span class="sxs-lookup"><span data-stu-id="9cdf1-111">[Subscription churn](predict-subscription-churn.md): Predicts whether a customer is at risk for no longer using your company’s subscription products or services.</span></span>
- <span data-ttu-id="9cdf1-112">[Транзакциялық жылыстау](predict-transactional-churn.md): тұтынушы сіздің өнімдеріңізді немесе қызметтеріңізді белгілі бір уақыт аралығында сатып алмайтынын болжаңыз.</span><span class="sxs-lookup"><span data-stu-id="9cdf1-112">[Transactional churn](predict-transactional-churn.md): Predict if a customer will no longer purchase your products or services in a certain time frame.</span></span>

## <a name="azure-machine-learning-integration"></a><span data-ttu-id="9cdf1-113">Azure компьютерлік оқыту бірігуі</span><span class="sxs-lookup"><span data-stu-id="9cdf1-113">Azure Machine Learning integration</span></span>

<span data-ttu-id="9cdf1-114">Егер ұйым Azure компьютерлік оқыту тәжірибелеріне негізделген компьютерлік оқыту сценарийлерін бұрыннан қолданса, Customer Insights бағдарламасындағы реттелетін модельдер мүмкіндігі нүктелерді қосуға көмектеседі.</span><span class="sxs-lookup"><span data-stu-id="9cdf1-114">If an organization already uses machine learning scenarios based on Azure Machine Learning experiments, the custom models feature in Customer Insights helps to connect the dots.</span></span> <span data-ttu-id="9cdf1-115">Түсінік жасау керек деректерді таңдауға көмектесетін жұмыс ағындарын жасаңыз және нәтижелерді сіздің тұтынушыларыңыздың бірыңғай профильдерімен салыстырыңыз.</span><span class="sxs-lookup"><span data-stu-id="9cdf1-115">Create workflows that help you choose the data you want to generate insights from and map the results to your unified customer profiles.</span></span> <span data-ttu-id="9cdf1-116">Қосымша ақпаратты [Реттелетін компьютерлік оқыту модельдері](custom-models.md) бөлімінен қараңыз.</span><span class="sxs-lookup"><span data-stu-id="9cdf1-116">For more information, see [Custom machine learning models](custom-models.md).</span></span>

## <a name="ai-builder-prediction"></a><span data-ttu-id="9cdf1-117">AI Builder болжамы</span><span class="sxs-lookup"><span data-stu-id="9cdf1-117">AI Builder prediction</span></span>

<span data-ttu-id="9cdf1-118">Кейде деректер жиынтығы толық емес, ал кейбір мәндер жоқ болады.</span><span class="sxs-lookup"><span data-stu-id="9cdf1-118">Sometimes, data sets are incomplete and some values are missing.</span></span> <span data-ttu-id="9cdf1-119">Customer Insights бағдарламасы тұтынушы нысаны мен сегменттері үшін жетіспейтін мәндерді болжауға көмектеседі.</span><span class="sxs-lookup"><span data-stu-id="9cdf1-119">Customer Insights can help to predict missing values for the Customer entity and segments.</span></span> <span data-ttu-id="9cdf1-120">Қосымша ақпарат алу үшін [Ішінара деректерді болжамдармен толықтыру](predictions.md) бөлімін қараңыз.</span><span class="sxs-lookup"><span data-stu-id="9cdf1-120">For more information, see [Complete your partial data with predictions](predictions.md).</span></span>
