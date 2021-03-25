---
title: Развертывание единого леса в системе номеров Skype
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
description: Ознакомьтесь с этой темой, чтобы узнать, как развернуть систему Skype Room System в одной локальной среде леса.
ms.openlocfilehash: df213b24ef3400aa5551a090d2dd218d05794988
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120328"
---
# <a name="skype-room-system-single-forest-on-premises-deployments"></a>Развертывание единого леса в системе номеров Skype
 
Ознакомьтесь с этой темой, чтобы узнать, как развернуть систему Skype Room System в одной локальной среде леса.
  
В этом разделе представлен обзор действий по обеспечению учетной записи Skype Room System на Exchange Server и Skype для бизнеса Server, размещенной в одном локальном развертывании леса.
  
## <a name="single-forest-on-premises-deployments"></a>Локальные развертывания с одним лесом

Если у вас уже есть учетная запись почтового ящика ресурса для комнаты для конференций, ее можно использовать. В противном случае потребуется создать новый. Для создания новой учетной записи почтового ящика ресурсов можно использовать как оболочку управления Exchange (PowerShell), так и консоль управления Exchange. Рекомендуется использовать новый (удалить старый почтовый ящик и повторно создать) почтовый ящик ресурса для Системы номеров Skype. Убедитесь, что перед удалением необходимо создать базу данных почтовых ящиков, а затем экспортировать их обратно в вновь созданный почтовый ящик с помощью клиента Outlook (дополнительные сведения см. в экспорте или обратном сборе сообщений, календаря, задач и контактов). Чтобы восстановить собрания, потерянные путем удаления почтового ящика, см. в руб. Подключение или восстановление [удаленного почтового ящика.](/exchange/connect-or-restore-a-deleted-mailbox-exchange-2013-help) 
  
Чтобы использовать существующую учетную запись почтового ящика ресурсов (например, LRS-01), выполните следующие действия:
  
1. Запустите следующую команду PowerShell управления Exchange:
    
   ```powershell
   Set-Mailbox -Name 'LRS-01' -Alias 'LRS01' -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

2. Если вы планируете создать новый почтовый ящик, то для одной лесной локальной организации Exchange запустите следующую команду:
    
   ```powershell
   New-Mailbox -UserPrincipalName LRS01@contoso.com -Alias LRS01 -Name "LRS-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

   В этом примере создается учетная запись пользователя с включенной поддержкой в Active Directory и почтовый ящик комнаты для конференц-зала в локальной организации Exchange. Параметр RoomMailboxPassword указывает пароль для учетной записи пользователя.
    
3. Настройте учетную запись для автоматического разрешения конфликтов, принимая собрания или отклоняет их. Учетные записи конференц-залов в Exchange, оборудованные системой Skype, могут управляться отдельными лицами, но обратите внимание, что до тех пор, пока человек не примет собрание, оно не будет отображаться в календаре домашнего экрана системы номеров Skype.
    
   ```powershell
   Set-CalendarProcessing -Identity LRS01 -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteSubject $false -RemovePrivateProperty $false
   ```

   Полный набор доступных команд см. в пункте Set-CalendarProcessing.
    
   Чтобы напомнить организаторам собрания о том, как сделать собрание Skype для бизнеса в Outlook, запустите следующую команду, чтобы настроить MailTip для новой учетной записи: 
    
   ```powershell
   Set-Mailbox -Identity LRS01@contoso.com -MailTip "This room is equipped with Lync Meeting Room (LRS), please make it a Lync Meeting to take advantage of the enhanced meeting experience from LRS"
   ```
4. Чтобы настроить локализованные строки, используйте следующие команды. Если требуется ваша организация, вы также можете добавить настраиваемые переводы: 
   ```powershell
   $Temp = Get-Mailbox  LRS01@ contoso.com 
   $Temp.MailTipTranslations += "ES: Spanish translation of the message"
   Set-Mailbox -Identity LRS01@contoso.com -MailTipTranslations $Temp.MailTipTranslations
   ```

5. Необязательный. Настройте текст приемки собраний, который предоставляет пользователям сведения о Комнате собраний Skype для бизнеса и о том, что следует ожидать при расписании собраний и вступать в них. 
    
   ```powershell
   Set-CalendarProcessing -Identity LRS01 -AddAdditionalResponse $TRUE -AdditionalResponse "This is the Additional Response Text"
   ```

## <a name="check-resource-mailbox-account-in-active-directory"></a>Проверка учетной записи почтовых ящиков ресурса в Active Directory

Учетная запись почтового ящика конференц-зала, созданная Exchange на шаге 1 выше, может быть отключенным объектом пользователя в Active Directory. Система номеров Skype не может войти или проверить подлинность с помощью проверки подлинности Kerberos/NTLM, если учетная запись отключена в Active Directory. Клиент системы номеров Skype должен иметь возможность проверки подлинности в веб-службах Exchange для получения параметров календаря, а также отправлять сообщения электронной почты с содержимым доски. 
  
Поэтому, если учетная запись отключена, необходимо включить эту учетную запись в Active Directory, делая следующее: 
  
1. В Active Directory запустите следующую команду, чтобы включить журнал учетной записи: 
    
   ```powershell
   Set-ADAccountPassword -Identity LRS01
   ```

   Запуск этой команды позволит ввести текущий пароль, а затем дважды ввести пароль для подтверждения.
    
2. После зачета пароля запустите следующую команду, чтобы включить учетную запись: 
    
   ```powershell
   Enable-ADAccount -Identity LRS01
   ```

## <a name="enabling-skype-room-system-accounts-for-skype-for-business"></a>Включение учетных записей skype Room System для Skype для бизнеса

В этом разделе представлен обзор действий, необходимых для того, чтобы включить Skype для бизнеса для вашей учетной записи конференц-зала, которая будет настроена в skype Room System. 
  
После создания учетной записи почтового ящика ресурсов для помещений для конференций используйте Skype для управления бизнес-серверами, чтобы включить учетные записи skype Room System для служб Skype для бизнеса.
  
> [!NOTE]
> В следующей процедуре предполагается, что вы включили учетную запись Skype Room System в Active Directory. 
  
1. Запустите следующую команду, чтобы включить учетную запись Skype Room System в пуле Skype для бизнеса Server:
    
   ```powershell
   Enable-CsMeetingRoom -SipAddress "sip:LRS01@contoso.com" -domaincontroller DC-ND-001.contoso.com -RegistrarPool LYNCPool15.contoso.com -Identity LRS01
   ```

2. Необязательный. Разрешить этой учетной записи делать и принимать телефонные вызовы PSTN, включив учетную запись для Корпоративная голосовая связь. Корпоративная голосовая связь не требуется для системы номеров Skype, но если вы не включаете ее для Корпоративная голосовая связь, клиент skype Room System не сможет предоставить функции набора номера PSTN:
    
   ```powershell
   Set-CsMeetingRoom LRS01 -domaincontroller DC-ND-001.contoso.com -LineURItel: +14255550555;ext=50555"
   Set-CsMeetingRoom -domaincontroller DC-ND-001.contoso.com -Identity LRS01 -EnterpriseVoiceEnabled $true
   ```

> [!NOTE]
> Если вы Корпоративная голосовая связь для учетной записи конференц-зала Skype Room System, настройте ограниченную голосовую политику, которая подходит для вашей организации. Если комната собраний Skype для бизнеса является общедоступным ресурсом, любой желающий может присоединиться к собранию, запланированному или разово. После присоединения к собранию человек может набрать любой номер. В Skype для бизнеса Server функция конференц-связи использует голосовую политику пользователя, в данном случае учетную запись Skype Room System, используемую для данной встречи. В более ранних версиях Lync Server используется голосовая политика организатора. Поэтому если пользователь более ранней версии Lync Server настроит зал собраний и пригласит учетную запись skype Room System, любой пользователь может присоединиться к собранию в Комнате собраний Skype для бизнеса и набрать любой национальный или региональный или международный телефонный номер, если организатору разрешено набирать эти номера. 
