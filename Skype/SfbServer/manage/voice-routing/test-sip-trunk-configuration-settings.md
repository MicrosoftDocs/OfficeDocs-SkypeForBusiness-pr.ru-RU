---
title: Тестирование параметров конфигурации магистрали SIP в Скайп для Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Параметров конфигурации магистрали SIP определите связь и возможности между сервером-посредником и шлюза телефонной сети (общего пользования PSTN), общедоступный IP-адрес учреждения (УАТС) или пограничный контроллер сеансов (SBC) у поставщика услуг. '
ms.openlocfilehash: d49b76c10505a009e6eed64d60632b52b08f3866
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2018
ms.locfileid: "27222704"
---
# <a name="test-sip-trunk-configuration-settings-in-skype-for-business-server"></a>Тестирование параметров конфигурации магистрали SIP в Скайп для Business Server

Параметров конфигурации магистрали SIP определите связь и возможности между сервером-посредником и шлюза телефонной сети (общего пользования PSTN), общедоступный IP-адрес учреждения (УАТС) или пограничный контроллер сеансов (SBC) у поставщика услуг. Эти параметры, в частности, определяют следующее:

- следует включать ли обход сервера-посредника на магистралях;
- Условия, при которых отправляются пакеты протокола RTCP управления транспорта реального времени.
- На каждой линии связи требуется ли шифрование по протоколу (SRTP).

При установке Скайп для Business Server глобальной коллекции параметров конфигурации магистрали SIP будет создан автоматически. Кроме того, администраторы могут создавать пользовательские коллекции настроек на уровне сайта или службы (только для службы шлюза ТСОП). Администраторы могут также использовать командлет [Test-CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsTrunkConfiguration) чтобы убедиться, что магистрали можно преобразовать номер, набираемый пользователем номер, могут быть обработаны шлюза.

Trunk configuration settings can only be tested by using Windows PowerShell and the Test-CsTrunkConfiguration cmdlet. Этот командлет можно запустить из Скайп для консоли Business Server или из удаленного сеанса Windows PowerShell. 

**Тестирование параметров конфигурации магистрали SIP**

Эта команда проверяет, могут ли параметры конфигурации магистрали для сайта Redmond правильно преобразовать набранный номер 4255551212.

```
$trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
Test-CsTrunkConfiguration -DialedNumber 4255551212 -TrunkConfiguration $trunk
```