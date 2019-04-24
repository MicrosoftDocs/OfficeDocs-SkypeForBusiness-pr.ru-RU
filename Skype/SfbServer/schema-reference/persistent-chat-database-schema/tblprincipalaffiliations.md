---
title: tblPrincipalAffiliations
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 45fd8484-5837-44d2-85bb-45c83546607c
description: Таблица tblPrincipalAffiliations содержит присоединения субъектов, которые описывают членство в расположениях, включая группы безопасности доменных служб Active Directory, контейнеры Active Directory и доменов.
ms.openlocfilehash: c93edb552c63ebd4f7344926a7d43858b42506ae
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212504"
---
# <a name="tblprincipalaffiliations"></a>tblPrincipalAffiliations
 
Таблица tblPrincipalAffiliations содержит присоединения субъектов, которые описывают членство в расположениях, включая группы безопасности доменных служб Active Directory, контейнеры Active Directory и доменов.
  
**Столбцы**

|**Столбец**|**Тип**|**Описание**|
|:-----|:-----|:-----|
|principalID  <br/> |int, не null  <br/> |Идентификатор присоединенного субъекта.  <br/> |
|affiliationID  <br/> |int, не null  <br/> |Идентификатор участника, представляющий принадлежность. Каждый участник (за исключением системы--пользователем) имеет также самораспаковывающийся принадлежность к.  <br/> |
|Индекс  <br/> |int, не null  <br/> |Индекс. Для назначения самораспаковывающийся значение -1, а для других принадлежности его последовательно увеличивается от 1 в каждой \<principalID affiliationId\> интервалов.  <br/> |
|updatedBy  <br/> |int, не null  <br/> |Участник, который выполнил последнее обновление. Обычно это 1, что означает синхронизации Active Directory.  <br/> |
   
**Ключи**

|**Столбцы**|**Описание**|
|:-----|:-----|
|\<principalID, индекса, affiliationID\>  <br/> |Первичный ключ.  <br/> |
|principalID  <br/> |Внешний ключ с подстановкой в таблице tblPrincipal.prinID.  <br/> |
|affiliationID  <br/> |Внешний ключ с подстановкой в таблице tblPrincipal.prinID.  <br/> |
   

