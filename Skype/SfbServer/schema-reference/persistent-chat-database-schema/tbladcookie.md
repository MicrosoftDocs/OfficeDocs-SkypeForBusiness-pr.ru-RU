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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 0a9102c4-47aa-40ea-8a0d-20e72ab09848
description: Тбладкукие включает в себя текущие cookie-файлы для синхронизации протокола Lightweight Directory Access.
ms.openlocfilehash: c9a4c666a5fe4a76ecb3685f60f1208ec3ea88ed
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814707"
---
# <a name="tbladcookie"></a>tblADCookie
 
Тбладкукие включает в себя текущие cookie-файлы для синхронизации протокола Lightweight Directory Access.
  
**Столбцов**

|**Столбец**|**Тип**|**Описание**|
|:-----|:-----|:-----|
|прингуид  <br/> |GUID, а не NULL  <br/> |Идентификатор GUID участника отслеживаемого домена.  <br/> |
|приндчост  <br/> |nvarchar (255)  <br/> |Полное доменное имя (FQDN) текущего контроллера домена, используемого для синхронизации доменных служб Active Directory. Имеет информационное значение.  <br/> |
|адкконтент  <br/> |изображение (двоичное)  <br/> |Cookie синхронизации Active Directory.  <br/> |
|ластупдатед  <br/> |datetime  <br/> |Метка времени со временем обновления строки.  <br/> |
|локкедунтил  <br/> |datetime  <br/> |Время, по истечении которого изменения строки будут заблокированы. Это является частью механизма программного обеспечения, который гарантирует, что только одна из служб чата выполняет синхронизацию службы каталогов Active Directory за один раз.  <br/> |
   
**Параметры**

|**Столбцы (-ы)**|**Описание**|
|:-----|:-----|
|прингуид  <br/> |Первичный ключ.  <br/> |
|прингуид  <br/> |Внешний ключ с подстановкой в таблице Principal. Прингуид.  <br/> |
   

