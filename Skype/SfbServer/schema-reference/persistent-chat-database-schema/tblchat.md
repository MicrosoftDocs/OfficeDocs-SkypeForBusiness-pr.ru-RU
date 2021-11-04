---
title: tblChat
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: b7fcf1b4-7a3f-4585-a6d9-95e7f030c7dc
description: Таблица tblChat содержит все сообщения чата.
ms.openlocfilehash: 12b5d1e7b7614ad68b054b5344c7758ca7eaa185
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/04/2021
ms.locfileid: "60761926"
---
# <a name="tblchat"></a>tblChat
 
Таблица tblChat содержит все сообщения чата.
  
**Columns**

|**Столбец**|**Тип**|**Описание**|
|:-----|:-----|:-----|
|channelId  <br/> |int, not null  <br/> |ИД узла.  <br/> |
|chatId  <br/> |bigint, not null  <br/> |Уникальный порядковый номер (для каждого ИД узла), определяющий порядок чата, который создается таблицей tblLastChatId.  <br/> |
|chatDate  <br/> |bigint, not null  <br/> |Метка времени для сообщения чата.  <br/> |
|userId  <br/> |int, not null  <br/> |ИД участника, отправителя сообщения.  <br/> |
|isAlert  <br/> |bit, not null  <br/> |True, если сообщение является оповещением. В противном случае — False.  <br/> |
|содержимое  <br/> |nvarchar (max), not null  <br/> | Содержимое чата (версия обычного текста). Обычно содержимое представлено в виде обычного текста за следующими исключениями: <br/>  Файлы, представленные в виде ссылок ma-filelink:. <br/>  Ссылки, представленные в виде элементов HTML (однако тип содержимого не может рассматриваться HTML). <br/>  Истории закодированы в формате "[STORY]....". <br/> |
|RTF  <br/> |varchar (max)  <br/> |Содержимое чата (версия RTF). Может быть Null, если клиент не предоставляет его.  <br/> |
   
**Ключ**

|**Столбец**|**Описание**|
|:-----|:-----|
|\<channelID, chatD\>  <br/> |Первичный ключ.  <br/> |
   

