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
ms.localizationpriority: medium
ms.assetid: 461361a0-9aa9-469d-ace0-dc70b95cd4a3
description: Импортирует конфигурацию Skype для бизнеса Cloud Connector Edition из локального файла на сервер хост-сервера облачного соединитела.
ms.openlocfilehash: efcc73fd5883c61753688923d44c01e10fc74ea8
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/26/2021
ms.locfileid: "58623407"
---
# <a name="import-ccconfiguration"></a>Import-CcConfiguration
 
Импортирует конфигурацию Skype для бизнеса Cloud Connector Edition из локального файла на сервер хост-сервера облачного соединитела.
  
```powershell
Import-CcConfiguration [-Force] [<CommonParameters>]
```

## <a name="examples"></a>Примеры
<a name="Examples"> </a>

### <a name="example-1"></a>Пример 1

В следующем примере CloudConnector.ini каталога устройств экземпляра облачного соединитетеля в каталог %SystemDrive%\ProgramData\CloudConnector:
  
```powershell
Import-CcConfiguration
```

## <a name="detailed-description"></a>Подробное описание
<a name="Examples"> </a>

Этот комлет копирует CloudConnector.ini из каталога устройства устройства облачного соединителя в каталог %SystemDrive%\ProgramData\CloudConnector. Каталог приборов определяется с помощью Set-CcApplianceDirectory. В кодлете будет перезаписываться любой существующий файл в %SystemDrive%\ProgramData\CloudConnector. Эта команда применяется к версии Cloud Connector Edition 2.0.1 и более поздней версии.
  
## <a name="parameters"></a>Параметры
<a name="Examples"> </a>

|**Параметр**|**Required**|**Тип**|**Описание**|
|:-----|:-----|:-----|:-----|
|Force  <br/> |Необязательный  <br/> |System.Management.Automation.SwitchParameter  <br/> |Перезаписывать существующий файл в %SystemDrive%\ProgramData\CloudConnector без уведомления.  <br/> |
   
## <a name="input-types"></a>Типы входных данных
<a name="Examples"> </a>

Нет. В Import-CcConfiguration не принимается конвейерный ввод.
  
## <a name="return-types"></a>Типы возвращаемых данных
<a name="Examples"> </a>

Нет.
  
## <a name="see-also"></a>См. также
<a name="Examples"> </a>

Export-CcConfiguration
  

