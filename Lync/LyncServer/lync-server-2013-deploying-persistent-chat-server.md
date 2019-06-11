---
title: 'Lync Server 2013: развертывание сервера сохраняемого чата'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploying Persistent Chat Server
ms:assetid: e3b930fb-6855-47f0-b6b3-7dfae386540d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205357(v=OCS.15)
ms:contentKeyID: 48185717
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6a730057735f187dc5e5080d532515a4eb9db110
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834535"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-persistent-chat-server-in-lync-server-2013"></a>Развертывание сервера сохраняемого чата в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2014-03-31_

Lync Server 2013, сервер сохраняемого чата входит в состав инфраструктуры Lync Server 2013.

Для развертывания сохраняемого сервера чата необходимо:

  - С помощью Topology Builder вы можете определить (или импортировать) и затем опубликовать свою топологию и компоненты, которые вы хотите развернуть.

  - Подготовка среды для развертывания постоянных серверных компонентов чата.

  - Установите и настройте компоненты сервера сохраняемого чата для развертывания.

Сервер для Lync Server 2013 Enterprise Edition доступен в виде отдельного пула (не размещается вместе с серверами переднего плана Enterprise Edition). Для хранения содержимого комнаты чата и других нужных метаданных сервер для работы с сохраняемым чат требуется сервер SQL Server из пула Enterprise Edition. Мы рекомендуем установить **персистентчатсторе** на выделенный сервер SQL Server, несмотря на то, что размещение сервера Lync Server 2013 и **персистентчатсторе** на одном и том же экземпляре SQL Server поддерживается.

Кроме того, с помощью Lync Server 2013 Standard Edition можно развернуть сервер сохраняемого чата. В этом случае сервер переднего плана **персистентчатсервице** размещается на компьютере Standard Edition, а сервер **персистентчатсторе** Server можно развернуть на локальном экземпляре SQL Server Express.

Подробные сведения о поддерживаемых конфигурациях сорасположений можно найти в разделе Поддерживаемые параметры совместного расположения [серверов в Lync server 2013](lync-server-2013-supported-server-collocation.md).

<div>


> [!IMPORTANT]  
> Мы не поддерживаем высокий уровень доступности сохраняемого сервера&nbsp;для работы с версией Standard Chat. Производительность и масштаб будут ограничены. Кроме того, мы поддерживаем только новый сервер&nbsp;стандартный выпуск для версии для постоянного чата. Мы не поддерживаем обновление Lync Server 2010, групповой чат с сервером для Lync Server 2013&nbsp;для обычного чата Server&nbsp;Standard Edition.



</div>

Если в вашей организации требуется поддержка соответствия требованиям, вы можете установить службу соответствия требованиям сервера для разговора на сервер переднего плана с постоянным участием. Для обеспечения соответствия требованиям требуется отдельная база данных.

Для каждой топологии требуется сервер с установленным Lync Server 2013 и сервер с установленным программным обеспечением базы данных SQL Server.

Используйте построитель топологии, чтобы добавить сохраняемый сервер чата в развертывание Lync Server 2013. Вы можете добавить один или несколько пулов серверов для постоянного чата с помощью Topology Builder. Следуйте тем же инструкциям по развертыванию, чтобы развернуть несколько пулов серверов сохраняемого чата, как и в случае с пулом. Подробные сведения можно найти в разделе [развертывание Lync Server 2013](lync-server-2013-deploying-lync-server.md) в документации по развертыванию.

Сведения о доступных топологиях, требованиях к техническим и программному обеспечению для установки постоянного сервера чата приведены в разделе [планирование сохраняемого сервера чата в Lync server 2013](lync-server-2013-planning-for-persistent-chat-server.md) в документации по планированию, [как работает сервер сохраняемого чата. в SharePoint Server 2013](lync-server-2013-how-persistent-chat-server-works.md) в документации по планированию, документации по развертыванию, документации по операциям и [поддерживаемому оборудованию для Lync Server 2013](lync-server-2013-supported-hardware.md) в документации по поддержке.

Подробные сведения о получении сертификатов, создании базы данных SQL Server и создании хранилищ файлов можно найти в разделе [развертывание Lync Server 2013](lync-server-2013-deploying-lync-server.md) в документации по развертыванию.

Один сервер-сервер для входа в чате может поддерживать 20 000 активных пользователей. Вы можете использовать серверный пул для постоянного чата с четырьмя активными серверами переднего плана, поддерживающими общее количество одновременных пользователей 80 000.

На виртуальном сервере также поддерживается сохраняемый сервер чатов. Виртуальный сервер может поддерживать до 20 000 одновременных пользователей, если он соответствует спецификациям физического сервера.

<div>


> [!IMPORTANT]  
> Для обеспечения безопасности файловой системы необходимо установить сохраняемый сервер чата в файловой системе NTFS. Файловая система FAT32 не поддерживается для сервера сохраняемого чата.



</div>

<div>

## <a name="in-this-section"></a>Содержание

  - [Как работает сервер сохраняемого чата в Lync Server 2013](lync-server-2013-how-persistent-chat-server-works.md)

  - [Контрольный список развертывания для сервера сохраняемого чата в Lync Server 2013](lync-server-2013-deployment-checklist-for-persistent-chat-server.md)

  - [Технические требования для постоянного сервера чата в Lync Server 2013](lync-server-2013-technical-requirements-for-persistent-chat-server.md)

  - [Настройка систем и инфраструктуры для сервера сохраняемого чата в Lync Server 2013](lync-server-2013-setting-up-systems-and-infrastructure-for-persistent-chat-server.md)

  - [Добавление сервера сохраняемого сеанса беседы в развертывание в Lync Server 2013](lync-server-2013-adding-persistent-chat-server-to-your-deployment.md)

  - [Установка сервера сохраняемого чата в Lync Server 2013](lync-server-2013-installing-persistent-chat-server.md)

  - [Добавление администратора сохраняемого чата в Lync Server 2013](lync-server-2013-adding-a-persistent-chat-administrator.md)

  - [Настройка сервера сохраняемого чата в Lync Server 2013](lync-server-2013-configuring-persistent-chat-server.md)

  - [Настройка сервера сохраняемого сеанса беседы с помощью командлетов Windows PowerShell](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md)

  - [Устранение неполадок конфигурации сервера сохраняемого чата с помощью командлетов Windows PowerShell в Lync Server 2013](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md)

  - [Настройка сервера сохраняемого чата для обеспечения высокой доступности и аварийного восстановления в Lync Server 2013](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md)

  - [Отработка отказа и восстановление после сбоя сервера сохраняемого чата в Lync Server 2013](lync-server-2013-failing-over-and-failing-back-persistent-chat-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

