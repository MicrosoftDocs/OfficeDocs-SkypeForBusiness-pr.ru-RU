---
title: Reset-CcCACertificate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 6/22/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 5ada7e55-df9b-4b4e-b752-2468f4e28b8a
description: Этот Reset-CcCACertificate переустановит сервер AD Службы сертификации для создания нового корневого сертификата ЦС.
ms.openlocfilehash: 6a7f377642ca8aa8722933e503a6c0c2f2613544
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824255"
---
# <a name="reset-cccacertificate"></a>Reset-CcCACertificate
 
Этот Reset-CcCACertificate переустановит сервер AD Службы сертификации для создания нового корневого сертификата ЦС.
  
```powershell
Reset-CcCACertificate
```

## <a name="parameters"></a>Параметры

Нет
  
## <a name="examples"></a>Примеры
<a name="Examples"> </a>

### <a name="example-1"></a>Пример 1

В следующем примере переустановка сервера AD Server службы сертификации для создания нового сертификата корневого ЦС:
  
```powershell
Reset-CcCACertificate
```

## <a name="detailed-description"></a>Подробное описание
<a name="DetailedDescription"> </a>

Если сертификат корневого ЦС скомпрометирован или больше не защищен, необходимо обновить сертификат корневого ЦС и все сертификаты, выданные корневым ЦС. Этот Reset-CcCACertificate отзывает все сертификаты, отменяет и переустанавлетирует ЦС сертификации, а затем очищает все сертификаты, связанные со старой службой центра сертификации. 
  
Дополнительные сведения см. в подключении "Срок действия сертификатов из ЦС, сервера-посредника и сервера-посредника истекает или они скомпрометированы" в устранении неполадок развертывания Cloud Connector.
  
## <a name="input-types"></a>Типы входных данных
<a name="InputTypes"> </a>

Нет. Этот Reset-CcCACertificate не принимает конвейерные входные данные.
  
## <a name="return-types"></a>Типы возвращаемых данных
<a name="ReturnTypes"> </a>

Нет.
  
## <a name="see-also"></a>См. также
<a name="ReturnTypes"> </a>

[Renew-CcCACertificate](renew-cccacertificate.md) Только версия 1.4.2
  
[Renew-CcServerCertificate](renew-ccservercertificate.md) Только версия 1.4.2
  
[Update-CcCACertificate](update-cccacertificate.md) Версия 2.0 и более поздние
  
[Renew-CcServerCertificate](renew-ccservercertificate.md) Версия 2.0 и более поздние
  
[Export-CcRootCertificate](export-ccrootcertificate.md)
  

