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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b7fcf1b4-7a3f-4585-a6d9-95e7f030c7dc
description: Тблчат включает в себя все сообщения чата.
ms.openlocfilehash: 7221136c435c1d4af836174ddfde5cbd02f4c5f6
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814677"
---
# <a name="tblchat"></a>tblChat
 
Тблчат включает в себя все сообщения чата.
  
**Столбцов**

|**Столбец**|**Тип**|**Описание**|
|:-----|:-----|:-----|
|чаннелид  <br/> |int, NOT NULL  <br/> |Идентификатор узла.  <br/> |
|чатид  <br/> |bigint, NOT NULL  <br/> |Уникальный порядковый номер (код узла), который определяет порядок помещения в чат, созданный Тблластчатид таблицей.  <br/> |
|чатдате  <br/> |bigint, NOT NULL  <br/> |Метка времени для сообщения чата.  <br/> |
|Идентификатора пользователя  <br/> |int, NOT NULL  <br/> |Идентификатор участника плаката.  <br/> |
|"о себе"  <br/> |bit, NOT NULL  <br/> |Значение true, если сообщение является предупредительным сообщением. В противном случае — false.  <br/> |
|конфликтов  <br/> |nvarchar (max), NOT NULL  <br/> | Содержимое чата (версия обычного текста). Содержимое обычно задается в виде обычного текста со следующими исключениями: <br/>  Файлы представлены в виде ссылок MA-филелинк: Links. <br/>  Ссылки представлены в виде HTML-элемента (несмотря на то, что тип контента не может считаться HTML). <br/>  Истории в формате "[История]........". <br/> |
|RTF  <br/> |varchar (max)  <br/> |Содержимое чата (версия RTF). Может иметь значение null, если клиент не предоставил его.  <br/> |
   
**Ключ**

|**Столбец**|**Описание**|
|:-----|:-----|
|\<Чаннелид, чат\>  <br/> |Первичный ключ.  <br/> |
   

