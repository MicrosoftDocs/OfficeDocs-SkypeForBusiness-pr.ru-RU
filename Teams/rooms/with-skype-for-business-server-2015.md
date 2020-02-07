---
title: Развертывание комнат Microsoft Teams с помощью Skype для бизнеса Server
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.custom: ''
ms.assetid: a038e34d-8bc8-4a59-8ed2-3fc00ec33dd7
description: В этой статье приведены сведения о том, как развертывать комнаты Microsoft Teams в Skype для бизнеса Server.
ms.openlocfilehash: ecea3e21181371ec22446c54b449ae7424517d4e
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41827887"
---
# <a name="deploy-microsoft-teams-rooms-with-skype-for-business-server"></a><span data-ttu-id="38d40-103">Развертывание комнат Microsoft Teams с помощью Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="38d40-103">Deploy Microsoft Teams Rooms with Skype for Business Server</span></span>
  
<span data-ttu-id="38d40-104">В этой статье объясняется, как добавить учетную запись устройства для комнат Microsoft Teams, если у вас есть развертывание с одним лесом и локальным.</span><span class="sxs-lookup"><span data-stu-id="38d40-104">This topic explains how you add a device account for Microsoft Teams Rooms when you have a single-forest, on-premises deployment.</span></span>
  
<span data-ttu-id="38d40-105">Если у вас есть локальное развертывание с Exchange 2013 с пакетом обновления 1 (SP1) или более поздней версии, а также Skype для бизнеса Server 2015 или более поздней версии, вы можете использовать указанные сценарии Windows PowerShell для создания учетных записей устройств.</span><span class="sxs-lookup"><span data-stu-id="38d40-105">If you have a single-forest, on-premises deployment with Exchange 2013 SP1 or later and Skype for Business Server 2015 or later, then you can use the provided Windows PowerShell scripts to create device accounts.</span></span> <span data-ttu-id="38d40-106">Если вы используете развертывание с несколькими лесами, вы можете использовать эквивалентные командлеты, которые будут давать одинаковые результаты.</span><span class="sxs-lookup"><span data-stu-id="38d40-106">If you're using a multi-forest deployment, you can use equivalent cmdlets that will produce the same results.</span></span> <span data-ttu-id="38d40-107">В этой статье описываются необходимые для этого командлеты.</span><span class="sxs-lookup"><span data-stu-id="38d40-107">Those cmdlets are described in this section.</span></span>

  
<span data-ttu-id="38d40-108">Перед развертыванием комнат Microsoft Teams убедитесь, что у вас есть необходимые разрешения для выполнения соответствующих командлетов.</span><span class="sxs-lookup"><span data-stu-id="38d40-108">Before you begin to deploy Microsoft Teams Rooms, be sure you have the right permissions to run the associated cmdlets.</span></span>
  

   ``` Powershell
   Set-ExecutionPolicy Unrestricted
   $org='contoso.com'
   $cred=Get-Credential $admin@$org
   $sessExchange = New-PSSession -ConfigurationName microsoft.exchange -Credential $cred -AllowRedirection -Authentication Kerberos -ConnectionUri
   "http://$strExchangeServer/powershell" -WarningAction SilentlyContinue
   $sessLync = New-PSSession -Credential $cred -ConnectionURI "https://$strLyncFQDN/OcsPowershell" -AllowRedirection -WarningAction SilentlyContinue
   Import-PSSession $sessExchange
   Import-PSSession $sessLync
   ```

   <span data-ttu-id="38d40-109">Обратите внимание, что $strExchangeServer — полное доменное имя (FQDN) сервера Exchange, а $strLyncFQDN — полное доменное название развертывания Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="38d40-109">Note that $strExchangeServer is the fully qualified domain name (FQDN) of your Exchange server, and $strLyncFQDN is the FQDN of your Skype for Business Server deployment.</span></span>

2. <span data-ttu-id="38d40-110">После установления сеанса вы сможете создать новый почтовый ящик и включить его в качестве Руммаилбоксаккаунт или изменить параметры существующего почтового ящика помещения.</span><span class="sxs-lookup"><span data-stu-id="38d40-110">After establishing a session, you'll either create a new mailbox and enable it as a RoomMailboxAccount, or change the settings for an existing room mailbox.</span></span> <span data-ttu-id="38d40-111">Это позволит выполнить проверку подлинности для учетной записи в комнатах Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="38d40-111">This will allow the account to authenticate to Microsoft Teams Rooms.</span></span>

    <span data-ttu-id="38d40-112">Изменение существующего почтового ящика ресурса:</span><span class="sxs-lookup"><span data-stu-id="38d40-112">If you're changing an existing resource mailbox:</span></span>

   ``` Powershell
   Set-Mailbox -Identity 'PROJECTRIGEL01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password>
   -AsPlainText -Force)
   ```

   <span data-ttu-id="38d40-113">Если вы создаете новый почтовый ящик ресурса, сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="38d40-113">If you're creating a new resource mailbox:</span></span>

   ``` Powershell
   New-Mailbox -UserPrincipalName PROJECTRIGEL01@contoso.com -Alias PROJECTRIGEL01 -Name "Project-Rigel-01" -Room
   -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. <span data-ttu-id="38d40-114">Вы можете настроить различные свойства Exchange для учетной записи устройства, чтобы улучшить процесс собрания для пользователей.</span><span class="sxs-lookup"><span data-stu-id="38d40-114">You can set various Exchange properties on the device account to improve the meeting experience for people.</span></span> <span data-ttu-id="38d40-115">Описание необходимых настроек приводится в разделе "Свойства Exchange".</span><span class="sxs-lookup"><span data-stu-id="38d40-115">You can see which properties need to be set in the Exchange properties section.</span></span>

   ``` Powershell
   Set-CalendarProcessing -Identity $acctUpn -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments
   $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity $acctUpn -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

4. <span data-ttu-id="38d40-116">Если вы решили, что пароль не просрочен, вы можете установить его с помощью командлетов Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="38d40-116">If you decide to have the password not expire, you can set that with Windows PowerShell cmdlets too.</span></span> <span data-ttu-id="38d40-117">Дополнительные сведения см. в разделе "Управление паролями".</span><span class="sxs-lookup"><span data-stu-id="38d40-117">See Password management for more information.</span></span>

   ``` Powershell
   Set-AdUser $acctUpn -PasswordNeverExpires $true
   ```

5. <span data-ttu-id="38d40-118">Включите учетную запись в службе каталогов Active Directory, чтобы она пройдет проверку подлинности в комнатах Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="38d40-118">Enable the account in Active Directory so it will authenticate to Microsoft Teams Rooms.</span></span>

   ``` Powershell
   Set-AdUser $acctUpn -Enabled $true
   ```

6. <span data-ttu-id="38d40-119">Включите учетную запись устройства в Skype для бизнеса Server, включив учетную запись Microsoft Teams в службе каталогов Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="38d40-119">Enable the device account with Skype for Business Server by enabling your Microsoft Teams Rooms Active Directory account on a Skype for Business Server pool:</span></span>

   ``` Powershell
   Enable-CsMeetingRoom -SipAddress sip:PROJECTRIGEL01@contoso.com -DomainController DC-ND-001.contoso.com
   -RegistrarPool LYNCPool15.contoso.com -Identity PROJECTRIGEL01
   ```

    <span data-ttu-id="38d40-120">Для этого вам понадобятся SIP-адрес и контроллер домена проекта.</span><span class="sxs-lookup"><span data-stu-id="38d40-120">You'll need to use the Session Initiation Protocol (SIP) address and domain controller for the Project</span></span>

7. <span data-ttu-id="38d40-121">**Необязательный**.</span><span class="sxs-lookup"><span data-stu-id="38d40-121">**Optional.**</span></span> <span data-ttu-id="38d40-122">Вы также можете разрешить комнатам Microsoft Teams принимать и принимать телефонные звонки по коммутируемой телефонной линии (PSTN), разрешая корпоративную голосовую связь для вашей учетной записи.</span><span class="sxs-lookup"><span data-stu-id="38d40-122">You can also allow Microsoft Teams Rooms to make and receive public switched telephone network (PSTN) phone calls by enabling Enterprise Voice for your account.</span></span> <span data-ttu-id="38d40-123">Корпоративная голосовая связь не является требованием для комнат Microsoft Teams, но если вы хотите использовать функции коммутируемого набора для клиента комнат Microsoft Teams, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="38d40-123">Enterprise Voice isn't a requirement for Microsoft Teams Rooms, but if you want PSTN dialing functionality for the Microsoft Teams Rooms client, here's how to enable it:</span></span>

   ``` Powershell
   Set-CsMeetingRoom PROJECTRIGEL01 -DomainController DC-ND-001.contoso.com -LineURI "tel:+14255550555;ext=50555"
   Set-CsMeetingRoom -DomainController DC-ND-001.contoso.com -Identity PROJECTRIGEL01 -EnterpriseVoiceEnabled $true
   Grant-CsVoicePolicy -PolicyName VP1 -Identity PROJECTRIGEL01
   Grant-CsDialPlan -PolicyName DP1 -Identity PROJECTRIGEL01
   ```

   <span data-ttu-id="38d40-p106">Обратите внимание, что используемые в примере контроллер домена и номер телефона необходимо заменить данными, соответствующими вашей среде. Значение параметра $true остается прежним.</span><span class="sxs-lookup"><span data-stu-id="38d40-p106">Again, you'll need to replace the provided domain controller and phone number examples with your own information. The parameter value $true stays the same.</span></span>

## <a name="sample-room-account-setup-in-exchange-and-skype-for-business-server-on-premises"></a><span data-ttu-id="38d40-126">Пример: Настройка учетной записи комнаты в Exchange и Skype для Business Server локально</span><span class="sxs-lookup"><span data-stu-id="38d40-126">Sample: room account setup in Exchange and Skype for Business Server on premises</span></span>

``` Powershell
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

## <a name="see-also"></a><span data-ttu-id="38d40-127">См. также</span><span class="sxs-lookup"><span data-stu-id="38d40-127">See also</span></span>

[<span data-ttu-id="38d40-128">Настройка учетных записей для комнат Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="38d40-128">Configure accounts for Microsoft Teams Rooms</span></span>](rooms-configure-accounts.md)

[<span data-ttu-id="38d40-129">Планирование комнат Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="38d40-129">Plan for Microsoft Teams Rooms</span></span>](rooms-plan.md)
  
[<span data-ttu-id="38d40-130">Развертывание комнат Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="38d40-130">Deploy Microsoft Teams Rooms</span></span>](rooms-deploy.md)
  
[<span data-ttu-id="38d40-131">Настройка консоли Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="38d40-131">Configure a Microsoft Teams Rooms console</span></span>](console.md)
  
[<span data-ttu-id="38d40-132">Управление приложением "Комнаты Microsoft Teams"</span><span class="sxs-lookup"><span data-stu-id="38d40-132">Manage Microsoft Teams Rooms</span></span>](rooms-manage.md)
