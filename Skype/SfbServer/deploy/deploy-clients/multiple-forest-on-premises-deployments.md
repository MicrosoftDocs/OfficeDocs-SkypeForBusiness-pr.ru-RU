---
title: Локальное развертывание системы комнат Skype с несколькими лесами
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
ms.assetid: 6793fca0-3970-44e4-8703-1925428c1967
description: В этом разделе вы узнаете, как развернуть систему комнат Skype в локальной среде с несколькими лесами.
ms.openlocfilehash: 168244033a681b9aa9dc6e4c9697b7e3c7e89127
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805749"
---
# <a name="skype-room-system-multiple-forest-on-premises-deployments"></a>Локальное развертывание системы комнат Skype с несколькими лесами
 
В этом разделе вы узнаете, как развернуть систему комнат Skype в локальной среде с несколькими лесами.
  
> [!NOTE]
> Для развертывания в нескольких лесах системе комнат Skype требуется Exchange Server 2013 CU6, выпущенный 26 августа 2014 г. Избегайте повторного использования существующего почтового ящика для системы комнат Skype. Используйте новый (удалить старый почтовый ящик и повторно создать) почтовый ящик ресурса для системы комнат Skype. Чтобы восстановить собрания, потерянные при удалении почтового ящика, см. в подключении или [восстановлении удаленного почтового ящика.](https://technet.microsoft.com/library/jj863438%28v=exchg.150%29.aspx) 
  
После создания почтового ящика можно использовать Set-CalendarProcessing для настройки почтового ящика. Дополнительные сведения можно найти в шагах с 3 по 6 в рамках локального развертывания с одним лесом. After creating an Exchange Resource mailbox for Skype Room System, enable the account for Skype for Business by following the steps in Enabling Skype Room System Accounts for Skype for Business under Single forest on-premises deployments.
  
## <a name="option-1-create-a-new-resource-mailbox"></a>Вариант 1. Создание почтового ящика ресурса

Развертывание системы комнат Skype в среде с несколькими лесами
  
1. Создание связанного пользователя (LinkedRoomTest) в Active Directory (лес проверки подлинности).
    
2. В командной Exchange Server командной Exchange Server следующие команды:
    
   ```powershell
   $cred = Get-Credential AuthForest\LinkedRoomTest
   new-mailbox -Alias LinkedRoomTest -LinkedMasterAccount AuthForest\LinkedRoomTest -LinkedDomainController AuthForest-4939.AuthForest.extest.contoso.com -UserPrincipalName LinkedRoomTest@ExchangeForest.contoso.comm -Name LinkedRoomTest -LinkedCredential $cred -LinkedRoom
   ```

## <a name="option-2-change-an-existing-room-mailbox-to-skype-room-system-linked-resource-mailbox"></a>Вариант 2. Изменение существующего почтового ящика помещения на почтовый ящик системы комнат Skype (связанный)

```powershell
$cred=Get-Credential AuthForest\LinkedRoomTest1
Set-mailbox -Alias LinkedRoomTest1 -LinkedMasterAccount AuthForest\LinkedRoomTest1 -LinkedDomainController AuthForest-4939.AuthForest.extest.contoso.com -Name LinkedRoomTest1 -LinkedCredential $cred -Identity LinkedRoomTest1
```


