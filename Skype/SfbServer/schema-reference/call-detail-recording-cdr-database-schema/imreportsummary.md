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
localization_priority: Normal
ms.assetid: 27ff9453-53f2-4fae-b637-70a086c9df96
description: Имрепортсуммаритабле предоставляет общий отчет о сеансах обмена мгновенными сообщениями, которые хранятся в Организации. Эта таблица введена в Microsoft Lync Server 2013.
ms.openlocfilehash: 647b8dc3e48e56d126a65f524de90954b7aeca8f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296128"
---
# <a name="imreportsummary-table-in-skype-for-business-server-2015"></a>Таблица Имрепортсуммари в Skype для бизнеса Server 2015
 
Имрепортсуммаритабле предоставляет общий отчет о сеансах обмена мгновенными сообщениями, которые хранятся в Организации. Эта таблица введена в Microsoft Lync Server 2013.
  
|**Столбец**|**Тип данных**|**Ключ/индекс**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**StartTime** <br/> |datetime  <br/> |Primary  <br/> |Дата и время начала сеанса обмена мгновенными сообщениями.  <br/> |
|**Тимепериод** <br/> |char (1)  <br/> |Primary  <br/> ||
|**Пулфкдн** <br/> |nvarchar (257)  <br/> |Primary  <br/> |Полное доменное имя пула, на котором размещается сеанс.  <br/> |
|**Аустипе** <br/> |целое  <br/> |Primary  <br/> |Приоритет звонка (например, срочной или несрочный). Информация о приоритетах хранится в [таблице каллприоритиес в Skype для бизнеса Server 2015](callpriorities.md).  <br/> |
|**Сессионкаунт** <br/> |bigint  <br/> |||
|**Мсгкаунт** <br/> |bigint  <br/> ||Общее количество мгновенных сообщений, пересылаемых во время сеанса.  <br/> |
   

