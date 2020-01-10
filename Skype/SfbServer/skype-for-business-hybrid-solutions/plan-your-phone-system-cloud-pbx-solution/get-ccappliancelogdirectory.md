---
title: Get-CcApplianceLogDirectory
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8f16d8ea-8161-4b07-9c79-d57e786b3e78
description: Командлет Get-CcApplianceLogDirectory показывает текущий каталог, в котором хранятся журналы устройства Skype для бизнеса Cloud Connector Edition.
ms.openlocfilehash: a8b7e1b13302bec27c2fe784804f8f43fe2e023c
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003399"
---
# <a name="get-ccappliancelogdirectory"></a>Get-CcApplianceLogDirectory
 
Командлет Get-CcApplianceLogDirectory показывает текущий каталог, в котором хранятся журналы устройства Skype для бизнеса Cloud Connector Edition.
  
Этот командлет применяется к версии Skype для бизнеса Cloud Connector Edition 1.4.1, 1.4.2.
  
```powershell
Get-CcApplianceLogDirectory
```

## <a name="parameters"></a>Параметры

Нет
  
## <a name="examples"></a>Примеры
<a name="Examples"> </a>

### <a name="example-1"></a>Пример 1

В следующем примере показана текущая папка, в которой хранятся журналы для текущего устройства в облачном соединителе:
  
```powershell
Get-CcApplianceLogDirectory
```

## <a name="detailed-description"></a>Подробное описание
<a name="DetailedDescription"> </a>

Командлет Get-Ккапплианцелогдиректори показывает текущий каталог, в котором хранятся журналы для устройства облачного соединителя. По умолчанию используется папка\%к:\усерс усерпрофиле%\клаудконнектор\апплианцерут\логс. 
  
Чтобы изменить этот каталог, выполните командлет Set-CcApplianceDirectory. 
  
Примечание. Отдельный командлет, позволяющий сменить только местоположение папки журналов без изменения каталога сайта, не предусмотрен.
  
## <a name="input-types"></a>Типы входных данных
<a name="InputTypes"> </a>

Нет. Командлет Get-CcApplianceLogDirectory не принимает входные данные по конвейеру.
  
## <a name="return-types"></a>Типы возвращаемых данных
<a name="ReturnTypes"> </a>

Эта команда возвращает путь к файлу.
  
## <a name="see-also"></a>См. также
<a name="ReturnTypes"> </a>

[Set-CcApplianceDirectory](set-ccappliancedirectory.md)
  

