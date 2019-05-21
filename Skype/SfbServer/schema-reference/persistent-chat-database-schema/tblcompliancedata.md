---
title: tblComplianceData
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 05b28f9b-4aba-4b69-ba8d-2ceeb6cbfaac
description: Тблкомплианцедата содержит события соответствия требованиям, которые пока не обрабатывались адаптером соответствия требованиям.
ms.openlocfilehash: b505b3e05fb2aebba98804f5b7ad6a1d4d2da53e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295512"
---
# <a name="tblcompliancedata"></a>tblComplianceData
 
Тблкомплианцедата содержит события соответствия требованиям, которые пока не обрабатывались адаптером соответствия требованиям.
  
**Столбцов**

|**Столбец**|**Тип**|**Описание**|
|:-----|:-----|:-----|
|Кмплевентид  <br/> |bigint, NOT NULL  <br/> |Код события.  <br/> |
|Ентридате  <br/> |smalldatetime, NOT NULL  <br/> |Время вставки (может быть в будущем для Кмплтипе = 9, так как в этом случае запись является заполнителем в этом случае).  <br/> |
|Кмплтипе  <br/> |int, NOT NULL  <br/> | Тип события соответствия: <br/>  1: чат <br/>  2: чат <br/>  3: Загрузка файла <br/>  4: Отправка файлов <br/>  9: подготовка к передаче файлов <br/>  10: удаление чата (с заменой) <br/>  11: Очистка чата <br/> |
|Кмплтиме  <br/> |bigint, NOT NULL  <br/> |Метка времени для события.  <br/> |
|Кмплчаннелури  <br/> |nvarchar (255), NOT NULL  <br/> |Универсальный код ресурса (URI) канала.  <br/> |
|Кмплчатид  <br/> |bigint  <br/> |ИДЕНТИФИКАТОР чата (соответствующая таблице Тблчат. Чатид).  <br/> |
|Кмплусерид  <br/> |int, NOT NULL  <br/> |Идентификатор участника афиши (соответствующий таблице ТблпринЦипал. Принид).  <br/> |
|Кмплусерури  <br/> |nvarchar (255), NOT NULL  <br/> |URI пользователя.  <br/> |
|Кмплмессаже  <br/> |nvarchar (max)  <br/> |Сообщение (Кодировка зависит от Кмплтипе).  <br/> |
   
**Ключ**

|**Столбец**|**Описание**|
|:-----|:-----|
|Кмплевентид  <br/> |Первичный ключ.  <br/> |
   

