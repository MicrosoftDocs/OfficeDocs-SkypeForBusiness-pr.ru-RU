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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 4d93424f-9072-43f5-83c2-3d539e3e9ca6
description: Диалоговая таблица — это вспомогательная таблица; Каждая запись отображает диалоговое окно протокола SIP.
ms.openlocfilehash: 85d4a9f16a88db386565c065161eedeb61fba913
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41809537"
---
# <a name="dialog-table"></a>Таблица Dialog
 
Диалоговая таблица — это вспомогательная таблица; Каждая запись отображает диалоговое окно протокола SIP.
  
|**Столбец**|**Тип данных**|**Ключ/индекс**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**конференцедатетиме** <br/> |datetime  <br/> |Primary  <br/> |Время, когда агент качества (QoE) получает первый отчет от вызывающего или вызываемого абонента. Используется в сочетании с Сессионсек для уникальной идентификации сеанса.  <br/> |
|**сессионсек** <br/> |целое  <br/> |Primary  <br/> |Порядковый номер, чтобы отличать сеансы связи с одинаковым Конференцедатетиме.  <br/> |
|**диалогид** <br/> |varchar (256)  <br/> ||ИДЕНТИФИКАТОР диалогового окна, который является глобально уникальным.  <br/> |
|**диалогидчекксум** <br/> |целое  <br/> |индекса  <br/> |Контрольная сумма идентификатора диалогового окна.  <br/> |
   

