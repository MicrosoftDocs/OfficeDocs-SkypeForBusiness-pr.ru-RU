---
title: tblFileToken
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 49e7dd79-1607-443c-818a-88c160e4ed06
description: Таблица tblFileToken содержит временные маркеры для передачи файлов.
ms.openlocfilehash: c6735cf7da1412cca86817360c1a35030e8b0df4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929856"
---
# <a name="tblfiletoken"></a>tblFileToken
 
Таблица tblFileToken содержит временные маркеры для передачи файлов.
  
**Столбцы**

|**Столбец**|**Тип**|**Описание**|
|:-----|:-----|:-----|
|fileToken  <br/> |nvarchar (50), отлично от null  <br/> |Уникальный маркер (GUID).  <br/> |
|fileTokenUserID  <br/> |int, не null  <br/> |Идентификатор субъекта, который передает файл.  <br/> |
|fileTokenChannelID  <br/> |Идентификатор GUID, не может быть null  <br/> |GUID узла комнаты чата.  <br/> |
|fileTokenExpireDate  <br/> |DateTime, не может быть null  <br/> |Время истечения срока действия. (Маркеры срок действия которых истекает через 30 минут, пока не прикрепленных (см. следующие описания в этой статье).  <br/> |
|fileTokenComplianceFileUrl  <br/> |nvarchar(256)  <br/> |URL-адрес переданного файла (для использования службой соответствия).  <br/> |
|fileTokenComplianceThumbnailUrl  <br/> |nvarchar(256)  <br/> |URL-адрес эскиза переданного файла (для использования службой соответствия).  <br/> |
|fileTokenComplianceTime  <br/> |datetime2  <br/> |Метка времени для операции переноса исходный файл (для использования службой соответствия).  <br/> |
|fileTokenComplianceIsUpload  <br/> |бит  <br/> |Значение true, если отправка; False при загрузке (для использования службой соответствия).  <br/> |
|fileTokenCompliancePinned  <br/> |bit, не может быть null  <br/> |Значение true, если прикрепленных маркер. Он используется для хранения маркера в таблице, пока служба соответствия имеет возможность получать соответствующие поля из нее.  <br/> |
   
**Ключи**

|**Столбец**|**Описание**|
|:-----|:-----|
|fileToken  <br/> |Первичный ключ.  <br/> |
|fileTokenChannelID  <br/> |Внешний ключ с подстановкой в таблице tblNode.nodeGuid.  <br/> |
   

