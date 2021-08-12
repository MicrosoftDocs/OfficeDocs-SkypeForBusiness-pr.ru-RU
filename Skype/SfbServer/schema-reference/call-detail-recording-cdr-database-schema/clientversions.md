---
title: Таблица ClientVersions в Skype для бизнеса Server 2015 г.
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
ms.assetid: 542316cf-a6db-4d52-ab28-8bf6d27a3b48
description: Таблица ClientVersions является вспомогательной таблицей, в которой хранится список различных типов и версий клиентов, которые приняли участие в сеансах, зарегистрированных в базе данных. Каждая запись в таблице представляет одну версию клиента.
ms.openlocfilehash: 1cf2f237fd05937f8eea9a8c7f180ae43418fd586b59c99679770efa2205af88
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2021
ms.locfileid: "54341774"
---
# <a name="clientversions-table-in-skype-for-business-server-2015"></a>Таблица ClientVersions в Skype для бизнеса Server 2015 г.
 
Таблица ClientVersions является вспомогательной таблицей, в которой хранится список различных типов и версий клиентов, которые приняли участие в сеансах, зарегистрированных в базе данных. Каждая запись в таблице представляет одну версию клиента.
  
|**Column**|**Тип данных**|**Key/Index**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**VersionId** <br/> |**int** <br/> |Primary  <br/> |Уникальный номер, идентифицирующий данный тип и версию клиента.  <br/> |
|**Версия** <br/> |**nvarchar (256)** <br/> ||Название версии.  <br/> |
|**ClientType** <br/> |int  <br/> ||Указывает тип клиента, используемого в этом сеансе. Дополнительные сведения см. [в таблице UserAgentDef.](useragentdef.md) <br/> Это поле было внедрено в Microsoft Lync Server 2013.  <br/> |
   

