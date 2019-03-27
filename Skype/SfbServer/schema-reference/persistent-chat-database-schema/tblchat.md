---
title: tblChat
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b7fcf1b4-7a3f-4585-a6d9-95e7f030c7dc
description: Таблица tblChat содержит все сообщения чата.
ms.openlocfilehash: 54e19fe729d9f96afb04d22a917864118de75efe
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30881307"
---
# <a name="tblchat"></a>tblChat
 
Таблица tblChat содержит все сообщения чата.
  
**Столбцы**

|**Столбец**|**Тип**|**Описание**.|
|:-----|:-----|:-----|
|channelId  <br/> |int, не null  <br/> |ИД узла.  <br/> |
|chatId  <br/> |bigint, не может быть null  <br/> |Уникальный порядковый номер (для каждого ИД узла), определяющий порядок чата, таблицей tblLastChatId.  <br/> |
|chatDate  <br/> |bigint, не может быть null  <br/> |Метка времени для сообщения чата.  <br/> |
|идентификатор пользователя  <br/> |int, не null  <br/> |Идентификатор субъекта Плакат.  <br/> |
|isAlert  <br/> |bit, не может быть null  <br/> |Значение true, если сообщение сообщения с оповещением. Значение false, если он не установлен.  <br/> |
|контент  <br/> |nvarchar (max), отлично от null  <br/> | Содержимое разговоров (текстовая версия). Содержимое обычно находится в обычный текст со следующими исключениями: <br/>  Файлы, представленные в виде ma-filelink: ссылки. <br/>  Ссылки, представленные в виде элементов HTML (Однако тип содержимого не может рассматриваться HTML). <br/>  Статьи, помеченные как «[STORY]....»-формату. <br/> |
|Формат RTF  <br/> |varchar(max)  <br/> |Содержимое разговоров (версия RTF). Может быть Null, если клиент не предоставляет его.  <br/> |
   
**Ключ**

|**Столбец**|**Описание**.|
|:-----|:-----|
|\<channelID chatD\>  <br/> |Первичный ключ.  <br/> |
   

