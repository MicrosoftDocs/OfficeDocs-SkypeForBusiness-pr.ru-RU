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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: e7d5b63e-ba7c-4757-8670-f96b2a91e646
description: Этот Publish-CcAppliance получает информацию о высокой доступности из конфигурации клиента в Интернете и публикует ее в Skype для бизнеса Cloud Connector Edition на сервере хост-сервера.
ms.openlocfilehash: 83b0a7e3806a271a358085bb0cca2a2ef6a518e67e124f0be97c1ff4616e3dcc
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2021
ms.locfileid: "54326185"
---
# <a name="publish-ccappliance"></a>Publish-CcAppliance
 
Этот Publish-CcAppliance получает информацию о высокой доступности из конфигурации клиента в Интернете и публикует ее в Skype для бизнеса Cloud Connector Edition на сервере хост-сервера. 
  
```powershell
Publish-CcAppliance
```

## <a name="parameters"></a>Параметры

Нет
  
## <a name="examples"></a>Примеры
<a name="Examples"> </a>

### <a name="example-1"></a>Пример 1

В следующем примере сведения о высокой доступности получаются из конфигурации клиента в Интернете и публикуются в устройстве Cloud Connector на сервере хост-сервера:
  
```powershell
Publish-CcAppliance
```

## <a name="detailed-description"></a>Подробное описание
<a name="DetailedDescription"> </a>

Сведения о высокой доступности содержат FQDNs сервера-посредника и IP-адреса сайта PSTN. Новые записи DNS A добавляются в IP-адреса AD Server для ip-адресов сервера-посредника. Новые элементы топологии обновляются в Центральный магазин управления для FQDNs-серверов-посредников и IP-адресов. 
  
## <a name="input-types"></a>Типы входных данных
<a name="InputTypes"> </a>

Нет. В Publish-CcAppliance не принимается конвейерный ввод.
  
## <a name="return-types"></a>Типы возвращаемых данных
<a name="ReturnTypes"> </a>

Нет
  
## <a name="see-also"></a>См. также
<a name="ReturnTypes"> </a>

[Install-CcAppliance](install-ccappliance.md)
  
[Uninstall-CcAppliance](uninstall-ccappliance.md)
  
[Register-CcAppliance](register-ccappliance.md)
  
[Unregister-CcAppliance](unregister-ccappliance.md)
  

