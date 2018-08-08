---
title: Тестирование параметров конфигурации магистрали SIP в Скайп для Business Server
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c8712308-0e2d-4e39-8f90-d1a250487a94
description: 'Сводка: Узнайте, как для проверки параметров конфигурации магистрали SIP с помощью Скайп для консоли Business Server.'
ms.openlocfilehash: ea0874eabacfb814c5cc668654c56c86c788beff
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2018
ms.locfileid: "20984073"
---
# <a name="test-sip-trunk-configuration-settings-in-skype-for-business-server"></a>Тестирование параметров конфигурации магистрали SIP в Скайп для Business Server
 
**Сводка:** Узнайте, как для проверки параметров конфигурации магистрали SIP с помощью Скайп для консоли Business Server.
  
Параметры конфигурации магистрали SIP определяют отношения и и возможности между сервером-посредником и шлюзом ТСОП, IP-УАТС или пограничным контроллером сеансов (SBC) у поставщика услуг. Эти параметры, в частности, определяют следующее:
  
- следует включать ли обход сервера-посредника на магистралях;
    
- условия, при которых отправляются пакеты протокола RTCP;
    
- требуется ли использовать шифрование протокола SRTP для каждой магистрали.
    
При установке Скайп для Business Server глобальной коллекции параметров конфигурации магистрали SIP будет создан автоматически. Кроме того, администраторы могут создавать пользовательские коллекции настроек на уровне сайта или службы (только для службы шлюза ТСОП). Администраторы также могут использовать командлет Test-CsTrunkConfiguration, чтобы проверить, может ли магистраль преобразовывать номер, набираемый пользователем, в номер, который может обрабатываться шлюзом.
  
Параметры конфигурации, можно проверить только с помощью Windows PowerShell и командлета [Test-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/test-cstrunkconfiguration?view=skype-ps) . Этот командлет можно запустить из Скайп для консоли Business Server или из удаленного сеанса Скайп для консоли Business Server.
  
### <a name="to-test-sip-trunk-configuration-settings"></a>Тестирование параметров конфигурации магистрали SIP

- Эта команда проверяет, могут ли параметры конфигурации магистрали для сайта Redmond правильно преобразовать набранный номер 4255551212.
    
  ```
  $trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
  Test-CsTrunkConfiguration -DialedNumber 4255551212 -TrunkConfiguration $trunk
  ```


