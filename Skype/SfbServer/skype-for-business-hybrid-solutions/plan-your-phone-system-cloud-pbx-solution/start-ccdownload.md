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
localization_priority: Normal
ms.assetid: 19338a34-1bfb-4787-b057-5e34a333711d
description: Командлет Start-CcDownload синхронно скачивает части выпуска облачного соединителя Skype для бизнеса и MSI-файл.
ms.openlocfilehash: 184c15d1932a179bb9ae07da515eeacfc115dfae
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34286945"
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

В следующем примере синхронизирующие биты и MSI-файл загружаются синхронно из общедоступного сайта скачивания облачного соединителя:
  
```
Start-CcDownload
```

### <a name="example-2"></a>Пример 2

В следующем примере синхронизирующие биты и MSI-файл загружаются синхронно из закрытого сайта скачивания.
  
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

Если на сайте загрузки доступна новая версия, запустите-Ккдовнлоад, чтобы скачать и установить MSI-файл с сайта загрузки, а затем синхронно Скачайте биты из облака. Если новая версия MSI-файла отсутствует, командлет Start-CcDownload скачает только BITS-файл Cloud Connector. Если BITS-файл Cloud Connector уже скачан, командлет Start-CcDownload не выполняется.
  
## <a name="parameters"></a>Параметры
<a name="DetailedDescription"> </a>

|**Параметр**|**Обязательно**|**Тип**|**Описание**|
|:-----|:-----|:-----|:-----|
|DownloadUrlRoot   <br/> |  Необязательно <br/> |System.String  <br/> | Полный URL-адрес конкретной версии облачного соединителя на закрытом сайте скачивания. Используйте этот параметр с осторожностью, убедитесь, что вы знаете, какую версию облачного соединителя вы скачиваете. <br/> |
|DownloadBitsOnly   <br/> |Необязательно  <br/> |System.Management.Automation.SwitchParameter  <br/> |Пропустите скачивание и установку MSI-файла с сайта для скачивания. Скачайте только BITS-файл Cloud Connector.  <br/> |
   
## <a name="input-types"></a>Типы входных данных
<a name="InputTypes"> </a>

Нет. Командлет Start-CcDownload не принимает входные данные по конвейеру.
  
## <a name="return-types"></a>Типы возвращаемых данных
<a name="ReturnTypes"> </a>

Отсутствуют
  
## <a name="see-also"></a>См. также
<a name="ReturnTypes"> </a>

Нет
  

