---
title: Восстановление CcCredentials
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aeca610b-db0a-45cf-95b9-ae9a6bbccb45
description: Командлет учетные данные копия на восстановление восстанавливает все учетные данные текущего Скайп для развертывания соединителя Cloud Business Edition.
ms.openlocfilehash: bb74444c5f63b792abf6c12c317c1a824298426c
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/05/2018
ms.locfileid: "19569735"
---
# <a name="restore-cccredentials"></a>Восстановление CcCredentials
 
Командлет учетные данные копия на восстановление восстанавливает все учетные данные текущего Скайп для развертывания соединителя Cloud Business Edition. 
  
Этот командлет применяется к Скайп для соединителя выпуск Business Cloud 2.1.
  
```
Restore-CcCredentials 
```

## <a name="detailed-description"></a>Подробное описание

Командлет Restore-CcCredentials очищает все учетные данные, необходимо повторно ввести все учетные данные, используемые для текущего Скайп для развертывания Cloud Business Connector.
  
## <a name="parameters"></a>Параметры

Нет
  
## <a name="input-types"></a>Типы входных данных

Нет. Командлет Restore-CcCredentials не принимает входные данные.
  
## <a name="return-types"></a>Типы возвращаемых данных

Нет.
  
## <a name="example"></a>Пример

В следующем примере восстанавливается все учетные данные текущего развертывания облака соединителя:
  
```
    PS C:\>Restore-CcCredentials
```

## <a name="see-also"></a>См. также

[Get-CcCredential](get-cccredential.md)
  
[SET-CcCredential](set-cccredential.md)
  

