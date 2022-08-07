---
title: Развертывание Комнаты Microsoft Teams с Skype для бизнеса Server
ms.author: dstrome
author: dstrome
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
- Teams_ITAdmin_Rooms
ms.assetid: a038e34d-8bc8-4a59-8ed2-3fc00ec33dd7
description: В этом разделе содержатся сведения о развертывании Комнаты Microsoft Teams с Skype для бизнеса Server.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 53903052efe28a85400ba8b418bd8869ef2dec4e
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/07/2022
ms.locfileid: "67271684"
---
# <a name="deploy-microsoft-teams-rooms-with-skype-for-business-server"></a>Развертывание Комнаты Microsoft Teams с Skype для бизнеса Server
  
В этом разделе объясняется, как добавить учетную запись ресурса Комнаты Microsoft Teams при развертывании с одним лесом в локальной среде.
  
Если у вас есть один лес, локальное развертывание с Exchange 2013 с пакетом обновления 1 (SP1) или более поздней версии и Skype для бизнеса Server 2015 или более поздней версии, можно использовать предоставленные скрипты Windows PowerShell для создания учетных записей устройств. Если вы используете развертывание с несколькими лесами, можно использовать эквивалентные командлеты, которые будут давать те же результаты. В этой статье описываются необходимые для этого командлеты.
  
Прежде чем приступить к развертыванию Комнаты Microsoft Teams, убедитесь, что у вас есть необходимые разрешения для запуска связанных командлетов.
  

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

   Обратите внимание$strExchangeServer что это полное доменное имя (FQDN) сервера Exchange, а $strLyncFQDN — полное доменное имя Skype для бизнеса Server развертывания.

2. После создания сеанса вы создадите новый почтовый ящик и включите его в качестве учетной записи RoomMailboxAccount или измените параметры для существующего почтового ящика помещения. Это позволит учетной записи выполнять проверку подлинности Комнаты Microsoft Teams.

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

3. Вы можете задать различные свойства Exchange в учетной записи Комнаты Teams, чтобы улучшить взаимодействие с пользователями. Описание необходимых настроек приводится в разделе "Свойства Exchange".

   ``` Powershell
   Set-CalendarProcessing -Identity ConferenceRoom01 -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments
   $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity ConferenceRoom01 -AddAdditionalResponse $true -AdditionalResponse "This is a Microsoft Teams and Skype for Business meeting room!"
   ```

4. Отключите срок действия пароля для учетной записи ресурса.

   ``` Powershell
   Set-AdUser ConferenceRoom01@contoso.com -PasswordNeverExpires $true
   ```

5. Включите учетную запись ресурса в Active Directory, чтобы она была Комнаты Microsoft Teams.

   ``` Powershell
   Set-AdUser ConferenceRoom01@contoso.com -Enabled $true
   ```

6. Включите учетную запись ресурса с Skype для бизнеса Server, включив учетную запись Комнаты Microsoft Teams Active Directory в Skype для бизнеса Server пуле:

   ``` Powershell
   Enable-CsMeetingRoom -Identity ConferenceRoom01 -SipAddress sip:ConferenceRoom01@contoso.com -DomainController DC-ND-001.contoso.com
   -RegistrarPool LYNCPool15.contoso.com 
   ```

    Измените значения `-DomainController` и `-RegistrarPool` атрибуты на значения, соответствующие вашей среде.

7. **Необязательный**. Вы также можете разрешить Комнаты Microsoft Teams совершать и принимать телефонные звонки по общедоступной телефонной сети (ТСОП), включив Корпоративная голосовая связь для своей учетной записи. Корпоративная голосовая связь не является требованием для Комнаты Microsoft Teams, но если вы хотите использовать функцию набора ТСОП для Комнаты Microsoft Teams, включите ее следующим образом:

   ``` Powershell
   Set-CsMeetingRoom -Identity ConferenceRoom01 -DomainController DC-ND-001.contoso.com -LineURI "tel:+14255550555;ext=50555"
   Set-CsMeetingRoom -Identity ConferenceRoom01 -DomainController DC-ND-001.contoso.com -EnterpriseVoiceEnabled $true
   Grant-CsVoicePolicy -Identity ConferenceRoom01 -PolicyName VP1
   Grant-CsDialPlan -Identity ConferenceRoom01 -PolicyName DP1
   ```

   Обратите внимание, что используемые в примере контроллер домена и номер телефона необходимо заменить данными, соответствующими вашей среде. Значение параметра $true остается прежним. Вам также потребуется заменить политику голосовой связи и имена политик абонентской группы.

## <a name="sample-room-account-setup-in-exchange-and-skype-for-business-server-on-premises"></a>Пример: настройка учетной записи комнаты в Exchange и Skype для бизнеса Server локально

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
