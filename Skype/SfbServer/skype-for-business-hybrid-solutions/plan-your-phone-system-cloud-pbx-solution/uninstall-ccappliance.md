---
title: Uninstall-CcAppliance
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/23/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e1b3cdd7-08e9-41a6-843a-3b4baf886cd0
description: 'Командлет Uninstall-CcAppliance удаляет работающее устройство Skype для бизнеса Cloud Connector Edition с сервера узла. '
ms.openlocfilehash: f37c3092103832c9efd3b24d2efbedf00e8f54ac
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003149"
---
# <a name="uninstall-ccappliance"></a>Uninstall-CcAppliance
 
Командлет Uninstall-CcAppliance удаляет работающее устройство Skype для бизнеса Cloud Connector Edition с сервера узла.  
  
```powershell
Uninstall-CcAppliance [-Version <string>] [-Force] [-Confirm <bool>] [<CommonParameters>]
```

## <a name="examples"></a>Примеры
<a name="Examples"> </a>

### <a name="example-1"></a>Пример 1

В следующем примере выполняется сток и удаление управляющего устройства облачного соединителя с хостового сервера.
  
```powershell
Uninstall-CcAppliance
```

### <a name="example-2"></a>Пример 2

В следующем примере выполняется сток и принудительное удаление работающего устройства облачного соединителя на сервере узла, даже если процесс стока завершился сбоем.
  
```powershell
Uninstall-CcAppliance -Force
```

### <a name="example-3"></a>Пример 3

В следующем примере удаляется резервная версия облачного соединителя без подтверждения пользователя.
  
```powershell
Uninstall-CcAppliance -Version 1.3.8 -Confirm:$false
```

## <a name="detailed-description"></a>Подробное описание
<a name="DetailedDescription"> </a>

Если вы удаляете текущую работающую версию облачного соединителя, сначала выполняются службы стока на сервере и на пограничном сервере, чтобы начать одновременные звонки перед удалением виртуальных машин. Если вы удаляете резервную версию, сток не выполняется.
  
## <a name="parameters"></a>Параметры
<a name="DetailedDescription"> </a>

|**Параметр**|**Обязательный**|**Тип**|**Описание**|
|:-----|:-----|:-----|:-----|
| Версия <br/> | Необязательно  <br/> |System.String  <br/> | Версия облачного соединителя, которая будет удалена с сервера узла. Если этот параметр не задан, удаляется текущая версия. <br/> |
|Force  <br/> |Необязательный  <br/> |System.Management.Automation.SwitchParameter  <br/> |При удалении текущей рабочей версии предпринимается попытка выполнить очистку на сервере-посреднике и пограничном сервере до удаления виртуальных машин. Если задан параметр "Force", виртуальные машины будут удалены даже в том случае, если работа служб очистки завершится сбоем. Этот параметр используется только для удаления текущей рабочей версии.  <br/> |
|Confirm  <br/> |Необязательно  <br/> |System.Management.Automation.SwitchParameter  <br/> |Запрашивать подтверждение пользователя, чтобы удалить виртуальные машины. Значение по умолчанию: TRUE.  <br/> |
   
## <a name="input-types"></a>Типы входных данных
<a name="InputTypes"> </a>

Нет. Командлет Uninstall-CcAppliance не принимает входные данные по конвейеру.
  
## <a name="return-types"></a>Типы возвращаемых данных
<a name="ReturnTypes"> </a>

Нет
  
## <a name="see-also"></a>См. также
<a name="ReturnTypes"> </a>

[Install-CcAppliance](install-ccappliance.md)
  
[Publish-CcAppliance](publish-ccappliance.md)
  
[Register-CcAppliance](register-ccappliance.md)
  
[Unregister-CcAppliance](unregister-ccappliance.md)
  

