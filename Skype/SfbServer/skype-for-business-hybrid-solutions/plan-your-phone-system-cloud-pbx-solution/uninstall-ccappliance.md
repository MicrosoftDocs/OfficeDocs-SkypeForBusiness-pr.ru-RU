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
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: e1b3cdd7-08e9-41a6-843a-3b4baf886cd0
description: Этот Uninstall-CcAppliance отстрагирует работающий Skype для бизнеса Cloud Connector Edition с сервера-хозяина.
ms.openlocfilehash: 12a15e7bc338fc503a1fafbd6e3059f73dcd40d4
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/26/2021
ms.locfileid: "58624951"
---
# <a name="uninstall-ccappliance"></a>Uninstall-CcAppliance
 
Этот Uninstall-CcAppliance отстрагирует работающий Skype для бизнеса Cloud Connector Edition с сервера-хозяина. 
  
```powershell
Uninstall-CcAppliance [-Version <string>] [-Force] [-Confirm <bool>] [<CommonParameters>]
```

## <a name="examples"></a>Примеры
<a name="Examples"> </a>

### <a name="example-1"></a>Пример 1

В следующем примере с сервера хост-сервера стекается и отстраняться устройство Cloud Connector:
  
```powershell
Uninstall-CcAppliance
```

### <a name="example-2"></a>Пример 2

Следующий пример слива и принудительного слива запущенного устройства облачного соединиттеля на сервере хост-сервера, даже если процесс слива не состоялся:
  
```powershell
Uninstall-CcAppliance -Force
```

### <a name="example-3"></a>Пример 3

В следующем примере можно отстранять версию резервного копирования облачного соединитетеля без подтверждения пользователя:
  
```powershell
Uninstall-CcAppliance -Version 1.3.8 -Confirm:$false
```

## <a name="detailed-description"></a>Подробное описание
<a name="DetailedDescription"> </a>

Если вы отстранять текущую версию облачного соединитетеля, службы слива сначала запускаются на сервере-посреднике и краевом сервере, чтобы завершить одновременное выполнение вызовов, прежде чем отстранять виртуальные машины. Если выполняется разгрузка резервной версии, осушение не выполняется.
  
## <a name="parameters"></a>Параметры
<a name="DetailedDescription"> </a>

|**Параметр**|**Required**|**Тип**|**Описание**|
|:-----|:-----|:-----|:-----|
| Версия <br/> | Необязательный <br/> |System.String  <br/> | Версия облачного соединитетеля, которая будет неустановлена на сервере хост-сервера. Если не указано, удалить текущую запущенную версию. <br/> |
|Force  <br/> |Необязательный  <br/> |System.Management.Automation.SwitchParameter  <br/> |При отстраив текущую запущенную версию, попытайтесь осушить серверы на сервере-посреднике и edge Server, прежде чем отстраить виртуальные машины. Если указать переключатель "Force", даже если службы стока сбой, виртуальные машины будут uninstalled. Этот параметр используется только для того, чтобы удалить текущую запущенную версию.  <br/> |
|Подтверждение  <br/> |Необязательный  <br/> |System.Management.Automation.SwitchParameter  <br/> |Попросите подтверждение пользователя удалить виртуальные машины. Значение по умолчанию — TRUE.  <br/> |
   
## <a name="input-types"></a>Типы входных данных
<a name="InputTypes"> </a>

Нет. В Uninstall-CcAppliance не принимается конвейерный ввод.
  
## <a name="return-types"></a>Типы возвращаемых данных
<a name="ReturnTypes"> </a>

Нет
  
## <a name="see-also"></a>См. также
<a name="ReturnTypes"> </a>

[Install-CcAppliance](install-ccappliance.md)
  
[Publish-CcAppliance](publish-ccappliance.md)
  
[Register-CcAppliance](register-ccappliance.md)
  
[Unregister-CcAppliance](unregister-ccappliance.md)
  

