---
title: Гибридное развертывание системы комнат Skype
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/17/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: eba70d88-13b3-4598-95d5-8a343c9e7d26
description: Прочтите этот раздел, чтобы узнать, как развертывание системы Скайп помещения в гибридной среде.
ms.openlocfilehash: e4ef63ec39106a2cb35201d43ca012b4ce173911
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="skype-room-system-hybrid-deployments"></a>Гибридное развертывание системы комнат Skype
 
Прочтите этот раздел, чтобы узнать, как развертывание системы Скайп помещения в гибридной среде.
  
## <a name="hybrid-deployments"></a>Гибридные развертывания

Если топология имеет Скайп для Business Server и Exchange Online и разместить ресурсов Скайп комнаты системных почтовых ящиков на Exchange Online, выполните следующие действия. В этом разделе также описываются гибридного сценария, где у вас есть Exchange Online и развернут сервер Exchange.
  
Для демонстрационных целей мы используем LyncSample.com для локального домена и LyncSample.ccstp.net для Интернет-домена.
  
1. Создание почтового ящика ресурсов в центре администрирования Exchange (LyncSample.ccsctp.net) с помощью подключения к консоли управления Exchange Online, как описано в Exchange Online подготовки.
    
  ```
  New-Mailbox -room -name "LRS Test 5" -RoomMailboxPassword (ConvertTo-SecureString <password> -AsPlainText -Force) -EnableRoomMailboxAccount $true 
  ```

    Вы можете проверить подключения OWA, с использованием lrstest5@LyncSample.ccsctp.net для входа.
    
2. В центре администрирования Office 365 Exchange добавьте lrstest5@LyncSample.com адрес электронной почты (на prem домена) и его настройка в качестве обратный адрес.
    
3. Создание lrstest5@LyncSample.com пользователя Active Directory на prem, равным lrstest5@LyncSample.com адрес электронной почты и задать целевой адрес lrstest5@LyncSample.com.
    
4. Запуск синхронизации службы каталогов и после завершения синхронизации убедитесь, что пользователи объединить в AAD и, что не могут изменить свойства на ресурсах получателя в центре администрирования Exchange Office 365.
    
5. Проверка возможности подключения к OWA с помощью lrstest5@LyncSample.com. (Ранее, проверено ли OWA подключения с использованием online домена.)
    
    После создания почтового ящика для его настройки можно использовать Set-CalendarProcessing в командной консоли Exchange Online. Для получения дополнительных сведений см. шаги 3-6 в разделе "Локальные развертывания с одиночным лесом".
    
    > [!NOTE]
    > Если у вас есть гибридной среде с Exchange Server и Exchange Online, перейдите к командной консоли Exchange и Enable-RemoteMailbox lrstest5@LyncSample.mail.ccsctp.net - RemoteRoutingAddress lrstest5@LyncSample.com-комнаты. Запустите синхронизацию с каталогом. 
  
    Если требуется разместить Скайп комнаты системных почтовых ящиков в Exchange Online, эти действия Командная консоль Exchange не являются обязательными и можно перейти к шагу 6.
    
6. Включение Скайп комнаты системную учетную запись для Скайп для бизнеса, выполнив следующий командлет на Скайп оболочки управления бизнеса:
    
   ```
   Enable-CsMeetingRoom -SipAddress 'sip: lrstest5@LyncSample.com' -RegistrarPool pool1.child.corp.LyncSample.com -Identity lrstest5@LyncSample.com
   Set-CsMeetingRoom -Identity lrstest5@LyncSample.com -EnterpriseVoiceEnabled $true
   ```

> [!NOTE]
> При наличии Скайп для бизнеса в Интернет вместо Скайп для Business Server в вышеприведенном сценарии, затем после заполнения почтовому ящику Exchange временного Скайп для бизнеса учетной записи, как описано в Скайп для бизнеса Online подготовки. 
  

