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
localization_priority: Normal
ms.assetid: 548ec156-4d1a-469d-a804-62cff226e5c2
description: ТблпринЦипалинвитес включает приглашения для всех подготовленных пользователей для всех узлов с автоматическим приглашением.
ms.openlocfilehash: 21344cfc34ce046a1dffdf7cd3ee9557da20a7ef
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295295"
---
# <a name="tblprincipalinvites"></a>tblPrincipalInvites
 
ТблпринЦипалинвитес включает приглашения для всех подготовленных пользователей для всех узлов с автоматическим приглашением.
  
**Столбцов**

|**Столбец**|**Тип**|**Описание**|
|:-----|:-----|:-----|
|Принид  <br/> |int, NOT NULL  <br/> |Идентификатор участника.  <br/> |
|ИНВИД  <br/> |int, NOT NULL  <br/> |Уникальный последовательный номер (для идентификатора участника), сформированный из таблицы Тблластинвитеид.  <br/> |
|Нодеид  <br/> |int, NOT NULL  <br/> |Идентификатор узла (только для комнаты чата).  <br/> |
|Креатедон  <br/> |DateTime, NOT NULL  <br/> |Время создания.  <br/> |
   
**Параметры**

|**Столбец**|**Описание**|
|:-----|:-----|
|\<Принид, Нодеид\>  <br/> |Первичный ключ.  <br/> |
|Принид  <br/> |Внешний ключ с подстановкой в таблице ТблпринЦипал. Принид.  <br/> |
|Нодеид  <br/> |Внешний ключ с подстановкой в таблице Тблноде. Нодеид.  <br/> |
   

