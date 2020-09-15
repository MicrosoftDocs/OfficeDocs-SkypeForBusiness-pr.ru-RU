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
description: Сведения о том, как использовать центр администрирования Microsoft Teams или Windows PowerShell для создания абонентских групп и управления ими (тарифные абонентские группы для коммутируемого звонка).
ms.openlocfilehash: 0655f81df9c8ce25368a281a7f5b3392f7fe6ec3
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814788"
---
# <a name="create-and-manage-dial-plans"></a><span data-ttu-id="3e9b1-103">Создание и использование абонентских групп</span><span class="sxs-lookup"><span data-stu-id="3e9b1-103">Create and manage dial plans</span></span>

<span data-ttu-id="3e9b1-104">После того как вы запланируете абонентские группы для Организации и выйдете все правила нормализации, которые необходимо создать для маршрутизации звонков, вы можете создать абонентские группы.</span><span class="sxs-lookup"><span data-stu-id="3e9b1-104">After you plan the dial plans for your organization and figured out all the normalization rules that need to be created for call routing, you're ready to create the dial plans.</span></span> <span data-ttu-id="3e9b1-105">Вы можете использовать центр администрирования Microsoft Teams или Windows PowerShell для создания абонентских групп и управления ими.</span><span class="sxs-lookup"><span data-stu-id="3e9b1-105">You can use the Microsoft Teams admin center or Windows PowerShell to create and manage dial plans.</span></span>  

## <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="3e9b1-106">С помощью Центра администрирования Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3e9b1-106">Using the Microsoft Teams admin center</span></span>

### <a name="create-a-dial-plan"></a><span data-ttu-id="3e9b1-107">Создание абонентской группы</span><span class="sxs-lookup"><span data-stu-id="3e9b1-107">Create a dial plan</span></span>

1. <span data-ttu-id="3e9b1-108">В левой области навигации центра администрирования Microsoft Teams выберите **Voice**  >  **абонентская**абонентская группа.</span><span class="sxs-lookup"><span data-stu-id="3e9b1-108">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Dial plan**.</span></span>
2. <span data-ttu-id="3e9b1-109">Нажмите кнопку **Добавить**, а затем введите имя и описание абонентского плана.</span><span class="sxs-lookup"><span data-stu-id="3e9b1-109">Click **Add**, and then enter a name and description for the dial plan.</span></span>
    <span data-ttu-id="3e9b1-110">![Снимок экрана, на котором показана страница "Добавление" для создания абонентской группы](media/create-dial-plan.png)</span><span class="sxs-lookup"><span data-stu-id="3e9b1-110">![Screenshot showing the Add page for creating a dial plan](media/create-dial-plan.png)</span></span>
3. <span data-ttu-id="3e9b1-111">В разделе **сведения о абонентской схеме**укажите внешний префикс набора номера, если пользователям необходимо набрать одну или несколько начальных цифр (например, 9), чтобы получить внешнюю строку.</span><span class="sxs-lookup"><span data-stu-id="3e9b1-111">Under **Dial plan details**, specify an external dialing prefix if users need to dial one or more additional leading digits (for example, 9) to get an external line.</span></span> <span data-ttu-id="3e9b1-112">Для этого выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="3e9b1-112">To do this:</span></span>
    1. <span data-ttu-id="3e9b1-113">В поле **Префикс внешнего набора** введите внешний префикс.</span><span class="sxs-lookup"><span data-stu-id="3e9b1-113">In the **External dialing prefix** box, enter an external dialing prefix.</span></span> <span data-ttu-id="3e9b1-114">Префикс может состоять не более чем из четырех знаков (#, \* и 0-9).</span><span class="sxs-lookup"><span data-stu-id="3e9b1-114">The prefix can be up to four characters (#,\*, and 0-9).</span></span>
    2. <span data-ttu-id="3e9b1-115">Включите **оптимизированный набор номера для устройств**.</span><span class="sxs-lookup"><span data-stu-id="3e9b1-115">Turn on **Optimized device dialing**.</span></span> <span data-ttu-id="3e9b1-116">Если указан внешний префикс набора номера, необходимо также включить этот параметр, чтобы применить префикс, чтобы звонки могли выполняться за пределами Организации.</span><span class="sxs-lookup"><span data-stu-id="3e9b1-116">If you specify an external dialing prefix, you must also turn on this setting to apply the prefix so calls can be made outside your organization.</span></span>
4. <span data-ttu-id="3e9b1-117">В разделе **правила нормализации**настройте и свяжите одно или несколько [правил нормализации](what-are-dial-plans.md#normalization-rules) для абонентской группы.</span><span class="sxs-lookup"><span data-stu-id="3e9b1-117">Under **Normalization rules**, configure and associate one or more [normalization rules](what-are-dial-plans.md#normalization-rules) for the dial plan.</span></span> <span data-ttu-id="3e9b1-118">Каждая абонентская группа должна иметь по крайней мере одно связанное с ним правило нормализации.</span><span class="sxs-lookup"><span data-stu-id="3e9b1-118">Each dial plan must have at least one normalization rule associated with it.</span></span>  <span data-ttu-id="3e9b1-119">Чтобы сделать это, выполните одно или несколько из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="3e9b1-119">To do this, do one or more of the following:</span></span>
    - <span data-ttu-id="3e9b1-120">Чтобы создать новое правило нормализации и связать его с абонентской панелью, нажмите кнопку **Добавить**, а затем укажите правило.</span><span class="sxs-lookup"><span data-stu-id="3e9b1-120">To create a new normalization rule and associate it with the dial plan, click **Add**, and then define the rule.</span></span>
    - <span data-ttu-id="3e9b1-121">Чтобы изменить правило нормализации, уже связанное с абонентской панелью, выберите правило, щелкнув слева от имени правила, а затем нажмите кнопку **изменить**.</span><span class="sxs-lookup"><span data-stu-id="3e9b1-121">To edit a normalization rule that's already associated with the dial plan, select the rule by clicking to the left of the rule name, and then click **Edit**.</span></span> <span data-ttu-id="3e9b1-122">Внесите нужные изменения и нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="3e9b1-122">Make the changes you want, and then click **Save**.</span></span>
    - <span data-ttu-id="3e9b1-123">Чтобы удалить правило нормализации абонентской группы, выберите правило, щелкнув слева от имени правила, а затем нажмите кнопку **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="3e9b1-123">To remove a normalization rule from the dial plan, select the rule by clicking to the left of the rule name, and then click **Remove**.</span></span>
5. <span data-ttu-id="3e9b1-124">Расположите правила нормализации в нужном порядке.</span><span class="sxs-lookup"><span data-stu-id="3e9b1-124">Arrange the normalization rules in the order that you want.</span></span> <span data-ttu-id="3e9b1-125">Нажмите кнопку **переместить вверх** или **Переместить вниз** , чтобы изменить расположение правил в списке.</span><span class="sxs-lookup"><span data-stu-id="3e9b1-125">Click **Move up** or **Move down** to change the position of rules in the list.</span></span>

    > [!NOTE]
    > <span data-ttu-id="3e9b1-126">Teams обходит список правил нормализации сверху вниз и использует первое правило, которое соответствует номеру набора.</span><span class="sxs-lookup"><span data-stu-id="3e9b1-126">Teams traverses the list of normalization rules from the top down and uses the first rule that matches the dialed number.</span></span> <span data-ttu-id="3e9b1-127">Если вы настроили абонентскую группу таким образом, чтобы номер с набором номера мог совпадать с более чем одним правилом нормализации, убедитесь в том, что более ограниченные правила сортируются над менее строгими.</span><span class="sxs-lookup"><span data-stu-id="3e9b1-127">If you set up a dial plan so that a dialed number can match more than one normalization rule, make sure the more restrictive rules are sorted above the less restrictive ones.</span></span>

6. <span data-ttu-id="3e9b1-128">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="3e9b1-128">Click **Save**.</span></span>
7. <span data-ttu-id="3e9b1-129">Если вы хотите протестировать абонентскую группу, в разделе **Проверка абонентской группы**введите номер телефона и нажмите кнопку **проверить**.</span><span class="sxs-lookup"><span data-stu-id="3e9b1-129">If you want to test the dial plan, under **Test dial plan**, enter a phone number, and then click **Test**.</span></span>

### <a name="edit-a-dial-plan"></a><span data-ttu-id="3e9b1-130">Изменение абонентской группы</span><span class="sxs-lookup"><span data-stu-id="3e9b1-130">Edit a dial plan</span></span>

1. <span data-ttu-id="3e9b1-131">В левой области навигации центра администрирования Microsoft Teams выберите **Voice**  >  **абонентская**абонентская группа.</span><span class="sxs-lookup"><span data-stu-id="3e9b1-131">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Dial plan**.</span></span>
2. <span data-ttu-id="3e9b1-132">Выберите абонентскую группу, щелкнув слева от имени абонентской группы, а затем нажмите кнопку **изменить**.</span><span class="sxs-lookup"><span data-stu-id="3e9b1-132">Select the dial plan by clicking to the left of the dial plan name, and then click **Edit**.</span></span>
3. <span data-ttu-id="3e9b1-133">Внесите нужные изменения и нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="3e9b1-133">Make the changes that you want, and then click **Save**.</span></span>

### <a name="assign-a-dial-plan-to-users"></a><span data-ttu-id="3e9b1-134">Назначение абонентской группы пользователям</span><span class="sxs-lookup"><span data-stu-id="3e9b1-134">Assign a dial plan to users</span></span>

<span data-ttu-id="3e9b1-135">Абонентская группа назначается точно так же, как и политики.</span><span class="sxs-lookup"><span data-stu-id="3e9b1-135">You assign a dial plan in the same way you assign policies.</span></span> [!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="using-powershell"></a><span data-ttu-id="3e9b1-136">Использование PowerShell</span><span class="sxs-lookup"><span data-stu-id="3e9b1-136">Using PowerShell</span></span>
  
### <a name="verify-and-start-remote-powershell"></a><span data-ttu-id="3e9b1-137">Проверка и запуск удаленной оболочки PowerShell</span><span class="sxs-lookup"><span data-stu-id="3e9b1-137">Verify and start Remote PowerShell</span></span>

 <span data-ttu-id="3e9b1-138">**Убедитесь в том, что вы используете Windows PowerShell версии 3,0 или более поздней.**</span><span class="sxs-lookup"><span data-stu-id="3e9b1-138">**Check that you are running Windows PowerShell version 3.0 or later**</span></span>
  
1. <span data-ttu-id="3e9b1-139">Чтобы убедиться в том, что у вас установлена версия 3,0 или выше: **меню "Пуск**"  >  **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="3e9b1-139">To verify that you're running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="3e9b1-140">Проверьте версию, введя в окне _Windows PowerShell_ команду **Get-Host**.</span><span class="sxs-lookup"><span data-stu-id="3e9b1-140">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="3e9b1-141">Если у вас нет версии 3,0 или более поздней, скачайте и установите обновления для Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3e9b1-141">If you don't have version 3.0 or later, download and install updates to Windows PowerShell.</span></span> <span data-ttu-id="3e9b1-142">Чтобы скачать и обновить Windows PowerShell до версии 4,0, ознакомьтесь с разгрузкой [платформы Windows Management Framework 4,0](https://go.microsoft.com/fwlink/?LinkId=716845) .</span><span class="sxs-lookup"><span data-stu-id="3e9b1-142">See [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0.</span></span> <span data-ttu-id="3e9b1-143">Перезагрузите компьютер после появления соответствующего запроса.</span><span class="sxs-lookup"><span data-stu-id="3e9b1-143">Restart your computer when you're prompted.</span></span>
    
4. <span data-ttu-id="3e9b1-144">Кроме того, вам потребуется установить модуль Windows PowerShell для Skype для бизнеса Online, который позволяет создавать удаленные сеансы Windows PowerShell, которые подключаются к Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="3e9b1-144">You'll also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span> <span data-ttu-id="3e9b1-145">Вы можете скачать этот модуль, который поддерживается только на компьютерах с 64-разрядными компьютерами и в [модуле Windows PowerShell для Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=294688).</span><span class="sxs-lookup"><span data-stu-id="3e9b1-145">You can download this module, which is supported only on 64-bit computers, at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688).</span></span> <span data-ttu-id="3e9b1-146">Перезагрузите компьютер, если будет предложено.</span><span class="sxs-lookup"><span data-stu-id="3e9b1-146">Restart your computer if you're prompted.</span></span>
    
<span data-ttu-id="3e9b1-147">Дополнительные сведения можно найти в разделе [подключение ко всем службам Microsoft 365 или Office 365 в одном окне Windows PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span><span class="sxs-lookup"><span data-stu-id="3e9b1-147">To learn more, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span></span>
  
 <span data-ttu-id="3e9b1-148">**Запуск сеанса Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="3e9b1-148">**Start a Windows PowerShell session**</span></span>
  
1. <span data-ttu-id="3e9b1-149">Нажмите кнопку **запустить**  >  **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="3e9b1-149">Click **Start** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="3e9b1-150">В окне **Windows PowerShell** подключитесь к Microsoft 365 или Office 365, выполнив следующие действия:</span><span class="sxs-lookup"><span data-stu-id="3e9b1-150">In the **Windows PowerShell** window, connect to Microsoft 365 or Office 365 by running:</span></span>
    
 
    > [!NOTE]
    > <span data-ttu-id="3e9b1-151">Skype для бизнеса Online уже входит в состав последнего модуля PowerShell для Teams.</span><span class="sxs-lookup"><span data-stu-id="3e9b1-151">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
    >
    > <span data-ttu-id="3e9b1-152">Если вы используете последнюю версию [общедоступной оболочки для Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/), вам не нужно устанавливать соединитель Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="3e9b1-152">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

    ```PowerShell
   Import-Module -Name MicrosoftTeams
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
    ```
  
### <a name="create-and-manage-your-dial-plans"></a><span data-ttu-id="3e9b1-153">Создание абонентских планов и управление ими</span><span class="sxs-lookup"><span data-stu-id="3e9b1-153">Create and manage your dial plans</span></span>

<span data-ttu-id="3e9b1-154">Создание абонентских групп клиентов и управление ими можно осуществлять с помощью одиночного командлета или сценария PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3e9b1-154">You can either use a single cmdlet or a PowerShell script to create and manage tenant dial plans.</span></span>
  
#### <a name="using-single-cmdlets"></a><span data-ttu-id="3e9b1-155">С помощью одиночного командлета</span><span class="sxs-lookup"><span data-stu-id="3e9b1-155">Using single cmdlets</span></span>

- <span data-ttu-id="3e9b1-156">Чтобы создать новую абонентскую группу, выполните:</span><span class="sxs-lookup"><span data-stu-id="3e9b1-156">To create a new dial plan, run:</span></span>
    
  ```PowerShell
  New-CsTenantDialPlan -Identity RedmondDialPlan -Description "Dial Plan for Redmond" -NormalizationRules <pslistmodifier> -ExternalAccessPrefix 9 -SimpleName "Dial-Plan-for-Redmond"
  ```

    <span data-ttu-id="3e9b1-157">Другие примеры и параметры см. в разделе [New-CsTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/new-cstenantdialplan).</span><span class="sxs-lookup"><span data-stu-id="3e9b1-157">For other examples and parameters, see [New-CsTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/new-cstenantdialplan).</span></span>
    
- <span data-ttu-id="3e9b1-158">Чтобы изменить параметры существующей абонентской группы, выполните:</span><span class="sxs-lookup"><span data-stu-id="3e9b1-158">To edit the settings of an existing dial plan, run:</span></span>
    
  ```PowerShell
  Set-CsTenantDialPlan -Identity RedmondDialPlan  -NormalizationRules <pslistmodifier> -ExternalAccessPrefix 9
    -SimpleName "Dial-Plan-for-Redmond"
  ```

    <span data-ttu-id="3e9b1-159">Другие примеры и параметры см. в разделе [Set-CsTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/set-cstenantdialplan).</span><span class="sxs-lookup"><span data-stu-id="3e9b1-159">For other examples and parameters, see [Set-CsTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/set-cstenantdialplan).</span></span>
    
- <span data-ttu-id="3e9b1-160">Чтобы добавить пользователей в абонентскую группу, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="3e9b1-160">To add users to a dial plan, run:</span></span>
    
  ```PowerShell
  Grant-CsTenantDialPlan -Identity amos.marble@contoso.com -PolicyName RedmondDialPlan
  ```

    <span data-ttu-id="3e9b1-161">Другие примеры и параметры см. в разделе [Grant-CsTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-cstenantdialplan).</span><span class="sxs-lookup"><span data-stu-id="3e9b1-161">For other examples and parameters, see [Grant-CsTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-cstenantdialplan).</span></span>
    
- <span data-ttu-id="3e9b1-162">Чтобы просмотреть параметры абонентской группы, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="3e9b1-162">To view the settings on a dial plan, run:</span></span>
    
  ```PowerShell
  Get-CsTenantDialPlan -Identity RedmondDialPlan
  ```

    <span data-ttu-id="3e9b1-163">Другие примеры и параметры см. в разделе [Get-CsTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/get-cstenantdialplan?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="3e9b1-163">For other examples and parameters, see [Get-CsTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/get-cstenantdialplan?view=skype-ps).</span></span>
    
- <span data-ttu-id="3e9b1-164">Чтобы удалить абонентскую группу, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="3e9b1-164">To delete a dial plan, run:</span></span>
    
  ```PowerShell
  Remove-CsTenantDialPlan -Identity RedmondDialPlan -force
  ```

    <span data-ttu-id="3e9b1-165">Другие примеры и параметры см. в разделе [Remove-CsTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/remove-cstenantdialplan?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="3e9b1-165">For other examples and parameters, see [Remove-CsTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/remove-cstenantdialplan?view=skype-ps).</span></span>
    
- <span data-ttu-id="3e9b1-166">Чтобы просмотреть параметры действующей абонентской группы, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="3e9b1-166">To see the settings of the effective dial plan, run:</span></span>
    
  ```PowerShell
  Get-CsEffectiveTenantDialPlan -Identity amos.marble@contoso.com
  ```

    <span data-ttu-id="3e9b1-167">Другие примеры и параметры см. в разделе [Get-CsEffectiveTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/get-cseffectivetenantdialplan).</span><span class="sxs-lookup"><span data-stu-id="3e9b1-167">For other examples and parameters, see [Get-CsEffectiveTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/get-cseffectivetenantdialplan).</span></span>
    
- <span data-ttu-id="3e9b1-168">Для проверки действующих параметров абонентской группы запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="3e9b1-168">To test the effective settings of a dial plan, run:</span></span>
    
  ```PowerShell
  Test-CsEffectiveTenantDialPlan -DialedNumber 14255550199 -Identity amos.marble@contoso.com
  ```

    <span data-ttu-id="3e9b1-169">Другие примеры и параметры см. в разделе [Test-CsEffectiveTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/test-cseffectivetenantdialplan?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="3e9b1-169">For other examples and parameters, see [Test-CsEffectiveTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/test-cseffectivetenantdialplan?view=skype-ps).</span></span>
    
#### <a name="using-a-powershell-script"></a><span data-ttu-id="3e9b1-170">С помощью скрипта PowerShell</span><span class="sxs-lookup"><span data-stu-id="3e9b1-170">Using a PowerShell script</span></span>

<span data-ttu-id="3e9b1-171">Запустите этот параметр, чтобы удалить правило нормализации, связанное с абонентской планом клиента, не требуя сначала удалить абонентскую группу.</span><span class="sxs-lookup"><span data-stu-id="3e9b1-171">Run this to delete a normalization rule that is associated with a tenant dial plan without needing to delete the tenant dial plan first:</span></span>
```PowerShell
$b1=New-CsVoiceNormalizationRule -Identity Global/NR4 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{add=$b1}
(Get-CsTenantDialPlan -Identity RedmondDialPlan).NormalizationRules
$b2=New-CsVoiceNormalizationRule -Identity Global/NR4 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{remove=$b2}
```
<span data-ttu-id="3e9b1-172">Запустите эту команду для добавления следующего правила нормализации к существующему клиенту абонентской группы с именем RedmondDialPlan.</span><span class="sxs-lookup"><span data-stu-id="3e9b1-172">Run this to add the following normalization rule to the existing tenant dial plan named RedmondDialPlan.</span></span>
```PowerShell
$nr1=New-CsVoiceNormalizationRule -Parent Global -Description 'Organization extension dialing' -Pattern '^(\\d{3})$' -Translation '+14255551$1' -Name NR1 -IsInternalExtension $false -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{add=$nr1}
```
<span data-ttu-id="3e9b1-173">Запустите эту команду для удаления следующего правила нормализации из существующего клиента абонентской группы с именем RedmondDialPlan.</span><span class="sxs-lookup"><span data-stu-id="3e9b1-173">Run this to remove the following normalization rule from the existing tenant dial plan named RedmondDialPlan.</span></span>
```PowerShell
$nr1=New-CsVoiceNormalizationRule -Parent Global/NR1 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{remove=$nr1}
```

<span data-ttu-id="3e9b1-174">Запустите следующую команду, когда вы хотите также проверить существующие правила нормализации, определить, какое из них нужно удалить, а затем использовать его индекс для удаления.</span><span class="sxs-lookup"><span data-stu-id="3e9b1-174">Run the following when you want to also examine the existing normalization rules, determine which one you want to delete, and then use its index to remove it.</span></span> <span data-ttu-id="3e9b1-175">Массив правил нормализации начинается с индекса 0.</span><span class="sxs-lookup"><span data-stu-id="3e9b1-175">The array of normalization rules starts with index 0.</span></span> <span data-ttu-id="3e9b1-176">Если мы хотим удалить з-х цифровое правило нормализации, индекс будет 1.</span><span class="sxs-lookup"><span data-stu-id="3e9b1-176">We would like to remove the 3-digit normalization rule, so that is index 1.</span></span>
  
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

<span data-ttu-id="3e9b1-177">Запустите эту команду для поиска всех пользователей, которым была присвоена абонентская группа клиента RedmondDialPlan.</span><span class="sxs-lookup"><span data-stu-id="3e9b1-177">Run this to find all users who have been granted the RedmondDialPlan tenant dial plan.</span></span>
  
```PowerShell
Get-CsOnlineUser | Where-Object {$_.TenantDialPlan -eq "RedmondDialPlan"}
```

<span data-ttu-id="3e9b1-178">Запустите этот элемент, чтобы удалить все назначенные TenantDialPlan от всех пользователей, у которых есть HostingProvider из sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="3e9b1-178">Run this to remove any assigned TenantDialPlan from all users who have a HostingProvider of sipfed.online.lync.com.</span></span>
```PowerShell
Get-CsOnlineUser -Filter {HostingProvider -eq "sipfed.online.lync.com"} | Grant-CsTenantDialPlan -policyname $null
```

<span data-ttu-id="3e9b1-179">Запустите эту команду для добавления существующей локальной абонентской группы с именем OPDP1 в качестве абонентской группы клиента для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="3e9b1-179">Run these to add the existing on-premises dial plan named OPDP1 as a tenant dial plan for your organization.</span></span> <span data-ttu-id="3e9b1-180">Необходимо сначала сохранить локальную абонентскую группу в XML-файл, а затем использовать ее для создания новой абонентской группы клиента.</span><span class="sxs-lookup"><span data-stu-id="3e9b1-180">You need to first save the on-premises dial plan to an .xml file, and then use it to create the new tenant dial plan.</span></span>
  
<span data-ttu-id="3e9b1-181">Запустите эту команду для сохранения локальной абонентской группы в XML-файл.</span><span class="sxs-lookup"><span data-stu-id="3e9b1-181">Run this to save the on-premises dial plan to the .xml file.</span></span>
  
```PowerShell
$DPName = "OPDP1"
$DPFileName = "dialplan.xml"
Get-CsDialplan $DPName | Export-Clixml $DPFileName
```

<span data-ttu-id="3e9b1-182">Запустите эту команду для создания новой абонентской группы клиента.</span><span class="sxs-lookup"><span data-stu-id="3e9b1-182">Run this to create the new tenant dial plan.</span></span>
  
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
    
## <a name="related-topics"></a><span data-ttu-id="3e9b1-183">См. также</span><span class="sxs-lookup"><span data-stu-id="3e9b1-183">Related topics</span></span>

- [<span data-ttu-id="3e9b1-184">Что такое абонентские группы?</span><span class="sxs-lookup"><span data-stu-id="3e9b1-184">What are dial plans?</span></span>](what-are-dial-plans.md)
- [<span data-ttu-id="3e9b1-185">Общие вопросы по передаче номеров телефонов</span><span class="sxs-lookup"><span data-stu-id="3e9b1-185">Transferring phone numbers common questions</span></span>](transferring-phone-numbers-common-questions.md)
- [<span data-ttu-id="3e9b1-186">Типы номеров телефонов, используемые в планах звонков</span><span class="sxs-lookup"><span data-stu-id="3e9b1-186">Different kinds of phone numbers used for Calling Plans</span></span>](different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [<span data-ttu-id="3e9b1-187">Управление номерами телефонов организации</span><span class="sxs-lookup"><span data-stu-id="3e9b1-187">Manage phone numbers for your organization</span></span>](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)
- [<span data-ttu-id="3e9b1-188">Условия и положения, распространяющиеся на экстренные вызовы</span><span class="sxs-lookup"><span data-stu-id="3e9b1-188">Emergency calling terms and conditions</span></span>](emergency-calling-terms-and-conditions.md)
- <span data-ttu-id="3e9b1-189">[Метка отказа в звонке в экстренном случае](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="3e9b1-189">[Emergency calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>
- [<span data-ttu-id="3e9b1-190">Обзор PowerShell в Teams</span><span class="sxs-lookup"><span data-stu-id="3e9b1-190">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
