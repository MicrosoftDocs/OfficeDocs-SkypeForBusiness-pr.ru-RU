---
title: 'Lync Server 2013: состояние репликации центрального хранилища управления'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Central management store replication status
ms:assetid: f514f88d-986b-4e45-b79b-e04a7616c1fe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720926(v=OCS.15)
ms:contentKeyID: 63969663
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eb72b44cf53a33b3c0d7a79f6adda8870fe37254
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135356"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="central-management-store-replication-status-in-lync-server-2013"></a><span data-ttu-id="f6efc-102">Состояние репликации центрального хранилища управления в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f6efc-102">Central management store replication status in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f6efc-103">_**Последнее изменение темы:** 2015-01-26_</span><span class="sxs-lookup"><span data-stu-id="f6efc-103">_**Topic Last Modified:** 2015-01-26_</span></span>

<span data-ttu-id="f6efc-104">Когда администратор вносит изменения в Lync Server (например, когда администратор создает новую политику голосовой связи или изменяет параметры конфигурации сервера адресной книги), она записывается в хранилище центрального хранилища управления.</span><span class="sxs-lookup"><span data-stu-id="f6efc-104">When an administrator makes a change of some kind to Lync Server (for example, when an administrator creates a new voice policy or changes the Address Book Server configuration settings) that change is recorded in the Central Management store.</span></span> <span data-ttu-id="f6efc-105">В свою очередь, это изменение необходимо реплицировать на все компьютеры, на которых выполняются службы или роли сервера Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f6efc-105">In turn, the change must then be replicated to all the computers that are running Lync Server services or server roles.</span></span>

<span data-ttu-id="f6efc-106">Для репликации данных главный репликатор (работающий на центральном сервере управления) создает моментальный снимок измененных данных конфигурации.</span><span class="sxs-lookup"><span data-stu-id="f6efc-106">To replicate data, the Master Replicator (running on the Central Management Server) creates a snapshot of the changed configuration data.</span></span> <span data-ttu-id="f6efc-107">Затем копия этого снимка отправляется на каждый компьютер, на котором выполняются службы или роли сервера Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f6efc-107">A copy of this snapshot is then sent to each computer that is running Lync Server services or server roles.</span></span> <span data-ttu-id="f6efc-108">На этих компьютерах агент репликации получает моментальный снимок и передает измененные данные.</span><span class="sxs-lookup"><span data-stu-id="f6efc-108">On those computers, a replication agent receives the snapshot and uploads the changed data.</span></span> <span data-ttu-id="f6efc-109">Затем агент отправляет главный репликатор сообщение, сообщающее о последнем состоянии репликации.</span><span class="sxs-lookup"><span data-stu-id="f6efc-109">The agent then sends the Master Replicator a message reporting the latest replication status.</span></span>

<span data-ttu-id="f6efc-110">Командлет Get-CsManagementStoreReplicationStatus позволяет проверить состояние репликации для всех (или всех) компьютеров Lync Server в Организации.</span><span class="sxs-lookup"><span data-stu-id="f6efc-110">The Get-CsManagementStoreReplicationStatus cmdlet enables you to verify the replication status for any (or all) of the Lync Server computers in your organization.</span></span>

<span data-ttu-id="f6efc-111">Кто может выполнить этот командлет?</span><span class="sxs-lookup"><span data-stu-id="f6efc-111">Who can run this cmdlet?</span></span> <span data-ttu-id="f6efc-112">По умолчанию члены следующих групп авторизованы для локального запуска командлета Get – CsManagementStoreReplicationStatus: RTCUniversalUserAdmins, RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="f6efc-112">By default, members of the following groups are authorized to run the Get-CsManagementStoreReplicationStatus cmdlet locally: RTCUniversalUserAdmins, RTCUniversalServerAdmins.</span></span>

<span data-ttu-id="f6efc-113">Чтобы получить список всех ролей RBAC, которым назначен этот командлет (включая все самостоятельно созданные роли RBAC), выполните следующую команду в командной консоли Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="f6efc-113">To return a list of all RBAC roles this cmdlet was assigned to (including any custom RBAC roles that you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Get-CsManagementStoreReplicationStatus"}

<div>

## <a name="see-also"></a><span data-ttu-id="f6efc-114">См. также</span><span class="sxs-lookup"><span data-stu-id="f6efc-114">See Also</span></span>


[<span data-ttu-id="f6efc-115">Get — CsManagementStoreReplicationStatus</span><span class="sxs-lookup"><span data-stu-id="f6efc-115">Get-CsManagementStoreReplicationStatus</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsManagementStoreReplicationStatus)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

