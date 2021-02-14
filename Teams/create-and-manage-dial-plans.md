---
title: Создание и использование абонентских групп
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: 7af17c94-5f8f-4452-ae1d-01f495b4dc94
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Calling Plans
- seo-marvel-apr2020
description: Узнайте, как создавать и управлять группами набора Windows PowerShell с помощью Центра администрирования Microsoft Teams или службы Windows PowerShell (наборы телефонных групп для звонков по СТАНП).
ms.openlocfilehash: 0655f81df9c8ce25368a281a7f5b3392f7fe6ec3
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814788"
---
# <a name="create-and-manage-dial-plans"></a><span data-ttu-id="9289f-103">Создание и использование абонентских групп</span><span class="sxs-lookup"><span data-stu-id="9289f-103">Create and manage dial plans</span></span>

<span data-ttu-id="9289f-104">После того как вы спланируйте наборы для своей организации и выясните все правила нормализации, которые необходимо создать для маршрутизации вызовов, вы можете при необходимости создать эти наборы.</span><span class="sxs-lookup"><span data-stu-id="9289f-104">After you plan the dial plans for your organization and figured out all the normalization rules that need to be created for call routing, you're ready to create the dial plans.</span></span> <span data-ttu-id="9289f-105">Вы можете использовать Центр администрирования Microsoft Teams или Windows PowerShell для создания телефонных групп и управления ими.</span><span class="sxs-lookup"><span data-stu-id="9289f-105">You can use the Microsoft Teams admin center or Windows PowerShell to create and manage dial plans.</span></span>  

## <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="9289f-106">С помощью Центра администрирования Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9289f-106">Using the Microsoft Teams admin center</span></span>

### <a name="create-a-dial-plan"></a><span data-ttu-id="9289f-107">Создание набора номера</span><span class="sxs-lookup"><span data-stu-id="9289f-107">Create a dial plan</span></span>

1. <span data-ttu-id="9289f-108">В левой области навигации Центра администрирования Microsoft Teams перейдите в группу  >  **голосового набора.**</span><span class="sxs-lookup"><span data-stu-id="9289f-108">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Dial plan**.</span></span>
2. <span data-ttu-id="9289f-109">Нажмите **кнопку**"Добавить" и введите имя и описание для набора номера.</span><span class="sxs-lookup"><span data-stu-id="9289f-109">Click **Add**, and then enter a name and description for the dial plan.</span></span>
    <span data-ttu-id="9289f-110">![Снимок экрана: страница добавления для создания набора номера](media/create-dial-plan.png)</span><span class="sxs-lookup"><span data-stu-id="9289f-110">![Screenshot showing the Add page for creating a dial plan](media/create-dial-plan.png)</span></span>
3. <span data-ttu-id="9289f-111">В **области сведений о** телефонной линии укажите внешний префикс набора, если пользователям нужно набрать одну или несколько цифр (например, 9), чтобы получить внешнюю линию.</span><span class="sxs-lookup"><span data-stu-id="9289f-111">Under **Dial plan details**, specify an external dialing prefix if users need to dial one or more additional leading digits (for example, 9) to get an external line.</span></span> <span data-ttu-id="9289f-112">Для этого выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="9289f-112">To do this:</span></span>
    1. <span data-ttu-id="9289f-113">В поле **внешнего префикса набора** номера введите внешний префикс набора номера.</span><span class="sxs-lookup"><span data-stu-id="9289f-113">In the **External dialing prefix** box, enter an external dialing prefix.</span></span> <span data-ttu-id="9289f-114">Префикс может быть не более четырех символов (#,\*и 0-9).</span><span class="sxs-lookup"><span data-stu-id="9289f-114">The prefix can be up to four characters (#,\*, and 0-9).</span></span>
    2. <span data-ttu-id="9289f-115">Включите **набор номера на оптимизированных устройствах.**</span><span class="sxs-lookup"><span data-stu-id="9289f-115">Turn on **Optimized device dialing**.</span></span> <span data-ttu-id="9289f-116">Если вы указали внешний префикс набора номера, необходимо также включить этот параметр, чтобы применить префикс, чтобы звонки можно было делать за пределами организации.</span><span class="sxs-lookup"><span data-stu-id="9289f-116">If you specify an external dialing prefix, you must also turn on this setting to apply the prefix so calls can be made outside your organization.</span></span>
4. <span data-ttu-id="9289f-117">В **правилах нормализации** настройте и соберите одно или несколько правил нормализации [для](what-are-dial-plans.md#normalization-rules) набора.</span><span class="sxs-lookup"><span data-stu-id="9289f-117">Under **Normalization rules**, configure and associate one or more [normalization rules](what-are-dial-plans.md#normalization-rules) for the dial plan.</span></span> <span data-ttu-id="9289f-118">С каждой телефонной планом должно быть связано хотя бы одно правило нормализации.</span><span class="sxs-lookup"><span data-stu-id="9289f-118">Each dial plan must have at least one normalization rule associated with it.</span></span>  <span data-ttu-id="9289f-119">Для этого сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="9289f-119">To do this, do one or more of the following:</span></span>
    - <span data-ttu-id="9289f-120">Чтобы создать новое правило нормализации и связать его с телефонной планом, нажмите кнопку "Добавить" **и** определите правило.</span><span class="sxs-lookup"><span data-stu-id="9289f-120">To create a new normalization rule and associate it with the dial plan, click **Add**, and then define the rule.</span></span>
    - <span data-ttu-id="9289f-121">Чтобы изменить правило нормализации, которое уже связано с ней, выберите его, щелкнув слева от его имени и нажав кнопку **"Изменить".**</span><span class="sxs-lookup"><span data-stu-id="9289f-121">To edit a normalization rule that's already associated with the dial plan, select the rule by clicking to the left of the rule name, and then click **Edit**.</span></span> <span data-ttu-id="9289f-122">Внести нужные изменения и нажмите кнопку **"Сохранить".**</span><span class="sxs-lookup"><span data-stu-id="9289f-122">Make the changes you want, and then click **Save**.</span></span>
    - <span data-ttu-id="9289f-123">Чтобы удалить правило нормализации из набора номера, выберите его, щелкнув слева от имени правила и нажав кнопку **"Удалить".**</span><span class="sxs-lookup"><span data-stu-id="9289f-123">To remove a normalization rule from the dial plan, select the rule by clicking to the left of the rule name, and then click **Remove**.</span></span>
5. <span data-ttu-id="9289f-124">Расположить правила нормализации в нужном порядке.</span><span class="sxs-lookup"><span data-stu-id="9289f-124">Arrange the normalization rules in the order that you want.</span></span> <span data-ttu-id="9289f-125">Нажмите **кнопку "Переместить** **вверх"** или "Вниз", чтобы изменить положение правил в списке.</span><span class="sxs-lookup"><span data-stu-id="9289f-125">Click **Move up** or **Move down** to change the position of rules in the list.</span></span>

    > [!NOTE]
    > <span data-ttu-id="9289f-126">Teams проходит по списку правил нормализации сверху вниз и использует первое правило, которое соответствует набратому номеру.</span><span class="sxs-lookup"><span data-stu-id="9289f-126">Teams traverses the list of normalization rules from the top down and uses the first rule that matches the dialed number.</span></span> <span data-ttu-id="9289f-127">Если настроена так, что набрано номер соответствует более чем одному правилу нормализации, убедитесь, что более строгие правила отсортировали над менее строгими.</span><span class="sxs-lookup"><span data-stu-id="9289f-127">If you set up a dial plan so that a dialed number can match more than one normalization rule, make sure the more restrictive rules are sorted above the less restrictive ones.</span></span>

6. <span data-ttu-id="9289f-128">Щелкните **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="9289f-128">Click **Save**.</span></span>
7. <span data-ttu-id="9289f-129">Если вы хотите проверить набережную, введите номер телефона в области "Тестирование набора номера" и нажмите кнопку **"Проверка".** </span><span class="sxs-lookup"><span data-stu-id="9289f-129">If you want to test the dial plan, under **Test dial plan**, enter a phone number, and then click **Test**.</span></span>

### <a name="edit-a-dial-plan"></a><span data-ttu-id="9289f-130">Изменение набора номера</span><span class="sxs-lookup"><span data-stu-id="9289f-130">Edit a dial plan</span></span>

1. <span data-ttu-id="9289f-131">В левой области навигации Центра администрирования Microsoft Teams перейдите в группу  >  **голосового набора.**</span><span class="sxs-lookup"><span data-stu-id="9289f-131">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Dial plan**.</span></span>
2. <span data-ttu-id="9289f-132">Выберите план набора, щелкнув слева от ее имени и нажав кнопку **"Изменить".**</span><span class="sxs-lookup"><span data-stu-id="9289f-132">Select the dial plan by clicking to the left of the dial plan name, and then click **Edit**.</span></span>
3. <span data-ttu-id="9289f-133">Внести нужные изменения и нажмите кнопку **"Сохранить".**</span><span class="sxs-lookup"><span data-stu-id="9289f-133">Make the changes that you want, and then click **Save**.</span></span>

### <a name="assign-a-dial-plan-to-users"></a><span data-ttu-id="9289f-134">Назначение пользователям набора номера</span><span class="sxs-lookup"><span data-stu-id="9289f-134">Assign a dial plan to users</span></span>

<span data-ttu-id="9289f-135">Вы назначаете план набора номера таким же образом, как и политики.</span><span class="sxs-lookup"><span data-stu-id="9289f-135">You assign a dial plan in the same way you assign policies.</span></span> [!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="using-powershell"></a><span data-ttu-id="9289f-136">С помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="9289f-136">Using PowerShell</span></span>
  
### <a name="verify-and-start-remote-powershell"></a><span data-ttu-id="9289f-137">Проверка и запуск удаленной powerShell</span><span class="sxs-lookup"><span data-stu-id="9289f-137">Verify and start Remote PowerShell</span></span>

 <span data-ttu-id="9289f-138">**Убедитесь, что вы работаете Windows PowerShell версии 3.0 или более поздней**</span><span class="sxs-lookup"><span data-stu-id="9289f-138">**Check that you are running Windows PowerShell version 3.0 or later**</span></span>
  
1. <span data-ttu-id="9289f-139">Чтобы убедиться, что у вас версия 3.0 или более **новая,** в меню "Пуск"  >  Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9289f-139">To verify that you're running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="9289f-140">Проверьте версию, введя в окне _Windows PowerShell_ команду **Get-Host**.</span><span class="sxs-lookup"><span data-stu-id="9289f-140">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="9289f-141">Если у вас нет версии 3.0 или более поздней, скачайте и установите обновления для Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9289f-141">If you don't have version 3.0 or later, download and install updates to Windows PowerShell.</span></span> <span data-ttu-id="9289f-142">Чтобы [скачать Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) и обновить Windows PowerShell до версии 4.0, см. Windows PowerShell 4.0.</span><span class="sxs-lookup"><span data-stu-id="9289f-142">See [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0.</span></span> <span data-ttu-id="9289f-143">Перезагрузите компьютер, когда вам будет предложено.</span><span class="sxs-lookup"><span data-stu-id="9289f-143">Restart your computer when you're prompted.</span></span>
    
4. <span data-ttu-id="9289f-144">Вам также потребуется установить модуль Windows PowerShell Skype для бизнеса Online, который позволяет создавать удаленные сеансы Windows PowerShell подключения к Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="9289f-144">You'll also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span> <span data-ttu-id="9289f-145">Вы можете скачать этот модуль, который поддерживается только на [](https://go.microsoft.com/fwlink/?LinkId=294688)64-Windows PowerShell-компьютерах.</span><span class="sxs-lookup"><span data-stu-id="9289f-145">You can download this module, which is supported only on 64-bit computers, at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688).</span></span> <span data-ttu-id="9289f-146">Перезагрузите компьютер, если будет предложено.</span><span class="sxs-lookup"><span data-stu-id="9289f-146">Restart your computer if you're prompted.</span></span>
    
<span data-ttu-id="9289f-147">Подробнее см. в одном окне подключения к всем службам [Microsoft 365 Windows PowerShell Office 365.](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window)</span><span class="sxs-lookup"><span data-stu-id="9289f-147">To learn more, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span></span>
  
 <span data-ttu-id="9289f-148">**Запуск сеанса Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="9289f-148">**Start a Windows PowerShell session**</span></span>
  
1. <span data-ttu-id="9289f-149">Нажмите **кнопку**  >  **"Windows PowerShell".**</span><span class="sxs-lookup"><span data-stu-id="9289f-149">Click **Start** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="9289f-150">В **окне Windows PowerShell** подключения к Microsoft 365 или Office 365, вы работаете:</span><span class="sxs-lookup"><span data-stu-id="9289f-150">In the **Windows PowerShell** window, connect to Microsoft 365 or Office 365 by running:</span></span>
    
 
    > [!NOTE]
    > <span data-ttu-id="9289f-151">Соединитель Skype для бизнеса Online сейчас является частью последнего модуля Teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9289f-151">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
    >
    > <span data-ttu-id="9289f-152">Если вы используете последний общедоступный выпуск [Teams PowerShell,](https://www.powershellgallery.com/packages/MicrosoftTeams/)вам не нужно устанавливать соединитель Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="9289f-152">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

    ```PowerShell
   Import-Module -Name MicrosoftTeams
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
    ```
  
### <a name="create-and-manage-your-dial-plans"></a><span data-ttu-id="9289f-153">Создание телефонных планов и управление ими</span><span class="sxs-lookup"><span data-stu-id="9289f-153">Create and manage your dial plans</span></span>

<span data-ttu-id="9289f-154">Создание абонентских групп клиентов и управление ими можно осуществлять с помощью одиночного командлета или сценария PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9289f-154">You can either use a single cmdlet or a PowerShell script to create and manage tenant dial plans.</span></span>
  
#### <a name="using-single-cmdlets"></a><span data-ttu-id="9289f-155">С помощью одиночного командлета</span><span class="sxs-lookup"><span data-stu-id="9289f-155">Using single cmdlets</span></span>

- <span data-ttu-id="9289f-156">Чтобы создать новую телефонную план, запустите ную экономию:</span><span class="sxs-lookup"><span data-stu-id="9289f-156">To create a new dial plan, run:</span></span>
    
  ```PowerShell
  New-CsTenantDialPlan -Identity RedmondDialPlan -Description "Dial Plan for Redmond" -NormalizationRules <pslistmodifier> -ExternalAccessPrefix 9 -SimpleName "Dial-Plan-for-Redmond"
  ```

    <span data-ttu-id="9289f-157">Другие примеры и параметры см. в разделе [New-CsTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/new-cstenantdialplan).</span><span class="sxs-lookup"><span data-stu-id="9289f-157">For other examples and parameters, see [New-CsTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/new-cstenantdialplan).</span></span>
    
- <span data-ttu-id="9289f-158">Чтобы изменить параметры существующей телефонной программы, запустите параметров:</span><span class="sxs-lookup"><span data-stu-id="9289f-158">To edit the settings of an existing dial plan, run:</span></span>
    
  ```PowerShell
  Set-CsTenantDialPlan -Identity RedmondDialPlan  -NormalizationRules <pslistmodifier> -ExternalAccessPrefix 9
    -SimpleName "Dial-Plan-for-Redmond"
  ```

    <span data-ttu-id="9289f-159">Другие примеры и параметры см. в разделе [Set-CsTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/set-cstenantdialplan).</span><span class="sxs-lookup"><span data-stu-id="9289f-159">For other examples and parameters, see [Set-CsTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/set-cstenantdialplan).</span></span>
    
- <span data-ttu-id="9289f-160">Чтобы добавить пользователей в абонентскую группу, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="9289f-160">To add users to a dial plan, run:</span></span>
    
  ```PowerShell
  Grant-CsTenantDialPlan -Identity amos.marble@contoso.com -PolicyName RedmondDialPlan
  ```

    <span data-ttu-id="9289f-161">Другие примеры и параметры см. в разделе [Grant-CsTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-cstenantdialplan).</span><span class="sxs-lookup"><span data-stu-id="9289f-161">For other examples and parameters, see [Grant-CsTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-cstenantdialplan).</span></span>
    
- <span data-ttu-id="9289f-162">Чтобы просмотреть параметры абонентской группы, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="9289f-162">To view the settings on a dial plan, run:</span></span>
    
  ```PowerShell
  Get-CsTenantDialPlan -Identity RedmondDialPlan
  ```

    <span data-ttu-id="9289f-163">Другие примеры и параметры см. в разделе [Get-CsTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/get-cstenantdialplan?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="9289f-163">For other examples and parameters, see [Get-CsTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/get-cstenantdialplan?view=skype-ps).</span></span>
    
- <span data-ttu-id="9289f-164">Чтобы удалить абонентскую группу, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="9289f-164">To delete a dial plan, run:</span></span>
    
  ```PowerShell
  Remove-CsTenantDialPlan -Identity RedmondDialPlan -force
  ```

    <span data-ttu-id="9289f-165">Другие примеры и параметры см. в разделе [Remove-CsTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/remove-cstenantdialplan?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="9289f-165">For other examples and parameters, see [Remove-CsTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/remove-cstenantdialplan?view=skype-ps).</span></span>
    
- <span data-ttu-id="9289f-166">Чтобы просмотреть параметры действующей абонентской группы, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="9289f-166">To see the settings of the effective dial plan, run:</span></span>
    
  ```PowerShell
  Get-CsEffectiveTenantDialPlan -Identity amos.marble@contoso.com
  ```

    <span data-ttu-id="9289f-167">Другие примеры и параметры см. в разделе [Get-CsEffectiveTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/get-cseffectivetenantdialplan).</span><span class="sxs-lookup"><span data-stu-id="9289f-167">For other examples and parameters, see [Get-CsEffectiveTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/get-cseffectivetenantdialplan).</span></span>
    
- <span data-ttu-id="9289f-168">Для проверки действующих параметров абонентской группы запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="9289f-168">To test the effective settings of a dial plan, run:</span></span>
    
  ```PowerShell
  Test-CsEffectiveTenantDialPlan -DialedNumber 14255550199 -Identity amos.marble@contoso.com
  ```

    <span data-ttu-id="9289f-169">Другие примеры и параметры см. в разделе [Test-CsEffectiveTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/test-cseffectivetenantdialplan?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="9289f-169">For other examples and parameters, see [Test-CsEffectiveTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/test-cseffectivetenantdialplan?view=skype-ps).</span></span>
    
#### <a name="using-a-powershell-script"></a><span data-ttu-id="9289f-170">С помощью скрипта PowerShell</span><span class="sxs-lookup"><span data-stu-id="9289f-170">Using a PowerShell script</span></span>

<span data-ttu-id="9289f-171">Чтобы удалить правило нормализации, связанное с клиентской телефонной планом, не нужно сначала удалять ее:</span><span class="sxs-lookup"><span data-stu-id="9289f-171">Run this to delete a normalization rule that is associated with a tenant dial plan without needing to delete the tenant dial plan first:</span></span>
```PowerShell
$b1=New-CsVoiceNormalizationRule -Identity Global/NR4 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{add=$b1}
(Get-CsTenantDialPlan -Identity RedmondDialPlan).NormalizationRules
$b2=New-CsVoiceNormalizationRule -Identity Global/NR4 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{remove=$b2}
```
<span data-ttu-id="9289f-172">Запустите эту команду для добавления следующего правила нормализации к существующему клиенту абонентской группы с именем RedmondDialPlan.</span><span class="sxs-lookup"><span data-stu-id="9289f-172">Run this to add the following normalization rule to the existing tenant dial plan named RedmondDialPlan.</span></span>
```PowerShell
$nr1=New-CsVoiceNormalizationRule -Parent Global -Description 'Organization extension dialing' -Pattern '^(\\d{3})$' -Translation '+14255551$1' -Name NR1 -IsInternalExtension $false -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{add=$nr1}
```
<span data-ttu-id="9289f-173">Запустите эту команду для удаления следующего правила нормализации из существующего клиента абонентской группы с именем RedmondDialPlan.</span><span class="sxs-lookup"><span data-stu-id="9289f-173">Run this to remove the following normalization rule from the existing tenant dial plan named RedmondDialPlan.</span></span>
```PowerShell
$nr1=New-CsVoiceNormalizationRule -Parent Global/NR1 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{remove=$nr1}
```

<span data-ttu-id="9289f-174">Запустите следующую команду, когда вы хотите также проверить существующие правила нормализации, определить, какое из них нужно удалить, а затем использовать его индекс для удаления.</span><span class="sxs-lookup"><span data-stu-id="9289f-174">Run the following when you want to also examine the existing normalization rules, determine which one you want to delete, and then use its index to remove it.</span></span> <span data-ttu-id="9289f-175">Массив правил нормализации начинается с индекса 0.</span><span class="sxs-lookup"><span data-stu-id="9289f-175">The array of normalization rules starts with index 0.</span></span> <span data-ttu-id="9289f-176">Если мы хотим удалить з-х цифровое правило нормализации, индекс будет 1.</span><span class="sxs-lookup"><span data-stu-id="9289f-176">We would like to remove the 3-digit normalization rule, so that is index 1.</span></span>
  
```PowerShell
Get-CsTenantDialPlan RedmondDialPlan).NormalizationRules
Description         : 4-digit
Pattern             : ^(\\d{4})$
Translation         : +1426666$1
Name                : NR2
IsInternalExtension : False

Description         : 3-digit
Pattern             : ^(\\d{3})$
Translation         : +14255551$1
Name                : NR12
IsInternalExtension : False

$nr1=(Get-CsTenantDialPlan RedmondDialPlan).NormalizationRules[1]
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{remove=$nr1}
```

<span data-ttu-id="9289f-177">Запустите эту команду для поиска всех пользователей, которым была присвоена абонентская группа клиента RedmondDialPlan.</span><span class="sxs-lookup"><span data-stu-id="9289f-177">Run this to find all users who have been granted the RedmondDialPlan tenant dial plan.</span></span>
  
```PowerShell
Get-CsOnlineUser | Where-Object {$_.TenantDialPlan -eq "RedmondDialPlan"}
```

<span data-ttu-id="9289f-178">Запустите этот запуск, чтобы удалить все назначенные TenantDialPlan для всех пользователей, у которых есть sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="9289f-178">Run this to remove any assigned TenantDialPlan from all users who have a HostingProvider of sipfed.online.lync.com.</span></span>
```PowerShell
Get-CsOnlineUser -Filter {HostingProvider -eq "sipfed.online.lync.com"} | Grant-CsTenantDialPlan -policyname $null
```

<span data-ttu-id="9289f-179">Запустите эту команду для добавления существующей локальной абонентской группы с именем OPDP1 в качестве абонентской группы клиента для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="9289f-179">Run these to add the existing on-premises dial plan named OPDP1 as a tenant dial plan for your organization.</span></span> <span data-ttu-id="9289f-180">Необходимо сначала сохранить локальную абонентскую группу в XML-файл, а затем использовать ее для создания новой абонентской группы клиента.</span><span class="sxs-lookup"><span data-stu-id="9289f-180">You need to first save the on-premises dial plan to an .xml file, and then use it to create the new tenant dial plan.</span></span>
  
<span data-ttu-id="9289f-181">Запустите эту команду для сохранения локальной абонентской группы в XML-файл.</span><span class="sxs-lookup"><span data-stu-id="9289f-181">Run this to save the on-premises dial plan to the .xml file.</span></span>
  
```PowerShell
$DPName = "OPDP1"
$DPFileName = "dialplan.xml"
Get-CsDialplan $DPName | Export-Clixml $DPFileName
```

<span data-ttu-id="9289f-182">Запустите эту команду для создания новой абонентской группы клиента.</span><span class="sxs-lookup"><span data-stu-id="9289f-182">Run this to create the new tenant dial plan.</span></span>
  
```PowerShell
$DPFileName = "dialplan.xml"
$dp = Import-Clixml $DPFileName
$NormRules = @()
ForEach($nr in $dp.NormalizationRules)
{
 $id1 = "Global/" + $nr.Name
 $nr2 = New-CsVoiceNormalizationRule -Identity $id1 -Description $nr.Description -Pattern $nr.Pattern -Translation $nr.Translation -IsInternalExtension $nr.IsInternalExtension -InMemory
 $NormRules += $nr2
}
New-CsTenantDialPlan -Identity $dp.SimpleName -ExternalAccessPrefix $dp.ExternalAccessPrefix -Description $dp.Description -OptimizeDeviceDialing $dp.OptimizeDeviceDialing -SimpleName $dp.SimpleName -NormalizationRules $NormRules
```
    
## <a name="related-topics"></a><span data-ttu-id="9289f-183">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="9289f-183">Related topics</span></span>

- [<span data-ttu-id="9289f-184">Что такое абонентские группы?</span><span class="sxs-lookup"><span data-stu-id="9289f-184">What are dial plans?</span></span>](what-are-dial-plans.md)
- [<span data-ttu-id="9289f-185">Общие вопросы по передаче номеров телефонов</span><span class="sxs-lookup"><span data-stu-id="9289f-185">Transferring phone numbers common questions</span></span>](transferring-phone-numbers-common-questions.md)
- [<span data-ttu-id="9289f-186">Типы номеров телефонов, используемые в планах звонков</span><span class="sxs-lookup"><span data-stu-id="9289f-186">Different kinds of phone numbers used for Calling Plans</span></span>](different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [<span data-ttu-id="9289f-187">Управление номерами телефонов организации</span><span class="sxs-lookup"><span data-stu-id="9289f-187">Manage phone numbers for your organization</span></span>](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)
- [<span data-ttu-id="9289f-188">Условия и положения, распространяющиеся на экстренные вызовы</span><span class="sxs-lookup"><span data-stu-id="9289f-188">Emergency calling terms and conditions</span></span>](emergency-calling-terms-and-conditions.md)
- <span data-ttu-id="9289f-189">[Метка заявление об отказе для экстренных вызовов](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="9289f-189">[Emergency calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>
- [<span data-ttu-id="9289f-190">Обзор PowerShell в Teams</span><span class="sxs-lookup"><span data-stu-id="9289f-190">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
