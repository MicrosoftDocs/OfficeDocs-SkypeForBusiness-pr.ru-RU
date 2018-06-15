---
title: Развертывание Систем комнат Skype версии 2 со Skype для бизнеса Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 1/18/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a038e34d-8bc8-4a59-8ed2-3fc00ec33dd7
description: В данном разделе приведены сведения о способах развертывания систем комнаты Скайп версии 2 с Скайп для Business Server 2015.
ms.openlocfilehash: da5d0319e3dd582d6f446471424814ece3a9d178
ms.sourcegitcommit: 4e9f4e2297cea3372a97f4ea178eb75ba6f8753f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/14/2018
ms.locfileid: "19887829"
---
# <a name="deploy-skype-room-systems-v2-with-skype-for-business-server-2015"></a><span data-ttu-id="199c5-103">Развертывание Систем комнат Skype версии 2 со Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="199c5-103">Deploy Skype Room Systems v2 with Skype for Business Server 2015</span></span>
  
<span data-ttu-id="199c5-104">В этом разделе объясняется, как добавить учетную запись устройства для систем комнаты Скайп версии 2 при наличии одним лесом локального развертывания.</span><span class="sxs-lookup"><span data-stu-id="199c5-104">This topic explains how you add a device account for Skype Room Systems v2 when you have a single-forest, on-premises deployment.</span></span>
  
<span data-ttu-id="199c5-105">При наличии одного леса, локальное развертывание Exchange 2013 с пакетом обновления 1 или более поздней версии и Скайп Business Server 2015 или более поздней версии отмеченными сценарии Windows PowerShell можно использовать для создания учетных записей устройства.</span><span class="sxs-lookup"><span data-stu-id="199c5-105">If you have a single-forest, on-premises deployment with Exchange 2013 SP1 or later and Skype for Business Server 2015 or later, then you can use the provided Windows PowerShell scripts to create device accounts.</span></span> <span data-ttu-id="199c5-106">Если вы используете развертывания нескольких лесов, можно использовать эквивалентный командлеты, которые будут создавать одинаковые результаты.</span><span class="sxs-lookup"><span data-stu-id="199c5-106">If you're using a multi-forest deployment, you can use equivalent cmdlets that will produce the same results.</span></span> <span data-ttu-id="199c5-107">В этой статье описываются необходимые для этого командлеты.</span><span class="sxs-lookup"><span data-stu-id="199c5-107">Those cmdlets are described in this section.</span></span>

<span data-ttu-id="199c5-108">Настройка учетных записей пользователей проще всего настроить их с помощью удаленной оболочки Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="199c5-108">The easiest way to set up user accounts is to configure them using remote Windows PowerShell.</span></span> <span data-ttu-id="199c5-109">Корпорация Майкрософт предоставляет [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), сценарий, который поможет создать новые учетные записи пользователей, или validate существующие учетные записи ресурсов, что у вас есть помогающих перевод их в совместимые учетных записей пользователей системы комнаты Скайп версии 2.</span><span class="sxs-lookup"><span data-stu-id="199c5-109">Microsoft provides [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), a script that will help create new user accounts, or validate existing resource accounts you have in order to help you turn them into compatible Skype Room Systems v2 user accounts.</span></span> <span data-ttu-id="199c5-110">При необходимости можно выполните следующие действия, чтобы настроить учетные записи, используемые устройства версии 2 Скайп комнаты систем.</span><span class="sxs-lookup"><span data-stu-id="199c5-110">If you prefer, you can follow the steps below to configure accounts your Skype Room Systems v2 device will use.</span></span>
  
## <a name="deploy-skype-room-systems-v2-with-skype-for-business-server-2015"></a><span data-ttu-id="199c5-111">Развертывание Систем комнат Skype версии 2 со Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="199c5-111">Deploy Skype Room Systems v2 with Skype for Business Server 2015</span></span>

<span data-ttu-id="199c5-112">Перед развертыванием системы комнаты Скайп версии 2 с Скайп для Business Server 2015 убедитесь, что удовлетворены требования.</span><span class="sxs-lookup"><span data-stu-id="199c5-112">Before you deploy Skype Room Systems v2 with Skype for Business Server 2015, be sure you have met the requirements.</span></span> <span data-ttu-id="199c5-113">Для получения дополнительных сведений см [систем комнаты Скайп версии 2](../../plan-your-deployment/clients-and-devices/requirements.md).</span><span class="sxs-lookup"><span data-stu-id="199c5-113">For more information, see [Skype Room Systems v2 requirements](../../plan-your-deployment/clients-and-devices/requirements.md).</span></span>
  
<span data-ttu-id="199c5-114">Перед началом развертывания систем комнаты Скайп версии 2, убедитесь, что у соответствующих разрешений для запуска связанного командлетов.</span><span class="sxs-lookup"><span data-stu-id="199c5-114">Before you begin to deploy Skype Room Systems v2, be sure you have the right permissions to run the associated cmdlets.</span></span>
  
1. <span data-ttu-id="199c5-115">Для запуска удаленного сеанса Windows PowerShell с ПК и подключитесь к Exchange.</span><span class="sxs-lookup"><span data-stu-id="199c5-115">Start a remote Windows PowerShell session from a PC and connect to Exchange.</span></span> 
    
   ```
   Set-ExecutionPolicy Unrestricted
   $org='contoso.com'
   $cred=Get-Credential $admin@$org
   $sessExchange = New-PSSession -ConfigurationName microsoft.exchange -Credential $cred -AllowRedirection -Authentication Kerberos -ConnectionUri
   "http://$strExchangeServer/powershell" -WarningAction SilentlyContinue
   $sessLync = New-PSSession -Credential $cred -ConnectionURI "https://$strLyncFQDN/OcsPowershell" -AllowRedirection -WarningAction SilentlyContinue
   Import-PSSession $sessExchange
   Import-PSSession $sessLync
 
   ```

   <span data-ttu-id="199c5-116">Обратите внимание на то, что $strExchangeServer — это полное доменное имя (FQDN) сервера Exchange и $strLyncFQDN — это полное доменное имя вашей Скайп для развертывания Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="199c5-116">Note that $strExchangeServer is the fully qualified domain name (FQDN) of your Exchange server, and $strLyncFQDN is the FQDN of your Skype for Business Server 2015 deployment.</span></span>
    
2. <span data-ttu-id="199c5-117">После установки сеанса будет либо создать новый почтовый ящик и включение как RoomMailboxAccount или изменение параметров для существующего почтового ящика помещения.</span><span class="sxs-lookup"><span data-stu-id="199c5-117">After establishing a session, you'll either create a new mailbox and enable it as a RoomMailboxAccount, or change the settings for an existing room mailbox.</span></span> <span data-ttu-id="199c5-118">Это позволит учетной записи для проверки подлинности системы комнаты Скайп версии 2.</span><span class="sxs-lookup"><span data-stu-id="199c5-118">This will allow the account to authenticate to Skype Room Systems v2.</span></span>
    
    <span data-ttu-id="199c5-119">Изменение существующего почтового ящика ресурса:</span><span class="sxs-lookup"><span data-stu-id="199c5-119">If you're changing an existing resource mailbox:</span></span>
    
   ```
   Set-Mailbox -Identity 'PROJECTRIGEL01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password>
   -AsPlainText -Force)
   ```

   <span data-ttu-id="199c5-120">Если вы создаете новый почтовый ящик ресурса:</span><span class="sxs-lookup"><span data-stu-id="199c5-120">If you're creating a new resource mailbox:</span></span>
    
   ```
   New-Mailbox -UserPrincipalName PROJECTRIGEL01@contoso.com -Alias PROJECTRIGEL01 -Name "Project-Rigel-01" -Room 
   -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. <span data-ttu-id="199c5-121">Можно задать различные свойства Exchange для учетной записи устройства, чтобы улучшить работу в собрание для людей.</span><span class="sxs-lookup"><span data-stu-id="199c5-121">You can set various Exchange properties on the device account to improve the meeting experience for people.</span></span> <span data-ttu-id="199c5-122">Описание необходимых настроек приводится в разделе "Свойства Exchange".</span><span class="sxs-lookup"><span data-stu-id="199c5-122">You can see which properties need to be set in the Exchange properties section.</span></span>
    
   ```
   Set-CalendarProcessing -Identity $acctUpn -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments 
   $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity $acctUpn -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

4. <span data-ttu-id="199c5-123">Если вы решили не срок действия пароля, можно задать, с помощью командлетов Windows PowerShell слишком.</span><span class="sxs-lookup"><span data-stu-id="199c5-123">If you decide to have the password not expire, you can set that with Windows PowerShell cmdlets too.</span></span> <span data-ttu-id="199c5-124">Дополнительные сведения см. в разделе "Управление паролями".</span><span class="sxs-lookup"><span data-stu-id="199c5-124">See Password management for more information.</span></span>
    
   ```
   Set-AdUser $acctUpn -PasswordNeverExpires $true
   ```

5. <span data-ttu-id="199c5-125">Включение учетной записи в службе каталогов Active Directory, он будет выполнять проверку подлинности для систем комнаты Скайп версии 2.</span><span class="sxs-lookup"><span data-stu-id="199c5-125">Enable the account in Active Directory so it will authenticate to Skype Room Systems v2.</span></span>
    
   ```
   Set-AdUser $acctUpn -Enabled $true
   ```

6. <span data-ttu-id="199c5-126">Включение учетной записи устройства с Скайп для Business Server 2015, включив свою учетную запись Active Directory систем комнаты Скайп версии 2 на Скайп для пула Business Server 2015:</span><span class="sxs-lookup"><span data-stu-id="199c5-126">Enable the device account with Skype for Business Server 2015 by enabling your Skype Room Systems v2 Active Directory account on a Skype for Business Server 2015 pool:</span></span>
    
   ```
   Enable-CsMeetingRoom -SipAddress sip:PROJECTRIGEL01@contoso.com -DomainController DC-ND-001.contoso.com 
   -RegistrarPool LYNCPool15.contoso.com -Identity PROJECTRIGEL01
   ```

    <span data-ttu-id="199c5-127">Для этого вам понадобятся SIP-адрес и контроллер домена проекта.</span><span class="sxs-lookup"><span data-stu-id="199c5-127">You'll need to use the Session Initiation Protocol (SIP) address and domain controller for the Project</span></span> 
    
7. <span data-ttu-id="199c5-128">**Необязательный**.</span><span class="sxs-lookup"><span data-stu-id="199c5-128">**Optional.**</span></span> <span data-ttu-id="199c5-129">Также можно разрешить систем комнаты Скайп v2 для выполнения и приема телефонных звонков телефонной сети (общего пользования PSTN), позволяя корпоративной голосовой связи для вашей учетной записи.</span><span class="sxs-lookup"><span data-stu-id="199c5-129">You can also allow Skype Room Systems v2 to make and receive public switched telephone network (PSTN) phone calls by enabling Enterprise Voice for your account.</span></span> <span data-ttu-id="199c5-130">Корпоративной голосовой связи не является обязательным требованием для систем комнаты Скайп версии 2, но если требуется использовать возможности набора номера ТСОП для клиентских систем комнаты Скайп версии 2, здесь — это способ его включения:</span><span class="sxs-lookup"><span data-stu-id="199c5-130">Enterprise Voice isn't a requirement for Skype Room Systems v2, but if you want PSTN dialing functionality for the Skype Room Systems v2 client, here's how to enable it:</span></span>
    
   ```
   Set-CsMeetingRoom PROJECTRIGEL01 -DomainController DC-ND-001.contoso.com -LineURI "tel:+14255550555;ext=50555"
   Set-CsMeetingRoom -DomainController DC-ND-001.contoso.com -Identity PROJECTRIGEL01 -EnterpriseVoiceEnabled $true
   Grant-CsVoicePolicy -PolicyName VP1 -Identity PROJECTRIGEL01
   Grant-CsDialPlan -PolicyName DP1 -Identity PROJECTRIGEL01
   ```

   <span data-ttu-id="199c5-p108">Обратите внимание, что используемые в примере контроллер домена и номер телефона необходимо заменить данными, соответствующими вашей среде. Значение параметра $true остается прежним.</span><span class="sxs-lookup"><span data-stu-id="199c5-p108">Again, you'll need to replace the provided domain controller and phone number examples with your own information. The parameter value $true stays the same.</span></span>
    
## <a name="sample-room-account-setup-in-exchange-and-skype-for-business-server-2015-on-premises"></a><span data-ttu-id="199c5-133">Пример: Настройка учетной записи помещения в Exchange и Скайп для Business Server 2015 локально</span><span class="sxs-lookup"><span data-stu-id="199c5-133">Sample: room account setup in Exchange and Skype for Business Server 2015 on premises</span></span>

```
New-Mailbox -Alias rigel1 -Name "Rigel 1" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String "" -AsPlainText -Force) 
-UserPrincipalName rigel1@contoso.com
 
Set-CalendarProcessing -Identity rigel1 -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false -DeleteSubject $false 
-RemovePrivateProperty $false
Set-CalendarProcessing -Identity rigel1 -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
 
Enable-CsMeetingRoom -Identity rigel1@contoso.com -RegistrarPool cs3.contoso.com -SipAddressType EmailAddress
Set-CsMeetingRoom -Identity rigel1 -EnterpriseVoiceEnabled $true -LineURI tel:+155555555555
Grant-CsVoicePolicy -PolicyName dk -Identity rigel1
Grant-CsDialPlan -PolicyName e15dp2.contoso.com -Identity rigel1
```

## <a name="see-also"></a><span data-ttu-id="199c5-134">См. также</span><span class="sxs-lookup"><span data-stu-id="199c5-134">See also</span></span>

[<span data-ttu-id="199c5-135">Настройка учетных записей для систем комнаты Скайп версии 2</span><span class="sxs-lookup"><span data-stu-id="199c5-135">Configure accounts for Skype Room Systems v2</span></span>](room-systems-v2-configure-accounts.md)

[<span data-ttu-id="199c5-136">Планирование для помещения Скайп систем версии 2</span><span class="sxs-lookup"><span data-stu-id="199c5-136">Plan for Skype Room Systems v2</span></span>](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)
  
[<span data-ttu-id="199c5-137">Развертывание Скайп комнаты систем версии 2</span><span class="sxs-lookup"><span data-stu-id="199c5-137">Deploy Skype Room Systems v2</span></span>](room-systems-v2.md)
  
[<span data-ttu-id="199c5-138">Настройка консоли систем комнаты Скайп версии 2</span><span class="sxs-lookup"><span data-stu-id="199c5-138">Configure a Skype Room Systems v2 console</span></span>](console.md)
  
[<span data-ttu-id="199c5-139">Управление Скайп комнаты систем версии 2</span><span class="sxs-lookup"><span data-stu-id="199c5-139">Manage Skype Room Systems v2</span></span>](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)