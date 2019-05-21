---
title: Publish-CcAppliance
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e7d5b63e-ba7c-4757-8670-f96b2a91e646
description: Командлет Publish-CcAppliance получает сведения о высокой доступности из конфигурации интерактивного клиента и публикует их на устройстве Skype для бизнеса Cloud Connector Edition на сервере узла.
ms.openlocfilehash: 2fd17e2afdceabc8fbfb44a808b7e6c9ce6bd894
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34287162"
---
# <a name="publish-ccappliance"></a>Publish-CcAppliance
 
Командлет Publish-CcAppliance получает сведения о высокой доступности из конфигурации интерактивного клиента и публикует их на устройстве Skype для бизнеса Cloud Connector Edition на сервере узла. 
  
```
Publish-CcAppliance
```

## <a name="parameters"></a>Параметры

Нет
  
## <a name="examples"></a>Примеры
<a name="Examples"> </a>

### <a name="example-1"></a>Пример 1

В следующем примере показано получение сведений о высокой доступности из конфигурации Интернет-клиента и его публикация на устройстве облачного соединителя на сервере узла.
  
```
Publish-CcAppliance
```

## <a name="detailed-description"></a>Подробное описание
<a name="DetailedDescription"> </a>

В сведениях о высокой доступности содержатся полные доменные имена и IP-адреса серверов-посредников для сайта ТСОП. На сервер Active Directory добавляется новая запись DNS A для IP-адресов сервера-посредника. Полные доменные имена сервера центрального хранилища управления и сервера-посредника обновляются в соответствии с новыми элементами топологии.  
  
## <a name="input-types"></a>Типы входных данных
<a name="InputTypes"> </a>

Нет. Командлет Publish-CcAppliance не принимает входные данные по конвейеру.
  
## <a name="return-types"></a>Типы возвращаемых данных
<a name="ReturnTypes"> </a>

Отсутствуют
  
## <a name="see-also"></a>См. также
<a name="ReturnTypes"> </a>

[Install-CcAppliance](install-ccappliance.md)
  
[Uninstall-CcAppliance](uninstall-ccappliance.md)
  
[Register-CcAppliance](register-ccappliance.md)
  
[Unregister-CcAppliance](unregister-ccappliance.md)
  

