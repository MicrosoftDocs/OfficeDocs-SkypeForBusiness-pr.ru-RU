---
title: tblPrincipalAffiliations
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
ms.openlocfilehash: 6126fb32b6b56c9a3ec142ad1b1186763f28d045
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/26/2021
ms.locfileid: "58580383"
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
   

