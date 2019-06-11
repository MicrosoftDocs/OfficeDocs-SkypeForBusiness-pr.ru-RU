---
title: 'Lync Server 2013: подготовка инфраструктуры и систем'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Preparing the infrastructure and systems
ms:assetid: 1254ee38-0679-4714-b293-1050f107c158
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398205(v=OCS.15)
ms:contentKeyID: 48183458
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0e724dd3b6105be3f4601c523dbbf558c91ca9f3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823793"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-the-infrastructure-and-systems-for-lync-server-2013"></a>Подготовка инфраструктуры и систем для Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2013-02-21_

Для развертывания Lync Server 2013 требуется использование построителя топологии для определения и публикации структуры топологии. Чтобы определить компоненты, необходимые для вашей топологии, вы используете Topology Builder для создания и сохранения структуры топологии. Прежде чем публиковать топологию в построителе топологии, выполните указанные ниже действия.

  - Получение и установка оборудования для каждого компонента в структуре топологии, созданной и сохраненной с помощью построителя топологии, включая все необходимые компьютеры (серверы с Lync Server 2013, серверы баз данных, серверы с запущенными информационными службами Интернета) ( IIS) и обратные прокси-серверы, сетевые адаптеры, подсистемы балансировки нагрузки оборудования и запоминающие устройства (например, файловые серверы). Подробные сведения о том, как определить топологию, указывающую компоненты, необходимые для вашего развертывания, приведены [в разделе Определение и Настройка топологии в Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md). Дополнительные сведения о требованиях к оборудованию для серверов можно найти в документации о поддержке [оборудования для Lync Server 2013](lync-server-2013-supported-hardware.md) .

  - Убедитесь, что сетевая инфраструктура соответствует требованиям. Подробности можно найти в разделе [требования к сетевой инфраструктуре для Lync Server 2013](lync-server-2013-network-infrastructure-requirements.md) в документации по планированию.

  - Настройте доменные службы Active Directory. Для публикации и включения топологии необходимы внутренние серверы, которые должны быть представлены учетными записями компьютеров в доменных СЛУЖБах Active Directory. Это можно сделать, присоединяя компьютеры к доменной службе Active Directory. Дополнительные сведения о подготовке доменных служб Active Directory можно найти в статьях [Подготовка службы AD DS для Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md).

  - Создайте файловый общий доступ. Сервер стандартных выпусков может размещать общую файловую систему для нужного файла, в корпоративной среде общий доступ к файлам не может размещаться на сервере переднего плана. Разрешения и членство в группах, необходимые для развертывания и настройки списка управления доступом (ACL) в папке, и общий доступ должны быть правильно заданы для успешного завершения построителя топологии. Необходимо убедиться в том, что у пользователя, выполняющего Topology Builder, есть следующие разрешения и членство в группах.
    
      - Член локальных администраторов
    
      - Член группы пользователей домена
    
      - Полный контроль над папкой "общий доступ" и "папка" в хранилище файлов

  - Для выпуска Enterprise Edition установите и настройте SQL Server. Для успешного завершения установки SQL Server необходимо, чтобы сервер SQL Server был подключен к сети, а пользователь, публикующий топологию, был локальным администратором SQL Server и должен быть членом группы sysadmin SQL Server в экземпляре SQL Server.

После выполнения всех задач подготовки, описанных в этой статье, но прежде чем публиковать топологию, вам также потребуется выполнить другие задачи подготовки, в том числе установка операционной системы Windows и другого необходимого программного обеспечения, Настройка IIS и настройка DNS. Подробнее об этих задачах можно узнать в разделе [требования к системе для серверов с Lync server 2013](lync-server-2013-system-requirements-for-servers-running-lync-server-2013.md), [Настройка служб IIS для Lync Server 2013](lync-server-2013-configure-iis.md)и [Подготовка инфраструктуры и систем для Lync Server 2013](lync-server-2013-preparing-the-infrastructure-and-systems.md). Кроме того, вы должны ознакомиться с требованиями клиентов и клиентов. Подробные сведения можно найти [в разделе Развертывание клиентов и устройств в Lync Server 2013](lync-server-2013-deploying-clients-and-devices.md).

<div>

## <a name="in-this-section"></a>Содержание

  - [Настройка оборудования для Lync Server 2013](lync-server-2013-hardware-setup.md)

  - [Установка программного обеспечения для Lync Server 2013](lync-server-2013-software-setup.md)

  - [Подготовка доменных служб Active Directory для Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md)

  - [Настройка SQL Server для Lync Server 2013](lync-server-2013-configure-sql-server-for-lync-server.md)

  - [Настройка DNS-записей в Lync Server 2013 для пула переднего плана или сервера Standard Edition](lync-server-2013-configure-dns-records-for-a-front-end-pool-or-standard-edition-server.md)

  - [Установка средств администрирования Lync Server 2013](lync-server-2013-install-lync-server-administrative-tools.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

