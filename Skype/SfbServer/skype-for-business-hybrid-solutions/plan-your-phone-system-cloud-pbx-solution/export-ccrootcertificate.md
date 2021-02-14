---
title: Export-CcRootCertificate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 9/20/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 1499e33c-6a7c-46b9-b9a1-f78d7853b45d
description: Этот Export-CcRootCertificate экспортирует сертификат корневого ЦС в локальный файл на сервере хост-сервера Skype для бизнеса Cloud Connector Edition.
ms.openlocfilehash: 2b252eba4688deb790d85b0c3663b09a9e85e7b9
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41800919"
---
# <a name="export-ccrootcertificate"></a>Export-CcRootCertificate
 
Этот Export-CcRootCertificate экспортирует сертификат корневого ЦС в локальный файл на сервере хост-сервера Skype для бизнеса Cloud Connector Edition. 
  
```powershell
Export-CcRootCertificate [[-Path] <string>]
```

## <a name="examples"></a>Примеры
<a name="Examples"> </a>

### <a name="example-1"></a>Пример 1

В следующем примере задан параметр Path в качестве пути к каталогу, а не пути к файлу. Он создает файл c:\test\CCERootCertificates.p7b.
  
```powershell
Export-CcRootCertificate -Path "C:\test" 
```

## <a name="detailed-description"></a>Подробное описание
<a name="DetailedDescription"> </a>

Этот Export-CcRootCertificate позволяет сохранить корневой и промежуточный сертификаты в путь к файлу. Это может быть полезно в случае аварийного восстановления. 
  
## <a name="parameters"></a>Параметры
<a name="DetailedDescription"> </a>

|**Параметр**|**Required**|**Тип**|**Описание**|
|:-----|:-----|:-----|:-----|
|Path  <br/> |Обязательный  <br/> |System.String  <br/> |Путь к файлу, в котором будет храниться сертификат.  <br/> |
   
## <a name="input-types"></a>Типы входных данных
<a name="InputTypes"> </a>

Нет. Этот Export-CcRootCertificate не принимает конвейерные входные данные. 
  
## <a name="return-types"></a>Типы возвращаемых данных
<a name="ReturnTypes"> </a>

Нет
  
## <a name="see-also"></a>См. также
<a name="ReturnTypes"> </a>

Нет
  

