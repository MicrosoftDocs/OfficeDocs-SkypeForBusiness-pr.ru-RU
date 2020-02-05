---
title: Развертывание одного локального леса для системы комнат Skype
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 80da9d71-3dcd-4ca4-8bd1-6d8196823206
description: В этом разделе описывается развертывание Системы комнат Skype в локальной среде с одиночным лесом.
ms.openlocfilehash: 47cbd43709dda35d728bf8324362bec075dc74b1
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768702"
---
# <a name="skype-room-system-single-forest-on-premises-deployments"></a>Развертывание одного локального леса для системы комнат Skype
 
В этом разделе описывается развертывание Системы комнат Skype в локальной среде с одиночным лесом.
  
В этом разделе приводятся общие сведения о том, как подготовить учетную запись системы комнаты Skype на сервере Exchange Server и в Skype для бизнеса Server, размещенных в одном лесе в локальной среде.
  
## <a name="single-forest-on-premises-deployments"></a>Локальные развертывания с одиночным лесом

Вы можете использовать учетную запись почтового ящика ресурса для конференц-зала, если она у вас есть. В противном случае потребуется создать новую учетную запись. Для создания новой учетной записи почтового ящика ресурса можно использовать либо командную консоль Exchange (PowerShell), либо консоль управления Exchange. Мы рекомендуем использовать новый почтовый ящик ресурсов (удаление старого почтового ящика и повторного создания) для системы комнат Skype. Обязательно выполните резервное копирование данные почтового ящика перед удалением и затем экспортируйте их обратно в повторно созданный почтовый ящик, используя клиент Outlook (дополнительные сведения см. в разделе "Экспорт или резервное копирование сообщений, календаря, задач и контактов"). Чтобы восстановить собрания из-за удаления почтового ящика, обратитесь к разделу [подключение или восстановление удаленного почтового ящика](https://technet.microsoft.com/library/jj863438%28v=exchg.150%29.aspx). 
  
Для использования существующей учетной записи почтового ящика ресурса (например, LRS-01) выполните следующие действия.
  
1. Выполните следующую команду в командной консоли Exchange PowerShell:
    
   ```powershell
   Set-Mailbox -Name 'LRS-01' -Alias 'LRS01' -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

2. Если вы планируете создать новый почтовый ящик, выполните следующую команду для локальной организации Exchange с одиночным лесом:
    
   ```powershell
   New-Mailbox -UserPrincipalName LRS01@contoso.com -Alias LRS01 -Name "LRS-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

   В приведенном выше примере создается активная учетная запись пользователя в Active Directory и почтовый ящик комнаты для конференц-зала в локальной организации Exchange. Параметр RoomMailboxPassword определяет пароль для учетной записи пользователя.
    
3. Настройте учетную запись для автоматического разрешения конфликтов путем приема/отклонения собраний. Система комнат Skype — это возможность управлять учетными записями комнаты на Конференции в Exchange, но обратите внимание на то, что до тех пор, пока они не будут принимать приглашение на собрание, оно не будет отображаться в календаре на начальном экране системы помещения Skype.
    
   ```powershell
   Set-CalendarProcessing -Identity LRS01 -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteSubject $false -RemovePrivateProperty $false
   ```

   Полный список доступных команд см. в Set-CalendarProcessing.
    
   Чтобы напомнить собранию организаторов на собрание Skype для бизнеса в Outlook, выполните следующую команду, чтобы настроить подсказку для новой учетной записи: 
    
   ```powershell
   Set-Mailbox -Identity LRS01@contoso.com -MailTip "This room is equipped with Lync Meeting Room (LRS), please make it a Lync Meeting to take advantage of the enhanced meeting experience from LRS"
   ```
4. Для настройки локализованных строк используйте следующие команды. Также можно добавить настраиваемые переводы, если это требуется для вашей организации. 
   ```powershell
   $Temp = Get-Mailbox  LRS01@ contoso.com 
   $Temp.MailTipTranslations += "ES: Spanish translation of the message"
   Set-Mailbox -Identity LRS01@contoso.com -MailTipTranslations $Temp.MailTipTranslations
   ```

5. Необязательно: Настройка текста для принятия приглашения на собрание, предоставляющего пользователям сведения о комнате собрания Skype для бизнеса, а также о том, что следует ожидать при планировании и присоединении к собраниям. 
    
   ```powershell
   Set-CalendarProcessing -Identity LRS01 -AddAdditionalResponse $TRUE -AdditionalResponse "This is the Additional Response Text"
   ```

## <a name="check-resource-mailbox-account-in-active-directory"></a>Проверка учетной записи почтового ящика ресурса в Active Directory

The conference room mailbox account created by Exchange in step 1 above might be a disabled user object in Active Directory. Система комнаты Skype не может войти в систему или пройти проверку подлинности с помощью Kerberos/NTLM, если учетная запись отключена в службе каталогов Active Directory. Клиент системы комнаты Skype должен быть в состоянии проверять подлинность с помощью веб-служб Exchange, чтобы получать параметры календаря, а также отправлять сообщения электронной почты с содержимым доски. 
  
Поэтому, если учетная запись отключена, необходимо включить ее в Active Directory, выполнив следующие действия. 
  
1. Для включения входа в учетную запись выполните следующую команду в Active Directory. 
    
   ```powershell
   Set-ADAccountPassword -Identity LRS01
   ```

   При запуске этой команды появится запрос на ввод текущего пароля и на повторный ввод пароля для подтверждения.
    
2. После настройки пароля выполните следующую команду, чтобы активировать учетную запись. 
    
   ```powershell
   Enable-ADAccount -Identity LRS01
   ```

## <a name="enabling-skype-room-system-accounts-for-skype-for-business"></a>Включение системных учетных записей комнаты Skype для Skype для бизнеса

В этом разделе приводятся общие сведения о действиях, необходимых для включения Skype для бизнеса для учетной записи комнаты для конференций, которая будет настроена в системе комнат Skype. 
  
После того как вы создадите учетную запись почтового ящика ресурсов для Конференц-зал, используйте командную консоль управления Skype для бизнеса Server для включения системных учетных записей Skype для бизнеса для служб Skype.
  
> [!NOTE]
> В описанной ниже процедуре предполагается, что вы включили учетную запись системы комнаты Skype в Active Directory. 
  
1. Выполните следующую команду, чтобы включить учетную запись системы комнаты Skype в пуле сервера Skype для бизнеса.
    
   ```powershell
   Enable-CsMeetingRoom -SipAddress "sip:LRS01@contoso.com" -domaincontroller DC-ND-001.contoso.com -RegistrarPool LYNCPool15.contoso.com -Identity LRS01
   ```

2. Optional: Allow this account to make and receive PSTN phone calls by enabling the account for Enterprise Voice. Корпоративная голосовая связь не требуется для системы комнат Skype, но если вы не включите ее для корпоративной голосовой связи, клиент системы комнат Skype не сможет предоставить возможность набора номера для PSTN:
    
   ```powershell
   Set-CsMeetingRoom LRS01 -domaincontroller DC-ND-001.contoso.com -LineURItel: +14255550555;ext=50555"
   Set-CsMeetingRoom -domaincontroller DC-ND-001.contoso.com -Identity LRS01 -EnterpriseVoiceEnabled $true
   ```

> [!NOTE]
> Если вы включите корпоративную голосовую почту для учетной записи комнаты на конференц-зале Skype, убедитесь, что вы настроили политику голосовой связи, подходящую для вашей организации. Если комната для собраний Skype для бизнеса — общедоступный ресурс, любой пользователь может использовать его для присоединения к собранию, как запланированное, так и нерегламентированное. After joining a meeting, the person could dial out to any number. В Skype для бизнеса Server функция исходящих звонков из конференций использует политику голосовой связи пользователя, в этом случае учетная запись комнаты для помещения в Skype, которая использовалась для присоединения к собранию. In earlier versions of Lync Server, the voice policy of the organizer is used. Таким образом, если пользователь более ранней версии Lync Server планирует комнату для собраний и приглашает учетную запись комнаты для помещения в комнату, любой пользователь может использовать для собрания собрание Skype для бизнеса, чтобы присоединиться к собранию и набрать любой национальный, региональный или Международный телефонный номер, если организатор может набрать эти номера. 
  

