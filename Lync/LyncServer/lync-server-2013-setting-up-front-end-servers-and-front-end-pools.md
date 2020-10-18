---
title: 'Lync Server 2013: Настройка серверов переднего плана и интерфейсных пулов'
description: 'Lync Server 2013: Настройка серверов переднего плана и интерфейсных пулов.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up Front End Servers and Front End pools
ms:assetid: c88526f9-69e2-47dd-b3d7-056139d74fb2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398827(v=OCS.15)
ms:contentKeyID: 48185381
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d746bf342f6937c068e32caddd484b708a123910
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577245"
---
# <a name="setting-up-front-end-servers-and-front-end-pools-for-lync-server-2013"></a><span data-ttu-id="eb25a-103">Настройка серверов переднего плана и интерфейсных пулов для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eb25a-103">Setting up Front End Servers and Front End pools for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eb25a-104">_**Последнее изменение темы:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="eb25a-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="eb25a-105">В этом разделе описывается установка Lync Server 2013 и Настройка ролей сервера для сервера Standard Edition и интерфейсного пула, включая серверы переднего плана и роли серверов, размещенные с серверами переднего плана.</span><span class="sxs-lookup"><span data-stu-id="eb25a-105">This section guides you through installing Lync Server 2013 and setting up the server roles for the Standard Edition server and the Front End pool, including the Front End Servers and any server roles that are collocated with the Front End Servers.</span></span> <span data-ttu-id="eb25a-106">Чтобы установить и настроить роли сервера, запустите мастер развертывания Lync Server на каждом компьютере, на котором устанавливается роль сервера.</span><span class="sxs-lookup"><span data-stu-id="eb25a-106">To install and set up server roles, you run the Lync Server Deployment Wizard on each computer on which you are installing a server role.</span></span> <span data-ttu-id="eb25a-107">Мастер развертывания используется для выполнения всех четырех этапов развертывания, в том числе для установки локального хранилища конфигурации, установки серверов переднего плана, настройки сертификатов и запуска служб.</span><span class="sxs-lookup"><span data-stu-id="eb25a-107">You use the Deployment Wizard to complete all four deployment steps, including installing the Local Configuration store, installing the Front End Servers, configuring certificates, and starting services.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="eb25a-108">Перед настройкой ролей сервера необходимо успешно опубликовать топологию.</span><span class="sxs-lookup"><span data-stu-id="eb25a-108">Before you can set up server roles, you must have successfully published a topology.</span></span> <span data-ttu-id="eb25a-109">Сведения о публикации топологии можно найти в статье <A href="lync-server-2013-finalizing-and-implementing-the-topology-design.md">Завершение и реализация топологии в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="eb25a-109">For details about publishing a topology, see <A href="lync-server-2013-finalizing-and-implementing-the-topology-design.md">Finalizing and implementing the topology design in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="eb25a-110">Содержание</span><span class="sxs-lookup"><span data-stu-id="eb25a-110">In This Section</span></span>

  - [<span data-ttu-id="eb25a-111">Установка локального хранилища конфигурации в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eb25a-111">Install the Local Configuration store in Lync Server 2013</span></span>](lync-server-2013-install-the-local-configuration-store.md)

  - [<span data-ttu-id="eb25a-112">Установка компонентов сервера для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eb25a-112">Install server components for Lync Server 2013</span></span>](lync-server-2013-install-lync-server-server-components.md)

  - [<span data-ttu-id="eb25a-113">Настройка сертификатов для серверов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eb25a-113">Configure certificates for servers in Lync Server 2013</span></span>](lync-server-2013-configure-certificates-for-servers.md)

  - [<span data-ttu-id="eb25a-114">Запуск служб на серверах для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eb25a-114">Start services on servers for Lync Server 2013</span></span>](lync-server-2013-start-services-on-servers.md)

  - [<span data-ttu-id="eb25a-115">Тестирование развертывания пула в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eb25a-115">Test the pool deployment in Lync Server 2013</span></span>](lync-server-2013-test-the-pool-deployment.md)

  - [<span data-ttu-id="eb25a-116">Тестирование сервера Standard Edition в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eb25a-116">Test the Standard Edition server in Lync Server 2013</span></span>](lync-server-2013-test-the-standard-edition-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

