---
title: Exit-CcUpdate
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
ms.assetid: 463dce1e-fb60-487d-bcf1-69e7b03ecd14
description: The Exit-CcUpdate cmdlet exits update maintenance mode on the Skype for Business Cloud Connector Edition host server.
ms.openlocfilehash: 315d6b7dccb6708901128bf8faa29a60f712e833
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41801769"
---
# <a name="exit-ccupdate"></a>Exit-CcUpdate
 
The Exit-CcUpdate cmdlet exits update maintenance mode on the Skype for Business Cloud Connector Edition host server. 
  
Этот cmdlet применяется к Skype для бизнеса Cloud Connector Edition 1.4.1, 1.4.2. 
  
```powershell
Exit-CcUpdate
```

## <a name="parameters"></a>Параметры

Нет
  
## <a name="examples"></a>Примеры
<a name="Examples"> </a>

### <a name="example-1"></a>Пример 1

Следующая команда помещает устройство, на котором оно выполняется, обратно в производственный режим: 
  
```powershell
Exit-CcUpdate
```

## <a name="detailed-description"></a>Подробное описание
<a name="DetailedDescription"> </a>

Если у вас есть устройства, которые были поставлены в режим обслуживания, указав Enter-CcUpdate, Exit-CcUpdate снова в режиме эксплуатации. 
  
Дополнительные сведения о переводить устройства в режим обслуживания см. в enter-CcUpdate.
  
## <a name="input-types"></a>Типы входных данных
<a name="InputTypes"> </a>

Нет. Этот Exit-CcUpdate не принимает конвейерные входные данные.
  
## <a name="return-types"></a>Типы возвращаемых данных
<a name="ReturnTypes"> </a>

Нет 
  
## <a name="see-also"></a>См. также
<a name="ReturnTypes"> </a>

[Enter-CcUpdate](enter-ccupdate.md)
  

