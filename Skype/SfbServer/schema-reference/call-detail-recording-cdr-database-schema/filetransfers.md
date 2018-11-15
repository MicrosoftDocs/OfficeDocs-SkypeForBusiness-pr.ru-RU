---
title: Представление FileTransfers
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e52c3ad0-152e-4a18-af1c-1aff0d205151
description: Просмотр FileTransfer сохранение информации о сеансах с передачей файлов peer-to-peer. В этом представлении была введена в Microsoft Lync Server 2013.
ms.openlocfilehash: 97bc5f957192c8a2c6d888f81fce0891aa2b4f75
ms.sourcegitcommit: 30620021ceba916a505437ab641a23393f55827a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/15/2018
ms.locfileid: "26531221"
---
# <a name="filetransfers-view"></a>Представление FileTransfers
 
Просмотр FileTransfer сохранение информации о сеансах с передачей файлов peer-to-peer. В этом представлении была введена в Microsoft Lync Server 2013.
  
> [!NOTE]
> Представление FileTransfers содержит все столбцы [SessionDetails view](sessiondetails-0.md) в дополнение к этому столбцов, перечисленных ниже.
  
|**Столбец**|**Тип данных**|**Сведения**|
|:-----|:-----|:-----|
|**FileName** <br/> |nvarchar(256)  <br/> |Имя файла, передан.  <br/> |
|**Файл cookie** <br/> |nvarchar(128)  <br/> |Используется для идентификации каждого последующего сообщения как связанного с этим сообщением.  <br/> |
|**FileIdentity** <br/> |uniqueidentifier  <br/> |Уникальный идентификатор для различения операций передачи файлов с одинаковыми именами файлов.  <br/> |
|**Прием** <br/> |бит  <br/> |Может быть значение TRUE или значение NULL. Если значение TRUE, затем Отклонить и Отмена будет NULL.  <br/> |
|**Отклонение** <br/> |бит  <br/> |Может быть значение TRUE или значение NULL. Если значение TRUE, затем принять и Отмена будет NULL.  <br/> |
|**Отмена**. <br/> |бит  <br/> |Может быть значение TRUE или значение NULL. Если значение TRUE, то принятия и отклонения будет NULL.  <br/> |
   

