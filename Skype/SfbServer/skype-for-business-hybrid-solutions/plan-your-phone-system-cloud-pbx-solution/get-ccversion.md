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
description: Возвращает версию устройства cloud Connector. Get-CCVersion можно использовать только на хост-машине Cloud Connector.
ms.openlocfilehash: d3da9813fd67228f8e198cd21edce3cc187ac9359617eb660a352b38c51a95ba
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2021
ms.locfileid: "54349511"
---
# <a name="get-ccversion"></a>Get-CcVersion
 
Возвращает версию устройства cloud Connector. Get-CCVersion можно использовать только на хост-машине Cloud Connector.
  
```powershell
Get-CcVersion [[-VersionType] <String>] [<CommonParameters>]
```

## <a name="detailed-description"></a>Подробное описание

Возвращает версию устройства Cloud Connector на основе установленных скриптов PowerShell, файлов в каталоге Appliance и виртуальных машин, развернутых на сервере хост-серверов.
  
## <a name="parameters"></a>Параметры

|**Параметр**|**Required**|**Тип**|**Описание**|
|:-----|:-----|:-----|:-----|
|VersionType  <br/> |Необязательный  <br/> |System.String  <br/> |Тип версии. Значение параметра может быть RunningScripts, RunningBits, BackupBits или Все. Значение по умолчанию — RunningScripts.  <br/> |
   
## <a name="examples"></a>Примеры
<a name="Examples"> </a>

### <a name="example-1"></a>Пример 1

В следующем примере показана версия облачного соединителя для запущенного скрипта в открытой консоли PowerShell:
  
```powershell
Get-CcVersion
```

### <a name="example-2"></a>Пример 2

В следующем примере показана версия облачного соединитетеля текущих бинарей, развернутых на виртуальных машинах. Вы можете увидеть версию в запущенных виртуальных именах машин в Hyper-v Manager:
  
```powershell
Get-CCVersion -VersionType RunningBits
```

## <a name="input-types"></a>Типы входных данных
<a name="Examples"> </a>

Нет. В Get-CcVersion не принимается конвейерный ввод.
  
## <a name="return-types"></a>Типы возвращаемых данных
<a name="Examples"> </a>

Нет.
  
## <a name="see-also"></a>См. также
<a name="Examples"> </a>

Нет.
  

