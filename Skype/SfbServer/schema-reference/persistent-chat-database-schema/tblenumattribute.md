---
title: tblEnumAttribute
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 17f8b87e-36a6-4f6a-8630-7c76b61a7595
description: tblEnumAttribute — это таблица содержит атрибуты Visibility и Behavior, используемые в таблице Node.
ms.openlocfilehash: 7555656f02fa7808e54100c03de8f80e0e078678
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30879702"
---
# <a name="tblenumattribute"></a>tblEnumAttribute
 
tblEnumAttribute — это таблица содержит атрибуты Visibility и Behavior, используемые в таблице Node.
  
**Столбцы**

|**Столбец**|**Тип**|**Описание**.|
|:-----|:-----|:-----|
|attributeID  <br/> |smallint, не может быть null  <br/> |Идентификатор атрибута.  <br/> |
|Имя_атрибута  <br/> |nvarchar (256), отлично от null  <br/> |Имя атрибута.  <br/> |
   
**Ключ**

|**Столбец**|**Описание**.|
|:-----|:-----|
|attributeID  <br/> |Первичный ключ.  <br/> |
   
**Значения таблицы**

|**attributeID**|**Имя_атрибута**|
|:-----|:-----|
|1  <br/> |Видимость.  <br/> |
|2  <br/> |Поведение.  <br/> |
   
## <a name="see-also"></a>См. также

[tblNode](tblnode.md)
