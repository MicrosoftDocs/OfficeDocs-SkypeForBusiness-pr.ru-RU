---
title: Start-CcDownload
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/8/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 19338a34-1bfb-4787-b057-5e34a333711d
description: The Start-CcDownload cmdlet downloads the Skype for Business Cloud Connector Edition bits and msi file synchronously.
ms.openlocfilehash: 3298b02fbb792392860f05ebb15a9221b45e47b4
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824183"
---
# <a name="start-ccdownload"></a>Start-CcDownload
 
The Start-CcDownload cmdlet downloads the Skype for Business Cloud Connector Edition bits and msi file synchronously.
  
В Cloud Connector версии 2.0 и более поздних версий можно также указать параметр DownloadBitsOnly.
  
```powershell
Start-CcDownload [[-DownloadUrlRoot] <string>] [-DownloadBitsOnly]  [<CommonParameters>]
```

## <a name="examples"></a>Примеры
<a name="Examples"> </a>

### <a name="example-1"></a>Пример 1

В следующем примере синхронно загружаются биты Cloud Connector и MSI-файл с общего сайта загрузки Cloud Connector:
  
```powershell
Start-CcDownload
```

### <a name="example-2"></a>Пример 2

Следующий пример синхронно скачивает биты Cloud Connector и MSI-файл с частного сайта загрузки:
  
```powershell
Start-CcDownload -DownloadUrlRoot "http://downloadserver/cloudconnector/latest"
```

### <a name="example-3"></a>Пример 3

Третий пример синхронно скачивает биты Cloud Connector и MSI-файл с частного сайта для скачивания.
  
```powershell
Start-CcDownload -DownloadBitsOnly
```

## <a name="detailed-description"></a>Подробное описание
<a name="DetailedDescription"> </a>

Если на сайте загрузки доступна новая версия, Start-CcDownload скачивает и устанавливает MSI-файл с сайта загрузки, а затем синхронно скачивает биты Cloud Connector. Если новая версия MSI-файла не существует, Start-CcDownload скачать только биты Cloud Connector. Если биты Cloud Connector уже загружены, Start-CcDownload не выполняется.
  
## <a name="parameters"></a>Параметры
<a name="DetailedDescription"> </a>

|**Параметр**|**Required**|**Тип**|**Описание**|
|:-----|:-----|:-----|:-----|
|DownloadUrlRoot  <br/> | Необязательный <br/> |System.String  <br/> | Полный URL-адрес определенной версии Cloud Connector на частном сайте загрузки. Используйте этот параметр с осторожностью— убедитесь, что вы знаете, какую версию Cloud Connector вы скачиваете. <br/> |
|DownloadBitsOnly  <br/> |Необязательный  <br/> |System.Management.Automation.SwitchParameter  <br/> |Пропустите этот шаг, чтобы скачать и установить MSI с сайта загрузки, скачайте только биты Cloud Connector.  <br/> |
   
## <a name="input-types"></a>Типы входных данных
<a name="InputTypes"> </a>

Нет. Этот Start-CcDownload не принимает конвейерные входные данные.
  
## <a name="return-types"></a>Типы возвращаемых данных
<a name="ReturnTypes"> </a>

Нет
  
## <a name="see-also"></a>См. также
<a name="ReturnTypes"> </a>

Нет
  

