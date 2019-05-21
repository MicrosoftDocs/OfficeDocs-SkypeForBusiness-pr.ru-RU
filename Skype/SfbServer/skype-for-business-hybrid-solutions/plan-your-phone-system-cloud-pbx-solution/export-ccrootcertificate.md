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
localization_priority: Normal
ms.assetid: 1499e33c-6a7c-46b9-b9a1-f78d7853b45d
description: 'Командлет Export-CcRootCertificate экспортирует корневой сертификат ЦС в локальный файл на сервере узла Skype для бизнеса Cloud Connector Edition. '
ms.openlocfilehash: 7d6d0978698b4b20b570107b51c9a89ff237b730
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34287385"
---
# <a name="export-ccrootcertificate"></a>Export-CcRootCertificate
 
Командлет Export-CcRootCertificate экспортирует корневой сертификат ЦС в локальный файл на сервере узла Skype для бизнеса Cloud Connector Edition.  
  
```
Export-CcRootCertificate [[-Path] <string>]
```

## <a name="examples"></a>Примеры
<a name="Examples"> </a>

### <a name="example-1"></a>Пример 1

В следующем примере параметр Path задается как путь к каталогу, а не к файлу. В нем создается файл c:\test\CCERootCertificates.p7b.
  
```
Export-CcRootCertificate -Path "C:\test" 
```

## <a name="detailed-description"></a>Подробное описание
<a name="DetailedDescription"> </a>

Командлет Export-CcRootCertificate позволяет вам сохранять корневые и промежуточные сертификаты, указав путь к файлу. Это может помочь при аварийном восстановлении.  
  
## <a name="parameters"></a>Параметры
<a name="DetailedDescription"> </a>

|**Параметр**|**Обязательно**|**Тип**|**Описание**|
|:-----|:-----|:-----|:-----|
|Путь  <br/> |Обязательно  <br/> |System.String  <br/> |Путь к файлу, где будет сохранен сертификат.   <br/> |
   
## <a name="input-types"></a>Типы входных данных
<a name="InputTypes"> </a>

Нет. Командлет Export-CcRootCertificate не принимает входные данные из конвейера.  
  
## <a name="return-types"></a>Типы возвращаемых данных
<a name="ReturnTypes"> </a>

Отсутствуют
  
## <a name="see-also"></a>См. также
<a name="ReturnTypes"> </a>

Нет
  

