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
localization_priority: Normal
ms.assetid: e1b3cdd7-08e9-41a6-843a-3b4baf886cd0
description: С помощью Uninstall-CcAppliance-сервера с хост-сервера будет выгрузка запущенного устройства Skype для бизнеса Cloud Connector Edition.
ms.openlocfilehash: c92ad5c31e2e254e4f10511835b6cc9f60c7c43c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824143"
---
# <a name="uninstall-ccappliance"></a>Uninstall-CcAppliance
 
С помощью Uninstall-CcAppliance-сервера с хост-сервера будет выгрузка запущенного устройства Skype для бизнеса Cloud Connector Edition. 
  
```powershell
Uninstall-CcAppliance [-Version <string>] [-Force] [-Confirm <bool>] [<CommonParameters>]
```

## <a name="examples"></a>Примеры
<a name="Examples"> </a>

### <a name="example-1"></a>Пример 1

В следующем примере устройство Cloud Connector с сервера хост-сервера будет разрядлено и выгрузлено:
  
```powershell
Uninstall-CcAppliance
```

### <a name="example-2"></a>Пример 2

В следующем примере на хост-сервере происходит принудительное истощается запущенное устройство Cloud Connector, даже если процесс утечки не удался:
  
```powershell
Uninstall-CcAppliance -Force
```

### <a name="example-3"></a>Пример 3

В следующем примере пошаговая версия резервной копии Cloud Connector будет без подтверждения пользователя:
  
```powershell
Uninstall-CcAppliance -Version 1.3.8 -Confirm:$false
```

## <a name="detailed-description"></a>Подробное описание
<a name="DetailedDescription"> </a>

Если вы укажете текущую запущенную версию Cloud Connector, на сервере-посреднике и на сервере-посреднике сначала будут запущены службы опустынения, чтобы завершиться выполнение одновременно работающих вызовов перед тем, как они будут выгружены виртуальными машинами. При выполнении стирания резервной версии не выполняется сток.
  
## <a name="parameters"></a>Параметры
<a name="DetailedDescription"> </a>

|**Параметр**|**Required**|**Тип**|**Описание**|
|:-----|:-----|:-----|:-----|
| Версия <br/> | Необязательный <br/> |System.String  <br/> | Версия Cloud Connector, которая будет выгрузлена с хост-сервера. Если он не указан, удалить текущую запущенную версию. <br/> |
|Force  <br/> |Необязательный  <br/> |System.Management.Automation.SwitchParameter  <br/> |При этом необходимо попытаться оцедить серверы на сервере-посреднике и на сервере-посреднике, прежде чем выгрузить виртуальные машины. Если указать переключатель Force, даже если службы разгрузки не будут работать, виртуальные машины будут выгрузки. Этот параметр используется только для того, чтобы удалить текущую запущенную версию.  <br/> |
|Подтверждение  <br/> |Необязательный  <br/> |System.Management.Automation.SwitchParameter  <br/> |Попросите пользователя подтвердить удалить виртуальные машины. Значение по умолчанию — TRUE.  <br/> |
   
## <a name="input-types"></a>Типы входных данных
<a name="InputTypes"> </a>

Нет. Этот Uninstall-CcAppliance не принимает конвейерные входные данные.
  
## <a name="return-types"></a>Типы возвращаемых данных
<a name="ReturnTypes"> </a>

Нет
  
## <a name="see-also"></a>См. также
<a name="ReturnTypes"> </a>

[Install-CcAppliance](install-ccappliance.md)
  
[Publish-CcAppliance](publish-ccappliance.md)
  
[Register-CcAppliance](register-ccappliance.md)
  
[Unregister-CcAppliance](unregister-ccappliance.md)
  

