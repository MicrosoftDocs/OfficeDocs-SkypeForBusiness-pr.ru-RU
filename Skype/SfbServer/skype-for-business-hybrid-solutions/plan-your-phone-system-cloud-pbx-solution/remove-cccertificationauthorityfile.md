---
title: Remove-CcCertificationAuthorityFile
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/20/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3600af8d-04de-4b9a-88ac-2491ca06494d
description: Этот Remove-CcCertificationAuthorityFile удаляет файл резервной копии службы центра сертификации в папке ЦС в каталоге share сайта Skype для бизнеса Cloud Connector Edition.
ms.openlocfilehash: 49a8f0f313b4153288ebdf037a41dc92f30e60d6
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824295"
---
# <a name="remove-cccertificationauthorityfile"></a>Remove-CcCertificationAuthorityFile
 
The Remove-CcCertificationAuthorityFile cmdlet removes the certification authority service backup file " &lt; SiteRootDirectory &gt; \CA\SfB CCE Root.p12" in the CA folder under the site share directory for Skype for Business Cloud Connector Edition. 
  
```powershell
Remove-CcCertificationAuthorityFile
```

## <a name="parameters"></a>Параметры

Нет
  
## <a name="examples"></a>Примеры
<a name="Examples"> </a>

### <a name="example-1"></a>Пример 1

В следующем примере удаляется файл резервной копии службы центра сертификации &lt; "SiteRootDirectory &gt; \CA\SfB CCE Root.p12" в папке ЦС в каталоге для совместной работы сайта:
  
```powershell
Remove-CcCertificationAuthorityFile
```

## <a name="input-types"></a>Типы входных данных
<a name="InputTypes"> </a>

Нет. Этот Remove-CcCertificationAuthorityFile не принимает конвейерные входные данные.
  
## <a name="return-types"></a>Типы возвращаемых данных
<a name="ReturnTypes"> </a>

Нет
  
## <a name="see-also"></a>См. также
<a name="ReturnTypes"> </a>

[Backup-CcCertificationAuthority](backup-cccertificationauthority.md)
  

