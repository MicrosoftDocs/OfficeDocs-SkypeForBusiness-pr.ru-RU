---
title: Просмотр сведений о конфигурации магистрали в Скайп для Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Параметров конфигурации магистрали SIP определите связь и возможности между сервером-посредником и шлюза телефонной сети (общего пользования PSTN), общедоступный IP-адрес учреждения (УАТС) или пограничный контроллер сеансов (SBC) у поставщика услуг.
ms.openlocfilehash: dab6a53d76bdc33ddd39117afd7f8b32a1c9c170
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33926088"
---
# <a name="view-trunk-configuration-information-in-skype-for-business-server"></a>Просмотр сведений о конфигурации магистрали в Скайп для Business Server

Параметров конфигурации магистрали SIP определите связь и возможности между сервером-посредником и шлюза телефонной сети (общего пользования PSTN), общедоступный IP-адрес учреждения (УАТС) или пограничный контроллер сеансов (SBC) у поставщика услуг.

- следует включать ли обход сервера-посредника на магистралях;
- Условия, при которых отправляются пакеты протокола RTCP управления транспорта реального времени.
- На каждой линии связи требуется ли шифрование по протоколу (SRTP).

При установке Скайп для Business Server глобальной коллекции параметров конфигурации магистрали SIP будет создан автоматически. Кроме того, администраторы могут создавать пользовательские коллекции настроек на уровне сайта или службы (только для службы шлюза ТСОП).

**Просмотр сведений о конфигурации магистрали SIP с помощью Скайп для панели управления Business Server**

1. В Скайп для панели управления Business Server щелкните **Маршрутизация голосовой связи**и затем щелкните **Настройка линии связи**.
2. На вкладке **Конфигурация магистрали** будет отображен список всех вашей коллекций параметров конфигурации магистрали; для каждого семейства сайтов вы увидите значения для свойства **Name**, **области действия**, **состояние**и **сервера-посредника** и числа **случаев использования PSTN**, **вызов правил номеров**и **именем правил номеров** связанный в коллекции. Чтобы просмотреть дополнительные сведения о коллекции параметров конфигурации магистральной линии связи, выберите коллекцию интересов, нажмите кнопку **Изменить**и нажмите кнопку **Показать подробности**. Обратите внимание на то, что можно просматривать подробные сведения только для одной коллекции параметров конфигурации магистрали за раз.

## <a name="viewing-sip-trunk-configuration-information-by-using-windows-powershell-cmdlets"></a>Просмотр сведений о конфигурации магистрали SIP с помощью командлетов Windows PowerShell

SIP-конфигурация магистрали, параметры можно просматривать с помощью Скайп for Business Server PowerShell и командлета Get-CsTrunkConfiguration. Этот командлет можно выполнять с Скайп для консоли Business Server или из удаленного сеанса Windows PowerShell. Дополнительные сведения об использовании удаленной оболочки Windows PowerShell для подключения к Скайп для Business Server содержатся статьи блога Lync Server Windows PowerShell «Быстрый запуск: управление Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell» в http://go.microsoft.com/fwlink/p/?linkId=255876. ЗАМЕНА ИЛИ УДАЛЕНИЕ ЭТОЙ ССЫЛКИ.


**Для просмотра сведений о конфигурации магистрали SIP**

Чтобы просмотреть сведения о все параметры конфигурации магистрали SIP, введите следующую команду в Скайп для консоли Business Server и нажмите клавишу ВВОД:

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
Для получения дополнительных сведений см раздел справки для командлета [Get-CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsTrunkConfiguration) .



