---
title: tblEnumAttribute
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 17f8b87e-36a6-4f6a-8630-7c76b61a7595
description: Тбленуматтрибуте — это жесткая таблица, которая содержит атрибуты видимости и поведения, которые используются в таблице node.
ms.openlocfilehash: b326ebe98592daccf7560dc90e299f31c158cd5c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295421"
---
# <a name="tblenumattribute"></a>tblEnumAttribute
 
Тбленуматтрибуте — это жесткая таблица, которая содержит атрибуты видимости и поведения, которые используются в таблице node.
  
**Столбцов**

|**Столбец**|**Тип**|**Описание**|
|:-----|:-----|:-----|
|attributeID  <br/> |smallint, NOT NULL  <br/> |Идентификатор атрибута.  <br/> |
|attributeName  <br/> |nvarchar (256), NOT NULL  <br/> |Имя атрибута.  <br/> |
   
**Ключ**

|**Столбец**|**Описание**|
|:-----|:-----|
|attributeID  <br/> |Первичный ключ.  <br/> |
   
**Значения таблицы**

|**attributeID**|**attributeName**|
|:-----|:-----|
|1  <br/> |Отображение.  <br/> |
|2  <br/> |Расширения.  <br/> |
   
## <a name="see-also"></a>См. также

[tblNode](tblnode.md)
