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
localization_priority: Normal
ms.assetid: 463dce1e-fb60-487d-bcf1-69e7b03ecd14
description: Командлет Exit-CcUpdate обновляет режим обслуживания на сервере узла Skype для бизнеса Cloud Connector Edition.
ms.openlocfilehash: f79023c50e951e6678abdccc29b12cb30a329dfc
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003449"
---
# <a name="exit-ccupdate"></a>Exit-CcUpdate
 
Командлет Exit-CcUpdate обновляет режим обслуживания на сервере узла Skype для бизнеса Cloud Connector Edition. 
  
Этот командлет применяется к версии Skype для бизнеса Cloud Connector Edition 1.4.1, 1.4.2. 
  
```powershell
Exit-CcUpdate
```

## <a name="parameters"></a>Параметры

Нет
  
## <a name="examples"></a>Примеры
<a name="Examples"> </a>

### <a name="example-1"></a>Пример 1

Следующая команда переводит устройство, на котором она выполняется, в рабочий режим: 
  
```powershell
Exit-CcUpdate
```

## <a name="detailed-description"></a>Подробное описание
<a name="DetailedDescription"> </a>

Если вы перевели какие-либо устройства в режим обслуживания с помощью командлета Enter-CcUpdate, командлет Exit-CcUpdate позволит вернуть их в рабочий режим. 
  
Дополнительные сведения о переводе устройств в режим обслуживания см. в описании командлета Enter-CcUpdate.
  
## <a name="input-types"></a>Типы входных данных
<a name="InputTypes"> </a>

Нет. Командлет Exit-CcUpdate не принимает входные данные по конвейеру.
  
## <a name="return-types"></a>Типы возвращаемых данных
<a name="ReturnTypes"> </a>

Отсутствуют 
  
## <a name="see-also"></a>См. также
<a name="ReturnTypes"> </a>

[Enter-CcUpdate](enter-ccupdate.md)
  

