---
title: 'Lync Server 2013: подготовка инфраструктуры и систем'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing the infrastructure and systems
ms:assetid: 1254ee38-0679-4714-b293-1050f107c158
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398205(v=OCS.15)
ms:contentKeyID: 48183458
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bb33552fde0da6dc91f21eeecaf1ea5e85d72159
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42201765"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="preparing-the-infrastructure-and-systems-for-lync-server-2013"></a>Подготовка инфраструктуры и систем для Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-02-21_

Для развертывания Lync Server 2013 необходимо использовать построитель топологий для определения и публикации структуры топологии. Чтобы определить компоненты, необходимые для вашей топологии, используйте построитель топологий для создания и сохранения структуры топологии. Перед публикацией топологии в построителе топологии выполните следующие действия.

  - Получите и установите оборудование для каждого компонента в структуре топологии, созданной и сохраненной с помощью построителя топологий, включая все необходимые компьютеры (серверы Lync Server 2013, серверы баз данных, серверы служб IIS ( IIS) и обратных прокси-серверов (при необходимости), сетевых адаптеров, аппаратных подсистем балансировки нагрузки и устройств хранения (например, файловых серверов). Сведения об определении топологии, указывающей компоненты, необходимые для развертывания, приведены [в статье определение и Настройка топологии в Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md). Для получения дополнительных сведений о требованиях к оборудованию для серверов ознакомьтесь со статьей [Supported Hardware for Lync Server 2013](lync-server-2013-supported-hardware.md) в документации по поддержке.

  - Убедитесь, что сетевая инфраструктура соответствует требованиям. Дополнительные сведения приведены в статье [требования к сетевой инфраструктуре для Lync Server 2013](lync-server-2013-network-infrastructure-requirements.md) в документации по планированию.

  - Настройка доменных служб Active Directory. Для публикации и активации топологии необходимо, чтобы внутренние серверы были представлены учетными записями компьютеров в AD DS. Этого можно достичь, присоединив компьютеры к AD DS. Сведения о подготовке AD DS приведены в статье [Подготовка доменных служб Active Directory для Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md).

  - Создайте общий файловый ресурс. Серверы Standard Edition могут разместить общий файловый ресурс для требуемого файла, а в развертывании Enterprise файловый ресурс не может размещаться на интерфейсном сервере. Разрешения и членство в группах, необходимое для развертывания и настройки списка управления доступом (ACL) для папки и общего ресурса должны быть правильно установлены, чтобы построитель топологии успешно завершил работу. Необходимо убедиться, что у пользователя, выполняющего построитель топологий, есть следующие разрешения и членство в группах:
    
      - Участник группы "Локальные администраторы"
    
      - Участник группы "Пользователи домена"
    
      - Полный доступ к общему файловому ресурсу и папке файлового хранилища

  - Для Enterprise Edition установите и настройте SQL Server. Для успешной установки SQL Server сервер на основе SQL Server должен быть доступен, а пользователь, который публикует топологию, должен быть локальным администратором на сервере SQL Server, а также должен быть членом группы SQL Server sysadmin на экземпляре SQL Server.

После завершения всех задач подготовки, описанных в этом разделе, но перед публикацией топологии, также требуется выполнить другие задачи, в том числе установить операционные системы Windows и другое необходимое ПО, настроить службы IIS и DNS. Сведения об этих задачах приведены в разделе [требования к системе для серверов, на которых работает Lync server 2013](lync-server-2013-system-requirements-for-servers-running-lync-server-2013.md), [Настройка служб IIS для Lync Server 2013](lync-server-2013-configure-iis.md)и [Подготовка инфраструктуры и систем для Lync Server 2013](lync-server-2013-preparing-the-infrastructure-and-systems.md). Кроме того, ознакомьтесь с клиентами и требованиями к клиентам. Дополнительные сведения см. [в статье Deploy clients and Devices in Lync Server 2013](lync-server-2013-deploying-clients-and-devices.md).

<div>

## <a name="in-this-section"></a>Содержание

  - [Настройка оборудования для Lync Server 2013](lync-server-2013-hardware-setup.md)

  - [Настройка программного обеспечения для Lync Server 2013](lync-server-2013-software-setup.md)

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

