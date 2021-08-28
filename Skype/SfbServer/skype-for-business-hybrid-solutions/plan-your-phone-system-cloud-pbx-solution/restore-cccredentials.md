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
ms.localizationpriority: medium
ms.assetid: aeca610b-db0a-45cf-95b9-ae9a6bbccb45
description: В Cc-Credentials восстановлены все учетные данные текущего Skype для бизнеса Cloud Connector Edition развертывания.
ms.openlocfilehash: 050c4265bff7673a7db620ff41a56a2735d6b4a7
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/26/2021
ms.locfileid: "58588441"
---
# <a name="restore-cccredentials"></a>Restore-CcCredentials
 
В Cc-Credentials восстановлены все учетные данные текущего Skype для бизнеса Cloud Connector Edition развертывания. 
  
Этот комлет применяется к Skype для бизнеса Cloud Connector Edition 2.1.
  
```powershell
Restore-CcCredentials 
```

## <a name="detailed-description"></a>Подробное описание

Этот Restore-CcCredentials очищает все учетные данные и побуждает повторно вводить все учетные данные, используемые для текущего развертывания Skype для бизнеса cloud Connector.
  
## <a name="parameters"></a>Параметры

Нет
  
## <a name="input-types"></a>Типы входных данных

Нет. В Restore-CcCredentials не принимается конвейерный ввод.
  
## <a name="return-types"></a>Типы возвращаемых данных

Нет.
  
## <a name="example"></a>Пример

В следующем примере восстанавливаются все учетные данные текущего развертывания облачного соединитела:
  
```powershell
    PS C:\>Restore-CcCredentials
```

## <a name="see-also"></a>Дополнительные материалы

[Get-CcCredential](get-cccredential.md)
  
[Set-CcCredential](set-cccredential.md)
  

