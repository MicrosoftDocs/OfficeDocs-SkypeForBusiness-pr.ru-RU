---
title: Развертывание групп Майкрософт комнат с Скайп for Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
- M365-voice
ms.custom: ''
ms.assetid: a038e34d-8bc8-4a59-8ed2-3fc00ec33dd7
description: В данном разделе приведены сведения о способах развертывания комнат группами Майкрософт с Скайп для Business Server.
ms.openlocfilehash: e5ba372a5990f7c63827f1f8b0426e67ae48b620
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32207876"
---
# <a name="deploy-microsoft-teams-rooms-with-skype-for-business-server"></a><span data-ttu-id="bf78b-103">Развертывание групп Майкрософт комнат с Скайп for Business Server</span><span class="sxs-lookup"><span data-stu-id="bf78b-103">Deploy Microsoft Teams Rooms with Skype for Business Server</span></span>
  
<span data-ttu-id="bf78b-104">В этом разделе объясняется, как добавить учетную запись устройства для комнат группами Майкрософт при наличии локального развертывания одним лесом.</span><span class="sxs-lookup"><span data-stu-id="bf78b-104">This topic explains how you add a device account for Microsoft Teams Rooms when you have a single-forest, on-premises deployment.</span></span>
  
<span data-ttu-id="bf78b-105">При наличии одного леса, локальное развертывание Exchange 2013 с пакетом обновления 1 или более поздней версии и Скайп Business Server 2015 или более поздней версии отмеченными сценарии Windows PowerShell можно использовать для создания учетных записей устройства.</span><span class="sxs-lookup"><span data-stu-id="bf78b-105">If you have a single-forest, on-premises deployment with Exchange 2013 SP1 or later and Skype for Business Server 2015 or later, then you can use the provided Windows PowerShell scripts to create device accounts.</span></span> <span data-ttu-id="bf78b-106">Если вы используете развертывания нескольких лесов, можно использовать эквивалентный командлеты, которые будут создавать одинаковые результаты.</span><span class="sxs-lookup"><span data-stu-id="bf78b-106">If you're using a multi-forest deployment, you can use equivalent cmdlets that will produce the same results.</span></span> <span data-ttu-id="bf78b-107">В этой статье описываются необходимые для этого командлеты.</span><span class="sxs-lookup"><span data-stu-id="bf78b-107">Those cmdlets are described in this section.</span></span>

  
<span data-ttu-id="bf78b-108">Перед началом развертывания комнат группами Майкрософт, убедитесь, что у соответствующих разрешений для запуска связанного командлетов.</span><span class="sxs-lookup"><span data-stu-id="bf78b-108">Before you begin to deploy Microsoft Teams Rooms, be sure you have the right permissions to run the associated cmdlets.</span></span>
  

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

   <span data-ttu-id="bf78b-109">Обратите внимание на то, что $strExchangeServer — это полное доменное имя (FQDN) сервера Exchange и $strLyncFQDN — это полное доменное имя вашей Скайп для развертывания Business Server.</span><span class="sxs-lookup"><span data-stu-id="bf78b-109">Note that $strExchangeServer is the fully qualified domain name (FQDN) of your Exchange server, and $strLyncFQDN is the FQDN of your Skype for Business Server deployment.</span></span>

2. <span data-ttu-id="bf78b-110">После установки сеанса будет либо создать новый почтовый ящик и включение как RoomMailboxAccount или изменение параметров для существующего почтового ящика помещения.</span><span class="sxs-lookup"><span data-stu-id="bf78b-110">After establishing a session, you'll either create a new mailbox and enable it as a RoomMailboxAccount, or change the settings for an existing room mailbox.</span></span> <span data-ttu-id="bf78b-111">Это позволит учетной записи для проверки подлинности комнат группами Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="bf78b-111">This will allow the account to authenticate to Microsoft Teams Rooms.</span></span>

    <span data-ttu-id="bf78b-112">Изменение существующего почтового ящика ресурса:</span><span class="sxs-lookup"><span data-stu-id="bf78b-112">If you're changing an existing resource mailbox:</span></span>

   ``` Powershell
   Set-Mailbox -Identity 'PROJECTRIGEL01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password>
   -AsPlainText -Force)
   ```

   <span data-ttu-id="bf78b-113">Если вы создаете новый почтовый ящик ресурса:</span><span class="sxs-lookup"><span data-stu-id="bf78b-113">If you're creating a new resource mailbox:</span></span>

   ``` Powershell
   New-Mailbox -UserPrincipalName PROJECTRIGEL01@contoso.com -Alias PROJECTRIGEL01 -Name "Project-Rigel-01" -Room
   -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. <span data-ttu-id="bf78b-114">Можно задать различные свойства Exchange для учетной записи устройства, чтобы улучшить работу в собрание для людей.</span><span class="sxs-lookup"><span data-stu-id="bf78b-114">You can set various Exchange properties on the device account to improve the meeting experience for people.</span></span> <span data-ttu-id="bf78b-115">Описание необходимых настроек приводится в разделе "Свойства Exchange".</span><span class="sxs-lookup"><span data-stu-id="bf78b-115">You can see which properties need to be set in the Exchange properties section.</span></span>

   ``` Powershell
   Set-CalendarProcessing -Identity $acctUpn -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments
   $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity $acctUpn -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

4. <span data-ttu-id="bf78b-116">Если вы решили не срок действия пароля, можно задать, с помощью командлетов Windows PowerShell слишком.</span><span class="sxs-lookup"><span data-stu-id="bf78b-116">If you decide to have the password not expire, you can set that with Windows PowerShell cmdlets too.</span></span> <span data-ttu-id="bf78b-117">Дополнительные сведения см. в разделе "Управление паролями".</span><span class="sxs-lookup"><span data-stu-id="bf78b-117">See Password management for more information.</span></span>

   ``` Powershell
   Set-AdUser $acctUpn -PasswordNeverExpires $true
   ```

5. <span data-ttu-id="bf78b-118">Включение учетной записи в службе каталогов Active Directory, он будет выполняться проверка подлинности комнат группами Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="bf78b-118">Enable the account in Active Directory so it will authenticate to Microsoft Teams Rooms.</span></span>

   ``` Powershell
   Set-AdUser $acctUpn -Enabled $true
   ```

6. <span data-ttu-id="bf78b-119">Включение учетной записи устройства с Скайп для сервера, включив свою учетную запись Microsoft комнат группами Active Directory на Скайп для пула Business Server:</span><span class="sxs-lookup"><span data-stu-id="bf78b-119">Enable the device account with Skype for Business Server by enabling your Microsoft Teams Rooms Active Directory account on a Skype for Business Server pool:</span></span>

   ``` Powershell
   Enable-CsMeetingRoom -SipAddress sip:PROJECTRIGEL01@contoso.com -DomainController DC-ND-001.contoso.com
   -RegistrarPool LYNCPool15.contoso.com -Identity PROJECTRIGEL01
   ```

    <span data-ttu-id="bf78b-120">Для этого вам понадобятся SIP-адрес и контроллер домена проекта.</span><span class="sxs-lookup"><span data-stu-id="bf78b-120">You'll need to use the Session Initiation Protocol (SIP) address and domain controller for the Project</span></span>

7. <span data-ttu-id="bf78b-121">**Необязательный**.</span><span class="sxs-lookup"><span data-stu-id="bf78b-121">**Optional.**</span></span> <span data-ttu-id="bf78b-122">Также можно разрешить комнат группами Майкрософт для выполнения и приема телефонных звонков телефонной сети (общего пользования PSTN), позволяя корпоративной голосовой связи для вашей учетной записи.</span><span class="sxs-lookup"><span data-stu-id="bf78b-122">You can also allow Microsoft Teams Rooms to make and receive public switched telephone network (PSTN) phone calls by enabling Enterprise Voice for your account.</span></span> <span data-ttu-id="bf78b-123">Корпоративной голосовой связи не является обязательным требованием для комнат группы Microsoft, но если требуется использовать возможности набора номера ТСОП для клиента комнат группами Майкрософт, здесь — это способ его включения:</span><span class="sxs-lookup"><span data-stu-id="bf78b-123">Enterprise Voice isn't a requirement for Microsoft Teams Rooms, but if you want PSTN dialing functionality for the Microsoft Teams Rooms client, here's how to enable it:</span></span>

   ``` Powershell
   Set-CsMeetingRoom PROJECTRIGEL01 -DomainController DC-ND-001.contoso.com -LineURI "tel:+14255550555;ext=50555"
   Set-CsMeetingRoom -DomainController DC-ND-001.contoso.com -Identity PROJECTRIGEL01 -EnterpriseVoiceEnabled $true
   Grant-CsVoicePolicy -PolicyName VP1 -Identity PROJECTRIGEL01
   Grant-CsDialPlan -PolicyName DP1 -Identity PROJECTRIGEL01
   ```

   <span data-ttu-id="bf78b-p106">Обратите внимание, что используемые в примере контроллер домена и номер телефона необходимо заменить данными, соответствующими вашей среде. Значение параметра $true остается прежним.</span><span class="sxs-lookup"><span data-stu-id="bf78b-p106">Again, you'll need to replace the provided domain controller and phone number examples with your own information. The parameter value $true stays the same.</span></span>

## <a name="sample-room-account-setup-in-exchange-and-skype-for-business-server-on-premises"></a><span data-ttu-id="bf78b-126">Пример: Настройка учетной записи помещения в Exchange и Скайп для Business Server локально</span><span class="sxs-lookup"><span data-stu-id="bf78b-126">Sample: room account setup in Exchange and Skype for Business Server on premises</span></span>

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

## <a name="see-also"></a><span data-ttu-id="bf78b-127">См. также</span><span class="sxs-lookup"><span data-stu-id="bf78b-127">See also</span></span>

[<span data-ttu-id="bf78b-128">Настройка учетных записей для комнат группами Майкрософт</span><span class="sxs-lookup"><span data-stu-id="bf78b-128">Configure accounts for Microsoft Teams Rooms</span></span>](room-systems-v2-configure-accounts.md)

[<span data-ttu-id="bf78b-129">Планирование для групп Майкрософт комнат</span><span class="sxs-lookup"><span data-stu-id="bf78b-129">Plan for Microsoft Teams Rooms</span></span>](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)
  
[<span data-ttu-id="bf78b-130">Развертывание групп Майкрософт комнат</span><span class="sxs-lookup"><span data-stu-id="bf78b-130">Deploy Microsoft Teams Rooms</span></span>](room-systems-v2.md)
  
[<span data-ttu-id="bf78b-131">Настройка консоли комнат группами Майкрософт</span><span class="sxs-lookup"><span data-stu-id="bf78b-131">Configure a Microsoft Teams Rooms console</span></span>](console.md)
  
[<span data-ttu-id="bf78b-132">Управление приложением "Комнаты Microsoft Teams"</span><span class="sxs-lookup"><span data-stu-id="bf78b-132">Manage Microsoft Teams Rooms</span></span>](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)