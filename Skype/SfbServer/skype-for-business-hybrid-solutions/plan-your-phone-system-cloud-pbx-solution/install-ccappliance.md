---
title: Install-CcAppliance
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
ms.assetid: 385453cd-3a96-4837-8bb4-513aa97a256b
description: Этот Install-CcAppliance устанавливает на сервере хост-сервера устройство Skype для бизнеса Cloud Connector Edition, в том числе виртуальные машины AD, центрального банка управления, сервера-посредника и сервера-посредника.
ms.openlocfilehash: fe1fab785e2681614f27035714b6ddead22b8707
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41799879"
---
# <a name="install-ccappliance"></a>Install-CcAppliance
 
Этот Install-CcAppliance устанавливает на сервере хост-сервера устройство Skype для бизнеса Cloud Connector Edition, в том числе виртуальные машины AD, центрального банка управления, сервера-посредника и сервера-посредника. 
  
```powershell
Install-CcAppliance [-Steps <array>] [-SkipExistingObjects] [-Upgrade] [-UpdateAllCredentials] [<CommonParameters>]
Install-CcAppliance [-Steps <array>] [-PrepareOnly]  [<CommonParameters>]
Install-CcAppliance [-ShowStepsOnly]  [<CommonParameters>]
```

## <a name="examples"></a>Примеры
<a name="Examples"> </a>

### <a name="example-1"></a>Пример 1

В следующем примере на сервере хост-сервера устанавливается новое устройство Cloud Connector:
  
```powershell
Install-CcAppliance
```

### <a name="example-2"></a>Пример 2

В следующем примере Cloud Connector обновляется до последней версии:
  
```powershell
Install-CcAppliance -Upgrade
```

### <a name="example-3"></a>Пример 3

В следующем примере удаляются все учетные данные Cloud Connector, кэшные на сервере, пользователь снова указывает все учетные данные, а затем устанавливает Cloud Connector:
  
```powershell
Install-CcAppliance -UpdateAllCredentials
```

### <a name="example-4"></a>Пример 4

В следующем примере показаны все этапы развертывания в консоли PowerShell:
  
```powershell
Install-CcAppliance -ShowStepsOnly
```

Параметр -ShowStepsOnly можно только для устранения неполадок.
  
### <a name="example-5"></a>Пример 5

В следующем примере создаются файлы конфигурации для каждого шага развертывания на сервере размещения. Файлы конфигурации сохраняются в папке \< ApplianceRoot \> \Instances \\<Version \> -default\ExportedConfig на сервере хост-сервера:
  
```powershell
Install-CcAppliance -PrepareOnly
```

Чтобы определить корень устройства, запустите Get-CcApplianceDirectory устройства. 
  
### <a name="example-6"></a>Пример 6

В следующем примере Cloud Connector выполняет шаги развертывания 1, 2 и 3 для создания виртуальных коммутаторов, создания виртуальной машины AD и установки службы домена на сервере AD. Если шаг уже выполнен, он пропускает этот шаг:
  
```powershell
Install-CcAppliance -Steps @(1,2,3) -SkipExistingObjects
```

Параметр SkipExistingObjects необходимо использовать вместе с параметром Steps.
  
> [!NOTE]
> Параметр Steps предназначен только для устранения неполадок. Не используйте этот параметр для развертывания устройства или обновления устройства, которое находится в службе. 
  
Чтобы определить этапы развертывания, запустите следующую команду:
  
Install-CcAppliance -ShowStepsOnly
  
## <a name="detailed-description"></a>Подробное описание
<a name="DetailedDescription"> </a>

Этот Install-CcAppliance используется для развертывания Cloud Connector на новом устройстве или обновления существующего устройства до последней версии.
  
Если у вас новое устройство, обязательно прочитайте статью "Подготовка среды для Cloud Connector", запустите Register-CcAppliance для регистрации устройства, а затем запустите Install-CcAppliance- Дополнительные сведения см. в сведениях о развертывании одного сайта в [Cloud Connector](deploy-a-single-site-in-cloud-connector.md) и развертывании нескольких сайтов [в Cloud Connector.](deploy-multiple-sites-in-cloud-connector.md) 
  
Если у вас есть существующее развертывание Cloud Connector и вы хотите обновить его, следуйте инструкциям в окне "Обновление до новой версии [Cloud Connector".](upgrade-to-a-new-version-of-cloud-connector.md)
  
## <a name="parameters"></a>Параметры
<a name="DetailedDescription"> </a>

|**Параметр**|**Required**|**Тип**|**Описание**|
|:-----|:-----|:-----|:-----|
|PrepareOnly  <br/> |Необязательный  <br/> |System.Management.Automation.SwitchParameter  <br/> | Создание файлов конфигурации для каждого шага развертывания. Этот параметр только для устранения неполадок. <br/> |
|ShowStepsOnly  <br/> |Необязательный  <br/> |System.Management.Automation.SwitchParameter  <br/> |Отображает только имена этапов развертывания. Этот параметр только для устранения неполадок.  <br/> |
|SkipExistingObjects  <br/> |Необязательный  <br/> |System.Management.Automation.SwitchParameter  <br/> |Этот параметр необходимо использовать вместе с параметром Steps. Этот параметр только для устранения неполадок.  <br/> |
|Действия  <br/> |Необязательна  <br/> |System.Array  <br/> |Запустите этапы развертывания. Этот параметр только для устранения неполадок.  <br/> |
|Обновление  <br/> |Необязательный  <br/> |System.Management.Automation.SwitchParameter  <br/> |Обновите существующий Cloud Connector до последней версии.  <br/> |
|UpdateAllCredentials  <br/> |Необязательный  <br/> |System.Management.Automation.SwitchParameter  <br/> |Удалите все учетные данные Cloud Connector в кэше. Запрос пользователя на указание новых учетных данных для установки.  <br/> |
   
## <a name="input-types"></a>Типы входных данных
<a name="InputTypes"> </a>

Нет. Этот Install-CcAppliance не принимает конвейерные входные данные.
  
## <a name="return-types"></a>Типы возвращаемых данных
<a name="ReturnTypes"> </a>

Нет
  
## <a name="see-also"></a>См. также
<a name="ReturnTypes"> </a>

[Publish-CcAppliance](publish-ccappliance.md)
  
[Register-CcAppliance](register-ccappliance.md)
  
[Unregister-CcAppliance](unregister-ccappliance.md)
  
[Uninstall-CcAppliance](uninstall-ccappliance.md)
  

