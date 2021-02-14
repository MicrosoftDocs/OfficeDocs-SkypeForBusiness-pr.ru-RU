---
title: Гибридные развертывания системы комнат Skype
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
ms.assetid: eba70d88-13b3-4598-95d5-8a343c9e7d26
description: В этом разделе вы узнаете, как развернуть систему комнат Skype в гибридной среде.
ms.openlocfilehash: 47be9204155a1ff6cf6e8d9dfa67723a370fec26
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805899"
---
# <a name="skype-room-system-hybrid-deployments"></a>Гибридные развертывания системы комнат Skype

В этом разделе вы узнаете, как развернуть систему комнат Skype в гибридной среде.
  
## <a name="hybrid-deployments"></a>Гибридные развертывания

Выполните следующие действия, если в вашей топологии есть Skype для бизнеса Server и Exchange Online, и вы хотите, чтобы почтовый ящик ресурса системы комнат Skype был в Exchange Online. В этом разделе также описывается гибридный сценарий, в котором развернуты exchange Online Exchange Server exchange Online.
  
Для наглядности мы используем LyncSample.com для локального домена и LyncSample.ccstp.net для интернет-домена.
  
1. Создайте почтовый ящик ресурса в Центре администрирования Exchange (LyncSample.ccsctp.net), подключившись к оболочке управления Exchange Online, как описано в exchange Online Provisioning.
    
   ```powershell
   New-Mailbox -room -name "LRS Test 5" -RoomMailboxPassword (ConvertTo-SecureString <password> -AsPlainText -Force) -EnableRoomMailboxAccount $true 
   ```

    Вы можете проверить подключение OWA с помощью lrstest5@LyncSample.ccsctp.net входа.
    
2. В Центре администрирования Microsoft 365 или Office 365 Exchange добавьте адрес электронной почты lrstest5@LyncSample.com (наемный домен) и установите его в качестве адреса ответа.
    
3. Создайте учетную lrstest5@LyncSample.com Active Directory, установите для адреса электронной почты lrstest5@LyncSample.com и за установите для целевого адреса lrstest5@LyncSample.com.
    
4. Активировать синхронизацию службы каталогов и после завершения синхронизации убедитесь, что пользователи объединены в AAD и что вы не можете изменить свойства в ресурсах получателей в Центре администрирования Microsoft 365 или Office 365 Exchange.
    
5. Проверьте подключение OWA с помощью lrstest5@LyncSample.com. (Ранее вы проверяли подключение OWA с помощью интернет-домена.)
    
    После создания почтового ящика можно использовать Set-CalendarProcessing в exchange Online Management Shell для настройки почтового ящика. Дополнительные сведения можно найти в действиях с 3 по 6 в статье "Развертывание с одним лесом на предварительном этапе".
    
   > [!NOTE]
   > Если у вас гибридная среда с Exchange Server и Exchange Online, перейдите в exchange Management Shell и Enable-RemoteMailbox lrstest5@LyncSample.com -RemoteRoutingAddress lrstest5@LyncSample.mail.ccsctp.net -Room. Затем активирует синхронизацию каталогов. 
  
    Если вы хотите, чтобы почтовый ящик системы комнат Skype был в Exchange Online, эти действия в exchange Management Shell не требуются, и вы можете перейти к шагу 6.
    
6. В включить учетную запись системы комнат Skype для Skype для бизнеса с помощью следующего команды в оболочке управления Skype для бизнеса:
    
   ```powershell
   Enable-CsMeetingRoom -SipAddress 'sip: lrstest5@LyncSample.com' -RegistrarPool pool1.child.corp.LyncSample.com -Identity lrstest5@LyncSample.com
   Set-CsMeetingRoom -Identity lrstest5@LyncSample.com -EnterpriseVoiceEnabled $true
   ```

> [!NOTE]
> Если в вышеуказанном сценарии вместо Skype для бизнеса Server имеется Skype для бизнеса Online, то после предоставления почтового ящика ресурса Exchange подымену учетной записи Skype для бизнеса, как описано в подукладке Skype для бизнеса Online. 
  

