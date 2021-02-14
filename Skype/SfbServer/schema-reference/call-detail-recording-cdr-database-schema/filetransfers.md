---
title: Представление FileTransfers
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
ms.assetid: e52c3ad0-152e-4a18-af1c-1aff0d205151
description: В представлении FileTransfer хранится информация об одноранговых сеансах передачи файлов. Это представление впервые было введено в Microsoft Lync Server 2013.
ms.openlocfilehash: 8b3c2db012b8969bd4b5b75ca19ed090f8227c53
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821689"
---
# <a name="filetransfers-view"></a>Представление FileTransfers
 
В представлении FileTransfer хранится информация об одноранговых сеансах передачи файлов. Это представление впервые было введено в Microsoft Lync Server 2013.
  
> [!NOTE]
> Представление FileTransfers содержит все столбцы в представлении [SessionDetails](sessiondetails-0.md) в дополнение к столбцам, перечисленным ниже.
  
|**Столбец**|**Тип данных**|**Details**|
|:-----|:-----|:-----|
|**FileName** <br/> |nvarchar(256)  <br/> |Имя переданного файла.  <br/> |
|**Cookie** <br/> |nvarchar(128)  <br/> |Используется для идентификации каждого последующего сообщения как связанного с этим сообщением.  <br/> |
|**FileIdentity** <br/> |uniqueidentifier  <br/> |Уникальный идентификатор для различения операций передачи файлов с одинаковыми именами файлов.  <br/> |
|**Accept** <br/> |bit  <br/> |Может иметь значение TRUE или NULL. Если значение равно TRUE, то значением параметров Reject и Cancel будет NULL.  <br/> |
|**Reject** <br/> |bit  <br/> |Может иметь значение TRUE или NULL. Если значение равно TRUE, то значением параметров Accept и Cancel будет NULL.  <br/> |
|**Отмена** <br/> |bit  <br/> |Может иметь значение TRUE или NULL. Если значение равно TRUE, то значением параметров Accept и Reject будет NULL.  <br/> |
   

