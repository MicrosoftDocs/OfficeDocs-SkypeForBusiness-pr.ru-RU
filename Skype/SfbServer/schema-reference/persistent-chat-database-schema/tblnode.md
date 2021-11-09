---
title: tblNode
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: a31d2961-aa83-4286-a12e-15d279c95f19
description: tblNode содержит дерево объектов (с узлами категории или комнаты чата), как управляется в панели управления и административных комлетах.
ms.openlocfilehash: 1e6d3a97f04d614a0993ca06d8a5b2a2f928b39d
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/08/2021
ms.locfileid: "60846252"
---
# <a name="tblnode"></a>tblNode
 
tblNode содержит дерево объектов (с узлами категории или комнаты чата), как управляется в панели управления и административных комлетах.
  
**Columns**

|**Столбец**|**Тип**|**Описание**|
|:-----|:-----|:-----|
|nodeID  <br/> |int, not null  <br/> |ИД узла (уникальное число).  <br/> |
|nodeGuid  <br/> |GUID, not null  <br/> |Глобальный уникальный ИД узла.  <br/> |
|parentID  <br/> |int  <br/> |ИД узла родительского элемента. Корневой узел (с ИД 1) включает себя в качестве родительского элемента.  <br/> |
|nodeType  <br/> |bit, not null  <br/> |True, если узел является категорией.  <br/> False, если узел является комнатой чата.  <br/> |
|nodeName  <br/> |nvarchar (256), not null  <br/> |Имя узла.  <br/> |
|nodeDesc  <br/> |nvarchar (256), not null  <br/> |Описание узла.  <br/> |
|invite  <br/> |bit  <br/> | Для категорий: <br/>  True, если приглашения включены. <br/>  False, если приглашения отключены. <br/>  Для комнат: <br/>  False, если приглашения отключены (переопределяет родительскую категорию). <br/>  Null, если настройки приглашений наследуются от родительской категории. <br/> |
|журнал  <br/> |bit  <br/> | Для категорий: <br/>  True, если журнал чата включен. <br/>  False, если журнал чата отключен. <br/>  Для комнат: <br/>  Null. <br/> |
|filePost  <br/> |bit  <br/> | Для категорий: <br/>  True, если передача файлов разрешена. <br/>  False, если передача файлов запрещена. <br/>  Для комнат: <br/>  Null. <br/> |
|отключено  <br/> |bit, not null  <br/> |True, если комната чата отключена. Применяется только к комнатам чата. (Для категорий — False.)  <br/> |
|поведение  <br/> |smallint, not null  <br/> | Поведение (поиск в таблице EnumValue): <br/>  4: Normal (обычные комнаты чата). <br/>  5: Auditorium (комнаты чата аудитории, участвовать могут только докладчики). <br/>  Применимо только к комнатам чата. <br/> |
|visibility  <br/> |smallint, not null  <br/> | Видимость (поиск в таблице EnumValue): <br/>  2: Private <br/>  3: Scoped <br/>  6: Open <br/>  Применяется только для комнат чата. <br/> |
|siopID  <br/> |GUID  <br/> |Глобальный уникальный ИД надстройки, если надстройка связана с этой комнатой чата. (Категории не имеют надстроек.)  <br/> Для поиска сведений о надстройках используется таблица SiopWhiteList.  <br/> |
|nodeAddedBy  <br/> |int, not null  <br/> |ИД субъекта, который создал этот узел.  <br/> |
|nodeAddedOn  <br/> |bigint, not null  <br/> |Метка времени создания узла.  <br/> |
|nodeUpdatedBy  <br/> |int, not null  <br/> |ИД субъекта, который выполнил последнее обновление этого узла.  <br/> |
|nodeUpdatedOn  <br/> |bigint, not null  <br/> |Метка времени последнего обновления этого узла.  <br/> |
|purgedOn  <br/> |datetime  <br/> |Время последней операции очистки (удаление областей из таблицы tblScopedPrincipal и ролей из таблицы tblPrincipalRole) для этого узла. Это используется внутренним механизмом обновления кэша службы чата.  <br/> |
   
**Keys**

|**Столбец**|**Описание**|
|:-----|:-----|
|nodeID  <br/> |Первичный ключ.  <br/> |
|поведение  <br/> |Внешний ключ с поиском в таблице tblEnumValue.valueID.  <br/> |
|visibility  <br/> |Внешний ключ с поиском в таблице tblEnumValue.valueID.  <br/> |
|parentID  <br/> |Внешний ключ с поиском в таблице tblNode.nodeID.  <br/> |
|siopID  <br/> |Внешний ключ с поиском в таблице tblSiopWhiteList.siopId.  <br/> |
   

