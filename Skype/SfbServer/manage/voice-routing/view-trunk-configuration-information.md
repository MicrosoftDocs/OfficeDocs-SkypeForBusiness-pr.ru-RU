---
title: Просмотр сведений о конфигурации магистрали в Skype для бизнеса Server
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
description: Параметры конфигурации магистрали SIP определяют возможности и отношения между сервером-посредником и шлюзом PSTN, IP-PBX и пограничным контроллером сеансов у поставщика услуг.
ms.openlocfilehash: c473c3fc19138ac91b44dff8552555418d36533f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826169"
---
# <a name="view-trunk-configuration-information-in-skype-for-business-server"></a>Просмотр сведений о конфигурации магистрали в Skype для бизнеса Server

Параметры конфигурации магистрали SIP определяют возможности и отношения между сервером-посредником и шлюзом PSTN, IP-PBX и пограничным контроллером сеансов у поставщика услуг.

- Следует ли включать обход сервера-посредника на магистралях.
- Условия, при которых передаются пакеты по протоколу RTCP.
- Требуется ли шифрование по протоколу SRTP на каждой магистрали.

При установке Skype для бизнеса Server создается глобальная коллекция параметров конфигурации магистрали SIP. Кроме того, администраторы могут создать настраиваемые коллекции параметров в области узла или службы (только для службы шлюза ТСОП).

**Просмотр сведений о конфигурации магистрали SIP с помощью панели управления Skype для бизнеса Server**

1. В панели управления Skype для бизнеса Server щелкните "Маршрутация голосовой почты" **и** выберите **"Конфигурация магистрали".**
2. На **вкладке "Конфигурация** магистрали" вы увидите список всех коллекций параметров конфигурации магистрали; для каждой коллекции вы увидите значения свойств **Name,** **Scope,** **State** и **Media Bypass,** а также количество вариантов  использования **PSTN,** правил номеров звонков и правил вызываемого номера, связанных с коллекцией. Чтобы увидеть дополнительные сведения о коллекции параметров конфигурации магистрали, щелкните коллекцию параметров, нажмите кнопку "Изменить" **и** выберите **"Показать подробности".** Обратите внимание, что вы можете просматривать подробные сведения только для одной коллекции параметров конфигурации магистрали одновременно.

## <a name="viewing-sip-trunk-configuration-information-by-using-windows-powershell-cmdlets"></a>Просмотр сведений о конфигурации магистрали SIP с помощью Windows PowerShell управления

Параметры конфигурации магистрали SIP можно просмотреть с помощью Skype для бизнеса Server PowerShell и Get-CsTrunkConfiguration управления. Этот cmdlet можно запустить либо из оболочки управления Skype для бизнеса Server, либо из удаленного сеанса Windows PowerShell. Подробные сведения об использовании удаленного Windows PowerShell для подключения к Skype для бизнеса Server см. в статье блога Lync Server Windows PowerShell "Краткое руководство: управление Microsoft Lync Server 2010 с помощью удаленной powerShell" по этой https://go.microsoft.com/fwlink/p/?linkId=255876 статье. ЗАМЕНИТЕ ИЛИ УДАЛИТЕ ЭТУ ССЫЛКУ.


**Просмотр сведений о конфигурации магистрали SIP**

Чтобы просмотреть сведения обо всех параметрах конфигурации магистрали SIP, введите следующую команду в командной оболочке Skype для бизнеса Server и нажмите ввод:

```powershell
Get-CsTrunkConfiguration
```

Это приведет к возврату приблизительно такой информации:

```console
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
Дополнительные сведения см. в разделе справки по [cmdlet Get-CsTrunkConfiguration.](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunkConfiguration)



