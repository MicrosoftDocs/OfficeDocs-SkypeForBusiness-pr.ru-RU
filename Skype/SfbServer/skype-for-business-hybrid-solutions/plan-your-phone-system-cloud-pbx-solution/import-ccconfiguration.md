---
title: Импорт CcConfiguration
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 10/11/2017
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 461361a0-9aa9-469d-ace0-dc70b95cd4a3
description: Импортирует Скайп для конфигурации соединителя Cloud Business Edition из локального файла для соединителя облачных хост-сервера.
ms.openlocfilehash: 46f4099258ce4090fa23ec980801e55f7300895f
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="import-ccconfiguration"></a>Импорт CcConfiguration
 
Импортирует Скайп для конфигурации соединителя Cloud Business Edition из локального файла для соединителя облачных хост-сервера.
  
```

Import-CcConfiguration [-Force] [<CommonParameters>]
```

## <a name="examples"></a>Примеры
<a name="Examples"> </a>

### <a name="example-1"></a>Пример 1

В следующем примере копируется CloudConnector.ini из каталога appliance экземпляра соединителя Cloud %SystemDrive%\ProgramData\CloudConnector каталог:
  
```
Import-CcConfiguration
```

## <a name="detailed-description"></a>Подробное описание
<a name="Examples"> </a>

Этот командлет копирует CloudConnector.ini из каталога appliance устройства соединителя облака в каталог %SystemDrive%\ProgramData\CloudConnector. С помощью командлета Set-CcApplianceDirectory указан каталог устройства. Командлет будет перезаписать существующий файл в папке % SystemDrive%\ProgramData\CloudConnector. Эта команда применяется к Edition соединителя облачных версии 2.0.1 и более поздних версий.
  
## <a name="parameters"></a>Параметры
<a name="Examples"> </a>

|**Параметр**|**Обязательно**|**Тип**|**Описание**|
|:-----|:-----|:-----|:-----|
|Force  <br/> | Необязательно  <br/> |System.Management.Automation.SwitchParameter  <br/> |Перезапись существующего файла в %SystemDrive%\ProgramData\CloudConnector без уведомления.  <br/> |
   
## <a name="input-types"></a>Типы входных данных
<a name="Examples"> </a>

Нет. Командлет Import-CcConfiguration не принимает входные данные.
  
## <a name="return-types"></a>Типы возвращаемых данных
<a name="Examples"> </a>

Нет.
  
## <a name="see-also"></a>См. также
<a name="Examples"> </a>

Export-CcConfiguration
  

