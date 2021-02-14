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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 7d370abd-0c01-4490-88a1-55b42e51b663
description: Возвращает версию устройства Cloud Connector. Get-CCVersion можно использовать только на хост-компьютере Cloud Connector.
ms.openlocfilehash: 706b480c2f8e277b7f41fe28e88cc062fea6603a
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41799849"
---
# <a name="get-ccversion"></a>Get-CcVersion
 
Возвращает версию устройства Cloud Connector. Get-CCVersion можно использовать только на хост-компьютере Cloud Connector.
  
```powershell
Get-CcVersion [[-VersionType] <String>] [<CommonParameters>]
```

## <a name="detailed-description"></a>Подробное описание

Возвращает версию устройства Cloud Connector на основе установленных сценариев PowerShell, файлов в каталоге устройства и виртуальных машин, развернутых на сервере размещения.
  
## <a name="parameters"></a>Параметры

|**Параметр**|**Required**|**Тип**|**Описание**|
|:-----|:-----|:-----|:-----|
|VersionType  <br/> |Необязательный  <br/> |System.String  <br/> |Тип версии. Значение параметра может быть RunningScripts, RunningBits, BackupBits или All. Значение по умолчанию — RunningScripts.  <br/> |
   
## <a name="examples"></a>Примеры
<a name="Examples"> </a>

### <a name="example-1"></a>Пример 1

В следующем примере показана версия Cloud Connector для запущенного сценария в открытой консоли PowerShell:
  
```powershell
Get-CcVersion
```

### <a name="example-2"></a>Пример 2

В следующем примере показана версия Cloud Connector запущенных в настоящее время binaries, развернутых на виртуальных машинах. Вы можете увидеть версию в именах работающих виртуальных машин в диспетчере Hyper-v:
  
```powershell
Get-CCVersion -VersionType RunningBits
```

## <a name="input-types"></a>Типы входных данных
<a name="Examples"> </a>

Нет. Этот Get-CcVersion не принимает конвейерные входные данные.
  
## <a name="return-types"></a>Типы возвращаемых данных
<a name="Examples"> </a>

Нет.
  
## <a name="see-also"></a>См. также
<a name="Examples"> </a>

Нет.
  

