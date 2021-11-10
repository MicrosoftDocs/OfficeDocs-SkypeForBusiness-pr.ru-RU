---
title: Использование PowerShell для задач в меню im и Presence
ms.reviewer: ''
ms.author: ankum
author: ankum
manager: ravrao
ms.date: 11/03/2021
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: ''
description: Сводка. Skype для бизнеса Server панели управления к сопоставлению cmdlet для меню im и Presence.
ms.openlocfilehash: 9d57e249fb839894454c05d25e78320153d4a306
ms.sourcegitcommit: 11a803d569a57410e7e648f53b28df80a53337b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/10/2021
ms.locfileid: "60888788"
---
# <a name="im-and-presence"></a>Обмен мгновенными сообщениями и сведениями о присутствии

В этой статье описывается, как аналогичные результаты элемента меню im и **Presence** в устаревшей панели управления могут быть достигнуты с помощью cmdlets.

В этой статье описаны следующие подмены:

- [Чат и присутствие](#im-and-presence)
  - [Фильтр файлов](#file-filter)
  - [Фильтр URL-адресов](#url-filter)

## <a name="file-filter"></a>Фильтр файлов

**Подмена FILE FILTER** позволяет администраторам управлять конфигурациями фильтров передачи файлов в организации. Эти конфигурации используются для блокировки возможности пользователя передавать определенные типы файлов (например, файлы с расширением файла .vbs или .ps1) с помощью Skype для бизнеса Server клиента.

Рассмотрим различные задачи, которые пользователь может выполнять в **ФАЙЛОВОМ** ФИЛЬТРЕ, и Skype для бизнеса эти задачи будут выполняться на карте.

---

> **Сценарий 1.** Список всех фильтров файлов

   ![Фильтр файлов списка](./media/file-filter-1.png)

***Командлет***

[Get-CsFileTransferFilterConfiguration](/powershell/module/skype/get-csfiletransferfilterconfiguration)

***Пример***

```powershell
 Get-CsFileTransferFilterConfiguration
```

---

> **Сценарий 2.** Создание нового фильтра файлов

   ![Создание фильтра файлов](./media/file-filter-2.png)

***Командлет***

[New-CsFileTransferFilterConfiguration](/powershell/module/skype/new-csfiletransferfilterconfiguration)  

***Пример***

```powershell
 New-CsFileTransferFilterConfiguration -Identity site:Redmond
```

---

> **Сценарий 3.** Сведения об выбранном фильтре файлов

   ![Получить фильтр файлов](./media/file-filter-3.png)

***Командлет***

[Get-CsFileTransferFilterConfiguration](/powershell/module/skype/get-csfiletransferfilterconfiguration)

***Пример***

```powershell
 Get-CsFileTransferFilterConfiguration -Identity site:Redmond
```

---

> **Сценарий 4.** Удаление выбранных фильтров файлов

   ![Удаление фильтра файлов](./media/file-filter-4.png)

***Командлет***

[Remove-CsFileTransferFilterConfiguration](/powershell/module/skype/remove-csfiletransferfilterconfiguration)

***Пример***

```powershell
 Remove-CsFileTransferFilterConfiguration -Identity site:Redmond
```

---

> **Сценарий 5.** Обновление фильтра файлов

   ![Обновление фильтра файлов](./media/file-filter-5.png)

***Командлет***

[Set-CsFileTransferFilterConfiguration](/powershell/module/skype/set-csfiletransferfilterconfiguration)

***Пример***

```powershell
 Set-CsFileTransferFilterConfiguration -Identity site:Redmond -Extensions @{Add=".ps1"}
```

---

## <a name="url-filter"></a>Фильтр URL-адресов

Элемент **URL-фильтра** в  чате и присутствии позволяет администраторам настраивать URL-фильтр, чтобы гиперссылки с определенными префиксами блокировали или не были активны. (Другими словами, участники не могут просто щелкнуть ссылку и перейти на сайт, на который ссылается URI; они должны копировать и вклеить ссылку вручную в браузер.)

Рассмотрим различные задачи, которые пользователь может выполнять в URL-фильтре, а также Skype для бизнеса эти задачи.

---
> **Сценарий 1.** Список всех фильтров URL-адресов

   ![Фильтр URL-адреса списка](./media/url-filter-1.png)

***Командлет***

[Get-CsImFilterConfiguration](/powershell/module/skype/get-csimfilterconfiguration)

***Пример***

```powershell
 Get-CsImFilterConfiguration
```

---

> **Сценарий 2.** Создание нового URL-фильтра

   ![Новый фильтр URL-адреса](./media/url-filter-2.png)

***Командлет***

[New-CsImFilterConfiguration](/powershell/module/skype/new-csimfilterconfiguration)  

***Пример***

```powershell
 New-CsImFilterConfiguration -Identity site:Redmond
```

---

> **Сценарий 3.** Сведения об выбранном URL-фильтре

   ![Получить ФИЛЬТР URL-адреса](./media/url-filter-3.png)

***Командлет***

[Get-CsImFilterConfiguration](/powershell/module/skype/get-csimfilterconfiguration)

***Пример***

```powershell
 Get-CsImFilterConfiguration -Identity site:Redmond
```

---

> **Сценарий 4.** Удаление выбранных URL-фильтров

   ![Удаление фильтра URL-адреса](./media/url-filter-4.png)

***Командлет***

[Remove-CsImFilterConfiguration](/powershell/module/skype/remove-csimfilterconfiguration)

***Пример***

```powershell
 Remove-CsImFilterConfiguration -Identity site:Redmond
```

---

> **Сценарий 5.** Обновление URL-фильтра

   ![Обновление URL-фильтра](./media/url-filter-5.png)

***Командлет***

[Set-CsImFilterConfiguration](/powershell/module/skype/set-csimfilterconfiguration)

***Пример***

```powershell
 Set-CsImFilterConfiguration -Identity site:Redmond -Enabled $False
```

---
