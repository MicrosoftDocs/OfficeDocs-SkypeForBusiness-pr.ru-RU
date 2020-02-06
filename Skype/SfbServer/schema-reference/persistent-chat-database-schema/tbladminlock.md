---
title: tblAdminLock
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
ms.assetid: 785a43c0-6892-474c-821c-fa9cdbeb99d8
description: Тбладминлокк содержит блокировку администратора, которая необходима для выполнения некоторых команд администратора.
ms.openlocfilehash: cb3a03fa7404004df37da2adf07eff1e37ff334f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814697"
---
# <a name="tbladminlock"></a>tblAdminLock
 
Тбладминлокк содержит блокировку администратора, которая необходима для выполнения некоторых команд администратора.
  
**Столбцов**

|**Столбец**|**Тип**|**Описание**|
|:-----|:-----|:-----|
|локкекспирестиме  <br/> |DateTime, NOT NULL  <br/> |Заблокируйте дату и время окончания срока действия. Владелец может периодически увеличивать это значение.  <br/> |
|локксерверид  <br/> |int, NOT NULL  <br/> |Идентификатор сервера, владеющего блокировкой.  <br/> |
|локкакторид  <br/> |int, NOT NULL  <br/> |Идентификатор участника, владеющего блокировкой.  <br/> |
   

