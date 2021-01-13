---
title: Представление VoIPDetails
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
localization_priority: Normal
ms.assetid: 14c44736-71ba-4fc5-82c7-1df65bf6261c
description: В представлении VoIPDetails хранится информация об одноранговых сеансах, где по крайней мере один пользователь является пользователем VoIP. Это представление впервые было введено в Microsoft Lync Server 2013.
ms.openlocfilehash: b42fecc7a0f43f86dba2439a373c7013c605a5e0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813079"
---
# <a name="voipdetails-view"></a>Представление VoIPDetails
 
В представлении VoIPDetails хранится информация об одноранговых сеансах, где по крайней мере один пользователь является пользователем VoIP. Это представление впервые было введено в Microsoft Lync Server 2013.
  
> [!NOTE]
> Представление VoIPDetails содержит все столбцы в представлении [SessionDetails,](sessiondetails-0.md) а также столбцы, перечисленные ниже.
  
|**Столбец**|**Тип данных**|**Details**|
|:-----|:-----|:-----|
|**FromPhone** <br/> |nvarchar(450)  <br/> |URI телефона пользователя, занявшего сеанс.  <br/> |
|**ToPhone** <br/> |nvarchar(450)  <br/> |URI телефона пользователя, который присоединился к сеансу.  <br/> |
|**DisconnectedByUri** <br/> |nvarchar(450)  <br/> |URI пользователя, отключившего сеанс.  <br/> |
|**DisconnectedByUriType** <br/> |nvarchar(256)  <br/> |Тип URI пользователя, отключившего сеанс. Дополнительные сведения см. в таблице [UriTypes.](uritypes.md) <br/> |
|**DisconnectedByTenant** <br/> |nvarchar(256)  <br/> |Клиент пользователя, отключившего сеанс.  <br/> |
|**DisconnectedByPhone** <br/> |nvarchar(450)  <br/> |URI телефона пользователя, отключившего сеанс.  <br/> |
|**FromMediationServer** <br/> |nvarchar(256)  <br/> |Сервер-посредник, используемый пользователем, который запустил сеанс.  <br/> |
|**ToMediationServer** <br/> |nvarchar(256)  <br/> |Сервер-посредник, используемый пользователем, который присоединился к сеансу.  <br/> |
|**FromGateway** <br/> |nvarchar(256)  <br/> |Шлюз, используемый пользователем, который запустил сеанс.  <br/> |
|**ToGateway** <br/> |nvarchar(256)  <br/> |Шлюз, используемый пользователем, который присоединился к сеансу.  <br/> |
   

