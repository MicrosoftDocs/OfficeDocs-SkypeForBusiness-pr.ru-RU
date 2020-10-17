---
title: 'Lync Server 2013: контрольный список развертывания контроля допуска звонков'
description: 'Lync Server 2013: контрольный список развертывания контроля допуска звонков.'
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
ms.openlocfilehash: db7a69bda3048f93089a47b43a0b433946b783f1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569195"
---
# <a name="call-admission-control-deployment-checklist-for-lync-server-2013"></a>Контрольный список развертывания контроля допуска звонков для Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-10-22_

Используйте следующий контрольный список, чтобы убедиться в выполнении всех необходимых задач конфигурации для развертывания контроля допуска звонков (CAC).

  - Если развернут один или несколько пограничных серверов, IP-адреса внешних интерфейсов необходимо добавить в список подсетей в параметрах конфигурации с битовой маской 32. Кроме того, необходимо связать эту подсеть (IP-адрес) с ИД сетевого узла для географического расположения, где развернута пограничная служба A/V.
    
    <div>
    

    > [!NOTE]  
    > Пограничные серверы не являются обязательным требованием для развертывания контроля допуска звонков.

    
    </div>

  - Убедитесь, что служба контроля допуска звонков включена либо с помощью панели управления Lync Server, либо с помощью командлета, указанного в разделе [Включение контроля допуска звонков в Lync Server 2013](lync-server-2013-enable-call-admission-control.md).

  - Убедитесь, что контроль допуска звонков включен на всех центральных сайтах. Это можно сделать с помощью построителя топологий. Если при публикации создается предупреждение, *не* игнорируйте его.

  - Убедитесь, что все подсети, управляемые в корпоративной сети, настроены в параметрах конфигурации сети. Кроме того, важно, чтобы каждая подсеть была связана с сетевым сайтом, как описано в [привязку подсети к сетевому сайту в Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md).

  - Убедитесь, что подсеть или IP-адреса всех серверов переднего плана, устройств для обеспечения связи в филиалах, серверов аудио- и видеоконференций (если они размещаются в отдельном пуле) и серверов-посредников настроены в параметрах конфигурации сети.

</div>

<span> </span>

</div>

</div>

</div>

