---
title: Skype одно лесных развертывание системы номеров
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 80da9d71-3dcd-4ca4-8bd1-6d8196823206
description: Ознакомьтесь с этой темой, чтобы узнать, как Skype систему номеров в одной локальной среде леса.
ms.openlocfilehash: 8093304ba538d67f64eb9f824033e9b4560fe976
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/05/2022
ms.locfileid: "62404441"
---
# <a name="skype-room-system-single-forest-on-premises-deployments"></a>Skype одно лесных развертывание системы номеров
 
Ознакомьтесь с этой темой, чтобы узнать, как Skype систему номеров в одной локальной среде леса.
  
В этом разделе представлен обзор действий по обеспечению Skype учетной записи системы Exchange Server и Skype для бизнеса Server, размещенной в одном локальном развертывании леса.
  
## <a name="single-forest-on-premises-deployments"></a>Локальные развертывания с одним лесом

Если у вас уже есть учетная запись почтового ящика ресурса для комнаты для конференций, ее можно использовать. В противном случае потребуется создать новый. Вы можете использовать Exchange (PowerShell) или консоль управления Exchange для создания новой учетной записи почтового ящика ресурса. Рекомендуется использовать новый (удалить старый почтовый ящик и повторно создать) почтовый ящик ресурса для Skype Room System. Убедитесь, что перед удалением необходимо создать базу данных почтовых ящиков, а затем экспортировать их обратно в вновь созданный почтовый ящик с помощью клиента Outlook (дополнительные сведения см. в экспорте или обратном использовании сообщений, календаря, задач и контактов). Чтобы восстановить собрания, потерянные путем удаления почтового ящика, Подключение или восстановить [удаленный почтовый ящик](/exchange/connect-or-restore-a-deleted-mailbox-exchange-2013-help). 
  
Чтобы использовать существующую учетную запись почтового ящика ресурсов (например, LRS-01), выполните следующие действия:
  
1. Запустите следующую команду Exchange PowerShell:
    
   ```powershell
   Set-Mailbox -Name 'LRS-01' -Alias 'LRS01' -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

2. Если вы планируете создать новый почтовый ящик, то для одного лесного локального Exchange организации запустите следующую команду:
    
   ```powershell
   New-Mailbox -UserPrincipalName LRS01@contoso.com -Alias LRS01 -Name "LRS-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

   В этом примере создается учетная запись пользователя с включенной поддержкой в Active Directory и почтовый ящик комнаты для конференц-зала в локальной Exchange организации. Параметр RoomMailboxPassword указывает пароль для учетной записи пользователя.
    
3. Настройте учетную запись для автоматического разрешения конфликтов, принимая собрания или отклоняет их. Skype учетные записи конференц-залов в Exchange могут управляться отдельными лицами, но обратите внимание, что до тех пор, пока человек не примет собрание, оно не будет отображаться в календаре домашнего экрана Skype room System.
    
   ```powershell
   Set-CalendarProcessing -Identity LRS01 -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteSubject $false -RemovePrivateProperty $false
   ```

   Полный набор доступных команд см. в пункте Set-CalendarProcessing.
    
   Чтобы напомнить организаторам собрания о том, что собрание Skype для бизнеса в Outlook, запустите следующую команду, чтобы настроить MailTip для новой учетной записи: 
    
   ```powershell
   Set-Mailbox -Identity LRS01@contoso.com -MailTip "This room is equipped with Lync Meeting Room (LRS), please make it a Lync Meeting to take advantage of the enhanced meeting experience from LRS"
   ```
4. Чтобы настроить локализованные строки, используйте следующие команды. Если требуется ваша организация, вы также можете добавить настраиваемые переводы: 
   ```powershell
   $Temp = Get-Mailbox  LRS01@ contoso.com 
   $Temp.MailTipTranslations += "ES: Spanish translation of the message"
   Set-Mailbox -Identity LRS01@contoso.com -MailTipTranslations $Temp.MailTipTranslations
   ```

5. Необязательный. Настройте текст приемки собрания, который предоставляет пользователям сведения о Skype для бизнеса Конференц-зал, а также о том, что следует ожидать, когда они запланировать собрания и присоединиться к ним. 
    
   ```powershell
   Set-CalendarProcessing -Identity LRS01 -AddAdditionalResponse $TRUE -AdditionalResponse "This is the Additional Response Text"
   ```

## <a name="check-resource-mailbox-account-in-active-directory"></a>Проверка учетной записи почтовых ящиков ресурса в Active Directory

Учетная запись почтового ящика конференц-зала, созданная Exchange на шаге 1 выше, может быть отключенным объектом пользователя в Active Directory. Skype система номеров не может войти или проверить подлинность с помощью проверки подлинности Kerberos/NTLM, если учетная запись отключена в Active Directory. Клиент Skype room System должен иметь возможность проверки подлинности Exchange веб-служб для получения параметров календаря, а также отправлять электронную почту с содержимым доски. 
  
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

## <a name="enabling-skype-room-system-accounts-for-skype-for-business"></a>Включение Skype учетных записей системы номеров для Skype для бизнеса

В этом разделе представлен обзор действий, необходимых для Skype для бизнеса вашей учетной записи конференц-зала, которая будет настроена в Skype room System. 
  
После создания учетной записи почтового ящика ресурса для комнаты для Skype для бизнеса Server управления используйте Skype учетные записи системы номеров для Skype для бизнеса служб.
  
> [!NOTE]
> Следующая процедура предполагает, что вы включили учетную запись Skype в Active Directory. 
  
1. Запустите следующую команду, чтобы включить Skype учетную запись системы номеров в Skype для бизнеса Server пуле:
    
   ```powershell
   Enable-CsMeetingRoom -SipAddress "sip:LRS01@contoso.com" -domaincontroller DC-ND-001.contoso.com -RegistrarPool LYNCPool15.contoso.com -Identity LRS01
   ```

2. Необязательный. Разрешить этой учетной записи делать и принимать телефонные звонки PSTN, включив учетную запись для Корпоративная голосовая связь. Корпоративная голосовая связь не требуется для Skype системы номеров, но если вы не включаете ее для Корпоративная голосовая связь, клиент Skype Room System не сможет предоставить функции набора номера PSTN:
    
   ```powershell
   Set-CsMeetingRoom LRS01 -domaincontroller DC-ND-001.contoso.com -LineURItel: +14255550555;ext=50555"
   Set-CsMeetingRoom -domaincontroller DC-ND-001.contoso.com -Identity LRS01 -EnterpriseVoiceEnabled $true
   ```

> [!NOTE]
> Если вы Корпоративная голосовая связь для учетной записи конференц-Skype системы залов, не забудьте настроить ограниченную голосовую политику, которая подходит для вашей организации. Если Skype для бизнеса Конференц-зал является общедоступным ресурсом, любой желающий может использовать его для пользования собранием, запланированным или внепланово. После присоединения к собранию человек может набрать любой номер. В Skype для бизнеса Server, функция dial-out из конференций использует голосовую политику пользователя, в этом случае Skype учетной записи системы номеров, используемой для присоединяться к собранию. В более ранних версиях Lync Server используется голосовая политика организатора. Поэтому если пользователь более ранней версии Lync Server настроит зал собраний и пригласит учетную запись комнаты Skype Room System, любой пользователь может использовать Skype для бизнеса Конференц-зал, чтобы присоединиться к собранию и набрать любой национальный или региональный или международный телефонный номер, если организатору разрешено набирать эти номера. 
