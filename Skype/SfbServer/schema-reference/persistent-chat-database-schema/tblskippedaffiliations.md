---
title: tblSkippedAffiliations
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 0b129b54-a7a8-42a6-9279-0e08410c06ec
description: tblSkippedAffiliations содержит присоединение, которое не удалось прочитать (обычно из-за ошибок доступа к доменным службам Active Directory).
ms.openlocfilehash: 3061a399de804898d3dc2c616fb3766206c2d624
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831429"
---
# <a name="tblskippedaffiliations"></a>tblSkippedAffiliations
 
tblSkippedAffiliations содержит присоединение, которое не удалось прочитать (обычно из-за ошибок доступа к доменным службам Active Directory).
  
**Columns**

|**Столбец**|**Тип**|**Описание**|
|:-----|:-----|:-----|
|prinID  <br/> |int, not null  <br/> |Идентификатор субъекта.  <br/> |
|affDescription  <br/> |nvarchar (256), не NULL  <br/> |Строка, идентифицирующая принадлежность.  <br/> Формат: guid:  _{0}_ uri: _{1}_> id:  _{2}_ <br/> |
|updatedBy  <br/> |int, не NULL  <br/> |Идентификатор субъекта, обновившего эту строку. Он всегда равен 1 (системный пользователь) поскольку синхронизация Active Directory является единственным источником этих записей.  <br/> |
   
**Keys**

|**Столбцы**|**Описание**|
|:-----|:-----|
|\<prinID, affDescription\>  <br/> |Первичный ключ.  <br/> |
|prinID  <br/> |Внешний ключ с поиском в таблице tblPrincipal.prinID.  <br/> |
   

