---
title: Настройка Lync Server для работы с System Center Operations Manager
description: Настройка Lync Server для работы с System Center Operations Manager.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Lync Server to work with System Center Operations Manager
ms:assetid: b55a24ab-648b-4142-b3cd-3792860ba872
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205188(v=OCS.15)
ms:contentKeyID: 48185179
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f58126c9e56d48548ba5ce6d74059809c55fecf5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48570775"
---
# <a name="configuring-lync-server-2013-to-work-with-system-center-operations-manager"></a>Настройка Lync Server 2013 для работы с System Center Operations Manager

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-10-22_

Чтобы настроить инфраструктуру Microsoft Lync Server 2013 для работы с System Center Operations Manager, необходимо выполнить три действия:

  - Определите и настройте основной сервер управления System Center Operations Manager. Настройка сервера управления включает установку System Center Operations Manager 2012 или System Center Operations Manager 2007 R2, а также настройку внутренней базы данных с помощью SQL Server. Действительную версию SQL Server, которую необходимо использовать, зависят от используемой версии System Center Operations Manager. Дополнительные сведения см. [в разделе Настройка основного сервера управления в Lync server 2013](lync-server-2013-configuring-the-primary-management-server.md).

  - Определите и настройте компьютеры Lync Server, которые необходимо отслеживать. Для наблюдения за компьютером Lync Server с помощью System Center Operations Manager необходимо установить файлы агента System Center Operations Manager и настроить каждый сервер для работы в качестве прокси-сервера.

  - Определите и настройте компьютеры, которые будут использоваться в качестве *узлов-наблюдателей*Lync Server. Узлы-наблюдатели — это компьютеры, которые периодически выполняют синтетические транзакции Lync Server, которые являются командлетами Windows PowerShell, которые проверяют, что ключевые компоненты Lync Server, такие как возможность входа в систему или возможность обмена мгновенными сообщениями, работают ожидаемым образом.

В подразделах этого раздела приведены инструкции по выполнению каждой из этих задач.

<div>

## <a name="in-this-section"></a>Содержание

  - [Настройка основного сервера управления в Lync Server 2013](lync-server-2013-configuring-the-primary-management-server.md)

  - [Установка пакетов управления Lync Server 2013](lync-server-2013-installing-the-lync-server-2013-management-packs.md)

  - [Настройка компьютеров Lync Server, которые будут отслеживаться в Lync Server 2013](lync-server-2013-configuring-the-lync-server-computers-that-will-be-monitored.md)

  - [Установка и настройка узлов-наблюдателей в Lync Server 2013](lync-server-2013-installing-and-configuring-watcher-nodes.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

