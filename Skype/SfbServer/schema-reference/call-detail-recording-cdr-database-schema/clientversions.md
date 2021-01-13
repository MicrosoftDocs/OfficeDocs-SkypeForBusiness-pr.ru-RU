---
title: Таблица ClientVersions в Skype для бизнеса Server 2015
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
ms.openlocfilehash: 9f72a640fa294a51e483f496cad9913177dfcd2c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813319"
---
# <a name="clientversions-table-in-skype-for-business-server-2015"></a>Таблица ClientVersions в Skype для бизнеса Server 2015
 
Таблица ClientVersions является вспомогательной таблицей, в которой хранится список различных типов и версий клиентов, которые приняли участие в сеансах, зарегистрированных в базе данных. Каждая запись в таблице представляет одну версию клиента.
  
|**Столбец**|**Тип данных**|**Ключ/индекс**|**Details**|
|:-----|:-----|:-----|:-----|
|**VersionId** <br/> |**int** <br/> |Primary  <br/> |Уникальный номер, идентифицирующий данный тип и версию клиента.  <br/> |
|**Версия** <br/> |**nvarchar(256)** <br/> ||Название версии.  <br/> |
|**ClientType** <br/> |int  <br/> ||Указывает тип клиента, используемого в этом сеансе. Дополнительные сведения см. в таблице [UserAgentDef.](useragentdef.md) <br/> Это поле было впервые введено в Microsoft Lync Server 2013.  <br/> |
   

