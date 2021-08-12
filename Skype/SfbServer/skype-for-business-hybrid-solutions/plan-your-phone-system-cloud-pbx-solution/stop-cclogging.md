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
description: Этот Stop-CcLogging перестает создавать журнал входящих и исходяющих вызовов для Skype для бизнеса Cloud Connector Edition устройства.
ms.openlocfilehash: 7813acf9867829cadaa26d84a0e8a6c33f825ef45b9fca781840a44f94574930
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2021
ms.locfileid: "54347564"
---
# <a name="stop-cclogging"></a>Stop-CcLogging
 
Этот Stop-CcLogging перестает создавать журнал входящих и исходяющих вызовов для Skype для бизнеса Cloud Connector Edition устройства.
  
```powershell
Stop-CcLogging [-RemoveCache]
```

## <a name="examples"></a>Примеры
<a name="Examples"> </a>

### <a name="example-1"></a>Пример 1

В следующем примере прекращается создание журнала входящих и исходяющих вызовов: 
  
```powershell
Stop-CcLogging
```

### <a name="example-2"></a>Пример 2

В следующем примере прекращается создание журнала входящих и исходяющих вызовов и очищается кэш-файлы:
  
```powershell
Stop-CcLogging -RemoveCache
```

## <a name="detailed-description"></a>Подробное описание
<a name="DetailedDescription"> </a>

Этот Stop-CcLogging прекращает ведение журнала входящих и исходяющих вызовов на устройстве. По умолчанию журнал автоматически остановится через четыре часа.
  
## <a name="parameters"></a>Параметры
<a name="DetailedDescription"> </a>

|**Параметр**|**Required**|**Тип**|**Описание**|
|:-----|:-----|:-----|:-----|
| RemoveCache <br/> | Необязательный <br/> | System.Management.Automation.SwitchParameter <br/> |Удаляет файлы кэша ведения журнала.  <br/> |
   
## <a name="input-types"></a>Типы входных данных
<a name="InputTypes"> </a>

Нет. В Stop-CcLogging не принимается конвейерный ввод.
  
## <a name="return-types"></a>Типы возвращаемых данных
<a name="ReturnTypes"> </a>

Нет
  
## <a name="see-also"></a>См. также
<a name="ReturnTypes"> </a>

[Search-CcLog](search-cclog.md)
  
[Start-CcLogging](start-cclogging.md)
  

