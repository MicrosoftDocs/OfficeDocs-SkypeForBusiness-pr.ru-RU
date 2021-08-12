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
description: Представление FileTransfer хранит сведения о одноранговых сеансах передачи файлов. Это представление было представлено в Microsoft Lync Server 2013.
ms.openlocfilehash: e805b770038eb7fae93337c5d6c26d7059e5764436328f6321e65c948e40c88d
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2021
ms.locfileid: "54349691"
---
# <a name="filetransfers-view"></a>Представление FileTransfers
 
Представление FileTransfer хранит сведения о одноранговых сеансах передачи файлов. Это представление было представлено в Microsoft Lync Server 2013.
  
> [!NOTE]
> Представление FileTransfers содержит все столбцы в представлении [SessionDetails](sessiondetails-0.md) в дополнение к столбцам, перечисленным ниже.
  
|**Column**|**Тип данных**|**Сведения**|
|:-----|:-----|:-----|
|**FileName** <br/> |nvarchar (256)  <br/> |Имя переданного файла.  <br/> |
|**Cookie** <br/> |nvarchar (128)  <br/> |Используется для идентификации каждого последующего сообщения как связанного с этим сообщением.  <br/> |
|**FileIdentity** <br/> |uniqueidentifier  <br/> |Уникальный идентификатор для различения операций передачи файлов с одинаковыми именами файлов.  <br/> |
|**Accept** <br/> |bit  <br/> |Может иметь значение TRUE или NULL. Если значение равно TRUE, то значением параметров Reject и Cancel будет NULL.  <br/> |
|**Reject** <br/> |bit  <br/> |Может иметь значение TRUE или NULL. Если значение равно TRUE, то значением параметров Accept и Cancel будет NULL.  <br/> |
|**Cancel** <br/> |bit  <br/> |Может иметь значение TRUE или NULL. Если значение равно TRUE, то значением параметров Accept и Reject будет NULL.  <br/> |
   

