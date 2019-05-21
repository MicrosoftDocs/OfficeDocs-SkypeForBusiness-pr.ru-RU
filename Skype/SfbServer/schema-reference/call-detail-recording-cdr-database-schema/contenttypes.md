---
title: Таблица "ContentType" в Skype для бизнеса Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e3e38035-457c-4173-bdb9-d53a7420eba2
description: Таблица ContentTypes является вспомогательной таблицей, в которой хранится список типов контента, используемых в одноранговых сеансах и сеансах конференц-связи. Каждая запись в таблице представляет один тип контента.
ms.openlocfilehash: b8422cbe95425ac79495c0506f4a94e70be3f9af
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296373"
---
# <a name="contenttypes-table-in-skype-for-business-server-2015"></a>Таблица "ContentType" в Skype для бизнеса Server 2015
 
Таблица ContentTypes является вспомогательной таблицей, в которой хранится список типов контента, используемых в одноранговых сеансах и сеансах конференц-связи. Каждая запись в таблице представляет один тип контента.
  
|**Столбец**|**Тип данных**|**Ключ/индекс**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**Контенттипеид** <br/> |целое  <br/> |Primary  <br/> |Уникальный номер, определяющий тип контента.  <br/> |
|**Контента** <br/> |nvarchar(256)  <br/> ||Имя типа контента.  <br/> |
   

