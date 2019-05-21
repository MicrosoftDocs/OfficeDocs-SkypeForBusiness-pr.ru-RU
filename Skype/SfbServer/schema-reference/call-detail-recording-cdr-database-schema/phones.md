---
title: Таблица Phones
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 41cb356d-9cc8-42b6-ac23-98a61b25aadc
description: Таблица phones является вспомогательной таблицей. Каждая запись в таблице хранит информацию об одном номере телефона, который участвует в звонках по протоколу VoIP с записями в базе данных.
ms.openlocfilehash: 684586f21b16c785bcc75458e5330c42aad2ccb4
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295946"
---
# <a name="phones-table"></a>Таблица Phones
 
Таблица phones является вспомогательной таблицей. Каждая запись в таблице хранит информацию об одном номере телефона, который участвует в звонках по протоколу VoIP с записями в базе данных.
  
|**Столбец**|**Тип данных**|**Ключ/индекс**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**Фонеид** <br/> |целое  <br/> |Primary  <br/> |Уникальный номер, идентифицирующий этот телефон.  <br/> |
|**Фонеури** <br/> |nvarchar (450)  <br/> | <br/> |Номер телефона.  <br/> |
|**Некступдатетс** <br/> |Датой  <br/> ||Метка времени (только для внутреннего использования).  <br/> Это поле было введено в Microsoft Lync Server 2013.  <br/> |
   

