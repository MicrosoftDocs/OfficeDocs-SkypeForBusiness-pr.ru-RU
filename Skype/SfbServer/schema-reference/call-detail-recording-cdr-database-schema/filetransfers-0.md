---
title: Таблица FileTransfers в Skype для бизнеса Server 2015 г.
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 5368e67c-d8a9-43a1-9472-a839950dedb3
description: Каждая запись представляет один сеанс передачи файлов.
ms.openlocfilehash: 59a8346bb000af9c556306d1314c93e45feb28ec
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/26/2021
ms.locfileid: "58593423"
---
# <a name="filetransfers-table-in-skype-for-business-server-2015"></a>Таблица FileTransfers в Skype для бизнеса Server 2015 г.
 
Каждая запись представляет один сеанс передачи файлов.
  
|**Столбец**|**Тип данных**|**Key/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Основной, внешний  <br/> |Время запроса сеанса. В сочетании с параметром **SessionIdSeq** определяет сеанс уникальным образом. Дополнительные сведения см. в таблице [Диалоги Skype для бизнеса Server 2015](dialogs.md) г. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Основной, внешний  <br/> |Идентификатор для идентификации сеанса. В сочетании с параметром **SessionIdTime** определяет сеанс уникальным образом. Дополнительные сведения см. в таблице [Диалоги Skype для бизнеса Server 2015](dialogs.md) г. <br/> |
|**Имя файла** <br/> |nvarchar (256)  <br/> ||Имя файла.  <br/> |
|**FileIdentity** <br/> |uniqueidentifier  <br/> ||Уникальный идентификатор, позволяющий разделять передачи файлов с одним именем.  <br/> |
|**Cookie** <br/> |nvarchar (128)  <br/> |Primary  <br/> |Используется для идентификации каждого последующего сообщения, как связанного с текущим.  <br/> |
|**Accept** <br/> |bit  <br/> ||Может иметь значение TRUE или NULL. Если значение равно TRUE, то значением параметров Reject и Cancel будет NULL.  <br/> |
|**Reject** <br/> |bit  <br/> ||Может иметь значение TRUE или NULL. Если значение равно TRUE, то значением параметров Accept и Cancel будет NULL.  <br/> |
|**Отмена** <br/> |bit  <br/> ||Может иметь значение TRUE или NULL. Если значение равно TRUE, то значением параметров Accept и Reject будет NULL.  <br/> |
|**LastModifiedTime** <br/> |Datetime  <br/> ||Для внутреннего использования службой мониторинга.  <br/> Это поле было введено Skype для бизнеса Server 2015 г.  <br/> |
   

