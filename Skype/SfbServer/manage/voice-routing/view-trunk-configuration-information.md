---
title: Просмотр сведений о настройке магистрали в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Параметры конфигурации магистральной магистрали SIP определяют связь и возможности между сервером-посредником и шлюзом коммутируемой телефонной сети (PSTN), Интернет-ПРОТОКОЛом (УАТС) или контроллером границ сеанса (SBC) в поставщике услуг.
ms.openlocfilehash: dd8bd94bb8831fc3e406bed46015b2d955a2359c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274872"
---
# <a name="view-trunk-configuration-information-in-skype-for-business-server"></a>Просмотр сведений о настройке магистрали в Skype для бизнеса Server

Параметры конфигурации магистральной магистрали SIP определяют связь и возможности между сервером-посредником и шлюзом коммутируемой телефонной сети (PSTN), Интернет-ПРОТОКОЛом (УАТС) или контроллером границ сеанса (SBC) в поставщике услуг.

- следует включать ли обход сервера-посредника на магистралях;
- Условия, при которых отправляются пакеты протокола управления транспортом в реальном времени (РТКП).
- Требуется ли шифрование на всех магистральах в режиме реального времени (SRTP).

При установке Skype для бизнеса Server для вас создается глобальная коллекция параметров конфигурации магистральной магистрали SIP. Кроме того, администраторы могут создавать пользовательские коллекции настроек на уровне сайта или службы (только для службы шлюза ТСОП).

**Просмотр сведений о настройке магистральной магистрали SIP с помощью панели управления Skype для бизнеса Server**

1. На панели управления Skype для бизнеса Server нажмите кнопку **Маршрутизация голоса**и выберите пункт **Настройка магистрали**.
2. На вкладке **Настройка магистрали** вы увидите список всех коллекций параметров конфигурации канала. для каждой коллекции вы увидите значения свойств пропускаемых **имен**, **областей**, **состояний**и **мультимедиа** , а также количество **использованных PSTN**, правил для **номерных номеров**и вызываемых **правил номеров** , связанных с коллекцией. Чтобы просмотреть дополнительные сведения о коллекции параметров конфигурации магистрали, щелкните нужную коллекцию, нажмите кнопку **изменить**, а затем выберите команду **Показать подробности**. Обратите внимание на то, что вы можете просматривать подробные сведения только для одной коллекции параметров конфигурации канала за один раз.

## <a name="viewing-sip-trunk-configuration-information-by-using-windows-powershell-cmdlets"></a>Просмотр сведений о настройке магистральной магистрали SIP с помощью командлетов Windows PowerShell

Параметры конфигурации магистральной магистрали SIP можно просмотреть с помощью Skype для бизнеса Server PowerShell и командлета Get-CsTrunkConfiguration. Этот командлет можно выполнить либо из командной консоли Skype для бизнеса Server, либо из удаленного сеанса Windows PowerShell. Дополнительные сведения об использовании удаленной оболочки Windows PowerShell для подключения к серверу Skype для бизнеса можно найти в статье "Краткое руководство по работе с Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" в http://go.microsoft.com/fwlink/p/?linkId=255876блоге Lync Server Windows PowerShell. ЗАМЕНА ИЛИ УДАЛЕНИЕ ЭТОЙ ССЫЛКИ.


**Просмотр сведений о настройке магистральной магистрали SIP**

Чтобы просмотреть сведения о всех параметрах настройки магистральной магистрали SIP, введите в командной консоли Skype для Business Server указанную ниже команду и нажмите клавишу ВВОД.

`Get-CsTrunkConfiguration`

Команда возвращает примерно следующую информацию:

```
Identity                                  : Global
OutboundTranslationRulesList              : {}
SipResponseCodeTranslationRulesList       : {}
OutboundCallingNumberTranslationRulesList : {}
PstnUsages                                : {}
Description                               :
ConcentratedTopology                      : True
EnableBypass                              : False
EnableMobileTrunkSupport                  : False
EnableReferSupport                        : True
EnableSessionTimer                        : False
EnableSignalBoost                         : False
MaxEarlyDialogs                           : 20
RemovePlusFromUri                         : False
RTCPActiveCalls                           : True
RTCPCallsOnHold                           : True
SRTPMode                                  : Required
EnablePIDFLOSupport                       : False
EnableRTPLatching                         : False
EnableOnlineVoice                         : False
ForwardCallHistory                        : False
Enable3pccRefer                           : False
ForwardPAI                                : False
EnableFastFailoverTimer                   : True
```
Дополнительные сведения можно найти в разделе справки по командлету [Get-CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsTrunkConfiguration) .



