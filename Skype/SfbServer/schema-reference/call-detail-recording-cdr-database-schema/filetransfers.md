---
title: Представление FileTransfers
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
ms.assetid: e52c3ad0-152e-4a18-af1c-1aff0d205151
description: Представление FileTransfer хранит сведения о одноранговых сеансах передачи файлов. Это представление было представлено в Microsoft Lync Server 2013.
ms.openlocfilehash: d8b173c7617dcaa37d3cea00f5bdb09ef34670da
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/05/2022
ms.locfileid: "62391851"
---
# <a name="filetransfers-view"></a>Представление FileTransfers
 
Представление FileTransfer хранит сведения о одноранговых сеансах передачи файлов. Это представление было представлено в Microsoft Lync Server 2013.
  
> [!NOTE]
> Представление FileTransfers содержит все столбцы в представлении [SessionDetails](sessiondetails-0.md) в дополнение к столбцам, перечисленным ниже.
  
|**Столбец**|**Тип данных**|**Сведения**|
|:-----|:-----|:-----|
|**FileName** <br/> |nvarchar (256)  <br/> |Имя переданного файла.  <br/> |
|**Cookie** <br/> |nvarchar (128)  <br/> |Используется для идентификации каждого последующего сообщения как связанного с этим сообщением.  <br/> |
|**FileIdentity** <br/> |uniqueidentifier  <br/> |Уникальный идентификатор для различения операций передачи файлов с одинаковыми именами файлов.  <br/> |
|**Accept** <br/> |bit  <br/> |Может иметь значение TRUE или NULL. Если значение равно TRUE, то значением параметров Reject и Cancel будет NULL.  <br/> |
|**Reject** <br/> |bit  <br/> |Может иметь значение TRUE или NULL. Если значение равно TRUE, то значением параметров Accept и Cancel будет NULL.  <br/> |
|**Отмена** <br/> |bit  <br/> |Может иметь значение TRUE или NULL. Если значение равно TRUE, то значением параметров Accept и Reject будет NULL.  <br/> |
   

