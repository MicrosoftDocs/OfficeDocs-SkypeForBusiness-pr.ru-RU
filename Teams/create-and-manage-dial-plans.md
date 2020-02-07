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
description: Сведения о том, как создавать абонентские группы и управлять ими (абонентские группы для звонков по коммутируемой телефонной связи) и как управлять ими.
ms.openlocfilehash: 774b0a78f39b91b634ed0833be3497935cb25c4f
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41826927"
---
# <a name="create-and-manage-dial-plans"></a><span data-ttu-id="8d0d2-103">Создание и использование абонентских групп</span><span class="sxs-lookup"><span data-stu-id="8d0d2-103">Create and manage dial plans</span></span>

<span data-ttu-id="8d0d2-104">После того как вы запланируете абонентские группы для Организации и выйдете все правила нормализации, которые необходимо создать для маршрутизации звонков, вы можете создать абонентские группы.</span><span class="sxs-lookup"><span data-stu-id="8d0d2-104">After you plan the dial plans for your organization and figured out all the normalization rules that need to be created for call routing, you're ready to create the dial plans.</span></span> <span data-ttu-id="8d0d2-105">Вы можете использовать центр администрирования Microsoft Teams или Windows PowerShell для создания абонентских групп и управления ими.</span><span class="sxs-lookup"><span data-stu-id="8d0d2-105">You can use the Microsoft Teams admin center or Windows PowerShell to create and manage dial plans.</span></span>  

## <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="8d0d2-106">Использование центра администрирования Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8d0d2-106">Using the Microsoft Teams admin center</span></span>

### <a name="create-a-dial-plan"></a><span data-ttu-id="8d0d2-107">Создание абонентской группы</span><span class="sxs-lookup"><span data-stu-id="8d0d2-107">Create a dial plan</span></span>

1. <span data-ttu-id="8d0d2-108">В левой области навигации центра администрирования Microsoft Teams выберите > **абонентская** **абонентская**группа.</span><span class="sxs-lookup"><span data-stu-id="8d0d2-108">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Dial plan**.</span></span>
2. <span data-ttu-id="8d0d2-109">Нажмите кнопку **Добавить**, а затем введите имя и описание абонентского плана.</span><span class="sxs-lookup"><span data-stu-id="8d0d2-109">Click **Add**, and then enter a name and description for the dial plan.</span></span>
    <span data-ttu-id="8d0d2-110">![Снимок экрана, на котором показана страница "Добавление" для создания абонентской группы](media/create-dial-plan.png)</span><span class="sxs-lookup"><span data-stu-id="8d0d2-110">![Screenshot showing the Add page for creating a dial plan](media/create-dial-plan.png)</span></span>
3. <span data-ttu-id="8d0d2-111">В разделе **сведения о абонентской схеме**укажите внешний префикс набора номера, если пользователям необходимо набрать одну или несколько начальных цифр (например, 9), чтобы получить внешнюю строку.</span><span class="sxs-lookup"><span data-stu-id="8d0d2-111">Under **Dial plan details**, specify an external dialing prefix if users need to dial one or more additional leading digits (for example, 9) to get an external line.</span></span> <span data-ttu-id="8d0d2-112">Для этого выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="8d0d2-112">To do this:</span></span>
    1. <span data-ttu-id="8d0d2-113">В поле **Префикс внешнего набора** введите внешний префикс.</span><span class="sxs-lookup"><span data-stu-id="8d0d2-113">In the **External dialing prefix** box, enter an external dialing prefix.</span></span> <span data-ttu-id="8d0d2-114">Префикс может состоять не более чем из четырех знаков (#, \* и 0-9).</span><span class="sxs-lookup"><span data-stu-id="8d0d2-114">The prefix can be up to four characters (#,\*, and 0-9).</span></span>
    2. <span data-ttu-id="8d0d2-115">Включите **оптимизированный набор номера для устройств**.</span><span class="sxs-lookup"><span data-stu-id="8d0d2-115">Turn on **Optimized device dialing**.</span></span> <span data-ttu-id="8d0d2-116">Если указан внешний префикс набора номера, необходимо также включить этот параметр, чтобы применить префикс, чтобы звонки могли выполняться за пределами Организации.</span><span class="sxs-lookup"><span data-stu-id="8d0d2-116">If you specify an external dialing prefix, you must also turn on this setting to apply the prefix so calls can be made outside your organization.</span></span>
4. <span data-ttu-id="8d0d2-117">В разделе **правила нормализации**настройте и свяжите одно или несколько [правил нормализации](what-are-dial-plans.md#normalization-rules) для абонентской группы.</span><span class="sxs-lookup"><span data-stu-id="8d0d2-117">Under **Normalization rules**, configure and associate one or more [normalization rules](what-are-dial-plans.md#normalization-rules) for the dial plan.</span></span> <span data-ttu-id="8d0d2-118">Каждая абонентская группа должна иметь по крайней мере одно связанное с ним правило нормализации.</span><span class="sxs-lookup"><span data-stu-id="8d0d2-118">Each dial plan must have at least one normalization rule associated with it.</span></span>  <span data-ttu-id="8d0d2-119">Чтобы сделать это, выполните одно или несколько из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="8d0d2-119">To do this, do one or more of the following:</span></span>
    - <span data-ttu-id="8d0d2-120">Чтобы создать новое правило нормализации и связать его с абонентской панелью, нажмите кнопку **Добавить**, а затем укажите правило.</span><span class="sxs-lookup"><span data-stu-id="8d0d2-120">To create a new normalization rule and associate it with the dial plan, click **Add**, and then define the rule.</span></span>
    - <span data-ttu-id="8d0d2-121">Чтобы изменить правило нормализации, уже связанное с абонентской панелью, выберите правило, щелкнув слева от имени правила, а затем нажмите кнопку **изменить**.</span><span class="sxs-lookup"><span data-stu-id="8d0d2-121">To edit a normalization rule that's already associated with the dial plan, select the rule by clicking to the left of the rule name, and then click **Edit**.</span></span> <span data-ttu-id="8d0d2-122">Внесите нужные изменения и нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="8d0d2-122">Make the changes you want, and then click **Save**.</span></span>
    - <span data-ttu-id="8d0d2-123">Чтобы удалить правило нормализации абонентской группы, выберите правило, щелкнув слева от имени правила, а затем нажмите кнопку **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="8d0d2-123">To remove a normalization rule from the dial plan, select the rule by clicking to the left of the rule name, and then click **Remove**.</span></span>
5. <span data-ttu-id="8d0d2-124">Расположите правила нормализации в нужном порядке.</span><span class="sxs-lookup"><span data-stu-id="8d0d2-124">Arrange the normalization rules in the order that you want.</span></span> <span data-ttu-id="8d0d2-125">Нажмите кнопку **переместить вверх** или **Переместить вниз** , чтобы изменить расположение правил в списке.</span><span class="sxs-lookup"><span data-stu-id="8d0d2-125">Click **Move up** or **Move down** to change the position of rules in the list.</span></span>

    > [!NOTE]
    > <span data-ttu-id="8d0d2-126">Teams обходит список правил нормализации сверху вниз и использует первое правило, которое соответствует номеру набора.</span><span class="sxs-lookup"><span data-stu-id="8d0d2-126">Teams traverses the list of normalization rules from the top down and uses the first rule that matches the dialed number.</span></span> <span data-ttu-id="8d0d2-127">Если вы настроили абонентскую группу таким образом, чтобы номер с набором номера мог совпадать с более чем одним правилом нормализации, убедитесь в том, что более ограниченные правила сортируются над менее строгими.</span><span class="sxs-lookup"><span data-stu-id="8d0d2-127">If you set up a dial plan so that a dialed number can match more than one normalization rule, make sure the more restrictive rules are sorted above the less restrictive ones.</span></span>

6. <span data-ttu-id="8d0d2-128">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="8d0d2-128">Click **Save**.</span></span>
7. <span data-ttu-id="8d0d2-129">Если вы хотите протестировать абонентскую группу, в разделе **Проверка абонентской группы**введите номер телефона и нажмите кнопку **проверить**.</span><span class="sxs-lookup"><span data-stu-id="8d0d2-129">If you want to test the dial plan, under **Test dial plan**, enter a phone number, and then click **Test**.</span></span>

### <a name="edit-a-dial-plan"></a><span data-ttu-id="8d0d2-130">Изменение абонентской группы</span><span class="sxs-lookup"><span data-stu-id="8d0d2-130">Edit a dial plan</span></span>

1. <span data-ttu-id="8d0d2-131">В левой области навигации центра администрирования Microsoft Teams выберите > **абонентская** **абонентская**группа.</span><span class="sxs-lookup"><span data-stu-id="8d0d2-131">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Dial plan**.</span></span>
2. <span data-ttu-id="8d0d2-132">Выберите абонентскую группу, щелкнув слева от имени абонентской группы, а затем нажмите кнопку **изменить**.</span><span class="sxs-lookup"><span data-stu-id="8d0d2-132">Select the dial plan by clicking to the left of the dial plan name, and then click **Edit**.</span></span>
3. <span data-ttu-id="8d0d2-133">Внесите нужные изменения и нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="8d0d2-133">Make the changes that you want, and then click **Save**.</span></span>

### <a name="add-users-to-a-dial-plan"></a><span data-ttu-id="8d0d2-134">Добавление пользователей в абонентскую группу</span><span class="sxs-lookup"><span data-stu-id="8d0d2-134">Add users to a dial plan</span></span>

1. <span data-ttu-id="8d0d2-135">В левой области навигации центра администрирования Microsoft Teams выберите > **абонентская** **абонентская**группа.</span><span class="sxs-lookup"><span data-stu-id="8d0d2-135">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Dial plan**.</span></span>
2. <span data-ttu-id="8d0d2-136">Выберите абонентскую группу, щелкнув слева от нее в качестве имени абонентского плана.</span><span class="sxs-lookup"><span data-stu-id="8d0d2-136">Select the dial plan by clicking to the left of the dial plan name.</span></span>
3. <span data-ttu-id="8d0d2-137">Выберите **Управление пользователями**.</span><span class="sxs-lookup"><span data-stu-id="8d0d2-137">Select **Manage users**.</span></span>
4. <span data-ttu-id="8d0d2-138">В области **Управление пользователями** найдите пользователя по отображаемому имени или по имени пользователя, выберите имя и нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="8d0d2-138">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="8d0d2-139">Повторите этот шаг для каждого пользователя, которого вы хотите добавить.</span><span class="sxs-lookup"><span data-stu-id="8d0d2-139">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="8d0d2-140">Завершив добавление пользователей, нажмите кнопку **Применить**.</span><span class="sxs-lookup"><span data-stu-id="8d0d2-140">When you're finished adding users, select **Apply**.</span></span>

## <a name="using-powershell"></a><span data-ttu-id="8d0d2-141">Использование PowerShell</span><span class="sxs-lookup"><span data-stu-id="8d0d2-141">Using PowerShell</span></span>
  
### <a name="verify-and-start-remote-powershell"></a><span data-ttu-id="8d0d2-142">Проверка и запуск удаленной оболочки PowerShell</span><span class="sxs-lookup"><span data-stu-id="8d0d2-142">Verify and start Remote PowerShell</span></span>

 <span data-ttu-id="8d0d2-143">**Убедитесь в том, что вы используете Windows PowerShell версии 3,0 или более поздней.**</span><span class="sxs-lookup"><span data-stu-id="8d0d2-143">**Check that you are running Windows PowerShell version 3.0 or later**</span></span>
  
1. <span data-ttu-id="8d0d2-144">Чтобы убедиться в том, что у вас установлена версия 3,0 или выше: **меню** > "Пуск"**Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="8d0d2-144">To verify that you're running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="8d0d2-145">Проверьте версию, введя в окне _Windows PowerShell_ команду **Get-Host**.</span><span class="sxs-lookup"><span data-stu-id="8d0d2-145">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="8d0d2-146">Если у вас нет версии 3,0 или более поздней, скачайте и установите обновления для Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8d0d2-146">If you don't have version 3.0 or later, download and install updates to Windows PowerShell.</span></span> <span data-ttu-id="8d0d2-147">Чтобы скачать и обновить Windows PowerShell до версии 4,0, ознакомьтесь с разгрузкой [платформы Windows Management Framework 4,0](https://go.microsoft.com/fwlink/?LinkId=716845) .</span><span class="sxs-lookup"><span data-stu-id="8d0d2-147">See [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0.</span></span> <span data-ttu-id="8d0d2-148">Перезагрузите компьютер после появления соответствующего запроса.</span><span class="sxs-lookup"><span data-stu-id="8d0d2-148">Restart your computer when you're prompted.</span></span>
    
4. <span data-ttu-id="8d0d2-149">Кроме того, вам потребуется установить модуль Windows PowerShell для Skype для бизнеса Online, который позволяет создавать удаленные сеансы Windows PowerShell, которые подключаются к Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="8d0d2-149">You'll also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span> <span data-ttu-id="8d0d2-150">Вы можете скачать этот модуль, который поддерживается только на компьютерах с 64-разрядными компьютерами и в [модуле Windows PowerShell для Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=294688).</span><span class="sxs-lookup"><span data-stu-id="8d0d2-150">You can download this module, which is supported only on 64-bit computers, at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688).</span></span> <span data-ttu-id="8d0d2-151">Перезагрузите компьютер, если будет предложено.</span><span class="sxs-lookup"><span data-stu-id="8d0d2-151">Restart your computer if you're prompted.</span></span>
    
<span data-ttu-id="8d0d2-152">Дополнительные сведения можно найти в разделе [подключение ко всем службам Office 365 в одном окне Windows PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span><span class="sxs-lookup"><span data-stu-id="8d0d2-152">To learn more, see [Connect to all Office 365 services in a single Windows PowerShell window](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span></span>
  
 <span data-ttu-id="8d0d2-153">**Запуск сеанса Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="8d0d2-153">**Start a Windows PowerShell session**</span></span>
  
1. <span data-ttu-id="8d0d2-154">Нажмите кнопку **запустить** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="8d0d2-154">Click **Start** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="8d0d2-155">В окне **Windows PowerShell** подключитесь к организации Office 365, выполнив следующую команду:</span><span class="sxs-lookup"><span data-stu-id="8d0d2-155">In the **Windows PowerShell** window, connect to your Office 365 organization by running:</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="8d0d2-156">Команду **Import-Module** нужно запускать только при первом использовании модуля Windows PowerShell в Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="8d0d2-156">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>
  

    ```PowerShell
    Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
    ```
  
### <a name="create-and-manage-your-dial-plans"></a><span data-ttu-id="8d0d2-157">Создание абонентских планов и управление ими</span><span class="sxs-lookup"><span data-stu-id="8d0d2-157">Create and manage your dial plans</span></span>

<span data-ttu-id="8d0d2-158">Создание абонентских групп клиентов и управление ими можно осуществлять с помощью одиночного командлета или сценария PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8d0d2-158">You can either use a single cmdlet or a PowerShell script to create and manage tenant dial plans.</span></span>
  
#### <a name="using-single-cmdlets"></a><span data-ttu-id="8d0d2-159">С помощью одиночного командлета</span><span class="sxs-lookup"><span data-stu-id="8d0d2-159">Using single cmdlets</span></span>

- <span data-ttu-id="8d0d2-160">Чтобы создать новую абонентскую группу, выполните:</span><span class="sxs-lookup"><span data-stu-id="8d0d2-160">To create a new dial plan, run:</span></span>
    
  ```PowerShell
  New-CsTenantDialPlan -Identity RedmondDialPlan -Description "Dial Plan for Redmond" -NormalizationRules <pslistmodifier> -ExternalAccessPrefix 9 -SimpleName "Dial-Plan-for-Redmond"
  ```

    <span data-ttu-id="8d0d2-161">Другие примеры и параметры см. в разделе [New-CsTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/new-cstenantdialplan).</span><span class="sxs-lookup"><span data-stu-id="8d0d2-161">For other examples and parameters, see [New-CsTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/new-cstenantdialplan).</span></span>
    
- <span data-ttu-id="8d0d2-162">Чтобы изменить параметры существующей абонентской группы, выполните:</span><span class="sxs-lookup"><span data-stu-id="8d0d2-162">To edit the settings of an existing dial plan, run:</span></span>
    
  ```PowerShell
  Set-CsTenantDialPlan -Identity RedmondDialPlan  -NormalizationRules <pslistmodifier> -ExternalAccessPrefix 9
    -SimpleName "Dial-Plan-for-Redmond"
  ```

    <span data-ttu-id="8d0d2-163">Другие примеры и параметры см. в разделе [Set-CsTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/set-cstenantdialplan).</span><span class="sxs-lookup"><span data-stu-id="8d0d2-163">For other examples and parameters, see [Set-CsTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/set-cstenantdialplan).</span></span>
    
- <span data-ttu-id="8d0d2-164">Чтобы добавить пользователей в абонентскую группу, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="8d0d2-164">To add users to a dial plan, run:</span></span>
    
  ```PowerShell
  Grant-CsTenantDialPlan -Identity amos.marble@contoso.com -PolicyName RedmondDialPlan
  ```

    <span data-ttu-id="8d0d2-165">Другие примеры и параметры см. в разделе [Grant-CsTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-cstenantdialplan).</span><span class="sxs-lookup"><span data-stu-id="8d0d2-165">For other examples and parameters, see [Grant-CsTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-cstenantdialplan).</span></span>
    
- <span data-ttu-id="8d0d2-166">Чтобы просмотреть параметры абонентской группы, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="8d0d2-166">To view the settings on a dial plan, run:</span></span>
    
  ```PowerShell
  Get-CsTenantDialPlan -Identity RedmondDialPlan
  ```

    <span data-ttu-id="8d0d2-167">Другие примеры и параметры см. в разделе [Get-CsTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/get-cstenantdialplan?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="8d0d2-167">For other examples and parameters, see [Get-CsTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/get-cstenantdialplan?view=skype-ps).</span></span>
    
- <span data-ttu-id="8d0d2-168">Чтобы удалить абонентскую группу, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="8d0d2-168">To delete a dial plan, run:</span></span>
    
  ```PowerShell
  Remove-CsTenantDialPlan -Identity RedmondDialPlan -force
  ```

    <span data-ttu-id="8d0d2-169">Другие примеры и параметры см. в разделе [Remove-CsTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/remove-cstenantdialplan?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="8d0d2-169">For other examples and parameters, see [Remove-CsTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/remove-cstenantdialplan?view=skype-ps).</span></span>
    
- <span data-ttu-id="8d0d2-170">Чтобы просмотреть параметры действующей абонентской группы, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="8d0d2-170">To see the settings of the effective dial plan, run:</span></span>
    
  ```PowerShell
  Get-CsEffectiveTenantDialPlan -Identity amos.marble@contoso.com
  ```

    <span data-ttu-id="8d0d2-171">Другие примеры и параметры см. в разделе [Get-CsEffectiveTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/get-cseffectivetenantdialplan).</span><span class="sxs-lookup"><span data-stu-id="8d0d2-171">For other examples and parameters, see [Get-CsEffectiveTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/get-cseffectivetenantdialplan).</span></span>
    
- <span data-ttu-id="8d0d2-172">Для проверки действующих параметров абонентской группы запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="8d0d2-172">To test the effective settings of a dial plan, run:</span></span>
    
  ```PowerShell
  Test-CsEffectiveTenantDialPlan -DialedNumber 14255550199 -Identity amos.marble@contoso.com
  ```

    <span data-ttu-id="8d0d2-173">Другие примеры и параметры см. в разделе [Test-CsEffectiveTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/test-cseffectivetenantdialplan?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="8d0d2-173">For other examples and parameters, see [Test-CsEffectiveTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/test-cseffectivetenantdialplan?view=skype-ps).</span></span>
    
#### <a name="using-a-powershell-script"></a><span data-ttu-id="8d0d2-174">С помощью скрипта PowerShell</span><span class="sxs-lookup"><span data-stu-id="8d0d2-174">Using a PowerShell script</span></span>

<span data-ttu-id="8d0d2-175">Запустите этот параметр, чтобы удалить правило нормализации, связанное с абонентской планом клиента, не требуя сначала удалить абонентскую группу.</span><span class="sxs-lookup"><span data-stu-id="8d0d2-175">Run this to delete a normalization rule that is associated with a tenant dial plan without needing to delete the tenant dial plan first:</span></span>
```PowerShell
$b1=New-CsVoiceNormalizationRule -Identity Global/NR4 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{add=$b1}
(Get-CsTenantDialPlan -Identity RedmondDialPlan).NormalizationRules
$b2=New-CsVoiceNormalizationRule -Identity Global/NR4 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{remove=$b2}
```
<span data-ttu-id="8d0d2-176">Запустите эту команду для добавления следующего правила нормализации к существующему клиенту абонентской группы с именем RedmondDialPlan.</span><span class="sxs-lookup"><span data-stu-id="8d0d2-176">Run this to add the following normalization rule to the existing tenant dial plan named RedmondDialPlan.</span></span>
```PowerShell
$nr1=New-CsVoiceNormalizationRule -Parent Global -Description 'Organization extension dialing' -Pattern '^(\\d{3})$' -Translation '+14255551$1' -Name NR1 -IsInternalExtension $false -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{add=$nr1}
```
<span data-ttu-id="8d0d2-177">Запустите эту команду для удаления следующего правила нормализации из существующего клиента абонентской группы с именем RedmondDialPlan.</span><span class="sxs-lookup"><span data-stu-id="8d0d2-177">Run this to remove the following normalization rule from the existing tenant dial plan named RedmondDialPlan.</span></span>
```PowerShell
$nr1=New-CsVoiceNormalizationRule -Parent Global/NR1 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{remove=$nr1}
```

<span data-ttu-id="8d0d2-178">Запустите следующую команду, когда вы хотите также проверить существующие правила нормализации, определить, какое из них нужно удалить, а затем использовать его индекс для удаления.</span><span class="sxs-lookup"><span data-stu-id="8d0d2-178">Run the following when you want to also examine the existing normalization rules, determine which one you want to delete, and then use its index to remove it.</span></span> <span data-ttu-id="8d0d2-179">Массив правил нормализации начинается с индекса 0.</span><span class="sxs-lookup"><span data-stu-id="8d0d2-179">The array of normalization rules starts with index 0.</span></span> <span data-ttu-id="8d0d2-180">Если мы хотим удалить з-х цифровое правило нормализации, индекс будет 1.</span><span class="sxs-lookup"><span data-stu-id="8d0d2-180">We would like to remove the 3-digit normalization rule, so that is index 1.</span></span>
  
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

<span data-ttu-id="8d0d2-181">Запустите эту команду для поиска всех пользователей, которым была присвоена абонентская группа клиента RedmondDialPlan.</span><span class="sxs-lookup"><span data-stu-id="8d0d2-181">Run this to find all users who have been granted the RedmondDialPlan tenant dial plan.</span></span>
  
```PowerShell
Get-CsOnlineUser | Where-Object {$_.TenantDialPlan -eq "RedmondDialPlan"}
```

<span data-ttu-id="8d0d2-182">Запустите этот элемент, чтобы удалить все назначенные Тенантдиалплан от всех пользователей, у которых есть Хостингпровидер из sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="8d0d2-182">Run this to remove any assigned TenantDialPlan from all users who have a HostingProvider of sipfed.online.lync.com.</span></span>
```PowerShell
Get-CsOnlineUser -Filter {HostingProvider -eq “sipfed.online.lync.com”} | Grant-CsTenantDialPlan -policyname $null
```

<span data-ttu-id="8d0d2-183">Запустите эту команду для добавления существующей локальной абонентской группы с именем OPDP1 в качестве абонентской группы клиента для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="8d0d2-183">Run these to add the existing on-premises dial plan named OPDP1 as a tenant dial plan for your organization.</span></span> <span data-ttu-id="8d0d2-184">Необходимо сначала сохранить локальную абонентскую группу в XML-файл, а затем использовать ее для создания новой абонентской группы клиента.</span><span class="sxs-lookup"><span data-stu-id="8d0d2-184">You need to first save the on-premises dial plan to an .xml file, and then use it to create the new tenant dial plan.</span></span>
  
<span data-ttu-id="8d0d2-185">Запустите эту команду для сохранения локальной абонентской группы в XML-файл.</span><span class="sxs-lookup"><span data-stu-id="8d0d2-185">Run this to save the on-premises dial plan to the .xml file.</span></span>
  
```PowerShell
$DPName = "OPDP1"
$DPFileName = "dialplan.xml"
Get-CsDialplan $DPName | Export-Clixml $DPFileName
```

<span data-ttu-id="8d0d2-186">Запустите эту команду для создания новой абонентской группы клиента.</span><span class="sxs-lookup"><span data-stu-id="8d0d2-186">Run this to create the new tenant dial plan.</span></span>
  
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
    
## <a name="related-topics"></a><span data-ttu-id="8d0d2-187">См. также</span><span class="sxs-lookup"><span data-stu-id="8d0d2-187">Related topics</span></span>

- [<span data-ttu-id="8d0d2-188">Что такое абонентские группы?</span><span class="sxs-lookup"><span data-stu-id="8d0d2-188">What are dial plans?</span></span>](what-are-dial-plans.md)
- [<span data-ttu-id="8d0d2-189">Общие вопросы по передаче номеров телефонов</span><span class="sxs-lookup"><span data-stu-id="8d0d2-189">Transferring phone numbers common questions</span></span>](transferring-phone-numbers-common-questions.md)
- [<span data-ttu-id="8d0d2-190">Типы номеров телефонов, используемые в планах звонков</span><span class="sxs-lookup"><span data-stu-id="8d0d2-190">Different kinds of phone numbers used for Calling Plans</span></span>](different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [<span data-ttu-id="8d0d2-191">Управление номерами телефонов организации</span><span class="sxs-lookup"><span data-stu-id="8d0d2-191">Manage phone numbers for your organization</span></span>](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)
- [<span data-ttu-id="8d0d2-192">Условия и положения, распространяющиеся на экстренные вызовы</span><span class="sxs-lookup"><span data-stu-id="8d0d2-192">Emergency calling terms and conditions</span></span>](emergency-calling-terms-and-conditions.md)
- <span data-ttu-id="8d0d2-193">[Метка отказа в звонке в экстренном случае](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="8d0d2-193">[Emergency calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>
- [<span data-ttu-id="8d0d2-194">Обзор PowerShell в Teams</span><span class="sxs-lookup"><span data-stu-id="8d0d2-194">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
