---
title: Настройка идентификатора абонента для пользователя
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: jens, roykuntz
ms.topic: article
ms.assetid: c7323490-d9b7-421a-aa76-5bd485f80583
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business Online
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Calling Plans
- seo-marvel-mar2020
description: Узнайте о Microsoft 365 и Office 365 по умолчанию (номер телефона, который назначен пользователю), который также называется ИД строки звонков. Вы можете изменить или заблокировать ИД вызываемой пользователем.
ms.openlocfilehash: 20b80bbc96f46d6b1a2766eea367132b9e0b1418
ms.sourcegitcommit: b39bd1de0219a9e3a3b0c97fc485c9578ddb643c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2021
ms.locfileid: "53230606"
---
# <a name="set-the-caller-id-for-a-user"></a><span data-ttu-id="1e1cc-104">Настройка идентификатора абонента для пользователя</span><span class="sxs-lookup"><span data-stu-id="1e1cc-104">Set the Caller ID for a user</span></span>

<span data-ttu-id="1e1cc-105">телефонная система в Microsoft 365 предоставляется стандартный номер телефона, который назначен пользователю.</span><span class="sxs-lookup"><span data-stu-id="1e1cc-105">Phone System in Microsoft 365 provides a default caller ID that is the user's assigned telephone number.</span></span> <span data-ttu-id="1e1cc-106">Можно изменить или заблокировать идентификатор абонента (также называемый идентификатором вызывающей линии) для пользователя.</span><span class="sxs-lookup"><span data-stu-id="1e1cc-106">You can either change or block the caller ID (also called a Calling Line ID) for a user.</span></span> <span data-ttu-id="1e1cc-107">Дополнительные сведения об использовании идентификатора абонента в своей организации можно получить, перейдя к статье [Использование идентификатора абонента в организации](how-can-caller-id-be-used-in-your-organization.md).</span><span class="sxs-lookup"><span data-stu-id="1e1cc-107">You can learn more about how to use caller ID in your organization by going [How can caller ID be used in your organization](how-can-caller-id-be-used-in-your-organization.md).</span></span>
  
<span data-ttu-id="1e1cc-108">По умолчанию следующие параметры ИД вызываемой стороны **отключены.**</span><span class="sxs-lookup"><span data-stu-id="1e1cc-108">By default, the following caller ID settings are **turned off**.</span></span> <span data-ttu-id="1e1cc-109">Это означает, что Teams номер телефона пользователя будет виден, когда пользователь звонит на телефон ЗВОНКОВ.</span><span class="sxs-lookup"><span data-stu-id="1e1cc-109">This means that the Teams user's phone number can be seen when that user makes a call to a PSTN phone.</span></span> <span data-ttu-id="1e1cc-110">Эти параметры можно изменить следующим образом:</span><span class="sxs-lookup"><span data-stu-id="1e1cc-110">You can change these settings as follows:</span></span>
  
- <span data-ttu-id="1e1cc-111">**ИД исходячего звоня** Вы можете заменить пользовательский номер телефона, который по умолчанию является его номером телефона, другим номером телефона.</span><span class="sxs-lookup"><span data-stu-id="1e1cc-111">**Outgoing caller ID** You can replace a user's Caller ID, which by default is their telephone number, with another phone number.</span></span> <span data-ttu-id="1e1cc-112">Например, можно изменить номер телефона пользователя с номера телефона на основной номер телефона для вашей компании или изменить номер телефона пользователя с номера телефона на основной номер для юридического отдела.</span><span class="sxs-lookup"><span data-stu-id="1e1cc-112">For example, you could change the user's Caller ID from their phone number to a main phone number for your business or change the user's Calling Line ID from their phone number to a main phone number for the legal department.</span></span> <span data-ttu-id="1e1cc-113">Вы можете изменить номер для звонков на любой номер веб-службы (платный или бесплатный).</span><span class="sxs-lookup"><span data-stu-id="1e1cc-113">You can change the Calling ID number to any online service number (toll or toll-free).</span></span> <span data-ttu-id="1e1cc-114">Вы также можете изменить номер телефона локального телефона, перенаправив его на учетную запись ресурса, используемую автозаправщиком или очередью звонков.</span><span class="sxs-lookup"><span data-stu-id="1e1cc-114">You can also change the Calling ID number to an on-premises phone number through Direct Routing that is assigned to a resource account used by an Auto Attendant or Call Queue.</span></span>
    
  > [!NOTE]
  > <span data-ttu-id="1e1cc-115">Если вы хотите использовать параметр *Service,* необходимо указать действительный номер службы.</span><span class="sxs-lookup"><span data-stu-id="1e1cc-115">If you want to use the *Service* parameter, you must specify a valid service number.</span></span>
  > <span data-ttu-id="1e1cc-116">Если номер учетной записи ресурса не отображается в drop down, используйте для этого powerShell.</span><span class="sxs-lookup"><span data-stu-id="1e1cc-116">You need to use the PowerShell cmdlets for Resource account number if not visible in drop down.</span></span>
  
- <span data-ttu-id="1e1cc-117">**Блокировать ИД исходящие вызовы.**</span><span class="sxs-lookup"><span data-stu-id="1e1cc-117">**Block outbound caller ID.**</span></span> <span data-ttu-id="1e1cc-118">Вы можете заблокировать отправление исходяющих звонков по ННР.</span><span class="sxs-lookup"><span data-stu-id="1e1cc-118">You can block the outgoing Caller ID from being sent on a user's outgoing PSTN calls.</span></span> <span data-ttu-id="1e1cc-119">В этом случае номер телефона не будет отображаться на телефоне звонимого человека.</span><span class="sxs-lookup"><span data-stu-id="1e1cc-119">Doing this will block their phone number from being displayed on the phone of a person being called.</span></span>
    
- <span data-ttu-id="1e1cc-120">**Заблокировать ИД входящих звонив.**</span><span class="sxs-lookup"><span data-stu-id="1e1cc-120">**Block incoming caller ID.**</span></span> <span data-ttu-id="1e1cc-121">Вы можете заблокировать получение ИД вызываемой службы при любых входящих звонках по ННР.</span><span class="sxs-lookup"><span data-stu-id="1e1cc-121">You can block a user from receiving Caller ID on any incoming PSTN calls.</span></span>

- <span data-ttu-id="1e1cc-122">**Set Calling Party Name (CNAM).**</span><span class="sxs-lookup"><span data-stu-id="1e1cc-122">**Set Calling Party Name (CNAM).**</span></span> <span data-ttu-id="1e1cc-123">Для ваших Microsoft Teams вы можете отправлять CNAM при исходящие звонки по ЗВОНКОВ по ННП.</span><span class="sxs-lookup"><span data-stu-id="1e1cc-123">For your Microsoft Teams users you can send a CNAM on outbound PSTN calls.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="1e1cc-124">При звонках в экстренные службы номер телефона пользователя (идентификатор абонента) передается всегда.</span><span class="sxs-lookup"><span data-stu-id="1e1cc-124">Emergency calls will always send the user's telephone number (caller ID).</span></span> 
  

  
<span data-ttu-id="1e1cc-125">Дополнительные информацию об этих параметрах и их [](how-can-caller-id-be-used-in-your-organization.md)использовании см. в этой статьи.</span><span class="sxs-lookup"><span data-stu-id="1e1cc-125">To learn more about these settings and how you can use them, see [How can caller ID be used in your organization](how-can-caller-id-be-used-in-your-organization.md).</span></span>
  
## <a name="set-your-caller-id-policy-settings"></a><span data-ttu-id="1e1cc-126">Задание настроек политики идентификатора абонента</span><span class="sxs-lookup"><span data-stu-id="1e1cc-126">Set your caller ID policy settings</span></span>

> [!NOTE]
> <span data-ttu-id="1e1cc-127">Чтобы установить для ИД звонящая номер телефона учетной записи ресурса и имя вызываемой стороны, используйте командлеты PowerShell New-CsCallingLineIdentity или Set-CsCallingLineIdentity в модуле Teams PowerShell 2.3.1 или более поздней.</span><span class="sxs-lookup"><span data-stu-id="1e1cc-127">To set the caller ID to a resource account phone number and to set the calling party name, use the PowerShell cmdlets New-CsCallingLineIdentity or Set-CsCallingLineIdentity in the Teams PowerShell module 2.3.1 or later.</span></span> <span data-ttu-id="1e1cc-128">(В настоящее время эти параметры недоступны в Центре Microsoft Teams администрирования.)</span><span class="sxs-lookup"><span data-stu-id="1e1cc-128">(These options are not currently available in the Microsoft Teams admin center.)</span></span> 

<span data-ttu-id="1e1cc-129">Откройте Windows PowerShell командную команду и запустите следующие команды:</span><span class="sxs-lookup"><span data-stu-id="1e1cc-129">Open a Windows PowerShell command prompt and run the following commands:</span></span>

```PowerShell
# When using Teams PowerShell Module

Import-Module MicrosoftTeams
$credential = Get-Credential
Connect-MicrosoftTeams -Credential $credential
``` 

### <a name="view-create-and-apply-policy-settings"></a><span data-ttu-id="1e1cc-130">Просмотр, создание и применение параметров политики</span><span class="sxs-lookup"><span data-stu-id="1e1cc-130">View, create, and apply policy settings</span></span>

1. <span data-ttu-id="1e1cc-131">Чтобы просмотреть все параметры политики ИД вызываемого звоня в организации, запустите:</span><span class="sxs-lookup"><span data-stu-id="1e1cc-131">To view all of the caller ID policy settings in your organization, run:</span></span>

     ```PowerShell
     Get-CsCallingLineIdentity |fl
     ```
   <span data-ttu-id="1e1cc-132">Дополнительные сведения [см. в окне Get-CsCallingLineIdentity.](/powershell/module/skype/Get-CsCallingLineIdentity)</span><span class="sxs-lookup"><span data-stu-id="1e1cc-132">For more information, see [Get-CsCallingLineIdentity](/powershell/module/skype/Get-CsCallingLineIdentity).</span></span>
    
2. <span data-ttu-id="1e1cc-133">Чтобы создать для своей организации политику кодов вызываемого звонка, используйте New-CsCallingIdentity управления:</span><span class="sxs-lookup"><span data-stu-id="1e1cc-133">To create a new caller ID policy for your organization, use the New-CsCallingIdentity cmdlet:</span></span>
    
     ```PowerShell
     New-CsCallingLineIdentity  -Identity Anonymous -Description "Anonymous policy" -CallingIDSubstitute Anonymous -EnableUserOverride $false
     ```
    <span data-ttu-id="1e1cc-134">Во всех случаях поле «Номер службы» не должно содержать начальный символ «+».</span><span class="sxs-lookup"><span data-stu-id="1e1cc-134">In all cases, the "Service Number" field should not include an initial "+".</span></span>

   <span data-ttu-id="1e1cc-135">Дополнительные сведения см. [в new-CsCallingLineIdentity.](/powershell/module/skype/New-CsCallingLineIdentity)</span><span class="sxs-lookup"><span data-stu-id="1e1cc-135">For more information, see [New-CsCallingLineIdentity](/powershell/module/skype/New-CsCallingLineIdentity).</span></span>
    
3. <span data-ttu-id="1e1cc-136">Применим новую политику, созданную с Grant-CsCallingIdentity управления.</span><span class="sxs-lookup"><span data-stu-id="1e1cc-136">Apply the new policy you created by using the Grant-CsCallingIdentity cmdlet.</span></span> <span data-ttu-id="1e1cc-137">Например, в следующем примере новая политика применяется к пользователю Amos Marble.</span><span class="sxs-lookup"><span data-stu-id="1e1cc-137">For example, the following example applies the new policy to user Amos Marble.</span></span>
    
     ```PowerShell
      Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName Anonymous
     ```
   <span data-ttu-id="1e1cc-138">Дополнительные сведения [см. в cmdlet grant-CsCallingLineIdentity.](/powershell/module/skype/Grant-CsCallingLineIdentity)</span><span class="sxs-lookup"><span data-stu-id="1e1cc-138">For more information, see [Grant-CsCallingLineIdentity](/powershell/module/skype/Grant-CsCallingLineIdentity) cmdlet.</span></span>
    

4. <span data-ttu-id="1e1cc-139">Если вы хотите заблокировать ИД входящих звонив, запустите:</span><span class="sxs-lookup"><span data-stu-id="1e1cc-139">If you want to block the incoming caller ID, run:</span></span>
    
   ```PowerShell
   Set-CsCallingLineIdentity  -Identity "Block Incoming" -BlockIncomingPstnCallerID $true
   ``` 

   <span data-ttu-id="1e1cc-140">Дополнительные сведения [см. в теме Set-CsCallingLineIdentity.](/powershell/module/skype/Set-CsCallingLineIdentity)</span><span class="sxs-lookup"><span data-stu-id="1e1cc-140">For more information, see [Set-CsCallingLineIdentity](/powershell/module/skype/Set-CsCallingLineIdentity).</span></span>
    
5. <span data-ttu-id="1e1cc-141">Чтобы применить параметр политики, созданный для пользователя в организации, запустите:</span><span class="sxs-lookup"><span data-stu-id="1e1cc-141">To apply the policy setting you created to a user in your organization, run:</span></span>
    
   ```PowerShell
   Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName "Block Incoming"
   ```
   <span data-ttu-id="1e1cc-142">Дополнительные сведения [см. в теме Grant-CsCallingLineIdentity.](/powershell/module/skype/Grant-CsCallingLineIdentity)</span><span class="sxs-lookup"><span data-stu-id="1e1cc-142">For more information, see [Grant-CsCallingLineIdentity](/powershell/module/skype/Grant-CsCallingLineIdentity).</span></span>

6. <span data-ttu-id="1e1cc-143">Чтобы создать политику "ИД звонящая", которая задает для имени вызываемого пользователя номер телефона указанной учетной записи ресурса и для имени вызываемой стороны — Contoso:</span><span class="sxs-lookup"><span data-stu-id="1e1cc-143">To create a new Caller ID policy that sets the Caller ID to the phone number of the specified resource account and sets the Calling party name to Contoso:</span></span>

   ```PowerShell
   $ObjId = (Get-CsOnlineApplicationInstance -Identity dkcq@contoso.com).ObjectId
   New-CsCallingLineIdentity  -Identity DKCQ -CallingIDSubstitute Resource -EnableUserOverride $false -ResourceAccount $ObjId -CompanyName "Contoso"
   ```

<span data-ttu-id="1e1cc-144">Если вы уже создали политику, вы можете изменить существующую политику с помощью [cmdlet Set-CsCallingLineIdentity,](/powershell/module/skype/Set-CsCallingLineIdentity) а затем применить параметры к пользователям с помощью cmdlet [Grant-CsCallingLineIdentity.](/powershell/module/skype/Grant-CsCallingLineIdentity)</span><span class="sxs-lookup"><span data-stu-id="1e1cc-144">If you have already created a policy, you can use the [Set-CsCallingLineIdentity](/powershell/module/skype/Set-CsCallingLineIdentity) cmdlet to make changes to the existing policy, and then use the [Grant-CsCallingLineIdentity](/powershell/module/skype/Grant-CsCallingLineIdentity) cmdlet to apply the settings to your users.</span></span>
    
### <a name="remove-a-policy-setting"></a><span data-ttu-id="1e1cc-145">Удаление параметра политики</span><span class="sxs-lookup"><span data-stu-id="1e1cc-145">Remove a policy setting</span></span>

<span data-ttu-id="1e1cc-146">Чтобы удалить политику организации, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="1e1cc-146">To remove a policy from your organization, run:</span></span>
  
```PowerShell
Remove-CsCallingLineIdentity -Identity "My Caller ID Policy"
```
<span data-ttu-id="1e1cc-147">Чтобы удалить политику пользователя, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="1e1cc-147">To remove a policy from a user, run:</span></span>
  
```PowerShell
Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName $null
```
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="1e1cc-148">Хотите узнать больше о Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="1e1cc-148">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="1e1cc-149">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span><span class="sxs-lookup"><span data-stu-id="1e1cc-149">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="1e1cc-150">С Windows PowerShell вы можете управлять Microsoft 365 с помощью единого администрирования, который упростит вашу повседневную работу.</span><span class="sxs-lookup"><span data-stu-id="1e1cc-150">With Windows PowerShell, you can manage Microsoft 365 using a single point of administration that can simplify your daily work.</span></span> <span data-ttu-id="1e1cc-151">Для начала работы с Windows PowerShell ознакомьтесь с приведенными ниже разделами.</span><span class="sxs-lookup"><span data-stu-id="1e1cc-151">To get started with Windows PowerShell, see these topics:</span></span>
    
- [<span data-ttu-id="1e1cc-152">Введение в Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="1e1cc-152">An introduction to Windows PowerShell</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
- [<span data-ttu-id="1e1cc-153">Шесть причин, по которым может потребоваться использовать Windows PowerShell управление Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="1e1cc-153">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Microsoft 365</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
- <span data-ttu-id="1e1cc-154">Windows PowerShell имеет множество преимуществ в скорости, простоте и эффективности работы по сравнению с использованием только Центр администрирования Microsoft 365, например при внесении изменений для множества пользователей одновременно.</span><span class="sxs-lookup"><span data-stu-id="1e1cc-154">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="1e1cc-155">Подробнее об этих преимуществах можно узнать в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="1e1cc-155">Learn about these advantages in the following topics:</span></span>
    
- <span data-ttu-id="1e1cc-156">[Лучшие способы управления Microsoft 365 с помощью Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="1e1cc-156">[Best ways to manage Microsoft 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
- [<span data-ttu-id="1e1cc-157">Использование Windows PowerShell для управления Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="1e1cc-157">Using Windows PowerShell to manage Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
- [<span data-ttu-id="1e1cc-158">Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="1e1cc-158">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
  
 ## <a name="related-topics"></a><span data-ttu-id="1e1cc-159">См. также:</span><span class="sxs-lookup"><span data-stu-id="1e1cc-159">Related topics</span></span>
[<span data-ttu-id="1e1cc-160">Общие вопросы по передаче номеров телефонов</span><span class="sxs-lookup"><span data-stu-id="1e1cc-160">Transferring phone numbers common questions</span></span>](./phone-number-calling-plans/port-order-overview.md)

[<span data-ttu-id="1e1cc-161">Типы номеров телефонов, используемые в планах звонков</span><span class="sxs-lookup"><span data-stu-id="1e1cc-161">Different kinds of phone numbers used for Calling Plans</span></span>](./different-kinds-of-phone-numbers-used-for-calling-plans.md)

[<span data-ttu-id="1e1cc-162">Управление номерами телефонов организации</span><span class="sxs-lookup"><span data-stu-id="1e1cc-162">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="1e1cc-163">Дополнительные сведения об идентификаторе вызывающей линии и имени вызывающего абонента</span><span class="sxs-lookup"><span data-stu-id="1e1cc-163">More about Calling Line ID and Calling Party Name</span></span>](/skypeforbusiness/what-are-calling-plans-in-office-365/more-about-calling-line-ID-and-calling-party-name)

[<span data-ttu-id="1e1cc-164">Условия и положения, распространяющиеся на экстренные вызовы</span><span class="sxs-lookup"><span data-stu-id="1e1cc-164">Emergency calling terms and conditions</span></span>](./emergency-calling-terms-and-conditions.md)

<span data-ttu-id="1e1cc-165">[Skype для бизнеса Online: заявление об отказе для звонков в экстренные службы](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="1e1cc-165">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>
