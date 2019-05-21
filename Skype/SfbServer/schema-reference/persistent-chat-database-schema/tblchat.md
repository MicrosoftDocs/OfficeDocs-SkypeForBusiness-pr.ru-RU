---
title: tblChat
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b7fcf1b4-7a3f-4585-a6d9-95e7f030c7dc
description: Тблчат включает в себя все сообщения чата.
ms.openlocfilehash: 15c7030fe14f62c5d32af54c0f5a6901da3f977b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295540"
---
# <a name="tblchat"></a>tblChat
 
Тблчат включает в себя все сообщения чата.
  
**Столбцов**

|**Столбец**|**Тип**|**Описание**|
|:-----|:-----|:-----|
|Чаннелид  <br/> |int, NOT NULL  <br/> |Идентификатор узла.  <br/> |
|Чатид  <br/> |bigint, NOT NULL  <br/> |Уникальный порядковый номер (код узла), который определяет порядок помещения в чат, созданный Тблластчатид таблицей.  <br/> |
|Чатдате  <br/> |bigint, NOT NULL  <br/> |Метка времени для сообщения чата.  <br/> |
|Идентификатора пользователя  <br/> |int, NOT NULL  <br/> |Идентификатор участника плаката.  <br/> |
|"о себе"  <br/> |bit, NOT NULL  <br/> |Значение true, если сообщение является предупредительным сообщением. В противном случае — false.  <br/> |
|конфликтов  <br/> |nvarchar (max), NOT NULL  <br/> | Содержимое чата (версия обычного текста). Содержимое обычно задается в виде обычного текста со следующими исключениями: <br/>  Файлы представлены в виде ссылок MA-филелинк: Links. <br/>  Ссылки представлены в виде HTML-элемента (несмотря на то, что тип контента не может считаться HTML). <br/>  Истории в формате "[История]........". <br/> |
|RTF  <br/> |varchar (max)  <br/> |Содержимое чата (версия RTF). Может иметь значение null, если клиент не предоставил его.  <br/> |
   
**Ключ**

|**Столбец**|**Описание**|
|:-----|:-----|
|\<Чаннелид, чат\>  <br/> |Первичный ключ.  <br/> |
   

