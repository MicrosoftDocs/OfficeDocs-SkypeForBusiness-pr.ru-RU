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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 45fd8484-5837-44d2-85bb-45c83546607c
description: ТблпринЦипалаффилиатионс содержит основные сведения о членстве в расположениях, в том числе о группах безопасности доменных служб Active Directory, в контейнерах Active Directory в доменах.
ms.openlocfilehash: 542bcc333d815b0577aec1fb11d4070540150d3c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814477"
---
# <a name="tblprincipalaffiliations"></a>tblPrincipalAffiliations
 
ТблпринЦипалаффилиатионс содержит основные сведения о членстве в расположениях, в том числе о группах безопасности доменных служб Active Directory, в контейнерах Active Directory в доменах.
  
**Столбцов**

|**Столбец**|**Тип**|**Описание**|
|:-----|:-----|:-----|
|принЦипалид  <br/> |int, NOT NULL  <br/> |Идентификатор присоединенного участника.  <br/> |
|аффилиатионид  <br/> |int, NOT NULL  <br/> |Идентификатор участника, представляющего назначение. Каждый принципал (за исключением системных типов пользователей) также имеет свое Самоназначение.  <br/> |
|индекса  <br/> |int, NOT NULL  <br/> |Индекса. Значение для самостоятельных принадлежностей —-1, а для других — для других — в пределах от 1 в каждом \<ПринЦипалид, аффилиатионид\> сегмент.  <br/> |
|упдатедби  <br/> |int, NOT NULL  <br/> |Основной участник, который обновил Последнее обновление. Обычно это 1, что означает синхронизацию Active Directory.  <br/> |
   
**Параметры**

|**Столбцов**|**Описание**|
|:-----|:-----|
|\<ПринЦипалид, index, Аффилиатионид\>  <br/> |Первичный ключ.  <br/> |
|принЦипалид  <br/> |Внешний ключ с подстановкой в таблице ТблпринЦипал. Принид.  <br/> |
|аффилиатионид  <br/> |Внешний ключ с подстановкой в таблице ТблпринЦипал. Принид.  <br/> |
   

