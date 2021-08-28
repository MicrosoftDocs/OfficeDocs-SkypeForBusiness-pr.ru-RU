---
title: 'Skype для бизнеса Server: Тестовые параметры конфигурации магистрали SIP'
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c8712308-0e2d-4e39-8f90-d1a250487a94
description: Сводка. Узнайте, как проверить параметры конфигурации магистрали SIP с помощью Skype для бизнеса Server управления.
ms.openlocfilehash: 08bcbc0548af42b7242047ce9c848f00f1af7096
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/26/2021
ms.locfileid: "58617005"
---
# <a name="skype-for-business-server-test-sip-trunk-configuration-settings"></a>Skype для бизнеса Server: Тестовые параметры конфигурации магистрали SIP
 
**Сводка:** Узнайте, как проверить параметры конфигурации магистрали SIP с помощью Skype для бизнеса Server управленческой оболочки.
  
Параметры конфигурации магистрали SIP определяют связь и возможности между сервером-посредником и шлюзом открытой телефонной сети (PSTN), шлюзом IP-Public Branch eXchange (PBX) или диспетчером пограничной связи сеанса (SBC) у поставщика услуг. Эти настройки можно использовать, чтобы определить следующие параметры:
  
- Следует ли включить обход мультимедиа в магистральных магистрали
    
- Условия, при которых отправляются пакеты протокола управления транспортом в режиме реального времени (RTCP).
    
- Требуется ли шифрование безопасного протокола транспорта в режиме реального времени (SRTP) для каждого магистрали
    
При установке Skype для бизнеса Server для вас создается глобальная коллекция параметров конфигурации магистрали SIP. Кроме того, администраторы могут создавать настраиваемые коллекции параметров в области сайта или в области службы (только для службы шлюзов PSTN). Администраторы также могут использовать Test-CsTrunkConfiguration, чтобы убедиться, что магистраль может преобразовать число, набраное пользователем, в число, с помощью которое шлюз может обрабатывать.
  
Параметры конфигурации магистрали можно проверить только с помощью Windows PowerShell и [комлета Test-CsTrunkConfiguration.](/powershell/module/skype/test-cstrunkconfiguration) Этот комлет можно запускать из Skype для бизнеса Server или удаленного сеанса Skype для бизнеса Server.
  
### <a name="to-test-sip-trunk-configuration-settings"></a>Тестирование параметров конфигурации магистрали SIP

- Эта команда проверяет, что параметры конфигурации магистрали для сайта Redmond могут правильно преобразовать набраный номер 4255551212.
    
  ```powershell
  $trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
  Test-CsTrunkConfiguration -DialedNumber 4255551212 -TrunkConfiguration $trunk
  ```
