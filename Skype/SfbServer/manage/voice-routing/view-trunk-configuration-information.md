---
title: Просмотр сведений о конфигурации магистрали в Skype для бизнеса Server
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
description: 'Параметры конфигурации магистрали SIP определяют возможности и отношения между сервером-посредником и шлюзом PSTN, IP-PBX и пограничным контроллером сеансов у поставщика услуг.'
---

# <a name="view-trunk-configuration-information-in-skype-for-business-server"></a>Просмотр сведений о конфигурации магистрали в Skype для бизнеса Server

Параметры конфигурации магистрали SIP определяют возможности и отношения между сервером-посредником и шлюзом PSTN, IP-PBX и пограничным контроллером сеансов у поставщика услуг.

- Следует ли включать обход сервера-посредника на магистралях.
- Условия, при которых передаются пакеты по протоколу RTCP.
- Требуется ли шифрование по протоколу SRTP на каждой магистрали.

При установке Skype для бизнеса Server для вас создается глобальная коллекция параметров конфигурации магистрали SIP. Кроме того, администраторы могут создать настраиваемые коллекции параметров в области узла или службы (только для службы шлюза ТСОП).

**Просмотр сведений о конфигурации магистрали SIP с помощью Skype для бизнеса Server панели управления**

1. В панели Skype для бизнеса Server нажмите **голосовую маршрутику** и нажмите кнопку **Конфигурация магистрали**.
2. На **вкладке Конфигурация** магистрали вы увидите список всех коллекций параметров конфигурации магистрали; Для каждой коллекции будут видеться значения свойств обхода **имен,** областей **, состояния** и мультимедиа, а также количество использования **PSTN****, правил** номеров звонков и правил номеров вызовов,  связанных с коллекцией. Чтобы узнать дополнительные сведения о коллекции параметров конфигурации магистрали, щелкните интересуемую коллекцию, нажмите кнопку **Изменить** и нажмите **кнопку Показать сведения**. Обратите внимание, что подробные сведения можно просматривать только для одной коллекции параметров конфигурации магистрали одновременно.

## <a name="viewing-sip-trunk-configuration-information-by-using-windows-powershell-cmdlets"></a>Просмотр сведений о конфигурации магистрали SIP с помощью Windows PowerShell-кодов

Параметры конфигурации магистрали SIP можно просмотреть с помощью Skype для бизнеса Server PowerShell и Get-CsTrunkConfiguration. Этот комлет можно запускать из Skype для бизнеса Server или удаленного сеанса Windows PowerShell. Подробные сведения об использовании удаленных Windows PowerShell для подключения к Skype для бизнеса Server см. в статье блога Lync Server Windows PowerShell "Быстрый запуск: управление Microsoft Lync Server 2010 с помощью удаленной powerShell"https://go.microsoft.com/fwlink/p/?linkId=255876. ЗАМЕНИТЕ ИЛИ УДАЛИТЕ ЭТУ ССЫЛКУ.


**Просмотр сведений о конфигурации магистрали SIP**

Чтобы просмотреть сведения обо всех параметрах конфигурации магистрали SIP, введите следующую команду в командной Skype для бизнеса Server, а затем нажмите кнопку ENTER:

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
Дополнительные сведения см. в разделе Справка для [cmdlet Get-CsTrunkConfiguration](/powershell/module/skype/Get-CsTrunkConfiguration) .