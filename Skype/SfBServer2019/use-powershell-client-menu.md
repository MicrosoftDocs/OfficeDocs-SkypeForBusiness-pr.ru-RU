---
title: Использование PowerShell для задач в меню клиента
ms.reviewer: ''
ms.author: v-smandalika
author: v-smandalika
manager: dansimp
ms.date: 10/12/2021
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: ''
description: Сводка. Skype для бизнеса Server панели управления к сопоставлению cmdlet для клиентского меню.
ms.openlocfilehash: 1dc0c3a9638af8fdec90fccb633909b9ccf40405
ms.sourcegitcommit: eba9fc680233e9e03773a2942f22afe6247eec41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/08/2021
ms.locfileid: "60824657"
---
# <a name="client"></a>Client

В этой статье описывается, как  с помощью cmdlets можно добиться аналогичных результатов элемента меню Клиента в устаревшей панели управления.

В этой статье описаны следующие подмены:

- [Клиент](#client)
  - [Политика версий клиентов](#client-version-policy)
  - [Конфигурация версий клиентов](#client-version-configuration)
  - [Обновление устройств](#device-update)
  - [Тестовое устройство](#test-device)
  - [Конфигурация журнала устройств](#device-log-configuration)
  - [Конфигурация устройств](#device-configuration)
  - [Политика мобильности](#mobility-policy)
  - [Конфигурация push-уведомлений](#push-notification-configuration)

## <a name="client-version-policy"></a>Политика версий клиентов

Элемент **подмены** CLIENT VERSION POLICY в меню **Client** возвращает сведения о клиентах, поддерживаемых Skype для бизнеса Server среде. Политика клиентских версий позволяет указать тех клиентов, которые могут войти в Skype для бизнеса Server систему.

Рассмотрим различные задачи, которые пользователь может выполнять в ПОЛИТИКЕ **CLIENT VERSION,** и Skype для бизнеса этих задач.

---
> **Сценарий 1.** Список всех политик клиентской версии

   ![Политика версии списка клиентов](./media/clientversionpolicy-1.png)

***Командлет***

[Get-CsClientVersionPolicy](/powershell/module/skype/get-csclientversionpolicy)

***Пример***

```powershell
 Get-CsClientVersionPolicy
```

---

> **Сценарий 2.** Создание новой политики клиентской версии

   ![Политика новой клиентской версии](./media/clientversionpolicy-2.png)

***Командлет***

[New-CsClientVersionPolicy](/powershell/module/skype/new-csclientversionpolicy)  

***Пример***

```powershell
 New-CsClientVersionPolicy -Identity site:Redmond
```

---

> **Сценарий 3.** Сведения о выбранной политике клиентской версии

   ![Получить политику клиентских версий](./media/clientversionpolicy-3.png)

***Командлет***

[Get-CsClientVersionPolicy](/powershell/module/skype/get-csclientversionpolicy)

***Пример***

```powershell
 Get-CsClientVersionPolicy -Identity site:Redmond
```

---

> **Сценарий 4.** Удаление политик выбранных клиентских версий

   ![Удаление политики клиентских версий](./media/clientversionpolicy-4.png)

***Командлет***

[Remove-CsClientVersionPolicy](/powershell/module/skype/remove-csclientversionpolicy)

***Пример***

```powershell
 Remove-CsClientVersionPolicy -Identity site:Redmond
```

---

> **Сценарий 5.** Обновление политики клиентской версии

   ![Обновление политики клиентских версий](./media/clientversionpolicy-5.png)

- **Аннотация 1 — результат**

    Эта аннотация на изображении указывает результат, то есть полученные и отображаемые данные.

    ***Командлет***

    [Get-CsClientVersionPolicyRule](/powershell/module/skype/get-csclientversionpolicyrule)

    ***Пример***

    ```powershell
    Get-CsClientVersionPolicyRule -Filter "Global/*"
    ```

- **Аннотация 2 — параметр (для пользователя)**

    Эта аннотация на изображении указывает на возможность реализации пользователем, то есть получения сведений о правилах политики клиентской версии.

    ***Командлет***

    [Get-CsClientVersionPolicyRule](/powershell/module/skype/get-csclientversionpolicyrule)

    ***Пример***

    ```powershell
    Get-CsClientVersionPolicyRule -Identity "Global/2336c611-a243-4c5d-994b-eea8a524d0e4"
    ```

- **Аннотация 3 . Параметр (для пользователя)**

    Эта аннотация на изображении указывает на возможность для пользователя реализовать, то есть создать новое правило политики клиентской версии.

    ***Командлет***

    [New-CsClientVersionPolicyRule](/powershell/module/skype/new-csclientversionpolicyrule)

    ***Пример***

    ```powershell
    $x = \[guid\]::NewGuid()

    New-CsClientVersionPolicyRule -Parent "site:Redmond" -RuleId $x -MajorVersion 4 -UserAgent InHouse
    ```

- **Аннотация 4 . Параметр (для пользователя)**

    Эта аннотация на изображении указывает пользователю возможность реализации, то есть фиксации/сохранения правила политики клиентской версии.

    ***Командлет***

    [Set-CsClientVersionPolicy](/powershell/module/skype/set-csclientversionpolicy)

    ***Пример***

    ```powershell
    Set-CsClientVersionPolicy -Identity site:Redmond -Rules $Null

    $x = Get-CsClientVersionPolicy -Identity site:Dublin | Select-Object -ExpandProperty Rules

    Set-CsClientVersionPolicy -Identity site:Redmond -Rules $x
    ```

---

## <a name="client-version-configuration"></a>Конфигурация версий клиентов

 Элемент **КОНФИГУРАЦИИ CLIENT VERSION** возвращает сведения о клиентах, поддерживаемых в Skype для бизнеса Server среде.

Рассмотрим различные задачи, которые пользователь может выполнять в КОНФИГУРАЦИИ **КЛИЕНТ** ВЕРСИИ, и Skype для бизнеса эти задачи на карте.

---
> **Сценарий 1.** Список всех конфигураций клиентской версии

   ![Конфигурация клиентской версии списка](./media/ClientVersionConfiguration-1.png)

***Командлет***

[Get-CsClientVersionConfiguration](/powershell/module/skype/get-csclientversionconfiguration)

***Пример***

```powershell
 Get-CsClientVersionConfiguration
```

---

> **Сценарий 2.** Создание новой конфигурации клиентской версии

   ![Создание конфигурации клиентской версии](./media/ClientVersionConfiguration-2.png)

***Командлет***

[New-CsClientVersionConfiguration](/powershell/module/skype/new-csclientversionconfiguration)  

***Пример***

```powershell
 New-CsClientVersionConfiguration -Identity site:Redmond -Enabled $False
```

---

> **Сценарий 3.** Сведения о конфигурации выбранной клиентской версии

   ![Настройка клиентской версии](./media/ClientVersionConfiguration-3.png)

***Командлет***

[Get-CsClientVersionConfiguration](/powershell/module/skype/get-csclientversionconfiguration)

***Пример***

```powershell
 Get-CsClientVersionConfiguration -Identity site:Redmond
```

---

> **Сценарий 4.** Удаление конфигураций выбранных клиентских версий

   ![Удаление конфигурации клиентской версии](./media/ClientVersionConfiguration-4.png)

***Командлет***

[Remove-CsClientVersionConfiguration](/powershell/module/skype/remove-csclientversionconfiguration)

***Пример***

```powershell
 Remove-CsClientVersionConfiguration -Identity site:Redmond
```

---

> **Сценарий 5.** Обновление конфигурации клиентской версии

   ![Обновление конфигурации клиентской версии](./media/ClientVersionConfiguration-5.png)

***Командлет***

[Set-CsClientVersionConfiguration](/powershell/module/skype/set-csclientversionconfiguration)

***Пример***

```powershell
Get-CsClientVersionConfiguration | Set-CsClientVersionConfiguration -DefaultURL "https://litwareinc.com/csclients"
```

---

> **Сценарий 6.** Включить и отключить конфигурации клиентской версии

![Включить конфигурацию клиентской версии](./media/ClientVersionConfiguration-6.png)

***Командлет***

[Set-CsClientVersionConfiguration](/powershell/module/skype/set-csclientversionconfiguration)

***Пример***

```powershell
Set-CsClientVersionConfiguration -Identity site:Redmond -Enabled $False
```

---

## <a name="device-update"></a>Обновление устройств

**Правила ОБНОВЛЕНИЯ УСТРОЙСТВА** используются для связи обновлений прошивки с устройствами, Skype для бизнеса Телефон Edition.

Рассмотрим различные задачи, которые пользователь может выполнять в ОБНОВЛЕНИИ **УСТРОЙСТВА,** и Skype для бизнеса эти задачи на карте.

---
> **Сценарий 1.** Список всех обновлений устройств

   ![Обновление устройства списка](./media/device-update-1.png)

***Командлет***

[Get-CsDeviceUpdateRule](/powershell/module/skype/get-csdeviceupdaterule)

***Пример***

```powershell
 Get-CsDeviceUpdateRule
```

---

> **Сценарий 2.** Удаление обновлений устройств

   ![Удаление обновления устройства](./media/device-update-2.png)

***Командлет***

[Remove-CsDeviceUpdateRule](/powershell/module/skype/remove-csdeviceupdaterule)  

***Пример***

```powershell
 Remove-CsDeviceUpdateRule -Identity service:WebServer:atl-cs-001.litwareinc.com/d5ce3c10-2588-420a-82ac-dc2d9b1222ff9
```

---

> **Сценарий 3.** Отмена обновлений устройств

   ![Отмена обновления устройства](./media/device-update-3.png)

***Командлет***

[Clear-CsDeviceUpdateFile](/powershell/module/skype/clear-csdeviceupdatefile)

***Пример***

```powershell
 Clear-CsDeviceUpdateFile -Identity "service:WebServer:atl-cs-001.litwareinc.com"
```

---

> **Сценарий 4.** Утверждение обновлений устройств

   ![Утверждение обновления устройства](./media/device-update-4.png)

***Командлет***

[Approve-CsDeviceUpdateRule](/powershell/module/skype/approve-csdeviceupdaterule)

***Пример***

```powershell
 Approve-CsDeviceUpdateRule -Identity service:WebServer:atl-cs-001.litwareinc.com/d5ce3c10-2588-420a-82ac-dc2d9b1222ff9
```

---

> **Сценарий 5.** Восстановление обновлений устройств

   ![Восстановление обновления устройства](./media/device-update-5.png)

***Командлет***

[Restore-CsDeviceUpdateRule](/powershell/module/skype/restore-csdeviceupdaterule)

***Пример***

```powershell
 Restore-CsDeviceUpdateRule -Identity service:WebServer:atl-cs-001.litwareinc.com/d5ce3c10-2588-420a-82ac-dc2d9b1222ff9
```

---

## <a name="test-device"></a>Тестовое устройство

Элемент **подпрограммы TEST DEVICE** предоставляет администраторам возможность протестировать обновления прошивки до их распространения на все устройства в организации.

Рассмотрим различные задачи, которые пользователь может выполнять на **УСТРОЙСТВЕ TEST,** и Skype для бизнеса эти задачи на карте.

---
> **Сценарий 1.** Список всех тестовых устройств

   ![Тестовый прибор списка](./media/testdevice-1.png)

***Командлет***

[Get-CsTestDevice](/powershell/module/skype/get-cstestdevice)

***Пример***

```powershell
 Get-CsTestDevice
```

---

> **Сценарий 2.** Создание нового тестового устройства

   ![Создание тестового устройства](./media/testdevice-2.png)

***Командлет***

[New-CsTestDevice](/powershell/module/skype/new-cstestdevice)  

***Пример***

```powershell
 New-CsTestDevice -Identity site:Redmond/UCPhone -IdentifierType SerialNumber -Identifier "07823-A345"
```

---

> **Сценарий 3.** Сведения об выбранном тестовом устройстве

   ![Получить тестовую устройство](./media/testdevice-3.png)

***Командлет***

[Get-CsTestDevice](/powershell/module/skype/get-cstestdevice)

***Пример***

```powershell
 Get-CsTestDevice -Identity site:Redmond/UCPhone
```

---

> **Сценарий 4.** Удаление выбранных тестовых устройств

   ![Удаление тестового устройства](./media/testdevice-4.png)

***Командлет***

[Remove-CsTestDevice](/powershell/module/skype/remove-cstestdevice)

***Пример***

```powershell
 Remove-CsTestDevice -Identity site:Redmond
```

---

> **Сценарий 5.** Обновление тестового устройства

   ![Обновление тестового устройства](./media/testdevice-5.png)

***Командлет***

[Set-CsTestDevice](/powershell/module/skype/set-cstestdevice)

***Пример***

```powershell
Set-CsTestDevice -Identity site:Redmond/UCPhone -IdentifierType SerialNumber -Identifier "09768-ABDR-83295"
```

---

## <a name="device-log-configuration"></a>Конфигурация журнала устройств

**Элемент подпрограммы** КОНФИГУРАЦИЯ ЖУРНАЛА УСТРОЙСТВ помогает управлять веб-службой обновления устройств , компонентом Skype для бизнеса Server, который позволяет администраторам распространять обновления прошивки на телефоны и другие устройства, которые работают Skype для бизнеса.

Рассмотрим различные задачи, которые пользователь может выполнять в КОНФИГУРАЦИИ ЖУРНАЛА **УСТРОЙСТВ,** и Skype для бизнеса эти задачи на карте.

---
> **Сценарий 1.** Список всех конфигураций журнала устройств

   ![Конфигурация журнала журнала устройств списка](./media/device-log-configuration-1.png)

***Командлет***

[Get-CsDeviceUpdateConfiguration](/powershell/module/skype/get-csdeviceupdateconfiguration)

***Пример***

```powershell
 Get-CsDeviceUpdateConfiguration
```

---

> **Сценарий 2.** Создание новой конфигурации журнала устройств

   ![Создание конфигурации журнала устройств](./media/device-log-configuration-2.png)

***Командлет***

[New-CsDeviceUpdateConfiguration](/powershell/module/skype/new-csdeviceupdateconfiguration)  

***Пример***

```powershell
 New-CsDeviceUpdateConfiguration -Identity site:Redmond "07823-A345"
```

---

> **Сценарий 3.** Сведения о выбранной конфигурации журнала устройств

   ![Настройка журнала устройств](./media/device-log-configuration-3.png)

***Командлет***

[Get-CsDeviceUpdateConfiguration](/powershell/module/skype/get-csdeviceupdateconfiguration)

***Пример***

```powershell
 Get-CsDeviceUpdateConfiguration -Identity Global
```

---

> **Сценарий 4.** Удаление выбранных конфигураций журнала устройств

   ![Удаление конфигурации журнала устройств](./media/device-log-configuration-4.png)

***Командлет***

[Remove-CsDeviceUpdateConfiguration](/powershell/module/skype/remove-csdeviceupdateconfiguration)

***Пример***

```powershell
 Remove-CsDeviceUpdateConfiguration -Identity site:Redmond
```

---

> **Сценарий 5.** Обновление конфигурации журнала устройств

   ![Обновление конфигурации журнала устройств](./media/device-log-configuration-5.png)

***Командлет***

[Set-CsDeviceUpdateConfiguration](/powershell/module/skype/set-csdeviceupdateconfiguration)

***Пример***

```powershell
Set-CsDeviceUpdateConfiguration -Identity global -MaxLogFileSize 2048000 -MaxLogCacheLimit 1024000
```

---

## <a name="device-configuration"></a>Конфигурация устройств

**Элемент КОНФИГУРАЦИИ** УСТРОЙСТВА помогает управлять сведениями о параметрах управления для телефонов UC. Эти параметры включают необходимый режим безопасности и возможность автоматической блокировки телефона после указанного периода бездействия.

Рассмотрим различные задачи, которые пользователь может выполнять в КОНФИГУРАЦИИ **УСТРОЙСТВА,** и Skype для бизнеса эти задачи на карте.

---

> **Сценарий 1.** Список всех политик мобильности

   ![Конфигурация устройства списка](./media/device-configuration-1.png)

***Командлет***

[Get-CsUCPhoneConfiguration](/powershell/module/skype/get-csucphoneconfiguration)

***Пример***

```powershell
 Get-CsUCPhoneConfiguration
```

---

> **Сценарий 2.** Создание новой конфигурации устройства

   ![Создание конфигурации устройств](./media/device-configuration-2.png)

***Командлет***

[New-CsUCPhoneConfiguration](/powershell/module/skype/new-csucphoneconfiguration)  

***Пример***

```powershell
 New-CsUCPhoneConfiguration -Identity site:Redmond -CalendarPollInterval "00:10:00" -LoggingLevel "Medium"
```

---

> **Сценарий 3.** Сведения о выбранной конфигурации устройства

   ![Настройка устройства](./media/device-configuration-3.png)

***Командлет***

[Get-CsUCPhoneConfiguration](/powershell/module/skype/get-csucphoneconfiguration)

***Пример***

```powershell
 Get-CsUCPhoneConfiguration -Identity site:Redmond
```

---

> **Сценарий 4.** Удаление выбранных конфигураций устройств

   ![Удаление конфигурации устройства](./media/device-configuration-4.png)

***Командлет***

[Remove-CsUCPhoneConfiguration](/powershell/module/skype/remove-csucphoneconfiguration)

***Пример***

```powershell
 Remove-CsUCPhoneConfiguration -Identity site:Redmond
```

---

> **Сценарий 5.** Обновляет конфигурацию устройства

   ![Обновление конфигурации устройства](./media/device-configuration-5.png)

***Командлет***

[Set-CsUCPhoneConfiguration](/powershell/module/skype/set-csucphoneconfiguration)

***Пример***

```powershell
 Set-CsUCPhoneConfiguration -Identity site:Redmond -PhoneLockTimeout "00:30:00"
```

---

## <a name="mobility-policy"></a>Политика мобильности

**ПОЛИТИКА МОБИЛЬНОСТИ** определяет, может ли пользователь использовать Skype для бизнеса Mobile. Эта функция позволяет пользователям выполнять и принимать телефонные звонки с помощью мобильного телефона, используя при этом номер рабочего телефона. Политики мобильности также могут использоваться для Wi-Fi подключения при принятии или приеме вызовов.

Рассмотрим различные задачи, которые пользователь может выполнять в политике **МОБИЛЬНОСТИ,** и Skype для бизнеса эти задачи на карте.

---

> **Сценарий 1.** Список всех политик мобильности

   ![Политика мобильности списка](media/mobility-policy-1.png)

***Командлет***

[Get-CsMobilityPolicy](/powershell/module/skype/get-csmobilitypolicy)

***Пример***

```powershell
 Get-CsMobilityPolicy
```

---

> **Сценарий 2.** Создание новой политики мобильности

   ![Создание политики мобильности](./media/mobility-policy-2.png)

***Командлет***

[New-CsMobilityPolicy](/powershell/module/skype/new-csmobilitypolicy)  

***Пример***

```powershell
 New-CsMobilityPolicy -Identity site:Redmond -EnableOutsideVoice $False
```

---

> **Сценарий 3.** Сведения о выбранной политике мобильности

   ![Получить политику мобильности](./media/mobility-policy-3.png)

***Командлет***

[Get-CsMobilityPolicy](/powershell/module/skype/get-csmobilitypolicy)

***Пример***

```powershell
 Get-CsMobilityPolicy -Identity "site:Redmond"
```

---

> **Сценарий 4.** Удаление выбранных политик мобильности

   ![Удаление политики мобильности](./media/mobility-policy-4.png)

***Командлет***

[Remove-CsMobilityPolicy](/powershell/module/skype/remove-csmobilitypolicy)

***Пример***

```powershell
 Remove-CsMobilityPolicy -Identity "site:Redmond"
```

---

> **Сценарий 5.** Обновление политики мобильности

   ![Обновление политики мобильности](./media/mobility-policy-5.png)

***Командлет***

[Set-CsMobilityPolicy](/powershell/module/skype/set-csmobilitypolicy)

***Пример***

```powershell
Set-CsMobilityPolicy -Identity "site:Redmond" -EnableOutsideVoice $False
```

---

## <a name="push-notification-configuration"></a>Конфигурация push-уведомлений

Служба push-уведомлений (Служба push-уведомлений Apple и Служба push-уведомлений Майкрософт) предоставляет способ отправки уведомлений о таких событиях, как новые мгновенные сообщения или новая голосовая почта на мобильные устройства, такие как iPhone и Windows Телефоны. Эти уведомления настроены на отправление, даже если Skype для бизнеса приложения на этих устройствах в настоящее время приостановлено или запущено в фоновом режиме.

Рассмотрим различные задачи, которые пользователь может выполнять в конфигурации **PUSH NOTIFICATION,** а также Skype для бизнеса эти задачи.

---

> **Сценарий 1.** Список всех политик мобильности

   ![Конфигурация push-уведомлений списка](./media/push-notification-config-1.png)

***Командлет***

[Get-CsPushNotificationConfiguration](/powershell/module/skype/get-cspushnotificationconfiguration)

***Пример***

```powershell
 Get-CsPushNotificationConfiguration
```

---

> **Сценарий 2.** Создание новой конфигурации push-уведомлений

   ![Создание конфигурации push-уведомлений](./media/push-notification-config-2.png)

***Командлет***

[New-CsPushNotificationConfiguration](/powershell/module/skype/new-cspushnotificationconfiguration)  

***Пример***

```powershell
 New-CsPushNotificationConfiguration -Identity "site:Redmond" -EnableApplePushNotificationService $True -EnableMicrosoftPushNotificationService -$True
```

---

> **Сценарий 3.** Сведения о выбранной конфигурации push-уведомлений

   ![Настройка push-уведомлений](./media/push-notification-config-3.png)

***Командлет***

[Get-CsPushNotificationConfiguration](/powershell/module/skype/get-cspushnotificationconfiguration)

***Пример***

```powershell
 Get-CsPushNotificationConfiguration -Identity "site:Redmond"
```

---

> **Сценарий 4.** Удаление выбранных конфигураций push-уведомлений

   ![Удаление конфигурации push-уведомлений](./media/push-notification-config-4.png)

***Командлет***

[Remove-CsPushNotificationConfiguration](/powershell/module/skype/remove-cspushnotificationconfiguration)

***Пример***

```powershell
 Remove-CsPushNotificationConfiguration -Identity "site:Redmond"
```

---

> **Сценарий 5.** Обновление конфигурации push-уведомлений

   ![Обновление конфигурации push-уведомлений](./media/push-notification-config-5.png)

***Командлет***

[Set-CsPushNotificationConfiguration](/powershell/module/skype/set-cspushnotificationconfiguration)

***Пример***

```powershell
 Set-CsPushNotificationConfiguration -Identity "site:Redmond" -EnableApplePushNotificationService $False
```

---
