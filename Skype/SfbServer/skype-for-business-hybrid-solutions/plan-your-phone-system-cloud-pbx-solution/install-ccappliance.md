---
title: Install-CcAppliance
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 385453cd-3a96-4837-8bb4-513aa97a256b
description: Командлет Install-CcAppliance устанавливает на сервер узла устройство Skype для бизнеса Cloud Connector Edition, включая виртуальные машины Active Directory, центрального хранилища управления, сервера-посредника и пограничного сервера.
ms.openlocfilehash: a3717e510ccadaa930d50573f067888780f7dce5
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="install-ccappliance"></a>Install-CcAppliance
 
Командлет Install-CcAppliance устанавливает на сервер узла устройство Skype для бизнеса Cloud Connector Edition, включая виртуальные машины Active Directory, центрального хранилища управления, сервера-посредника и пограничного сервера. 
  
```
Install-CcAppliance [-Steps <array>] [-SkipExistingObjects] [-Upgrade] [-UpdateAllCredentials] [<CommonParameters>]
Install-CcAppliance [-Steps <array>] [-PrepareOnly]  [<CommonParameters>]
Install-CcAppliance [-ShowStepsOnly]  [<CommonParameters>]

```

## <a name="examples"></a>Примеры
<a name="Examples"> </a>

### <a name="example-1"></a>Пример 1

Следующий пример устанавливает новый соединитель облачных устройства на хост-сервера:
  
```
Install-CcAppliance
```

### <a name="example-2"></a>Пример 2

В следующем примере соединитель облачных обновляется до последней версии:
  
```
Install-CcAppliance -Upgrade
```

### <a name="example-3"></a>Пример 3

В следующем примере показано удаление всех учетных данных облачных соединителя, кэшируются на хост-сервера, выдает запрос пользователю для указания еще раз, все учетные данные и устанавливает соединителя облачных:
  
```
Install-CcAppliance -UpdateAllCredentials
```

### <a name="example-4"></a>Пример 4

В следующем примере в консоли PowerShell выводятся все шаги по развертыванию:
  
```
Install-CcAppliance -ShowStepsOnly
```

Параметр -ShowStepsOnly используется только для устранения неполадок.
  
### <a name="example-5"></a>Пример 5

В следующем примере создаются файлы конфигурации для каждого шага развертывания на сервере узла. Будут сохранены файлы конфигурации \<ApplianceRoot\>\Instances\\< версии\>-default\ExportedConfig папку на хост-сервера:
  
```
Install-CcAppliance -PrepareOnly
```

Чтобы определить корневой каталог устройства, выполните командлет Get-CcApplianceDirectory. 
  
### <a name="example-6"></a>Пример 6

В следующем примере Cloud Connector выполняет шаги развертывания 1, 2 и 3, создавая виртуальные коммутаторы и виртуальные машины Active Directory, после чего устанавливая службу домена на сервер Active Directory. Если шаг уже был выполнен ранее, он пропускается:
  
```
Install-CcAppliance -Steps @(1,2,3) -SkipExistingObjects
```

Вместе с параметром Steps необходимо использовать параметр SkipExistingObjects.
  
> [!NOTE]
> Параметр Steps используется только для устранения неполадок. Не используйте этот параметр для развертывания нового или обновления работающего устройства. 
  
Чтобы определить шаги развертывания, выполните следующий командлет:
  
Install-CcAppliance - ShowStepsOnly
  
## <a name="detailed-description"></a>Подробное описание
<a name="DetailedDescription"> </a>

Командлет Install-CcAppliance используется для развертывания облака соединитель для нового устройства или для обновления существующего устройства до последней версии.
  
Если у вас есть новые устройства, обязательно ознакомьтесь со сведениями подготовить среду для соединителя облачных сначала, выполните командлет Register-CcAppliance для регистрации устройства и затем используйте командлет Install-CcAppliance. Дополнительные сведения можно [Развернуть один сайт в облаке соединителя](deploy-a-single-site-in-cloud-connector.md) и [развертывания нескольких сайтов в облаке соединителя](deploy-multiple-sites-in-cloud-connector.md). 
  
Если у вас есть существующее развертывание облачных соединителя и необходимо обновить, пожалуйста, следуйте инструкциям в [обновление до новой версии облачных соединителя](upgrade-to-a-new-version-of-cloud-connector.md).
  
## <a name="parameters"></a>Параметры
<a name="DetailedDescription"> </a>

|**Параметр**|**Обязательно**|**Тип**|**Описание**|
|:-----|:-----|:-----|:-----|
|PrepareOnly  <br/> |Необязательно  <br/> |System.Management.Automation.SwitchParameter  <br/> | Создает файлы конфигурации для каждого шага развертывания. Этот параметр используется только для устранения неполадок.  <br/> |
|ShowStepsOnly  <br/> |Необязательно  <br/> |System.Management.Automation.SwitchParameter  <br/> |Отображает только названия шагов развертывания. Этот параметр используется только для устранения неполадок.  <br/> |
|SkipExistingObjects  <br/> |Необязательно  <br/> |System.Management.Automation.SwitchParameter  <br/> |Этот параметр используется вместе с параметром Steps. Этот параметр используется только для устранения неполадок.  <br/> |
|Steps  <br/> |Необязательно  <br/> |System.Array  <br/> |Выполняет шаги развертывания. Этот параметр используется только для устранения неполадок.  <br/> |
|Upgrade  <br/> |Необязательно  <br/> |System.Management.Automation.SwitchParameter  <br/> |Обновляет существующее развертывание Cloud Connector до последней версии.  <br/> |
|UpdateAllCredentials  <br/> |Необязательно  <br/> |System.Management.Automation.SwitchParameter  <br/> |Удаление всех учетных данных облачных соединителя в кэше. Отображает запрос для ввода пользователем новых учетных данных для установки.  <br/> |
   
## <a name="input-types"></a>Типы входных данных
<a name="InputTypes"> </a>

Нет. Командлет Install-CcAppliance не принимает входные данные по конвейеру.
  
## <a name="return-types"></a>Типы возвращаемых данных
<a name="ReturnTypes"> </a>

Нет
  
## <a name="see-also"></a>См. также
<a name="ReturnTypes"> </a>

[Публикация CcAppliance](publish-ccappliance.md)
  
[Register-CcAppliance](register-ccappliance.md)
  
[Отмена регистрации CcAppliance](unregister-ccappliance.md)
  
[Удаление CcAppliance](uninstall-ccappliance.md)
  

