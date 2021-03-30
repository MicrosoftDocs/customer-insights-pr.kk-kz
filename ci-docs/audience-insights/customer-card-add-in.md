---
title: Тұтынушы картасының қондырмасын орнату және конфигурациялау
description: Dynamics 365 Customer Insights Тұтынушы картасы қондырмасын орнатыңыз және теңшеңіз.
ms.date: 01/20/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: f3c4a01f9ce7749eeee72f7901620dae7cb9b8d3
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597334"
---
# <a name="customer-card-add-in-preview"></a><span data-ttu-id="48943-103">Тұтынушы картасының қондырмасы (алдын ала қарау)</span><span class="sxs-lookup"><span data-stu-id="48943-103">Customer Card Add-in (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="48943-104">Dynamics 365 бағдарламаларында тікелей тұтынушыларыңыздың 360 градустық көрінісін алыңыз.</span><span class="sxs-lookup"><span data-stu-id="48943-104">Get a 360-degree view of your customers directly in Dynamics 365 apps.</span></span> <span data-ttu-id="48943-105">Тұтынушы картасының қондырмасымен демографиялық көрсеткіштер, түсініктер мен әрекеттің уақыт шкалаларын қараңыз.</span><span class="sxs-lookup"><span data-stu-id="48943-105">View demographics, insights, and activity timelines with the Customer Card Add-in.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="48943-106">Алғышарттар</span><span class="sxs-lookup"><span data-stu-id="48943-106">Prerequisites</span></span>

- <span data-ttu-id="48943-107">Бірыңғай интерфейс қосылған 9.0 және кейінгі нұсқасындағы Dynamics 365 (Сату орталығы немесе Тұтынушыға қызмет көрсету орталығы) бағдарламасы.</span><span class="sxs-lookup"><span data-stu-id="48943-107">Dynamics 365 app (such as Sales Hub or Customer Service Hub), version 9.0 and later with Unified Interface enabled.</span></span>
- <span data-ttu-id="48943-108">Тұтынушы профильдері [Common Data Service арқылы Dynamics 365 бағдарламасынан алынған](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="48943-108">Customer profiles [ingested from the Dynamics 365 app using Common Data Service](connect-power-query.md).</span></span>
- <span data-ttu-id="48943-109">Тұтынушы картасы қондырмасының пайдаланушылары аудитория мәліметтерінде [пайдаланушылар ретінде қосылуы](permissions.md) қажет.</span><span class="sxs-lookup"><span data-stu-id="48943-109">Users of the Customer Card Add-in need to be [added as users](permissions.md) in audience insights.</span></span>
- <span data-ttu-id="48943-110">[Конфигурацияланған іздеу және сүзгілеу мүмкіндіктері](search-filter-index.md).</span><span class="sxs-lookup"><span data-stu-id="48943-110">[Configured search and filter capabilities](search-filter-index.md).</span></span>
- <span data-ttu-id="48943-111">Демографиялық бақылау: демографиялық өрістер (жас немесе жыныс секілді) тұтынушының бірыңғай профилінде қолжетімді.</span><span class="sxs-lookup"><span data-stu-id="48943-111">Demographic control: Demographic fields(such as age or gender) are available in the unified customer profile.</span></span>
- <span data-ttu-id="48943-112">Арттыруды басқару құралы: тұтынушы профильдеріне қолданылған белсенді [арттыруларды](enrichment-hub.md) талап етеді.</span><span class="sxs-lookup"><span data-stu-id="48943-112">Enrichment control: Requires active [enrichments](enrichment-hub.md) applied to customer profiles.</span></span>
- <span data-ttu-id="48943-113">Интеллектті бақылау: Azure Machine Learning ([Болжамдар](predictions.md) немесе [Реттелетін үлгілер](custom-models.md)) арқылы жасалған деректер қажет</span><span class="sxs-lookup"><span data-stu-id="48943-113">Intelligence control: Requires data generated using Azure Machine Learning ([Predictions](predictions.md) or [Custom Models](custom-models.md))</span></span>
- <span data-ttu-id="48943-114">Өлшемді бақылау: [конфигурацияланған өлшемдерді](measures.md) қажет етеді.</span><span class="sxs-lookup"><span data-stu-id="48943-114">Measure control: Requires [configured measures](measures.md).</span></span>
- <span data-ttu-id="48943-115">Уақыт шкаласын бақылау: [конфигурацияланған әрекеттерді](activities.md) қажет етеді.</span><span class="sxs-lookup"><span data-stu-id="48943-115">Timeline control: Requires [configured activities](activities.md).</span></span>

## <a name="install-the-customer-card-add-in"></a><span data-ttu-id="48943-116">Тұтынушы картасы қондырмасын орнату</span><span class="sxs-lookup"><span data-stu-id="48943-116">Install the Customer Card Add-in</span></span>

<span data-ttu-id="48943-117">Тұтынушы картасының қондырмасы – Dynamics 365 жүйесіндегі Customer Engagement бағдарламаларының шешімі.</span><span class="sxs-lookup"><span data-stu-id="48943-117">The Customer Card Add-in is a solution for customer engagement apps in Dynamics 365.</span></span> <span data-ttu-id="48943-118">Шешімді орнату үшін AppSource жүйесіне өтіп, **Dynamics тұтынушы картасын** іздеңіз.</span><span class="sxs-lookup"><span data-stu-id="48943-118">To install the solution, go to AppSource and search for **Dynamics Customer Card**.</span></span> <span data-ttu-id="48943-119">[AppSource жүйесіндегі тұтынушы картасының қондырмасын](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) таңдап, **Оны қазір алу** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="48943-119">Select the [Customer Card Add-in on AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) and select **Get It Now**.</span></span>

<span data-ttu-id="48943-120">Шешімді орнату үшін Dynamics 365 бағдарламасына арналған әкімші тіркелгі деректерімен кіру қажет болуы мүмкін.</span><span class="sxs-lookup"><span data-stu-id="48943-120">You may need to sign in with your admin credentials for the Dynamics 365 app to install the solution.</span></span>

<span data-ttu-id="48943-121">Ортаңызға шешімді орнатуға біраз уақыт кетуі мүмкін.</span><span class="sxs-lookup"><span data-stu-id="48943-121">It can take some time for the solution to be installed to your environment.</span></span>

## <a name="configure-the-customer-card-add-in"></a><span data-ttu-id="48943-122">Тұтынушы картасының қондырмасын конфигурациялау</span><span class="sxs-lookup"><span data-stu-id="48943-122">Configure the Customer Card Add-in</span></span>

1. <span data-ttu-id="48943-123">Әкімші ретінде Dynamics 365 ішіндегі **Параметрлер** бөліміне өтіп, **Шешімдер** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="48943-123">As an admin, go to the **Settings** section in Dynamics 365 and select **Solutions**.</span></span>

1. <span data-ttu-id="48943-124">**Dynamics 365 Customer Insights тұтынушы картасының қондырмасы (алдын ала қарау)** шешімі үшін **Көрсетілетін атау** сілтемесін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="48943-124">Select the **Display Name** link for the **Dynamics 365 Customer Insights Customer Card Add-in (Preview)** solution.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="48943-125">![Көрсетілетін атын таңдау](media/select-display-name.png "Көрсетілетін атын таңдау")</span><span class="sxs-lookup"><span data-stu-id="48943-125">![Select display name](media/select-display-name.png "Select display name")</span></span>

1. <span data-ttu-id="48943-126">**Кіру** опциясын таңдап, Customer Insights бағдарламасын конфигурациялау үшін пайдаланатын әкімші тіркелгісінің деректерін енгізіңіз.</span><span class="sxs-lookup"><span data-stu-id="48943-126">Select **Sign in** and enter the credentials for the admin account you use to configure Customer Insights.</span></span>

   > [!NOTE]
   > <span data-ttu-id="48943-127">**Кіру** түймесін таңдаған кезде шолғыштың ашылмалы терезені құлыптау құралы аутентификация терезесін бұғаттамайтынын тексеріңіз.</span><span class="sxs-lookup"><span data-stu-id="48943-127">Check that the browser pop-up blocker does not block the authentication window when you select the **Sign in** button.</span></span>

1. <span data-ttu-id="48943-128">Деректер алынатын ортаны таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="48943-128">Select the environment you want to fetch data from.</span></span>

1. <span data-ttu-id="48943-129">Өрістерді Dynamics 365 бағдарламасында қандай жазбалармен салыстыруға болатындығын анықтаңыз.</span><span class="sxs-lookup"><span data-stu-id="48943-129">Define which the field mapping to records in the Dynamics 365 app.</span></span>
   - <span data-ttu-id="48943-130">Контактімен салыстыру үшін контакт нысанының идентификаторына сәйкес келетін тұтынушы нысанындағы өрісті таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="48943-130">To map with a contact, select the field in the Customer entity that matches the ID of your contact entity.</span></span>
   - <span data-ttu-id="48943-131">Тіркелгімен салыстыру үшін тіркелгі нысанының идентификаторына сәйкес келетін тұтынушы нысанындағы өрісті таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="48943-131">To map with an account, select the field in the Customer entity that matches the ID of your account entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="48943-132">![Контакт ИД өрісі](media/contact-id-field.png "Контакт ИД өрісі")</span><span class="sxs-lookup"><span data-stu-id="48943-132">![Contact ID field](media/contact-id-field.png "Contact ID field")</span></span>

1. <span data-ttu-id="48943-133">Параметрді сақтау үшін **Конфигурацияны сақтау** параметрлерін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="48943-133">Select **Save configuration** to save the settings.</span></span>

1. <span data-ttu-id="48943-134">Әрі қарай, пайдаланушылар тұтынушы картасын теңшей және көре алатындай етіп Dynamics 365 жүйесінде қауіпсіздік рөлдерін тағайындау керек.</span><span class="sxs-lookup"><span data-stu-id="48943-134">Next, you need to assign security roles in Dynamics 365 so users can customize and see the customer card.</span></span> <span data-ttu-id="48943-135">Dynamics 365 жүйесінде **Параметрлер** > **Қауіпсіздік** > **Пайдаланушылар** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="48943-135">In Dynamics 365, go to **Settings** > **Security** > **Users**.</span></span> <span data-ttu-id="48943-136">Пайдаланушы рөлдерін өзгерту үшін пайдаланушыларды таңдап, **Рөлдерді басқару** опциясын басыңыз.</span><span class="sxs-lookup"><span data-stu-id="48943-136">Select the users to edit user roles and select **Manage roles**.</span></span>

1. <span data-ttu-id="48943-137">**Customer Insights картасын баптаушы** рөлін бүкіл ұйымға арналған картада көрсетілген мазмұнды теңшейтін пайдаланушыларға белгілеңіз.</span><span class="sxs-lookup"><span data-stu-id="48943-137">Assign the **Customer Insights Card Customizer** role to users who will customize the content shown on the card for the whole organization.</span></span>

## <a name="add-customer-card-controls-to-forms"></a><span data-ttu-id="48943-138">Тұтынушы картасын пішіндерге қосу</span><span class="sxs-lookup"><span data-stu-id="48943-138">Add Customer Card controls to forms</span></span>
  
1. <span data-ttu-id="48943-139">Тұтынушы картасының басқару элементтерін контакт пішініне қосу үшін Dynamics 365 бағдарламасында **Параметрлер** > **Теңшелімдер** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="48943-139">To add the Customer Card controls to your Contact form, go to the **Settings** > **Customizations** in Dynamics 365.</span></span>

1. <span data-ttu-id="48943-140">**Жүйені теңшеу** пәрменін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="48943-140">Select **Customize the System**.</span></span>

1. <span data-ttu-id="48943-141">**Контакт** нысанын шолыңыз, оны кеңейтіп, **Пішіндер** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="48943-141">Browse to the **Contact** entity, expand it and select **Forms**.</span></span>

1. <span data-ttu-id="48943-142">Тұтынушы картасын басқару құралдарын қосу керек контакт пішінін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="48943-142">Select the contact form to which you want to add the Customer Card controls.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="48943-143">![Контакт пішінін таңдау](media/contact-active-forms.png "Контакт пішінін таңдау")</span><span class="sxs-lookup"><span data-stu-id="48943-143">![Select Contact form](media/contact-active-forms.png "Select Contact form")</span></span>

1. <span data-ttu-id="48943-144">Басқару құралын қосу үшін, пішін өңдегішінде кез келген **Өріс жетектеушісі** өрісін басқару құралы пайда болатын орынға сүйреңіз.</span><span class="sxs-lookup"><span data-stu-id="48943-144">To add a control, in the form editor, drag any field from the **Field Explorer** to where you want the control to appear.</span></span>

1. <span data-ttu-id="48943-145">Жаңа ғана қосқан пішіннен өрісті таңдап, **Сипаттарды өзгерту** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="48943-145">Select the field on the form that you just added, and select **Change Properties**.</span></span>

1. <span data-ttu-id="48943-146">**Басқару құралдары** қойыншасына өтіп, **Басқару құралын қосу** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="48943-146">Go to the **Controls** tab and select **Add Control**.</span></span> <span data-ttu-id="48943-147">Қолжетімді басқару элементтерінің бірін таңдап, **Қосу** опциясын басыңыз.</span><span class="sxs-lookup"><span data-stu-id="48943-147">Choose one of the available custom controls and select **Add**.</span></span>

1. <span data-ttu-id="48943-148">**Өріс сипаттары** диалог терезесінде **Пішінде белгіні көрсету** құсбелгісін алыңыз.</span><span class="sxs-lookup"><span data-stu-id="48943-148">In the **Field Properties** dialog, clear the **Display label on the form** check box.</span></span>

1. <span data-ttu-id="48943-149">Басқаруға арналған **Веб** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="48943-149">Select the **Web** option for the control.</span></span> <span data-ttu-id="48943-150">Арттыруды басқару үшін **enrichmentType** өрісін теңшеу арқылы көрсету қажет арттыру түрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="48943-150">For the Enrichment control, select which enrichment type you want to display by configuring the **enrichmentType** field.</span></span> <span data-ttu-id="48943-151">Әр арттыру түріне жеке арттыру бақылауын қосыңыз.</span><span class="sxs-lookup"><span data-stu-id="48943-151">Add a separate enrichment control for each enrichment type.</span></span>

1. <span data-ttu-id="48943-152">Жаңартылған контакт пішінін жариялау үшін **Сақтау** және **Жариялау** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="48943-152">Select **Save** and **Publish** to publish the updated contact form.</span></span>

1. <span data-ttu-id="48943-153">Жарияланған контакт пішініне өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="48943-153">Go to the published contact form.</span></span> <span data-ttu-id="48943-154">Жаңадан қосылған басқару элементін көресіз.</span><span class="sxs-lookup"><span data-stu-id="48943-154">You'll see the newly added control.</span></span> <span data-ttu-id="48943-155">Алғаш рет пайдаланған кезде жүйеге кіруіңіз керек болуы мүмкін.</span><span class="sxs-lookup"><span data-stu-id="48943-155">You might need to sign in the first time you use it.</span></span>

1. <span data-ttu-id="48943-156">Реттелетін басқару құралын көрсету керек мәліметті теңшеу үшін үстіңгі оң жақ бұрыштан өңдеу түймесін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="48943-156">To customize what you want to show on the custom control, select the edit button in the upper-right corner.</span></span>

## <a name="upgrade-customer-card-add-in"></a><span data-ttu-id="48943-157">Тұтынушы картасының қондырмасын жаңарту</span><span class="sxs-lookup"><span data-stu-id="48943-157">Upgrade Customer Card Add-in</span></span>
<span data-ttu-id="48943-158">Тұтынушы картасы қондырмасы автоматты түрде жаңартылмайды.</span><span class="sxs-lookup"><span data-stu-id="48943-158">The Customer Card Add-in doesn't upgrade automatically.</span></span> <span data-ttu-id="48943-159">Соңғы нұсқаға жаңарту үшін қондырмасы орнатылған Dynamics 365 бағдарламасында осы процедураны орындаңыз.</span><span class="sxs-lookup"><span data-stu-id="48943-159">To upgrade to the latest version, follow this procedure in the Dynamics 365 app that has the Add-in installed.</span></span>

1. <span data-ttu-id="48943-160">Dynamics 365 бағдарламасында **Параметрлер** > **Реттеу** және **Шешімдер** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="48943-160">In the Dynamics 365 app, go to **Settings** > **Customization** and select **Solutions**.</span></span>

1. <span data-ttu-id="48943-161">Қондырмалар кестесінде **CustomerInsightsCustomerCard** дерегін іздеп, жолды таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="48943-161">In the table of add-ins look for **CustomerInsightsCustomerCard** and select the row.</span></span>

1. <span data-ttu-id="48943-162">Әрекет жолағында **Шешім жаңартуын қолдану** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="48943-162">Select the **Apply Solution Upgrade** in the action bar.</span></span>

   :::image type="content" source="media/customer-card-add-in-upgrade.png" alt-text="Шешімді Dynamics 365 бағдарламаларының реттеу аймағында жаңарту":::

1. <span data-ttu-id="48943-164">Жаңарту процесін бастағаннан кейін жаңарту аяқталғанға дейін жүктеу индикаторын көресіз.</span><span class="sxs-lookup"><span data-stu-id="48943-164">After starting the upgrade process, you'll see a loading indicator until the upgrade completes.</span></span> <span data-ttu-id="48943-165">Егер жаңа нұсқасы болмаса, жаңарту кезінде қате туралы хабарлама көрсетіледі.</span><span class="sxs-lookup"><span data-stu-id="48943-165">If there's no newer version, the upgrade will show an error message.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]