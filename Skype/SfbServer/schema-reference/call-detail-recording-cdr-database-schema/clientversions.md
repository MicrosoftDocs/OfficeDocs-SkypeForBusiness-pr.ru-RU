---
title: Таблица ClientVersions в Skype для бизнеса Server 2015 г.
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 542316cf-a6db-4d52-ab28-8bf6d27a3b48
description: Таблица ClientVersions является вспомогательной таблицей, в которой хранится список различных типов и версий клиентов, которые приняли участие в сеансах, зарегистрированных в базе данных. Каждая запись в таблице представляет одну версию клиента.
ms.openlocfilehash: dd9afc6addef78bf255e6237f1b29f5cac4ee071
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/05/2022
ms.locfileid: "62386328"
---
# <a name="clientversions-table-in-skype-for-business-server-2015"></a>Таблица ClientVersions в Skype для бизнеса Server 2015 г.
 
Таблица ClientVersions является вспомогательной таблицей, в которой хранится список различных типов и версий клиентов, которые приняли участие в сеансах, зарегистрированных в базе данных. Каждая запись в таблице представляет одну версию клиента.
  
|**Столбец**|**Тип данных**|**Key/Index**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**VersionId** <br/> |**int** <br/> |Primary  <br/> |Уникальный номер, идентифицирующий данный тип и версию клиента.  <br/> |
|**Версия** <br/> |**nvarchar (256)** <br/> ||Название версии.  <br/> |
|**ClientType** <br/> |int  <br/> ||Указывает тип клиента, используемого в этом сеансе. Дополнительные сведения см. [в таблице UserAgentDef](useragentdef.md) . <br/> Это поле было внедрено в Microsoft Lync Server 2013.  <br/> |
   

