---
title: Сброс CcCACertificate
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 6/22/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5ada7e55-df9b-4b4e-b752-2468f4e28b8a
description: Командлет Reset-CcCACertificate переустанавливает сервера AD службы центра сертификации для создания нового сертификата корневого ЦС.
ms.openlocfilehash: dc86c39e844accc789ba7a3503aa6261d40e5cb2
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="reset-cccacertificate"></a>Сброс CcCACertificate
 
Командлет Reset-CcCACertificate переустанавливает сервера AD службы центра сертификации для создания нового сертификата корневого ЦС.
  
```
Reset-CcCACertificate
```

## <a name="parameters"></a>Параметры

Нет
  
## <a name="examples"></a>Примеры
<a name="Examples"> </a>

### <a name="example-1"></a>Пример 1

В следующем примере переустанавливается сервер Active Directory службы центра сертификации для создания нового сертификата корневого центра сертификации.
  
```
Reset-CcCACertificate
```

## <a name="detailed-description"></a>Подробное описание
<a name="DetailedDescription"> </a>

Если сертификат корневого центра сертификации скомпрометирован или не обеспечивает нужный уровень безопасности, необходимо обновить его и все остальные сертификаты, выданные корневым центром сертификации. Командлет Reset-CcCACertificate отзывает все сертификаты, удаляет и переустанавливает центр сертификации, после чего очищает все сертификаты, связанные со старой службой центра сертификации. 
  
Для получения дополнительных сведений см раздел «Сертификат центра сертификации или внутренних сертификатам, выданным CMS, сервер-посредник и пограничного сервера, срок действия или скомпрометированы» Устранение неполадок развертывания облака соединителя.
  
## <a name="input-types"></a>Типы входных данных
<a name="InputTypes"> </a>

Нет. Командлет Reset-CcCACertificate не принимает входные данные по конвейеру.
  
## <a name="return-types"></a>Типы возвращаемых данных
<a name="ReturnTypes"> </a>

Нет.
  
## <a name="see-also"></a>См. также
<a name="ReturnTypes"> </a>

[Обновить CcCACertificate](renew-cccacertificate.md) Только версии 1.4.2
  
[Обновить CcServerCertificate](renew-ccservercertificate.md) Только версии 1.4.2
  
[Обновление CcCACertificate](update-cccacertificate.md) Версии 2.0 и более поздних версий
  
[Обновить CcServerCertificate](renew-ccservercertificate.md) Версии 2.0 и более поздних версий
  
[Export-CcRootCertificate](export-ccrootcertificate.md)
  

