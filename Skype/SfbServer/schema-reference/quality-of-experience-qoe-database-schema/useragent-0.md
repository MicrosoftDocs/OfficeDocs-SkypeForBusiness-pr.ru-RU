---
title: Представление "UserAgent"
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
ms.assetid: b986f76f-f16e-4e5e-96cb-6e8f7f9b42ee
description: В представлении UserAgent хранятся сведения о агентах пользователей, которые были вовлечены в сеансы с записями в базе данных. Это представление было представлено в Microsoft Lync Server 2013.
ms.openlocfilehash: 76ac99b1fdadbeb6817b36483f4fe5762db47333
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41805087"
---
# <a name="useragent-view"></a>Представление "UserAgent"
 
В представлении UserAgent хранятся сведения о агентах пользователей, которые были вовлечены в сеансы с записями в базе данных. Это представление было представлено в Microsoft Lync Server 2013.
  
|**Столбец**|**Тип данных**|**Сведения**|
|:-----|:-----|:-----|
|усераженткэй  <br/> |целое  <br/> |Уникальный номер, идентифицирующий агент пользователя.  <br/> |
|UserAgent  <br/> |nvarchar(256)  <br/> |Строка агента пользователя.  <br/> |
|уатипе  <br/> |smallint  <br/> |Тип агента пользователя. Дополнительные сведения приведены в [таблице UserAgent](useragent.md) . <br/> |
|уакатегори  <br/> |nvarchar (64)  <br/> |Категория, к которой принадлежит агент пользователя. Например, агент пользователя Conferencing_Attendant_1 .0 принадлежит Уакатегори Каа.  <br/> |
   

