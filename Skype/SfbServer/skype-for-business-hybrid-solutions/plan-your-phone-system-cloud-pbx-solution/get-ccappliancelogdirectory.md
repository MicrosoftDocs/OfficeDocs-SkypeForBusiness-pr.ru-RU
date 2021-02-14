---
title: Get-CcApplianceLogDirectory
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
ms.assetid: 8f16d8ea-8161-4b07-9c79-d57e786b3e78
description: The Get-CcApplianceLogDirectory shows the current directory where logs for a Skype for Business Cloud Connector Edition appliance are stored.
ms.openlocfilehash: 284846bbc305d76602ae1e2f065fcdd571c9deb2
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41800829"
---
# <a name="get-ccappliancelogdirectory"></a>Get-CcApplianceLogDirectory
 
The Get-CcApplianceLogDirectory shows the current directory where logs for a Skype for Business Cloud Connector Edition appliance are stored.
  
Этот cmdlet применяется к Skype для бизнеса Cloud Connector Edition 1.4.1, 1.4.2.
  
```powershell
Get-CcApplianceLogDirectory
```

## <a name="parameters"></a>Параметры

Нет
  
## <a name="examples"></a>Примеры
<a name="Examples"> </a>

### <a name="example-1"></a>Пример 1

В следующем примере показана текущая папка, в которой хранятся журналы для текущего устройства Cloud Connector:
  
```powershell
Get-CcApplianceLogDirectory
```

## <a name="detailed-description"></a>Подробное описание
<a name="DetailedDescription"> </a>

Этот Get-CcApplianceLogDirectory показывает текущий каталог, в котором хранятся журналы для устройства Cloud Connector. Папка по умолчанию C:\Users \% userprofile%\CloudConnector\ApplianceRoot\Logs. 
  
Вы можете изменить каталог с помощью Set-CcApplianceDirectory управления. 
  
Примечание. Не существует никаких cmdlet, который изменяет только расположение папки журнала без изменения каталога устройства.
  
## <a name="input-types"></a>Типы входных данных
<a name="InputTypes"> </a>

Нет. Этот Get-CcApplianceLogDirectory не принимает конвейерные входные данные.
  
## <a name="return-types"></a>Типы возвращаемых данных
<a name="ReturnTypes"> </a>

Эта команда возвращает путь к файлу.
  
## <a name="see-also"></a>См. также
<a name="ReturnTypes"> </a>

[Set-CcApplianceDirectory](set-ccappliancedirectory.md)
  

