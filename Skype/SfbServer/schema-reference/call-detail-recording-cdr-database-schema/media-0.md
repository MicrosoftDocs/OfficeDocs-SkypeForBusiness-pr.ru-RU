---
title: Представление Media
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1a7b2e59-082e-4188-98ae-48ae9bd3494a
description: Представление Media сохранение информации о один тип носителя используется в сеансе peer-to-peer. Один сеанс может быть представлена нескольких записей в таблице, если используется более одного типа мультимедиа. В этом представлении была введена в Microsoft Lync Server 2013.
ms.openlocfilehash: 83caf609efae4e97961e7c62c3a1ed6c6004e8e8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33930695"
---
# <a name="media-view"></a>Представление Media
 
Представление Media сохранение информации о один тип носителя используется в сеансе peer-to-peer. Один сеанс может быть представлена нескольких записей в таблице, если используется более одного типа мультимедиа. В этом представлении была введена в Microsoft Lync Server 2013.
  
> [!NOTE]
> Представление Media не должен использоваться для расчета продолжительность мультимедиа для сеанса. Это представление содержит передачи сведений exchange мультимедиа в сеансе. Мультимедиа exchange, это делается путем запроса INVITE и StartTime указывает время отправки ПРИГЛАШЕНИЯ в работе. Время пригласить не означает, что время начала мультимедиа из-за мультимедиа начинается только после принятия сеанса. 
  
Представление Media содержит все столбцы [SessionDetails view](sessiondetails-0.md) Кроме перечисленных ниже.
  
|**Столбец**|**Тип данных**|**Сведения**|
|:-----|:-----|:-----|
|**Media** <br/> |nvarchar(256)  <br/> |Тип носителя. [Таблица MediaList](medialist.md) для получения дополнительных сведений см. <br/> |
|**MediaStartTime** <br/> |datetime  <br/> |Время отправки запроса мультимедиа.  <br/> |
|**MediaEndTime** <br/> |datetime  <br/> |Время окончания сеанса.  <br/> |
   

