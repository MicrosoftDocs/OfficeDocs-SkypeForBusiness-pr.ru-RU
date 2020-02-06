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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 542316cf-a6db-4d52-ab28-8bf6d27a3b48
description: Таблица Клиентверсионс является вспомогательной таблицей, в которой хранится список различных типов клиентов и версий, которые принимали участие в сеансах, записанных в базе данных. Каждая запись в таблице представляет одну версию клиента.
ms.openlocfilehash: c616f7d44d138732e96f2d71c7fdf0197c75ca5c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815407"
---
# <a name="clientversions-table-in-skype-for-business-server-2015"></a>Таблица Клиентверсионс в Skype для бизнеса Server 2015
 
Таблица Клиентверсионс является вспомогательной таблицей, в которой хранится список различных типов клиентов и версий, которые принимали участие в сеансах, записанных в базе данных. Каждая запись в таблице представляет одну версию клиента.
  
|**Столбец**|**Тип данных**|**Ключ/индекс**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**VersionId** <br/> |**целое** <br/> |Primary  <br/> |Уникальный номер, показывающий этот тип клиента и версию.  <br/> |
|**Версия** <br/> |**nvarchar(256)** <br/> ||Название версии.  <br/> |
|**клиенттипе** <br/> |целое  <br/> ||Указывает тип клиента, используемого в сеансе. Для получения дополнительных сведений ознакомьтесь с [таблицей усеражентдеф](useragentdef.md) . <br/> Это поле было введено в Microsoft Lync Server 2013.  <br/> |
   

