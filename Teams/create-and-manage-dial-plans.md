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
description: Узнайте, как использовать центр администрирования Microsoft Teams или центр Windows PowerShell для создания телефонных планов (наборных групп звонков по ЗВОНКОВ) и управления ими.
ms.openlocfilehash: f94c847f5c75e793856c0975678e2806629e2dcd
ms.sourcegitcommit: 32e3bb588abcbeded2d885483384c06706b280eb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2021
ms.locfileid: "52282366"
---
# <a name="create-and-manage-dial-plans"></a><span data-ttu-id="09dfd-103">Создание и использование абонентских групп</span><span class="sxs-lookup"><span data-stu-id="09dfd-103">Create and manage dial plans</span></span>

<span data-ttu-id="09dfd-104">После того как вы спланируйте наборные планы для своей организации и разберемся со всеми правилами нормализации, которые необходимо создать для маршрутизации вызовов, вы можете создать их.</span><span class="sxs-lookup"><span data-stu-id="09dfd-104">After you plan the dial plans for your organization and figured out all the normalization rules that need to be created for call routing, you're ready to create the dial plans.</span></span> <span data-ttu-id="09dfd-105">Если у учетной записи администратора есть действительная Teams лицензия, вы можете использовать центр администрирования Microsoft Teams или Windows PowerShell для создания телефонных планов и управления ими.</span><span class="sxs-lookup"><span data-stu-id="09dfd-105">With an administrator account that has a valid Teams license, you can use the Microsoft Teams admin center or Windows PowerShell to create and manage dial plans.</span></span>  

## <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="09dfd-106">С помощью Центра администрирования Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="09dfd-106">Using the Microsoft Teams admin center</span></span>

### <a name="create-a-dial-plan"></a><span data-ttu-id="09dfd-107">Создание набора номера</span><span class="sxs-lookup"><span data-stu-id="09dfd-107">Create a dial plan</span></span>

1. <span data-ttu-id="09dfd-108">В левой области навигации Центра администрирования Microsoft Teams перейдите в **группу**  >  **голосового набора** номера .</span><span class="sxs-lookup"><span data-stu-id="09dfd-108">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Dial plan**.</span></span>
2. <span data-ttu-id="09dfd-109">Нажмите **кнопку** Добавить и введите имя и описание для набора номера.</span><span class="sxs-lookup"><span data-stu-id="09dfd-109">Click **Add**, and then enter a name and description for the dial plan.</span></span>
    <span data-ttu-id="09dfd-110">![Снимок экрана: страница добавления для создания набора номера](media/create-dial-plan.png)</span><span class="sxs-lookup"><span data-stu-id="09dfd-110">![Screenshot showing the Add page for creating a dial plan](media/create-dial-plan.png)</span></span>
3. <span data-ttu-id="09dfd-111">В **области Сведения о телефонной** линии укажите внешний префикс набора, если пользователям нужно набрать одну или несколько цифр (например, 9), чтобы получить внешнюю линию.</span><span class="sxs-lookup"><span data-stu-id="09dfd-111">Under **Dial plan details**, specify an external dialing prefix if users need to dial one or more additional leading digits (for example, 9) to get an external line.</span></span> <span data-ttu-id="09dfd-112">Для этого выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="09dfd-112">To do this:</span></span>
    1. <span data-ttu-id="09dfd-113">В поле **Внешний префикс набора** номера введите внешний префикс набора номера.</span><span class="sxs-lookup"><span data-stu-id="09dfd-113">In the **External dialing prefix** box, enter an external dialing prefix.</span></span> <span data-ttu-id="09dfd-114">Префикс может быть не более четырех символов (#,\*и 0-9).</span><span class="sxs-lookup"><span data-stu-id="09dfd-114">The prefix can be up to four characters (#,\*, and 0-9).</span></span>
    2. <span data-ttu-id="09dfd-115">Включите **оптимизированный набор номера устройства**.</span><span class="sxs-lookup"><span data-stu-id="09dfd-115">Turn on **Optimized device dialing**.</span></span> <span data-ttu-id="09dfd-116">Если вы указали внешний префикс набора номера, необходимо также включить этот параметр, чтобы применить префикс, чтобы звонки можно было делать за пределами организации.</span><span class="sxs-lookup"><span data-stu-id="09dfd-116">If you specify an external dialing prefix, you must also turn on this setting to apply the prefix so calls can be made outside your organization.</span></span>
4. <span data-ttu-id="09dfd-117">В **области Правила нормализации** настройте и соберите одно или несколько правил нормализации [для](what-are-dial-plans.md#normalization-rules) плана набора номера.</span><span class="sxs-lookup"><span data-stu-id="09dfd-117">Under **Normalization rules**, configure and associate one or more [normalization rules](what-are-dial-plans.md#normalization-rules) for the dial plan.</span></span> <span data-ttu-id="09dfd-118">С каждой телефонной планом должно быть связано хотя бы одно правило нормализации.</span><span class="sxs-lookup"><span data-stu-id="09dfd-118">Each dial plan must have at least one normalization rule associated with it.</span></span>  <span data-ttu-id="09dfd-119">Для этого сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="09dfd-119">To do this, do one or more of the following:</span></span>
    - <span data-ttu-id="09dfd-120">Чтобы создать новое правило нормализации и связать его с телефонной планом, нажмите кнопку Добавить **и** определите правило.</span><span class="sxs-lookup"><span data-stu-id="09dfd-120">To create a new normalization rule and associate it with the dial plan, click **Add**, and then define the rule.</span></span>
    - <span data-ttu-id="09dfd-121">Чтобы изменить правило нормализации, уже связанное с планом набора номера, выберите его, щелкнув слева от имени правила и выбрав изменить **.**</span><span class="sxs-lookup"><span data-stu-id="09dfd-121">To edit a normalization rule that's already associated with the dial plan, select the rule by clicking to the left of the rule name, and then click **Edit**.</span></span> <span data-ttu-id="09dfd-122">Внести нужные изменения и нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="09dfd-122">Make the changes you want, and then click **Save**.</span></span>
    - <span data-ttu-id="09dfd-123">Чтобы удалить правило нормализации из набора номера, выберите его, щелкнув слева от имени правила и выбрав **удалить**.</span><span class="sxs-lookup"><span data-stu-id="09dfd-123">To remove a normalization rule from the dial plan, select the rule by clicking to the left of the rule name, and then click **Remove**.</span></span>
5. <span data-ttu-id="09dfd-124">Расположить правила нормализации в нужном порядке.</span><span class="sxs-lookup"><span data-stu-id="09dfd-124">Arrange the normalization rules in the order that you want.</span></span> <span data-ttu-id="09dfd-125">Нажмите **кнопку Вверх** **или** Вниз, чтобы изменить положение правил в списке.</span><span class="sxs-lookup"><span data-stu-id="09dfd-125">Click **Move up** or **Move down** to change the position of rules in the list.</span></span>

    > [!NOTE]
    > <span data-ttu-id="09dfd-126">Teams список правил нормализации сверху вниз и использует первое правило, которое соответствует набратому номеру.</span><span class="sxs-lookup"><span data-stu-id="09dfd-126">Teams traverses the list of normalization rules from the top down and uses the first rule that matches the dialed number.</span></span> <span data-ttu-id="09dfd-127">Если вы настроили для набора номера несколько правил нормализации, убедитесь, что более строгие правила отсортировали над менее строгими.</span><span class="sxs-lookup"><span data-stu-id="09dfd-127">If you set up a dial plan so that a dialed number can match more than one normalization rule, make sure the more restrictive rules are sorted above the less restrictive ones.</span></span>

6. <span data-ttu-id="09dfd-128">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="09dfd-128">Click **Save**.</span></span>
7. <span data-ttu-id="09dfd-129">Если вы хотите проверить набор номеров, **введите** номер телефона в области Проверка набора номера и нажмите кнопку **Проверить**.</span><span class="sxs-lookup"><span data-stu-id="09dfd-129">If you want to test the dial plan, under **Test dial plan**, enter a phone number, and then click **Test**.</span></span>

### <a name="edit-a-dial-plan"></a><span data-ttu-id="09dfd-130">Изменение набора номера</span><span class="sxs-lookup"><span data-stu-id="09dfd-130">Edit a dial plan</span></span>

1. <span data-ttu-id="09dfd-131">В левой области навигации Центра администрирования Microsoft Teams перейдите в **группу**  >  **голосового набора** номера .</span><span class="sxs-lookup"><span data-stu-id="09dfd-131">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Dial plan**.</span></span>
2. <span data-ttu-id="09dfd-132">Выберите план набора номера, щелкнув слева от имени телефонной программы, а затем нажмите кнопку **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="09dfd-132">Select the dial plan by clicking to the left of the dial plan name, and then click **Edit**.</span></span>
3. <span data-ttu-id="09dfd-133">Внести нужные изменения и нажмите кнопку **Сохранить.**</span><span class="sxs-lookup"><span data-stu-id="09dfd-133">Make the changes that you want, and then click **Save**.</span></span>

### <a name="assign-a-dial-plan-to-users"></a><span data-ttu-id="09dfd-134">Назначение набора номера пользователям</span><span class="sxs-lookup"><span data-stu-id="09dfd-134">Assign a dial plan to users</span></span>

<span data-ttu-id="09dfd-135">Вы назначаете план набора номера так же, как назначаете политики.</span><span class="sxs-lookup"><span data-stu-id="09dfd-135">You assign a dial plan in the same way you assign policies.</span></span> [!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="using-powershell"></a><span data-ttu-id="09dfd-136">С помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="09dfd-136">Using PowerShell</span></span>
  
### <a name="start-powershell"></a><span data-ttu-id="09dfd-137">Запуск PowerShell</span><span class="sxs-lookup"><span data-stu-id="09dfd-137">Start PowerShell</span></span>
- <span data-ttu-id="09dfd-138">Откройте Windows PowerShell командную команду и запустите следующие команды:</span><span class="sxs-lookup"><span data-stu-id="09dfd-138">Open a Windows PowerShell command prompt and run the following commands:</span></span>

```powershell
  # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
```
  
### <a name="create-and-manage-your-dial-plans"></a><span data-ttu-id="09dfd-139">Создание телефонных планов и управление ими</span><span class="sxs-lookup"><span data-stu-id="09dfd-139">Create and manage your dial plans</span></span>

<span data-ttu-id="09dfd-140">Создание абонентских групп клиентов и управление ими можно осуществлять с помощью одиночного командлета или сценария PowerShell.</span><span class="sxs-lookup"><span data-stu-id="09dfd-140">You can either use a single cmdlet or a PowerShell script to create and manage tenant dial plans.</span></span>
  
#### <a name="using-single-cmdlets"></a><span data-ttu-id="09dfd-141">С помощью одиночного командлета</span><span class="sxs-lookup"><span data-stu-id="09dfd-141">Using single cmdlets</span></span>

- <span data-ttu-id="09dfd-142">Чтобы создать новую телефонную план, запустите:</span><span class="sxs-lookup"><span data-stu-id="09dfd-142">To create a new dial plan, run:</span></span>
    
  ```PowerShell
  New-CsTenantDialPlan -Identity RedmondDialPlan -Description "Dial Plan for Redmond" -NormalizationRules <pslistmodifier> -ExternalAccessPrefix 9 -SimpleName "Dial-Plan-for-Redmond"
  ```

    <span data-ttu-id="09dfd-143">Другие примеры и параметры см. в разделе [New-CsTenantDialPlan](/powershell/module/skype/new-cstenantdialplan).</span><span class="sxs-lookup"><span data-stu-id="09dfd-143">For other examples and parameters, see [New-CsTenantDialPlan](/powershell/module/skype/new-cstenantdialplan).</span></span>
    
- <span data-ttu-id="09dfd-144">Чтобы изменить параметры существующей телефонной программы, запустите:</span><span class="sxs-lookup"><span data-stu-id="09dfd-144">To edit the settings of an existing dial plan, run:</span></span>
    
  ```PowerShell
  Set-CsTenantDialPlan -Identity RedmondDialPlan  -NormalizationRules <pslistmodifier> -ExternalAccessPrefix 9
    -SimpleName "Dial-Plan-for-Redmond"
  ```

    <span data-ttu-id="09dfd-145">Другие примеры и параметры см. в разделе [Set-CsTenantDialPlan](/powershell/module/skype/set-cstenantdialplan).</span><span class="sxs-lookup"><span data-stu-id="09dfd-145">For other examples and parameters, see [Set-CsTenantDialPlan](/powershell/module/skype/set-cstenantdialplan).</span></span>
    
- <span data-ttu-id="09dfd-146">Чтобы добавить пользователей в абонентскую группу, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="09dfd-146">To add users to a dial plan, run:</span></span>
    
  ```PowerShell
  Grant-CsTenantDialPlan -Identity amos.marble@contoso.com -PolicyName RedmondDialPlan
  ```

    <span data-ttu-id="09dfd-147">Другие примеры и параметры см. в разделе [Grant-CsTenantDialPlan](/powershell/module/skype/grant-cstenantdialplan).</span><span class="sxs-lookup"><span data-stu-id="09dfd-147">For other examples and parameters, see [Grant-CsTenantDialPlan](/powershell/module/skype/grant-cstenantdialplan).</span></span>
    
- <span data-ttu-id="09dfd-148">Чтобы просмотреть параметры абонентской группы, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="09dfd-148">To view the settings on a dial plan, run:</span></span>
    
  ```PowerShell
  Get-CsTenantDialPlan -Identity RedmondDialPlan
  ```

    <span data-ttu-id="09dfd-149">Другие примеры и параметры см. в разделе [Get-CsTenantDialPlan](/powershell/module/skype/get-cstenantdialplan?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="09dfd-149">For other examples and parameters, see [Get-CsTenantDialPlan](/powershell/module/skype/get-cstenantdialplan?view=skype-ps).</span></span>
    
- <span data-ttu-id="09dfd-150">Чтобы удалить абонентскую группу, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="09dfd-150">To delete a dial plan, run:</span></span>
    
  ```PowerShell
  Remove-CsTenantDialPlan -Identity RedmondDialPlan -force
  ```

    <span data-ttu-id="09dfd-151">Другие примеры и параметры см. в разделе [Remove-CsTenantDialPlan](/powershell/module/skype/remove-cstenantdialplan?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="09dfd-151">For other examples and parameters, see [Remove-CsTenantDialPlan](/powershell/module/skype/remove-cstenantdialplan?view=skype-ps).</span></span>
    
- <span data-ttu-id="09dfd-152">Чтобы просмотреть параметры действующей абонентской группы, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="09dfd-152">To see the settings of the effective dial plan, run:</span></span>
    
  ```PowerShell
  Get-CsEffectiveTenantDialPlan -Identity amos.marble@contoso.com
  ```

    <span data-ttu-id="09dfd-153">Другие примеры и параметры см. в разделе [Get-CsEffectiveTenantDialPlan](/powershell/module/skype/get-cseffectivetenantdialplan).</span><span class="sxs-lookup"><span data-stu-id="09dfd-153">For other examples and parameters, see [Get-CsEffectiveTenantDialPlan](/powershell/module/skype/get-cseffectivetenantdialplan).</span></span>
    
- <span data-ttu-id="09dfd-154">Для проверки действующих параметров абонентской группы запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="09dfd-154">To test the effective settings of a dial plan, run:</span></span>
    
  ```PowerShell
  Test-CsEffectiveTenantDialPlan -DialedNumber 14255550199 -Identity amos.marble@contoso.com
  ```

    <span data-ttu-id="09dfd-155">Другие примеры и параметры см. в разделе [Test-CsEffectiveTenantDialPlan](/powershell/module/skype/test-cseffectivetenantdialplan?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="09dfd-155">For other examples and parameters, see [Test-CsEffectiveTenantDialPlan](/powershell/module/skype/test-cseffectivetenantdialplan?view=skype-ps).</span></span>
    
#### <a name="using-a-powershell-script"></a><span data-ttu-id="09dfd-156">С помощью скрипта PowerShell</span><span class="sxs-lookup"><span data-stu-id="09dfd-156">Using a PowerShell script</span></span>

<span data-ttu-id="09dfd-157">Чтобы удалить правило нормализации, связанное с клиентской телефонной планом, не нужно сначала удалять ее:</span><span class="sxs-lookup"><span data-stu-id="09dfd-157">Run this to delete a normalization rule that is associated with a tenant dial plan without needing to delete the tenant dial plan first:</span></span>
```PowerShell
$b1=New-CsVoiceNormalizationRule -Identity Global/NR4 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{add=$b1}
(Get-CsTenantDialPlan -Identity RedmondDialPlan).NormalizationRules
$b2=New-CsVoiceNormalizationRule -Identity Global/NR4 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{remove=$b2}
```
<span data-ttu-id="09dfd-158">Запустите эту команду для добавления следующего правила нормализации к существующему клиенту абонентской группы с именем RedmondDialPlan.</span><span class="sxs-lookup"><span data-stu-id="09dfd-158">Run this to add the following normalization rule to the existing tenant dial plan named RedmondDialPlan.</span></span>
```PowerShell
$nr1=New-CsVoiceNormalizationRule -Parent Global -Description 'Organization extension dialing' -Pattern '^(\\d{3})$' -Translation '+14255551$1' -Name NR1 -IsInternalExtension $false -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{add=$nr1}
```
<span data-ttu-id="09dfd-159">Запустите эту команду для удаления следующего правила нормализации из существующего клиента абонентской группы с именем RedmondDialPlan.</span><span class="sxs-lookup"><span data-stu-id="09dfd-159">Run this to remove the following normalization rule from the existing tenant dial plan named RedmondDialPlan.</span></span>
```PowerShell
$nr1=New-CsVoiceNormalizationRule -Parent Global/NR1 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{remove=$nr1}
```

<span data-ttu-id="09dfd-160">Запустите следующую команду, когда вы хотите также проверить существующие правила нормализации, определить, какое из них нужно удалить, а затем использовать его индекс для удаления.</span><span class="sxs-lookup"><span data-stu-id="09dfd-160">Run the following when you want to also examine the existing normalization rules, determine which one you want to delete, and then use its index to remove it.</span></span> <span data-ttu-id="09dfd-161">Массив правил нормализации начинается с индекса 0.</span><span class="sxs-lookup"><span data-stu-id="09dfd-161">The array of normalization rules starts with index 0.</span></span> <span data-ttu-id="09dfd-162">Если мы хотим удалить з-х цифровое правило нормализации, индекс будет 1.</span><span class="sxs-lookup"><span data-stu-id="09dfd-162">We would like to remove the 3-digit normalization rule, so that is index 1.</span></span>
  
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

<span data-ttu-id="09dfd-163">Запустите эту команду для поиска всех пользователей, которым была присвоена абонентская группа клиента RedmondDialPlan.</span><span class="sxs-lookup"><span data-stu-id="09dfd-163">Run this to find all users who have been granted the RedmondDialPlan tenant dial plan.</span></span>
  
```PowerShell
Get-CsOnlineUser | Where-Object {$_.TenantDialPlan -eq "RedmondDialPlan"}
```

<span data-ttu-id="09dfd-164">Запустите этот запуск, чтобы удалить все назначенное tenantDialPlan всех пользователей, у которых есть hostingProvider sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="09dfd-164">Run this to remove any assigned TenantDialPlan from all users who have a HostingProvider of sipfed.online.lync.com.</span></span>
```PowerShell
Get-CsOnlineUser -Filter {HostingProvider -eq "sipfed.online.lync.com"} | Grant-CsTenantDialPlan -policyname $null
```

<span data-ttu-id="09dfd-165">Запустите эту команду для добавления существующей локальной абонентской группы с именем OPDP1 в качестве абонентской группы клиента для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="09dfd-165">Run these to add the existing on-premises dial plan named OPDP1 as a tenant dial plan for your organization.</span></span> <span data-ttu-id="09dfd-166">Необходимо сначала сохранить локальную абонентскую группу в XML-файл, а затем использовать ее для создания новой абонентской группы клиента.</span><span class="sxs-lookup"><span data-stu-id="09dfd-166">You need to first save the on-premises dial plan to an .xml file, and then use it to create the new tenant dial plan.</span></span>
  
<span data-ttu-id="09dfd-167">Запустите эту команду для сохранения локальной абонентской группы в XML-файл.</span><span class="sxs-lookup"><span data-stu-id="09dfd-167">Run this to save the on-premises dial plan to the .xml file.</span></span>
  
```PowerShell
$DPName = "OPDP1"
$DPFileName = "dialplan.xml"
Get-CsDialplan $DPName | Export-Clixml $DPFileName
```

<span data-ttu-id="09dfd-168">Запустите эту команду для создания новой абонентской группы клиента.</span><span class="sxs-lookup"><span data-stu-id="09dfd-168">Run this to create the new tenant dial plan.</span></span>
  
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
    
## <a name="related-topics"></a><span data-ttu-id="09dfd-169">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="09dfd-169">Related topics</span></span>

- [<span data-ttu-id="09dfd-170">Что такое абонентские группы?</span><span class="sxs-lookup"><span data-stu-id="09dfd-170">What are dial plans?</span></span>](what-are-dial-plans.md)
- [<span data-ttu-id="09dfd-171">Общие вопросы по передаче номеров телефонов</span><span class="sxs-lookup"><span data-stu-id="09dfd-171">Transferring phone numbers common questions</span></span>](./phone-number-calling-plans/port-order-overview.md)
- [<span data-ttu-id="09dfd-172">Типы номеров телефонов, используемые в планах звонков</span><span class="sxs-lookup"><span data-stu-id="09dfd-172">Different kinds of phone numbers used for Calling Plans</span></span>](different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [<span data-ttu-id="09dfd-173">Управление номерами телефонов организации</span><span class="sxs-lookup"><span data-stu-id="09dfd-173">Manage phone numbers for your organization</span></span>](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)
- [<span data-ttu-id="09dfd-174">Условия и положения, распространяющиеся на экстренные вызовы</span><span class="sxs-lookup"><span data-stu-id="09dfd-174">Emergency calling terms and conditions</span></span>](emergency-calling-terms-and-conditions.md)
- <span data-ttu-id="09dfd-175">[Заявление об отказе от ответственности экстренных вызовов](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="09dfd-175">[Emergency calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>
- [<span data-ttu-id="09dfd-176">Обзор PowerShell в Teams</span><span class="sxs-lookup"><span data-stu-id="09dfd-176">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
