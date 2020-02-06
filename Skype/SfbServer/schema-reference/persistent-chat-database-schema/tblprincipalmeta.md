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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 808490d4-7d6d-47a2-b8af-b5940d47073b
description: ТблпринЦипалмета содержит участников, которые необходимо обновлять из доменных служб Active Directory.
ms.openlocfilehash: c76f4a74b3f627d360a2d745e46b6f2dac26bff0
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813577"
---
# <a name="tblprincipalmeta"></a>tblPrincipalMeta
 
ТблпринЦипалмета содержит участников, которые необходимо обновлять из доменных служб Active Directory.
  
**Столбцов**

|**Столбец**|**Тип**|**Описание**|
|:-----|:-----|:-----|
|принид  <br/> |int, NOT NULL  <br/> |Идентификатор участника.  <br/> |
|принаффилиатионсдирти  <br/> |bit, NOT NULL  <br/> |Значение true, если присвоить участникам участники необходимо обновлять.  <br/> |
|принаттрибутесдирти  <br/> |bit, NOT NULL  <br/> |Значение true, если атрибуты участника нужно обновить.  <br/> |
|принделетед  <br/> |bit, NOT NULL  <br/> |Значение true, если участник удален.  <br/> |
|трикаунт  <br/> |целое  <br/> |Количество попыток обновления участника из доменных служб Active Directory, произошедших в данный момент.  <br/> |
|ласттри  <br/> |datetime  <br/> |Метка времени последней попытки обновить участника. Может иметь значение null, если вы еще не пытались обновить обновление.  <br/> |
|нексттри  <br/> |datetime  <br/> |Метка времени для следующего запланированного обновления. Может иметь значение null, если дальнейшее обновление не запланировано.  <br/> |
   
**Параметры**

|**Столбец**|**Описание**|
|:-----|:-----|
|принид  <br/> |Первичный ключ.  <br/> |
|принид  <br/> |Внешний ключ с подстановкой в таблице ТблпринЦипал. Принид.  <br/> |
   

