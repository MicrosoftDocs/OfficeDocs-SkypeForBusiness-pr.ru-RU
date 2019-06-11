---
title: Настройка сервера Lync Server для работы с System Center Operations Manager
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Lync Server to work with System Center Operations Manager
ms:assetid: b55a24ab-648b-4142-b3cd-3792860ba872
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205188(v=OCS.15)
ms:contentKeyID: 48185179
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6a6f26d4701cf1ed48f0069bcf7994e20ef0b2af
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841223"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-lync-server-2013-to-work-with-system-center-operations-manager"></a>Настройка Lync Server 2013 для работы с System Center Operations Manager

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-10-22_

Чтобы настроить инфраструктуру Microsoft Lync Server 2013 для работы с System Center Operations Manager, необходимо выполнить три действия.

  - Определение и Настройка основного сервера управления System Center Operations Manager. Настройка сервера управления включает установку System Center Operations Manager 2012 или System Center Operations Manager 2007 R2, а также настройку серверной базы данных с помощью SQL Server. Фактическая версия SQL Server, которую необходимо использовать, зависит от версии System Center Operations Manager, который вы используете. Подробности можно найти [в разделе Настройка основного сервера управления в Lync server 2013](lync-server-2013-configuring-the-primary-management-server.md).

  - Определите и настройте компьютеры Lync Server, которые вы хотите отслеживать. Для наблюдения за компьютером Lync Server с помощью System Center Operations Manager необходимо установить файлы агента System Center Operations Manager и настроить каждый сервер для работы в качестве прокси-сервера.

  - Определите и настройте компьютеры, которые должны выступать в качестве *узлов наблюдения за*Lync Server. Узлы наблюдения — это компьютеры, периодически выполняющие синтетические транзакции Lync Server, которые являются командлетами Windows PowerShell, которые проверяют, что ключевые компоненты сервера Lync, такие как возможность входа в систему или возможности обмена мгновенными сообщениями: работают должным образом.

В подразделах этого раздела содержатся инструкции по выполнению каждой из этих задач.

<div>

## <a name="in-this-section"></a>Содержание

  - [Настройка основного сервера управления в Lync Server 2013](lync-server-2013-configuring-the-primary-management-server.md)

  - [Установка пакетов управления Lync Server 2013](lync-server-2013-installing-the-lync-server-2013-management-packs.md)

  - [Настройка компьютеров с Lync Server, которые будут отслеживаться в Lync Server 2013](lync-server-2013-configuring-the-lync-server-computers-that-will-be-monitored.md)

  - [Установка и настройка узлов наблюдения в Lync Server 2013](lync-server-2013-installing-and-configuring-watcher-nodes.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

