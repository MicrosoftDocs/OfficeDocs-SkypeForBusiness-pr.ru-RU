---
title: Таблица Dialog
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4d93424f-9072-43f5-83c2-3d539e3e9ca6
description: Диалоговая таблица — это вспомогательная таблица; Каждая запись отображает диалоговое окно протокола SIP.
ms.openlocfilehash: e6bbaa3c40ebf53c5fd9fc410acca7779128bf39
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294959"
---
# <a name="dialog-table"></a>Таблица Dialog
 
Диалоговая таблица — это вспомогательная таблица; Каждая запись отображает диалоговое окно протокола SIP.
  
|**Столбец**|**Тип данных**|**Ключ/индекс**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**Конференцедатетиме** <br/> |datetime  <br/> |Primary  <br/> |Время, когда агент качества (QoE) получает первый отчет от вызывающего или вызываемого абонента. Используется в сочетании с Сессионсек для уникальной идентификации сеанса.  <br/> |
|**Сессионсек** <br/> |целое  <br/> |Primary  <br/> |Порядковый номер, чтобы отличать сеансы связи с одинаковым Конференцедатетиме.  <br/> |
|**Диалогид** <br/> |varchar (256)  <br/> ||ИДЕНТИФИКАТОР диалогового окна, который является глобально уникальным.  <br/> |
|**Диалогидчекксум** <br/> |целое  <br/> |индекса  <br/> |Контрольная сумма идентификатора диалогового окна.  <br/> |
   

