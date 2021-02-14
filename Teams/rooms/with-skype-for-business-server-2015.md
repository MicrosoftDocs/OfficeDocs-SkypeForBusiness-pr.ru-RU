---
title: Развертывание комнат Microsoft Teams с помощью Skype для бизнеса Server
ms.author: dstrome
author: dstrome
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
ms.assetid: a038e34d-8bc8-4a59-8ed2-3fc00ec33dd7
description: Сведения о том, как развернуть комнаты Microsoft Teams в Skype для бизнеса Server, можно найти в этой теме.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 9ee33ec1ded7e8461f629c4552236ee60828a168
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662264"
---
# <a name="deploy-microsoft-teams-rooms-with-skype-for-business-server"></a>Развертывание комнат Microsoft Teams с помощью Skype для бизнеса Server
  
В этой теме объясняется, как добавить учетную запись устройства для комнат Microsoft Teams при локальном развертывании с одним лесом.
  
Если вы используете один лес, локальное развертывание с Exchange 2013 с sp1 или более поздней и Skype для бизнеса Server 2015 или более поздней, вы можете использовать предоставленные сценарии Windows PowerShell для создания учетных записей устройств. При развертывании с несколькими лесами можно использовать эквивалентные cmdlets, которые будут создавать одинаковые результаты. В этой статье описываются необходимые для этого командлеты.

  
Прежде чем приступить к развертыванию комнат Microsoft Teams, убедитесь, что у вас есть права на запуск связанных командлетов.
  

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

   Обратите внимание$strExchangeServer что $strExchangeServer — это полное доменное имя вашего сервера Exchange, а $strLyncFQDN — полное доменное имя развертывания Skype для бизнеса Server.

2. После создания сеанса вам нужно будет создать новый почтовый ящик и включить его в качестве учетной записи RoomMailboxAccount или изменить параметры для существующего почтового ящика помещения. Это позволит учетной записи аутентификацию в комнатах Microsoft Teams.

    Изменение существующего почтового ящика ресурса:

   ``` Powershell
   Set-Mailbox -Identity 'PROJECTRIGEL01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password>
   -AsPlainText -Force)
   ```

   Если вы создаете новый почтовый ящик ресурса:

   ``` Powershell
   New-Mailbox -UserPrincipalName PROJECTRIGEL01@contoso.com -Alias PROJECTRIGEL01 -Name "Project-Rigel-01" -Room
   -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. Вы можете настроить различные свойства Exchange в учетной записи устройства, чтобы улучшить качество собраний для пользователей. Описание необходимых настроек приводится в разделе "Свойства Exchange".

   ``` Powershell
   Set-CalendarProcessing -Identity $acctUpn -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments
   $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity $acctUpn -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

4. Если вы решите, что срок действия пароля не истек, можно также Windows PowerShell с помощью Windows PowerShell. Дополнительные сведения см. в разделе "Управление паролями".

   ``` Powershell
   Set-AdUser $acctUpn -PasswordNeverExpires $true
   ```

5. В включить учетную запись в Active Directory, чтобы она пройдет проверку подлинности в комнатах Microsoft Teams.

   ``` Powershell
   Set-AdUser $acctUpn -Enabled $true
   ```

6. Включите учетную запись устройства с помощью Skype для бизнеса Server, включив учетную запись Microsoft Teams Rooms Active Directory в пул Skype для бизнеса Server.

   ``` Powershell
   Enable-CsMeetingRoom -SipAddress sip:PROJECTRIGEL01@contoso.com -DomainController DC-ND-001.contoso.com
   -RegistrarPool LYNCPool15.contoso.com -Identity PROJECTRIGEL01
   ```

    Для этого вам понадобятся SIP-адрес и контроллер домена проекта.

7. **Необязательный**. Вы также можете разрешить комнаты Microsoft Teams делать и принимать телефонные вызовы телефонной сети общего звонков с Корпоративная голосовая связь телефонной сети общего звонков, включив Корпоративная голосовая связь для вашей учетной записи. Корпоративная голосовая связь не является обязательной возможностью использовать комнаты Microsoft Teams, но если вы хотите, чтобы для клиента комнат Microsoft Teams были функции набора по СТАНП, вот как это сделать:

   ``` Powershell
   Set-CsMeetingRoom PROJECTRIGEL01 -DomainController DC-ND-001.contoso.com -LineURI "tel:+14255550555;ext=50555"
   Set-CsMeetingRoom -DomainController DC-ND-001.contoso.com -Identity PROJECTRIGEL01 -EnterpriseVoiceEnabled $true
   Grant-CsVoicePolicy -PolicyName VP1 -Identity PROJECTRIGEL01
   Grant-CsDialPlan -PolicyName DP1 -Identity PROJECTRIGEL01
   ```

   Обратите внимание, что используемые в примере контроллер домена и номер телефона необходимо заменить данными, соответствующими вашей среде. Значение параметра $true остается прежним.

## <a name="sample-room-account-setup-in-exchange-and-skype-for-business-server-on-premises"></a>Пример: настройка учетной записи помещения в локальной сети Exchange и Skype для бизнеса Server

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

## <a name="related-topics"></a>Статьи по теме

[Настройка учетных записей для комнат Microsoft Teams](rooms-configure-accounts.md)

[Планирование комнат Microsoft Teams](rooms-plan.md)
  
[Развертывание комнат Microsoft Teams](rooms-deploy.md)
  
[Настройка консоли комнат Microsoft Teams](console.md)
  
[Управление комнатами Microsoft Teams](rooms-manage.md)
