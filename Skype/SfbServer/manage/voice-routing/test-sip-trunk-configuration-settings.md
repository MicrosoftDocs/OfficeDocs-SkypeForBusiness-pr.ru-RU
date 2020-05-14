---
title: Проверка параметров конфигурации магистрали SIP в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'Параметры конфигурации магистрали SIP определяют возможности и отношения между сервером-посредником и шлюзом PSTN, IP-PBX и пограничным контроллером сеансов у поставщика услуг. '
ms.openlocfilehash: bed342de3f602499f16b9f27ee0726f10d2c867e
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/13/2020
ms.locfileid: "42048192"
---
# <a name="test-sip-trunk-configuration-settings-in-skype-for-business-server"></a>Проверка параметров конфигурации магистрали SIP в Skype для бизнеса Server

Параметры конфигурации линий связи SIP определяют возможности и связи между сервером-посредником и шлюзом телефонной сети общего пользования (ТСОП), IP-PBX или пограничным контроллером сеансов (SBC) на стороне поставщика услуг. Эти параметры позволяют определить:

- Следует ли включить обход медиаданных на линиях связи.
- Условия, при которых передаются пакеты по протоколу RTCP.
- Требуется ли шифрование по протоколу SRTP на каждой магистрали.

При установке Skype для бизнеса Server создается глобальная коллекция параметров конфигурации магистрали SIP. Кроме того, администраторы могут создать настраиваемые коллекции параметров в области узла или службы (только для службы шлюза ТСОП). Администраторы также могут использовать командлет [Test-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/Test-CsTrunkConfiguration) , чтобы проверить, может ли магистраль преобразовать номер, набранный пользователем, на номер, который может обрабатываться шлюзом.

Параметры конфигурации магистрали можно тестировать только с помощью Windows PowerShell и командлета Test-CsTrunkConfiguration. Этот командлет можно запустить либо из командной консоли Skype для бизнеса Server, либо из удаленного сеанса Windows PowerShell. 

**Тестирование параметров конфигурации магистрали SIP**

Эта команда проверяет, могут ли параметры конфигурации магистрали для сайта Redmond правильно преобразовать набранный номер 4255551212.

```PowerShell
$trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
Test-CsTrunkConfiguration -DialedNumber 4255551212 -TrunkConfiguration $trunk
```
