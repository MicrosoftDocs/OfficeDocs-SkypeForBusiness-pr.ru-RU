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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b50c3f4a-bab6-4cb9-b40e-016cf1a9c607
description: Тблактивепирс включает в себя текущие одноранговые соединения между службами чата.
ms.openlocfilehash: 4604c13dbff9565748dd59e5917a5c133bd71947
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814717"
---
# <a name="tblactivepeers"></a>tblActivePeers
 
Тблактивепирс включает в себя текущие одноранговые соединения между службами чата.
  
**Столбцов**

|**Столбец**|**Тип**|**Описание**|
|:-----|:-----|:-----|
|аплсерверид  <br/> |int, NOT NULL  <br/> |Идентификатор сервера, на котором размещена запись.  <br/> |
|аплпирид  <br/> |int, NOT NULL  <br/> |Идентификатор однорангового узла, к которому подключен сервер публикации.  <br/> |
   
**Параметры**

|**Столбец**|**Описание**|
|:-----|:-----|
|\<Аплсерверид, Аплпирид\>  <br/> |Первичный ключ.  <br/> |
|аплсерверид  <br/> |Внешний ключ с подстановкой в таблице Тблсерверидентити. Серверид.  <br/> |
|аплпирид  <br/> |Внешний ключ с подстановкой в таблице Тблсерверидентити. Серверид.  <br/> |
   

