---
title: tblComplianceFanout
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
ms.assetid: f5d9f342-a7cb-4b54-baa6-e656256b75ad
description: Тблкомплианцефанаут включает все серверы, которые обрабатывали событие соответствия требованиям.
ms.openlocfilehash: cdf455563ccfc971963144b9d4e848d5678cac80
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814657"
---
# <a name="tblcompliancefanout"></a>tblComplianceFanout
 
Тблкомплианцефанаут включает все серверы, которые обрабатывали событие соответствия требованиям.
  
**Столбцов**

|**Столбец**|**Тип**|**Описание**|
|:-----|:-----|:-----|
|фанаутевентид  <br/> |целое  <br/> |Код события.  <br/> |
|фанаутсерверид  <br/> |целое  <br/> |Идентификация сервера (соответствующая таблице Тблсерверидентити. Серверид).  <br/> |
   
**Ключ**

|**Столбец**|**Описание**|
|:-----|:-----|
|фанаутевентид  <br/> |Внешний ключ с подстановкой в таблице Тблкомплианцедата. Кмплевентид.  <br/> |
   

