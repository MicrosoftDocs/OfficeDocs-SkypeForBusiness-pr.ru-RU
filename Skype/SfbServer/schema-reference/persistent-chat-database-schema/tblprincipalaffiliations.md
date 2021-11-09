---
title: tblPrincipalAffiliations
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 45fd8484-5837-44d2-85bb-45c83546607c
description: tblPrincipalAffiliations содержит основные принадлежности, которые описывают членство в расположениях, включая группы безопасности active Directory Domain Services, в контейнерах Active Directory в доменах.
ms.openlocfilehash: f3625a9877fffdf024131e4a0f1611018d972660
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/08/2021
ms.locfileid: "60864606"
---
# <a name="tblprincipalaffiliations"></a>tblPrincipalAffiliations
 
tblPrincipalAffiliations содержит основные принадлежности, которые описывают членство в расположениях, включая группы безопасности active Directory Domain Services, в контейнерах Active Directory в доменах.
  
**Columns**

|**Столбец**|**Тип**|**Описание**|
|:-----|:-----|:-----|
|principalID  <br/> |int, NOT NULL  <br/> |Идентификатор присоединенного субъекта.  <br/> |
|affiliationID  <br/> |int, NOT NULL  <br/> |Идентификатор субъекта, представляющего присоединение. Каждый субъект (за исключением типов пользователей системы) также присоединен сам к себе.  <br/> |
|index  <br/> |int, NOT NULL  <br/> |Индекс. Значение для самостоятельной принадлежности — -1, а для других присоединений последовательно увеличивается с 1 в каждом \<principalID, affiliationId\> ведре.  <br/> |
|updatedBy  <br/> |int, NOT NULL  <br/> |Субъект, выполнивший последнее обновление. Обычно это 1, что означает синхронизацию с Active Directory.  <br/> |
   
**Keys**

|**Columns**|**Описание**|
|:-----|:-----|
|\<principalID, index, affiliationID\>  <br/> |Первичный ключ.  <br/> |
|principalID  <br/> |Внешний ключ с поиском в таблице tblPrincipal.prinID.  <br/> |
|affiliationID  <br/> |Внешний ключ с поиском в таблице tblPrincipal.prinID.  <br/> |
   

