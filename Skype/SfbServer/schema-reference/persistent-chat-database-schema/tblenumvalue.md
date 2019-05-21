---
title: tblEnumValue
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a33df20c-d19d-4f5c-b012-29dab8fb9200
description: Тбленумвалуе — это жесткая таблица, содержащая значения видимости и поведения атрибутов, используемых в таблице node.
ms.openlocfilehash: bf1ddf75fc7b7fd78c85f47626b465a4d74e5ca2
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295428"
---
# <a name="tblenumvalue"></a>tblEnumValue
 
Тбленумвалуе — это жесткая таблица, содержащая значения видимости и поведения атрибутов, используемых в таблице node.
  
**Столбцов**

|**Столбец**|**Тип**|**Описание**|
|:-----|:-----|:-----|
|Валуеид  <br/> |smallint, NOT NULL  <br/> |Идентификатор значения.  <br/> |
|attributeID  <br/> |smallint, NOT NULL  <br/> |Идентификатор атрибута.  <br/> |
|attributeValue  <br/> |nvarchar (256), NOT NULL  <br/> |Имя значения.  <br/> |
   
**Параметры**

|**Столбец**|**Описание**|
|:-----|:-----|
|Валуеид  <br/> |Первичный ключ.  <br/> |
|attributeID  <br/> |Внешний ключ с подстановкой в таблице Тбленуматтрибуте. attributeID.  <br/> |
   
**Значения таблицы**

|**Валуеид**|**attributeID**|**attributeValue**|
|:-----|:-----|:-----|
|2  <br/> |1  <br/> |закрытые  <br/> |
|3  <br/> |1  <br/> |област  <br/> |
|4  <br/> |2  <br/> |нормальный  <br/> |
|5  <br/> |2  <br/> |Аудиториум  <br/> |
|6  <br/> |1  <br/> |запуска  <br/> |
   
## <a name="see-also"></a>См. также

[tblNode](tblnode.md)
