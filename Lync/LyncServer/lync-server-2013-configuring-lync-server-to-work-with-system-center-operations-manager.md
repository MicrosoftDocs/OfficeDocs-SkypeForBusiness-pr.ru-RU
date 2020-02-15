---
title: Настройка Lync Server для работы с System Center Operations Manager
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
ms.openlocfilehash: ff72248e691d3e5358fda79a98d318cfc3a382eb
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2020
ms.locfileid: "42008451"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-lync-server-2013-to-work-with-system-center-operations-manager"></a><span data-ttu-id="ed0ae-102">Настройка Lync Server 2013 для работы с System Center Operations Manager</span><span class="sxs-lookup"><span data-stu-id="ed0ae-102">Configuring Lync Server 2013 to work with System Center Operations Manager</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ed0ae-103">_**Последнее изменение темы:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="ed0ae-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="ed0ae-104">Чтобы настроить инфраструктуру Microsoft Lync Server 2013 для работы с System Center Operations Manager, необходимо выполнить три действия:</span><span class="sxs-lookup"><span data-stu-id="ed0ae-104">In order to configure your Microsoft Lync Server 2013 infrastructure to work with System Center Operations Manager you must do three things:</span></span>

  - <span data-ttu-id="ed0ae-105">Определите и настройте основной сервер управления System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="ed0ae-105">Identify and configure your primary System Center Operations Manager management server.</span></span> <span data-ttu-id="ed0ae-106">Настройка сервера управления включает установку System Center Operations Manager 2012 или System Center Operations Manager 2007 R2, а также настройку внутренней базы данных с помощью SQL Server.</span><span class="sxs-lookup"><span data-stu-id="ed0ae-106">Configuring the management server includes installing System Center Operations Manager 2012 or System Center Operations Manager 2007 R2, as well as setting up a back-end database using SQL Server.</span></span> <span data-ttu-id="ed0ae-107">Действительную версию SQL Server, которую необходимо использовать, зависят от используемой версии System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="ed0ae-107">The actual version of SQL Server that you need to be use depends on the version of System Center Operations Manager you are using.</span></span> <span data-ttu-id="ed0ae-108">Дополнительные сведения см. [в разделе Настройка основного сервера управления в Lync server 2013](lync-server-2013-configuring-the-primary-management-server.md).</span><span class="sxs-lookup"><span data-stu-id="ed0ae-108">For details, see [Configuring the primary management server in Lync Server 2013](lync-server-2013-configuring-the-primary-management-server.md).</span></span>

  - <span data-ttu-id="ed0ae-109">Определите и настройте компьютеры Lync Server, которые необходимо отслеживать.</span><span class="sxs-lookup"><span data-stu-id="ed0ae-109">Identify and configure the Lync Server computers that you want to monitor.</span></span> <span data-ttu-id="ed0ae-110">Для наблюдения за компьютером Lync Server с помощью System Center Operations Manager необходимо установить файлы агента System Center Operations Manager и настроить каждый сервер для работы в качестве прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="ed0ae-110">To monitor a Lync Server computer by using System Center Operations Manager you must install the System Center Operations Manager agent files, and configure each server to act as a proxy.</span></span>

  - <span data-ttu-id="ed0ae-111">Определите и настройте компьютеры, которые будут использоваться в качестве *узлов-наблюдателей*Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ed0ae-111">Identify and configure the computers that you want to act as Lync Server *watcher nodes*.</span></span> <span data-ttu-id="ed0ae-112">Узлы-наблюдатели — это компьютеры, которые периодически выполняют синтетические транзакции Lync Server, которые являются командлетами Windows PowerShell, которые проверяют, что ключевые компоненты Lync Server, такие как возможность входа в систему или возможность обмена мгновенными сообщениями, работает должным образом.</span><span class="sxs-lookup"><span data-stu-id="ed0ae-112">Watcher nodes are computers that periodically run Lync Server synthetic transactions, which are Windows PowerShell cmdlets that verify that key Lync Server components, such as the ability to log on to the system or the ability to exchange instant messages are working as expected.</span></span>

<span data-ttu-id="ed0ae-113">В подразделах этого раздела приведены инструкции по выполнению каждой из этих задач.</span><span class="sxs-lookup"><span data-stu-id="ed0ae-113">The topics in this section contain instructions for carrying out each of these tasks.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="ed0ae-114">Содержание</span><span class="sxs-lookup"><span data-stu-id="ed0ae-114">In This Section</span></span>

  - [<span data-ttu-id="ed0ae-115">Настройка основного сервера управления в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ed0ae-115">Configuring the primary management server in Lync Server 2013</span></span>](lync-server-2013-configuring-the-primary-management-server.md)

  - [<span data-ttu-id="ed0ae-116">Установка пакетов управления Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ed0ae-116">Installing the Lync Server 2013 management packs</span></span>](lync-server-2013-installing-the-lync-server-2013-management-packs.md)

  - [<span data-ttu-id="ed0ae-117">Настройка компьютеров Lync Server, которые будут отслеживаться в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ed0ae-117">Configuring the Lync Server computers that will be monitored in Lync Server 2013</span></span>](lync-server-2013-configuring-the-lync-server-computers-that-will-be-monitored.md)

  - [<span data-ttu-id="ed0ae-118">Установка и настройка узлов-наблюдателей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ed0ae-118">Installing and configuring watcher nodes in Lync Server 2013</span></span>](lync-server-2013-installing-and-configuring-watcher-nodes.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

