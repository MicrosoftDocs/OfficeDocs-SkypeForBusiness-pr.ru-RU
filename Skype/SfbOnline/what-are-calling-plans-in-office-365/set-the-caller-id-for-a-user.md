---
title: Настройка идентификатора абонента для пользователя
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz
ms.topic: article
ms.assetid: c7323490-d9b7-421a-aa76-5bd485f80583
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Calling Plans
description: The Phone System in Office 365 provides a default caller ID that is the user's assigned telephone number. You can either change or block the caller ID (also called a Calling Line ID) for a user. You can learn more about how to use caller ID in your organization by going How can caller ID be used in your organization.
ms.openlocfilehash: 2f86e28a99c1c129943d97d58e97e73a355719ab
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/04/2018
ms.locfileid: "25371736"
---
# <a name="set-the-caller-id-for-a-user"></a><span data-ttu-id="d95f4-105">Настройка идентификатора абонента для пользователя</span><span class="sxs-lookup"><span data-stu-id="d95f4-105">Set the Caller ID for a user</span></span>
<span data-ttu-id="d95f4-p102">The Phone System in Office 365 provides a default caller ID that is the user's assigned telephone number. You can either change or block the caller ID (also called a Calling Line ID) for a user. You can learn more about how to use caller ID in your organization by going [How can caller ID be used in your organization](how-can-caller-id-be-used-in-your-organization.md).</span><span class="sxs-lookup"><span data-stu-id="d95f4-p102">The Phone System in Office 365 provides a default caller ID that is the user's assigned telephone number. You can either change or block the caller ID (also called a Calling Line ID) for a user. You can learn more about how to use caller ID in your organization by going [How can caller ID be used in your organization](how-can-caller-id-be-used-in-your-organization.md).</span></span>
  
> [!TIP]
> <span data-ttu-id="d95f4-109">В настоящее время в Skype для бизнеса Online невозможно заблокировать входящие вызовы.</span><span class="sxs-lookup"><span data-stu-id="d95f4-109">You can't block incoming calls currently in Skype for Business Online.</span></span> 
  
<span data-ttu-id="d95f4-110">Для изменения доступны следующие настройки:</span><span class="sxs-lookup"><span data-stu-id="d95f4-110">There are settings that you can change:</span></span>
  
> [!NOTE]
> <span data-ttu-id="d95f4-111">Эта функция **не предназначена** для организаций с локальными развертываниями Lync или Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="d95f4-111">This **is not** for on-premises organizations with Lync or Skype for Business Server.</span></span>
  
- <span data-ttu-id="d95f4-p103">**Изменить идентификатор исходящего абонента**. Вы можете заменить идентификатор абонента (по умолчанию соответствует номеру телефона, назначенному пользователю) другим номером. Например, вы можете заменить идентификатор абонента основным рабочим номером вашей организации или юридического отдела. В качестве идентификатора абонента можно указать любой номер **службы** в Интернете (как платный, так и бесплатный).</span><span class="sxs-lookup"><span data-stu-id="d95f4-p103">**Change their outgoing caller ID** You can replace a user's Caller ID, which by default is their telephone number, with another phone number. For example, you could change the user's Caller ID from their phone number to a main phone number for your business or change the user's Calling Line ID from their phone number to a main phone number for the legal department. You can change the Calling ID number to any Online **service** number (toll or toll-free).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="d95f4-115">Чтобы использовать параметр  _Service_, необходимо указать допустимый номер службы.</span><span class="sxs-lookup"><span data-stu-id="d95f4-115">If you want to use the  _Service_ parameter, you must specify a valid service number.</span></span>
  
- <span data-ttu-id="d95f4-p104">**Block their outbound caller ID** You can block the outgoing Caller ID from being sent on a user's outgoing PSTN calls. Doing this will block their phone number from being displayed on the phone of a person being called.</span><span class="sxs-lookup"><span data-stu-id="d95f4-p104">**Block their outbound caller ID** You can block the outgoing Caller ID from being sent on a user's outgoing PSTN calls. Doing this will block their phone number from being displayed on the phone of a person being called.</span></span>
    
- <span data-ttu-id="d95f4-118">**Блокировать их входящих идентификатора звонящего** Можно запретить пользователю получение идентификатора звонящего на входящие вызовы ТСОП.</span><span class="sxs-lookup"><span data-stu-id="d95f4-118">**Block their incoming caller ID** You can block a user from receiving Caller ID on any incoming PSTN calls.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="d95f4-119">При звонках в экстренные службы номер телефона пользователя (идентификатор абонента) передается всегда.</span><span class="sxs-lookup"><span data-stu-id="d95f4-119">Emergency calls will always send the user's telephone number (caller ID).</span></span> 
  
<span data-ttu-id="d95f4-p105">По умолчанию все параметры идентификатора абонента **отключены**. Это означает, что при звонке по телефону через ТСОП будет отображаться номер телефона пользователя в Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="d95f4-p105">By default, all of these caller ID settings are **turned off**. This means that the Skype for Business Online user's phone number can be seen when that user makes a call to a PSTN phone.</span></span>
  
<span data-ttu-id="d95f4-122">Дополнительные сведения об этих параметрах и их использовании см. [Как можно использовать идентификатор абонента в организации?](how-can-caller-id-be-used-in-your-organization.md).</span><span class="sxs-lookup"><span data-stu-id="d95f4-122">To learn more about these settings and how you can use them, go [How can caller ID be used in your organization](how-can-caller-id-be-used-in-your-organization.md).</span></span>
  
## <a name="set-your-caller-id-policy-settings"></a><span data-ttu-id="d95f4-123">Задание настроек политики идентификатора абонента</span><span class="sxs-lookup"><span data-stu-id="d95f4-123">Set your caller ID policy settings</span></span>

> [!NOTE]
> <span data-ttu-id="d95f4-124">Для всех параметров идентификатора звонящего в Скайп для бизнеса в Интернет необходимо использовать Windows PowerShell и **нельзя использовать** **Скайп по центру администрирования бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="d95f4-124">For all of the Caller ID settings in Skype for Business Online, you must use Windows PowerShell and you **can't use** the **Skype for Business admin center**.</span></span> 
  
### <a name="verify-and-start-windows-powershell"></a><span data-ttu-id="d95f4-125">Проверка и запуск Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d95f4-125">Verify and start Windows PowerShell</span></span>

- <span data-ttu-id="d95f4-126">**Убедитесь в том, что у вас установлена оболочка Windows PowerShell 3.0 или более поздней версии**</span><span class="sxs-lookup"><span data-stu-id="d95f4-126">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
    
1. <span data-ttu-id="d95f4-127">Чтобы убедиться, что запущена версия 3.0 или более поздняя версия: **Меню "Пуск"** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="d95f4-127">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="d95f4-128">Проверьте версию, введя в окне _Windows PowerShell_ команду **Get-Host**.</span><span class="sxs-lookup"><span data-stu-id="d95f4-128">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="d95f4-p106">Если у вас более ранняя версия, вам необходимо скачать и установить обновления для Windows PowerShell. Чтобы скачать и обновить Windows PowerShell до версии 4.0, перейдите на страницу [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845). При появлении запроса перезагрузите компьютер.</span><span class="sxs-lookup"><span data-stu-id="d95f4-p106">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell. See [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0. Restart your computer when you are prompted.</span></span>
    
4. <span data-ttu-id="d95f4-p107">Вам также потребуется установить модуль Windows PowerShell для Skype для бизнеса online, с помощью которого можно создать удаленный сеанс Windows PowerShell с подключением к Skype для бизнеса online. Этот модуль, который поддерживается только на 64-разрядных компьютерах, можно скачать в Центре загрузки Майкрософт на странице [Модуль Windows PowerShell для Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=294688). При появлении запроса перезагрузите компьютер.</span><span class="sxs-lookup"><span data-stu-id="d95f4-p107">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Restart your computer if you are prompted.</span></span>
    
    <span data-ttu-id="d95f4-135">Больше информации приведено в статье [Подключение ко всем службам Office 365 с помощью единого окна Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span><span class="sxs-lookup"><span data-stu-id="d95f4-135">If you need to know more, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span></span>
    
- <span data-ttu-id="d95f4-136">**Запуск сеанса Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="d95f4-136">**Start a Windows PowerShell session**</span></span>
    
1. <span data-ttu-id="d95f4-137">Из **меню "Пуск"** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="d95f4-137">From the **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="d95f4-138">В окне **Windows PowerShell** подключитесь к организации Office 365, выполнив следующую команду:</span><span class="sxs-lookup"><span data-stu-id="d95f4-138">In the **Windows PowerShell** window, connect to your Office 365 organization by running:</span></span>
    
   > [!NOTE]
   > <span data-ttu-id="d95f4-139">Команду **Import-Module** нужно запускать только при первом использовании модуля Windows PowerShell в Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="d95f4-139">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>
   > 
   > ```
   > Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
   > ```
   > 
   > ```
   > $credential = Get-Credential
   > ```
   > 
   > ```
   > $session = New-CsOnlineSession -Credential $credential
   > ```
   > 
   > ```
   > Import-PSSession $session
   > ```

<span data-ttu-id="d95f4-140">Дополнительные сведения о запуске Windows PowerShell, см [подключиться ко всем службам Office 365 в одном окне Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx) или [подключение к Скайп для бизнеса в Интернет с помощью Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="d95f4-140">If you want more information about starting Windows PowerShell, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx) or [Connecting to Skype for Business Online by using Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).</span></span>
    
### <a name="see-all-of-the-caller-id-policy-settings-in-your-organization"></a><span data-ttu-id="d95f4-141">Просмотр всех настроек политики идентификатора абонента в организации</span><span class="sxs-lookup"><span data-stu-id="d95f4-141">See all of the caller ID policy settings in your organization</span></span>

- <span data-ttu-id="d95f4-142">Чтобы просмотреть все параметры политики идентификатор звонящего в вашей организации, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="d95f4-142">To view all of the caller ID policy settings in your organization, run:</span></span>

  ```
  Get-CsCallingLineIdentity |fl
  ```
  <span data-ttu-id="d95f4-143">Просмотрите Дополнительные сведения и примеры для [Get-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793856.aspx).</span><span class="sxs-lookup"><span data-stu-id="d95f4-143">See more examples and details for [Get-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793856.aspx).</span></span>
    
### <a name="create-a-new-caller-id-policy-for-your-organization"></a><span data-ttu-id="d95f4-144">Создание политики идентификатора абонента для организации</span><span class="sxs-lookup"><span data-stu-id="d95f4-144">Create a new caller ID policy for your organization</span></span>


- <span data-ttu-id="d95f4-145">Чтобы создать новую политику идентификатор звонящего, который задает идентификатор звонящего для анонимного, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="d95f4-145">To create a new caller ID policy that sets the caller ID to anonymous, run:</span></span>
    
  ```
  New-CsCallingLineIdentity  -Identity Anonymous -Description "Anonymous policy" -CallingIDSubstitute Anonymous -EnableUserOverride $false
  ```
  > [!NOTE]  
  > <span data-ttu-id="d95f4-146">Во всех случаях поле «Номер службы» не должно содержать начальный символ «+».</span><span class="sxs-lookup"><span data-stu-id="d95f4-146">In all cases, the "Service Number" field should not include an initial "+".</span></span>

  <span data-ttu-id="d95f4-147">Просмотрите дополнительные примеры и подробные сведения для [New-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793855.aspx).</span><span class="sxs-lookup"><span data-stu-id="d95f4-147">See more examples and details for [New-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793855.aspx).</span></span>
    
- <span data-ttu-id="d95f4-148">Чтобы применить новую политику, которую вы создали мрамор Amos, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="d95f4-148">To apply the new policy you created to Amos Marble, run:</span></span>
    
  ```
   Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName Anonymous
  ```
  <span data-ttu-id="d95f4-149">Дополнительные сведения о командлете [Grant-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793857.aspx).</span><span class="sxs-lookup"><span data-stu-id="d95f4-149">See more on the [Grant-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793857.aspx) cmdlet.</span></span>
    
<span data-ttu-id="d95f4-150">Если вы уже создали политику, можно использовать командлет [Set-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793854.aspx) внесение изменений в существующую политику и затем используйте командлет [Grant-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793857.aspx) для применения параметров для пользователей.</span><span class="sxs-lookup"><span data-stu-id="d95f4-150">If you have already created a policy, you can use the [Set-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793854.aspx) cmdlet to make changes to the existing policy, and then use the [Grant-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793857.aspx) cmdlet to apply the settings to your users.</span></span>
  
### <a name="set-it-so-the-incoming-caller-id-is-blocked"></a><span data-ttu-id="d95f4-151">Блокировка идентификатора входящего абонента</span><span class="sxs-lookup"><span data-stu-id="d95f4-151">Set it so the incoming caller ID is blocked</span></span>

- <span data-ttu-id="d95f4-152">Чтобы блокировать входящие идентификатора звонящего, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="d95f4-152">To block the incoming caller ID, run:</span></span>
    
  ```
  Set-CsCallingLineIdentity  -Identity "Block Incoming" -BlockIncomingPstnCallerID $true -EnableUserOverride $true
  ```
  <span data-ttu-id="d95f4-153">Просмотрите Дополнительные сведения и примеры для [Set-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793854.aspx).</span><span class="sxs-lookup"><span data-stu-id="d95f4-153">See more examples and details for [Set-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793854.aspx).</span></span>
    
- <span data-ttu-id="d95f4-154">Чтобы применить политику, которую вы создали для пользователей в вашей организации, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="d95f4-154">To apply the policy setting you created to a user in your organization, run:</span></span>
    
  ```
  Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName "Block Incoming"
  ```
    <span data-ttu-id="d95f4-155">Дополнительные сведения о командлете [Grant-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793857.aspx).</span><span class="sxs-lookup"><span data-stu-id="d95f4-155">See more on the [Grant-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793857.aspx) cmdlet.</span></span>
    
### <a name="remove-a-caller-id-policy"></a><span data-ttu-id="d95f4-156">Удаление политики идентификатора абонента</span><span class="sxs-lookup"><span data-stu-id="d95f4-156">Remove a caller ID policy</span></span>

<span data-ttu-id="d95f4-157">Чтобы удалить политику организации, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="d95f4-157">To remove a policy from your organization, run:</span></span>
  
```
Remove-CsCallingLineIdentity -Identity "My Caller ID Policy"
```
<span data-ttu-id="d95f4-158">Чтобы удалить политику пользователя, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="d95f4-158">To remove a policy from a user, run:</span></span>
  
```
Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName $null
```
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="d95f4-159">Хотите узнать больше о Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="d95f4-159">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="d95f4-p108">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span><span class="sxs-lookup"><span data-stu-id="d95f4-p108">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="d95f4-163">Введение в Windows PowerShell и Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="d95f4-163">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="d95f4-164">Шесть причин использовать Windows PowerShell для управления Office 365 </span><span class="sxs-lookup"><span data-stu-id="d95f4-164">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Office 365 </span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="d95f4-p109">Windows PowerShell имеет множество преимуществ в скорости, простоте и эффективности работы по сравнению с использованием только Центра администрирования Office 365, например при внесении изменений для множества пользователей одновременно. Подробнее об этих преимуществах можно узнать в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="d95f4-p109">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="d95f4-167">Лучшие способы управления Office 365 с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d95f4-167">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="d95f4-168">Использование Windows PowerShell для управления Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="d95f4-168">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="d95f4-169">Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="d95f4-169">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
  
 ## <a name="related-topics"></a><span data-ttu-id="d95f4-170">См. также:</span><span class="sxs-lookup"><span data-stu-id="d95f4-170">Related topics</span></span>
[<span data-ttu-id="d95f4-171">Общие вопросы по передаче номеров телефонов</span><span class="sxs-lookup"><span data-stu-id="d95f4-171">Transferring phone numbers common questions</span></span>](/microsoftteams/transferring-phone-numbers-common-questions)

[<span data-ttu-id="d95f4-172">Типы номеров телефонов, используемые в планах звонков</span><span class="sxs-lookup"><span data-stu-id="d95f4-172">Different kinds of phone numbers used for Calling Plans</span></span>](/microsoftteams/different-kinds-of-phone-numbers-used-for-calling-plans)

[<span data-ttu-id="d95f4-173">Управление номерами телефонов организации</span><span class="sxs-lookup"><span data-stu-id="d95f4-173">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="d95f4-174">Дополнительные сведения об идентификаторе вызывающей линии и имени вызывающего абонента</span><span class="sxs-lookup"><span data-stu-id="d95f4-174">More about Calling Line ID and Calling Party Name</span></span>](../what-are-calling-plans-in-office-365/more-about-calling-line-ID-and-calling-party-name.md)

[<span data-ttu-id="d95f4-175">Условия и положения, распространяющиеся на экстренные вызовы</span><span class="sxs-lookup"><span data-stu-id="d95f4-175">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)

<span data-ttu-id="d95f4-176">[Skype для бизнеса Online: заявление об отказе для звонков в экстренные службы](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="d95f4-176">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>
 
