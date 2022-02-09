---
title: tblFileToken
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
ms.assetid: 49e7dd79-1607-443c-818a-88c160e4ed06
description: Таблица tblFileToken содержит временные маркеры для передачи файлов.
ms.openlocfilehash: 78d132123430143f9609f544d54f176ea5d966d1
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/05/2022
ms.locfileid: "62417452"
---
# <a name="tblfiletoken"></a>tblFileToken
 
Таблица tblFileToken содержит временные маркеры для передачи файлов.
  
**Columns**

|**Столбец**|**Тип**|**Описание**|
|:-----|:-----|:-----|
|fileToken  <br/> |nvarchar (50), NOT NULL  <br/> |Уникальный маркер (GUID).  <br/> |
|fileTokenUserID  <br/> |int, NOT NULL  <br/> |Идентификатор субъекта, который передает файл.  <br/> |
|fileTokenChannelID  <br/> |GUID, не NULL  <br/> |GUID узла комнаты чата.  <br/> |
|fileTokenExpireDate  <br/> |datetime, NOT NULL  <br/> |Срок действия. (Срок действия маркеров истекает через 30 минут, если они не были закреплены; см. описания в этом столбце.)  <br/> |
|fileTokenComplianceFileUrl  <br/> |nvarchar (256)  <br/> |URL-адрес переданного файла (для использования службой соответствия).  <br/> |
|fileTokenComplianceThumbnailUrl  <br/> |nvarchar (256)  <br/> |URL-адрес эскиза переданного файла (для использования службой соответствия).  <br/> |
|fileTokenComplianceTime  <br/> |datetime2  <br/> |Метка времени для фактической операции передачи файла (для использования службой соответствия).  <br/> |
|fileTokenComplianceIsUpload  <br/> |bit  <br/> |True при отправке; False при загрузке (для использования службой соответствия).  <br/> |
|fileTokenCompliancePinned  <br/> |bit, NOT NULL  <br/> |True, если маркер закреплен. Он используется для сохраняния маркера в таблице до тех пор, пока служба соответствия не будет иметь возможность извлечь из него соответствующие поля.  <br/> |
   
**Keys**

|**Столбец**|**Описание**|
|:-----|:-----|
|fileToken  <br/> |Первичный ключ.  <br/> |
|fileTokenChannelID  <br/> |Внешний ключ для поиска в таблице tblNode.nodeGuid.  <br/> |
   

