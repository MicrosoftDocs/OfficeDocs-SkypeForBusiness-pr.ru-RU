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
localization_priority: Normal
ms.assetid: 47ed4559-fb63-42cd-8ecd-b7d1617e91d3
description: The Backup-CcCertificationAuthority cmdlet backs up the Skype for Business Cloud Connector Edition certification authority service to a file and saves it to the CA folder under the site share directory.
ms.openlocfilehash: 4e12b2349f5834866fc69442fb2947425416fe23
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803809"
---
# <a name="backup-cccertificationauthority"></a>Backup-CcCertificationAuthority
 
The Backup-CcCertificationAuthority cmdlet backs up the Skype for Business Cloud Connector Edition certification authority service to a file and saves it to the CA folder under the site share directory.
  
```powershell
Backup-CcCertificationAuthority 
```

## <a name="parameters"></a>Параметры

Нет
  
## <a name="examples"></a>Примеры
<a name="Examples"> </a>

### <a name="example-1"></a>Пример 1

В следующем примере архивация службы центра сертификации в файл и сохранение его в папку ЦС в каталоге для совместной работы сайта:
  
```powershell
Backup-CcCertificationAuthority 
```

## <a name="detailed-description"></a>Подробное описание
<a name="DetailedDescription"> </a>

Резервное копирование в сертификационных органах может оказаться полезным, если вы планируете использовать устройство Cloud Connector с тем же сертификатом в случае аварии или если вы хотите переместить его на новое оборудование. Команда сохраняет копию службы сертификации Cloud Connector с сервера AD Server в \< "SiteRootDirectory \> \CA\SfB CCE Root.p12".
  
## <a name="input-types"></a>Типы входных данных
<a name="InputTypes"> </a>

Нет. Этот Backup-CcCertificationAuthority не принимает конвейерные входные данные.
  
## <a name="return-types"></a>Типы возвращаемых данных
<a name="ReturnTypes"> </a>

Нет
  
## <a name="see-also"></a>См. также
<a name="ReturnTypes"> </a>

[Remove-CcCertificationAuthorityFile](remove-cccertificationauthorityfile.md)
  

