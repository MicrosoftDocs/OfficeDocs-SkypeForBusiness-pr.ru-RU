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
localization_priority: Normal
ms.assetid: 487a430b-af66-4ea6-b28e-4e33cfdb7f9e
description: Таблица диалогов — это вспомогательная таблица, в которой хранятся сведения о Диалогидс для одноранговых сеансов.
ms.openlocfilehash: 61230cf7f72405c4c5f27ff7b159afe4e5a7842e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296324"
---
# <a name="dialogs-table-in-skype-for-business-server-2015"></a>Таблица диалогов в Skype для бизнеса Server 2015
 
Таблица диалогов — это вспомогательная таблица, в которой хранятся сведения о Диалогидс для одноранговых сеансов.
  
|**Столбец**|**Тип данных**|**Ключ/индекс**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**Сессионидтиме** <br/> |datetime  <br/> |Primary  <br/> |Время запроса сеанса; используется в сочетании с Сессионидсек для уникальной идентификации сеанса.  <br/> |
|**Сессионидсек** <br/> |целое  <br/> |Primary  <br/> |ИДЕНТИФИКАЦИОНный номер для идентификации сеанса. Используется в сочетании с Сессионидтиме для уникальной идентификации сеанса.  <br/> |
|**Екстерналчекксум** <br/> |целое  <br/> | <br/> |Контрольная сумма Екстерналид. Это поле используется для увеличения скорости поиска в базе данных.  <br/> |
|**Екстерналид** <br/> |varbinary (775)  <br/> | <br/> |ИДЕНТИФИКАТОР диалогового окна SIP, сохраненный в виде двоичного файла. Двоичный формат:  <br/> диалоговое окно; тег "from-Tag"  <br/> Эти данные можно преобразовать в текстовый формат, используя следующий синтаксис:  <br/>  `cast(cast(ExternalId as varbinary(max)) as varchar(max))` <br/> |
   

