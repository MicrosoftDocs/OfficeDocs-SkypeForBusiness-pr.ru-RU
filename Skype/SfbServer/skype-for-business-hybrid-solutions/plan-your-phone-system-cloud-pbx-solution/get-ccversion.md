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
ms.openlocfilehash: a7d50bbcd01dc80fe3e2202286c1adc1b5d5f9bd
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003349"
---
# <a name="get-ccversion"></a>Get-CcVersion
 
Возвращает версию устройства Cloud Connector. Использовать командлет Get-CCVersion можно только на хост-компьютере Cloud Connector.
  
```powershell
Get-CcVersion [[-VersionType] <String>] [<CommonParameters>]
```

## <a name="detailed-description"></a>Подробное описание

Возвращает версию устройства облачного соединителя, основанную на установленных сценариях PowerShell, файлах в каталоге устройства и виртуальных машинах, развернутых на сервере узла.
  
## <a name="parameters"></a>Параметры

|**Параметр**|**Обязательный**|**Тип**|**Описание**|
|:-----|:-----|:-----|:-----|
|VersionType  <br/> |Необязательно  <br/> |System.String  <br/> |Тип версии. Этот параметр может иметь значения RunningScripts, RunningBits, BackupBits или All. Значение по умолчанию: RunningScripts.   <br/> |
   
## <a name="examples"></a>Примеры
<a name="Examples"> </a>

### <a name="example-1"></a>Пример 1

В следующем примере показана версия облачного соединителя запущенного сценария на открытой консоли PowerShell.
  
```powershell
Get-CcVersion
```

### <a name="example-2"></a>Пример 2

В следующем примере показана версия облачного соединителя для исполняемых в данный момент двоичных файлов, развернутых на виртуальных машинах. Версию можно просмотреть в названиях виртуальных машин в диспетчере Hyper-V.
  
```powershell
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
  

