---
title: Get-CcVersion
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 6/30/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7d370abd-0c01-4490-88a1-55b42e51b663
description: Возвращает версию устройства Cloud Connector. Использовать командлет Get-CCVersion можно только на хост-компьютере Cloud Connector.
ms.openlocfilehash: b002b4a9f0cae34a2cdd7b8817e86a3e4ec2eb9a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34287253"
---
# <a name="get-ccversion"></a>Get-CcVersion
 
Возвращает версию устройства Cloud Connector. Использовать командлет Get-CCVersion можно только на хост-компьютере Cloud Connector.
  
```
Get-CcVersion [[-VersionType] <String>] [<CommonParameters>]
```

## <a name="detailed-description"></a>Подробное описание

Возвращает версию устройства облачного соединителя, основанную на установленных сценариях PowerShell, файлах в каталоге устройства и виртуальных машинах, развернутых на сервере узла.
  
## <a name="parameters"></a>Параметры

|**Параметр**|**Обязательно**|**Тип**|**Описание**|
|:-----|:-----|:-----|:-----|
|VersionType  <br/> |Необязательно  <br/> |System.String  <br/> |Тип версии. Этот параметр может иметь значения RunningScripts, RunningBits, BackupBits или All. Значение по умолчанию: RunningScripts.   <br/> |
   
## <a name="examples"></a>Примеры
<a name="Examples"> </a>

### <a name="example-1"></a>Пример 1

В следующем примере показана версия облачного соединителя запущенного сценария на открытой консоли PowerShell.
  
```
Get-CcVersion
```

### <a name="example-2"></a>Пример 2

В следующем примере показана версия облачного соединителя для исполняемых в данный момент двоичных файлов, развернутых на виртуальных машинах. Версию можно просмотреть в названиях виртуальных машин в диспетчере Hyper-V.
  
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
  

