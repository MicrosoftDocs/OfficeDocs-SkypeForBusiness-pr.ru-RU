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
localization_priority: Normal
ms.assetid: 5ada7e55-df9b-4b4e-b752-2468f4e28b8a
description: Командлет Reset-CcCACertificate переустанавливает сервер Active Directory службы центра сертификации для создания нового сертификата корневого центра сертификации.
ms.openlocfilehash: 3cac8629a52d915df55408a44d8d31701106a5bd
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34287071"
---
# <a name="reset-cccacertificate"></a>Reset-CcCACertificate
 
Командлет Reset-CcCACertificate переустанавливает сервер Active Directory службы центра сертификации для создания нового сертификата корневого центра сертификации.
  
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
  
Дополнительные сведения можно найти в разделе сертификаты центра сертификации или внутренние сертификаты, выданные серверу CMS, сервер-посредника, а также на пограничном сервере и нарушающие его срок действия, которые устраняют проблемы с развертыванием облачного соединителя.
  
## <a name="input-types"></a>Типы входных данных
<a name="InputTypes"> </a>

Нет. Командлет Reset-CcCACertificate не принимает входные данные по конвейеру.
  
## <a name="return-types"></a>Типы возвращаемых данных
<a name="ReturnTypes"> </a>

Нет. 
  
## <a name="see-also"></a>См. также
<a name="ReturnTypes"> </a>

[Renew-CcCACertificate](renew-cccacertificate.md) Только для версии 1.4.2
  
[Renew-CcServerCertificate](renew-ccservercertificate.md) Только для версии 1.4.2
  
[Update-CcCACertificate](update-cccacertificate.md) Версия 2.0 и более поздние версии
  
[Продление подписки на кксерверцертификате](renew-ccservercertificate.md) Версия 2,0 и более поздние версии
  
[Export-CcRootCertificate](export-ccrootcertificate.md)
  

