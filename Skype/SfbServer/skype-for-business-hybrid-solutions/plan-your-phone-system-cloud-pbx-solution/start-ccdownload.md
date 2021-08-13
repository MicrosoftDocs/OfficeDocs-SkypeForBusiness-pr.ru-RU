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
description: Этот Start-CcDownload синхронно загружает Skype для бизнеса Cloud Connector Edition и файл msi.
ms.openlocfilehash: 0447c75ac3e6df79a20d2c87b664bfb92cf7124fc7253c839a88fad1b335eaec
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2021
ms.locfileid: "54351918"
---
# <a name="start-ccdownload"></a>Start-CcDownload
 
Этот Start-CcDownload синхронно загружает Skype для бизнеса Cloud Connector Edition и файл msi.
  
С cloud Connector версии 2.0 и более поздней версии можно также указать параметр DownloadBitsOnly.
  
```powershell
Start-CcDownload [[-DownloadUrlRoot] <string>] [-DownloadBitsOnly]  [<CommonParameters>]
```

## <a name="examples"></a>Примеры
<a name="Examples"> </a>

### <a name="example-1"></a>Пример 1

В следующем примере с сайта скачивания общедоступных подключений cloud Connector синхронно загружаются биты и файл msi:
  
```powershell
Start-CcDownload
```

### <a name="example-2"></a>Пример 2

В следующем примере с частного сайта загрузки синхронно загружаются биты облачного соединитела и файл msi:
  
```powershell
Start-CcDownload -DownloadUrlRoot "http://downloadserver/cloudconnector/latest"
```

### <a name="example-3"></a>Пример 3

В третьем примере с частного сайта скачивания синхронно загружаются биты cloud Connector и файл msi.
  
```powershell
Start-CcDownload -DownloadBitsOnly
```

## <a name="detailed-description"></a>Подробное описание
<a name="DetailedDescription"> </a>

Если на сайте скачивания доступна новая версия, Start-CcDownload скачивает и устанавливает файл msi с сайта загрузки, а затем синхронно скачивает биты облачного соединителя. Если нет новой версии файла msi, Start-CcDownload скачивает только биты облачного соединитела. Если биты облачного соединиттеля уже загружены, Start-CcDownload не выполняется.
  
## <a name="parameters"></a>Параметры
<a name="DetailedDescription"> </a>

|**Параметр**|**Required**|**Тип**|**Описание**|
|:-----|:-----|:-----|:-----|
|DownloadUrlRoot  <br/> | Необязательный <br/> |System.String  <br/> | Полный URL-адрес определенной версии облачного соединителя на частном сайте загрузки. Используйте этот параметр с осторожностью, убедитесь, что вам известно о том, какую версию облачного соединиттеля вы скачиваете. <br/> |
|DownloadBitsOnly  <br/> |Необязательный  <br/> |System.Management.Automation.SwitchParameter  <br/> |Пропустите шаг, чтобы скачать и установить MSI с сайта загрузки, скачайте только биты Облачного соединителя.  <br/> |
   
## <a name="input-types"></a>Типы входных данных
<a name="InputTypes"> </a>

Нет. В Start-CcDownload не принимается конвейерный ввод.
  
## <a name="return-types"></a>Типы возвращаемых данных
<a name="ReturnTypes"> </a>

Нет
  
## <a name="see-also"></a>См. также
<a name="ReturnTypes"> </a>

Нет
  

