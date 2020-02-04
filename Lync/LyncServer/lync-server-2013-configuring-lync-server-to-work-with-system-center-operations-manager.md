---
title: Настройка сервера Lync Server для работы с System Center Operations Manager
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
ms.openlocfilehash: f0cf422ddab501acf521c26c36d8f373bd42dbf9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762777"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-lync-server-2013-to-work-with-system-center-operations-manager"></a><span data-ttu-id="957f6-102">Настройка Lync Server 2013 для работы с System Center Operations Manager</span><span class="sxs-lookup"><span data-stu-id="957f6-102">Configuring Lync Server 2013 to work with System Center Operations Manager</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="957f6-103">_**Тема последнего изменения:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="957f6-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="957f6-104">Чтобы настроить инфраструктуру Microsoft Lync Server 2013 для работы с System Center Operations Manager, необходимо выполнить три действия.</span><span class="sxs-lookup"><span data-stu-id="957f6-104">In order to configure your Microsoft Lync Server 2013 infrastructure to work with System Center Operations Manager you must do three things:</span></span>

  - <span data-ttu-id="957f6-105">Определение и Настройка основного сервера управления System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="957f6-105">Identify and configure your primary System Center Operations Manager management server.</span></span> <span data-ttu-id="957f6-106">Настройка сервера управления включает установку System Center Operations Manager 2012 или System Center Operations Manager 2007 R2, а также настройку серверной базы данных с помощью SQL Server.</span><span class="sxs-lookup"><span data-stu-id="957f6-106">Configuring the management server includes installing System Center Operations Manager 2012 or System Center Operations Manager 2007 R2, as well as setting up a back-end database using SQL Server.</span></span> <span data-ttu-id="957f6-107">Фактическая версия SQL Server, которую необходимо использовать, зависит от версии System Center Operations Manager, который вы используете.</span><span class="sxs-lookup"><span data-stu-id="957f6-107">The actual version of SQL Server that you need to be use depends on the version of System Center Operations Manager you are using.</span></span> <span data-ttu-id="957f6-108">Подробности можно найти [в разделе Настройка основного сервера управления в Lync server 2013](lync-server-2013-configuring-the-primary-management-server.md).</span><span class="sxs-lookup"><span data-stu-id="957f6-108">For details, see [Configuring the primary management server in Lync Server 2013](lync-server-2013-configuring-the-primary-management-server.md).</span></span>

  - <span data-ttu-id="957f6-109">Определите и настройте компьютеры Lync Server, которые вы хотите отслеживать.</span><span class="sxs-lookup"><span data-stu-id="957f6-109">Identify and configure the Lync Server computers that you want to monitor.</span></span> <span data-ttu-id="957f6-110">Для наблюдения за компьютером Lync Server с помощью System Center Operations Manager необходимо установить файлы агента System Center Operations Manager и настроить каждый сервер для работы в качестве прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="957f6-110">To monitor a Lync Server computer by using System Center Operations Manager you must install the System Center Operations Manager agent files, and configure each server to act as a proxy.</span></span>

  - <span data-ttu-id="957f6-111">Определите и настройте компьютеры, которые должны выступать в качестве *узлов наблюдения за*Lync Server.</span><span class="sxs-lookup"><span data-stu-id="957f6-111">Identify and configure the computers that you want to act as Lync Server *watcher nodes*.</span></span> <span data-ttu-id="957f6-112">Узлы наблюдения — это компьютеры, периодически выполняющие синтетические транзакции Lync Server, которые являются командлетами Windows PowerShell, которые проверяют, что ключевые компоненты сервера Lync, такие как возможность входа в систему или возможности обмена мгновенными сообщениями: работают должным образом.</span><span class="sxs-lookup"><span data-stu-id="957f6-112">Watcher nodes are computers that periodically run Lync Server synthetic transactions, which are Windows PowerShell cmdlets that verify that key Lync Server components, such as the ability to log on to the system or the ability to exchange instant messages are working as expected.</span></span>

<span data-ttu-id="957f6-113">В подразделах этого раздела содержатся инструкции по выполнению каждой из этих задач.</span><span class="sxs-lookup"><span data-stu-id="957f6-113">The topics in this section contain instructions for carrying out each of these tasks.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="957f6-114">Содержание</span><span class="sxs-lookup"><span data-stu-id="957f6-114">In This Section</span></span>

  - [<span data-ttu-id="957f6-115">Настройка основного сервера управления в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="957f6-115">Configuring the primary management server in Lync Server 2013</span></span>](lync-server-2013-configuring-the-primary-management-server.md)

  - [<span data-ttu-id="957f6-116">Установка пакетов управления Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="957f6-116">Installing the Lync Server 2013 management packs</span></span>](lync-server-2013-installing-the-lync-server-2013-management-packs.md)

  - [<span data-ttu-id="957f6-117">Настройка компьютеров с Lync Server, которые будут отслеживаться в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="957f6-117">Configuring the Lync Server computers that will be monitored in Lync Server 2013</span></span>](lync-server-2013-configuring-the-lync-server-computers-that-will-be-monitored.md)

  - [<span data-ttu-id="957f6-118">Установка и настройка узлов наблюдения в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="957f6-118">Installing and configuring watcher nodes in Lync Server 2013</span></span>](lync-server-2013-installing-and-configuring-watcher-nodes.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

