---
title: Развертывание Комнаты Microsoft Teams с помощью Skype для бизнеса Server
ms.author: czawideh
author: cazawideh
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
ms.assetid: a038e34d-8bc8-4a59-8ed2-3fc00ec33dd7
description: Дополнительные сведения о развертывании Комнаты Microsoft Teams с помощью Skype для бизнеса Server.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 358fa9295ec150f9c57a18252c76d309078b8e29
ms.sourcegitcommit: a894e9397050e09bfaab02e700e943a3bbeb1302
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2022
ms.locfileid: "63503486"
---
# <a name="deploy-microsoft-teams-rooms-with-skype-for-business-server"></a>Развертывание Комнаты Microsoft Teams с помощью Skype для бизнеса Server
  
В этой теме объясняется, как добавить учетную запись ресурса для Комнаты Microsoft Teams при развертывании с одним лесом в локальном развертывании.
  
Если у вас один лес, локальное развертывание с Exchange 2013 с SP1 или более поздней и Skype для бизнеса Server 2015 или более поздней, то вы можете создавать учетные записи устройств с помощью Windows PowerShell сценариев. При развертывании с несколькими лесами можно использовать эквивалентные cmdlets, которые будут работать с одинаковыми результатами. В этой статье описываются необходимые для этого командлеты.
  
Прежде чем приступить к развертыванию Комнаты Microsoft Teams, убедитесь, что у вас есть права на запуск связанных с ней cmdlets.
  

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

   Обратите внимание$strExchangeServer что $strExchangeServer — это полное доменное имя вашего сервера Exchange, а $strLyncFQDN — полное доменное Skype для бизнеса Server развертывания.

2. После создания сеанса вы либо создайте новый почтовый ящик, чтобы включить его в качестве учетной записи RoomMailboxAccount, либо измените параметры существующего почтового ящика комнаты. Это позволит учетной записи проверить подлинность для Комнаты Microsoft Teams.

    Изменение существующего почтового ящика ресурса:

   ``` Powershell
   Set-Mailbox -Identity 'ConferenceRoome01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password>
   -AsPlainText -Force)
   ```

   Если вы создаете новый почтовый ящик ресурса:

   ``` Powershell
   New-Mailbox -UserPrincipalName ConferenceRoom01@contoso.com -Alias ConferenceRoom01 -Name "Conference Room 01" -Room
   -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. Вы можете настроить различные Exchange в учетной записи Комнаты Teams ресурсов, чтобы улучшить качество собраний для пользователей. Описание необходимых настроек приводится в разделе "Свойства Exchange".

   ``` Powershell
   Set-CalendarProcessing -Identity ConferenceRoom01 -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments
   $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity ConferenceRoom01 -AddAdditionalResponse $true -AdditionalResponse "This is a Microsoft Teams and Skype for Business meeting room!"
   ```

4. Отключите срок действия пароля для учетной записи ресурса.

   ``` Powershell
   Set-AdUser ConferenceRoom01@contoso.com -PasswordNeverExpires $true
   ```

5. В этой службе можно включить учетную запись ресурса в Active Directory, чтобы она пройдет проверку подлинности Комнаты Microsoft Teams.

   ``` Powershell
   Set-AdUser ConferenceRoom01@contoso.com -Enabled $true
   ```

6. Включите учетную запись ресурса Skype для бизнеса Server, включив учетную запись Комнаты Microsoft Teams Active Directory в Skype для бизнеса Server пуле:

   ``` Powershell
   Enable-CsMeetingRoom -Identity ConferenceRoom01 -SipAddress sip:ConferenceRoom01@contoso.com -DomainController DC-ND-001.contoso.com
   -RegistrarPool LYNCPool15.contoso.com 
   ```

    Измените `-DomainController` значения и `-RegistrarPool` атрибуты на значения, подходящие для вашей среды.

7. **Необязательный**. Вы также можете разрешить Комнаты Microsoft Teams телефонную сеть общего звонков (STN), включив Корпоративная голосовая связь для вашей учетной записи. Корпоративная голосовая связь не является требованием для Комнаты Microsoft Teams, но если вы хотите использовать функции набора номера через Комнаты Microsoft Teams, вот как это сделать:

   ``` Powershell
   Set-CsMeetingRoom -Identity ConferenceRoom01 -DomainController DC-ND-001.contoso.com -LineURI "tel:+14255550555;ext=50555"
   Set-CsMeetingRoom -Identity ConferenceRoom01 -DomainController DC-ND-001.contoso.com -EnterpriseVoiceEnabled $true
   Grant-CsVoicePolicy -Identity ConferenceRoom01 -PolicyName VP1
   Grant-CsDialPlan -Identity ConferenceRoom01 -PolicyName DP1
   ```

   Обратите внимание, что используемые в примере контроллер домена и номер телефона необходимо заменить данными, соответствующими вашей среде. Значение параметра $true остается прежним. Вам также потребуется заменить названия политик голосовой политики и плана набора номера.

## <a name="sample-room-account-setup-in-exchange-and-skype-for-business-server-on-premises"></a>Пример: настройка учетной записи Exchange и Skype для бизнеса Server локально

``` Powershell
New-Mailbox -Alias ConferenceRoom01 -Name "Conference Room 01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String "" -AsPlainText -Force) -UserPrincipalName ConferenceRoom01@contoso.com

Set-CalendarProcessing -Identity ConferenceRoom01 -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
Set-CalendarProcessing -Identity ConferenceRoom01 -AddAdditionalResponse $true -AdditionalResponse "This is a Microsoft Teams and Skype for Business meeting room!"

Enable-CsMeetingRoom -Identity ConferenceRoom01@contoso.com -RegistrarPool cs3.contoso.com -SipAddressType EmailAddress
Set-CsMeetingRoom -Identity ConferenceRoom01 -EnterpriseVoiceEnabled $true -LineURI tel:+155555555555
Grant-CsVoicePolicy -Identity ConferenceRoom01 -PolicyName dk
Grant-CsDialPlan -Identity ConferenceRoom01 -PolicyName e15dp2.contoso.com
```

## <a name="related-topics"></a>Статьи по теме

[Настройка учетных записей для Комнаты Microsoft Teams](rooms-configure-accounts.md)

[Планирование комнат Microsoft Teams](rooms-plan.md)
  
[Развертывание комнат Microsoft Teams](rooms-deploy.md)
  
[Настройка консоли комнат Microsoft Teams](console.md)
  
[Управление комнатами Microsoft Teams](rooms-manage.md)
