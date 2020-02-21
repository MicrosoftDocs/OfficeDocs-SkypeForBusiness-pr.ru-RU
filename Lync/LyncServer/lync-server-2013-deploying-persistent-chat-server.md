---
title: 'Lync Server 2013: развертывание сервера сохраняемого чата'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying Persistent Chat Server
ms:assetid: e3b930fb-6855-47f0-b6b3-7dfae386540d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205357(v=OCS.15)
ms:contentKeyID: 48185717
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4eb457dbaee5e91b7b4f408018242384cd8992c2
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42188262"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploying-persistent-chat-server-in-lync-server-2013"></a>Развертывание сервера сохраняемого чата в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2014-03-31_

Lync Server 2013, сервер сохраняемого чата входит в состав инфраструктуры Lync Server 2013.

При развертывании сервера сохраняемого чата необходимо выполнить указанные ниже действия.

  - Используйте построитель топологий для определения или импорта и последующей публикации топологии и компонентов, которые требуется развернуть.

  - Подготовьте среду для развертывания компонентов сервера сохраняемого чата.

  - Установите и настройте компоненты сервера сохраняемого чата для развертывания.

Сервер сохраняемого чата доступен в составе Lync Server 2013 Enterprise Edition в виде отдельного пула (без совместного размещения на серверах переднего плана Enterprise Edition). Сервер сохраняемого чата требует наличия внутреннего сервера SQL Server в пуле Enterprise Edition для хранения содержимого комнаты чата и других релевантных метаданных. Рекомендуется установить **PersistentChatStore** на выделенный сервер переднего плана SQL Server, хотя совместное размещение внешних серверов Lync Server 2013 и **PersistentChatStore** в одном экземпляре SQL Server поддерживается.

Сервер сохраняемого чата также можно развернуть с помощью Lync Server 2013 Standard Edition. В этом случае сервер переднего плана **PersistentChatService** размещается на компьютере Standard Edition, а внутренний сервер **PersistentChatStore** может быть развернут на локальном экземпляре SQL Server Express.

Дополнительные сведения о поддерживаемых конфигурациях совместного расположения приведены [в разделе Поддержка выровненных серверов в Lync server 2013](lync-server-2013-supported-server-collocation.md).

<div>


> [!IMPORTANT]  
> Мы не поддерживаем высокий уровень доступности для сервера&nbsp;сохраняемого чата Standard Edition. Производительность и масштабирование будут ограничены. Кроме того, поддерживается только новый сервер сервера&nbsp;Standard Edition для сохраняемого чата. Мы не поддерживаем обновление Lync Server 2010, Group Chat Server до версии сервера&nbsp;&nbsp;сохраняемого чата для сервера Standard chat для Lync Server 2013.



</div>

Если в Организации требуется поддержка соответствия требованиям, вы можете установить службу соответствия сервера сохраняемого чата на сервере переднего плана сервера сохраняемого чата. Для совместимости требуется отдельная база данных.

Для каждой топологии требуется как минимум сервер с установленным Lync Server 2013 и сервер с установленным программным обеспечением баз данных SQL Server.

Используйте построитель топологий, чтобы добавить сервер сохраняемого чата в развертывания Lync Server 2013. Вы можете добавить один или несколько пулов серверов сохраняемого чата с помощью построителя топологий. Следуйте тем же инструкциям по развертыванию, чтобы развернуть несколько пулов серверов сохраняемого чата, как и для любого пула. Дополнительные сведения см. в разделе [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) в документации по развертыванию.

Сведения о доступных топологиях, а также требованиях к техническим и программному обеспечению для установки сервера сохраняемого чата приведены в статье [Планирование сервера сохраняемого чата в Lync server 2013](lync-server-2013-planning-for-persistent-chat-server.md) в документации по планированию, [как сервер сохраняемого чата в Lync Server 2013](lync-server-2013-how-persistent-chat-server-works.md) в документации по планированию, документации по развертыванию или документации по работе, а также [поддерживаемое оборудование для Lync Server 2013](lync-server-2013-supported-hardware.md) в документации по поддержке.

Для получения дополнительных сведений о получении сертификатов, создании базы данных SQL Server и создании хранилищ файлов ознакомьтесь со статьей [deploy Lync Server 2013](lync-server-2013-deploying-lync-server.md) в документации по развертыванию.

Один сервер переднего плана сервера сохраняемого чата может поддерживать 20 000 активных пользователей. Пул серверов сохраняемого чата может иметь до четырех активных серверов переднего плана, поддерживающих всего 80 000 одновременно работающих пользователей.

Сервер сохраняемого чата также поддерживается на виртуальном сервере. Виртуальный сервер может поддерживать до 20000 пользователей при условии соответствия характеристикам физического сервера.

<div>


> [!IMPORTANT]  
> Для обеспечения безопасности файловой системы необходимо установить сервер сохраняемого чата в файловой системе NTFS. Файловая система FAT32 не поддерживается для сервера сохраняемого чата.



</div>

<div>

## <a name="in-this-section"></a>Содержание

  - [Принцип работы сервера сохраняемого чата в Lync Server 2013](lync-server-2013-how-persistent-chat-server-works.md)

  - [Контрольный список развертывания для сервера сохраняемого чата в Lync Server 2013](lync-server-2013-deployment-checklist-for-persistent-chat-server.md)

  - [Технические требования для сервера сохраняемого чата в Lync Server 2013](lync-server-2013-technical-requirements-for-persistent-chat-server.md)

  - [Настройка систем и инфраструктуры для сервера сохраняемого чата в Lync Server 2013](lync-server-2013-setting-up-systems-and-infrastructure-for-persistent-chat-server.md)

  - [Добавление сервера сохраняемого чата в развертывание в Lync Server 2013](lync-server-2013-adding-persistent-chat-server-to-your-deployment.md)

  - [Установка сервера сохраняемого чата в Lync Server 2013](lync-server-2013-installing-persistent-chat-server.md)

  - [Добавление администратора сохраняемого чата в Lync Server 2013](lync-server-2013-adding-a-persistent-chat-administrator.md)

  - [Настройка сервера сохраняемого чата в Lync Server 2013](lync-server-2013-configuring-persistent-chat-server.md)

  - [Настройка сервера сохраняемого чата с помощью командлетов Windows PowerShell](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md)

  - [Устранение неполадок конфигурации сервера сохраняемого чата с помощью командлетов Windows PowerShell в Lync Server 2013](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md)

  - [Настройка сервера сохраняемого чата для обеспечения высокой доступности и аварийного восстановления в Lync Server 2013](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md)

  - [Отработка отказа и отработка отказа сервера сохраняемого чата в Lync Server 2013](lync-server-2013-failing-over-and-failing-back-persistent-chat-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

