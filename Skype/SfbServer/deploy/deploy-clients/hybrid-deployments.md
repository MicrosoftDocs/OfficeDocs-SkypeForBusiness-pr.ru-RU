---
title: Skype Гибридное развертывание room System
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: eba70d88-13b3-4598-95d5-8a343c9e7d26
description: Ознакомьтесь с этой темой, чтобы узнать, как Skype систему номеров в гибридной среде.
ms.openlocfilehash: caebf77f0ef5abb2b56c64446ad04a052d8f98f9
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/08/2021
ms.locfileid: "60841951"
---
# <a name="skype-room-system-hybrid-deployments"></a>Skype Гибридное развертывание room System

Ознакомьтесь с этой темой, чтобы узнать, как Skype систему номеров в гибридной среде.
  
## <a name="hybrid-deployments"></a>Гибридные развертывания

Следуйте этим шагам, если топология имеет Skype для бизнеса Server и Exchange Online, и вы хотите Skype почтовый ящик ресурса room System на Exchange Online. В этом разделе также описывается гибридный сценарий, в котором Exchange Online и Exchange Server развертывания.
  
Для иллюстративных целей мы LyncSample.com для локального домена и LyncSample.ccstp.net для интернет-домена.
  
1. Создайте почтовый ящик ресурса Exchange центре администрирования (LyncSample.ccsctp.net) путем подключения к оболочке управления Exchange Online, как описано в Exchange Online Подготовка.
    
   ```powershell
   New-Mailbox -room -name "LRS Test 5" -RoomMailboxPassword (ConvertTo-SecureString <password> -AsPlainText -Force) -EnableRoomMailboxAccount $true 
   ```

    Вы можете проверить подключение OWA с помощью lrstest5@LyncSample.ccsctp.net для входа.
    
2. В центре Microsoft 365 или Office 365 Exchange добавьте адрес электронной почты lrstest5@LyncSample.com (домен на преме) и установите его в качестве ответа.
    
3. Создайте на предварительном основе lrstest5@LyncSample.com Active Directory, установите адрес электронной почты lrstest5@LyncSample.com и установите целевой lrstest5@LyncSample.com.
    
4. Синхронизация каталогов и после завершения синхронизации убедитесь, что пользователи сливаются в AAD и что вы не можете изменить свойства ресурсов получателя в центре администрирования Microsoft 365 или Office 365 Exchange.
    
5. Проверка подключения OWA с помощью lrstest5@LyncSample.com. (Ранее вы проверили подключение OWA с помощью интернет-домена.)
    
    После создания почтового ящика можно использовать Set-CalendarProcessing на Exchange Online для настройки почтового ящика. Дополнительные сведения можно найти в статье Этапы 3-6 в развертывании единого леса на предварительном этапе.
    
   > [!NOTE]
   > Если у вас гибридная среда с Exchange Server и Exchange Online, перейдите в Exchange Management Shell и Enable-RemoteMailbox lrstest5@LyncSample.com-RemoteRoutingAddress lrstest5@LyncSample.mail.ccsctp.net-Room. Затем срабатывает синхронизация каталогов. 
  
    Если вы хотите уместить почтовый ящик Skype системы номеров в Exchange Online, эти действия Exchange управления не требуются, и вы можете перейти к шагу 6.
    
6. Варим Skype учетную запись системы номеров для Skype для бизнеса, заняв следующие команды в Skype для бизнеса Management Shell:
    
   ```powershell
   Enable-CsMeetingRoom -SipAddress 'sip: lrstest5@LyncSample.com' -RegistrarPool pool1.child.corp.LyncSample.com -Identity lrstest5@LyncSample.com
   Set-CsMeetingRoom -Identity lrstest5@LyncSample.com -EnterpriseVoiceEnabled $true
   ```

> [!NOTE]
> Если вы Skype для бизнеса Online вместо Skype для бизнеса Server в описанной выше ситуации, то после Exchange почтового ящика ресурса Skype для бизнеса учетную запись, описанную в Skype для бизнеса Online Подготовка. 
  

