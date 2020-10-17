---
title: 'Lync Server 2013: Устранение неполадок в командлетах ролей серверов и служб'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Troubleshooting server roles and services cmdlets
ms:assetid: 03be4cae-bf35-40b2-8e02-477b64afa4c9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415628(v=OCS.15)
ms:contentKeyID: 48183268
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5909fb8cdd2326d7c86bac5524a1ee02b5393b5c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48508746"
---
# <a name="troubleshooting-server-roles-and-services-cmdlets-in-lync-server-2013"></a>Устранение неполадок командлетов служб и ролей сервера в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-08-27_

Командлеты по устранению неполадок предоставляют различные способы проверки того, что Microsoft Lync Server 2013 работает должным образом. Например, командлеты CsHealthMonitoringConfiguration позволяют вам настроить тестовые учетные записи для пулов регистраторов и директоров. В свою очередь, вы можете использовать эти тестовые учетные записи для подтверждения того, что пользователи могут успешно выполнять обычные задачи, такие как вход в систему, обмен мгновенными сообщениями или звонок на телефон, находящийся в телефонной сети общего пользования (ТСОП).

<div>


> [!NOTE]
> Дополнительные сведения о командлетах можно найти в блоге Lync Server &nbsp; Windows PowerShell по адресу <A href="https://go.microsoft.com/fwlink/p/?linkid=263432">https://go.microsoft.com/fwlink/p/?linkId=263432</A> . Содержимое и URL-адрес любого блога могут быть изменены без предварительного уведомления.



</div>

<div>

## <a name="server-roles-and-services-cmdlets"></a>Командлеты для ролей серверов и служб

Ниже приведен список командлетов, которые относятся непосредственно к диагностике ролей серверов и служб:

**Диагностика ролей серверов и служб**

  - <span></span>  
    [Get — CsAudioTestServiceApplication](https://technet.microsoft.com/library/Gg412984(v=OCS.15))

  - <span></span>  
    [Set — CsAudioTestServiceApplication](https://technet.microsoft.com/library/Gg398907(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get — CsHealthMonitoringConfiguration](https://technet.microsoft.com/library/Gg398667(v=OCS.15))

  - <span></span>  
    [New — CsHealthMonitoringConfiguration](https://technet.microsoft.com/library/Gg398718(v=OCS.15))

  - <span></span>  
    [Remove — CsHealthMonitoringConfiguration](https://technet.microsoft.com/library/Gg425794(v=OCS.15))

  - <span></span>  
    [Set — CsHealthMonitoringConfiguration](https://technet.microsoft.com/library/Gg425847(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get — CsDiagnosticConfiguration](https://technet.microsoft.com/library/Gg413034(v=OCS.15))

  - <span></span>  
    [New — CsDiagnosticConfiguration](https://technet.microsoft.com/library/Gg398733(v=OCS.15))

  - <span></span>  
    [Remove — CsDiagnosticConfiguration](https://technet.microsoft.com/library/Gg412853(v=OCS.15))

  - <span></span>  
    [Set — CsDiagnosticConfiguration](https://technet.microsoft.com/library/Gg425734(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [New — CsDiagnosticsFilter](https://technet.microsoft.com/library/Gg413009(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get — CsDiagnosticHeaderConfiguration](https://technet.microsoft.com/library/Gg412774(v=OCS.15))

  - <span></span>  
    [New — CsDiagnosticHeaderConfiguration](https://technet.microsoft.com/library/Gg398350(v=OCS.15))

  - <span></span>  
    [Remove — CsDiagnosticHeaderConfiguration](https://technet.microsoft.com/library/Gg398941(v=OCS.15))

  - <span></span>  
    [Set — CsDiagnosticHeaderConfiguration](https://technet.microsoft.com/library/Gg399045(v=OCS.15))

</div>

</div>

<span> </span>

</div>

</div>

</div>

