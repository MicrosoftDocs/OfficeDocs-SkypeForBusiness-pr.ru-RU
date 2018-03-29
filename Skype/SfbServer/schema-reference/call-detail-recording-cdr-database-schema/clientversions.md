---
title: Таблица ClientVersions в Скайп для Business Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 542316cf-a6db-4d52-ab28-8bf6d27a3b48
description: Таблица ClientVersions — собой вспомогательную таблицу, в которой хранится список различных типов клиентов и версии, которые участвовали в сеансах, записанные в базе данных. Каждая запись в таблице представляет одну версию клиента.
ms.openlocfilehash: 488c7f4211eacb6fc496d6198258c119641ebd14
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="clientversions-table-in-skype-for-business-server-2015"></a>Таблица ClientVersions в Скайп для Business Server 2015
 
Таблица ClientVersions — собой вспомогательную таблицу, в которой хранится список различных типов клиентов и версии, которые участвовали в сеансах, записанные в базе данных. Каждая запись в таблице представляет одну версию клиента.
  
|**Столбец**|**Тип данных**|**Ключ или индекс**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**VersionId** <br/> |**int** <br/> |Primary  <br/> |Уникальный номер, идентифицирующий этот тип и версию клиента.  <br/> |
|**Версия** <br/> |**nvarchar(256)** <br/> ||Название версии.  <br/> |
|**Типа клиента** <br/> |целое  <br/> ||Указывает тип клиента, используемая в сеансе. [Таблица useragentdef](useragentdef.md) для получения дополнительных сведений см. <br/> В этом поле было представлено в Microsoft Lync Server 2013.  <br/> |
   

