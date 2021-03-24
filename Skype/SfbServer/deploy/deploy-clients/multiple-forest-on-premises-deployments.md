---
title: Несколько локального развертывания системы номеров Skype
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
description: Ознакомьтесь с этой темой, чтобы узнать, как развернуть систему skype Room System в нескольких лесных локальной среде.
ms.openlocfilehash: d215ce13059c414d6c6142d7cd1e93ea9011c97b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093533"
---
# <a name="skype-room-system-multiple-forest-on-premises-deployments"></a>Несколько локального развертывания системы номеров Skype
 
Ознакомьтесь с этой темой, чтобы узнать, как развернуть систему skype Room System в нескольких лесных локальной среде.
  
> [!NOTE]
> Чтобы развернуться в нескольких лесах, skype Room System требует Exchange Server 2013 cu6, выпущенный 26 августа 2014 г. Избегайте повторного использования существующего почтового ящика для системы номеров Skype. Используйте новый (удаление старого почтового ящика и повторное создание) почтовый ящик ресурса для системы номеров Skype. Чтобы восстановить собрания, потерянные путем удаления почтового ящика, см. в руб. Подключение или восстановление [удаленного почтового ящика.](/exchange/connect-or-restore-a-deleted-mailbox-exchange-2013-help) 
  
После создания почтового ящика можно использовать Set-CalendarProcessing для настройки почтового ящика. Дополнительные сведения можно найти в статье шаги 3-6 в рамках локального развертывания "Единый лес". Создав почтовый ящик Exchange Resource для системы номеров Skype, включим учетную запись Skype для бизнеса, следуя шагам в статье Включение учетных записей skype Room System для Skype для бизнеса в рамках локального развертывания Единого леса.
  
## <a name="option-1-create-a-new-resource-mailbox"></a>Вариант 1. Создание нового почтового ящика ресурса

Развертывание системы skype Room System в среде с несколькими лесами:
  
1. Создание связанного пользователя (LinkedRoomTest) в Active Directory (Лес проверки подлинности).
    
2. Запустите следующие команды в командной Exchange Server:
    
   ```powershell
   $cred = Get-Credential AuthForest\LinkedRoomTest
   new-mailbox -Alias LinkedRoomTest -LinkedMasterAccount AuthForest\LinkedRoomTest -LinkedDomainController AuthForest-4939.AuthForest.extest.contoso.com -UserPrincipalName LinkedRoomTest@ExchangeForest.contoso.comm -Name LinkedRoomTest -LinkedCredential $cred -LinkedRoom
   ```

## <a name="option-2-change-an-existing-room-mailbox-to-skype-room-system-linked-resource-mailbox"></a>Вариант 2. Изменение существующего почтового ящика комнаты на почтовый ящик ресурса Skype Room System (связанный)

```powershell
$cred=Get-Credential AuthForest\LinkedRoomTest1
Set-mailbox -Alias LinkedRoomTest1 -LinkedMasterAccount AuthForest\LinkedRoomTest1 -LinkedDomainController AuthForest-4939.AuthForest.extest.contoso.com -Name LinkedRoomTest1 -LinkedCredential $cred -Identity LinkedRoomTest1
```