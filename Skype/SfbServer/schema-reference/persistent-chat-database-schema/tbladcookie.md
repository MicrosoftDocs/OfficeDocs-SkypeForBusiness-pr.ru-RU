---
title: tblADCookie
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0a9102c4-47aa-40ea-8a0d-20e72ab09848
description: Тбладкукие включает в себя текущие cookie-файлы для синхронизации протокола Lightweight Directory Access.
ms.openlocfilehash: d75b1dc90d36aa0535fdac62b9e1a7061694cc76
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295533"
---
# <a name="tbladcookie"></a>tblADCookie
 
Тбладкукие включает в себя текущие cookie-файлы для синхронизации протокола Lightweight Directory Access.
  
**Столбцов**

|**Столбец**|**Тип**|**Описание**|
|:-----|:-----|:-----|
|Прингуид  <br/> |GUID, а не NULL  <br/> |Идентификатор GUID участника отслеживаемого домена.  <br/> |
|Приндчост  <br/> |nvarchar (255)  <br/> |Полное доменное имя (FQDN) текущего контроллера домена, используемого для синхронизации доменных служб Active Directory. Имеет информационное значение.  <br/> |
|Адкконтент  <br/> |изображение (двоичное)  <br/> |Cookie синхронизации Active Directory.  <br/> |
|Ластупдатед  <br/> |datetime  <br/> |Метка времени со временем обновления строки.  <br/> |
|Локкедунтил  <br/> |datetime  <br/> |Время, по истечении которого изменения строки будут заблокированы. Это является частью механизма программного обеспечения, который гарантирует, что только одна из служб чата выполняет синхронизацию службы каталогов Active Directory за один раз.  <br/> |
   
**Параметры**

|**Столбцы (-ы)**|**Описание**|
|:-----|:-----|
|Прингуид  <br/> |Первичный ключ.  <br/> |
|Прингуид  <br/> |Внешний ключ с подстановкой в таблице Principal. Прингуид.  <br/> |
   

