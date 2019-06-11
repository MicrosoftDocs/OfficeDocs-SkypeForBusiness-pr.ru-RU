---
title: 'Lync Server 2013: обзор развертывания'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment overview
ms:assetid: da67555e-f410-4c37-9996-d511f37da8d1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205305(v=OCS.15)
ms:contentKeyID: 48185555
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f71a61e2bd374f1dfe2863aead5bbadc23c8afe8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834485"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-overview-for-lync-server-2013"></a><span data-ttu-id="f7030-102">Обзор развертывания для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f7030-102">Deployment overview for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f7030-103">_**Тема последнего изменения:** 2013-03-12_</span><span class="sxs-lookup"><span data-stu-id="f7030-103">_**Topic Last Modified:** 2013-03-12_</span></span>

<span data-ttu-id="f7030-104">Основное различие между Lync Server 2013 Enterprise Edition и Lync Server 2013 Standard Edition состоит в том, что стандартный выпуск не поддерживает возможности высокой доступности, включенные в Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="f7030-104">The main difference between Lync Server 2013 Enterprise Edition and Lync Server 2013 Standard Edition is that Standard Edition does not support the high availability features included with Enterprise Edition.</span></span> <span data-ttu-id="f7030-105">Для обеспечения высокой доступности вам нужно развернуть несколько серверов переднего плана в пул, а затем вы можете создать зеркальную копию сервера под управлением SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f7030-105">For high availability, you need to deploy multiple Front End Servers to a pool and then you can mirror the server running SQL Server.</span></span> <span data-ttu-id="f7030-106">С помощью Enterprise Edition вы можете выделять или определять отдельное сервер-посредник.</span><span class="sxs-lookup"><span data-stu-id="f7030-106">With Enterprise Edition you can choose to collocate or define a stand-alone Mediation Server.</span></span> <span data-ttu-id="f7030-107">Сервер мониторинга и сервер архивации могут использовать изолированный сервер, на котором работает SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f7030-107">The Monitoring Server and Archiving Server can use a stand-alone server running SQL Server.</span></span> <span data-ttu-id="f7030-108">Кроме того, у них могут быть экземпляры SQL Server, запущенные на сервере базы данных, для серверов и групп с внешними интерфейсами.</span><span class="sxs-lookup"><span data-stu-id="f7030-108">Or, they can have instances of SQL Server running on the database server for the Front End Servers and pools.</span></span>

<span data-ttu-id="f7030-109">Серверы Lync Server 2013 Standard Edition предназначены для небольших организаций и удаленных расположений, которые географически удаляются из основного развертывания Организации.</span><span class="sxs-lookup"><span data-stu-id="f7030-109">Servers running Lync Server 2013 Standard Edition are intended for smaller organizations and remote locations, which are geographically removed from the organization’s main deployment.</span></span> <span data-ttu-id="f7030-110">Два стандартных сервера выпуска, Объединенные вместе для перехода на другой ресурс, в случае аварии могут поддерживать до 5 000 пользователей.</span><span class="sxs-lookup"><span data-stu-id="f7030-110">Two Standard Edition server servers paired together for failover in case of disaster can support up to 5,000 users.</span></span> <span data-ttu-id="f7030-111">Вы не можете выдавать пул серверов стандартных выпусков (например, серверы переднего плана) в Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="f7030-111">You cannot pool Standard Edition servers like you can Front End Servers in Enterprise Edition.</span></span> <span data-ttu-id="f7030-112">Кроме того, база данных SQL Server, используемая в стандартном выпуске, — это размещенный сервер, на котором работает SQL Server Express, разработанный для обработки рабочих нагрузок сервера Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="f7030-112">Also, the SQL Server database that Standard Edition uses is a collocated server running SQL Server Express that is designed to handle Standard Edition server workloads.</span></span> <span data-ttu-id="f7030-113">Это не значит, что все роли должны располагаться на сервере Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="f7030-113">This is not to say that all roles must reside on a Standard Edition server.</span></span> <span data-ttu-id="f7030-114">Вы можете использовать изолированные серверы обновлений и пограничные серверы.</span><span class="sxs-lookup"><span data-stu-id="f7030-114">You can have stand-alone Mediation Servers and Edge Servers.</span></span> <span data-ttu-id="f7030-115">База данных SQL Server для централизованного управления хранилищем и целях Lync Server 2013 должны располагаться на сервере Standard Edition, расположенном на сервере с запущенным SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f7030-115">The SQL Server database for the Central Management store and for the purposes of Lync Server 2013 must reside on the Standard Edition server collocated with the server running SQL Server.</span></span> <span data-ttu-id="f7030-116">Сервер мониторинга и сервер архивации используют изолированный сервер с базой данных SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f7030-116">The Monitoring Server and Archiving Server use a stand-alone server with the SQL Server database.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

