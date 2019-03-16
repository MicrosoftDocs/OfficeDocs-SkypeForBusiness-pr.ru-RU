---
title: Развертывание Скайп комнаты v2 систем с Скайп для Business Server
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
ms.custom: ''
ms.assetid: a038e34d-8bc8-4a59-8ed2-3fc00ec33dd7
description: В данном разделе приведены сведения о способах развертывания систем комнаты Скайп версии 2 с Скайп для Business Server.
ms.openlocfilehash: 5159d9cc8835ebe2b6e1d74e2f7644ee11232b63
ms.sourcegitcommit: a589b86520028d8751653386265f6ce1e066818b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/16/2019
ms.locfileid: "30645396"
---
# <a name="deploy-skype-room-systems-v2-with-skype-for-business-server"></a>Развертывание Скайп комнаты v2 систем с Скайп для Business Server
  
В этом разделе объясняется, как добавить учетную запись устройства для систем комнаты Скайп версии 2 при наличии одним лесом локального развертывания.
  
При наличии одного леса, локальное развертывание Exchange 2013 с пакетом обновления 1 или более поздней версии и Скайп Business Server 2015 или более поздней версии отмеченными сценарии Windows PowerShell можно использовать для создания учетных записей устройства. Если вы используете развертывания нескольких лесов, можно использовать эквивалентный командлеты, которые будут создавать одинаковые результаты. В этой статье описываются необходимые для этого командлеты.

Настройка учетных записей пользователей проще всего настроить их с помощью удаленной оболочки Windows PowerShell. Корпорация Майкрософт предоставляет [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), сценарий, который поможет создать новые учетные записи пользователей, или validate существующие учетные записи ресурсов, что у вас есть помогающих перевод их в совместимые учетных записей пользователей системы комнаты Скайп версии 2. При необходимости можно выполните следующие действия, чтобы настроить учетные записи, используемые устройства версии 2 Скайп комнаты систем.

## <a name="requirements"></a>Требования

Перед развертыванием системы комнаты Скайп версии 2 с Скайп для Business Server убедитесь, что удовлетворены требования. Дополнительные сведения см. в разделе [Skype Room Systems v2 requirements](../../plan-your-deployment/clients-and-devices/requirements.md).
  
Перед началом развертывания систем комнаты Скайп версии 2, убедитесь, что у соответствующих разрешений для запуска связанного командлетов.
  
1. Для запуска удаленного сеанса Windows PowerShell с ПК и подключитесь к Exchange.

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

2. После установки сеанса будет либо создать новый почтовый ящик и включение как RoomMailboxAccount или изменение параметров для существующего почтового ящика помещения. Это позволит учетной записи для проверки подлинности системы комнаты Скайп версии 2.

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

5. Включение учетной записи в службе каталогов Active Directory, он будет выполнять проверку подлинности для систем комнаты Скайп версии 2.

   ``` Powershell
   Set-AdUser $acctUpn -Enabled $true
   ```

6. Включение учетной записи устройства с Скайп для сервера, включив свою учетную запись Active Directory систем комнаты Скайп версии 2 на Скайп для пула Business Server:

   ``` Powershell
   Enable-CsMeetingRoom -SipAddress sip:PROJECTRIGEL01@contoso.com -DomainController DC-ND-001.contoso.com
   -RegistrarPool LYNCPool15.contoso.com -Identity PROJECTRIGEL01
   ```

    Для этого вам понадобятся SIP-адрес и контроллер домена проекта.

7. **Необязательный**. Также можно разрешить систем комнаты Скайп v2 для выполнения и приема телефонных звонков телефонной сети (общего пользования PSTN), позволяя корпоративной голосовой связи для вашей учетной записи. Корпоративной голосовой связи не является обязательным требованием для систем комнаты Скайп версии 2, но если требуется использовать возможности набора номера ТСОП для клиентских систем комнаты Скайп версии 2, здесь — это способ его включения:

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

[Настройка учетных записей для систем комнаты Скайп версии 2](room-systems-v2-configure-accounts.md)

[Plan for Skype Room Systems v2](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)
  
[Развертывание Систем комнат Skype версии 2](room-systems-v2.md)
  
[Настройка консоли для Систем комнат Skype версии 2](console.md)
  
[Управление Системами комнат Skype версии 2](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)