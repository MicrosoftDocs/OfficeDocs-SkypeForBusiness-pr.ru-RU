---
title: Switch-CcVersion
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
ms.assetid: 95e37b13-525b-4690-be32-839312e4ffe3
description: Этот Switch-CcVersion отключает запущенные устройства и переключается на новое развертывание или резервное устройство.
ms.openlocfilehash: 31dbb841caae51de0accedf081fa576ec378044b
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824153"
---
# <a name="switch-ccversion"></a>Switch-CcVersion
 
Этот Switch-CcVersion отключает запущенные устройства и переключается на новое развертывание или резервное устройство. 
  
```powershell
Switch-CcVersion [-Force]
```

## <a name="examples"></a>Примеры
<a name="Examples"> </a>

### <a name="example-1"></a>Пример 1

В следующем примере службы текущего запущенного устройства разрядяются, а затем переключаются на только что развернутые или резервные устройства.
  
```powershell
Switch-CcVersion
```

### <a name="example-2"></a>Пример 2

В следующем примере службы текущего запущенного устройства и принудительно останавливаются в случае сбойной работы служб. Затем команда переключается на новое развертывание или резервное устройство:
  
```powershell
Switch-CcVersion -Force
```

## <a name="detailed-description"></a>Подробное описание
<a name="DetailedDescription"> </a>

Этот Switch-CcVersion истощает службы Cloud Connector на сервере-посреднике и на сервере-посреднике. Все запущенные вызовы будут завершены, но устройство отклоняет все новые вызовы. После этого он отключает запущенные устройства от корпоративной сети и интернет-сетей, отключает все виртуальные машины, принадлежащие устройству, а затем подключает устройство резервного копирования к корпоративным и интернет-сетям.
  
## <a name="parameters"></a>Параметры
<a name="DetailedDescription"> </a>

|**Параметр**|**Required**|**Тип**|**Описание**|
|:-----|:-----|:-----|:-----|
| Force <br/> | Необязательный <br/> |System.Management.Automation.SwitchParameter  <br/> | Принудительно останавливает службы в случае сбой их ливни. <br/> |
   
## <a name="input-types"></a>Типы входных данных
<a name="InputTypes"> </a>

Нет
  
## <a name="return-types"></a>Типы возвращаемых данных
<a name="ReturnTypes"> </a>

Нет
  
## <a name="see-also"></a>См. также
<a name="ReturnTypes"> </a>

Нет
  

