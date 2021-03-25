---
title: Настройка идентификатора абонента для пользователя
ms.author: mikeplum
author: MikePlumleyMSFT
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
description: Узнайте о microsoft 365 и стандартном номере звоня в Office 365 (который назначен пользователю), который также называется ИД линии звонков. Вы можете изменить или заблокировать ИД вызываемой точки пользователя.
ms.openlocfilehash: 41883e00955cf5f39f4420fb10ead1be2e131a77
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117157"
---
# <a name="set-the-caller-id-for-a-user"></a><span data-ttu-id="d8a11-104">Настройка идентификатора абонента для пользователя</span><span class="sxs-lookup"><span data-stu-id="d8a11-104">Set the Caller ID for a user</span></span>
<span data-ttu-id="d8a11-105">Телефонная система в Microsoft 365 и Office 365 предоставляет номер телефона, который назначен пользователю по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="d8a11-105">The Phone System in Microsoft 365 and Office 365 provides a default caller ID that is the user's assigned telephone number.</span></span> <span data-ttu-id="d8a11-106">Можно изменить или заблокировать идентификатор абонента (также называемый идентификатором вызывающей линии) для пользователя.</span><span class="sxs-lookup"><span data-stu-id="d8a11-106">You can either change or block the caller ID (also called a Calling Line ID) for a user.</span></span> <span data-ttu-id="d8a11-107">Дополнительные сведения об использовании идентификатора абонента в своей организации можно получить, перейдя к статье [Использование идентификатора абонента в организации](how-can-caller-id-be-used-in-your-organization.md).</span><span class="sxs-lookup"><span data-stu-id="d8a11-107">You can learn more about how to use caller ID in your organization by going [How can caller ID be used in your organization](how-can-caller-id-be-used-in-your-organization.md).</span></span>
  
> [!TIP]
> <span data-ttu-id="d8a11-108">В настоящее время в Skype для бизнеса Online невозможно заблокировать входящие вызовы.</span><span class="sxs-lookup"><span data-stu-id="d8a11-108">You can't block incoming calls currently in Skype for Business Online.</span></span> 
  
<span data-ttu-id="d8a11-109">Для изменения доступны следующие настройки:</span><span class="sxs-lookup"><span data-stu-id="d8a11-109">There are settings that you can change:</span></span>
  
> [!NOTE]
> <span data-ttu-id="d8a11-110">Эта функция **не предназначена** для организаций с локальными развертываниями Lync или Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="d8a11-110">This **is not** for on-premises organizations with Lync or Skype for Business Server.</span></span>
  
- <span data-ttu-id="d8a11-p103">**Изменить идентификатор исходящего абонента**. Вы можете заменить идентификатор абонента (по умолчанию соответствует номеру телефона, назначенному пользователю) другим номером. Например, вы можете заменить идентификатор абонента основным рабочим номером вашей организации или юридического отдела. В качестве идентификатора абонента можно указать любой номер **службы** в Интернете (как платный, так и бесплатный).</span><span class="sxs-lookup"><span data-stu-id="d8a11-p103">**Change their outgoing caller ID** You can replace a user's Caller ID, which by default is their telephone number, with another phone number. For example, you could change the user's Caller ID from their phone number to a main phone number for your business or change the user's Calling Line ID from their phone number to a main phone number for the legal department. You can change the Calling ID number to any Online **service** number (toll or toll-free).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="d8a11-114">Чтобы использовать параметр  _Service_, необходимо указать допустимый номер службы.</span><span class="sxs-lookup"><span data-stu-id="d8a11-114">If you want to use the  _Service_ parameter, you must specify a valid service number.</span></span>
  
- <span data-ttu-id="d8a11-115">**Блокировать ИД исходящие вызываемой вызовы** Вы можете заблокировать отправление исходя из этой службы ИД звонив пользователю во время исходяющих звонков по ДНР.</span><span class="sxs-lookup"><span data-stu-id="d8a11-115">**Block their outbound caller ID** You can block the outgoing Caller ID from being sent on a user's outgoing PSTN calls.</span></span> <span data-ttu-id="d8a11-116">В этом случае номер телефона не будет отображаться на телефоне звонимого.</span><span class="sxs-lookup"><span data-stu-id="d8a11-116">Doing this will block their phone number from being displayed on the phone of a person being called.</span></span>
    
- <span data-ttu-id="d8a11-117">**Блокировать его ИД входящих вызовов** Вы можете заблокировать получение ИД вызываемой службы во всех входящих звонках по ДНР.</span><span class="sxs-lookup"><span data-stu-id="d8a11-117">**Block their incoming caller ID** You can block a user from receiving Caller ID on any incoming PSTN calls.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="d8a11-118">При звонках в экстренные службы номер телефона пользователя (идентификатор абонента) передается всегда.</span><span class="sxs-lookup"><span data-stu-id="d8a11-118">Emergency calls will always send the user's telephone number (caller ID).</span></span> 
  
<span data-ttu-id="d8a11-p105">По умолчанию все параметры идентификатора абонента **отключены**. Это означает, что при звонке по телефону через ТСОП будет отображаться номер телефона пользователя в Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="d8a11-p105">By default, all of these caller ID settings are **turned off**. This means that the Skype for Business Online user's phone number can be seen when that user makes a call to a PSTN phone.</span></span>
  
<span data-ttu-id="d8a11-121">Дополнительные сведения об этих параметрах и их использовании см. [Как можно использовать идентификатор абонента в организации?](how-can-caller-id-be-used-in-your-organization.md).</span><span class="sxs-lookup"><span data-stu-id="d8a11-121">To learn more about these settings and how you can use them, go [How can caller ID be used in your organization](how-can-caller-id-be-used-in-your-organization.md).</span></span>
  
## <a name="set-your-caller-id-policy-settings"></a><span data-ttu-id="d8a11-122">Задание настроек политики идентификатора абонента</span><span class="sxs-lookup"><span data-stu-id="d8a11-122">Set your caller ID policy settings</span></span>

> [!NOTE]
> <span data-ttu-id="d8a11-123">Для всех параметров " ИД звоня" в Skype для бизнеса Online  необходимо использовать Windows PowerShell и не использовать Центр администрирования **Skype для бизнеса.**</span><span class="sxs-lookup"><span data-stu-id="d8a11-123">For all of the Caller ID settings in Skype for Business Online, you must use Windows PowerShell and you **can't use** the **Skype for Business admin center**.</span></span> 
  
### <a name="start-powershell"></a><span data-ttu-id="d8a11-124">Запуск PowerShell</span><span class="sxs-lookup"><span data-stu-id="d8a11-124">Start PowerShell</span></span>

- <span data-ttu-id="d8a11-125">Откройте Windows PowerShell и запустите следующие команды:</span><span class="sxs-lookup"><span data-stu-id="d8a11-125">Open a Windows PowerShell command prompt and run the following commands:</span></span>

```powershell
  # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
```
    
### <a name="see-all-of-the-caller-id-policy-settings-in-your-organization"></a><span data-ttu-id="d8a11-126">Просмотр всех настроек политики идентификатора абонента в организации</span><span class="sxs-lookup"><span data-stu-id="d8a11-126">See all of the caller ID policy settings in your organization</span></span>

- <span data-ttu-id="d8a11-127">Чтобы просмотреть все параметры политики "ИД звоня" в организации, запустите 4</span><span class="sxs-lookup"><span data-stu-id="d8a11-127">To view all of the caller ID policy settings in your organization, run:</span></span>

  ```PowerShell
  Get-CsCallingLineIdentity |fl
  ```
  <span data-ttu-id="d8a11-128">См. другие примеры и подробные сведения о [Get-CsCallingLineIdentity.](/powershell/module/skype/Get-CsCallingLineIdentity)</span><span class="sxs-lookup"><span data-stu-id="d8a11-128">See more examples and details for [Get-CsCallingLineIdentity](/powershell/module/skype/Get-CsCallingLineIdentity).</span></span>
    
### <a name="create-a-new-caller-id-policy-for-your-organization"></a><span data-ttu-id="d8a11-129">Создание политики идентификатора абонента для организации</span><span class="sxs-lookup"><span data-stu-id="d8a11-129">Create a new caller ID policy for your organization</span></span>


- <span data-ttu-id="d8a11-130">Чтобы создать новую политику, которая задает анонимный ИД звоня, запустите 4.</span><span class="sxs-lookup"><span data-stu-id="d8a11-130">To create a new caller ID policy that sets the caller ID to anonymous, run:</span></span>
    
  ```PowerShell
  New-CsCallingLineIdentity  -Identity Anonymous -Description "Anonymous policy" -CallingIDSubstitute Anonymous -EnableUserOverride $false
  ```
  > [!NOTE]  
  > <span data-ttu-id="d8a11-131">Во всех случаях поле «Номер службы» не должно содержать начальный символ «+».</span><span class="sxs-lookup"><span data-stu-id="d8a11-131">In all cases, the "Service Number" field should not include an initial "+".</span></span>

  <span data-ttu-id="d8a11-132">См. другие примеры и подробные сведения о [New-CsCallingLineIdentity.](/powershell/module/skype/New-CsCallingLineIdentity)</span><span class="sxs-lookup"><span data-stu-id="d8a11-132">See more examples and details for [New-CsCallingLineIdentity](/powershell/module/skype/New-CsCallingLineIdentity).</span></span>
    
- <span data-ttu-id="d8a11-133">Чтобы применить новую политику, созданную для amos Marble, запустите 365:</span><span class="sxs-lookup"><span data-stu-id="d8a11-133">To apply the new policy you created to Amos Marble, run:</span></span>
    
  ```PowerShell
   Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName Anonymous
  ```
  <span data-ttu-id="d8a11-134">Дополнительные сведения о командлете [Grant-CsCallingLineIdentity](/powershell/module/skype/Grant-CsCallingLineIdentity).</span><span class="sxs-lookup"><span data-stu-id="d8a11-134">See more on the [Grant-CsCallingLineIdentity](/powershell/module/skype/Grant-CsCallingLineIdentity) cmdlet.</span></span>
    
<span data-ttu-id="d8a11-135">Если политика уже создана, вы можете внести изменения в существующую политику с помощью [cmdlet Set-CsCallingLineIdentity,](/powershell/module/skype/Set-CsCallingLineIdentity) а затем применить параметры к пользователям с помощью cmdletentity [Grant-CsCallingLineIdentity.](/powershell/module/skype/Grant-CsCallingLineIdentity)</span><span class="sxs-lookup"><span data-stu-id="d8a11-135">If you have already created a policy, you can use the [Set-CsCallingLineIdentity](/powershell/module/skype/Set-CsCallingLineIdentity) cmdlet to make changes to the existing policy, and then use the [Grant-CsCallingLineIdentity](/powershell/module/skype/Grant-CsCallingLineIdentity) cmdlet to apply the settings to your users.</span></span>
  
### <a name="set-it-so-the-incoming-caller-id-is-blocked"></a><span data-ttu-id="d8a11-136">Блокировка идентификатора входящего абонента</span><span class="sxs-lookup"><span data-stu-id="d8a11-136">Set it so the incoming caller ID is blocked</span></span>

- <span data-ttu-id="d8a11-137">Чтобы заблокировать ИД входящих звонив, запустите 4.</span><span class="sxs-lookup"><span data-stu-id="d8a11-137">To block the incoming caller ID, run:</span></span>
    
  ```PowerShell
  Set-CsCallingLineIdentity  -Identity "Block Incoming" -BlockIncomingPstnCallerID $true -EnableUserOverride $true
  ```
  <span data-ttu-id="d8a11-138">См. другие примеры и подробные сведения о [Set-CsCallingLineIdentity.](/powershell/module/skype/Set-CsCallingLineIdentity)</span><span class="sxs-lookup"><span data-stu-id="d8a11-138">See more examples and details for [Set-CsCallingLineIdentity](/powershell/module/skype/Set-CsCallingLineIdentity).</span></span>
    
- <span data-ttu-id="d8a11-139">Чтобы применить параметр политики, созданный для пользователя в организации, запустите 3</span><span class="sxs-lookup"><span data-stu-id="d8a11-139">To apply the policy setting you created to a user in your organization, run:</span></span>
    
  ```PowerShell
  Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName "Block Incoming"
  ```
    <span data-ttu-id="d8a11-140">Дополнительные сведения о командлете [Grant-CsCallingLineIdentity](/powershell/module/skype/Grant-CsCallingLineIdentity).</span><span class="sxs-lookup"><span data-stu-id="d8a11-140">See more on the [Grant-CsCallingLineIdentity](/powershell/module/skype/Grant-CsCallingLineIdentity) cmdlet.</span></span>
    
### <a name="remove-a-caller-id-policy"></a><span data-ttu-id="d8a11-141">Удаление политики идентификатора абонента</span><span class="sxs-lookup"><span data-stu-id="d8a11-141">Remove a caller ID policy</span></span>

<span data-ttu-id="d8a11-142">Чтобы удалить политику организации, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="d8a11-142">To remove a policy from your organization, run:</span></span>
  
```PowerShell
Remove-CsCallingLineIdentity -Identity "My Caller ID Policy"
```
<span data-ttu-id="d8a11-143">Чтобы удалить политику пользователя, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="d8a11-143">To remove a policy from a user, run:</span></span>
  
```PowerShell
Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName $null
```
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="d8a11-144">Хотите узнать больше о Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="d8a11-144">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="d8a11-145">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span><span class="sxs-lookup"><span data-stu-id="d8a11-145">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="d8a11-146">С Windows PowerShell вы можете управлять Microsoft 365, Office 365 и Skype для бизнеса Online, используя единый пункт администрирования, который упростит выполнение ваших повседневных задач.</span><span class="sxs-lookup"><span data-stu-id="d8a11-146">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="d8a11-147">Чтобы начать работу с Windows PowerShell, ознакомьтесь с приведенными ниже разделами.</span><span class="sxs-lookup"><span data-stu-id="d8a11-147">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="d8a11-148">Введение в Windows PowerShell и Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="d8a11-148">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
  - [<span data-ttu-id="d8a11-149">Шесть причин, по которым может потребоваться использовать Windows PowerShell для управления Microsoft 365 или Office 365</span><span class="sxs-lookup"><span data-stu-id="d8a11-149">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Microsoft 365 or Office 365</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
- <span data-ttu-id="d8a11-150">Windows PowerShell имеет множество преимуществ в скорости, простоте и эффективности работы по сравнению с использованием только Центра администрирования Microsoft 365, например при внесении изменений для множества пользователей одновременно.</span><span class="sxs-lookup"><span data-stu-id="d8a11-150">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="d8a11-151">Подробнее об этих преимуществах можно узнать в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="d8a11-151">Learn about these advantages in the following topics:</span></span>
    
  - <span data-ttu-id="d8a11-152">[Лучшие способы управления Microsoft 365 или Office 365 с помощью Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="d8a11-152">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
  - [<span data-ttu-id="d8a11-153">Использование Windows PowerShell для управления Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="d8a11-153">Using Windows PowerShell to manage Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
  - [<span data-ttu-id="d8a11-154">Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="d8a11-154">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
  
 ## <a name="related-topics"></a><span data-ttu-id="d8a11-155">См. также:</span><span class="sxs-lookup"><span data-stu-id="d8a11-155">Related topics</span></span>
[<span data-ttu-id="d8a11-156">Общие вопросы по передаче номеров телефонов</span><span class="sxs-lookup"><span data-stu-id="d8a11-156">Transferring phone numbers common questions</span></span>](./phone-number-calling-plans/port-order-overview.md)

[<span data-ttu-id="d8a11-157">Типы номеров телефонов, используемые в планах звонков</span><span class="sxs-lookup"><span data-stu-id="d8a11-157">Different kinds of phone numbers used for Calling Plans</span></span>](./different-kinds-of-phone-numbers-used-for-calling-plans.md)

[<span data-ttu-id="d8a11-158">Управление номерами телефонов организации</span><span class="sxs-lookup"><span data-stu-id="d8a11-158">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="d8a11-159">Дополнительные сведения об идентификаторе вызывающей линии и имени вызывающего абонента</span><span class="sxs-lookup"><span data-stu-id="d8a11-159">More about Calling Line ID and Calling Party Name</span></span>](/skypeforbusiness/what-are-calling-plans-in-office-365/more-about-calling-line-ID-and-calling-party-name)

[<span data-ttu-id="d8a11-160">Условия и положения, распространяющиеся на экстренные вызовы</span><span class="sxs-lookup"><span data-stu-id="d8a11-160">Emergency calling terms and conditions</span></span>](./emergency-calling-terms-and-conditions.md)

<span data-ttu-id="d8a11-161">[Skype для бизнеса Online: заявление об отказе для звонков в экстренные службы](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="d8a11-161">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>
