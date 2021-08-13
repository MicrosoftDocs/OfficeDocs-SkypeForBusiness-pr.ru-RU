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
description: Этот Switch-CcVersion отключает работающий прибор и переключается на недавно развернутый или резервный.
ms.openlocfilehash: 1558f34d2388dc75bf4398ba15fc09cd36c439e2d70a39588ee697bc0ef04341
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2021
ms.locfileid: "54320042"
---
# <a name="switch-ccversion"></a>Switch-CcVersion
 
Этот Switch-CcVersion отключает работающий прибор и переключается на недавно развернутый или резервный. 
  
```powershell
Switch-CcVersion [-Force]
```

## <a name="examples"></a>Примеры
<a name="Examples"> </a>

### <a name="example-1"></a>Пример 1

В следующем примере стекаются службы текущего запущенного устройства, а затем переключаются на недавно развернутый или резервный прибор:
  
```powershell
Switch-CcVersion
```

### <a name="example-2"></a>Пример 2

В следующем примере истощаются службы текущего запущенного устройства и принудительно останавливаются службы в случае слива служб. Затем команда переключается на недавно развернутый или резервный аппарат:
  
```powershell
Switch-CcVersion -Force
```

## <a name="detailed-description"></a>Подробное описание
<a name="DetailedDescription"> </a>

Этот Switch-CcVersion истощает службы облачного соединителя на сервере-посреднике и краевом сервере. Все запущенные вызовы будут завершены, но устройство отклоняет все новые вызовы. После слива, комлет отключает работающий прибор от корпоративных и интернет-сетей, отключает все виртуальные машины, принадлежащие устройству, а затем подключает устройство резервного копирования к корпоративным и интернет-сетям.
  
## <a name="parameters"></a>Параметры
<a name="DetailedDescription"> </a>

|**Параметр**|**Required**|**Тип**|**Описание**|
|:-----|:-----|:-----|:-----|
| Force <br/> | Необязательный <br/> |System.Management.Automation.SwitchParameter  <br/> | Принудительно останавливает службы, если сбой слива служб. <br/> |
   
## <a name="input-types"></a>Типы входных данных
<a name="InputTypes"> </a>

Нет
  
## <a name="return-types"></a>Типы возвращаемых данных
<a name="ReturnTypes"> </a>

Нет
  
## <a name="see-also"></a>См. также
<a name="ReturnTypes"> </a>

Нет
  

