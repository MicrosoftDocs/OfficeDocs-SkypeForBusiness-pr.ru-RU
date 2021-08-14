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
description: Этот Export-CcRootCertificate экспортирует корневой сертификат ЦС в локальный файл на Skype для бизнеса Cloud Connector Edition сервере.
ms.openlocfilehash: 04ba7af5801f124a76e515b311a0507e3cbb764a6f2769d9f1d9080ec8c7d9d9
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2021
ms.locfileid: "54326255"
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
|Path  <br/> |Обязательный  <br/> |System.String  <br/> |Путь к файлу, в котором будет храниться сертификат.  <br/> |
   
## <a name="input-types"></a>Типы входных данных
<a name="InputTypes"> </a>

Нет. В Export-CcRootCertificate не принимается конвейерный ввод. 
  
## <a name="return-types"></a>Типы возвращаемых данных
<a name="ReturnTypes"> </a>

Нет
  
## <a name="see-also"></a>См. также
<a name="ReturnTypes"> </a>

Нет
  

