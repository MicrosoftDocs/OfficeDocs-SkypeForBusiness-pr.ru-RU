---
title: Таблица Клиентверсионс в Skype для бизнеса Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 542316cf-a6db-4d52-ab28-8bf6d27a3b48
description: Таблица Клиентверсионс является вспомогательной таблицей, в которой хранится список различных типов клиентов и версий, которые принимали участие в сеансах, записанных в базе данных. Каждая запись в таблице представляет одну версию клиента.
ms.openlocfilehash: b42bc79fb04ca4ce2ef88fb7c280db7bc281e23b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296513"
---
# <a name="clientversions-table-in-skype-for-business-server-2015"></a>Таблица Клиентверсионс в Skype для бизнеса Server 2015
 
Таблица Клиентверсионс является вспомогательной таблицей, в которой хранится список различных типов клиентов и версий, которые принимали участие в сеансах, записанных в базе данных. Каждая запись в таблице представляет одну версию клиента.
  
|**Столбец**|**Тип данных**|**Ключ/индекс**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**VersionId** <br/> |**целое** <br/> |Primary  <br/> |Уникальный номер, показывающий этот тип клиента и версию.  <br/> |
|**Версия** <br/> |**nvarchar(256)** <br/> ||Название версии.  <br/> |
|**Клиенттипе** <br/> |целое  <br/> ||Указывает тип клиента, используемого в сеансе. Для получения дополнительных сведений ознакомьтесь с [таблицей усеражентдеф](useragentdef.md) . <br/> Это поле было введено в Microsoft Lync Server 2013.  <br/> |
   

