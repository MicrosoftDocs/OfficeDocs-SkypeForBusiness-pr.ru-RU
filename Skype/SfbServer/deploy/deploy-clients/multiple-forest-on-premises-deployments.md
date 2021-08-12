---
title: Skype Развертывание нескольких лесных локальной системы Room System
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
description: Ознакомьтесь с этой темой, чтобы узнать, как Skype систему номеров в локальной среде с несколькими лесами.
ms.openlocfilehash: dc1d7fa3a3ca7cbcf62f7c038fb8fd6b4fcedc84319452ec8eaf02781f311bf3
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2021
ms.locfileid: "54310068"
---
# <a name="skype-room-system-multiple-forest-on-premises-deployments"></a>Skype Развертывание нескольких лесных локальной системы Room System
 
Ознакомьтесь с этой темой, чтобы узнать, как Skype систему номеров в локальной среде с несколькими лесами.
  
> [!NOTE]
> Чтобы развернуться в нескольких лесах, Skype room System Exchange Server 2013 cu6 выпущен 26 августа 2014 г. Избегайте повторного использования существующего почтового ящика для Skype системы номеров. Используйте новый (удалить старый почтовый ящик и повторно создать) почтовый ящик ресурса для Skype Room System. Чтобы восстановить собрания, потерянные путем удаления почтового ящика, Подключение или восстановить [удаленный почтовый ящик.](/exchange/connect-or-restore-a-deleted-mailbox-exchange-2013-help) 
  
После создания почтового ящика можно использовать Set-CalendarProcessing для настройки почтового ящика. Дополнительные сведения можно найти в статье шаги 3-6 в рамках локального развертывания "Единый лес". Создав почтовый ящик Exchange Resource для Skype Room System, включим учетную запись Skype для бизнеса, следуя шагам в статье Включение учетных записей системы Skype номеров для Skype для бизнеса в рамках локального развертывания Единого леса.
  
## <a name="option-1-create-a-new-resource-mailbox"></a>Вариант 1. Создание нового почтового ящика ресурса

Развертывание Skype в многолесной среде:
  
1. Создание связанного пользователя (LinkedRoomTest) в Active Directory (Лес проверки подлинности).
    
2. Запустите следующие команды в командной Exchange Server управления:
    
   ```powershell
   $cred = Get-Credential AuthForest\LinkedRoomTest
   new-mailbox -Alias LinkedRoomTest -LinkedMasterAccount AuthForest\LinkedRoomTest -LinkedDomainController AuthForest-4939.AuthForest.extest.contoso.com -UserPrincipalName LinkedRoomTest@ExchangeForest.contoso.comm -Name LinkedRoomTest -LinkedCredential $cred -LinkedRoom
   ```

## <a name="option-2-change-an-existing-room-mailbox-to-skype-room-system-linked-resource-mailbox"></a>Вариант 2. Изменение существующего почтового ящика комнаты на Skype (связанный) почтовый ящик ресурса системы номеров

```powershell
$cred=Get-Credential AuthForest\LinkedRoomTest1
Set-mailbox -Alias LinkedRoomTest1 -LinkedMasterAccount AuthForest\LinkedRoomTest1 -LinkedDomainController AuthForest-4939.AuthForest.extest.contoso.com -Name LinkedRoomTest1 -LinkedCredential $cred -Identity LinkedRoomTest1
```