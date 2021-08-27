---
title: Set-CcApplianceDirectory
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/21/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 6da93ddb-ca99-4b5d-9b33-3d70659730b2
description: Этот Set-CcApplianceDirectory задает рабочий каталог на сервере Skype для бизнеса Cloud Connector Edition сервере. Все файлы развертывания хранятся в этом каталоге.
ms.openlocfilehash: 0f64fbb52cd12020104e98051564379d1fbc4985
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/26/2021
ms.locfileid: "58617675"
---
# <a name="set-ccappliancedirectory"></a>Set-CcApplianceDirectory
 
Этот Set-CcApplianceDirectory задает рабочий каталог на сервере Skype для бизнеса Cloud Connector Edition сервере. Все файлы развертывания хранятся в этом каталоге.
  
```powershell
Set-CcApplianceDirectory[[-Path] <string>]
```

## <a name="examples"></a>Примеры
<a name="Examples"> </a>

### <a name="example-1"></a>Пример 1

В следующем примере рабочий каталог на хост-сервере задает c:\cloudconnector\applianceroot:
  
```powershell
Set-CcApplianceDirectory -Path "c:\cloudconnector\applianceroot"
```

## <a name="parameters"></a>Параметры
<a name="Examples"> </a>

|**Параметр**|**Required**|**Тип**|**Описание**|
|:-----|:-----|:-----|:-----|
| Путь <br/> | Обязательный <br/> |System.String  <br/> | Указывает путь, в котором хранятся все файлы развертывания. <br/> |
   
## <a name="input-types"></a>Типы входных данных
<a name="InputTypes"> </a>

Нет. В Set-CcApplianceDirectory не принимается конвейерный ввод.
  
## <a name="return-types"></a>Типы возвращаемых данных
<a name="ReturnTypes"> </a>

Нет
  
## <a name="see-also"></a>См. также
<a name="ReturnTypes"> </a>

Нет
  

