---
title: tblActivePeers
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b50c3f4a-bab6-4cb9-b40e-016cf1a9c607
description: Тблактивепирс включает в себя текущие одноранговые соединения между службами чата.
ms.openlocfilehash: f45a04019cafc2304baf825b5000e96ca7a6cead
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295547"
---
# <a name="tblactivepeers"></a>tblActivePeers
 
Тблактивепирс включает в себя текущие одноранговые соединения между службами чата.
  
**Столбцов**

|**Столбец**|**Тип**|**Описание**|
|:-----|:-----|:-----|
|Аплсерверид  <br/> |int, NOT NULL  <br/> |Идентификатор сервера, на котором размещена запись.  <br/> |
|Аплпирид  <br/> |int, NOT NULL  <br/> |Идентификатор однорангового узла, к которому подключен сервер публикации.  <br/> |
   
**Параметры**

|**Столбец**|**Описание**|
|:-----|:-----|
|\<Аплсерверид, Аплпирид\>  <br/> |Первичный ключ.  <br/> |
|Аплсерверид  <br/> |Внешний ключ с подстановкой в таблице Тблсерверидентити. Серверид.  <br/> |
|Аплпирид  <br/> |Внешний ключ с подстановкой в таблице Тблсерверидентити. Серверид.  <br/> |
   

