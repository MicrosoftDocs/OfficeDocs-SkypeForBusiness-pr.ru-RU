---
title: 'Lync Server 2013: настройка серверов и пулов переднего плана'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Setting up Front End Servers and Front End pools
ms:assetid: c88526f9-69e2-47dd-b3d7-056139d74fb2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398827(v=OCS.15)
ms:contentKeyID: 48185381
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ab21e5933623af58834d3b9effa5ba1e2beecc43
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849726"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-front-end-servers-and-front-end-pools-for-lync-server-2013"></a><span data-ttu-id="54de8-102">Настройка серверов и пулов переднего плана для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="54de8-102">Setting up Front End Servers and Front End pools for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="54de8-103">_**Тема последнего изменения:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="54de8-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="54de8-104">В этом разделе рассказывается, как установить Lync Server 2013 и настроить роли сервера для стандартного выпуска Standard Server и пула переднего плана, включая серверы переднего плана и любые серверные роли, размещенные с помощью серверного переднего плана.</span><span class="sxs-lookup"><span data-stu-id="54de8-104">This section guides you through installing Lync Server 2013 and setting up the server roles for the Standard Edition server and the Front End pool, including the Front End Servers and any server roles that are collocated with the Front End Servers.</span></span> <span data-ttu-id="54de8-105">Для установки и настройки ролей сервера вы запускаете мастер развертывания Lync Server на каждом компьютере, на котором устанавливается роль сервера.</span><span class="sxs-lookup"><span data-stu-id="54de8-105">To install and set up server roles, you run the Lync Server Deployment Wizard on each computer on which you are installing a server role.</span></span> <span data-ttu-id="54de8-106">Мастер развертывания используется для выполнения всех четырех шагов развертывания, в том числе для установки локального хранилища конфигурации и серверов переднего плана, настройки сертификатов и запуска служб.</span><span class="sxs-lookup"><span data-stu-id="54de8-106">You use the Deployment Wizard to complete all four deployment steps, including installing the Local Configuration store, installing the Front End Servers, configuring certificates, and starting services.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="54de8-107">Для настройки ролей сервера необходимо успешно опубликовать топологию.</span><span class="sxs-lookup"><span data-stu-id="54de8-107">Before you can set up server roles, you must have successfully published a topology.</span></span> <span data-ttu-id="54de8-108">Подробные сведения о публикации топологии можно найти в статьях <A href="lync-server-2013-finalizing-and-implementing-the-topology-design.md">Завершение и реализация топологии в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="54de8-108">For details about publishing a topology, see <A href="lync-server-2013-finalizing-and-implementing-the-topology-design.md">Finalizing and implementing the topology design in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="54de8-109">Содержание</span><span class="sxs-lookup"><span data-stu-id="54de8-109">In This Section</span></span>

  - [<span data-ttu-id="54de8-110">Установка локального хранилища конфигурации в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="54de8-110">Install the Local Configuration store in Lync Server 2013</span></span>](lync-server-2013-install-the-local-configuration-store.md)

  - [<span data-ttu-id="54de8-111">Установка компонентов сервера для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="54de8-111">Install server components for Lync Server 2013</span></span>](lync-server-2013-install-lync-server-server-components.md)

  - [<span data-ttu-id="54de8-112">Настройка сертификатов для серверов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="54de8-112">Configure certificates for servers in Lync Server 2013</span></span>](lync-server-2013-configure-certificates-for-servers.md)

  - [<span data-ttu-id="54de8-113">Запуск служб на серверах для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="54de8-113">Start services on servers for Lync Server 2013</span></span>](lync-server-2013-start-services-on-servers.md)

  - [<span data-ttu-id="54de8-114">Тестирование развертывания пула в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="54de8-114">Test the pool deployment in Lync Server 2013</span></span>](lync-server-2013-test-the-pool-deployment.md)

  - [<span data-ttu-id="54de8-115">Тестирование сервера Standard Edition в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="54de8-115">Test the Standard Edition server in Lync Server 2013</span></span>](lync-server-2013-test-the-standard-edition-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

