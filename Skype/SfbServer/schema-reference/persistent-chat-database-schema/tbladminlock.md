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
localization_priority: Normal
ms.assetid: 785a43c0-6892-474c-821c-fa9cdbeb99d8
description: Тбладминлокк содержит блокировку администратора, которая необходима для выполнения некоторых команд администратора.
ms.openlocfilehash: ccdc2b2667dee4d1d82a583ef7e7698d3107651a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295526"
---
# <a name="tbladminlock"></a>tblAdminLock
 
Тбладминлокк содержит блокировку администратора, которая необходима для выполнения некоторых команд администратора.
  
**Столбцов**

|**Столбец**|**Тип**|**Описание**|
|:-----|:-----|:-----|
|Локкекспирестиме  <br/> |DateTime, NOT NULL  <br/> |Заблокируйте дату и время окончания срока действия. Владелец может периодически увеличивать это значение.  <br/> |
|Локксерверид  <br/> |int, NOT NULL  <br/> |Идентификатор сервера, владеющего блокировкой.  <br/> |
|Локкакторид  <br/> |int, NOT NULL  <br/> |Идентификатор участника, владеющего блокировкой.  <br/> |
   

