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
localization_priority: Normal
ms.assetid: b986f76f-f16e-4e5e-96cb-6e8f7f9b42ee
description: В представлении UserAgent хранятся сведения о агентах пользователей, которые были вовлечены в сеансы с записями в базе данных. Это представление было представлено в Microsoft Lync Server 2013.
ms.openlocfilehash: 874a9c986ec77c3e19b557cd65dcf6dbeb045752
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294609"
---
# <a name="useragent-view"></a>Представление "UserAgent"
 
В представлении UserAgent хранятся сведения о агентах пользователей, которые были вовлечены в сеансы с записями в базе данных. Это представление было представлено в Microsoft Lync Server 2013.
  
|**Столбец**|**Тип данных**|**Сведения**|
|:-----|:-----|:-----|
|Усераженткэй  <br/> |целое  <br/> |Уникальный номер, идентифицирующий агент пользователя.  <br/> |
|UserAgent  <br/> |nvarchar(256)  <br/> |Строка агента пользователя.  <br/> |
|Уатипе  <br/> |smallint  <br/> |Тип агента пользователя. Дополнительные сведения приведены в [таблице UserAgent](useragent.md) . <br/> |
|Уакатегори  <br/> |nvarchar (64)  <br/> |Категория, к которой принадлежит агент пользователя. Например, агент пользователя КонференЦинг_аттендант_ 1.0 принадлежит к Уакатегори Каа.  <br/> |
   

