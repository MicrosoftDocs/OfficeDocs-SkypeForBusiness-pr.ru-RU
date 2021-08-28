---
title: Export-CcConfiguration
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: e3775bd6-682c-4f62-aafc-974fe3a65c61
description: Экспортирует конфигурацию Skype для бизнеса Cloud Connector Edition в локальный файл на Skype для бизнеса Cloud Connector Edition сервере.
ms.openlocfilehash: b2b3ea0171b68701b47b8ae2ed239f2e0495855b
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/26/2021
ms.locfileid: "58625011"
---
# <a name="export-ccconfiguration"></a>Export-CcConfiguration
 
Экспортирует конфигурацию Skype для бизнеса Cloud Connector Edition в локальный файл на Skype для бизнеса Cloud Connector Edition сервере.
  
```powershell
Export-CcConfiguration [-Path] <String> [<CommonParameters>]
```

## <a name="examples"></a>Примеры
<a name="Examples"> </a>

### <a name="example-1"></a>Пример 1

В следующем примере параметр Path определяется как полный путь к файлу и экспортирует конфигурации в этот файл.
  
```powershell
Export-CcConfiguration -Path "C:\test\CloudConnector.ini" 
```

## <a name="detailed-description"></a>Подробное описание
<a name="Examples"> </a>

Этот Export-CcConfiguration позволяет сохранить конфигурацию облачного соединителя в файл на выбранном пути. Эта команда была представлена в версии 2.0 Cloud Connector Edition.
  
## <a name="parameters"></a>Параметры
<a name="Examples"> </a>

|**Параметр**|**Required**|**Тип**|**Описание**|
|:-----|:-----|:-----|:-----|
|Путь  <br/> |Обязательный  <br/> |System.String  <br/> |Полный путь к файлу, в котором будут храниться конфигурации облачного соединитела.  <br/> |
   
## <a name="input-types"></a>Типы входных данных
<a name="Examples"> </a>

Нет. В Export-CcConfiguration не принимается конвейерный ввод.
  
## <a name="return-types"></a>Типы возвращаемых данных
<a name="Examples"> </a>

Нет.
  
## <a name="see-also"></a>См. также
<a name="Examples"> </a>

Import-CcConfiguration
  

