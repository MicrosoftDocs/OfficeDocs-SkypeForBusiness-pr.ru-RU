---
title: tblServerIdentity
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
ms.assetid: 5411c9bc-b0b3-41fc-8b7e-fa71cccd770b
description: Тблсерверидентити включает в себя серверы активных чатов в пуле серверов сохраняемого чата.
ms.openlocfilehash: 4f6389f21c35da914b4943a279d8d485b6ec1eae
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812277"
---
# <a name="tblserveridentity"></a>tblServerIdentity
 
Тблсерверидентити включает в себя серверы активных чатов в пуле серверов сохраняемого чата.
  
**Столбцов**

|**Столбец**|**Тип**|**Описание**|
|:-----|:-----|:-----|
|серверид  <br/> |int, NOT NULL  <br/> |Идентификатор сервера. Соответствует ИДЕНТИФИКАТОРу экземпляра из хранилища центрального управления.  <br/> |
|сервераддресс  <br/> |nvarchar (256), NOT NULL  <br/> |Адрес сервера с использованием адреса Windows Communication Foundation.  <br/> |
|серверластпингтиме  <br/> |datetime  <br/> |Последнее время, в течение которого сервер канала обновил эту строку, чтобы дать свидетельство о том, что оно запущено.  <br/> |
   
**Ключ**

|**Столбец**|**Описание**|
|:-----|:-----|
|серверид  <br/> |Первичный ключ.  <br/> |
   

