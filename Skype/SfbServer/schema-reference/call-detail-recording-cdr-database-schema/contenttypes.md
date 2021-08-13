---
title: Таблица ContentTypes в Skype для бизнеса Server 2015 г.
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: e3e38035-457c-4173-bdb9-d53a7420eba2
description: Таблица ContentTypes является вспомогательной таблице, в которой содержится список типов содержимого, используемых как для одноранговых сеансов, так и для сеансов конференций. Каждая запись в таблице представляет один тип содержимого.
ms.openlocfilehash: 6f15fe8bc5f4da7e12fa3b36de6b613fc1783b3d21e5903e2840f3cd22f5e139
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2021
ms.locfileid: "54336426"
---
# <a name="contenttypes-table-in-skype-for-business-server-2015"></a>Таблица ContentTypes в Skype для бизнеса Server 2015 г.
 
Таблица ContentTypes является вспомогательной таблице, в которой содержится список типов содержимого, используемых как для одноранговых сеансов, так и для сеансов конференций. Каждая запись в таблице представляет один тип содержимого.
  
|**Column**|**Тип данных**|**Key/Index**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**ContentTypeId** <br/> |int  <br/> |Primary  <br/> |Уникальный номер, идентифицирующий этот тип содержимого.  <br/> |
|**ContentType** <br/> |nvarchar (256)  <br/> ||Имя типа содержимого.  <br/> |
   

