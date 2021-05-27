---
title: Dynamics 365 бағдарламаларына арналған тұтынушы картасының қондырмасы
description: Осы қондырмамен Dynamics 365 бағдарламаларында аудитория туралы түсініктердегі деректерді көрсетіңіз.
ms.date: 05/18/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 88492943ddbf9ae30c64d92b261433b74f34f682
ms.sourcegitcommit: d74430270f1b754322287c4f045d7febdae35be2
ms.translationtype: HT
ms.contentlocale: kk-KZ
ms.lasthandoff: 05/18/2021
ms.locfileid: "6059595"
---
# <a name="customer-card-add-in-preview"></a><span data-ttu-id="9c028-103">Тұтынушы картасының қондырмасы (алдын ала қарау)</span><span class="sxs-lookup"><span data-stu-id="9c028-103">Customer Card Add-in (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="9c028-104">Dynamics 365 бағдарламаларында тікелей тұтынушыларыңыздың 360 градустық көрінісін алыңыз.</span><span class="sxs-lookup"><span data-stu-id="9c028-104">Get a 360-degree view of your customers directly in Dynamics 365 apps.</span></span> <span data-ttu-id="9c028-105">Қолдау көрсетілетін Dynamics 365 бағдарламасына орнатылған тұтынушы картасының қондырмасы арқылы демографиялық деректерді, түсініктер мен әрекеттің уақыт шкалаларын көрсетуді таңдауға болады.</span><span class="sxs-lookup"><span data-stu-id="9c028-105">With the Customer Card Add-in installed in a supported Dynamics 365 app you can choose to display demographics, insights, and activity timelines.</span></span> <span data-ttu-id="9c028-106">Қондырма қосылған Dynamics 365 бағдарламасындағы деректерге әсер етпей, Customer Insights бағдарламасынан деректерді алады.</span><span class="sxs-lookup"><span data-stu-id="9c028-106">The add-in will retrieve data from Customer Insights without affecting the data in the connected Dynamics 365 app.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="9c028-107">Алғышарттар</span><span class="sxs-lookup"><span data-stu-id="9c028-107">Prerequisites</span></span>

- <span data-ttu-id="9c028-108">Қондырма тек Sales немесе Customer Service бағдарламасының 9.0 немесе және одан кейінгі нұсқалары сияқты Dynamics 365 модельге негізделген бағдарламаларымен жұмыс істейді.</span><span class="sxs-lookup"><span data-stu-id="9c028-108">The add-in only works with Dynamics 365 model-driven apps, such as Sales or Customer Service, version 9.0 and later.</span></span>
- <span data-ttu-id="9c028-109">Dynamics 365 деректері аудитория туралы түсініктер тұтынушы профилінде көрсетілуі үшін олар [Common Data Service қосқышының көмегімен Dynamics 365 бағдарламасынан алынуы керек](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="9c028-109">For your Dynamics 365 data to map to the audience insights customer profiles they need to be [ingested from the Dynamics 365 app using the Common Data Service connector](connect-power-query.md).</span></span>
- <span data-ttu-id="9c028-110">Тұтынушы картасы қондырмасының барлық Dynamics 365 пайдаланушыларын деректерді көру үшін аудитория туралы түсініктерге [пайдаланушылар ретінде қосу керек](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="9c028-110">All Dynamics 365 users of the Customer Card Add-in must be [added as users](permissions.md) in audience insights to see the data.</span></span>
- <span data-ttu-id="9c028-111">Аудитория туралы түсініктердегі [конфигурацияланған іздеу және сүзгі мүмкіндіктері](search-filter-index.md) жұмыс істейтін деректерді іздеу үшін қажет.</span><span class="sxs-lookup"><span data-stu-id="9c028-111">[Configured search and filter capabilities](search-filter-index.md) in audience insights are required for lookup of data to work.</span></span>
- <span data-ttu-id="9c028-112">Әр қондырманы басқару элементі аудитория туралы түсініктердегі нақты деректерге сүйенеді:</span><span class="sxs-lookup"><span data-stu-id="9c028-112">Each add-in control relies on specific data in audience insights:</span></span>
  - <span data-ttu-id="9c028-113">Өлшемді бақылау: [конфигурацияланған өлшемдерді](measures.md) қажет етеді.</span><span class="sxs-lookup"><span data-stu-id="9c028-113">Measure control: Requires [configured measures](measures.md).</span></span>
  - <span data-ttu-id="9c028-114">Зияткерлік басқару элементі: [болжамдар](predictions.md) немесе [реттелетін модельдер](custom-models.md) көмегімен жасалған деректерді қажет етеді.</span><span class="sxs-lookup"><span data-stu-id="9c028-114">Intelligence control: Requires data generated using [predictions](predictions.md) or [custom models](custom-models.md).</span></span>
  - <span data-ttu-id="9c028-115">Демографиялық бақылау: демографиялық өрістер (жас немесе жыныс секілді) тұтынушының бірыңғай профилінде қолжетімді.</span><span class="sxs-lookup"><span data-stu-id="9c028-115">Demographic control: Demographic fields(such as age or gender) are available in the unified customer profile.</span></span>
  - <span data-ttu-id="9c028-116">Арттыруды басқару құралы: тұтынушы профильдеріне қолданылған белсенді [арттыруларды](enrichment-hub.md) талап етеді.</span><span class="sxs-lookup"><span data-stu-id="9c028-116">Enrichment control: Requires active [enrichments](enrichment-hub.md) applied to customer profiles.</span></span>
  - <span data-ttu-id="9c028-117">Уақыт шкаласын бақылау: [конфигурацияланған әрекеттерді](activities.md) қажет етеді.</span><span class="sxs-lookup"><span data-stu-id="9c028-117">Timeline control: Requires [configured activities](activities.md).</span></span>

## <a name="install-the-customer-card-add-in"></a><span data-ttu-id="9c028-118">Тұтынушы картасы қондырмасын орнату</span><span class="sxs-lookup"><span data-stu-id="9c028-118">Install the Customer Card Add-in</span></span>

<span data-ttu-id="9c028-119">Тұтынушы картасының қондырмасы – Dynamics 365 жүйесіндегі Customer Engagement бағдарламаларының шешімі.</span><span class="sxs-lookup"><span data-stu-id="9c028-119">The Customer Card Add-in is a solution for customer engagement apps in Dynamics 365.</span></span> <span data-ttu-id="9c028-120">Шешімді орнату үшін AppSource жүйесіне өтіп, **Dynamics тұтынушы картасын** іздеңіз.</span><span class="sxs-lookup"><span data-stu-id="9c028-120">To install the solution, go to AppSource and search for **Dynamics Customer Card**.</span></span> <span data-ttu-id="9c028-121">[AppSource жүйесіндегі тұтынушы картасының қондырмасын](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) таңдап, **Оны қазір алу** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="9c028-121">Select the [Customer Card Add-in on AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) and select **Get It Now**.</span></span>

<span data-ttu-id="9c028-122">Шешімді орнату үшін Dynamics 365 бағдарламасына арналған әкімші тіркелгі деректерімен кіру қажет болуы мүмкін.</span><span class="sxs-lookup"><span data-stu-id="9c028-122">You may need to sign in with your admin credentials for the Dynamics 365 app to install the solution.</span></span>

<span data-ttu-id="9c028-123">Ортаңызға шешімді орнатуға біраз уақыт кетуі мүмкін.</span><span class="sxs-lookup"><span data-stu-id="9c028-123">It can take some time for the solution to be installed to your environment.</span></span>

## <a name="configure-the-customer-card-add-in"></a><span data-ttu-id="9c028-124">Тұтынушы картасының қондырмасын конфигурациялау</span><span class="sxs-lookup"><span data-stu-id="9c028-124">Configure the Customer Card Add-in</span></span>

1. <span data-ttu-id="9c028-125">Әкімші ретінде Dynamics 365 ішіндегі **Параметрлер** бөліміне өтіп, **Шешімдер** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="9c028-125">As an admin, go to the **Settings** section in Dynamics 365 and select **Solutions**.</span></span>

1. <span data-ttu-id="9c028-126">**Dynamics 365 Customer Insights тұтынушы картасының қондырмасы (алдын ала қарау)** шешімі үшін **Көрсетілетін атау** сілтемесін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="9c028-126">Select the **Display Name** link for the **Dynamics 365 Customer Insights Customer Card Add-in (Preview)** solution.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="9c028-127">![Көрсетілетін атын таңдау](media/select-display-name.png "Көрсетілетін атын таңдау")</span><span class="sxs-lookup"><span data-stu-id="9c028-127">![Select display name](media/select-display-name.png "Select display name")</span></span>

1. <span data-ttu-id="9c028-128">**Кіру** опциясын таңдап, Customer Insights бағдарламасын конфигурациялау үшін пайдаланатын әкімші тіркелгісінің деректерін енгізіңіз.</span><span class="sxs-lookup"><span data-stu-id="9c028-128">Select **Sign in** and enter the credentials for the admin account you use to configure Customer Insights.</span></span>

   > [!NOTE]
   > <span data-ttu-id="9c028-129">**Кіру** түймесін таңдаған кезде шолғыштың ашылмалы терезені құлыптау құралы аутентификация терезесін бұғаттамайтынын тексеріңіз.</span><span class="sxs-lookup"><span data-stu-id="9c028-129">Check that the browser pop-up blocker does not block the authentication window when you select the **Sign in** button.</span></span>

1. <span data-ttu-id="9c028-130">Деректерді алу керек Customer Insights ортасын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="9c028-130">Select the Customer Insights environment you want to fetch data from.</span></span>

1. <span data-ttu-id="9c028-131">Dynamics 365 бағдарламасында өрісті жазбалармен салыстыруды анықтаңыз.</span><span class="sxs-lookup"><span data-stu-id="9c028-131">Define the field mapping to records in the Dynamics 365 app.</span></span> <span data-ttu-id="9c028-132">Customer Insights ішіндегі деректерге байланысты сіз келесі опцияларды салыстыруды таңдай аласыз:</span><span class="sxs-lookup"><span data-stu-id="9c028-132">Depending on your data in Customer Insights you can choose to map the following options:</span></span>
   - <span data-ttu-id="9c028-133">Контактімен салыстыру үшін контакт нысанының идентификаторына сәйкес келетін тұтынушы нысанындағы өрісті таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="9c028-133">To map with a contact, select the field in the Customer entity that matches the ID of your contact entity.</span></span>
   - <span data-ttu-id="9c028-134">Тіркелгімен салыстыру үшін тіркелгі нысанының идентификаторына сәйкес келетін тұтынушы нысанындағы өрісті таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="9c028-134">To map with an account, select the field in the Customer entity that matches the ID of your account entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="9c028-135">![Контакт ИД өрісі](media/contact-id-field.png "Контакт ИД өрісі")</span><span class="sxs-lookup"><span data-stu-id="9c028-135">![Contact ID field](media/contact-id-field.png "Contact ID field")</span></span>

1. <span data-ttu-id="9c028-136">Параметрді сақтау үшін **Конфигурацияны сақтау** параметрлерін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="9c028-136">Select **Save configuration** to save the settings.</span></span>

1. <span data-ttu-id="9c028-137">Әрі қарай, пайдаланушылар тұтынушы картасын теңшей және көре алатындай етіп Dynamics 365 жүйесінде қауіпсіздік рөлдерін тағайындау керек.</span><span class="sxs-lookup"><span data-stu-id="9c028-137">Next, you need to assign security roles in Dynamics 365 so users can customize and see the customer card.</span></span> <span data-ttu-id="9c028-138">Dynamics 365 жүйесінде **Параметрлер** > **Қауіпсіздік** > **Пайдаланушылар** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="9c028-138">In Dynamics 365, go to **Settings** > **Security** > **Users**.</span></span> <span data-ttu-id="9c028-139">Пайдаланушы рөлдерін өзгерту үшін пайдаланушыларды таңдап, **Рөлдерді басқару** опциясын басыңыз.</span><span class="sxs-lookup"><span data-stu-id="9c028-139">Select the users to edit user roles and select **Manage roles**.</span></span>

1. <span data-ttu-id="9c028-140">**Customer Insights картасын баптаушы** рөлін бүкіл ұйымға арналған картада көрсетілген мазмұнды теңшейтін пайдаланушыларға белгілеңіз.</span><span class="sxs-lookup"><span data-stu-id="9c028-140">Assign the **Customer Insights Card Customizer** role to users who will customize the content shown on the card for the whole organization.</span></span>

## <a name="add-customer-card-controls-to-forms"></a><span data-ttu-id="9c028-141">Тұтынушы картасын пішіндерге қосу</span><span class="sxs-lookup"><span data-stu-id="9c028-141">Add Customer Card controls to forms</span></span>
  
1. <span data-ttu-id="9c028-142">Тұтынушы картасының басқару элементтерін контакт пішініне қосу үшін Dynamics 365 бағдарламасында **Параметрлер** > **Теңшелімдер** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="9c028-142">To add the Customer Card controls to your Contact form, go to the **Settings** > **Customizations** in Dynamics 365.</span></span>

1. <span data-ttu-id="9c028-143">**Жүйені теңшеу** пәрменін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="9c028-143">Select **Customize the System**.</span></span>

1. <span data-ttu-id="9c028-144">**Контакт** нысанын шолыңыз, оны кеңейтіп, **Пішіндер** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="9c028-144">Browse to the **Contact** entity, expand it and select **Forms**.</span></span>

1. <span data-ttu-id="9c028-145">Тұтынушы картасын басқару құралдарын қосу керек контакт пішінін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="9c028-145">Select the contact form to which you want to add the Customer Card controls.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="9c028-146">![Контакт пішінін таңдау](media/contact-active-forms.png "Контакт пішінін таңдау")</span><span class="sxs-lookup"><span data-stu-id="9c028-146">![Select Contact form](media/contact-active-forms.png "Select Contact form")</span></span>

1. <span data-ttu-id="9c028-147">Басқару құралын қосу үшін, пішін өңдегішінде кез келген **Өріс жетектеушісі** өрісін басқару құралы пайда болатын орынға сүйреңіз.</span><span class="sxs-lookup"><span data-stu-id="9c028-147">To add a control, in the form editor, drag any field from the **Field Explorer** to where you want the control to appear.</span></span>

1. <span data-ttu-id="9c028-148">Жаңа ғана қосқан пішіннен өрісті таңдап, **Сипаттарды өзгерту** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="9c028-148">Select the field on the form that you just added, and select **Change Properties**.</span></span>

1. <span data-ttu-id="9c028-149">**Басқару құралдары** қойыншасына өтіп, **Басқару құралын қосу** параметрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="9c028-149">Go to the **Controls** tab and select **Add Control**.</span></span> <span data-ttu-id="9c028-150">Қолжетімді басқару элементтерінің бірін таңдап, **Қосу** опциясын басыңыз.</span><span class="sxs-lookup"><span data-stu-id="9c028-150">Choose one of the available custom controls and select **Add**.</span></span>

1. <span data-ttu-id="9c028-151">**Өріс сипаттары** диалог терезесінде **Пішінде белгіні көрсету** құсбелгісін алыңыз.</span><span class="sxs-lookup"><span data-stu-id="9c028-151">In the **Field Properties** dialog, clear the **Display label on the form** check box.</span></span>

1. <span data-ttu-id="9c028-152">Басқаруға арналған **Веб** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="9c028-152">Select the **Web** option for the control.</span></span> <span data-ttu-id="9c028-153">Арттыруды басқару үшін **enrichmentType** өрісін теңшеу арқылы көрсету қажет арттыру түрін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="9c028-153">For the Enrichment control, select which enrichment type you want to display by configuring the **enrichmentType** field.</span></span> <span data-ttu-id="9c028-154">Әр арттыру түріне жеке арттыру бақылауын қосыңыз.</span><span class="sxs-lookup"><span data-stu-id="9c028-154">Add a separate enrichment control for each enrichment type.</span></span>

1. <span data-ttu-id="9c028-155">Жаңартылған контакт пішінін жариялау үшін **Сақтау** және **Жариялау** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="9c028-155">Select **Save** and **Publish** to publish the updated contact form.</span></span>

1. <span data-ttu-id="9c028-156">Жарияланған контакт пішініне өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="9c028-156">Go to the published contact form.</span></span> <span data-ttu-id="9c028-157">Жаңадан қосылған басқару элементін көресіз.</span><span class="sxs-lookup"><span data-stu-id="9c028-157">You'll see the newly added control.</span></span> <span data-ttu-id="9c028-158">Алғаш рет пайдаланған кезде жүйеге кіруіңіз керек болуы мүмкін.</span><span class="sxs-lookup"><span data-stu-id="9c028-158">You might need to sign in the first time you use it.</span></span>

1. <span data-ttu-id="9c028-159">Реттелетін басқару құралын көрсету керек мәліметті теңшеу үшін үстіңгі оң жақ бұрыштан өңдеу түймесін таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="9c028-159">To customize what you want to show on the custom control, select the edit button in the upper-right corner.</span></span>

## <a name="upgrade-customer-card-add-in"></a><span data-ttu-id="9c028-160">Тұтынушы картасының қондырмасын жаңарту</span><span class="sxs-lookup"><span data-stu-id="9c028-160">Upgrade Customer Card Add-in</span></span>
<span data-ttu-id="9c028-161">Тұтынушы картасы қондырмасы автоматты түрде жаңартылмайды.</span><span class="sxs-lookup"><span data-stu-id="9c028-161">The Customer Card Add-in doesn't upgrade automatically.</span></span> <span data-ttu-id="9c028-162">Соңғы нұсқаға жаңарту үшін қондырмасы орнатылған Dynamics 365 бағдарламасында осы процедураны орындаңыз.</span><span class="sxs-lookup"><span data-stu-id="9c028-162">To upgrade to the latest version, follow this procedure in the Dynamics 365 app that has the Add-in installed.</span></span>

1. <span data-ttu-id="9c028-163">Dynamics 365 бағдарламасында **Параметрлер** > **Реттеу** және **Шешімдер** тармағына өтіңіз.</span><span class="sxs-lookup"><span data-stu-id="9c028-163">In the Dynamics 365 app, go to **Settings** > **Customization** and select **Solutions**.</span></span>

1. <span data-ttu-id="9c028-164">Қондырмалар кестесінде **CustomerInsightsCustomerCard** дерегін іздеп, жолды таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="9c028-164">In the table of add-ins look for **CustomerInsightsCustomerCard** and select the row.</span></span>

1. <span data-ttu-id="9c028-165">Әрекет жолағында **Шешім жаңартуын қолдану** опциясын таңдаңыз.</span><span class="sxs-lookup"><span data-stu-id="9c028-165">Select the **Apply Solution Upgrade** in the action bar.</span></span>

   :::image type="content" source="media/customer-card-add-in-upgrade.png" alt-text="Шешімді Dynamics 365 бағдарламаларының реттеу аймағында жаңарту":::

1. <span data-ttu-id="9c028-167">Жаңарту процесін бастағаннан кейін жаңарту аяқталғанға дейін жүктеу индикаторын көресіз.</span><span class="sxs-lookup"><span data-stu-id="9c028-167">After starting the upgrade process, you'll see a loading indicator until the upgrade completes.</span></span> <span data-ttu-id="9c028-168">Егер жаңа нұсқасы болмаса, жаңарту кезінде қате туралы хабарлама көрсетіледі.</span><span class="sxs-lookup"><span data-stu-id="9c028-168">If there's no newer version, the upgrade will show an error message.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
