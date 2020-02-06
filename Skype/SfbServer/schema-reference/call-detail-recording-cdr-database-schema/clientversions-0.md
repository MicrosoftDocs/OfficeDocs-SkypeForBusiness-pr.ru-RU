---
title: Представление Клиентверсионс
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
ms.assetid: caf7678f-83a0-46c8-83cc-fee4c3991f52
description: В представлении Клиентверсионс хранятся сведения о различных типах и версиях клиентов, которые принимали участие в сеансах, записанных в базе данных. Каждая запись в представлении представляет собой одну версию клиента. Это представление было представлено в Microsoft Lync Server 2013.
ms.openlocfilehash: d37e2a1599eaf8906d11fdb8faf545aa3447f00f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815417"
---
# <a name="clientversions-view"></a>Представление Клиентверсионс
 
В представлении Клиентверсионс хранятся сведения о различных типах и версиях клиентов, которые принимали участие в сеансах, записанных в базе данных. Каждая запись в представлении представляет собой одну версию клиента. Это представление было представлено в Microsoft Lync Server 2013.
  
> [!NOTE]
> Для некоторых столбцов может быть несколько записей. 
  
|**Столбец**|**Тип данных**|**Сведения**|
|:-----|:-----|:-----|
|**VersionId** <br/> |целое  <br/> |Уникальный номер, показывающий этот тип клиента и версию.  <br/> |
|**Версия** <br/> |nvarchar(256)  <br/> |Представляет агент пользователя.  <br/> |
|**клиенттипе** <br/> |целое  <br/> |Тип клиента.  <br/> |
|**клиенткатегори** <br/> |nvarchar (64)  <br/> |Категория, к которой относится клиент. Например, клиент Conferencing_Attendant_1 .0 принадлежит Клиенткатегори Каа.  <br/> |
   

