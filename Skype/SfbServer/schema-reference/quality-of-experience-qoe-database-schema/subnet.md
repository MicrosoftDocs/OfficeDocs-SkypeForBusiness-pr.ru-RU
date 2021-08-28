---
title: Таблица subnet
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 76f5c995-96c8-4aa3-bc30-1d74991d7c42
description: Таблица Subnet является вспомогательной. Каждая запись представляет одну подсеть, определенную в параметрах конфигурации сети.
ms.openlocfilehash: e7fd43963414b24ed684d8f1efa59c7e634839bd
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/26/2021
ms.locfileid: "58613799"
---
# <a name="subnet-table"></a>Таблица subnet
 
Таблица Subnet является вспомогательной. Каждая запись представляет одну подсеть, определенную в параметрах конфигурации сети.
  
|**Столбец**|**Тип данных**|**Key/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**SubnetIP** <br/> |int  <br/> |Основной, внешний  <br/> |Целочисленное представление IP-адреса подсети.  <br/> |
|**SubnetMask** <br/> |int  <br/> ||Маска подсети.  <br/> |
|**UserSiteKey** <br/> |int  <br/> |Foreign  <br/> |Ссылки из [таблицы UserSite](usersite.md).  <br/> |
|**SubnetDescription** <br/> |nvarchar (512)  <br/> ||Описание подсети.  <br/> |
   

