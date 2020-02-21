---
title: 'Lync Server 2013: сбор данных'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Data collection
ms:assetid: e40b03e5-455d-4bbc-831a-c61b1380db53
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399008(v=OCS.15)
ms:contentKeyID: 48185722
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6e6ef9454912b2d421302d7e696350a6f83bc9fd
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42206956"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="data-collection-in-lync-server-2013"></a>Сбор данных в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-09-08_

В коммуникационном программном обеспечении Microsoft Lync Server 2013 вы можете запустить средство планирования Microsoft Lync Server 2013, не Задокументируйте существующие и предложенные IP-адреса и полные доменные имена пограничных серверов, но значительно сложнее Поэтому, не вызывая ошибок конфигурации. Например, если в течение определенного периода времени требуется сосуществование, то распространенной ошибкой является повторное использование FQDN из существующего пограничного развертывания для развертывания Lync Server 2013 Edge. Записав текущие и предлагаемые IP-адреса и полные доменные имена в электронную таблицу, обычную таблицу или другую визуальную форму, вы можете избежать ошибок во время установки.

<div>


> [!WARNING]  
> Если вы использовали предыдущие версии средства планирования, возможно, вы использовали средство для создания топологии и экспортированного документа топологии, который будет использоваться в построителе топологий для публикации топологии. Возможность экспорта топологии была удалена из средства планирования. Использование предыдущей версии средства планирования для создания топологии документа для Lync Server 2013 не рекомендуется и приводит к непредвиденным результатам.



</div>

Таким образом, рекомендуемый подход — использовать следующий шаблон сбора данных, соответствующий пограничной топологии, для сбора различных полных доменных имен и IP-адресов, которые необходимо будет ввести в средство планирования. Записав текущую и предлагаемую конфигурацию, вы можете разместить значения в нужном контексте для вашей производственной среде. Также вы должны подумать о том, как вы будете настроить сосуществование и такие компоненты, как простые URL-адреса, общие файловые ресурсы и балансировка нагрузки.

Для успешного развертывания Microsoft Lync Server 2013 необходимо знать взаимодействие и зависимость от отдельных компонентов. Собирая данные из существующей инфраструктуры сети и сервера и применяя рекомендации по планированию, приведенные в этих разделах, можно интегрировать компоненты пограничного сервера Lync Server 2013 в инфраструктуру.

В [выборе топологии в Lync Server 2013](lync-server-2013-choosing-a-topology.md)существует три основные архитектуры с двумя вариациями, в которых всего пять возможных сценариев развертывания. One of these scenarios will be the starting point for your data collection. The IP addresses, server names, and domain names are examples that coincide with the matching certificate, firewall, and DNS diagrams that detail the information required for a complete planning solution. The diagrams and filling in your required certificate, DNS and firewall values is especially important in cross-team communications where the management of the certification authority, firewall configuration and DNS is managed by teams other than the team that plans the deployment. The diagrams provide information on required components that can be used to communicate these requirements for cross-team collaboration.

The provided diagrams are intentionally generic, but allow for the collection of all pertinent data that would be necessary for communication of requirements in a cross team scenario where networking, firewall, certificate creation and management, server deployment, and server management are handled by different groups. Наличие необходимых сведений о настройке сети, брандмауэрах, портах и протоколах, сертификатах и серверах не является ценным при развертывании Lync Server.

**Пограничный сервер и пограничный пул**

![7624717a-ce99-4ae8-a929-2c4d74a2e47d](images/Gg399008.7624717a-ce99-4ae8-a929-2c4d74a2e47d(OCS.15).jpg "7624717a-ce99-4ae8-a929-2c4d74a2e47d")

**Reverse Proxy**

![cf63fc50-2d11-4334-afc8-2d664ba1b6bb](images/Gg399008.cf63fc50-2d11-4334-afc8-2d664ba1b6bb(OCS.15).jpg "cf63fc50-2d11-4334-afc8-2d664ba1b6bb")

**директор или пул директоров;**

![56ba29ff-1309-4d5d-bf5c-35372169e947](images/Gg399008.56ba29ff-1309-4d5d-bf5c-35372169e947(OCS.15).jpg "56ba29ff-1309-4d5d-bf5c-35372169e947")

</div>

<span> </span>

</div>

</div>

</div>

