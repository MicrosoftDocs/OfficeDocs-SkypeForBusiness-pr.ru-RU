---
title: Stop-CcLogging
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: fee9eda7-ad15-40d2-b9fe-21c5462d3309
description: Командлет Stop-CcLogging прекращает ведение журналов входящих и исходящих звонков для устройства Skype для бизнеса Cloud Connector Edition.
ms.openlocfilehash: 8a012e9b1a94c3698cc61da4326eb0ccbb27bca2
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824163"
---
# <a name="stop-cclogging"></a>Stop-CcLogging
 
Командлет Stop-CcLogging прекращает ведение журналов входящих и исходящих звонков для устройства Skype для бизнеса Cloud Connector Edition.
  
```powershell
Stop-CcLogging [-RemoveCache]
```

## <a name="examples"></a>Примеры
<a name="Examples"> </a>

### <a name="example-1"></a>Пример 1

В следующем примере прекращается ведение журналов входящих и исходящих звонков: 
  
```powershell
Stop-CcLogging
```

### <a name="example-2"></a>Пример 2

В следующем примере прекращается ведение журналов входящих и исходящих звонков, а также удаляются файлы кэша:
  
```powershell
Stop-CcLogging -RemoveCache
```

## <a name="detailed-description"></a>Подробное описание
<a name="DetailedDescription"> </a>

Командлет Stop-CcLogging прекращает ведение журналов входящих и исходящих звонков для устройства. По умолчанию ведение журналов автоматически прекращается через четыре часа.
  
## <a name="parameters"></a>Параметры
<a name="DetailedDescription"> </a>

|**Параметр**|**Обязательный**|**Тип**|**Описание**|
|:-----|:-----|:-----|:-----|
| RemoveCache <br/> | Необязательно <br/> | System.Management.Automation.SwitchParameter <br/> |Удаляет файлы кэша журналов.  <br/> |
   
## <a name="input-types"></a>Типы входных данных
<a name="InputTypes"> </a>

Нет. Командлет Stop-CcLogging не принимает входные данные по конвейеру.
  
## <a name="return-types"></a>Типы возвращаемых данных
<a name="ReturnTypes"> </a>

Нет
  
## <a name="see-also"></a>См. также
<a name="ReturnTypes"> </a>

[Search-CcLog](search-cclog.md)
  
[Start-CcLogging](start-cclogging.md)
  

