---
title: Удаление CcAppliance
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/23/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e1b3cdd7-08e9-41a6-843a-3b4baf886cd0
description: 'Командлет Uninstall-CcAppliance удаляет работающее устройство Skype для бизнеса Cloud Connector Edition с сервера узла. '
ms.openlocfilehash: 325e21d28ef87f9d27e87721452bc3d67d197169
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="uninstall-ccappliance"></a>Удаление CcAppliance
 
Командлет Uninstall-CcAppliance удаляет работающее устройство Skype для бизнеса Cloud Connector Edition с сервера узла.  
  
```
Uninstall-CcAppliance [-Version <string>] [-Force] [-Confirm <bool>] [<CommonParameters>]
```

## <a name="examples"></a>Примеры
<a name="Examples"> </a>

### <a name="example-1"></a>Пример 1

В следующем примере извлекаются и удаляет appliance облачных соединителя с хост-сервера:
  
```
Uninstall-CcAppliance
```

### <a name="example-2"></a>Пример 2

Далее примере извлекаются и принудительно удаляет выполняемого appliance облачных соединителя на хост-сервера, даже в том случае, если не удалось выполнить процесс обозначает:
  
```
Uninstall-CcAppliance -Force
```

### <a name="example-3"></a>Пример 3

Следующий пример удаляет в облаке соединителя резервной версии без запроса подтверждения пользователя:
  
```
Uninstall-CcAppliance -Version 1.3.8 -Confirm:$false
```

## <a name="detailed-description"></a>Подробное описание
<a name="DetailedDescription"> </a>

При удалении текущей версии выполняемого соединителя облачных обозначает службы сначала выполняются на сервер-посредник и пограничного сервера, чтобы позволить одновременных звонков завершить перед удалением виртуальных машин. При удалении резервной версии опустошения не выполняется.
  
## <a name="parameters"></a>Параметры
<a name="DetailedDescription"> </a>

|**Параметр**|**Обязательно**|**Тип**|**Описание**|
|:-----|:-----|:-----|:-----|
| Версия <br/> | Необязательно <br/> |System.String  <br/> | Версия облачных соединитель, который будет удален из хост-сервера. Если этот параметр не задан, удаляется текущая версия. <br/> |
|Force  <br/> | Необязательно  <br/> |System.Management.Automation.SwitchParameter  <br/> |При удалении текущей рабочей версии предпринимается попытка выполнить очистку на сервере-посреднике и пограничном сервере до удаления виртуальных машин. Если задан параметр "Force", виртуальные машины будут удалены даже в том случае, если работа служб очистки завершится сбоем. Этот параметр используется только для удаления текущей рабочей версии.  <br/> |
|Confirm  <br/> |Необязательно  <br/> |System.Management.Automation.SwitchParameter  <br/> |Запрос подтверждения пользователя для удаления виртуальных машин. Значение по умолчанию: TRUE.  <br/> |
   
## <a name="input-types"></a>Типы входных данных
<a name="InputTypes"> </a>

Нет. Командлет Uninstall-CcAppliance не принимает входные данные по конвейеру.
  
## <a name="return-types"></a>Типы возвращаемых данных
<a name="ReturnTypes"> </a>

Нет
  
## <a name="see-also"></a>См. также
<a name="ReturnTypes"> </a>

[Install-CcAppliance](install-ccappliance.md)
  
[Публикация CcAppliance](publish-ccappliance.md)
  
[Register-CcAppliance](register-ccappliance.md)
  
[Отмена регистрации CcAppliance](unregister-ccappliance.md)
  

