---
title: Развертывание нескольких локальных лесов для системы комнат Skype
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6793fca0-3970-44e4-8703-1925428c1967
description: В этом разделе описывается развертывание системы комнат Skype в локальной среде с несколькими лесами.
ms.openlocfilehash: eb5aa2cbe3bef26602279ffa9d4a5dc38a7e7bc2
ms.sourcegitcommit: a2deac5e8308fc58aba34060006bffad2b19abed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "36775044"
---
# <a name="skype-room-system-multiple-forest-on-premises-deployments"></a>Развертывание нескольких локальных лесов для системы комнат Skype
 
В этом разделе описывается развертывание системы комнат Skype в локальной среде с несколькими лесами.
  
> [!NOTE]
> Для развертывания в нескольких лесах для системы комнат Skype требуется Exchange Server 2013 CU6 выпущены 26 августа 2014 г. Старайтесь не использовать существующий почтовый ящик для системы комнат Skype. Использование нового почтового ящика ресурсов (удаление старого почтового ящика и повторного создания) для системы комнат Skype. Чтобы восстановить собрания из-за удаления почтового ящика, обратитесь к разделу [подключение или восстановление удаленного почтового ящика](https://technet.microsoft.com/library/jj863438%28v=exchg.150%29.aspx). 
  
After creating the mailbox, you can use Set-CalendarProcessing to configure the mailbox. Refer to steps 3 through 6 under Single forest on-premises deployments for more details. После создания почтового ящика ресурсов Exchange для системы комнат Skype включите учетную запись Skype для бизнеса, выполнив действия, описанные в статье Включение системных учетных записей Skype для бизнеса в рамках локальных развертываний с одним лесом.
  
## <a name="option-1-create-a-new-resource-mailbox"></a>Вариант 1. Создание нового почтового ящика ресурсов

Чтобы развернуть систему комнат Skype в среде с несколькими лесами:
  
1. Создайте связанного пользователя (LinkedRoomTest) в Active Directory (Authentication Forest).
    
2. Выполните следующие команды в командной консоли Exchange Server:
    
   ```
   $cred = Get-Credential AuthForest\LinkedRoomTest
   new-mailbox -Alias LinkedRoomTest -LinkedMasterAccount AuthForest\LinkedRoomTest -LinkedDomainController AuthForest-4939.AuthForest.extest.contoso.com -UserPrincipalName LinkedRoomTest@ExchangeForest.contoso.comm -Name LinkedRoomTest -LinkedCredential $cred -LinkedRoom
   ```

## <a name="option-2-change-an-existing-room-mailbox-to-skype-room-system-linked-resource-mailbox"></a>Вариант 2: изменение почтового ящика помещения на почтовый ящик системы комнаты Skype (связанный)

```
$cred=Get-Credential AuthForest\LinkedRoomTest1
Set-mailbox -Alias LinkedRoomTest1 -LinkedMasterAccount AuthForest\LinkedRoomTest1 -LinkedDomainController AuthForest-4939.AuthForest.extest.contoso.com -Name LinkedRoomTest1 -LinkedCredential $cred -Identity LinkedRoomTest1
```


