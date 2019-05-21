---
title: tblPrincipalAffiliations
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 45fd8484-5837-44d2-85bb-45c83546607c
description: ТблпринЦипалаффилиатионс содержит основные сведения о членстве в расположениях, в том числе о группах безопасности доменных служб Active Directory, в контейнерах Active Directory в доменах.
ms.openlocfilehash: cda9827f4a4ab7e17a156cc867e4925c88d06ff3
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295316"
---
# <a name="tblprincipalaffiliations"></a>tblPrincipalAffiliations
 
ТблпринЦипалаффилиатионс содержит основные сведения о членстве в расположениях, в том числе о группах безопасности доменных служб Active Directory, в контейнерах Active Directory в доменах.
  
**Столбцов**

|**Столбец**|**Тип**|**Описание**|
|:-----|:-----|:-----|
|ПринЦипалид  <br/> |int, NOT NULL  <br/> |Идентификатор присоединенного участника.  <br/> |
|Аффилиатионид  <br/> |int, NOT NULL  <br/> |Идентификатор участника, представляющего назначение. Каждый принципал (за исключением системных типов пользователей) также имеет свое Самоназначение.  <br/> |
|индекса  <br/> |int, NOT NULL  <br/> |Индекса. Значение для самостоятельных принадлежностей —-1, а для других — для других — в пределах от 1 в каждом \<ПринЦипалид, аффилиатионид\> сегмент.  <br/> |
|Упдатедби  <br/> |int, NOT NULL  <br/> |Основной участник, который обновил Последнее обновление. Обычно это 1, что означает синхронизацию Active Directory.  <br/> |
   
**Параметры**

|**Столбцов**|**Описание**|
|:-----|:-----|
|\<ПринЦипалид, index, Аффилиатионид\>  <br/> |Первичный ключ.  <br/> |
|ПринЦипалид  <br/> |Внешний ключ с подстановкой в таблице ТблпринЦипал. Принид.  <br/> |
|Аффилиатионид  <br/> |Внешний ключ с подстановкой в таблице ТблпринЦипал. Принид.  <br/> |
   

