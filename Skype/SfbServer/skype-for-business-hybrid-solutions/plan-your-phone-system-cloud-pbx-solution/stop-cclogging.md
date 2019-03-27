---
title: Stop-CcLogging
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fee9eda7-ad15-40d2-b9fe-21c5462d3309
description: Командлет Stop-CcLogging прекращает ведение журналов входящих и исходящих звонков для устройства Skype для бизнеса Cloud Connector Edition.
ms.openlocfilehash: eaccde49421cd22e32b23b89d8b5ea42dd073912
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30879625"
---
# <a name="stop-cclogging"></a>Stop-CcLogging
 
Командлет Stop-CcLogging прекращает ведение журналов входящих и исходящих звонков для устройства Skype для бизнеса Cloud Connector Edition.
  
```
Stop-CcLogging [-RemoveCache]
```

## <a name="examples"></a>Примеры
<a name="Examples"> </a>

### <a name="example-1"></a>Пример 1

В следующем примере прекращается ведение журналов входящих и исходящих звонков: 
  
```
Stop-CcLogging
```

### <a name="example-2"></a>Пример 2

В следующем примере прекращается ведение журналов входящих и исходящих звонков, а также удаляются файлы кэша:
  
```
Stop-CcLogging -RemoveCache
```

## <a name="detailed-description"></a>Подробное описание
<a name="DetailedDescription"> </a>

Командлет Stop-CcLogging прекращает ведение журналов входящих и исходящих звонков для устройства. По умолчанию ведение журналов автоматически прекращается через четыре часа.
  
## <a name="parameters"></a>Параметры
<a name="DetailedDescription"> </a>

|**Параметр**|**Обязательно**|**Тип**|**Описание**.|
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
  

