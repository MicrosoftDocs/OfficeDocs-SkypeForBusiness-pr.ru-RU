---
title: tblPreference
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f94eb128-f782-42ff-a568-ed3529573bc8
description: tblPreference содержит параметры клиента пользователей. Обычно используется клиентами предшествующих Lync 2013.
ms.openlocfilehash: 28656951c80e6e4010e6ca559e3f650e2b9bac4b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="tblpreference"></a>tblPreference
 
tblPreference содержит параметры клиента пользователей. Обычно используется клиентами предшествующих Lync 2013.
  
**Столбцы**

|**Столбец**|**Тип**|**Описание**|
|:-----|:-----|:-----|
|prefLabel  <br/> |nvarchar (255), отлично от null  <br/> |Метка имеет формат, таких как: \<uri sip пользователя\>|имя пользователя. \<набор установок\>.  <br/> |
|prefSeqID  <br/> |int, не null  <br/> |Порядковый номер (каждой отдельной метки) для управления версиями.  <br/> |
|prefContent  <br/> |nvarchar (максимум)  <br/> |Зашифрованное содержимое.  <br/> |
|lastModifiedBy  <br/> |int, не null  <br/> |Идентификатор субъекта, обновившего.  <br/> |
   
**Ключ**

|**Столбец**|**Описание**|
|:-----|:-----|
|\<prefLabel prefSeqID\>  <br/> |Первичный ключ.  <br/> |
   

