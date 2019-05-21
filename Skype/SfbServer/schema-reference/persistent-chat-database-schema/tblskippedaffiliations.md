---
title: tblSkippedAffiliations
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0b129b54-a7a8-42a6-9279-0e08410c06ec
description: Тблскиппедаффилиатионс включает назначения, которые не удалось прочитать (обычно из-за ошибок доступа к доменным службам Active Directory).
ms.openlocfilehash: 481bf92a4014bf2af8e1c4794d1793f2c93e7c36
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295155"
---
# <a name="tblskippedaffiliations"></a>tblSkippedAffiliations
 
Тблскиппедаффилиатионс включает назначения, которые не удалось прочитать (обычно из-за ошибок доступа к доменным службам Active Directory).
  
**Столбцов**

|**Столбец**|**Тип**|**Описание**|
|:-----|:-----|:-----|
|Принид  <br/> |int, NOT NULL  <br/> |Идентификатор участника.  <br/> |
|Аффдескриптион  <br/> |nvarchar (256), NOT NULL  <br/> |Строка, указывающая на принадлежность.  <br/> Формат: GUID: _{0}_ URI: _{1}__гт_ ID:_{2}_ <br/> |
|Упдатедби  <br/> |int, NOT NULL  <br/> |Идентификатор участника, который обновил эту строку. Это всегда 1 (Системный пользователь), так как служба каталогов Active Directory — это единственный источник этих записей.  <br/> |
   
**Параметры**

|**Столбцы (-ы)**|**Описание**|
|:-----|:-----|
|\<Принид, Аффдескриптион\>  <br/> |Первичный ключ.  <br/> |
|Принид  <br/> |Внешний ключ с подстановкой в таблице ТблпринЦипал. Принид.  <br/> |
   

