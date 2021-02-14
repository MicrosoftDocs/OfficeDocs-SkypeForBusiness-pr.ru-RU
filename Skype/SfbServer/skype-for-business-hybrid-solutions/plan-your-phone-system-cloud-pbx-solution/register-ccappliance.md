---
title: Register-CcAppliance
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 7/18/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 01eed3c5-af68-4db7-90b3-d28ebe7ffef1
description: Этот Register-CcAppliance регистрирует сведения об устройстве на сайте STN в конфигурации интерактивного клиента. Прежде чем развертывать устройство и управлять им с помощью службы управления Skype для бизнеса Cloud Connector Edition, необходимо зарегистрировать его.
ms.openlocfilehash: a94f9d7189f4872fcee2439afd2b210933f8bb06
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824305"
---
# <a name="register-ccappliance"></a>Register-CcAppliance
 
Этот Register-CcAppliance регистрирует сведения об устройстве на сайте STN в конфигурации интерактивного клиента. Прежде чем развертывать устройство и управлять им с помощью службы управления Skype для бизнеса Cloud Connector Edition, необходимо зарегистрировать его.
  
```powershell
Register-CcAppliance [[-SiteName] <string>] [[-ApplianceName] <string>] [-Local]
```

## <a name="examples"></a>Примеры
<a name="Examples"> </a>

### <a name="example-1"></a>Пример 1

В следующем примере сведения о текущем устройстве регистрируются в конфигурации интерактивного клиента:
  
```powershell
Register-CcAppliance
```

### <a name="example-2"></a>Пример 2

В следующем примере проверяется локализованная регистрация без подключения к конфигурации интерактивного клиента:
  
```powershell
Register-CcAppliance -Local
```

### <a name="example-3"></a>Пример 3

В следующем примере текущее устройство с именем Appliance1 регистрируется на сайте STN "Site1":
  
```powershell
Register-CcAppliance -SiteName Site1 -ApplianceName Appliance1
```

## <a name="detailed-description"></a>Подробное описание
<a name="DetailedDescription"> </a>

Необходимо вводить имя и пароль учетной записи администратора клиента. Используйте учетную запись, созданную для управления Cloud Connector в Интернете. 
  
В выпуске 1.4.2 и более ранних версиях следуйте инструкциям, чтобы предоставить пароль внешнего сертификата, пароль администратора безопасного режима, пароль администратора домена и пароль администратора ВМ. 
  
В выпуске 2.0 и более поздних версиях следуйте инструкциям, чтобы предоставить пароль внешнего сертификата, пароль CceService и пароль CABackupFile.
  
По завершении регистрации перезапустите службу управления Cloud Connector и войдите в службы под учетной записью CceService.
  
SiteName в сочетании с внешним FQDN edge Server в CloudConnector.ini файле считается удостоверением сайта STN. Если для регистрации сайта не использовались ни имя сайта, ни внешнее имя FQDN edge Server, для этого устройства будет создан новый сайт в конфигурации интерактивного клиента. При обнаружении удостоверения сайта STN сайт STN будет использовать это удостоверение, и устройство будет зарегистрировано на этом сайте STN. 
  
В следующей ситуации сбой при этом указывает на то, что site1 уже зарегистрирован: 
  
- SiteName — site1, а внешнее имя FQDN edgserver1.contoso.com. 
    
- Сайт STN, имя которого siteName — Site1, а внешнее имя FQDN edgserver.contoso.com.
    
- Сайт STN, имя сайта которого — NewSite, а внешнее edgserver1.contoso.com зарегистрируется. 
    
ApplianceName в сочетании с FQDN сервера-CloudConnector.ini в файле устройства считается удостоверением устройства. Если для регистрации устройства не использовались ни имя устройства, ни FQDN сервера-посредника, в конфигурации интерактивного клиента будет создано новое устройство. Если устройство уже зарегистрировано, то он не будет работать.
  
В следующей ситуации сбой при этом указывает на то, что устройство уже зарегистрировано: 
  
- ApplianceName — это Appliance1, а сервер-посредник — ms1.vdomain.com.
    
- На текущем сайте STN, если устройство с именем Appliance1 и FQDN сервера-посредника ms.vdomain.com или устройство с именем NewAppliance и FQDN сервера-ms1.vdomain.com было зарегистрировано.
    
## <a name="parameters"></a>Параметры
<a name="DetailedDescription"> </a>

|**Параметр**|**Required**|**Тип**|**Описание**|
|:-----|:-----|:-----|:-----|
|SiteName  <br/> |Необязательный  <br/> |System.String  <br/> |Имя сайта STN, на котором зарегистрировано устройство. Значение по умолчанию — SiteName в CloudConnector.ini файле.  <br/> |
|ApplianceName  <br/> |Необязательный  <br/> |System.String  <br/> |Имя текущего устройства. Значение по умолчанию — имя компьютера хост-сервера.  <br/> |
|Локальный  <br/> |Необязательный  <br/> |System.Management.Automation.SwitchParameter  <br/> |Проверьте конфигурации регистрации локально, не подключаясь к конфигурации интерактивного клиента.  <br/> |
   
## <a name="input-types"></a>Типы входных данных
<a name="InputTypes"> </a>

Нет. Этот Register-CcAppliance не принимает конвейерные входные данные.
  
## <a name="return-types"></a>Типы возвращаемых данных
<a name="ReturnTypes"> </a>

Нет
  
## <a name="see-also"></a>См. также
<a name="ReturnTypes"> </a>

[Unregister-CcAppliance](unregister-ccappliance.md)
  
[Publish-CcAppliance](publish-ccappliance.md)
  
[Install-CcAppliance](install-ccappliance.md)
  
[Uninstall-CcAppliance](uninstall-ccappliance.md)
  

