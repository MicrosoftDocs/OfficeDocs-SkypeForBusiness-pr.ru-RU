---
title: Skype для бизнеса Server - Тестовые параметры конфигурации магистрали SIP
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
description: 'Параметры конфигурации магистрали SIP определяют связь и возможности между шлюзом-посредником и шлюзом PST, PBX или SBC у поставщика услуг. '
---

# <a name="skype-for-business-server---test-sip-trunk-configuration-settings"></a>Skype для бизнеса Server - Тестовые параметры конфигурации магистрали SIP

Параметры конфигурации линий связи SIP определяют возможности и связи между сервером-посредником и шлюзом телефонной сети общего пользования (ТСОП), IP-PBX или пограничным контроллером сеансов (SBC) на стороне поставщика услуг. Эти параметры позволяют определить:

- Следует ли включить обход медиаданных на линиях связи.
- Условия, при которых передаются пакеты по протоколу RTCP.
- Требуется ли шифрование по протоколу SRTP на каждой магистрали.

При установке Skype для бизнеса Server для вас создается глобальная коллекция параметров конфигурации магистрали SIP. Кроме того, администраторы могут создать настраиваемые коллекции параметров в области узла или службы (только для службы шлюза ТСОП). Администраторы также могут использовать комлет [Test-CsTrunkConfiguration](/powershell/module/skype/Test-CsTrunkConfiguration) , чтобы убедиться, что магистраль может преобразовать число, набраное пользователем, на номер, который может обрабатываться шлюзом.

Параметры конфигурации магистрали можно проверить только с помощью Windows PowerShell и Test-CsTrunkConfiguration. Этот комлет можно запускать из Skype для бизнеса Server или удаленного сеанса Windows PowerShell. 

**Тестирование параметров конфигурации магистрали SIP**

Эта команда проверяет, что параметры конфигурации магистрали для сайта Redmond могут правильно преобразовать набраный номер 4255551212.

```PowerShell
$trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
Test-CsTrunkConfiguration -DialedNumber 4255551212 -TrunkConfiguration $trunk
```
