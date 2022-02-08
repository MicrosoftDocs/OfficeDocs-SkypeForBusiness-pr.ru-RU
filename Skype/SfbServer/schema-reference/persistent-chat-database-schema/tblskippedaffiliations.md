---
title: tblSkippedAffiliations
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 0b129b54-a7a8-42a6-9279-0e08410c06ec
description: tblSkippedAffiliations содержит присоединение, которое не удалось прочитать (как правило, из-за ошибок доступа к службам доступа к доменам Active Directory).
ms.openlocfilehash: b0996e3208e760c55b1b9d621d00e92a8e7a7112
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/05/2022
ms.locfileid: "62394791"
---
# <a name="tblskippedaffiliations"></a>tblSkippedAffiliations
 
tblSkippedAffiliations содержит присоединение, которое не удалось прочитать (как правило, из-за ошибок доступа к службам доступа к доменам Active Directory).
  
**Columns**

|**Столбец**|**Тип**|**Описание**|
|:-----|:-----|:-----|
|prinID  <br/> |int, not null  <br/> |Идентификатор субъекта.  <br/> |
|affDescription  <br/> |nvarchar (256), не NULL  <br/> |Строка, идентифицирующая принадлежность.  <br/> Формат: guid:  _{0}_ uri: _{1}_> id:  _{2}_ <br/> |
|updatedBy  <br/> |int, не NULL  <br/> |Идентификатор субъекта, обновившего эту строку. Он всегда равен 1 (системный пользователь) поскольку синхронизация Active Directory является единственным источником этих записей.  <br/> |
   
**Keys**

|**Column(s)**|**Описание**|
|:-----|:-----|
|\<prinID, affDescription\>  <br/> |Первичный ключ.  <br/> |
|prinID  <br/> |Внешний ключ с поиском в таблице tblPrincipal.prinID.  <br/> |
   

