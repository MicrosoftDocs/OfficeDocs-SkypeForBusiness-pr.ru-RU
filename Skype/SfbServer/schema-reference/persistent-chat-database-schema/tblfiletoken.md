---
title: tblFileToken
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
ms.assetid: 49e7dd79-1607-443c-818a-88c160e4ed06
description: Таблица tblFileToken содержит временные маркеры для передачи файлов.
ms.openlocfilehash: f099b641f732d2f6ccecf699335e9e88736484cc4eac7bfbce8d4a2d7dd6e810
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2021
ms.locfileid: "54301295"
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
   

