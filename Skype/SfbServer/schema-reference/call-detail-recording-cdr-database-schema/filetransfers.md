---
title: Представление FileTransfers
ms.reviewer: ''
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
ms.openlocfilehash: a39e00becd772e74eb12de1a8ce5975e6626cffa
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213090"
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
   

