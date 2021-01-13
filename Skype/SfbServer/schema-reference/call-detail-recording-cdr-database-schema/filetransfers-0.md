---
title: Таблица FileTransfers в Skype для бизнеса Server 2015
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
localization_priority: Normal
ms.assetid: 5368e67c-d8a9-43a1-9472-a839950dedb3
description: Каждая запись представляет один сеанс передачи файлов.
ms.openlocfilehash: fde871bb434a2aa458bc59cfdf098c82ba3a7093
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821699"
---
# <a name="filetransfers-table-in-skype-for-business-server-2015"></a>Таблица FileTransfers в Skype для бизнеса Server 2015
 
Каждая запись представляет один сеанс передачи файлов.
  
|**Столбец**|**Тип данных**|**Ключ/индекс**|**Details**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Основной, внешний  <br/> |Время запроса сеанса. В сочетании с параметром **SessionIdSeq** определяет сеанс уникальным образом. Дополнительные сведения см. в таблице [Dialogs в Skype для бизнеса Server 2015.](dialogs.md) <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Основной, внешний  <br/> |Идентификатор для идентификации сеанса. В сочетании с параметром **SessionIdTime** определяет сеанс уникальным образом. Дополнительные сведения см. в таблице [Dialogs в Skype для бизнеса Server 2015.](dialogs.md) <br/> |
|**Имя файла** <br/> |nvarchar(256)  <br/> ||Имя файла.  <br/> |
|**FileIdentity** <br/> |uniqueidentifier  <br/> ||Уникальный идентификатор, позволяющий разделять передачи файлов с одним именем.  <br/> |
|**Cookie** <br/> |nvarchar(128)  <br/> |Primary  <br/> |Используется для идентификации каждого последующего сообщения, как связанного с текущим.  <br/> |
|**Accept** <br/> |bit  <br/> ||Может иметь значение TRUE или NULL. Если значение равно TRUE, то значением параметров Reject и Cancel будет NULL.  <br/> |
|**Reject** <br/> |bit  <br/> ||Может иметь значение TRUE или NULL. Если значение равно TRUE, то значением параметров Accept и Cancel будет NULL.  <br/> |
|**Отмена** <br/> |bit  <br/> ||Может иметь значение TRUE или NULL. Если значение равно TRUE, то значением параметров Accept и Reject будет NULL.  <br/> |
|**LastModifiedTime** <br/> |Datetime  <br/> ||Для внутреннего использования службой мониторинга.  <br/> Это поле было впервые введено в Skype для бизнеса Server 2015.  <br/> |
   

