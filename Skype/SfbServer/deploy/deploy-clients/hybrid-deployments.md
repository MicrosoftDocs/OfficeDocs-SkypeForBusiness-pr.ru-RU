---
title: Гибридные развертывания системы комнат Skype
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
ms.assetid: eba70d88-13b3-4598-95d5-8a343c9e7d26
description: В этом разделе рассказывается, как развертывать систему комнат Skype в гибридной среде.
ms.openlocfilehash: 5773fac7aa87a6ee8c7c64c68124e48f4be67b66
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/13/2020
ms.locfileid: "44219679"
---
# <a name="skype-room-system-hybrid-deployments"></a>Гибридные развертывания системы комнат Skype

В этом разделе рассказывается, как развертывать систему комнат Skype в гибридной среде.
  
## <a name="hybrid-deployments"></a>Гибридные развертывания

Выполните указанные ниже действия, если ваша топология использует Skype для бизнеса Server и Exchange Online, и вы хотите разместить почтовый ящик ресурса системы комнат Skype в Exchange Online. В этом разделе также описывается гибридный сценарий, в котором вы развернули как Exchange Online, так и Exchange Server.
  
Для иллюстрации целей мы используем LyncSample.com для локального домена и LyncSample.ccstp.net для домена в сети.
  
1. Создайте почтовый ящик ресурса в центре администрирования Exchange (LyncSample.ccsctp.net), подключившись к командной консоли Exchange Online, как описано в статье Подготовка Exchange Online.
    
   ```powershell
   New-Mailbox -room -name "LRS Test 5" -RoomMailboxPassword (ConvertTo-SecureString <password> -AsPlainText -Force) -EnableRoomMailboxAccount $true 
   ```

    Вы можете проверить подключение OWA, используя lrstest5@LyncSample.ccsctp.net для входа в систему.
    
2. В центре администрирования Exchange для Microsoft 365 или Office 365 добавьте адрес электронной почты lrstest5@LyncSample.com (локальный домен) и задайте его в качестве адреса для ответа.
    
3. Создайте локальный пользователь lrstest5@LyncSample.com Active Directory, задайте для него адрес электронной почты lrstest5@LyncSample.com и задайте для целевого адреса значение lrstest5@LyncSample.com.
    
4. Активируйте синхронизацию службы каталогов и после завершения синхронизации убедитесь, что пользователи объединяются в AAD и что не удается изменить свойства в ресурсах получателей в центре администрирования Microsoft 365 или Office 365 Exchange.
    
5. Проверьте возможность подключения OWA с помощью lrstest5@LyncSample.com. (Ранее вы проверили возможности подключения к OWA с помощью домена Online.)
    
    После создания почтового ящика можно использовать командлет Set-CalendarProcessing в командной консоли Exchange Online для настройки почтового ящика. Для получения дополнительных сведений обратитесь к разделу 3 – 6 в разделе локальное развертывание в пределах одного леса.
    
   > [!NOTE]
   > Если вы используете гибридную среду с Exchange Server и Exchange Online, перейдите в командную консоль Exchange и включите параметр-RemoteMailbox lrstest5@LyncSample.com-RemoteRoutingAddress lrstest5@LyncSample.mail.ccsctp.net-Room. Затем активируйте синхронизацию службы каталогов. 
  
    Если вы хотите разместить почтовый ящик системы комнат Skype в Exchange Online, эти действия для командной консоли Exchange не требуются, и вы можете перейти к шагу 6.
    
6. Включите учетную запись системы комнат Skype для Skype для бизнеса, выполнив следующий командлет в командной консоли Skype для бизнеса:
    
   ```powershell
   Enable-CsMeetingRoom -SipAddress 'sip: lrstest5@LyncSample.com' -RegistrarPool pool1.child.corp.LyncSample.com -Identity lrstest5@LyncSample.com
   Set-CsMeetingRoom -Identity lrstest5@LyncSample.com -EnterpriseVoiceEnabled $true
   ```

> [!NOTE]
> Если вы используете Skype для бизнеса Online вместо Skype для бизнеса Server в указанном выше сценарии, то после подготовки почтового ящика ресурсов Exchange предоставьте учетную запись Skype для бизнеса, как описано в статье Подготовка Skype для бизнеса Online. 
  

