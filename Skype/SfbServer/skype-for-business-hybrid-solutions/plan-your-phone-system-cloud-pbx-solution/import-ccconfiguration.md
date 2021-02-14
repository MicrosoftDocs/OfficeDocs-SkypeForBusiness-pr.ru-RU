---
title: Import-CcConfiguration
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 10/11/2017
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 461361a0-9aa9-469d-ace0-dc70b95cd4a3
description: Импортирует конфигурацию Skype для бизнеса Cloud Connector Edition из локального файла на хост-сервер Cloud Connector.
ms.openlocfilehash: 626ba52d4d67f99dd67d3d1f91d26d6e6d03f95e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41799859"
---
# <a name="import-ccconfiguration"></a>Import-CcConfiguration
 
Импортирует конфигурацию Skype для бизнеса Cloud Connector Edition из локального файла на хост-сервер Cloud Connector.
  
```powershell
Import-CcConfiguration [-Force] [<CommonParameters>]
```

## <a name="examples"></a>Примеры
<a name="Examples"> </a>

### <a name="example-1"></a>Пример 1

В следующем примере CloudConnector.ini из каталога устройства экземпляра Cloud Connector в каталог %SystemDrive%\ProgramData\CloudConnector:
  
```powershell
Import-CcConfiguration
```

## <a name="detailed-description"></a>Подробное описание
<a name="Examples"> </a>

Этот cmdlet копирует CloudConnector.ini из каталога устройства устройства Cloud Connector в каталог %SystemDrive%\ProgramData\CloudConnector. Каталог устройства указывается с помощью Set-CcApplianceDirectory устройства. Он перезапишет существующий файл в папке %SystemDrive%\ProgramData\CloudConnector. Эта команда применяется к Cloud Connector Edition версии 2.0.1 и более поздних версий.
  
## <a name="parameters"></a>Параметры
<a name="Examples"> </a>

|**Параметр**|**Required**|**Тип**|**Описание**|
|:-----|:-----|:-----|:-----|
|Force  <br/> |Необязательный  <br/> |System.Management.Automation.SwitchParameter  <br/> |Перезаписать существующий файл в папке %SystemDrive%\ProgramData\CloudConnector без уведомления.  <br/> |
   
## <a name="input-types"></a>Типы входных данных
<a name="Examples"> </a>

Нет. Этот Import-CcConfiguration не принимает конвейерные входные данные.
  
## <a name="return-types"></a>Типы возвращаемых данных
<a name="Examples"> </a>

Нет.
  
## <a name="see-also"></a>См. также
<a name="Examples"> </a>

Export-CcConfiguration
  

