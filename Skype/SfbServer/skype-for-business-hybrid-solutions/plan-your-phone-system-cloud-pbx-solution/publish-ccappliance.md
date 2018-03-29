---
title: Публикация CcAppliance
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e7d5b63e-ba7c-4757-8670-f96b2a91e646
description: Командлет Publish-CcAppliance получает сведения о высокой доступности из конфигурации интерактивного клиента и публикует их на устройстве Skype для бизнеса Cloud Connector Edition на сервере узла.
ms.openlocfilehash: c0a2639156a0794ec34fd62a58027255d24d461e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="publish-ccappliance"></a>Публикация CcAppliance
 
Командлет Publish-CcAppliance получает сведения о высокой доступности из конфигурации интерактивного клиента и публикует их на устройстве Skype для бизнеса Cloud Connector Edition на сервере узла. 
  
```
Publish-CcAppliance
```

## <a name="parameters"></a>Параметры

Нет
  
## <a name="examples"></a>Примеры
<a name="Examples"> </a>

### <a name="example-1"></a>Пример 1

В следующем примере возвращает сведения о высокой доступности из конфигурации сети клиентов и публикуется в облаке соединителя устройство на хост-сервера:
  
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

Нет
  
## <a name="see-also"></a>См. также
<a name="ReturnTypes"> </a>

[Install-CcAppliance](install-ccappliance.md)
  
[Удаление CcAppliance](uninstall-ccappliance.md)
  
[Register-CcAppliance](register-ccappliance.md)
  
[Отмена регистрации CcAppliance](unregister-ccappliance.md)
  

