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
ms.localizationpriority: medium
ms.assetid: 1499e33c-6a7c-46b9-b9a1-f78d7853b45d
description: Этот Export-CcRootCertificate экспортирует корневой сертификат ЦС в локальный файл на Skype для бизнеса Cloud Connector Edition сервере.
ms.openlocfilehash: e00041088af39bf6f11abd5309ff293bd37bf38f
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/26/2021
ms.locfileid: "58625001"
---
# <a name="export-ccrootcertificate"></a>Export-CcRootCertificate
 
Этот Export-CcRootCertificate экспортирует корневой сертификат ЦС в локальный файл на Skype для бизнеса Cloud Connector Edition сервере. 
  
```powershell
Export-CcRootCertificate [[-Path] <string>]
```

## <a name="examples"></a>Примеры
<a name="Examples"> </a>

### <a name="example-1"></a>Пример 1

В следующем примере параметр Path определяется как путь каталога, а не путь файла. Он создает файл c:\test\CCERootCertificates.p7b.
  
```powershell
Export-CcRootCertificate -Path "C:\test" 
```

## <a name="detailed-description"></a>Подробное описание
<a name="DetailedDescription"> </a>

Этот Export-CcRootCertificate позволяет сохранить корневые и промежуточные сертификаты на путь файла. Это может быть полезно в случае аварийного восстановления. 
  
## <a name="parameters"></a>Параметры
<a name="DetailedDescription"> </a>

|**Параметр**|**Required**|**Тип**|**Описание**|
|:-----|:-----|:-----|:-----|
|Путь  <br/> |Обязательный  <br/> |System.String  <br/> |Путь к файлу, в котором будет храниться сертификат.  <br/> |
   
## <a name="input-types"></a>Типы входных данных
<a name="InputTypes"> </a>

Нет. В Export-CcRootCertificate не принимается конвейерный ввод. 
  
## <a name="return-types"></a>Типы возвращаемых данных
<a name="ReturnTypes"> </a>

Нет
  
## <a name="see-also"></a>См. также
<a name="ReturnTypes"> </a>

Нет
  

