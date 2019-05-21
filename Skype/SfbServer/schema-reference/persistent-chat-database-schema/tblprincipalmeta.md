---
title: tblPrincipalMeta
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 808490d4-7d6d-47a2-b8af-b5940d47073b
description: ТблпринЦипалмета содержит участников, которые необходимо обновлять из доменных служб Active Directory.
ms.openlocfilehash: 9cff5b2515613ac3540d82e545862bf4fdb58b94
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295260"
---
# <a name="tblprincipalmeta"></a>tblPrincipalMeta
 
ТблпринЦипалмета содержит участников, которые необходимо обновлять из доменных служб Active Directory.
  
**Столбцов**

|**Столбец**|**Тип**|**Описание**|
|:-----|:-----|:-----|
|Принид  <br/> |int, NOT NULL  <br/> |Идентификатор участника.  <br/> |
|Принаффилиатионсдирти  <br/> |bit, NOT NULL  <br/> |Значение true, если присвоить участникам участники необходимо обновлять.  <br/> |
|Принаттрибутесдирти  <br/> |bit, NOT NULL  <br/> |Значение true, если атрибуты участника нужно обновить.  <br/> |
|Принделетед  <br/> |bit, NOT NULL  <br/> |Значение true, если участник удален.  <br/> |
|Трикаунт  <br/> |целое  <br/> |Количество попыток обновления участника из доменных служб Active Directory, произошедших в данный момент.  <br/> |
|Ласттри  <br/> |datetime  <br/> |Метка времени последней попытки обновить участника. Может иметь значение null, если вы еще не пытались обновить обновление.  <br/> |
|Нексттри  <br/> |datetime  <br/> |Метка времени для следующего запланированного обновления. Может иметь значение null, если дальнейшее обновление не запланировано.  <br/> |
   
**Параметры**

|**Столбец**|**Описание**|
|:-----|:-----|
|Принид  <br/> |Первичный ключ.  <br/> |
|Принид  <br/> |Внешний ключ с подстановкой в таблице ТблпринЦипал. Принид.  <br/> |
   

