---
title: Использование PowerShell для задач по мониторингу и архивам меню
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
description: Сводка. Skype для бизнеса Server панели управления к сопоставлению cmdlet для меню Мониторинга и архивирования.
ms.openlocfilehash: b286cf1ad1f52e67c4e4171402927c24908aa4ac
ms.sourcegitcommit: 3b5ae6ebf4384166c628f66a4f17e6fe4455b708
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/29/2021
ms.locfileid: "61626485"
---
# <a name="monitoring-and-archiving"></a>Мониторинг и архивирование

В этой статье описывается, как  с помощью cmdlets можно добиться аналогичных результатов, как в элементе меню мониторинга и архива в устаревшей панели управления.

В этой статье описаны следующие подмены:

- [Мониторинг и архивирование](#monitoring-and-archiving)
  - [Запись сведений о звонке](#call-detail-recording)
  - [Качество данных по опыту](#quality-of-experience-data)
  - [Политика архивирования](#archiving-policy)
  - [Конфигурация архивирования](#archiving-configuration)

## <a name="call-detail-recording"></a>Запись сведений о звонке

**Подмена ЗАПИСИ** CALL DETAIL позволяет администраторам управлять настройками записи детализации вызовов (CDR). CDR позволяет отслеживать использование таких вещей, как одноранговые сеансы обмена мгновенными сообщениями, телефонные вызовы голосовой связи по протоколу Интернета (VoIP) и вызовы конференций.

Рассмотрим различные задачи, которые пользователь может выполнять в записи **CALL DETAIL,** и Skype для бизнеса эти задачи на карте.

---

> **Сценарий 1.** Список всех конфигураций CDR

   ![Конфигурация cdr списка](./media/cdr-configurations-1.png)

***Командлет***

[Get-CsCdrConfiguration](/powershell/module/skype/get-cscdrconfiguration)

***Пример***

```powershell
 Get-CsCdrConfiguration
```

---

> **Сценарий 2.** Создание новой конфигурации CDR

   ![Создание конфигурации cdr](./media/cdr-configurations-2.png)

***Командлет***

[New-CsCdrConfiguration](/powershell/module/skype/new-cscdrconfiguration)  

***Пример***

```powershell
 New-CsCdrConfiguration -Identity site:Redmond -EnableCDR $False
```

---

> **Сценарий 3.** Сведения о выбранной конфигурации CDR

   ![Получить конфигурацию cdr](./media/cdr-configurations-3.png)

***Командлет***

[Get-CsCdrConfiguration](/powershell/module/skype/get-cscdrconfiguration)

***Пример***

```powershell
 Get-CsCdrConfiguration -Identity site:Redmond
```

---

> **Сценарий 4.** Удаление выбранных конфигураций CDR

   ![Удаление конфигурации cdr](./media/cdr-configurations-4.png)

***Командлет***

[Remove-CsCdrConfiguration](/powershell/module/skype/remove-cscdrconfiguration)

***Пример***

```powershell
 Remove-CsCdrConfiguration -Identity site:Redmond
```

---

> **Сценарий 5.** Обновление конфигурации CDR

   ![Обновление конфигурации cdr](./media/cdr-configurations-5.png)

***Командлет***

[Set-CsCdrConfiguration](/powershell/module/skype/set-cscdrconfiguration)

***Пример***

```powershell
 Set-CsCdrConfiguration -Identity site:Redmond -PurgeHourOfDay 23
```

---

## <a name="quality-of-experience-data"></a>Качество данных по опыту

Под **меню QUALITY OF EXPERIENCE DATA** позволяет администраторам управлять настройками качества работы (QoE). по всей организации; это включает управление расширением групп, настройками сертификатов и разрешенными методами проверки подлинности. Так как администраторы могут настраивать различные параметры на глобальном уровне, на сайте и в области служб (хотя и только для службы веб-служб), можно настроить возможности веб-служб для разных пользователей и разных местоположений.

Рассмотрим различные задачи, которые пользователь может выполнять в ВЕБ-службе, и Skype для бизнеса эти задачи на карте.

---
> **Сценарий 1.** Список всех конфигураций QoE

   ![Конфигурация списка QoE](./media/qoe-configuration-1.png)

***Командлет***

[Get-CsQoEConfiguration](/powershell/module/skype/get-csqoeconfiguration)

***Пример***

```powershell
 Get-CsQoEConfiguration
```

---

> **Сценарий 2.** Создание новой конфигурации QoE

   ![Новая конфигурация QoE](./media/qoe-configuration-2.png)

***Командлет***

[New-CsQoEConfiguration](/powershell/module/skype/new-csqoeconfiguration)  

***Пример***

```powershell
 New-CsQoEConfiguration -Identity site:Redmond -EnableQoE $False
```

---

> **Сценарий 3.** Сведения о выбранной конфигурации QoE

   ![Настройка QoE](./media/qoe-configuration-3.png)

***Командлет***

[Get-CsQoEConfiguration](/powershell/module/skype/get-csqoeconfiguration)

***Пример***

```powershell
 Get-CsQoEConfiguration -Identity site:Redmond
```

---

> **Сценарий 4.** Удаление выбранных конфигураций QoE

   ![Удаление конфигурации QoE](./media/qoe-configuration-4.png)

***Командлет***

[Remove-CsQoEConfiguration](/powershell/module/skype/remove-csqoeconfiguration)

***Пример***

```powershell
 Remove-CsQoEConfiguration -Identity site:Redmond
```

---

> **Сценарий 5.** Обновление конфигурации QoE

   ![Обновление конфигурации QoE](./media/qoe-configuration-5.png)

***Командлет***

[Set-CsQoEConfiguration](/powershell/module/skype/set-csqoeconfiguration)

***Пример***

```powershell
 Set-CsQoEConfiguration -Identity site:Redmond -EnableQoE $False
```

---

## <a name="archiving-policy"></a>Политика архивирования

Администраторы могут использовать **ПОЛИТИКУ АРХИВА ДЛЯ** управления политиками архива сеансов обмена мгновенными сообщениями (IM). Политики архива позволяют архивировать все сеансы im и веб-конференций, которые проходят между внутренними пользователями и/или между внутренними пользователями и внешними пользователями.

Рассмотрим различные задачи, которые пользователь может выполнять в ПОЛИТИКЕ АРХИВА, и Skype для бизнеса эти задачи на карте.

---

> **Сценарий 1.** Список всех политик архива

   ![Политика архива списка](./media/archiving-policy-1.png)

***Командлет***

[Get-CsArchivingPolicy](/powershell/module/skype/get-csarchivingpolicy)

***Пример***

```powershell
 Get-CsArchivingPolicy
```

---

> **Сценарий 2.** Создание новой политики архива

   ![Создание политики архива](./media/archiving-policy-2.png)

***Командлет***

[New-CsArchivingPolicy](/powershell/module/skype/new-csarchivingpolicy)  

***Пример***

```powershell
 New-CsArchivingPolicy -Identity site:Redmond -ArchiveInternal $True
```

---

> **Сценарий 3.** Сведения об выбранной политике архива

   ![Политика архива](./media/archiving-policy-3.png)

***Командлет***

[Get-CsArchivingPolicy](/powershell/module/skype/get-csarchivingpolicy)

***Пример***

```powershell
 Get-CsArchivingPolicy -Identity site:Redmond
```

---

> **Сценарий 4.** Удаление выбранных политик архива

   ![Удаление политики архива](./media/archiving-policy-4.png)

***Командлет***

[Remove-CsArchivingPolicy](/powershell/module/skype/remove-csarchivingpolicy)

***Пример***

```powershell
 Remove-CsArchivingPolicy -Identity site:Redmond
```

---

> **Сценарий 5.** Обновление политики архива

   ![Политика обновления архива](./media/archiving-policy-5.png)

***Командлет***

[Set-CsArchivingPolicy](/powershell/module/skype/set-csarchivingpolicy)

***Пример***

```powershell
 Set-CsArchivingPolicy -Identity global -ArchiveInternal $True
```

---

## <a name="archiving-configuration"></a>Конфигурация архивирования

Администраторы могут использовать **КОНФИГУРАЦИЮ АРХИВАЦИИ** для настройки архивации сеансов обмена мгновенными сообщениями (или если) в организации.

Рассмотрим различные задачи, которые пользователь может выполнять в КОНФИГУРАЦИИ **АРХИВАЦИИ,** а также Skype для бизнеса эти задачи на карте.

---

> **Сценарий 1.** Список всех конфигураций архивации

   ![Конфигурация архивации списков](./media/archiving-configuration-1.png)

***Командлет***

[Get-CsArchivingConfiguration](/powershell/module/skype/get-csarchivingconfiguration)

***Пример***

```powershell
 Get-CsArchivingConfiguration
```

---

> **Сценарий 2.** Создание новой конфигурации архивации

   ![Создание конфигурации архивации](./media/archiving-configuration-2.png)

***Командлет***

[New-CsArchivingConfiguration](/powershell/module/skype/new-csarchivingconfiguration)  

***Пример***

```powershell
 New-CsArchivingConfiguration -Identity site:Redmond -EnableArchiving "ImOnly"
```

---

> **Сценарий 3.** Сведения о выбранной конфигурации архивации

   ![Настройка архивации](./media/archiving-configuration-3.png)

***Командлет***

[Get-CsArchivingConfiguration](/powershell/module/skype/get-csarchivingconfiguration)

***Пример***

```powershell
 Get-CsArchivingConfiguration -Identity site:Redmond
```

---

> **Сценарий 4.** Удаление выбранных конфигураций архивации

   ![Удаление конфигурации архивации](./media/archiving-configuration-4.png)

***Командлет***

[Remove-CsArchivingConfiguration](/powershell/module/skype/remove-csarchivingconfiguration)

***Пример***

```powershell
 Remove-CsArchivingConfiguration -Identity site:Redmond
```

---

> **Сценарий 5.** Обновление конфигурации архивации

   ![Обновление конфигурации архивации](./media/archiving-configuration-5.png)

***Командлет***

[Set-CsArchivingConfiguration](/powershell/module/skype/set-csarchivingconfiguration)

***Пример***

```powershell
 Set-CsArchivingConfiguration -Identity site:Redmond -ArchiveDuplicateMessages $False -KeepArchivingDataForDays 30
```

---
