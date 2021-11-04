---
title: Таблица ContentTypes в Skype для бизнеса Server 2015 г.
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: e3e38035-457c-4173-bdb9-d53a7420eba2
description: Таблица ContentTypes является вспомогательной таблице, в которой содержится список типов содержимого, используемых как для одноранговых сеансов, так и для сеансов конференций. Каждая запись в таблице представляет один тип содержимого.
ms.openlocfilehash: 98e360f218de3cd3e998ae09e5bc4abd83d5b28b
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/04/2021
ms.locfileid: "60744015"
---
# <a name="contenttypes-table-in-skype-for-business-server-2015"></a>Таблица ContentTypes в Skype для бизнеса Server 2015 г.
 
Таблица ContentTypes является вспомогательной таблице, в которой содержится список типов содержимого, используемых как для одноранговых сеансов, так и для сеансов конференций. Каждая запись в таблице представляет один тип содержимого.
  
|**Столбец**|**Тип данных**|**Key/Index**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**ContentTypeId** <br/> |int  <br/> |Primary  <br/> |Уникальный номер, идентифицирующий этот тип содержимого.  <br/> |
|**ContentType** <br/> |nvarchar (256)  <br/> ||Имя типа содержимого.  <br/> |
   

