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
localization_priority: Normal
ms.assetid: 44da2f8d-0bf5-4f3e-b2e7-bb181dbbe646
description: Этот Renew-CcCACertificate обновляет сертификат корневого ЦС Skype для бизнеса Cloud Connector Edition, срок действия которого истекает или уже истек. Эта команда была изменена Update-CcCACertificate в Cloud Connector 2.0 и более поздних выпусках.
ms.openlocfilehash: e92709cd1da0ffccd2b356000dbd2345ba56a1d9
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824275"
---
# <a name="renew-cccacertificate"></a>Renew-CcCACertificate
 
Этот Renew-CcCACertificate обновляет сертификат корневого ЦС Skype для бизнеса Cloud Connector Edition, срок действия которого истекает или уже истек. Эта команда была изменена Update-CcCACertificate в Cloud Connector 2.0 и более поздних выпусках.
  
```powershell
Renew-CcCACertificate
```

## <a name="parameters"></a>Параметры

Нет
  
## <a name="examples"></a>Примеры
<a name="Examples"> </a>

### <a name="example-1"></a>Пример 1

В следующем примере обновляется сертификат корневого ЦС: 
  
```powershell
Renew-CcCACertificate 
```

## <a name="detailed-description"></a>Подробное описание
<a name="DetailedDescription"> </a>

Сертификат корневого ЦС Cloud Connector действителен в течение пяти лет с даты установки службы ЦС.
  
Если срок действия корневого сертификата истекает или уже истек, запустите Renew-CcCACertificate для его продления. После продления корневого сертификата серверу AD Server, центральному окню управления и edge Server автоматически будут выданы новые сертификаты.
  
Если на одном сайте STN несколько устройств, запустите Renew-CcCACertificate на всех устройствах одного сайта STN.
  
На последнем этапе запустите Export-CcRootCertificate для экспорта корневого сертификата в локальный файл на первом устройстве, а затем скопируйте и установите экспортный сертификат на шлюзы STN.
  
## <a name="input-types"></a>Типы входных данных
<a name="InputTypes"> </a>

Нет. Этот Renew-CcCACertificate не принимает конвейерные входные данные.
  
## <a name="return-types"></a>Типы возвращаемых данных
<a name="ReturnTypes"> </a>

Нет
  
## <a name="see-also"></a>См. также
<a name="ReturnTypes"> </a>

[Reset-CcCACertificate](reset-cccacertificate.md)
  
[Renew-CcServerCertificate](renew-ccservercertificate.md)
  
[Export-CcRootCertificate](export-ccrootcertificate.md)
  

