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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: aeca610b-db0a-45cf-95b9-ae9a6bbccb45
description: С помощью Cc-Credentials восстановления восстанавливаются все учетные данные текущего развертывания Skype для бизнеса Cloud Connector Edition.
ms.openlocfilehash: b2cd35b284bcd7e49aabbaa3055c397915565d09
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824245"
---
# <a name="restore-cccredentials"></a>Restore-CcCredentials
 
С помощью Cc-Credentials восстановления восстанавливаются все учетные данные текущего развертывания Skype для бизнеса Cloud Connector Edition. 
  
Этот cmdlet применяется к Skype для бизнеса Cloud Connector Edition 2.1.
  
```powershell
Restore-CcCredentials 
```

## <a name="detailed-description"></a>Подробное описание

Этот Restore-CcCredentials очищает все учетные данные и вам будет предложено повторно ввести все учетные данные, используемые для текущего развертывания Skype для бизнеса Cloud Connector.
  
## <a name="parameters"></a>Параметры

Нет
  
## <a name="input-types"></a>Типы входных данных

Нет. Этот Restore-CcCredentials не принимает конвейерные входные данные.
  
## <a name="return-types"></a>Типы возвращаемых данных

Нет.
  
## <a name="example"></a>Пример

В следующем примере восстанавливаются все учетные данные текущего развертывания Cloud Connector:
  
```powershell
    PS C:\>Restore-CcCredentials
```

## <a name="see-also"></a>См. также

[Get-CcCredential](get-cccredential.md)
  
[Set-CcCredential](set-cccredential.md)
  

