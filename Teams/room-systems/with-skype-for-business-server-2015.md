---
title: Развертывание групп Майкрософт комнат с Скайп for Business Server
ms.author: v-lanac
author: lanachin
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
ms.openlocfilehash: f62006dc3f83d6f60c224f8e75ba4958ff0a7bfc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33915799"
---
# <a name="deploy-microsoft-teams-rooms-with-skype-for-business-server"></a>Развертывание групп Майкрософт комнат с Скайп for Business Server
  
В этом разделе объясняется, как добавить учетную запись устройства для комнат группами Майкрософт при наличии локального развертывания одним лесом.
  
При наличии одного леса, локальное развертывание Exchange 2013 с пакетом обновления 1 или более поздней версии и Скайп Business Server 2015 или более поздней версии отмеченными сценарии Windows PowerShell можно использовать для создания учетных записей устройства. Если вы используете развертывания нескольких лесов, можно использовать эквивалентный командлеты, которые будут создавать одинаковые результаты. В этой статье описываются необходимые для этого командлеты.

  
Перед началом развертывания комнат группами Майкрософт, убедитесь, что у соответствующих разрешений для запуска связанного командлетов.
  

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

   Обратите внимание на то, что $strExchangeServer — это полное доменное имя (FQDN) сервера Exchange и $strLyncFQDN — это полное доменное имя вашей Скайп для развертывания Business Server.

2. После установки сеанса будет либо создать новый почтовый ящик и включение как RoomMailboxAccount или изменение параметров для существующего почтового ящика помещения. Это позволит учетной записи для проверки подлинности комнат группами Майкрософт.

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

3. Можно задать различные свойства Exchange для учетной записи устройства, чтобы улучшить работу в собрание для людей. Описание необходимых настроек приводится в разделе "Свойства Exchange".

   ``` Powershell
   Set-CalendarProcessing -Identity $acctUpn -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments
   $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity $acctUpn -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

4. Если вы решили не срок действия пароля, можно задать, с помощью командлетов Windows PowerShell слишком. Дополнительные сведения см. в разделе "Управление паролями".

   ``` Powershell
   Set-AdUser $acctUpn -PasswordNeverExpires $true
   ```

5. Включение учетной записи в службе каталогов Active Directory, он будет выполняться проверка подлинности комнат группами Майкрософт.

   ``` Powershell
   Set-AdUser $acctUpn -Enabled $true
   ```

6. Включение учетной записи устройства с Скайп для сервера, включив свою учетную запись Microsoft комнат группами Active Directory на Скайп для пула Business Server:

   ``` Powershell
   Enable-CsMeetingRoom -SipAddress sip:PROJECTRIGEL01@contoso.com -DomainController DC-ND-001.contoso.com
   -RegistrarPool LYNCPool15.contoso.com -Identity PROJECTRIGEL01
   ```

    Для этого вам понадобятся SIP-адрес и контроллер домена проекта.

7. **Необязательный**. Также можно разрешить комнат группами Майкрософт для выполнения и приема телефонных звонков телефонной сети (общего пользования PSTN), позволяя корпоративной голосовой связи для вашей учетной записи. Корпоративной голосовой связи не является обязательным требованием для комнат группы Microsoft, но если требуется использовать возможности набора номера ТСОП для клиента комнат группами Майкрософт, здесь — это способ его включения:

   ``` Powershell
   Set-CsMeetingRoom PROJECTRIGEL01 -DomainController DC-ND-001.contoso.com -LineURI "tel:+14255550555;ext=50555"
   Set-CsMeetingRoom -DomainController DC-ND-001.contoso.com -Identity PROJECTRIGEL01 -EnterpriseVoiceEnabled $true
   Grant-CsVoicePolicy -PolicyName VP1 -Identity PROJECTRIGEL01
   Grant-CsDialPlan -PolicyName DP1 -Identity PROJECTRIGEL01
   ```

   Обратите внимание, что используемые в примере контроллер домена и номер телефона необходимо заменить данными, соответствующими вашей среде. Значение параметра $true остается прежним.

## <a name="sample-room-account-setup-in-exchange-and-skype-for-business-server-on-premises"></a>Пример: Настройка учетной записи помещения в Exchange и Скайп для Business Server локально

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

[Настройка учетных записей для комнат группами Майкрософт](room-systems-v2-configure-accounts.md)

[Планирование для групп Майкрософт комнат](skype-room-systems-v2-0.md)
  
[Развертывание групп Майкрософт комнат](room-systems-v2.md)
  
[Настройка консоли комнат группами Майкрософт](console.md)
  
[Управление приложением "Комнаты Microsoft Teams"](skype-room-systems-v2.md)
