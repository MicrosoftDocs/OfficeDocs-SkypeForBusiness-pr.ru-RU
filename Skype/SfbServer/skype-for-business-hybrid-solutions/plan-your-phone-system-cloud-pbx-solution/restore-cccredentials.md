---
title: Restore-CcCredentials
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aeca610b-db0a-45cf-95b9-ae9a6bbccb45
description: Командлет Restore CC-Credential восстанавливает все учетные данные текущего развертывания Skype для бизнеса Cloud Connector Edition.
ms.openlocfilehash: efa1bcda9af6abccd2ced0faf1e772e779a4483f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34287085"
---
# <a name="restore-cccredentials"></a>Restore-CcCredentials
 
Командлет Restore CC-Credential восстанавливает все учетные данные текущего развертывания Skype для бизнеса Cloud Connector Edition. 
  
Этот командлет применим к Skype для бизнеса Cloud Connector Edition 2,1.
  
```
Restore-CcCredentials 
```

## <a name="detailed-description"></a>Подробное описание

Командлет Restore-Кккредентиалс удаляет все учетные данные и предлагает вам повторно ввести все учетные данные, которые используются для текущего развертывания облачного соединителя Skype для бизнеса.
  
## <a name="parameters"></a>Параметры

Нет
  
## <a name="input-types"></a>Типы входных данных

Отсутствуют. Командлет Restore-Кккредентиалс не поддерживает конвейерный вход.
  
## <a name="return-types"></a>Типы возвращаемых данных

Нет. 
  
## <a name="example"></a>Пример

В следующем примере восстанавливаются все учетные данные для текущего развертывания облачного соединителя:
  
```
    PS C:\>Restore-CcCredentials
```

## <a name="see-also"></a>См. также

[Get-CcCredential](get-cccredential.md)
  
[Set-CcCredential](set-cccredential.md)
  

