---
title: Тестирование параметров конфигурации магистрали SIP в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'Параметры конфигурации магистрали SIP определяют возможности и отношения между сервером-посредником и шлюзом PSTN, IP-PBX и пограничным контроллером сеансов у поставщика услуг. '
ms.openlocfilehash: 87f5b8aa07a7545f30f1d0e8b81b33197ea704c1
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103025"
---
# <a name="test-sip-trunk-configuration-settings-in-skype-for-business-server"></a>Тестирование параметров конфигурации магистрали SIP в Skype для бизнеса Server

Параметры конфигурации линий связи SIP определяют возможности и связи между сервером-посредником и шлюзом телефонной сети общего пользования (ТСОП), IP-PBX или пограничным контроллером сеансов (SBC) на стороне поставщика услуг. Эти параметры позволяют определить:

- Следует ли включить обход медиаданных на линиях связи.
- Условия, при которых передаются пакеты по протоколу RTCP.
- Требуется ли шифрование по протоколу SRTP на каждой магистрали.

При установке Skype для бизнеса Server создается глобальная коллекция параметров конфигурации магистрали SIP. Кроме того, администраторы могут создать настраиваемые коллекции параметров в области узла или службы (только для службы шлюза ТСОП). Администраторы также могут использовать комлет [Test-CsTrunkConfiguration,](/powershell/module/skype/Test-CsTrunkConfiguration) чтобы убедиться, что магистраль может преобразовать число, набраное пользователем, на номер, который может обрабатываться шлюзом.

Параметры конфигурации магистрали можно проверить только с помощью Windows PowerShell и Test-CsTrunkConfiguration. Этот комлет можно выполнить либо из оболочки управления skype для бизнес-серверов, либо из удаленного сеанса Windows PowerShell. 

**Тестирование параметров конфигурации магистрали SIP**

Эта команда проверяет, что параметры конфигурации магистрали сайта Redmond могут правильно преобразовать набраный номер 4255551212.

```PowerShell
$trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
Test-CsTrunkConfiguration -DialedNumber 4255551212 -TrunkConfiguration $trunk
```