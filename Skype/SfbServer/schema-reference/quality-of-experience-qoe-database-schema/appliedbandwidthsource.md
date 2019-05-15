---
title: Таблица AppliedBandwidthSource
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 24fb3caf-19b3-4c0a-90d7-ca5d53de32ad
description: Таблица appliedbandwidthsource представляет собой вспомогательную таблицу. Каждая запись представляет один источник.
ms.openlocfilehash: 49e4fd4b2c2543399d073d5d03e8cccad8b0038e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33924852"
---
# <a name="appliedbandwidthsource-table"></a>Таблица AppliedBandwidthSource
 
Таблица appliedbandwidthsource представляет собой вспомогательную таблицу. Каждая запись представляет один источник.
  
|**Столбец**|**Тип данных**|**Ключ/индекс**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**AppliedBandwidthSourceKey** <br/> |целое  <br/> |Primary  <br/> |Уникальный номер, определяющий источник.  <br/> |
|**AppliedBandwidthSource** <br/> |varchar(256)  <br/> |Уникальный  <br/> |Это источник накладываемого ограничение пропускной способности. Этот параметр описывает где готовится к ограничение пропускной способности из (например, «Сервер политики», «ВКЛЮЧИТЬ сервер» или «Модальность»).  <br/> |
   

