---
title: Renew-CcCACertificate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 7/18/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 44da2f8d-0bf5-4f3e-b2e7-bb181dbbe646
description: Этот Renew-CcCACertificate обновляет корневой сертификат ca Skype для бизнеса Cloud Connector Edition, который истек или уже истек. Эта команда была изменена на Update-CcCACertificate в cloud Connector 2.0 и более поздних выпусках.
ms.openlocfilehash: f48839360af0be72279547e1e1f9cbd695c48b39
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/26/2021
ms.locfileid: "58624981"
---
# <a name="renew-cccacertificate"></a>Renew-CcCACertificate
 
Этот Renew-CcCACertificate обновляет корневой сертификат ca Skype для бизнеса Cloud Connector Edition, который истек или уже истек. Эта команда была изменена на Update-CcCACertificate в cloud Connector 2.0 и более поздних выпусках.
  
```powershell
Renew-CcCACertificate
```

## <a name="parameters"></a>Параметры

Нет
  
## <a name="examples"></a>Примеры
<a name="Examples"> </a>

### <a name="example-1"></a>Пример 1

В следующем примере обновляется корневой сертификат ЦС: 
  
```powershell
Renew-CcCACertificate 
```

## <a name="detailed-description"></a>Подробное описание
<a name="DetailedDescription"> </a>

Сертификат корневого ca облачного соединитетеля действителен в течение пяти лет со дня установки службы сертификации.
  
Если срок действия корневого сертификата истек или истек, запустите Renew-CcCACertificate для обновления сертификата. После возобновления корневого сертификата автоматически будут выдаваться новые сертификаты AD Server, Central Management Store и Edge Server.
  
Если на одном сайте PSTN имеется несколько устройств, запустите Renew-CcCACertificate во всех устройствах одного сайта PSTN.
  
В качестве последнего шага запустите Export-CcRootCertificate для экспорта корневого сертификата в локальный файл в первом устройстве, а затем скопируйте и установите экспортируемую сертификацию на шлюзы PSTN.
  
## <a name="input-types"></a>Типы входных данных
<a name="InputTypes"> </a>

Нет. В Renew-CcCACertificate не принимается конвейерный ввод.
  
## <a name="return-types"></a>Типы возвращаемых данных
<a name="ReturnTypes"> </a>

Нет
  
## <a name="see-also"></a>См. также
<a name="ReturnTypes"> </a>

[Reset-CcCACertificate](reset-cccacertificate.md)
  
[Renew-CcServerCertificate](renew-ccservercertificate.md)
  
[Export-CcRootCertificate](export-ccrootcertificate.md)
  

