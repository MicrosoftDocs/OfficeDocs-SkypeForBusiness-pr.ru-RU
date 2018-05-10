---
title: Развертывание телефонов для приложения Skype для бизнеса Online
description: Познакомьтесь с действиями развертывания для получения микропрограммы, при необходимости обновите ее, назначение лицензий и настройка параметров для телефонов общего пользования.
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: wasseemh
ms.date: 01/22/2018
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
- Strat_SB_PSTN
ms.openlocfilehash: 453f9db6a022e924406594c567ea564b10f58694
ms.sourcegitcommit: 7ec95ea34422e635661f3659bbc43a7a3484ff99
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/09/2018
---
## <a name="common-area-phones"></a><span data-ttu-id="6e0f7-103">Региональные телефоны</span><span class="sxs-lookup"><span data-stu-id="6e0f7-103">Common Area Phones</span></span>
<span data-ttu-id="6e0f7-104">Телефон общего пользования или БОЛТЫ, обычно размещаются в общей области и не связанные с отдельным пользователем.</span><span class="sxs-lookup"><span data-stu-id="6e0f7-104">A common area phone, or CAP, is typically placed in a shared area and not associated with an individual user.</span></span> <span data-ttu-id="6e0f7-105">Например, телефонов области приема, телефона помещения двери телефон или собрания, CAPs настраиваются как устройства, а не пользователей и автоматического входа в сеть.</span><span class="sxs-lookup"><span data-stu-id="6e0f7-105">For example, a reception area phone, door phone or meeting room phone, CAPs are set up as devices rather than users and automatically  sign in to the network.</span></span> <span data-ttu-id="6e0f7-106">В приведенные ниже действия мы поможет Настройка учетной записи для телефонной системой Microsoft с вызова планы и разверните узел.</span><span class="sxs-lookup"><span data-stu-id="6e0f7-106">In the steps below, we’ll help you set up an account for Microsoft Phone System with Calling Plans and then deploy a CAP.</span></span>

## <a name="prerequisites-for-common-area-phones"></a><span data-ttu-id="6e0f7-107">Необходимые условия для телефонов общего пользования</span><span class="sxs-lookup"><span data-stu-id="6e0f7-107">Prerequisites for Common Area Phones</span></span>

<span data-ttu-id="6e0f7-108">Убедитесь, что у вас есть следующие:</span><span class="sxs-lookup"><span data-stu-id="6e0f7-108">Confirm that you have the following:</span></span>

    - <span data-ttu-id="6e0f7-109">Купить телефон общего пользования SKU</span><span class="sxs-lookup"><span data-stu-id="6e0f7-109">Purchased Common Area Phone SKU</span></span> 
    - <span data-ttu-id="6e0f7-110">Обновление микропрограммы (видеть поддерживается встроенного по в разделеhttps://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online)</span><span class="sxs-lookup"><span data-stu-id="6e0f7-110">Updated firmware (See Supported Firmware in topichttps://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online)</span></span>
    - <span data-ttu-id="6e0f7-111">Утвержденная (Просмотр списка на телефоныhttps://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/deploying-skype-for-business-online-phones)</span><span class="sxs-lookup"><span data-stu-id="6e0f7-111">Approved  phones (view the list at https://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/deploying-skype-for-business-online-phones)</span></span> 


## <a name="check-the-firmware-for-your-phone"></a><span data-ttu-id="6e0f7-112">Проверьте микропрограммы для своего телефона</span><span class="sxs-lookup"><span data-stu-id="6e0f7-112">Check the firmware for your phone</span></span>
- <span data-ttu-id="6e0f7-113">**Телефоны Polycom VVX**  выберите **Settings** > **Status** > **Platform** > **Application** > **Main** (Параметры > Состояние > Платформа > Приложение > Основные).</span><span class="sxs-lookup"><span data-stu-id="6e0f7-113">**Polycom VVX phones**, go to **Settings** > **Status** > **Platform** > **Application** > **Main**.</span></span>
- <span data-ttu-id="6e0f7-114">**Телефоны Yealink**  выберите пункт **Status** (Состояние) на главном экране телефона.</span><span class="sxs-lookup"><span data-stu-id="6e0f7-114">**Yealink phones**, go to **Status** on the main phone screen.</span></span>
- <span data-ttu-id="6e0f7-115">**Телефоны AudioCodes**  выберите **Menu** > **Device Status** > **Firmware version** (Меню > Состояние устройства > Версия встроенного ПО).</span><span class="sxs-lookup"><span data-stu-id="6e0f7-115">**AudioCodes phones**, go to **Menu** > **Device Status** > **Firmware version** from the start screen.</span></span> 
- <span data-ttu-id="6e0f7-116">**Телефоны Lync Phone Edition (LPE)**  выберите **Menu** > **System Information** (Меню > Сведения о системе) на начальном экране.</span><span class="sxs-lookup"><span data-stu-id="6e0f7-116">**Lync Phone Edition (LPE) phones**, go to **Menu** > **System Information** from the start screen.</span></span>

<span data-ttu-id="6e0f7-117">Служба Skype для бизнеса управляет обновлением встроенного ПО.</span><span class="sxs-lookup"><span data-stu-id="6e0f7-117">Firmware updates are managed by the Skype for Business Service.</span></span> <span data-ttu-id="6e0f7-118">Обновление для каждого сертифицированного телефона Skype для бизнеса загружается на сервер обновлений Skype для бизнеса, а на всех устройствах обновление включено по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="6e0f7-118">Every Skype for Business certified phone's firmware is uploaded to the Skype for Business Update server, and device update is enabled on all phones by default.</span></span> 

<span data-ttu-id="6e0f7-119">В зависимости от периода неактивности телефона и интервалов опроса на телефоны автоматически загружаются и устанавливаются последние версии сертифицированных сборок.</span><span class="sxs-lookup"><span data-stu-id="6e0f7-119">Depending on the inactivity time on the phone and polling intervals, phones will automatically download and install the latest certified builds.</span></span> <span data-ttu-id="6e0f7-120">Чтобы отключить обновление устройства, выполните командлет [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx) и присвойте параметру _EnableDeviceUpdate_ значение `false`.</span><span class="sxs-lookup"><span data-stu-id="6e0f7-120">You can disable the device update settings by using the [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx) cmdlet and setting the _EnableDeviceUpdate_ parameter to `false`.</span></span>

## <a name="create-cap"></a><span data-ttu-id="6e0f7-121">Создание Политики</span><span class="sxs-lookup"><span data-stu-id="6e0f7-121">Create CAP</span></span>
<span data-ttu-id="6e0f7-122">Создайте ограничение, настроив параметры перед настройкой физического телефона.</span><span class="sxs-lookup"><span data-stu-id="6e0f7-122">You create the CAP by configuring the settings before you set up the physical phone.</span></span>

#### <a name="purchase-the-common-area-phone-sku"></a><span data-ttu-id="6e0f7-123">Приобрести телефон общего пользования SKU.</span><span class="sxs-lookup"><span data-stu-id="6e0f7-123">Purchase the Common Area Phone SKU.</span></span> 
    In the Office 365 admin center, go to **Billing > Purchase Services**, and add **Common Area Phone**.

#### <a name="set-up-the-common-area-phone-----this-section-could-use-a-screen-shot--"></a><span data-ttu-id="6e0f7-124">Настройка телефона общего пользования<!-- this section could use a screen shot--></span><span class="sxs-lookup"><span data-stu-id="6e0f7-124">Set up the common area phone  <!-- this section could use a screen shot--></span></span>

<span data-ttu-id="6e0f7-125">**Создание пользователя**</span><span class="sxs-lookup"><span data-stu-id="6e0f7-125">**Create user**</span></span> 
1. <span data-ttu-id="6e0f7-126">Назначение телефона общего пользования SKU</span><span class="sxs-lookup"><span data-stu-id="6e0f7-126">Assign Common Area Phone SKU</span></span>
2. <span data-ttu-id="6e0f7-127">Назначьте вызов планирование (при использовании с телефонной системой Microsoft с вызова планы).</span><span class="sxs-lookup"><span data-stu-id="6e0f7-127">Assign Calling Plan (if using Microsoft Phone System with Calling Plans).</span></span> 
3. <span data-ttu-id="6e0f7-128">Назначение доступно телефонный номер в Скайп по центру администрирования бизнес и запросить новый номер телефона.</span><span class="sxs-lookup"><span data-stu-id="6e0f7-128">Assign an available telephone number in the Skype for Business Admin Center, or request a new telephone number.</span></span>

<span data-ttu-id="6e0f7-129">**Создание нового пользователя**</span><span class="sxs-lookup"><span data-stu-id="6e0f7-129">**Create New User**</span></span>

1. <span data-ttu-id="6e0f7-130">На левой панели подготовки у вас есть параметр, чтобы ввести имя и фамилию (например, для приема Main).</span><span class="sxs-lookup"><span data-stu-id="6e0f7-130">In the provisioning pane, you have an option to enter a first and last name (for example, Reception Main).</span></span>
2. <span data-ttu-id="6e0f7-131">Введите отображаемое имя (обязательно), например, «прием Main».</span><span class="sxs-lookup"><span data-stu-id="6e0f7-131">Enter a display name (required), for example, "Main Reception."</span></span>
3. <span data-ttu-id="6e0f7-132">Введите имя пользователя (обязательно), например «MainReception» @» домен» (имя компании или enterprise)</span><span class="sxs-lookup"><span data-stu-id="6e0f7-132">Enter a username (required), for example “MainReception” @” domain” (company or enterprise name)</span></span>
4. <span data-ttu-id="6e0f7-133">Введите расположение (Страна).</span><span class="sxs-lookup"><span data-stu-id="6e0f7-133">Enter Location (country).</span></span>

<span data-ttu-id="6e0f7-134">**Назначение телефона общего пользования SKU** В центре администрирования Office 365 перейдите в раздел **выставления счетов > приобрести службы** и добавьте **Телефон общего пользования**</span><span class="sxs-lookup"><span data-stu-id="6e0f7-134">**Assign Common Area Phone SKU** In the Office 365 admin center, go to **Billing > Purchase Services** and add **Common Area Phone**</span></span>

<span data-ttu-id="6e0f7-135">**Назначьте план вызова в БОЛТЫ SKU**</span><span class="sxs-lookup"><span data-stu-id="6e0f7-135">**Assign Calling Plan in CAP SKU**</span></span>

1. <span data-ttu-id="6e0f7-136">Выберите вызов планируете включить на телефоне.</span><span class="sxs-lookup"><span data-stu-id="6e0f7-136">Select a Calling Plan to enable the phone.</span></span> 
2. <span data-ttu-id="6e0f7-137">Добавьте ограничения для поддержки телефонной системой и Скайп для бизнеса Online (план 2) в SKU БОЛТЫ.</span><span class="sxs-lookup"><span data-stu-id="6e0f7-137">Add the CAP to enable the Phone System and Skype for Business Online Plan 2 in the CAP SKU.</span></span> <!-- odd order for step -->

<span data-ttu-id="6e0f7-138">**Назначить телефонный номер**</span><span class="sxs-lookup"><span data-stu-id="6e0f7-138">**Assign a telephone number**</span></span>
1. <span data-ttu-id="6e0f7-139">Поиск доступных телефонных номеров в списке **голосовой связи > телефонных номеров**.</span><span class="sxs-lookup"><span data-stu-id="6e0f7-139">Check for available phone numbers under **Voice > Phone Numbers**.</span></span>
2. <span data-ttu-id="6e0f7-140">Выберите номер из списка доступных номеров телефонов.</span><span class="sxs-lookup"><span data-stu-id="6e0f7-140">Select a number from the available list of phone numbers number.</span></span>
3. <span data-ttu-id="6e0f7-141">Подтвердите выбор, выбрав **голосовой связи** и **Номера телефонов**.</span><span class="sxs-lookup"><span data-stu-id="6e0f7-141">Confirm your selection by selecting **Voice** and **Phone Numbers**.</span></span>

    ><span data-ttu-id="6e0f7-142">[Примечание] Пользователям голосовой связи отображаются только при наличии телефонной системой лицензия применяется, несмотря на то, что даже после применения, может потребоваться время обновления.</span><span class="sxs-lookup"><span data-stu-id="6e0f7-142">[Note] Voice users only show if they have the Phone System licence applied, although even after applying, it can take time to refresh.</span></span> <span data-ttu-id="6e0f7-143">Иногда повторного открытия Скайп для администрирования бизнес центр помогает.</span><span class="sxs-lookup"><span data-stu-id="6e0f7-143">Sometime reopening Skype for Business Admin center helps.</span></span>
    
## <a name="configure-phone"></a><span data-ttu-id="6e0f7-144">Настройка телефона</span><span class="sxs-lookup"><span data-stu-id="6e0f7-144">Configure Phone</span></span>

<span data-ttu-id="6e0f7-145">**Подготовка физических телефоны**</span><span class="sxs-lookup"><span data-stu-id="6e0f7-145">**Prepare the physical phones**</span></span> 

<span data-ttu-id="6e0f7-146">Выбранные телефон должен иметь режим телефон общего пользования.</span><span class="sxs-lookup"><span data-stu-id="6e0f7-146">Your selected phone needs to have the Common Area Phone mode.</span></span> 

<span data-ttu-id="6e0f7-147">***Телефон Polycom VVX пример***</span><span class="sxs-lookup"><span data-stu-id="6e0f7-147">***Example Polycom VVX phone***</span></span>

<span data-ttu-id="6e0f7-148">Общие области телефона режим включите на Polycom VVX, выполнив следующие действия:</span><span class="sxs-lookup"><span data-stu-id="6e0f7-148">Enable Common Area Phone Mode on Polycom VVX by following these steps:</span></span>
1. <span data-ttu-id="6e0f7-149">В браузере используйте веб-интерфейс для перехода в режим ограничения на VVX</span><span class="sxs-lookup"><span data-stu-id="6e0f7-149">In your browser, use the web interface to enable CAP mode on the VVX</span></span>
2. <span data-ttu-id="6e0f7-150">Перейдите к **параметру** и в Скайп для параметра бизнеса, выберите **Телефон общего пользования**.</span><span class="sxs-lookup"><span data-stu-id="6e0f7-150">Go to **Setting**  and in the Skype for Business Setting option, select **Common Area Phone**.</span></span>
3. <span data-ttu-id="6e0f7-151">Нажмите кнопку **Сохранить** для сохранения параметров конфигурации.</span><span class="sxs-lookup"><span data-stu-id="6e0f7-151">Click **Save** to save your configuration settings.</span></span>

<span data-ttu-id="6e0f7-152">Теперь, когда включен режим БОЛТЫ телефона, настройте телефон, с помощью телефона отображаются.</span><span class="sxs-lookup"><span data-stu-id="6e0f7-152">Now that the CAP phone mode is enabled, set up the phone using the phone's display.</span></span>

1. <span data-ttu-id="6e0f7-153">В диалоговом окне настройки нажмите кнопку **Дополнительно**.</span><span class="sxs-lookup"><span data-stu-id="6e0f7-153">In the Settings, select **Advanced**.</span></span>
2. <span data-ttu-id="6e0f7-154">Введите пароль.</span><span class="sxs-lookup"><span data-stu-id="6e0f7-154">Enter password.</span></span>
3. <span data-ttu-id="6e0f7-155">В параметрах администрирования выберите **Общие параметры телефона зоны**.</span><span class="sxs-lookup"><span data-stu-id="6e0f7-155">In Administration settings, select **Common Area Phone Settings**.</span></span>
4. <span data-ttu-id="6e0f7-156">Включить телефон общего пользования и БОЛТЫ администрирования</span><span class="sxs-lookup"><span data-stu-id="6e0f7-156">Enable Common Area Phone and CAP Admin</span></span>
5. <span data-ttu-id="6e0f7-157">Выберите пункт **Сохранить настройки**.</span><span class="sxs-lookup"><span data-stu-id="6e0f7-157">Select **Save Config**.</span></span>

<span data-ttu-id="6e0f7-158">Телефон готов подготовить к работе, который будет выполняться при входе на начальном экране.</span><span class="sxs-lookup"><span data-stu-id="6e0f7-158">Your phone is ready to be provisioned, which you'll do when you sign in on the home screen.</span></span>

1. <span data-ttu-id="6e0f7-159">Вход, выбрав **Параметры > функции > Скайп для бизнеса.**</span><span class="sxs-lookup"><span data-stu-id="6e0f7-159">Sign in by selecting **settings > features > Skype for Business.**</span></span>
2. <span data-ttu-id="6e0f7-160">Выберите учетные данные пользователя и выберите select **web учетное (узел)** для генерации кода.</span><span class="sxs-lookup"><span data-stu-id="6e0f7-160">Select User Credentials, and select select **web sign-in (CAP)** to generate a code..</span></span>
3. <span data-ttu-id="6e0f7-161">Последовательно выберите пункты подготовки портала http://aka.ms/skypecapи войдите в качестве **администратора**.</span><span class="sxs-lookup"><span data-stu-id="6e0f7-161">Go to the provisioning portal http://aka.ms/skypecap, and sign in as **admin**.</span></span>
4. <span data-ttu-id="6e0f7-162">Введите отображаемое имя (например, для приема Main) для просмотра вашего БОЛТЫ.</span><span class="sxs-lookup"><span data-stu-id="6e0f7-162">Enter display name (for example, Main Reception) to view your CAP.</span></span>

><span data-ttu-id="6e0f7-163">[Примечание] Если «Поиск для телефонов общего пользования только» — этот флажок установлен, снимите флажок и выполните поиск еще раз.</span><span class="sxs-lookup"><span data-stu-id="6e0f7-163">[Note] If “Search for Common Area Phones only” is checked, clear the checkbox and search again.</span></span>

5. <span data-ttu-id="6e0f7-164">В окне код связывания введите код, отображаемые на телефоне и щелкните **подготовить к работе**.</span><span class="sxs-lookup"><span data-stu-id="6e0f7-164">In the pairing code window, enter the code displayed on the phone and click **Provision**.</span></span>

<span data-ttu-id="6e0f7-165">WHT последнем шаге телефон должен автоматический вход в систему.</span><span class="sxs-lookup"><span data-stu-id="6e0f7-165">Wht this last step, the phone should sign in automatically.</span></span>

<span data-ttu-id="6e0f7-166">Дополнительные сведения о доступных телефонов представлены в [ ](https://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/deploying-skype-for-business-online-phones).</span><span class="sxs-lookup"><span data-stu-id="6e0f7-166">Learn more about available phones at [](https://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/deploying-skype-for-business-online-phones).</span></span>


