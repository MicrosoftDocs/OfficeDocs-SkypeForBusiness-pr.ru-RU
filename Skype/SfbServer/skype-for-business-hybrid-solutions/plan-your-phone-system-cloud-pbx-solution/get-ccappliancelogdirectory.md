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
description: В Get-CcApplianceLogDirectory показан текущий каталог, в котором хранятся журналы Skype для бизнеса Cloud Connector Edition устройства.
ms.openlocfilehash: 75f3ba3a5de5198456e053bd51ef567df1a0ae43461e9888e87294d3af406288
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2021
ms.locfileid: "54318662"
---
# <a name="get-ccappliancelogdirectory"></a>Get-CcApplianceLogDirectory
 
В Get-CcApplianceLogDirectory показан текущий каталог, в котором хранятся журналы Skype для бизнеса Cloud Connector Edition устройства.
  
Этот комлет применяется к Skype для бизнеса Cloud Connector Edition 1.4.1, 1.4.2.
  
```powershell
Get-CcApplianceLogDirectory
```

## <a name="parameters"></a>Параметры

Нет
  
## <a name="examples"></a>Примеры
<a name="Examples"> </a>

### <a name="example-1"></a>Пример 1

В следующем примере показана текущая папка, в которой хранятся журналы для текущего устройства облачного соединитетеля:
  
```powershell
Get-CcApplianceLogDirectory
```

## <a name="detailed-description"></a>Подробное описание
<a name="DetailedDescription"> </a>

В Get-CcApplianceLogDirectory показан текущий каталог, в котором хранятся журналы для устройства облачного соединителя. Папка по умолчанию — C:\Users \% userprofile%\CloudConnector\ApplianceRoot\Logs. 
  
Каталог можно изменить с помощью Set-CcApplianceDirectory. 
  
Примечание. Не существует комлета, который изменяет только расположение папки журнала без изменения каталога приборов.
  
## <a name="input-types"></a>Типы входных данных
<a name="InputTypes"> </a>

Нет. В Get-CcApplianceLogDirectory не принимается конвейерный ввод.
  
## <a name="return-types"></a>Типы возвращаемых данных
<a name="ReturnTypes"> </a>

Эта команда возвращает путь файла.
  
## <a name="see-also"></a>См. также
<a name="ReturnTypes"> </a>

[Set-CcApplianceDirectory](set-ccappliancedirectory.md)
  

