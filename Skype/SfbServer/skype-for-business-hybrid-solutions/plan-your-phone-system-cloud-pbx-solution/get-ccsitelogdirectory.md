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
localization_priority: Normal
ms.assetid: 6625494d-1b63-4d99-a589-c8c69c4addba
description: Командлет Get-CcSiteLogDirectory показывает текущий каталог, в котором хранятся журналы уровня сайта для Skype для бизнеса Cloud Connector Edition.
ms.openlocfilehash: bc47c2ea2d81e70538305daa98f97a35cf3d9e0a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34287288"
---
# <a name="get-ccsitelogdirectory"></a>Get-CcSiteLogDirectory
 
Командлет Get-CcSiteLogDirectory показывает текущий каталог, в котором хранятся журналы уровня сайта для Skype для бизнеса Cloud Connector Edition. 
  
Этот командлет применяется к версии Skype для бизнеса Cloud Connector Edition 1.4.1, 1.4.2.
  
```
Get-CcSiteLogDirectory
```

## <a name="parameters"></a>Параметры

Нет
  
## <a name="examples"></a>Примеры
<a name="Examples"> </a>

### <a name="example-1"></a>Пример 1

В следующем примере показана текущая папка, в которой хранятся файлы журнала для сайта облачного соединителя.
  
```
Get-CcSiteLogDirectory
```

## <a name="detailed-description"></a>Подробное описание
<a name="DetailedDescription"> </a>

По умолчанию используется папка\%к:\усерс усерпрофиле%\клаудконнектор\ситерут\логс. Чтобы изменить эту папку, выполните командлет Set-CcSiteDirectory. Отдельный командлет, позволяющий сменить только местоположение папки журналов без изменения каталога сайта, не предусмотрен.
  
## <a name="input-types"></a>Типы входных данных
<a name="InputTypes"> </a>

Нет. Командлет Get-CcSiteLogDirectory не принимает входные данные по конвейеру.
  
## <a name="return-types"></a>Типы возвращаемых данных
<a name="ReturnTypes"> </a>

Команда возвращает путь к файлу.
  
## <a name="see-also"></a>См. также
<a name="ReturnTypes"> </a>

[Set-CcSiteDirectory](set-ccsitedirectory.md)
  

