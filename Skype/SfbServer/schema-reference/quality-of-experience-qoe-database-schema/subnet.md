---
title: Таблица subnet
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
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
ms.openlocfilehash: 92e582332e0e7c20c443a57c4ba0cc6abbb66cad
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/05/2022
ms.locfileid: "62394601"
---
# <a name="subnet-table"></a>Таблица subnet
 
Таблица Subnet является вспомогательной. Каждая запись представляет одну подсеть, определенную в параметрах конфигурации сети.
  
|**Столбец**|**Тип данных**|**Key/Index**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**SubnetIP** <br/> |int  <br/> |Основной, внешний  <br/> |Целочисленное представление IP-адреса подсети.  <br/> |
|**SubnetMask** <br/> |int  <br/> ||Маска подсети.  <br/> |
|**UserSiteKey** <br/> |int  <br/> |Foreign  <br/> |Ссылки из [таблицы UserSite](usersite.md).  <br/> |
|**SubnetDescription** <br/> |nvarchar (512)  <br/> ||Описание подсети.  <br/> |
   

