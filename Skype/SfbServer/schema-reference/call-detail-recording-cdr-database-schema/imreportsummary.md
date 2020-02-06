---
title: Таблица Имрепортсуммари в Skype для бизнеса Server 2015
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
ms.assetid: 27ff9453-53f2-4fae-b637-70a086c9df96
description: Имрепортсуммаритабле предоставляет общий отчет о сеансах обмена мгновенными сообщениями, которые хранятся в Организации. Эта таблица введена в Microsoft Lync Server 2013.
ms.openlocfilehash: f845a882bb8bd6ba5ca434ffc42a34725cfeac51
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815147"
---
# <a name="imreportsummary-table-in-skype-for-business-server-2015"></a>Таблица Имрепортсуммари в Skype для бизнеса Server 2015
 
Имрепортсуммаритабле предоставляет общий отчет о сеансах обмена мгновенными сообщениями, которые хранятся в Организации. Эта таблица введена в Microsoft Lync Server 2013.
  
|**Столбец**|**Тип данных**|**Ключ/индекс**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**StartTime** <br/> |datetime  <br/> |Primary  <br/> |Дата и время начала сеанса обмена мгновенными сообщениями.  <br/> |
|**тимепериод** <br/> |char (1)  <br/> |Primary  <br/> ||
|**пулфкдн** <br/> |nvarchar (257)  <br/> |Primary  <br/> |Полное доменное имя пула, на котором размещается сеанс.  <br/> |
|**аустипе** <br/> |целое  <br/> |Primary  <br/> |Приоритет звонка (например, срочной или несрочный). Информация о приоритетах хранится в [таблице каллприоритиес в Skype для бизнеса Server 2015](callpriorities.md).  <br/> |
|**сессионкаунт** <br/> |bigint  <br/> |||
|**мсгкаунт** <br/> |bigint  <br/> ||Общее количество мгновенных сообщений, пересылаемых во время сеанса.  <br/> |
   

