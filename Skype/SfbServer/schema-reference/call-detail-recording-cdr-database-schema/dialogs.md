---
title: Таблица диалогов в Skype для бизнеса Server 2015
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
ms.assetid: 487a430b-af66-4ea6-b28e-4e33cfdb7f9e
description: Таблица диалогов — это вспомогательная таблица, в которой хранятся сведения о Диалогидс для одноранговых сеансов.
ms.openlocfilehash: f6cfc3e078ee8f4492d6f5baf65f66df77d7aedf
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815277"
---
# <a name="dialogs-table-in-skype-for-business-server-2015"></a>Таблица диалогов в Skype для бизнеса Server 2015
 
Таблица диалогов — это вспомогательная таблица, в которой хранятся сведения о Диалогидс для одноранговых сеансов.
  
|**Столбец**|**Тип данных**|**Ключ/индекс**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**сессионидтиме** <br/> |datetime  <br/> |Primary  <br/> |Время запроса сеанса; используется в сочетании с Сессионидсек для уникальной идентификации сеанса.  <br/> |
|**сессионидсек** <br/> |целое  <br/> |Primary  <br/> |ИДЕНТИФИКАЦИОНный номер для идентификации сеанса. Используется в сочетании с Сессионидтиме для уникальной идентификации сеанса.  <br/> |
|**екстерналчекксум** <br/> |целое  <br/> | <br/> |Контрольная сумма Екстерналид. Это поле используется для увеличения скорости поиска в базе данных.  <br/> |
|**екстерналид** <br/> |varbinary (775)  <br/> | <br/> |ИДЕНТИФИКАТОР диалогового окна SIP, сохраненный в виде двоичного файла. Двоичный формат:  <br/> диалоговое окно; тег "from-Tag"  <br/> Эти данные можно преобразовать в текстовый формат, используя следующий синтаксис:  <br/>  `cast(cast(ExternalId as varbinary(max)) as varchar(max))` <br/> |
   

