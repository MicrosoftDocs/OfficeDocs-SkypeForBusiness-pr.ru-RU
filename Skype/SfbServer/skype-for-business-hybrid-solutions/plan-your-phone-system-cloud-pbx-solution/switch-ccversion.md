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
description: 'Командлет Switch-CcVersion отключает работающее устройство и выполняет переключение на только что развернутое или резервное устройство. '
ms.openlocfilehash: 31dbb841caae51de0accedf081fa576ec378044b
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824153"
---
# <a name="switch-ccversion"></a>Switch-CcVersion
 
Командлет Switch-CcVersion отключает работающее устройство и выполняет переключение на только что развернутое или резервное устройство.  
  
```powershell
Switch-CcVersion [-Force]
```

## <a name="examples"></a>Примеры
<a name="Examples"> </a>

### <a name="example-1"></a>Пример 1

В следующем примере очищаются службы работающего устройства и выполняется переключение на только что развернутое или резервное устройство.
  
```powershell
Switch-CcVersion
```

### <a name="example-2"></a>Пример 2

В следующем примере очищаются службы работающего устройства, а в случае сбоя очистки службы принудительно останавливаются. Затем эта команда выполняет переключение на только что развернутое или резервное устройство.
  
```powershell
Switch-CcVersion -Force
```

## <a name="detailed-description"></a>Подробное описание
<a name="DetailedDescription"> </a>

Командлет Switch-Ккверсион перестокует службы облачного соединителя на сервере-посреднике и пограничном сервере. Все выполняемые звонки завершаются, а устройство будет отклонять любые новые звонки. После очистки командлет отключает работающее устройство от корпоративной сети и Интернета, выключает все принадлежащие устройству виртуальные машины, после чего подключает к корпоративной сети и Интернету резервное устройство.
  
## <a name="parameters"></a>Параметры
<a name="DetailedDescription"> </a>

|**Параметр**|**Обязательный**|**Тип**|**Описание**|
|:-----|:-----|:-----|:-----|
| Force <br/> | Необязательно <br/> |System.Management.Automation.SwitchParameter  <br/> |  Принудительно останавливает службы при сбое их очистки. <br/> |
   
## <a name="input-types"></a>Типы входных данных
<a name="InputTypes"> </a>

Нет
  
## <a name="return-types"></a>Типы возвращаемых данных
<a name="ReturnTypes"> </a>

Отсутствуют
  
## <a name="see-also"></a>См. также
<a name="ReturnTypes"> </a>

Нет
  

