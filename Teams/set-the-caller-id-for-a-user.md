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
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Calling Plans
- seo-marvel-mar2020
description: Узнайте о ИДЕНТИФИКАТОРе вызывающего абонента Office 365 по умолчанию (назначенный пользователю номер телефона), также называемом ИДЕНТИФИКАТОРом телефонной линии. Вы можете изменить или заблокировать идентификатор звонящего пользователя.
ms.openlocfilehash: 3e19b1de929057880573c29ba75aa0ec1091139f
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "43780528"
---
# <a name="set-the-caller-id-for-a-user"></a><span data-ttu-id="5fd6d-104">Настройка идентификатора абонента для пользователя</span><span class="sxs-lookup"><span data-stu-id="5fd6d-104">Set the Caller ID for a user</span></span>
<span data-ttu-id="5fd6d-105">Телефонная система в Office 365 предоставляет стандартный идентификатор абонента. Он же является номером телефона, назначенным пользователю.</span><span class="sxs-lookup"><span data-stu-id="5fd6d-105">The Phone System in Office 365 provides a default caller ID that is the user's assigned telephone number.</span></span> <span data-ttu-id="5fd6d-106">Можно изменить или заблокировать идентификатор абонента (также называемый идентификатором вызывающей линии) для пользователя.</span><span class="sxs-lookup"><span data-stu-id="5fd6d-106">You can either change or block the caller ID (also called a Calling Line ID) for a user.</span></span> <span data-ttu-id="5fd6d-107">Дополнительные сведения об использовании идентификатора абонента в своей организации можно получить, перейдя к статье [Использование идентификатора абонента в организации](how-can-caller-id-be-used-in-your-organization.md).</span><span class="sxs-lookup"><span data-stu-id="5fd6d-107">You can learn more about how to use caller ID in your organization by going [How can caller ID be used in your organization](how-can-caller-id-be-used-in-your-organization.md).</span></span>
  
> [!TIP]
> <span data-ttu-id="5fd6d-108">В настоящее время в Skype для бизнеса Online невозможно заблокировать входящие вызовы.</span><span class="sxs-lookup"><span data-stu-id="5fd6d-108">You can't block incoming calls currently in Skype for Business Online.</span></span> 
  
<span data-ttu-id="5fd6d-109">Для изменения доступны следующие настройки:</span><span class="sxs-lookup"><span data-stu-id="5fd6d-109">There are settings that you can change:</span></span>
  
> [!NOTE]
> <span data-ttu-id="5fd6d-110">Эта функция **не предназначена** для организаций с локальными развертываниями Lync или Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="5fd6d-110">This **is not** for on-premises organizations with Lync or Skype for Business Server.</span></span>
  
- <span data-ttu-id="5fd6d-p103">**Изменить идентификатор исходящего абонента**. Вы можете заменить идентификатор абонента (по умолчанию соответствует номеру телефона, назначенному пользователю) другим номером. Например, вы можете заменить идентификатор абонента основным рабочим номером вашей организации или юридического отдела. В качестве идентификатора абонента можно указать любой номер **службы** в Интернете (как платный, так и бесплатный).</span><span class="sxs-lookup"><span data-stu-id="5fd6d-p103">**Change their outgoing caller ID** You can replace a user's Caller ID, which by default is their telephone number, with another phone number. For example, you could change the user's Caller ID from their phone number to a main phone number for your business or change the user's Calling Line ID from their phone number to a main phone number for the legal department. You can change the Calling ID number to any Online **service** number (toll or toll-free).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="5fd6d-114">Чтобы использовать параметр  _Service_, необходимо указать допустимый номер службы.</span><span class="sxs-lookup"><span data-stu-id="5fd6d-114">If you want to use the  _Service_ parameter, you must specify a valid service number.</span></span>
  
- <span data-ttu-id="5fd6d-115">**Блокировка идентификатора исходящего вызывающего абонента** Вы можете заблокировать поступающий идентификатор вызывающего абонента при исходящих звонках с помощью КТСОП пользователя.</span><span class="sxs-lookup"><span data-stu-id="5fd6d-115">**Block their outbound caller ID** You can block the outgoing Caller ID from being sent on a user's outgoing PSTN calls.</span></span> <span data-ttu-id="5fd6d-116">Это заблокирует отображение номера телефона на телефоне вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="5fd6d-116">Doing this will block their phone number from being displayed on the phone of a person being called.</span></span>
    
- <span data-ttu-id="5fd6d-117">**Блокировка идентификатора входящего вызывающего абонента** Вы можете запретить пользователю получать идентификатор вызывающего абонента во всех входящих звонках по сети PSTN.</span><span class="sxs-lookup"><span data-stu-id="5fd6d-117">**Block their incoming caller ID** You can block a user from receiving Caller ID on any incoming PSTN calls.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="5fd6d-118">При звонках в экстренные службы номер телефона пользователя (идентификатор абонента) передается всегда.</span><span class="sxs-lookup"><span data-stu-id="5fd6d-118">Emergency calls will always send the user's telephone number (caller ID).</span></span> 
  
<span data-ttu-id="5fd6d-p105">По умолчанию все параметры идентификатора абонента **отключены**. Это означает, что при звонке по телефону через ТСОП будет отображаться номер телефона пользователя в Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="5fd6d-p105">By default, all of these caller ID settings are **turned off**. This means that the Skype for Business Online user's phone number can be seen when that user makes a call to a PSTN phone.</span></span>
  
<span data-ttu-id="5fd6d-121">Дополнительные сведения об этих параметрах и их использовании см. [Как можно использовать идентификатор абонента в организации?](how-can-caller-id-be-used-in-your-organization.md).</span><span class="sxs-lookup"><span data-stu-id="5fd6d-121">To learn more about these settings and how you can use them, go [How can caller ID be used in your organization](how-can-caller-id-be-used-in-your-organization.md).</span></span>
  
## <a name="set-your-caller-id-policy-settings"></a><span data-ttu-id="5fd6d-122">Задание настроек политики идентификатора абонента</span><span class="sxs-lookup"><span data-stu-id="5fd6d-122">Set your caller ID policy settings</span></span>

> [!NOTE]
> <span data-ttu-id="5fd6d-123">Для всех параметров идентификации вызывающего абонента в Skype для бизнеса Online необходимо использовать Windows PowerShell и **нельзя использовать** **центр администрирования Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="5fd6d-123">For all of the Caller ID settings in Skype for Business Online, you must use Windows PowerShell and you **can't use** the **Skype for Business admin center**.</span></span> 
  
### <a name="verify-and-start-windows-powershell"></a><span data-ttu-id="5fd6d-124">Проверка и запуск Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="5fd6d-124">Verify and start Windows PowerShell</span></span>

- <span data-ttu-id="5fd6d-125">**Убедитесь в том, что у вас установлена оболочка Windows PowerShell 3.0 или более поздней версии**</span><span class="sxs-lookup"><span data-stu-id="5fd6d-125">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
    
1. <span data-ttu-id="5fd6d-126">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="5fd6d-126">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="5fd6d-127">Проверьте версию, введя в окне _Windows PowerShell_ команду **Get-Host**.</span><span class="sxs-lookup"><span data-stu-id="5fd6d-127">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="5fd6d-128">Если у вас более ранняя версия, вам необходимо скачать и установить обновления для Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5fd6d-128">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell.</span></span> <span data-ttu-id="5fd6d-129">Чтобы скачать и обновить Windows PowerShell до версии 4,0, ознакомьтесь с разгрузкой [платформы Windows Management Framework 4,0](https://go.microsoft.com/fwlink/?LinkId=716845) .</span><span class="sxs-lookup"><span data-stu-id="5fd6d-129">See [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0.</span></span> <span data-ttu-id="5fd6d-130">При появлении запроса перезагрузите компьютер.</span><span class="sxs-lookup"><span data-stu-id="5fd6d-130">Restart your computer when you are prompted.</span></span>
    
4. <span data-ttu-id="5fd6d-p107">Вам также потребуется установить модуль Windows PowerShell для Skype для бизнеса online, с помощью которого можно создать удаленный сеанс Windows PowerShell с подключением к Skype для бизнеса online. Этот модуль, который поддерживается только на 64-разрядных компьютерах, можно скачать в Центре загрузки Майкрософт на странице [Модуль Windows PowerShell для Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=294688). При появлении запроса перезагрузите компьютер.</span><span class="sxs-lookup"><span data-stu-id="5fd6d-p107">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Restart your computer if you are prompted.</span></span>
    
    <span data-ttu-id="5fd6d-134">Больше информации приведено в статье [Подключение ко всем службам Office 365 с помощью единого окна Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx).</span><span class="sxs-lookup"><span data-stu-id="5fd6d-134">If you need to know more, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx).</span></span>
    
- <span data-ttu-id="5fd6d-135">**Запуск сеанса Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="5fd6d-135">**Start a Windows PowerShell session**</span></span>
    
1. <span data-ttu-id="5fd6d-136">From the **Start Menu** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="5fd6d-136">From the **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="5fd6d-137">В окне **Windows PowerShell** подключитесь к службе Microsoft 365 или Office 365, выполнив следующие действия:</span><span class="sxs-lookup"><span data-stu-id="5fd6d-137">In the **Windows PowerShell** window, connect to your Microsoft 365 or Office 365 by running:</span></span>
    
   > [!NOTE]
   > <span data-ttu-id="5fd6d-138">Команду **Import-Module** нужно запускать только при первом использовании модуля Windows PowerShell в Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="5fd6d-138">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>
   > 
   ```PowerShell
    Import-Module -Name SkypeOnlineConnector
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
   ```

<span data-ttu-id="5fd6d-139">Если вы хотите получить дополнительные сведения о запуске Windows PowerShell, ознакомьтесь со статьей [подключение ко всем службам Office 365 в одном окне Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx) или [Настройка компьютера для Windows PowerShell](/skypeforbusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="5fd6d-139">If you want more information about starting Windows PowerShell, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx) or [Set up your computer for Windows PowerShell](/skypeforbusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>
    
### <a name="see-all-of-the-caller-id-policy-settings-in-your-organization"></a><span data-ttu-id="5fd6d-140">Просмотр всех настроек политики идентификатора абонента в организации</span><span class="sxs-lookup"><span data-stu-id="5fd6d-140">See all of the caller ID policy settings in your organization</span></span>

- <span data-ttu-id="5fd6d-141">Чтобы просмотреть все параметры политики идентификации вызывающего абонента в Организации, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="5fd6d-141">To view all of the caller ID policy settings in your organization, run:</span></span>

  ```PowerShell
  Get-CsCallingLineIdentity |fl
  ```
  <span data-ttu-id="5fd6d-142">Ознакомьтесь с дополнительными примерами и подробными сведениями о [Get-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793856.aspx).</span><span class="sxs-lookup"><span data-stu-id="5fd6d-142">See more examples and details for [Get-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793856.aspx).</span></span>
    
### <a name="create-a-new-caller-id-policy-for-your-organization"></a><span data-ttu-id="5fd6d-143">Создание политики идентификатора абонента для организации</span><span class="sxs-lookup"><span data-stu-id="5fd6d-143">Create a new caller ID policy for your organization</span></span>


- <span data-ttu-id="5fd6d-144">Чтобы создать политику идентификации вызывающего абонента, которая устанавливает анонимный идентификатор вызывающего абонента, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="5fd6d-144">To create a new caller ID policy that sets the caller ID to anonymous, run:</span></span>
    
  ```PowerShell
  New-CsCallingLineIdentity  -Identity Anonymous -Description "Anonymous policy" -CallingIDSubstitute Anonymous -EnableUserOverride $false
  ```
  > [!NOTE]  
  > <span data-ttu-id="5fd6d-145">Во всех случаях поле «Номер службы» не должно содержать начальный символ «+».</span><span class="sxs-lookup"><span data-stu-id="5fd6d-145">In all cases, the "Service Number" field should not include an initial "+".</span></span>

  <span data-ttu-id="5fd6d-146">Ознакомьтесь с дополнительными примерами и подробными сведениями о [новых ВозCsCallingLineIdentityх](https://technet.microsoft.com/library/mt793855.aspx).</span><span class="sxs-lookup"><span data-stu-id="5fd6d-146">See more examples and details for [New-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793855.aspx).</span></span>
    
- <span data-ttu-id="5fd6d-147">Чтобы применить новую политику, созданную для Иван мрамора, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="5fd6d-147">To apply the new policy you created to Amos Marble, run:</span></span>
    
  ```PowerShell
   Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName Anonymous
  ```
  <span data-ttu-id="5fd6d-148">Дополнительные сведения о командлете [Grant-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793857.aspx).</span><span class="sxs-lookup"><span data-stu-id="5fd6d-148">See more on the [Grant-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793857.aspx) cmdlet.</span></span>
    
<span data-ttu-id="5fd6d-149">Если вы уже создали политику, вы можете использовать командлет [Set-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793854.aspx) , чтобы внести изменения в существующую политику, а затем использовать командлет [Grant-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793857.aspx) , чтобы применить параметры к вашим пользователям.</span><span class="sxs-lookup"><span data-stu-id="5fd6d-149">If you have already created a policy, you can use the [Set-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793854.aspx) cmdlet to make changes to the existing policy, and then use the [Grant-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793857.aspx) cmdlet to apply the settings to your users.</span></span>
  
### <a name="set-it-so-the-incoming-caller-id-is-blocked"></a><span data-ttu-id="5fd6d-150">Блокировка идентификатора входящего абонента</span><span class="sxs-lookup"><span data-stu-id="5fd6d-150">Set it so the incoming caller ID is blocked</span></span>

- <span data-ttu-id="5fd6d-151">Чтобы заблокировать входящий идентификатор вызывающего абонента, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="5fd6d-151">To block the incoming caller ID, run:</span></span>
    
  ```PowerShell
  Set-CsCallingLineIdentity  -Identity "Block Incoming" -BlockIncomingPstnCallerID $true -EnableUserOverride $true
  ```
  <span data-ttu-id="5fd6d-152">Ознакомьтесь с дополнительными примерами и подробными сведениями о [Set-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793854.aspx).</span><span class="sxs-lookup"><span data-stu-id="5fd6d-152">See more examples and details for [Set-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793854.aspx).</span></span>
    
- <span data-ttu-id="5fd6d-153">Чтобы применить параметр политики, созданный для пользователя в Организации, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="5fd6d-153">To apply the policy setting you created to a user in your organization, run:</span></span>
    
  ```PowerShell
  Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName "Block Incoming"
  ```
    <span data-ttu-id="5fd6d-154">Дополнительные сведения о командлете [Grant-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793857.aspx).</span><span class="sxs-lookup"><span data-stu-id="5fd6d-154">See more on the [Grant-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793857.aspx) cmdlet.</span></span>
    
### <a name="remove-a-caller-id-policy"></a><span data-ttu-id="5fd6d-155">Удаление политики идентификатора абонента</span><span class="sxs-lookup"><span data-stu-id="5fd6d-155">Remove a caller ID policy</span></span>

<span data-ttu-id="5fd6d-156">Чтобы удалить политику организации, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="5fd6d-156">To remove a policy from your organization, run:</span></span>
  
```PowerShell
Remove-CsCallingLineIdentity -Identity "My Caller ID Policy"
```
<span data-ttu-id="5fd6d-157">Чтобы удалить политику пользователя, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="5fd6d-157">To remove a policy from a user, run:</span></span>
  
```PowerShell
Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName $null
```
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="5fd6d-158">Хотите узнать больше о Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="5fd6d-158">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="5fd6d-159">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span><span class="sxs-lookup"><span data-stu-id="5fd6d-159">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="5fd6d-160">С помощью Windows PowerShell вы можете управлять Office 365 и Skype для бизнеса online, используя единый центр администрирования, который упростит выполнение ваших повседневных задач.</span><span class="sxs-lookup"><span data-stu-id="5fd6d-160">With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="5fd6d-161">Чтобы начать работу с Windows PowerShell, ознакомьтесь с приведенными ниже разделами.</span><span class="sxs-lookup"><span data-stu-id="5fd6d-161">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="5fd6d-162">Введение в Windows PowerShell и Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="5fd6d-162">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="5fd6d-163">Шесть причин, по которым вам может потребоваться использовать Windows PowerShell для управления Office 365</span><span class="sxs-lookup"><span data-stu-id="5fd6d-163">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Office 365</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="5fd6d-164">Windows PowerShell обладает многими преимуществами для ускорения, простоты и продуктивности с помощью центра администрирования Microsoft 365, например при одновременном изменении параметров для нескольких пользователей.</span><span class="sxs-lookup"><span data-stu-id="5fd6d-164">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="5fd6d-165">Подробнее об этих преимуществах можно узнать в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="5fd6d-165">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="5fd6d-166">Лучшие способы управления Office 365 с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="5fd6d-166">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="5fd6d-167">Использование Windows PowerShell для управления Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="5fd6d-167">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="5fd6d-168">Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="5fd6d-168">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
  
 ## <a name="related-topics"></a><span data-ttu-id="5fd6d-169">См. также:</span><span class="sxs-lookup"><span data-stu-id="5fd6d-169">Related topics</span></span>
[<span data-ttu-id="5fd6d-170">Общие вопросы по передаче номеров телефонов</span><span class="sxs-lookup"><span data-stu-id="5fd6d-170">Transferring phone numbers common questions</span></span>](/microsoftteams/transferring-phone-numbers-common-questions)

[<span data-ttu-id="5fd6d-171">Типы номеров телефонов, используемые в планах звонков</span><span class="sxs-lookup"><span data-stu-id="5fd6d-171">Different kinds of phone numbers used for Calling Plans</span></span>](/microsoftteams/different-kinds-of-phone-numbers-used-for-calling-plans)

[<span data-ttu-id="5fd6d-172">Управление номерами телефонов организации</span><span class="sxs-lookup"><span data-stu-id="5fd6d-172">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="5fd6d-173">Дополнительные сведения об идентификаторе вызывающей линии и имени вызывающего абонента</span><span class="sxs-lookup"><span data-stu-id="5fd6d-173">More about Calling Line ID and Calling Party Name</span></span>](/skypeforbusiness/what-are-calling-plans-in-office-365/more-about-calling-line-ID-and-calling-party-name)

[<span data-ttu-id="5fd6d-174">Условия и положения, распространяющиеся на экстренные вызовы</span><span class="sxs-lookup"><span data-stu-id="5fd6d-174">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)

<span data-ttu-id="5fd6d-175">[Skype для бизнеса Online: заявление об отказе для звонков в экстренные службы](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="5fd6d-175">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>
 
