---
title: Backup-CcCertificationAuthority
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 47ed4559-fb63-42cd-8ecd-b7d1617e91d3
description: Этот Backup-CcCertificationAuthority возвращает службу Skype для бизнеса Cloud Connector Edition сертификации в файл и сохраняет его в папке ЦС в каталоге акций сайта.
ms.openlocfilehash: f7803a1c773ca3561b13ef5a263002cc4b8e049a
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/26/2021
ms.locfileid: "58582533"
---
# <a name="backup-cccertificationauthority"></a>Backup-CcCertificationAuthority
 
Этот Backup-CcCertificationAuthority возвращает службу Skype для бизнеса Cloud Connector Edition сертификации в файл и сохраняет его в папке ЦС в каталоге акций сайта.
  
```powershell
Backup-CcCertificationAuthority 
```

## <a name="parameters"></a>Параметры

Нет
  
## <a name="examples"></a>Примеры
<a name="Examples"> </a>

### <a name="example-1"></a>Пример 1

В следующем примере служба сертификации возвращается в файл и сохраняет его в папке ЦС в каталоге совместной работы сайта:
  
```powershell
Backup-CcCertificationAuthority 
```

## <a name="detailed-description"></a>Подробное описание
<a name="DetailedDescription"> </a>

Резервное копирование органа сертификации может быть полезно, если планируется передиплоять устройство облачного соединителя с тем же сертификатом в случае аварии или при переходе устройства на новое оборудование. Команда сохраняет копию службы сертификации cloud Connector от AD Server до \<SiteRootDirectory\> "\CA\SfB CCE Root.p12".
  
## <a name="input-types"></a>Типы входных данных
<a name="InputTypes"> </a>

Нет. В Backup-CcCertificationAuthority не принимается конвейерный ввод.
  
## <a name="return-types"></a>Типы возвращаемых данных
<a name="ReturnTypes"> </a>

Нет
  
## <a name="see-also"></a>См. также
<a name="ReturnTypes"> </a>

[Remove-CcCertificationAuthorityFile](remove-cccertificationauthorityfile.md)
  

