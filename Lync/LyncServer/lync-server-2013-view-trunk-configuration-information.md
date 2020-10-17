---
title: 'Lync Server 2013: Просмотр сведений о конфигурации магистрали'
description: 'Lync Server 2013: Просмотр сведений о конфигурации магистрали.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View trunk configuration information
ms:assetid: ebe10e14-08c2-4797-9254-9ed89516d5cd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721927(v=OCS.15)
ms:contentKeyID: 49733862
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1b4e1d3063d65f8c27ad231f063249748046f759
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565435"
---
# <a name="view-trunk-configuration-information-in-lync-server-2013"></a>Просмотр сведений о конфигурации магистрали в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-02-22_

Параметры конфигурации линий связи SIP определяют возможности и связи между сервером-посредником и шлюзом телефонной сети общего пользования (ТСОП), IP-PBX или пограничным контроллером сеансов (SBC) на стороне поставщика услуг. Эти параметры позволяют определить:

  - Следует ли включить обход медиаданных на линиях связи.

  - Условия, при которых передаются пакеты по протоколу RTCP.

  - Требуется ли шифрование по протоколу SRTP на каждой магистрали.

При установке Microsoft Lync Server 2013 создается глобальная коллекция параметров конфигурации магистрали SIP. Кроме того, администраторы могут создать настраиваемые коллекции параметров в области узла или службы (только для службы шлюза ТСОП).

<div>

## <a name="to-view-sip-trunk-configuration-information-by-using-lync-server-control-panel"></a>Просмотр сведений о конфигурации магистрали SIP с помощью панели управления Lync Server

1.  В панели управления Lync Server щелкните **Маршрутизация голосовой связи** , а затем щелкните **Конфигурация магистрали**.

2.  На вкладке **Конфигурация магистрали** отображается список всех параметров конфигурации магистрали. для каждой коллекции будут отображены значения свойств " **имя**", " **область**", " **состояние**" и "обход сервера- **посредника** ", а также количество **использованных PSTN** **правил для номеров вызовов**, а также **вызываемых правил для нумерации** , связанных с коллекцией. Чтобы просмотреть дополнительные сведения о коллекции параметров конфигурации магистрали, щелкните интересующую коллекцию, нажмите кнопку **изменить**, а затем щелкните **Показать подробности**. Обратите внимание, что подробные сведения можно просматривать только для одной коллекции параметров конфигурации магистрали одновременно.

</div>

<div>

## <a name="viewing-sip-trunk-configuration-information-by-using-windows-powershell-cmdlets"></a>Просмотр сведений о конфигурации магистрали SIP с помощью командлетов Windows PowerShell

Параметры конфигурации магистрали SIP можно просмотреть с помощью Lync Server PowerShell и командлета Get-CsTrunkConfiguration. Этот командлет можно запустить из командной консоли Lync Server 2013 или из удаленного сеанса Windows PowerShell. Сведения об использовании удаленной оболочки Windows PowerShell для подключения к Lync Server приведены в статье "Краткое руководство по управлению Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" в статье Lync Server Windows PowerShell в блоге [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .

<div>

## <a name="to-view-sip-trunk-configuration-information"></a>Просмотр сведений о конфигурации магистрали SIP

  - Чтобы просмотреть сведения о всех параметрах конфигурации магистрали SIP, введите следующую команду в командной консоли Lync Server и нажмите клавишу ВВОД:
    
        Get-CsTrunkConfiguration
    
    Это приведет к возврату приблизительно такой информации:
    
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

</div>

Для получения дополнительных сведений обратитесь к разделу "Справка" для командлета [Get – CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunkConfiguration) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

