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
description: Сводка. Сведения о проверке параметров конфигурации магистрали SIP с помощью оболочки управления Skype для бизнеса Server.
ms.openlocfilehash: 8b3a98d54fd0d2dc8bb69e553e0c0a3a7b98b1ca
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830639"
---
# <a name="test-sip-trunk-configuration-settings-in-skype-for-business-server"></a>Тестирование параметров конфигурации магистрали SIP в Skype для бизнеса Server
 
**Сводка:** Узнайте, как тестировать параметры конфигурации магистрали SIP с помощью оболочки управления Skype для бизнеса Server.
  
Параметры конфигурации магистрали SIP определяют отношения и возможности между сервером-посредником и шлюзом телефонной сети общего параметров (PSTN), УАЦ IP-Public Branch eXchange (PBX) или пограничным контроллером сеансов (SBC) у поставщика услуг. Эти настройки можно использовать, чтобы определить следующие параметры:
  
- Следует ли включать обход сервера-посредника на магистралях.
    
- Условия, при которых отправляются пакеты протокола RTCP.
    
- Требуется ли шифрование SRTP для каждой магистрали.
    
При установке Skype для бизнеса Server создается глобальная коллекция параметров конфигурации магистрали SIP. Кроме того, администраторы могут создать настраиваемые коллекции параметров в области узла или службы (только для службы шлюза ТСОП). Администраторы также могут использовать Test-CsTrunkConfiguration, чтобы убедиться, что магистраль может преобразовать номер, набираемый пользователем, в номер, который может обрабатываться шлюзом.
  
Параметры конфигурации магистрали можно проверить только с помощью Windows PowerShell и с помощью Windows PowerShell [Test-CsTrunkConfiguration.](https://docs.microsoft.com/powershell/module/skype/test-cstrunkconfiguration?view=skype-ps) Этот cmdlet можно запустить либо из оболочки управления Skype для бизнеса Server, либо из удаленного сеанса в skype для бизнеса Server Management Shell.
  
### <a name="to-test-sip-trunk-configuration-settings"></a>Тестирование параметров конфигурации магистрали SIP

- Эта команда проверяет, могут ли параметры конфигурации магистрали для сайта Redmond правильно преобразовать набраный номер 4255551212.
    
  ```powershell
  $trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
  Test-CsTrunkConfiguration -DialedNumber 4255551212 -TrunkConfiguration $trunk
  ```


