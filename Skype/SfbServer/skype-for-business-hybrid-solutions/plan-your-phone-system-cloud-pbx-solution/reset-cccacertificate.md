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
description: Этот Reset-CcCACertificate переустановил службу AD Server службы сертификации для создания нового корневого сертификата ЦС.
ms.openlocfilehash: 8e0cb93e6f10f28df28213579674a6cda6e7e2cd1cf201319f77dc26be69de80
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2021
ms.locfileid: "54340725"
---
# <a name="reset-cccacertificate"></a>Reset-CcCACertificate
 
Этот Reset-CcCACertificate переустановил службу AD Server службы сертификации для создания нового корневого сертификата ЦС.
  
```powershell
Reset-CcCACertificate
```

## <a name="parameters"></a>Параметры

Нет
  
## <a name="examples"></a>Примеры
<a name="Examples"> </a>

### <a name="example-1"></a>Пример 1

В следующем примере переустановка службы AD Server службы сертификации для создания нового корневого сертификата ЦС:
  
```powershell
Reset-CcCACertificate
```

## <a name="detailed-description"></a>Подробное описание
<a name="DetailedDescription"> </a>

Если корневой сертификат ЦС скомпрометирован или более не защищен, необходимо обновить корневой сертификат ЦС и все сертификаты, выданные корневым ЦС. Этот Reset-CcCACertificate отзывает все сертификаты, отменяет и переустановит управление сертификатами, а затем очищает все сертификаты, связанные со старой службой сертификации. 
  
Дополнительные сведения см. в справке "Сертификаты или внутренние сертификаты, выданные CMS, mediation Server и Edge Server, находятся вблизи истечения срока действия или находятся под угрозой" в устранении неполадок в развертывании облачного соединитетеля.
  
## <a name="input-types"></a>Типы входных данных
<a name="InputTypes"> </a>

Нет. В Reset-CcCACertificate не принимается конвейерный ввод.
  
## <a name="return-types"></a>Типы возвращаемых данных
<a name="ReturnTypes"> </a>

Нет.
  
## <a name="see-also"></a>См. также
<a name="ReturnTypes"> </a>

[Renew-CcCACertificate](renew-cccacertificate.md) Только версия 1.4.2
  
[Renew-CcServerCertificate](renew-ccservercertificate.md) Только версия 1.4.2
  
[Update-CcCACertificate](update-cccacertificate.md) Версия 2.0 и более поздние версии
  
[Renew-CcServerCertificate](renew-ccservercertificate.md) Версия 2.0 и более поздние версии
  
[Export-CcRootCertificate](export-ccrootcertificate.md)
  

