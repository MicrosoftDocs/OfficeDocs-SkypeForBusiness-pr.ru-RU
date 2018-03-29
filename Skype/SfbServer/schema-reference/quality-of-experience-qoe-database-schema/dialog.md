---
title: Таблица Dialog
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4d93424f-9072-43f5-83c2-3d539e3e9ca6
description: В таблице диалогового окна представляет собой вспомогательную таблицу; Каждая запись представляет один диалоговое окно Session Initiation Protocol (SIP).
ms.openlocfilehash: 0380f9c7c48ff7d3b26b9ea5442fb5ac2155f785
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="dialog-table"></a>Таблица Dialog
 
В таблице диалогового окна представляет собой вспомогательную таблицу; Каждая запись представляет один диалоговое окно Session Initiation Protocol (SIP).
  
|**Столбец**|**Тип данных**|**Ключ или индекс**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Primary  <br/> |Время, когда агент работы (QoE) получает первый отчет от вызывающего и вызываемого абонента. Используется в сочетании с SessionSeq для уникальной идентификации сеанса.  <br/> |
|**SessionSeq** <br/> |целое  <br/> |Primary  <br/> |Порядковый номер, позволяющий различать сеансы, когда у них есть же ConferenceDateTime.  <br/> |
|**DialogID** <br/> |varchar(256)  <br/> ||Глобальный уникальный идентификатор диалогового окна.  <br/> |
|**DialogIDChecksum** <br/> |целое  <br/> |Индекс  <br/> |Контрольная сумма идентификатора диалогового окна.  <br/> |
   

