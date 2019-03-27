---
title: Unregister-CcAppliance
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3d516e65-fb9b-4a0b-8296-969fc9eda334
description: Командлет Unregister-CcAppliance отменяет регистрацию текущего устройства Skype для бизнеса Cloud Connector Edition для сайта ТСОП в конфигурации интерактивного клиента.
ms.openlocfilehash: 6ee21f66c2b189aff8c8aa7d831369536618b18c
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30892006"
---
# <a name="unregister-ccappliance"></a>Unregister-CcAppliance
 
Командлет Unregister-CcAppliance отменяет регистрацию текущего устройства Skype для бизнеса Cloud Connector Edition для сайта ТСОП в конфигурации интерактивного клиента.
  
```
Unregister-CcAppliance [[-SiteName] <string>] [[-ApplianceName] <string>] [-Local]
```

## <a name="examples"></a>Примеры
<a name="Examples"> </a>

### <a name="example-1"></a>Пример 1

В следующем примере отменяется регистрация текущего устройства в конфигурации интерактивного клиента:
  
```
Unregister-CcAppliance
```

### <a name="example-2"></a>Пример 2

В следующем примере выполняется локальная проверка отмены регистрации без подключения к конфигурации интерактивного клиента:
  
```
Unregister-CcAppliance -Local
```

### <a name="example-3"></a>Пример 3

В следующем примере отменяется регистрация текущего устройства с именем "Appliance1" на сайте ТСОП "Site1":
  
```
Unregister-CcAppliance -SiteName Site1 -ApplianceName Appliance1
```

## <a name="detailed-description"></a>Подробное описание
<a name="DetailedDescription"> </a>

Как и в случае с командлетом Register-CcAppliance, в качестве удостоверения сайта ТСОП выступает имя сайта в сочетании с внешним полным доменным именем пограничного сервера в файле CloudConnector.ini. Аналогичным образом, в качестве удостоверения устройства выступает имя устройства в сочетании с внешним полным доменным именем сервера-посредника в файле CloudConnector.ini.
  
После незарегистрированных устройства перезагрузите соединителя облачной службы управления и журналов на как учетная запись сетевой службы.
  
## <a name="parameters"></a>Параметры
<a name="DetailedDescription"> </a>

|**Параметр**|**Обязательно**|**Тип**|**Описание**.|
|:-----|:-----|:-----|:-----|
| SiteName <br/> |Необязательно   <br/> |System.String  <br/> |Имя сайта ТСОП, на котором регистрируется устройство. В качестве значения по умолчанию принимается значение SiteName в файле CloudConnector.ini.  <br/> |
|ApplianceName  <br/> |Необязательно   <br/> |System.String  <br/> |Имя текущего устройства В качестве значения по умолчанию принимается имя компьютера, присвоенное серверу узла.  <br/> |
|Локально  <br/> |Необязательно  <br/> |System.Management.Automation.SwitchParameter  <br/> |Локальная проверка конфигурации регистрации без подключения к конфигурации интерактивного клиента.  <br/> |
   
## <a name="input-types"></a>Типы входных данных
<a name="InputTypes"> </a>

Нет. Командлет Unregister-CcAppliance не принимает входные данные по конвейеру.
  
## <a name="return-types"></a>Типы возвращаемых данных
<a name="ReturnTypes"> </a>

Нет
  
## <a name="see-also"></a>См. также
<a name="ReturnTypes"> </a>

[Register-CcAppliance](register-ccappliance.md)
  
[Install-CcAppliance](install-ccappliance.md)
  
[Uninstall-CcAppliance](uninstall-ccappliance.md)
  
[Publish-CcAppliance](publish-ccappliance.md)
  

