---
title: Enter-CcUpdate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
ms.date: 3/31/2017
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 330367f2-22b0-43e3-b8fb-3e0d2e3b330e
description: The Enter-CcUpdate cmdlet prepares the Skype for Business Cloud Connector Edition host server for the update process by putting it in maintenance mode. Устройство немедленно останавливает все службы, завершая все текущие вызовы и отклоняет все новые вызовы.
ms.openlocfilehash: 25d2fbc56bd4de6a08985de18c178d5a8f993492
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802179"
---
# <a name="enter-ccupdate"></a>Enter-CcUpdate

The Enter-CcUpdate cmdlet prepares the Skype for Business Cloud Connector Edition host server for the update process by putting it in maintenance mode. Устройство немедленно останавливает все службы, завершая все текущие вызовы и отклоняет все новые вызовы.
  
```powershell
Enter-CcUpdate
```

## <a name="parameters"></a>Параметры

Нет
  
## <a name="examples"></a>Примеры
<a name="Examples"> </a>

### <a name="example-1"></a>Пример 1

В следующем примере устройство подготавливается к процессу обновления, перейдя в режим обслуживания:
  
```powershell
Enter-CcUpdate 
```

## <a name="detailed-description"></a>Подробное описание
<a name="DetailedDescription"> </a>

Этот Enter-CcUpdate немедленно остановит все службы, завершив все текущие вызовы, и устройство отклоняет все новые вызовы, которые передаются на другие производственные устройства. Необходимо убедиться, что на остальных производственных устройствах достаточно емкости для обработки вызовов с устройства, которое вы хотите обновить.
  
Режим обслуживания полезен, если на вашем устройстве включено автоматическое обновление, например, и Корпорация Майкрософт выпускает критическое обновление. Режим обслуживания также полезен, если вы решили отключить автоматические обновления, но вы выполняете обновления вручную на согласованной основе.
  
После установки обновлений устройство можно вернуть в производственный режим с помощью Exit-CcUpdate управления.
  
> [!NOTE]
> Если вы решили вручную обновить устройство Cloud Connector, вам потребуется обновить его в течение 60 дней после того, как корпорация Майкрософт выпустит следующую версию. Корпорация Майкрософт поддерживает ранее выпущенную версию Cloud Connector в течение 60 дней после выпуска новой версии 
  
## <a name="input-types"></a>Типы входных данных
<a name="InputTypes"> </a>

Нет. Этот Enter-CCUpdate не принимает конвейерные входные данные.
  
## <a name="return-types"></a>Типы возвращаемых данных
<a name="ReturnTypes"> </a>

Нет 
  
## <a name="see-also"></a>См. также
<a name="ReturnTypes"> </a>

[Exit-CcUpdate](exit-ccupdate.md)
  

