---
title: Start-CcDownload
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/8/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 19338a34-1bfb-4787-b057-5e34a333711d
description: Командлет Start-CcDownload синхронно скачивает части выпуска облачного соединителя Skype для бизнеса и MSI-файл.
ms.openlocfilehash: aec8d5c1848e7e55d6ed4b7e4d3633942f74ab55
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="start-ccdownload"></a>Start-CcDownload
 
Командлет Start-CcDownload синхронно скачивает части выпуска облачного соединителя Skype для бизнеса и MSI-файл.
  
В Cloud Connector версии 2.0 и более поздних также можно задать параметр DownloadBitsOnly.
  
```
Start-CcDownload [[-DownloadUrlRoot] <string>] [-DownloadBitsOnly]  [<CommonParameters>]
```

## <a name="examples"></a>Примеры
<a name="Examples"> </a>

### <a name="example-1"></a>Пример 1

Следующий пример файлы для загрузки bits облачных соединителя и msi-файл синхронно с сайта загрузки облака соединителя
  
```
Start-CcDownload
```

### <a name="example-2"></a>Пример 2

Следующий пример файлы для загрузки bits облачных соединителя и msi-файл синхронно с сайта закрытый файл для загрузки
  
```
Start-CcDownload -DownloadUrlRoot "http://downloadserver/cloudconnector/latest"
```

### <a name="example-3"></a>Пример 3

В третьем примере синхронно скачиваются файлы BITS и MSI Cloud Connector с закрытого сайта для скачивания.
  
```
Start-CcDownload -DownloadBitsOnly
```

## <a name="detailed-description"></a>Подробное описание
<a name="DetailedDescription"> </a>

При наличии новой версии доступны в узле загрузки, Start-CcDownload загрузить и установить msi-файл с сайта загрузки и синхронно Загрузите бит облачных соединителя. Если новая версия MSI-файла отсутствует, командлет Start-CcDownload скачает только BITS-файл Cloud Connector. Если BITS-файл Cloud Connector уже скачан, командлет Start-CcDownload не выполняется.
  
## <a name="parameters"></a>Параметры
<a name="DetailedDescription"> </a>

|**Параметр**|**Обязательно**|**Тип**|**Описание**|
|:-----|:-----|:-----|:-----|
|DownloadUrlRoot  <br/> |  Необязательно <br/> |System.String  <br/> | Полный URL-адрес определенной версии соединителя облака в частном Загрузите сайта. Используйте этот параметр с осторожностью, убедитесь, что для загрузки версии облачных соединителя. <br/> |
|DownloadBitsOnly  <br/> |Необязательно   <br/> |System.Management.Automation.SwitchParameter  <br/> |Пропустите скачивание и установку MSI-файла с сайта для скачивания. Скачайте только BITS-файл Cloud Connector.  <br/> |
   
## <a name="input-types"></a>Типы входных данных
<a name="InputTypes"> </a>

Нет. Командлет Start-CcDownload не принимает входные данные по конвейеру.
  
## <a name="return-types"></a>Типы возвращаемых данных
<a name="ReturnTypes"> </a>

Нет
  
## <a name="see-also"></a>См. также
<a name="ReturnTypes"> </a>

Нет
  

