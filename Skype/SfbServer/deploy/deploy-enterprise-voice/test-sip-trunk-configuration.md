---
title: Тестирование параметров конфигурации магистрали SIP в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c8712308-0e2d-4e39-8f90-d1a250487a94
description: Сводка. Узнайте, как проверить параметры конфигурации магистрали SIP с помощью оболочки управления Skype для бизнес-серверов.
ms.openlocfilehash: 6f569c7e397e7902cb347e13b4077acb5a9b34fb
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103375"
---
# <a name="test-sip-trunk-configuration-settings-in-skype-for-business-server"></a>Тестирование параметров конфигурации магистрали SIP в Skype для бизнеса Server
 
**Сводка:** Узнайте, как проверить параметры конфигурации магистрали SIP с помощью оболочки управления серверами Skype для бизнеса.
  
Параметры конфигурации магистрали SIP определяют связь и возможности между сервером-посредником и шлюзом открытой телефонной сети (PSTN), шлюзом IP-Public Branch eXchange (PBX) или диспетчером пограничной связи сеанса (SBC) у поставщика услуг. Эти настройки можно использовать, чтобы определить следующие параметры:
  
- Следует ли включать обход сервера-посредника на магистралях.
    
- Условия, при которых отправляются пакеты протокола контроля транспорта в режиме реального времени (RTCP).
    
- Требуется ли шифрование безопасного транспортного протокола реального времени (SRTP) на каждом магистрали.
    
При установке Skype для бизнеса Server создается глобальная коллекция параметров конфигурации магистрали SIP. Кроме того, администраторы могут создать настраиваемые коллекции параметров в области узла или службы (только для службы шлюза ТСОП). Администраторы также могут использовать Test-CsTrunkConfiguration, чтобы убедиться, что магистраль может преобразовать число, набраное пользователем, на номер, который может обрабатываться шлюзом.
  
Параметры конфигурации магистрали можно проверить только с помощью Windows PowerShell и [комлета Test-CsTrunkConfiguration.](/powershell/module/skype/test-cstrunkconfiguration?view=skype-ps) Этот комдлет можно выполнить либо из оболочки управления Skype для бизнес-серверов, либо из удаленного сеанса оболочки управления Skype для бизнес-серверов.
  
### <a name="to-test-sip-trunk-configuration-settings"></a>Тестирование параметров конфигурации магистрали SIP

- Эта команда проверяет, что параметры конфигурации магистрали сайта Redmond могут правильно преобразовать набраный номер 4255551212.
    
  ```powershell
  $trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
  Test-CsTrunkConfiguration -DialedNumber 4255551212 -TrunkConfiguration $trunk
  ```