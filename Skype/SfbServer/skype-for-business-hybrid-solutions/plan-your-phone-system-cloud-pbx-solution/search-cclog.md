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
localization_priority: Normal
ms.assetid: bbae05f9-d8de-40dc-8968-d225dcde80e4
description: Командлет Search-CcLog выполняет поиск журналов входящих и исходящих звонков в каталоге журнала устройства Skype для бизнеса Cloud Connector Edition.
ms.openlocfilehash: 7d1591953004ecf0e0d0a3bfdf2e998e06002325
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34287043"
---
# <a name="search-cclog"></a>Search-CcLog
 
Командлет Search-CcLog выполняет поиск журналов входящих и исходящих звонков в каталоге журнала устройства Skype для бизнеса Cloud Connector Edition.
  
```
Search-CcLog [[-StartTime] <datetime>] [[-EndTime] <datetime>] [[-FileName] <string>]
```

## <a name="examples"></a>Примеры
<a name="Examples"> </a>

### <a name="example-1"></a>Пример 1

В следующем примере выполняется поиск журналов входящих и исходящих звонков в каталоге журнала устройства с использованием имени файла по умолчанию.
  
```
Search-CcLog -StartTime "8/31/2012 8:00AM" -EndTime "8/31/2012 6:00PM"
```

### <a name="example-2"></a>Пример 2

В следующем примере выполняется поиск журналов входящих и исходящих звонков с использованием указанных имени файла и пути к нему.
  
```
Search-CcLog -StartTime "8/31/2012 8:00AM" -EndTime "8/31/2012 6:00PM" -FileName "C:\Log\LogFile.log"
```

## <a name="detailed-description"></a>Подробное описание
<a name="DetailedDescription"> </a>

Командлет  Search-CsClsLogging предоставляет параметр командной строки для поиска файлов журнала, созданных службой централизованного ведения журналов.
  
## <a name="parameters"></a>Параметры
<a name="DetailedDescription"> </a>

|**Параметр**|**Обязательно**|**Тип**|**Описание**|
|:-----|:-----|:-----|:-----|
|StartTime  <br/> | Обязательно <br/> |System.Datetime  <br/> | Начальные дата и время для искомых записей журнала. Указываются в местном часовом поясе. <br/> |
|EndTime  <br/> |Обязательно  <br/> |System.Datetime  <br/> |Конечные дата и время для искомых записей журнала. Указываются в местном часовом поясе.  <br/> |
|FileName  <br/> |Обязательно  <br/> |System.String  <br/> |Указывает полный путь к текстовому файлу, содержащему результаты поиска.  <br/> |
   
## <a name="input-types"></a>Типы входных данных
<a name="InputTypes"> </a>

Нет. Командлет Search-CcLog не принимает входные данные по конвейеру.
  
## <a name="return-types"></a>Типы возвращаемых данных
<a name="ReturnTypes"> </a>

Нет
  
## <a name="see-also"></a>См. также
<a name="ReturnTypes"> </a>

[Start-CcLogging](start-cclogging.md)
  
[Stop-CcLogging](stop-cclogging.md)
  

