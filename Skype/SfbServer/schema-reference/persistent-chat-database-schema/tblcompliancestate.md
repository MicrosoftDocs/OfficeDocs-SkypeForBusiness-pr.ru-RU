---
title: tblComplianceState
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
ms.assetid: ea82e56c-3cca-4d89-b4e6-6bcaeb1f2830
description: Тблкомплианцестате включает в себя сведения о состоянии соответствия требованиям всего пула.
ms.openlocfilehash: 6f3a7b1b7744260d0630a5328021b1752137a797
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814637"
---
# <a name="tblcompliancestate"></a>tblComplianceState
 
Тблкомплианцестате включает в себя сведения о состоянии соответствия требованиям всего пула.
  
**Столбцов**

|**Столбец**|**Тип**|**Описание**|
|:-----|:-----|:-----|
|ластпроцесседентрид  <br/> |bigint, NOT NULL  <br/> |Идентификатор последнего обработанного события соответствия требованиям.  <br/> |
|активесерверид  <br/> |int, NOT NULL  <br/> |Идентификатор сервера соответствия, который удерживает монопольную блокировку для базы данных, или значение-1, если нет.  <br/> |
|локкекспиратионтиме  <br/> |datetime2, NOT NULL  <br/> |Заблокируйте срок действия (если Активесерверид не является 1).  <br/> |
   

