---
title: Таблица ContentTypes в Скайп для Business Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e3e38035-457c-4173-bdb9-d53a7420eba2
description: Таблица ContentTypes представляет собой вспомогательную таблицу, в которой хранится список типов контента, используемые в сеансах peer-to-peer и конференциям. Каждая запись в таблице представляет один тип контента.
ms.openlocfilehash: 207e2a4e6ba605950181c437c236205fc8b2778f
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="contenttypes-table-in-skype-for-business-server-2015"></a>Таблица ContentTypes в Скайп для Business Server 2015
 
Таблица ContentTypes представляет собой вспомогательную таблицу, в которой хранится список типов контента, используемые в сеансах peer-to-peer и конференциям. Каждая запись в таблице представляет один тип контента.
  
|**Столбец**|**Тип данных**|**Ключ или индекс**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**ContentTypeId** <br/> |целое  <br/> |Primary  <br/> |Уникальный номер, идентифицирующий тип контента.  <br/> |
|**ContentType** <br/> |nvarchar(256)  <br/> ||Имя типа контента.  <br/> |
   

