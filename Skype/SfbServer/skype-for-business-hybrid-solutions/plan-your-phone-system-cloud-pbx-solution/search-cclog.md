---
title: CcLog поиска
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/20/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: bbae05f9-d8de-40dc-8968-d225dcde80e4
description: Командлет Search-CcLog выполняет поиск журналов входящих и исходящих звонков в каталоге журнала устройства Skype для бизнеса Cloud Connector Edition.
ms.openlocfilehash: 3d7d34f2e069b9c4ed728dcc805af5ccf9d13067
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="search-cclog"></a>CcLog поиска
 
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
|Время начала  <br/> | Обязательно <br/> |System.Datetime  <br/> | Начальные дата и время для искомых записей журнала. Указываются в местном часовом поясе. <br/> |
|Время окончания  <br/> |Обязательно  <br/> |System.Datetime  <br/> |Конечные дата и время для искомых записей журнала. Указываются в местном часовом поясе.  <br/> |
|Имя файла  <br/> |Обязательно  <br/> |System.String  <br/> |Указывает полный путь к текстовому файлу, содержащему результаты поиска.  <br/> |
   
## <a name="input-types"></a>Типы входных данных
<a name="InputTypes"> </a>

Нет. Командлет Search-CcLog не принимает входные данные по конвейеру.
  
## <a name="return-types"></a>Типы возвращаемых данных
<a name="ReturnTypes"> </a>

Нет
  
## <a name="see-also"></a>См. также
<a name="ReturnTypes"> </a>

[Start-CcLogging](start-cclogging.md)
  
[STOP-CcLogging](stop-cclogging.md)
  

