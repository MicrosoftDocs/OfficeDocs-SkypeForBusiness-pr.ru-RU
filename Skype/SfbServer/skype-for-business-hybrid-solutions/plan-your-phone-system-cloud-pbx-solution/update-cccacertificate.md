---
title: Update-CcCACertificate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 7/11/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 5b474789-75de-443c-89bd-de89be55a1dd
description: Этот Update-CcCACertificate обновляет корневой сертификат ca Skype для бизнеса Cloud Connector Edition, который истек или уже истек.
ms.openlocfilehash: 824959ab053c7eb7cc71eb60a5d6ecbeb2c7a847
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/26/2021
ms.locfileid: "58628411"
---
# <a name="update-cccacertificate"></a>Update-CcCACertificate
 
Этот Update-CcCACertificate обновляет корневой сертификат ca Skype для бизнеса Cloud Connector Edition, который истек или уже истек. 
  
```powershell
Update-CcCACertificate
```

## <a name="parameters"></a>Параметры

Нет.
  
## <a name="examples"></a>Примеры
<a name="Examples"> </a>

### <a name="example-1"></a>Пример 1

В следующем примере обновляется корневой сертификат ЦС: 
  
```powershell
Update-CcCACertificate 
```

## <a name="detailed-description"></a>Подробное описание
<a name="DetailedDescription"> </a>

Сертификат корневого ca облачного соединитетеля действителен в течение пяти лет со дня установки службы сертификации.
  
Если срок действия корневого сертификата истек или истек, запустите Update-CcCACertificate для обновления сертификата. После возобновления корневого сертификата автоматически будут выдаваться новые сертификаты AD Server, Central Management Store и Edge Server.
  
Если на одном сайте PSTN имеется несколько устройств, запустите Update-CcCACertificate во всех устройствах одного сайта PSTN.
  
В качестве последнего шага запустите Export-CcRootCertificate для экспорта корневого сертификата в локальный файл в первом устройстве, а затем скопируйте и установите экспортируемую сертификацию на шлюзы PSTN.
  
Эта команда заменяет командлет Renew-CcCACertificate в Cloud Connector 2.0 и более поздних выпусках.
  
## <a name="input-types"></a>Типы входных данных
<a name="InputTypes"> </a>

Нет. В Update-CcCACertificate не принимается конвейерный ввод.
  
## <a name="return-types"></a>Типы возвращаемых данных
<a name="ReturnTypes"> </a>

Нет. 
  
## <a name="see-also"></a>См. также
<a name="ReturnTypes"> </a>

[Reset-CcCACertificate](reset-cccacertificate.md)
  
[Renew-CcServerCertificate](renew-ccservercertificate.md)
  
[Export-CcRootCertificate](export-ccrootcertificate.md)
  

