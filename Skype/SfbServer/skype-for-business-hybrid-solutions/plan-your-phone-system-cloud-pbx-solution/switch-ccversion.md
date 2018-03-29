---
title: Переключатель CcVersion
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 95e37b13-525b-4690-be32-839312e4ffe3
description: Командлет Switch-CcVersion отключает работающее устройство и выполняет переключение на только что развернутое или резервное устройство.
ms.openlocfilehash: 651dad80ef5c9907eb6c182527b646da7aa5acc8
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="switch-ccversion"></a>Переключатель CcVersion
 
Командлет Switch-CcVersion отключает работающее устройство и выполняет переключение на только что развернутое или резервное устройство. 
  
```
Switch-CcVersion [-Force]
```

## <a name="examples"></a>Примеры
<a name="Examples"> </a>

### <a name="example-1"></a>Пример 1

В следующем примере очищаются службы работающего устройства и выполняется переключение на только что развернутое или резервное устройство.
  
```
Switch-CcVersion
```

### <a name="example-2"></a>Пример 2

В следующем примере очищаются службы работающего устройства, а в случае сбоя очистки службы принудительно останавливаются. Затем эта команда выполняет переключение на только что развернутое или резервное устройство.
  
```
Switch-CcVersion -Force
```

## <a name="detailed-description"></a>Подробное описание
<a name="DetailedDescription"> </a>

Командлет переключатель CcVersion теряется соединителя облачных служб на сервер-посредник и пограничного сервера. Все выполняемые звонки завершаются, а устройство будет отклонять любые новые звонки. После очистки командлет отключает работающее устройство от корпоративной сети и Интернета, выключает все принадлежащие устройству виртуальные машины, после чего подключает к корпоративной сети и Интернету резервное устройство.
  
## <a name="parameters"></a>Параметры
<a name="DetailedDescription"> </a>

|**Параметр**|**Обязательно**|**Тип**|**Описание**|
|:-----|:-----|:-----|:-----|
| Force <br/> |  Необязательно <br/> |System.Management.Automation.SwitchParameter  <br/> | Принудительно останавливает службы при сбое их очистки. <br/> |
   
## <a name="input-types"></a>Типы входных данных
<a name="InputTypes"> </a>

Нет
  
## <a name="return-types"></a>Типы возвращаемых данных
<a name="ReturnTypes"> </a>

Нет
  
## <a name="see-also"></a>См. также
<a name="ReturnTypes"> </a>

Нет
  

