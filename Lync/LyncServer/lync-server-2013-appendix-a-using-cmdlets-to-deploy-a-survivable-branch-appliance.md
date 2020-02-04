---
title: 'Lync Server 2013: Приложение A. Использование командлетов для развертывания устройств для обеспечения связи в филиалах'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: 'Appendix A: Using cmdlets to deploy a Survivable Branch Appliance'
ms:assetid: 796a26cf-7ec9-453b-8757-6153a6dd86c5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398598(v=OCS.15)
ms:contentKeyID: 48184569
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4a2da84e03cc05607a47f1fe5af4a8b7987946df
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737799"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="appendix-a-using-cmdlets-to-deploy-a-survivable-branch-appliance-in-lync-server-2013"></a>Приложение A. Использование командлетов для развертывания устройств для обеспечения связи в филиалах в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-10-07_

В этой статье описано, как развернуть бесперебойно работающее устройство филиала с помощью командной консоли Lync Server Management Shell. Выполните эту процедуру на центральном веб-сайте.

<div>

## <a name="to-deploy-a-survivable-branch-appliance-remotely"></a>Удаленное развертывание бесперебойно работающего устройства филиала

1.  Выполните действия, описанные в разделе [Добавление сайтов филиалов в топологию в Lync Server 2013](lync-server-2013-add-branch-sites-to-your-topology.md) , чтобы добавить новый сайт филиала.

2.  Присоедините сайт филиалов к домену.

3.  Добавьте группу РткуниверсалсбатечниЦианс в локальную группу администраторов.

4.  Перезапустите сервер и войдите в него как член группы РткуниверсалсбатечниЦианс.

5.  В командной консоли Lync Server введите следующие команды, заменив заполнители правильными сведениями для своей организации:
    
        Export-CsConfiguration -FileName C:\CSConfig.zip
        Import-CsConfiguration -LocalStore -FileName C:\CSConfig.zip -Verbose
        Enable-CSReplica -Verbose
        Enable-CsComputer -Verbose
        Request-CsCertificate -New -Type default -CA <YourCA> -Verbose
        Set-CsCertificate -Type Default -Thumbprint <YourCertThumbprint>
        Start-cswindowsservice -verbose

</div>

</div>

<span> </span>

</div>

</div>

</div>

