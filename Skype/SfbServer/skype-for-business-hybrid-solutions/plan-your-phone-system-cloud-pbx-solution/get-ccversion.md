---
title: Get-CcVersion
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 6/30/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7d370abd-0c01-4490-88a1-55b42e51b663
description: Возвращает версию устройства Cloud Connector. Использовать командлет Get-CCVersion можно только на хост-компьютере Cloud Connector.
ms.openlocfilehash: 5e5428e53d53eec66bafa9eb566059ef1b5a5833
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30881335"
---
# <a name="get-ccversion"></a>Get-CcVersion
 
Возвращает версию устройства Cloud Connector. Использовать командлет Get-CCVersion можно только на хост-компьютере Cloud Connector.
  
```
Get-CcVersion [[-VersionType] <String>] [<CommonParameters>]
```

## <a name="detailed-description"></a>Подробное описание

Возвращает номер версии соединителя облачных устройства для обеспечения связи на основании скриптов PowerShell установлен, файлы в каталоге Appliance и виртуальных машин, развернутых на хост-сервера.
  
## <a name="parameters"></a>Параметры

|**Параметр**|**Обязательно**|**Тип**|**Описание**.|
|:-----|:-----|:-----|:-----|
|VersionType  <br/> |Необязательно  <br/> |System.String  <br/> |Тип версии. Этот параметр может иметь значения RunningScripts, RunningBits, BackupBits или All. Значение по умолчанию: RunningScripts.   <br/> |
   
## <a name="examples"></a>Примеры
<a name="Examples"> </a>

### <a name="example-1"></a>Пример 1

В следующем примере показано версии облачных соединителя запущенные в настоящий момент скрипта в открыть консоль PowerShell:
  
```
Get-CcVersion
```

### <a name="example-2"></a>Пример 2

В следующем примере показано версии облачных соединителя запущенные в настоящий момент двоичные файлы, развертывание виртуальных машин. Версию можно просмотреть в названиях виртуальных машин в диспетчере Hyper-V.
  
```
Get-CCVersion -VersionType RunningBits
```

## <a name="input-types"></a>Типы входных данных
<a name="Examples"> </a>

Нет. Командлет Get-CcVersion не принимает входные данные по конвейеру.
  
## <a name="return-types"></a>Типы возвращаемых данных
<a name="Examples"> </a>

Нет. 
  
## <a name="see-also"></a>См. также
<a name="Examples"> </a>

Нет.
  

