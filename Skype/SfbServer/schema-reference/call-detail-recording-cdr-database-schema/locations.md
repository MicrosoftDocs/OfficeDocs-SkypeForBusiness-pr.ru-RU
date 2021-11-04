---
title: Таблица расположения в Skype для бизнеса Server 2015 г.
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
ms.assetid: 78dc1b14-5394-4f8e-89d3-4ba593272a04
description: Каждая запись представляет одну ссылку на расположение в экстренном звонке, например звонке E9-1-1.
ms.openlocfilehash: 7a14e44e5514944c69f751e21ed055a9ab1fa114
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/04/2021
ms.locfileid: "60746555"
---
# <a name="locations-table-in-skype-for-business-server-2015"></a>Таблица расположения в Skype для бизнеса Server 2015 г.
 
Каждая запись представляет одну ссылку на расположение в экстренном звонке, например звонке E9-1-1.
  
|**Столбец**|**Тип данных**|**Key/Index**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Основной, внешний  <br/> |Время запроса сеанса. В сочетании с параметром **SessionIdSeq** определяет сеанс уникальным образом. Дополнительные сведения см. в таблице [Диалоги Skype для бизнеса Server 2015](dialogs.md) г. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Основной, внешний  <br/> |Идентификатор для идентификации сеанса. В сочетании с параметром **SessionIdTime** определяет сеанс уникальным образом. Дополнительные сведения см. в таблице [Диалоги Skype для бизнеса Server 2015](dialogs.md) г. <br/> |
|**Location** <br/> |nvarchar (max)  <br/> ||Расположение экстренного звонка.  <br/> |
   

