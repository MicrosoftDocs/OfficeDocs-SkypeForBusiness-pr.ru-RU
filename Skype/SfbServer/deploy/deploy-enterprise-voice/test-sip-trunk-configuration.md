---
title: 'Skype для бизнеса Server: Тестовые параметры конфигурации магистрали SIP'
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
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
ms.openlocfilehash: dd79e60b81bb5e9f0edbd93a9ddda96edfdee218
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/05/2022
ms.locfileid: "62396031"
---
# <a name="skype-for-business-server-test-sip-trunk-configuration-settings"></a>Skype для бизнеса Server: Тестовые параметры конфигурации магистрали SIP
 
**Сводка:** Узнайте, как проверить параметры конфигурации магистрали SIP с помощью Skype для бизнеса Server управленческой оболочки.
  
Параметры конфигурации магистрали SIP определяют связь и возможности между сервером-посредником и шлюзом открытой телефонной сети (PSTN), шлюзом IP-Public Branch eXchange (PBX) или диспетчером пограничной связи сеанса (SBC) у поставщика услуг. Эти настройки можно использовать, чтобы определить следующие параметры:
  
- Следует ли включить обход мультимедиа в магистральных магистрали
    
- Условия, при которых отправляются пакеты протокола управления транспортом в режиме реального времени (RTCP).
    
- Требуется ли шифрование безопасного протокола транспорта в режиме реального времени (SRTP) для каждого магистрали
    
При установке Skype для бизнеса Server для вас создается глобальная коллекция параметров конфигурации магистрали SIP. Кроме того, администраторы могут создавать настраиваемые коллекции параметров в области сайта или в области службы (только для службы шлюзов PSTN). Администраторы также могут использовать Test-CsTrunkConfiguration, чтобы убедиться, что магистраль может преобразовать число, набраное пользователем, в число, с помощью которое шлюз может обрабатывать.
  
Параметры конфигурации магистрали можно проверить только с помощью Windows PowerShell и [комлета Test-CsTrunkConfiguration](/powershell/module/skype/test-cstrunkconfiguration). Этот комлет можно запускать из Skype для бизнеса Server или удаленного сеанса Skype для бизнеса Server.
  
### <a name="to-test-sip-trunk-configuration-settings"></a>Тестирование параметров конфигурации магистрали SIP

- Эта команда проверяет, что параметры конфигурации магистрали для сайта Redmond могут правильно преобразовать набраный номер 4255551212.
    
  ```powershell
  $trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
  Test-CsTrunkConfiguration -DialedNumber 4255551212 -TrunkConfiguration $trunk
  ```
