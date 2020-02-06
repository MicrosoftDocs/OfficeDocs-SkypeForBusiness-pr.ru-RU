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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 05b28f9b-4aba-4b69-ba8d-2ceeb6cbfaac
description: Тблкомплианцедата содержит события соответствия требованиям, которые пока не обрабатывались адаптером соответствия требованиям.
ms.openlocfilehash: f09acd44e803c629e45afa18683ac7bc863564a9
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814667"
---
# <a name="tblcompliancedata"></a>tblComplianceData
 
Тблкомплианцедата содержит события соответствия требованиям, которые пока не обрабатывались адаптером соответствия требованиям.
  
**Столбцов**

|**Столбец**|**Тип**|**Описание**|
|:-----|:-----|:-----|
|кмплевентид  <br/> |bigint, NOT NULL  <br/> |Код события.  <br/> |
|ентридате  <br/> |smalldatetime, NOT NULL  <br/> |Время вставки (может быть в будущем для Кмплтипе = 9, так как в этом случае запись является заполнителем в этом случае).  <br/> |
|кмплтипе  <br/> |int, NOT NULL  <br/> | Тип события соответствия: <br/>  1: чат <br/>  2: чат <br/>  3: Загрузка файла <br/>  4: Отправка файлов <br/>  9: подготовка к передаче файлов <br/>  10: удаление чата (с заменой) <br/>  11: Очистка чата <br/> |
|кмплтиме  <br/> |bigint, NOT NULL  <br/> |Метка времени для события.  <br/> |
|кмплчаннелури  <br/> |nvarchar (255), NOT NULL  <br/> |Универсальный код ресурса (URI) канала.  <br/> |
|кмплчатид  <br/> |bigint  <br/> |ИДЕНТИФИКАТОР чата (соответствующая таблице Тблчат. Чатид).  <br/> |
|кмплусерид  <br/> |int, NOT NULL  <br/> |Идентификатор участника афиши (соответствующий таблице ТблпринЦипал. Принид).  <br/> |
|кмплусерури  <br/> |nvarchar (255), NOT NULL  <br/> |URI пользователя.  <br/> |
|кмплмессаже  <br/> |nvarchar (max)  <br/> |Сообщение (Кодировка зависит от Кмплтипе).  <br/> |
   
**Ключ**

|**Столбец**|**Описание**|
|:-----|:-----|
|кмплевентид  <br/> |Первичный ключ.  <br/> |
   

