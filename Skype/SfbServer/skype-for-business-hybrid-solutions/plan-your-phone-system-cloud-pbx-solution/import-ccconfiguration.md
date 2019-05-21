---
title: Import-CcConfiguration
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 10/11/2017
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 461361a0-9aa9-469d-ace0-dc70b95cd4a3
description: Импорт конфигурации облачного соединителя Skype для бизнеса из локального файла на хост-сервер облачного соединителя.
ms.openlocfilehash: 3e165250b5158513aa683770d5eb1768c0e1e29c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34287281"
---
# <a name="import-ccconfiguration"></a>Import-CcConfiguration
 
Импорт конфигурации облачного соединителя Skype для бизнеса из локального файла на хост-сервер облачного соединителя.
  
```
Import-CcConfiguration [-Force] [<CommonParameters>]
```

## <a name="examples"></a>Примеры
<a name="Examples"> </a>

### <a name="example-1"></a>Пример 1

В следующем примере копируется Клаудконнектор. ini из каталога устройства в экземпляре облачного соединителя в каталог%Системдриве%\програмдата\клаудконнектор:
  
```
Import-CcConfiguration
```

## <a name="detailed-description"></a>Подробное описание
<a name="Examples"> </a>

Этот командлет копирует Клаудконнектор. ini из каталога управляющего устройства облачного соединителя в каталог%Системдриве%\програмдата\клаудконнектор. Каталог Appliance (устройство) задается с помощью командлета Set-Ккапплианцедиректори. Командлет перезапишет существующий файл в%Системдриве%\програмдата\клаудконнектор. Эта команда применима к Cloud Connector Edition версии 2.0.1 и более поздних версий.
  
## <a name="parameters"></a>Параметры
<a name="Examples"> </a>

|**Параметр**|**Обязательно**|**Тип**|**Описание**|
|:-----|:-----|:-----|:-----|
|Force  <br/> |Необязательно  <br/> |System.Management.Automation.SwitchParameter  <br/> |Перезаписать существующий файл в%Системдриве%\програмдата\клаудконнектор без уведомления.  <br/> |
   
## <a name="input-types"></a>Типы входных данных
<a name="Examples"> </a>

Нет. Командлет Import-Ккконфигуратион не поддерживает конвейерные входные данные.
  
## <a name="return-types"></a>Типы возвращаемых данных
<a name="Examples"> </a>

Нет.
  
## <a name="see-also"></a>См. также
<a name="Examples"> </a>

Export-CcConfiguration
  

