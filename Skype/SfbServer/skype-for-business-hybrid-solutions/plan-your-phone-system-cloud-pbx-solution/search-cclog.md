---
title: Search-CcLog
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/20/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: bbae05f9-d8de-40dc-8968-d225dcde80e4
description: Этот Search-CcLog ищет журналы входящих и исходяющих звонков в каталоге журналов устройств Skype для бизнеса Cloud Connector Edition.
ms.openlocfilehash: a512d715f1640184217ce07e0b666954a6541fd2
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824235"
---
# <a name="search-cclog"></a>Search-CcLog
 
Этот Search-CcLog ищет журналы входящих и исходяющих звонков в каталоге журналов устройств Skype для бизнеса Cloud Connector Edition.
  
```powershell
Search-CcLog [[-StartTime] <datetime>] [[-EndTime] <datetime>] [[-FileName] <string>]
```

## <a name="examples"></a>Примеры
<a name="Examples"> </a>

### <a name="example-1"></a>Пример 1

В следующем примере выполняется поиск журналов входящих и исходяющих вызовов в каталоге журнала устройств с использованием имени файла по умолчанию:
  
```powershell
Search-CcLog -StartTime "8/31/2012 8:00AM" -EndTime "8/31/2012 6:00PM"
```

### <a name="example-2"></a>Пример 2

В следующем примере выполняется поиск журналов входящих и исходяющих вызовов с использованием заданного пути и имени файла:
  
```powershell
Search-CcLog -StartTime "8/31/2012 8:00AM" -EndTime "8/31/2012 6:00PM" -FileName "C:\Log\LogFile.log"
```

## <a name="detailed-description"></a>Подробное описание
<a name="DetailedDescription"> </a>

Командлет Search-CsClsLogging предоставляет параметр командной строки для поиска файлов журнала, генерируемых службой централизованного ведения журнала.
  
## <a name="parameters"></a>Параметры
<a name="DetailedDescription"> </a>

|**Параметр**|**Required**|**Тип**|**Описание**|
|:-----|:-----|:-----|:-----|
|StartTime  <br/> | Обязательна <br/> |System.Datetime  <br/> | Начальные дата и время для искомых записей журнала. Указываются в местном часовом поясе. <br/> |
|EndTime  <br/> |Обязательна  <br/> |System.Datetime  <br/> |Конечные дата и время для искомых записей журнала. Указываются в местном часовом поясе.  <br/> |
|FileName  <br/> |Обязательный  <br/> |System.String  <br/> |Указывает полный путь к текстовом файлу, содержащего результаты поиска.  <br/> |
   
## <a name="input-types"></a>Типы входных данных
<a name="InputTypes"> </a>

Нет. Этот Search-CcLog не принимает конвейерные входные данные.
  
## <a name="return-types"></a>Типы возвращаемых данных
<a name="ReturnTypes"> </a>

Нет
  
## <a name="see-also"></a>См. также
<a name="ReturnTypes"> </a>

[Start-CcLogging](start-cclogging.md)
  
[Stop-CcLogging](stop-cclogging.md)
  

