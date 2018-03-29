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
description: Просмотр FileTranfer сохранение информации о сеансах с передачей файлов peer-to-peer. В этом представлении была введена в Microsoft Lync Server 2013.
ms.openlocfilehash: 69b986c24a3a8f3646738eb3e1e3e97794be8e9e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="filetransfers-view"></a>Представление FileTransfers
 
Просмотр FileTranfer сохранение информации о сеансах с передачей файлов peer-to-peer. В этом представлении была введена в Microsoft Lync Server 2013.
  
> [!NOTE]
> Представление FileTransfers содержит все столбцы [SessionDetails view](sessiondetails-0.md) в дополнение к этому столбцов, перечисленных ниже.
  
|**Столбец**|**Тип данных**|**Сведения**|
|:-----|:-----|:-----|
|**Имя файла** <br/> |nvarchar(256)  <br/> |Имя файла, передан.  <br/> |
|**Файл cookie** <br/> |nvarchar(128)  <br/> |Используется для идентификации каждого последующего сообщения как связанного с этим сообщением.  <br/> |
|**FileIdentity** <br/> |uniqueidentifier  <br/> |Уникальный идентификатор для различения операций передачи файлов с одинаковыми именами файлов.  <br/> |
|**Прием** <br/> |бит  <br/> |Может быть значение TRUE или значение NULL. Если значение TRUE, затем Отклонить и Отмена будет NULL.  <br/> |
|**Отклонение** <br/> |бит  <br/> |Может быть значение TRUE или значение NULL. Если значение TRUE, затем принять и Отмена будет NULL.  <br/> |
|**Отмена**. <br/> |бит  <br/> |Может быть значение TRUE или значение NULL. Если значение TRUE, то принятия и отклонения будет NULL.  <br/> |
   

