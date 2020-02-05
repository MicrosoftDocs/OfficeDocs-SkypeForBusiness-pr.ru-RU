---
title: Проверка параметров конфигурации магистральной магистрали SIP в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 'Сводка: Проверка параметров конфигурации магистральной магистрали SIP с помощью командной консоли Skype для бизнеса Server.'
ms.openlocfilehash: a85af538f5729310c75e57313b049dcb14d09542
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41766912"
---
# <a name="test-sip-trunk-configuration-settings-in-skype-for-business-server"></a>Проверка параметров конфигурации магистральной магистрали SIP в Skype для бизнеса Server
 
**Сводка:** Сведения о том, как проверить параметры конфигурации магистральной магистрали SIP с помощью командной консоли Skype для бизнеса Server.
  
Параметры конфигурации магистрали SIP определяют отношения и и возможности между сервером-посредником и шлюзом ТСОП, IP-УАТС или пограничным контроллером сеансов (SBC) у поставщика услуг. Эти параметры, в частности, определяют следующее:
  
- следует включать ли обход сервера-посредника на магистралях;
    
- условия, при которых отправляются пакеты протокола RTCP;
    
- требуется ли использовать шифрование протокола SRTP для каждой магистрали.
    
При установке Skype для бизнеса Server для вас создается глобальная коллекция параметров конфигурации магистральной магистрали SIP. Кроме того, администраторы могут создавать пользовательские коллекции настроек на уровне сайта или службы (только для службы шлюза ТСОП). Администраторы также могут использовать командлет Test-CsTrunkConfiguration, чтобы проверить, может ли магистраль преобразовывать номер, набираемый пользователем, в номер, который может обрабатываться шлюзом.
  
Trunk configuration settings can only be tested by using Windows PowerShell and the [Test-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/test-cstrunkconfiguration?view=skype-ps) cmdlet. Этот командлет можно выполнить либо из командной консоли Skype для бизнеса Server, либо из удаленного сеанса командной консоли Skype для бизнеса Server.
  
### <a name="to-test-sip-trunk-configuration-settings"></a>Тестирование параметров конфигурации магистрали SIP

- Эта команда проверяет, могут ли параметры конфигурации магистрали для сайта Redmond правильно преобразовать набранный номер 4255551212.
    
  ```powershell
  $trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
  Test-CsTrunkConfiguration -DialedNumber 4255551212 -TrunkConfiguration $trunk
  ```


