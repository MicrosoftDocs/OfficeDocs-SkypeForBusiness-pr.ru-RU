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
description: Командлет Backup-CcCertificationAuthority резервное копирование службы центра сертификации Skype для бизнеса Cloud Connector Edition в файл и сохраняет его в папке ЦС в каталоге общего ресурса сайта.
ms.openlocfilehash: 4dc67fa9e1b4a9a52b3e447b09d91a74704be690
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/25/2022
ms.locfileid: "65675461"
---
# <a name="backup-cccertificationauthority"></a>Backup-CcCertificationAuthority

Командлет Backup-CcCertificationAuthority создает резервную копию Skype для бизнеса Cloud Connector Edition центра сертификации в файл. Командлет также сохраняет его в папке ЦС в каталоге общего ресурса сайта.

```powershell
Backup-CcCertificationAuthority
```

## <a name="parameters"></a>Параметры

Нет

## <a name="examples"></a>Примеры
<a name="Examples"> </a>

### <a name="example-1"></a>Пример 1

В следующем примере создается резервная копия службы центра сертификации в файл и сохраняется в папке ЦС в каталоге общей папки сайта:

```powershell
Backup-CcCertificationAuthority
```

## <a name="detailed-description"></a>Подробное описание
<a name="DetailedDescription"> </a>

Резервное копирование центра сертификации может быть полезно, если вы планируете повторно развернуть устройство Cloud Connector с тем же сертификатом. Например:

- Аварийное восстановление.
- Переместите устройство на новое оборудование.

Эта команда сохраняет копию службы центра сертификации Cloud Connector с сервера AD в `"<SiteRootDirectory>\CA\SfB CCE Root.p12"`.

## <a name="input-types"></a>Типы входных данных
<a name="InputTypes"> </a>

Нет. Командлет Backup-CcCertificationAuthority не принимает конвейерные входные данные.

## <a name="return-types"></a>Типы возвращаемых данных
<a name="ReturnTypes"> </a>

Нет

## <a name="see-also"></a>См. также
<a name="ReturnTypes"> </a>

[Remove-CcCertificationAuthorityFile](remove-cccertificationauthorityfile.md)
  