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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 17f8b87e-36a6-4f6a-8630-7c76b61a7595
description: Тбленуматтрибуте — это жесткая таблица, которая содержит атрибуты видимости и поведения, которые используются в таблице node.
ms.openlocfilehash: 8244e2fb6ace6c4ed73f017f52df0c85d1f02315
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814617"
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
