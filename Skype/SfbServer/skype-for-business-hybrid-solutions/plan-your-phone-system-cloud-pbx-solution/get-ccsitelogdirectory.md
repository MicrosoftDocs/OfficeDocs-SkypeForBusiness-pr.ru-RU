---
title: Get-CcSiteLogDirectory
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/20/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 6625494d-1b63-4d99-a589-c8c69c4addba
description: В Get-CcSiteLogDirectory показан текущий каталог, в котором хранятся журналы уровня Skype для бизнеса Cloud Connector Edition сайта.
ms.openlocfilehash: 65d99093f6390eade15e9783bd286bc438ede23d
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/26/2021
ms.locfileid: "58616365"
---
# <a name="get-ccsitelogdirectory"></a>Get-CcSiteLogDirectory
 
В Get-CcSiteLogDirectory показан текущий каталог, в котором хранятся журналы уровня Skype для бизнеса Cloud Connector Edition сайта. 
  
Этот комлет применяется к Skype для бизнеса Cloud Connector Edition 1.4.1, 1.4.2.
  
```powershell
Get-CcSiteLogDirectory
```

## <a name="parameters"></a>Параметры

Нет
  
## <a name="examples"></a>Примеры
<a name="Examples"> </a>

### <a name="example-1"></a>Пример 1

В следующем примере показана текущая папка, в которой хранятся файлы журнала для сайта Cloud Connector:
  
```powershell
Get-CcSiteLogDirectory
```

## <a name="detailed-description"></a>Подробное описание
<a name="DetailedDescription"> </a>

Папка по умолчанию — C:\Users \% userprofile%\CloudConnector\SiteRoot\Logs. Вы можете изменить папку, заняв Set-CcSiteDirectory. Не существует отдельного cmdlet, который изменяет только расположение папки журнала без изменения каталога сайта.
  
## <a name="input-types"></a>Типы входных данных
<a name="InputTypes"> </a>

Нет. В Get-CcSiteLogDirectory не принимается конвейерный ввод.
  
## <a name="return-types"></a>Типы возвращаемых данных
<a name="ReturnTypes"> </a>

Команда возвращает путь файла.
  
## <a name="see-also"></a>См. также
<a name="ReturnTypes"> </a>

[Set-CcSiteDirectory](set-ccsitedirectory.md)
  

