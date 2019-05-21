---
title: Развертывание комнат Microsoft Teams с помощью Skype для бизнеса Server
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
- M365-voice
ms.custom: ''
ms.assetid: a038e34d-8bc8-4a59-8ed2-3fc00ec33dd7
description: В этой статье приведены сведения о том, как развертывать комнаты Microsoft Teams в Skype для бизнеса Server.
ms.openlocfilehash: a0e476738cb1ff68020b87624cbcdbabb220c248
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34288446"
---
# <a name="deploy-microsoft-teams-rooms-with-skype-for-business-server"></a>Развертывание комнат Microsoft Teams с помощью Skype для бизнеса Server
  
В этой статье объясняется, как добавить учетную запись устройства для комнат Microsoft Teams, если у вас есть развертывание с одним лесом и локальным.
  
Если у вас есть локальное развертывание с Exchange 2013 с пакетом обновления 1 (SP1) или более поздней версии, а также Skype для бизнеса Server 2015 или более поздней версии, вы можете использовать указанные сценарии Windows PowerShell для создания учетных записей устройств. Если вы используете развертывание с несколькими лесами, вы можете использовать эквивалентные командлеты, которые будут давать одинаковые результаты. В этой статье описываются необходимые для этого командлеты.

  
Перед развертыванием комнат Microsoft Teams убедитесь, что у вас есть необходимые разрешения для выполнения соответствующих командлетов.
  

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

   Обратите внимание, что $strExchangeServer — полное доменное имя (FQDN) сервера Exchange, а $strLyncFQDN — полное доменное название развертывания Skype для бизнеса Server.

2. После установления сеанса вы сможете создать новый почтовый ящик и включить его в качестве Руммаилбоксаккаунт или изменить параметры существующего почтового ящика помещения. Это позволит выполнить проверку подлинности для учетной записи в комнатах Microsoft Teams.

    Изменение существующего почтового ящика ресурса:

   ``` Powershell
   Set-Mailbox -Identity 'PROJECTRIGEL01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password>
   -AsPlainText -Force)
   ```

   Если вы создаете новый почтовый ящик ресурса, сделайте следующее:

   ``` Powershell
   New-Mailbox -UserPrincipalName PROJECTRIGEL01@contoso.com -Alias PROJECTRIGEL01 -Name "Project-Rigel-01" -Room
   -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. Вы можете настроить различные свойства Exchange для учетной записи устройства, чтобы улучшить процесс собрания для пользователей. Описание необходимых настроек приводится в разделе "Свойства Exchange".

   ``` Powershell
   Set-CalendarProcessing -Identity $acctUpn -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments
   $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity $acctUpn -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

4. Если вы решили, что пароль не просрочен, вы можете установить его с помощью командлетов Windows PowerShell. Дополнительные сведения см. в разделе "Управление паролями".

   ``` Powershell
   Set-AdUser $acctUpn -PasswordNeverExpires $true
   ```

5. Включите учетную запись в службе каталогов Active Directory, чтобы она пройдет проверку подлинности в комнатах Microsoft Teams.

   ``` Powershell
   Set-AdUser $acctUpn -Enabled $true
   ```

6. Включите учетную запись устройства в Skype для бизнеса Server, включив учетную запись Microsoft Teams в службе каталогов Skype для бизнеса Server.

   ``` Powershell
   Enable-CsMeetingRoom -SipAddress sip:PROJECTRIGEL01@contoso.com -DomainController DC-ND-001.contoso.com
   -RegistrarPool LYNCPool15.contoso.com -Identity PROJECTRIGEL01
   ```

    Для этого вам понадобятся SIP-адрес и контроллер домена проекта.

7. **Необязательный**. Вы также можете разрешить комнатам Microsoft Teams принимать и принимать телефонные звонки по коммутируемой телефонной линии (PSTN), разрешая корпоративную голосовую связь для вашей учетной записи. Корпоративная голосовая связь не является требованием для комнат Microsoft Teams, но если вы хотите использовать функции коммутируемого набора для клиента комнат Microsoft Teams, выполните указанные ниже действия.

   ``` Powershell
   Set-CsMeetingRoom PROJECTRIGEL01 -DomainController DC-ND-001.contoso.com -LineURI "tel:+14255550555;ext=50555"
   Set-CsMeetingRoom -DomainController DC-ND-001.contoso.com -Identity PROJECTRIGEL01 -EnterpriseVoiceEnabled $true
   Grant-CsVoicePolicy -PolicyName VP1 -Identity PROJECTRIGEL01
   Grant-CsDialPlan -PolicyName DP1 -Identity PROJECTRIGEL01
   ```

   Обратите внимание, что используемые в примере контроллер домена и номер телефона необходимо заменить данными, соответствующими вашей среде. Значение параметра $true остается прежним.

## <a name="sample-room-account-setup-in-exchange-and-skype-for-business-server-on-premises"></a>Пример: Настройка учетной записи комнаты в Exchange и Skype для Business Server локально

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

## <a name="see-also"></a>См. также

[Настройка учетных записей для комнат Microsoft Teams](room-systems-v2-configure-accounts.md)

[Планирование комнат Microsoft Teams](skype-room-systems-v2-0.md)
  
[Развертывание комнат Microsoft Teams](room-systems-v2.md)
  
[Настройка консоли Microsoft Teams](console.md)
  
[Управление приложением "Комнаты Microsoft Teams"](skype-room-systems-v2.md)
