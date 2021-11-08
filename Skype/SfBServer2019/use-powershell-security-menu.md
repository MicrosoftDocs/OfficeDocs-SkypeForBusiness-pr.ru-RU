---
title: Использование PowerShell для задач в меню безопасности
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
description: Сводка. Skype для бизнеса Server панели управления к сопоставлению cmdlet для меню Безопасности.
ms.openlocfilehash: 6e726b13b9428b213011126abf5ac0869e6cfbf8
ms.sourcegitcommit: eba9fc680233e9e03773a2942f22afe6247eec41
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/08/2021
ms.locfileid: "60824996"
---
# <a name="security"></a>Безопасность

В этой статье описывается, как аналогичные результаты элемента меню **безопасности** в устаревшей панели управления могут быть достигнуты с помощью cmdlets.

В этой статье описаны следующие подмены:

- [Безопасность](#security)
  - [Регистратор](#registrar)
  - [Веб-служба](#web-service)
  - [Политика ПИН-кодов](#pin-policy)

## <a name="registrar"></a>Регистратор

**Подмена REGISTRAR** позволяет администраторам управлять прокси-серверами с помощью параметров конфигурации прокси-сервера. Эти параметры, которые могут применяться как в глобальном масштабе, так и в области служб (хотя и только для служб Edge Server и Registrar), позволяют контролировать такие параметры, как протоколы проверки подлинности, которые могут использоваться конечными точками клиента, и будет ли сжатие использоваться для входящих и исходяющих подключений прокси-серверов.

Рассмотрим различные задачи, которые пользователь может выполнять в **REGISTRAR,** и Skype для бизнеса этих задач.

---

> **Сценарий 1.** Список всех конфигураций прокси

   ![Конфигурация прокси-сервера списка](./media/proxy-configurations-1.png)

***Командлет***

[Get-CsProxyConfiguration](/powershell/module/skype/get-csproxyconfiguration)

***Пример***

```powershell
 Get-CsProxyConfiguration
```

---

> **Сценарий 2.** Создание новой конфигурации прокси

   ![Создание конфигурации прокси](./media/proxy-configurations-2.png)

***Командлет***

[New-CsProxyConfiguration](/powershell/module/skype/new-csproxyconfiguration)  

***Пример***

```powershell
 New-CsProxyConfiguration -Identity "service:EdgeServer:atl-edge-001.litwareinc.com" -RequestServerCompression $True -MaxClientMessageBodySizeKb 256
```

---

> **Сценарий 3.** Сведения о выбранной конфигурации прокси

   ![Настройка прокси](./media/proxy-configurations-3.png)

***Командлет***

[Get-CsProxyConfiguration](/powershell/module/skype/get-csproxyconfiguration)

***Пример***

```powershell
 Get-CsProxyConfiguration -Identity "service:EdgeServer:atl-cs-001.litwareinc.com"
```

---

> **Сценарий 4.** Удаление выбранных конфигураций прокси

   ![Удаление конфигурации прокси](./media/proxy-configurations-4.png)

***Командлет***

[Remove-CsProxyConfiguration](/powershell/module/skype/remove-csproxyconfiguration)

***Пример***

```powershell
 Remove-CsProxyConfiguration -Identity service:EdgeServer:atl-edge-011.litwareinc.com
```

---

> **Сценарий 5.** Обновление конфигурации прокси

   ![Обновление конфигурации прокси](./media/proxy-configurations-5.png)

***Командлет***

[Set-CsProxyConfiguration](/powershell/module/skype/set-csproxyconfiguration)

***Пример***

```powershell
 Set-CsProxyConfiguration -Identity service:EdgeServer:atl-edge-001.litwareinc.com -AcceptServerCompression $True
```

---

## <a name="web-service"></a>Веб-служба

Элемент **подмены** ВЕБ-службы в **области Безопасности** позволяет администраторам управлять настройками веб-служб по всей организации; это включает управление расширением групп, настройками сертификатов и разрешенными методами проверки подлинности. Так как администраторы могут настраивать различные параметры на глобальном уровне, на сайте и в области служб (хотя и только для службы веб-служб), можно настроить возможности веб-служб для разных пользователей и разных местоположений.

Рассмотрим различные задачи, которые пользователь может выполнять в ВЕБ-службе, и Skype для бизнеса эти задачи на карте.

---
> **Сценарий 1.** Список всех конфигураций веб-службы

   ![Конфигурация веб-службы списка](./media/web-service-1.png)

***Командлет***

[Get-CsWebServiceConfiguration](/powershell/module/skype/get-cswebserviceconfiguration)

***Пример***

```powershell
 Get-CsWebServiceConfiguration
```

---

> **Сценарий 2.** Создание новой конфигурации веб-службы

   ![Новая конфигурация веб-службы](./media/web-service-2.png)

***Командлет***

[New-CsWebServiceConfiguration](/powershell/module/skype/new-cswebserviceconfiguration)  

***Пример***

```powershell
 New-CsWebServiceConfiguration -Identity site:Redmond -EnableGroupExpansion $False -UseCertificateAuth $True
```

---

> **Сценарий 3.** Сведения о выбранной конфигурации веб-службы

   ![Настройка веб-службы](./media/web-service-3.png)

***Командлет***

[Get-CsWebServiceConfiguration](/powershell/module/skype/get-cswebserviceconfiguration)

***Пример***

```powershell
 Get-CsWebServiceConfiguration -Identity site:Redmond
```

---

> **Сценарий 4.** Удаление выбранных конфигураций веб-служб

   ![Удаление конфигурации веб-службы](./media/web-service-4.png)

***Командлет***

[Remove-CsWebServiceConfiguration](/powershell/module/skype/remove-cswebserviceconfiguration)

***Пример***

```powershell
 Remove-CsWebServiceConfiguration -Identity site:Redmond
```

---

> **Сценарий 5.** Обновление конфигурации веб-службы

   ![Обновление конфигурации веб-службы](./media/Web-service-5.png)

***Командлет***

[Set-CsWebServiceConfiguration](/powershell/module/skype/set-cswebserviceconfiguration)

***Пример***

```powershell
 Set-CsWebServiceConfiguration -Identity site:Redmond -EnableGroupExpansion $True
```

---

## <a name="pin-policy"></a>Политика ПИН-кодов

Администраторы могут использовать **PIN-политику** для управления свойствами проверки подлинности ПИН-кода; например, можно указать минимальную длину ПИН-кода и определить, разрешит ли один пин-код с использованием "общих шаблонов", таких как последовательные цифры (например, ПИН-код типа 123456)

Рассмотрим различные задачи, которые пользователь может выполнять в PIN-политике, а также Skype для бизнеса эти задачи.

---

> **Сценарий 1.** Список всех политик ПИН-кода

   ![Политика пин-кода списка](./media/pin-policy-1.png)

***Командлет***

[Get-CsPinPolicy](/powershell/module/skype/get-cspinpolicy)

***Пример***

```powershell
 Get-CsPinPolicy
```

---

> **Сценарий 2.** Создание новой политики ПИН-кода

   ![Создание политики пин-кода](./media/pin-policy-2.png)

***Командлет***

[New-CsPinPolicy](/powershell/module/skype/new-cspinpolicy)  

***Пример***

```powershell
 New-CsPinPolicy -Identity "site:Redmond" -MinPasswordLength 10
```

---

> **Сценарий 3.** Сведения об выбранной политике ПИН-кода

   ![Получить политику PIN-кода](./media/pin-policy-3.png)

***Командлет***

[Get-CsPinPolicy](/powershell/module/skype/get-cspinpolicy)

***Пример***

```powershell
 Get-CsPinPolicy -Identity "site:Redmond"
```

---

> **Сценарий 4.** Удаление выбранных политик ПИН-кода

   ![Удаление политики PIN-кода](./media/pin-policy-4.png)

***Командлет***

[Remove-CsPinPolicy](/powershell/module/skype/remove-cspinpolicy)

***Пример***

```powershell
 Remove-CsPinPolicy -Identity RedmondUsersPinPolicy
```

---

> **Сценарий 5.** Обновление политики PIN-кода

   ![Политика обновления ПИН-кода](./media/pin-policy-5.png)

***Командлет***

[Set-CsPinPolicy](/powershell/module/skype/set-cspinpolicy)

***Пример***

```powershell
 Set-CsPinPolicy -Identity site:Redmond -MinPasswordLength 10
```

---
