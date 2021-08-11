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
description: Этот Exit-CcUpdate выходит из режима обслуживания обновления на Skype для бизнеса Cloud Connector Edition сервере.
ms.openlocfilehash: d55004f071caa67492d5368e36007d9c3c307b90aabbc33d79d1feeb4aa37356
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2021
ms.locfileid: "54288844"
---
# <a name="exit-ccupdate"></a>Exit-CcUpdate
 
Этот Exit-CcUpdate выходит из режима обслуживания обновления на Skype для бизнеса Cloud Connector Edition сервере. 
  
Этот комлет применяется к Skype для бизнеса Cloud Connector Edition 1.4.1, 1.4.2. 
  
```powershell
Exit-CcUpdate
```

## <a name="parameters"></a>Параметры

Нет
  
## <a name="examples"></a>Примеры
<a name="Examples"> </a>

### <a name="example-1"></a>Пример 1

Следующая команда помещает устройство, на котором он запускается обратно в режим производства: 
  
```powershell
Exit-CcUpdate
```

## <a name="detailed-description"></a>Подробное описание
<a name="DetailedDescription"> </a>

Если у вас есть устройства, которые вы вложили в режим обслуживания, указав Enter-CcUpdate, Exit-CcUpdate будет возвращать их в режим производства. 
  
Дополнительные сведения о вводе приборов в режим обслуживания см. введите-CcUpdate.
  
## <a name="input-types"></a>Типы входных данных
<a name="InputTypes"> </a>

Нет. В Exit-CcUpdate не принимается конвейерный ввод.
  
## <a name="return-types"></a>Типы возвращаемых данных
<a name="ReturnTypes"> </a>

Нет 
  
## <a name="see-also"></a>См. также
<a name="ReturnTypes"> </a>

[Enter-CcUpdate](enter-ccupdate.md)
  

