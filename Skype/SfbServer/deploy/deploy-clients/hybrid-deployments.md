---
title: Гибридное развертывание системы комнат Skype
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: eba70d88-13b3-4598-95d5-8a343c9e7d26
description: В этой статье рассказывается о том, как развертывать системы комнат Skype в гибридной среде.
ms.openlocfilehash: 80e7efaf5fe3705e052d40606ea5944527d43a61
ms.sourcegitcommit: a2deac5e8308fc58aba34060006bffad2b19abed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "36774960"
---
# <a name="skype-room-system-hybrid-deployments"></a>Гибридное развертывание системы комнат Skype

В этой статье рассказывается о том, как развертывать системы комнат Skype в гибридной среде.
  
## <a name="hybrid-deployments"></a>Гибридное развертывание

Если в вашей топологии есть Skype для бизнеса Server и Exchange Online, а вы хотите разместить почтовый ящик системы комнаты комнат Skype на Exchange Online, выполните указанные ниже действия. This section also covers a hybrid scenario where you have both Exchange Online and Exchange Server deployed.
  
Для наглядной цели мы используем LyncSample.com для локального домена и LyncSample.ccstp.net для домена в сети.
  
1. Создайте почтовый ящик ресурсов в центре администрирования Exchange (LyncSample.ccsctp.net), подключившись к командной консоли Exchange Online, как описано в разделе Подготовка Exchange Online.
    
   ```
   New-Mailbox -room -name "LRS Test 5" -RoomMailboxPassword (ConvertTo-SecureString <password> -AsPlainText -Force) -EnableRoomMailboxAccount $true 
   ```

    Вы можете проверить подключение к OWA, используя lrstest5@LyncSample.ccsctp.net для входа в систему.
    
2. В центре администрирования Office 365 добавьте адрес электронной почты lrstest5@LyncSample.com (локальный домен) и укажите адрес ответа.
    
3. Создайте локальную пользовательскую lrstest5@LyncSample.com Active Directory, установите для адреса электронной почты значение lrstest5@LyncSample.com и задайте для целевого адреса значение lrstest5@LyncSample.com.
    
4. Активация службы синхронизации каталогов и после завершения синхронизации убедитесь в том, что пользователи объединяются в AAD и что вы не можете изменять свойства в ресурсах получателя в центре администрирования Office365 Exchange.
    
5. Проверьте подключение к OWA с помощью lrstest5@LyncSample.com. (Ранее вы проверили возможности подключения к OWA с помощью домена в сети.)
    
    После создания почтового ящика для его настройки можно использовать Set-CalendarProcessing в командной консоли Exchange Online. Для получения дополнительных сведений см. шаги 3-6 в разделе "Локальные развертывания с одиночным лесом".
    
   > [!NOTE]
   > Если у вас есть гибридная среда с Exchange Server и Exchange Online, перейдите в командную консоль Exchange и включите-Ремотемаилбокс lrstest5@LyncSample.com-Ремотераутингаддресс lrstest5@LyncSample.mail.ccsctp.net-Room. Запустите синхронизацию с каталогом. 
  
    Если вы хотите разместить почтовый ящик системы комнаты Skype в Exchange Online, эти инструкции командной консоли Exchange не требуются, и вы можете перейти к действию 6.
    
6. Включите учетную запись системы комнаты Skype для Skype для бизнеса, выполнив в командной консоли Skype для бизнеса следующий командлет:
    
   ```
   Enable-CsMeetingRoom -SipAddress 'sip: lrstest5@LyncSample.com' -RegistrarPool pool1.child.corp.LyncSample.com -Identity lrstest5@LyncSample.com
   Set-CsMeetingRoom -Identity lrstest5@LyncSample.com -EnterpriseVoiceEnabled $true
   ```

> [!NOTE]
> Если у вас есть Skype для бизнеса Online вместо Skype для бизнеса Server в описанной выше ситуации, после подготовки почтового ящика Exchange для подготовки к работе необходимо подготовить учетную запись Skype для бизнеса, как описано в разделе Подготовка Skype для бизнеса Online. 
  

