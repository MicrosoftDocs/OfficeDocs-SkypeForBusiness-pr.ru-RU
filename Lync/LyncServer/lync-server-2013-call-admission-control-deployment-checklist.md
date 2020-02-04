---
title: 'Lync Server 2013: контрольный список развертывания управления допуском звонков'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call admission control deployment checklist
ms:assetid: d56a525f-3da5-4ac0-a311-0c5efd98c9df
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398928(v=OCS.15)
ms:contentKeyID: 48185525
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e768cdd11d92b3aab5ce849f91cc1a422f119407
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741759"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-admission-control-deployment-checklist-for-lync-server-2013"></a>Контрольный список развертывания управления допуском звонков для Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-10-22_

Используйте следующий контрольный список, чтобы убедиться, что вы выполнили все необходимые задачи по настройке для развертывания управления допуском вызовов (CAC).

  - Если один или несколько пограничных серверов развертываются, то каждый IP-адрес внешнего интерфейса должен быть добавлен в список подсетей в параметрах сетевой конфигурации с битовой маской 32. Следует также связать эту подсеть (IP-адрес) с идентификатором сетевого сайта для географического расположения, где развернута пограничная служба A/V.
    
    <div>
    

    > [!NOTE]  
    > Пограничные серверы не обязаны реализовывать CAC.

    
    </div>

  - Убедитесь в том, что служба CAC включена либо с помощью панели управления Lync Server, либо путем запуска командлета, как указано в разделе [Включение функции управления допуском звонков в Lync Server 2013](lync-server-2013-enable-call-admission-control.md).

  - Убедитесь в том, что контроль допуска звонков включен на всех центральных сайтах. Это можно сделать с помощью построителя топологии. Если при публикации формируется предупреждение, *не* игнорируйте его.

  - Убедитесь в том, что параметры всех подсетей, управляемых в корпоративной сети, соответствуют конфигурации сети. Кроме того, очень важно, чтобы каждая подсеть была связана с сетевым сайтом, как описано в разделах [Подключение подсети к сетевому сайту в Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md).

  - Убедитесь, что подсеть или IP-адреса всех серверов переднего плана, устройств для обеспечения связи в филиалах, серверов аудио- и видеоконференций (если они размещаются в отдельном пуле) и серверов-посредников настроены в параметрах конфигурации сети.

</div>

<span> </span>

</div>

</div>

</div>

