---
title: Локальное развертывание системы комнат Skype с одним лесом
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 80da9d71-3dcd-4ca4-8bd1-6d8196823206
description: В этом разделе вы узнаете, как развернуть систему комнат Skype в локальной среде с одним лесом.
ms.openlocfilehash: 0449a5e909fa044df12766aec0a036bf97315386
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820759"
---
# <a name="skype-room-system-single-forest-on-premises-deployments"></a>Локальное развертывание системы комнат Skype с одним лесом
 
В этом разделе вы узнаете, как развернуть систему комнат Skype в локальной среде с одним лесом.
  
В этом разделе приводится обзор действий по обеспечению учетной записи системы комнат Skype в локальном развертывании Exchange Server и Skype для бизнеса Server, размещенной в локальном развертывании с одним лесом.
  
## <a name="single-forest-on-premises-deployments"></a>Локальные развертывания с одним лесом

Если у вас уже есть учетная запись почтового ящика ресурса для комнаты, вы можете использовать ее. В противном случае потребуется создать новый. Для создания новой учетной записи почтового ящика ресурса можно использовать либо оболочку управления Exchange (PowerShell), либо консоль управления Exchange. Мы рекомендуем использовать новый (удалить старый почтовый ящик и повторно создать) почтовый ящик ресурса для системы комнат Skype. Перед удалением убедитесь в том, что необходимо создать их базу данных почтового ящика, а затем экспортировать их обратно в повторно созданный почтовый ящик с помощью клиента Outlook (дополнительные сведения см. в этой теме. Чтобы восстановить собрания, потерянные при удалении почтового ящика, см. в подключении или [восстановлении удаленного почтового ящика.](https://technet.microsoft.com/library/jj863438%28v=exchg.150%29.aspx) 
  
Чтобы использовать существующую учетную запись почтового ящика ресурса (например, LRS-01), выполните следующие действия.
  
1. Запустите следующую команду Exchange Management PowerShell:
    
   ```powershell
   Set-Mailbox -Name 'LRS-01' -Alias 'LRS01' -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

2. Если вы планируете создать почтовый ящик, для локальной организации Exchange с одним лесом запустите следующую команду:
    
   ```powershell
   New-Mailbox -UserPrincipalName LRS01@contoso.com -Alias LRS01 -Name "LRS-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

   В примере выше создается включенная учетная запись пользователя в Active Directory и почтовый ящик помещения для конференц-зала в локальной организации Exchange. Параметр RoomMailboxPassword указывает пароль для учетной записи пользователя.
    
3. Настройте учетную запись для автоматического разрешения конфликтов, принимая или отклоняет собрания. Учетными записями конференц-залов, оснащенными системой комнат Skype, в Exchange могут управлять отдельные пользователи, но обратите внимание, что до тех пор, пока отдельный человек не примет собрание, оно не будет отображаться в календаре домашнего экрана системы комнат Skype.
    
   ```powershell
   Set-CalendarProcessing -Identity LRS01 -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteSubject $false -RemovePrivateProperty $false
   ```

   Полный набор доступных команд см. в командной части Set-CalendarProcessing.
    
   Чтобы напомнить организаторам собрания, что собрание необходимо сделать собранием Skype для бизнеса по сети в Outlook, запустите следующую команду, чтобы настроить для новой учетной записи mailTip следующую команду: 
    
   ```powershell
   Set-Mailbox -Identity LRS01@contoso.com -MailTip "This room is equipped with Lync Meeting Room (LRS), please make it a Lync Meeting to take advantage of the enhanced meeting experience from LRS"
   ```
4. Используйте следующие команды для настройки локализованных строк. При необходимости в организации можно также добавить настраиваемые переводы: 
   ```powershell
   $Temp = Get-Mailbox  LRS01@ contoso.com 
   $Temp.MailTipTranslations += "ES: Spanish translation of the message"
   Set-Mailbox -Identity LRS01@contoso.com -MailTipTranslations $Temp.MailTipTranslations
   ```

5. Необязательно: настройте текст приемки собрания, который предоставляет пользователям сведения о комнате для собраний Skype для бизнеса и о том, что следует ожидать при их расписании и подмыве собрания. 
    
   ```powershell
   Set-CalendarProcessing -Identity LRS01 -AddAdditionalResponse $TRUE -AdditionalResponse "This is the Additional Response Text"
   ```

## <a name="check-resource-mailbox-account-in-active-directory"></a>Проверка учетной записи почтового ящика ресурса в Active Directory

Учетная запись почтового ящика конференц-зала, созданная Exchange на шаге 1 выше, может быть отключенным объектом пользователя в Active Directory. Skype Room System cannot sign in or authenticate by using Kerberos/NTLM authentication if the account is disabled in Active Directory. Клиент системы комнат Skype должен иметь возможность проверки подлинности в веб-службах Exchange для получения параметров календаря, а также отправлять электронную почту с содержимым доски. 
  
Поэтому если учетная запись отключена, необходимо включить эту учетную запись в Active Directory, выступая следующим образом: 
  
1. В Active Directory запустите следующую команду, чтобы включить вход в учетную запись: 
    
   ```powershell
   Set-ADAccountPassword -Identity LRS01
   ```

   При запуске этой команды вам будет предложено ввести текущий пароль, а затем повторно ввести пароль дважды для подтверждения.
    
2. После этого запустите следующую команду, чтобы включить учетную запись: 
    
   ```powershell
   Enable-ADAccount -Identity LRS01
   ```

## <a name="enabling-skype-room-system-accounts-for-skype-for-business"></a>Включение учетных записей системы комнат Skype для Skype для бизнеса

В этом разделе представлен обзор действий, необходимых для того, чтобы включить Skype для бизнеса для учетной записи конференц-зала, которая будет настроена в системе комнат Skype. 
  
After you create a resource mailbox account for the conferencing rooms, use Skype for Business Server Management Shell to enable Skype Room System accounts for Skype for Business services.
  
> [!NOTE]
> В следующей процедуре предполагается, что вы включили учетную запись системы комнат Skype в Active Directory. 
  
1. Чтобы включить учетную запись системы комнат Skype в пуле Skype для бизнеса Server, запустите следующую команду:
    
   ```powershell
   Enable-CsMeetingRoom -SipAddress "sip:LRS01@contoso.com" -domaincontroller DC-ND-001.contoso.com -RegistrarPool LYNCPool15.contoso.com -Identity LRS01
   ```

2. Необязательный. Разрешить этой учетной записи делать и принимать телефонные вызовы PSTN, включив учетную запись для Корпоративная голосовая связь. Корпоративная голосовая связь не требуется для системы комнат Skype, но если не включить ее для Корпоративная голосовая связь, клиент системы комнат Skype не сможет предоставить функции набора номера ЗВОНКОВ:
    
   ```powershell
   Set-CsMeetingRoom LRS01 -domaincontroller DC-ND-001.contoso.com -LineURItel: +14255550555;ext=50555"
   Set-CsMeetingRoom -domaincontroller DC-ND-001.contoso.com -Identity LRS01 -EnterpriseVoiceEnabled $true
   ```

> [!NOTE]
> If you enable Корпоративная голосовая связь for the Skype Room System conference room account, make sure to configure a restricted Voice Policy suitable for your organization. Если комната для собраний Skype для бизнеса является общедоступным ресурсом, ее может использовать любой человек, чтобы присоединиться к собранию по расписанию или по расписанию. После присоединения к собранию человек может звонить на любой номер. В Skype для бизнеса Server функция набора номера из конференций использует политику голосовой связи пользователя, в данном случае это учетная запись системы комнат Skype, используемая для присоединиться к собранию. В более ранних версиях Lync Server используется политика голосовой почты организатора. Таким образом, если пользователь более ранней версии Lync Server запланировать комнату для собраний и пригласить учетную запись системы комнат Skype, любой пользователь может присоединиться к собранию с помощью комнаты для собраний Skype для бизнеса и набрать любой номер телефона для национальных, региональных или международных звонков, если организатору разрешено набирать эти номера. 
  

