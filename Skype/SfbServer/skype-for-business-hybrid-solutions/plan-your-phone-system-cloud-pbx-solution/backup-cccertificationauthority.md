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
localization_priority: Normal
ms.assetid: 47ed4559-fb63-42cd-8ecd-b7d1617e91d3
description: Командлет Backup-CcCertificationAuthority выполняет резервное копирование службы центра сертификации Skype для бизнеса Cloud Connector Edition в файл и сохраняет папку CA в общем каталоге сайта.
ms.openlocfilehash: f99745e1dd5e28e2d7d8d10d4d152c7ada913fbf
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003029"
---
# <a name="backup-cccertificationauthority"></a>Backup-CcCertificationAuthority
 
Командлет Backup-CcCertificationAuthority выполняет резервное копирование службы центра сертификации Skype для бизнеса Cloud Connector Edition в файл и сохраняет папку CA в общем каталоге сайта.
  
```powershell
Backup-CcCertificationAuthority 
```

## <a name="parameters"></a>Параметры

Нет
  
## <a name="examples"></a>Примеры
<a name="Examples"> </a>

### <a name="example-1"></a>Пример 1

В следующем примере выполняется резервное копирование службы центра сертификации в файл и сохранение папки CA в общем каталоге сайта.
  
```powershell
Backup-CcCertificationAuthority 
```

## <a name="detailed-description"></a>Подробное описание
<a name="DetailedDescription"> </a>

Резервное копирование центра сертификации может быть полезно, если вы планируете повторное развертывание устройства облачного соединителя с помощью того же сертификата в случае аварии или вы хотите переместить устройство на новое оборудование. С помощью этой команды можно сохранить копию службы центра сертификации облачного соединителя с AD на сервере "\<СИТЕРУТДИРЕКТОРИ\>\ка\сфб кце root. p12".
  
## <a name="input-types"></a>Типы входных данных
<a name="InputTypes"> </a>

Нет. Командлет Backup-CcCertificationAuthority не принимает входные данные по конвейеру.
  
## <a name="return-types"></a>Типы возвращаемых данных
<a name="ReturnTypes"> </a>

Отсутствуют
  
## <a name="see-also"></a>См. также
<a name="ReturnTypes"> </a>

[Remove-CcCertificationAuthorityFile](remove-cccertificationauthorityfile.md)
  

