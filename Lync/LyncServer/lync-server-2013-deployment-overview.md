---
title: 'Lync Server 2013: Общие сведения о развертывании'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment overview
ms:assetid: da67555e-f410-4c37-9996-d511f37da8d1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205305(v=OCS.15)
ms:contentKeyID: 48185555
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0b21d6c6a977fbb94a54114753f32c022aa5e713
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213801"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deployment-overview-for-lync-server-2013"></a><span data-ttu-id="99c28-102">Обзор развертывания для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="99c28-102">Deployment overview for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="99c28-103">_**Последнее изменение темы:** 2013-03-12_</span><span class="sxs-lookup"><span data-stu-id="99c28-103">_**Topic Last Modified:** 2013-03-12_</span></span>

<span data-ttu-id="99c28-104">Основное различие между Lync Server 2013 Enterprise Edition и Lync Server 2013 Standard Edition заключается в том, что стандартный выпуск не поддерживает функции высокого уровня доступности, включенные в Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="99c28-104">The main difference between Lync Server 2013 Enterprise Edition and Lync Server 2013 Standard Edition is that Standard Edition does not support the high availability features included with Enterprise Edition.</span></span> <span data-ttu-id="99c28-105">Для обеспечения высокой доступности необходимо развернуть несколько серверов переднего плана в пул, а затем можно создать зеркальный набор для сервера, на котором работает SQL Server.</span><span class="sxs-lookup"><span data-stu-id="99c28-105">For high availability, you need to deploy multiple Front End Servers to a pool and then you can mirror the server running SQL Server.</span></span> <span data-ttu-id="99c28-106">В Enterprise Edition можно выбрать размещение или определение отдельного сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="99c28-106">With Enterprise Edition you can choose to collocate or define a stand-alone Mediation Server.</span></span> <span data-ttu-id="99c28-107">Сервер мониторинга и сервер архивации могут использовать изолированный сервер, на котором работает SQL Server.</span><span class="sxs-lookup"><span data-stu-id="99c28-107">The Monitoring Server and Archiving Server can use a stand-alone server running SQL Server.</span></span> <span data-ttu-id="99c28-108">Или они могут иметь экземпляры SQL Server, запущенные на сервере баз данных, для серверов и пулов переднего плана.</span><span class="sxs-lookup"><span data-stu-id="99c28-108">Or, they can have instances of SQL Server running on the database server for the Front End Servers and pools.</span></span>

<span data-ttu-id="99c28-109">Серверы, на которых работает Lync Server 2013 Standard Edition, предназначены для небольших организаций и удаленных расположений, которые географически удаляются из основного развертывания Организации.</span><span class="sxs-lookup"><span data-stu-id="99c28-109">Servers running Lync Server 2013 Standard Edition are intended for smaller organizations and remote locations, which are geographically removed from the organization’s main deployment.</span></span> <span data-ttu-id="99c28-110">Два сервера Standard Edition, Объединенных для отработки отказа в случае аварии, могут поддерживать до 5 000 пользователей.</span><span class="sxs-lookup"><span data-stu-id="99c28-110">Two Standard Edition server servers paired together for failover in case of disaster can support up to 5,000 users.</span></span> <span data-ttu-id="99c28-111">Вы не можете осуществлять объединение серверов Standard Edition, например серверов переднего плана в Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="99c28-111">You cannot pool Standard Edition servers like you can Front End Servers in Enterprise Edition.</span></span> <span data-ttu-id="99c28-112">Кроме того, база данных SQL Server, используемая в стандартном выпуске, — это совмещенный сервер, на котором работает SQL Server Express, предназначенный для обработки рабочих нагрузок сервера Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="99c28-112">Also, the SQL Server database that Standard Edition uses is a collocated server running SQL Server Express that is designed to handle Standard Edition server workloads.</span></span> <span data-ttu-id="99c28-113">Это не означает, что все роли должны располагаться на сервере Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="99c28-113">This is not to say that all roles must reside on a Standard Edition server.</span></span> <span data-ttu-id="99c28-114">У вас могут быть изолированные серверы-посредники и пограничные серверы.</span><span class="sxs-lookup"><span data-stu-id="99c28-114">You can have stand-alone Mediation Servers and Edge Servers.</span></span> <span data-ttu-id="99c28-115">База данных SQL Server для центрального хранилища управления и в целях Lync Server 2013 должна размещаться на сервере Standard Edition, размещенном на сервере SQL Server.</span><span class="sxs-lookup"><span data-stu-id="99c28-115">The SQL Server database for the Central Management store and for the purposes of Lync Server 2013 must reside on the Standard Edition server collocated with the server running SQL Server.</span></span> <span data-ttu-id="99c28-116">Сервер мониторинга и сервер архивации используют изолированный сервер с базой данных SQL Server.</span><span class="sxs-lookup"><span data-stu-id="99c28-116">The Monitoring Server and Archiving Server use a stand-alone server with the SQL Server database.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

