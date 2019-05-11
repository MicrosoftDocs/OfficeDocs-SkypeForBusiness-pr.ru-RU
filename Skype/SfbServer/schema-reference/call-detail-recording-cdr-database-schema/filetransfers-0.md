---
title: Таблица FileTransfers в Скайп для Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/15/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5368e67c-d8a9-43a1-9472-a839950dedb3
description: Каждая запись представляет один сеанс передачи файлов.
ms.openlocfilehash: 2d249cb303bca7726a8c666bc8b906841be5ce1d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33901061"
---
# <a name="filetransfers-table-in-skype-for-business-server-2015"></a>Таблица FileTransfers в Скайп для Business Server 2015
 
Каждая запись представляет один сеанс передачи файлов.
  
|**Столбец**|**Тип данных**|**Ключ/индекс**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Основной, внешний  <br/> |Время запроса сеанса. Используется совместно с **SessionIdSeq** для уникальной идентификации сеанса. В разделе [диалоговых окон в таблице в Скайп для Business Server 2015](dialogs.md) для получения дополнительных сведений. <br/> |
|**SessionIdSeq** <br/> |целое  <br/> |Основной, внешний  <br/> |Номер идентификатора для идентификации сеанса. Используется в сочетании с **SessionIdTime** для уникальной идентификации сеанса. В разделе [диалоговых окон в таблице в Скайп для Business Server 2015](dialogs.md) для получения дополнительных сведений. <br/> |
|**Имя файла** <br/> |nvarchar(256)  <br/> ||Имя файла.  <br/> |
|**FileIdentity** <br/> |uniqueidentifier  <br/> ||Уникальный идентификатор для различения операций передачи файлов с одинаковыми именами файлов.  <br/> |
|**Файл cookie** <br/> |nvarchar(128)  <br/> |Primary  <br/> |Используется для идентификации каждого последующего сообщения как связанного с этим сообщением.  <br/> |
|**Прием** <br/> |бит  <br/> ||Может быть значение TRUE или значение NULL. Если значение TRUE, затем Отклонить и Отмена будет NULL.  <br/> |
|**Отклонение** <br/> |бит  <br/> ||Может быть значение TRUE или значение NULL. Если значение TRUE, затем принять и Отмена будет NULL.  <br/> |
|**Отмена**. <br/> |бит  <br/> ||Может быть значение TRUE или значение NULL. Если значение TRUE, то принятия и отклонения будет NULL.  <br/> |
|**LastModifiedTime** <br/> |Даты и времени  <br/> ||Для внутреннего использования службой мониторинга.  <br/> В этом поле было представлено в Скайп для Business Server 2015.  <br/> |
   

