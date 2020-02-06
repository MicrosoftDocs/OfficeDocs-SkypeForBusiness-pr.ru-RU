---
title: tblPrincipalInvites
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
ms.assetid: 548ec156-4d1a-469d-a804-62cff226e5c2
description: ТблпринЦипалинвитес включает приглашения для всех подготовленных пользователей для всех узлов с автоматическим приглашением.
ms.openlocfilehash: dfa41ec5715c7c5255b26fcdb32561e74c4f08df
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814187"
---
# <a name="tblprincipalinvites"></a>tblPrincipalInvites
 
ТблпринЦипалинвитес включает приглашения для всех подготовленных пользователей для всех узлов с автоматическим приглашением.
  
**Столбцов**

|**Столбец**|**Тип**|**Описание**|
|:-----|:-----|:-----|
|принид  <br/> |int, NOT NULL  <br/> |Идентификатор участника.  <br/> |
|инвид  <br/> |int, NOT NULL  <br/> |Уникальный последовательный номер (для идентификатора участника), сформированный из таблицы Тблластинвитеид.  <br/> |
|нодеид  <br/> |int, NOT NULL  <br/> |Идентификатор узла (только для комнаты чата).  <br/> |
|креатедон  <br/> |DateTime, NOT NULL  <br/> |Время создания.  <br/> |
   
**Параметры**

|**Столбец**|**Описание**|
|:-----|:-----|
|\<Принид, Нодеид\>  <br/> |Первичный ключ.  <br/> |
|принид  <br/> |Внешний ключ с подстановкой в таблице ТблпринЦипал. Принид.  <br/> |
|нодеид  <br/> |Внешний ключ с подстановкой в таблице Тблноде. Нодеид.  <br/> |
   

