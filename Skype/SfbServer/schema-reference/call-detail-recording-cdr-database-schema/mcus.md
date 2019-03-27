---
title: Таблица Mcus в Скайп для Business Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 271b7963-8fd8-4d92-a701-1a62aaf895ee
description: Таблица Mcus представляет собой вспомогательную таблицу. Каждая запись хранит сведения об одной службы конференц-связи. Следующие службы обмена мгновенными Сообщениями конференц-связи и служба телефонной конференц-связи (который выполняются как процессы на серверах переднего плана) и служба веб-конференций и A / службы аудио-и видеоконференциями.
ms.openlocfilehash: e051af3a77d4f9b8231c122c596a3b6915f6f3e1
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30893014"
---
# <a name="mcus-table-in-skype-for-business-server-2015"></a>Таблица Mcus в Скайп для Business Server 2015
 
Таблица Mcus представляет собой вспомогательную таблицу. Каждая запись хранит сведения об одной службы конференц-связи. Следующие службы обмена мгновенными Сообщениями конференц-связи и служба телефонной конференц-связи (который выполняются как процессы на серверах переднего плана) и служба веб-конференций и A / службы аудио-и видеоконференциями. 
  
|**Столбец**|**Тип данных**|**Ключ/индекс**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**McuId** <br/> |целое  <br/> |Primary  <br/> |Уникальный номер, идентифицирующий этот сервер конференций.  <br/> |
|**McuUri** <br/> |nvarchar(450)  <br/> | <br/> | <br/> |
|**McuTypeId** <br/> |inyint  <br/> | Внешний <br/> |Тип сервера конференций, такие как conf:chat (для мгновенных сообщений) или conf:audio-видео. В [таблице UriTypes](uritypes.md) для получения дополнительных сведений см. <br/> |
   

