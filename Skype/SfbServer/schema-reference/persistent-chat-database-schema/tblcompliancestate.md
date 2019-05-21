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
localization_priority: Normal
ms.assetid: ea82e56c-3cca-4d89-b4e6-6bcaeb1f2830
description: Тблкомплианцестате включает в себя сведения о состоянии соответствия требованиям всего пула.
ms.openlocfilehash: 1c5571d7150c3859978f8d217f0264f67ee993d5
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295477"
---
# <a name="tblcompliancestate"></a>tblComplianceState
 
Тблкомплианцестате включает в себя сведения о состоянии соответствия требованиям всего пула.
  
**Столбцов**

|**Столбец**|**Тип**|**Описание**|
|:-----|:-----|:-----|
|Ластпроцесседентрид  <br/> |bigint, NOT NULL  <br/> |Идентификатор последнего обработанного события соответствия требованиям.  <br/> |
|Активесерверид  <br/> |int, NOT NULL  <br/> |Идентификатор сервера соответствия, который удерживает монопольную блокировку для базы данных, или значение-1, если нет.  <br/> |
|Локкекспиратионтиме  <br/> |datetime2, NOT NULL  <br/> |Заблокируйте срок действия (если Активесерверид не является 1).  <br/> |
   

