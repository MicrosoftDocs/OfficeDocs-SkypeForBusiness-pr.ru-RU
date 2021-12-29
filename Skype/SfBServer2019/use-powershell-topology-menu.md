---
title: Использование PowerShell для задач в меню Топология
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
description: Сводка. Skype для бизнеса Server панели управления к сопоставлению cmdlet для меню Топология.
ms.openlocfilehash: da5374863d7b9e7c8217802ce98e10cfdab92e54
ms.sourcegitcommit: 3b5ae6ebf4384166c628f66a4f17e6fe4455b708
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/29/2021
ms.locfileid: "61626482"
---
# <a name="topology"></a>Топология

В этой статье описывается, как аналогичные результаты элемента меню **Топология** в устаревшей панели управления могут быть достигнуты с помощью cmdlets.

В этой статье описаны следующие подмены:

- [Топология](#topology)
  - [Состояние](#status)
  - [Приложение server](#server-application)
  - [Простой URL-адрес](#simple-url)
  - [Надежное приложение](#trusted-application)

## <a name="status"></a>Статус

**Подмена STATUS** позволяет администраторам управлять компьютерами в топологии.

Рассмотрим различные задачи, которые пользователь может выполнять в **STATUS,** и Skype для бизнеса эти задачи на карте.

---

> **Сценарий 1.** Список всех компьютеров и их состояние

   ![Список компьютера и состояния](./media/topology-status-1.png)

   ***Командлет***

   [Get-CsPool](/powershell/module/skype/get-cspool)

   ***Пример***

   ```powershell
    Get-CsPool
   ```

   ***Командлет***

   [Get-CsComputer](/powershell/module/skype/get-cscomputer)

   ***Пример***

   ```powershell
    Get-CsComputer
   ```

   ***Командлет***

   [Get-CsManagementStoreReplicationStatus](/powershell/module/skype/get-csmanagementstorereplicationstatus)

   ***Пример***

   ```powershell
   Get-CsManagementStoreReplicationStatus
   ```

---

## <a name="server-application"></a>Приложение server

Серверные приложения относятся к отдельным программам, которые работают в Skype для бизнеса Server. **Подмена** ПРИЛОЖЕНИЯ SERVER предоставляет администраторам возможность возвращать сведения о любых (или всех) приложениях, запущенных в Skype для бизнеса Server.

Рассмотрим различные задачи, которые пользователь может выполнять в **ПРИЛОЖЕНИИ SERVER,** и Skype для бизнеса этих задач.

---
> **Сценарий 1.** Список всех серверных приложений

   ![Приложение List Server](./media/server-application-1.png)

***Командлет***

[Get-CsServerApplication](/powershell/module/skype/get-csserverapplication)

***Пример***

```powershell
 Get-CsServerApplication
```

---

> **Сценарий 2.** Включить/отключить или выбрать критически важное или неизбрать критическое серверного приложения

   ![Изменение приложения Server](./media/server-application-2.png)

***Командлет***

[Set-CsServerApplication](/powershell/module/skype/get-csserverapplication)

***Пример***

```powershell
 Set-CsServerApplication -Identity "Registrar:atl-cs-001.litwareinc.com/ExumRouting" -Enabled $True
```

---

## <a name="simple-url"></a>Простой URL-адрес

Простые URL-адреса упрощают пользователям присоединяться к собраниям и конференциям, а также упрощают доступ администраторов к панели управления Skype для бизнеса Server. Подмена URL-адресов **SIMPLE** помогает администратору просматривать их.

Рассмотрим различные задачи, которые пользователь может выполнять на **ПРОСТОМ** URL-адресе, и Skype для бизнеса эти задачи можно на карте.

---
> **Сценарий 1.** Список всех простых конфигураций URL-адресов

   ![Список простых URL-адресов](./media/simple-url-1.png)

***Командлет***

[Get-CsSimpleUrlConfiguration](/powershell/module/skype/get-cssimpleurlconfiguration)

***Пример***

```powershell
 Get-CsSimpleUrlConfiguration | Select-Object -ExpandProperty SimpleUrl
```

---

## <a name="trusted-application"></a>Надежное приложение

Доверенным приложением является приложение, разработанное третьей стороной, которому предоставляется доверенный статус для работы в Skype для бизнеса Server, но это не встроенная часть продукта. **Подмена TRUSTED APPLICATION** помогает администратору просматривать их.

Рассмотрим различные задачи, которые пользователь может выполнять в **TRUSTED APPLICATION,** и Skype для бизнеса эти задачи на карте.

---
> **Сценарий 1.** Список всех доверенных приложений

   ![Список доверенных приложений](./media/trusted-application-1.png)

***Командлет***

[Get-CsTrustedApplication](/powershell/module/skype/get-cstrustedapplication)

***Пример***

```powershell
 Get-CsTrustedApplication
```

---
