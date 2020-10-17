---
title: 'Lync Server 2013: выполнение и мониторинг резервных копий'
description: 'Lync Server 2013: выполнение и мониторинг резервных копий.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Performing and monitoring backups
ms:assetid: 2df415d4-0f37-460e-99ff-4035a9a2f445
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720912(v=OCS.15)
ms:contentKeyID: 63969595
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2fb8ce99e850f0918974be08eb10796ef1397225
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557235"
---
# <a name="performing-and-monitoring-backups-in-lync-server-2013"></a><span data-ttu-id="f6d76-103">Выполнение и мониторинг резервных копий в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f6d76-103">Performing and monitoring backups in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f6d76-104">_**Последнее изменение темы:** 2014-05-15_</span><span class="sxs-lookup"><span data-stu-id="f6d76-104">_**Topic Last Modified:** 2014-05-15_</span></span>

<span data-ttu-id="f6d76-105">Ваши бизнес-приоритеты должны учитывать спецификацию требований к резервному копированию и восстановлению в Организации.</span><span class="sxs-lookup"><span data-stu-id="f6d76-105">Your business priorities should drive the specification of backup and restoration requirements for your organization.</span></span> <span data-ttu-id="f6d76-106">Выполнение резервного копирования серверов и данных является первой строкой обороны при аварийном планировании.</span><span class="sxs-lookup"><span data-stu-id="f6d76-106">Performing backups of the servers and data is the first line of defense in planning for a disaster.</span></span>

<span data-ttu-id="f6d76-107">На компьютерах, на которых работают службы Lync Server 2013 или Server Roles, должна быть копия текущей топологии, текущих параметров конфигурации и текущих политик, прежде чем они смогут работать в своей роли.</span><span class="sxs-lookup"><span data-stu-id="f6d76-107">Computers that run Lync Server 2013 services or server roles must have a copy of the current topology, current configuration settings, and current policies before they can function in their appointed role.</span></span> <span data-ttu-id="f6d76-108">Lync Server несет ответственность за передачу этих сведений на каждый компьютер, которым она необходима.</span><span class="sxs-lookup"><span data-stu-id="f6d76-108">Lync Server is responsible for making sure that this information is passed along to each computer that needs it.</span></span>

<span data-ttu-id="f6d76-109">Командлеты **Export — CsConfiguration** и **Import CsConfiguration** используются для резервного копирования и восстановления топологии Lync Server, параметров конфигурации и политик во время обновления центрального хранилища управления.</span><span class="sxs-lookup"><span data-stu-id="f6d76-109">The **Export-CsConfiguration** and **Import-CsConfiguration** cmdlets are used to back up and restore your Lync Server topology, configuration settings, and policies during a Central Management store upgrade.</span></span> <span data-ttu-id="f6d76-110">Командлеты **Export – CsConfiguration** позволяют экспортировать данные в. ZIP-файл.</span><span class="sxs-lookup"><span data-stu-id="f6d76-110">The **Export-CsConfiguration** cmdlets enable you to export data to a .ZIP file.</span></span> <span data-ttu-id="f6d76-111">Затем можно использовать командлет **Import-CsConfiguration** для чтения. ZIP-файл и восстановите топологию, параметры конфигурации и политики в центральном хранилище управления.</span><span class="sxs-lookup"><span data-stu-id="f6d76-111">You can then use the **Import-CsConfiguration** cmdlet to read that .ZIP file and restore the topology, configuration settings, and policies to the Central Management store.</span></span> <span data-ttu-id="f6d76-112">После этого службы репликации Lync Server будут реплицировать восстановленные данные на другие компьютеры, на которых работают службы Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f6d76-112">After that, the replication services of Lync Server will replicate the restored information to other computers that are running Lync Server services.</span></span>

<span data-ttu-id="f6d76-113">Возможность экспорта и импорта данных конфигурации также используется при начальной настройке компьютеров, расположенных в сети периметра (например, на пограничных серверах).</span><span class="sxs-lookup"><span data-stu-id="f6d76-113">The ability to export and import configuration data is also used during the initial configuration of computers that are located in your perimeter network (for example, Edge Servers).</span></span> <span data-ttu-id="f6d76-114">При настройке компьютера в сети периметра необходимо сначала выполнить репликацию вручную с помощью командлетов CsConfiguration: необходимо экспортировать данные конфигурации с помощью командлета **Export — CsConfiguration** , а затем скопировать. ZIP-файл на компьютер в сети периметра.</span><span class="sxs-lookup"><span data-stu-id="f6d76-114">When configuring a computer in the perimeter network, you must first perform a manual replication using the CsConfiguration cmdlets: you must export the configuration data by using **Export-CsConfiguration** and then copy the .ZIP file to the computer in the perimeter network.</span></span> <span data-ttu-id="f6d76-115">После этого можно воспользоваться **Import-CsConfiguration** и параметром LocalStore для импорта данных.</span><span class="sxs-lookup"><span data-stu-id="f6d76-115">After that, you can use **Import-CsConfiguration** and the LocalStore parameter to import the data.</span></span> <span data-ttu-id="f6d76-116">Это необходимо сделать только один раз.</span><span class="sxs-lookup"><span data-stu-id="f6d76-116">You only have to do this one time.</span></span> <span data-ttu-id="f6d76-117">После этого репликация будет выполняться автоматически.</span><span class="sxs-lookup"><span data-stu-id="f6d76-117">After that, replication will occur automatically.</span></span>

<span data-ttu-id="f6d76-118">По умолчанию право на локальный запуск командлета **Export-CsConfiguration** имеют члены группы RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="f6d76-118">Who can run this cmdlet: By default, members of the following groups are authorized to run the **Export-CsConfiguration** cmdlet locally: RTCUniversalServerAdmins.</span></span> <span data-ttu-id="f6d76-119">Чтобы получить список всех ролей RBAC, назначен этот командлет (включая все самостоятельно созданные роли RBAC), выполните следующую команду из командной строки Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="f6d76-119">To return a list of all RBAC roles, this cmdlet is assigned to (including any custom RBAC roles that you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

`Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Export-CsConfiguration"}`

<span data-ttu-id="f6d76-120">Все резервные базы данных SQL Server 2012 должны быть резервными копиями в соответствии с рекомендациями [SQL](https://go.microsoft.com/fwlink/p/?linkid=290716).</span><span class="sxs-lookup"><span data-stu-id="f6d76-120">All SQL 2012 Back End databases should be backed up as per [SQL best practices](https://go.microsoft.com/fwlink/p/?linkid=290716).</span></span>

<span data-ttu-id="f6d76-121">Регулярное тестирование плана аварийного восстановления для инфраструктуры Lync Server 2013 следует выполнять в лабораторной среде, насколько это возможно.</span><span class="sxs-lookup"><span data-stu-id="f6d76-121">Regular testing of the Disaster Recovery Plan for your Lync Server 2013 infrastructure should be performed in a lab environment that mimics the production environment as closely as possible.</span></span> <span data-ttu-id="f6d76-122">Для получения дополнительных сведений о тестировании аварийного восстановления обратитесь к разделу Monthly Tasks.</span><span class="sxs-lookup"><span data-stu-id="f6d76-122">Refer to the Monthly Tasks for more information about Disaster Recovery Testing.</span></span>

<span data-ttu-id="f6d76-123">Обратите внимание на то, что частота резервного копирования может быть скорректирована в соответствии с целями точки восстановления и точки восстановления.</span><span class="sxs-lookup"><span data-stu-id="f6d76-123">Note that the backup frequency can be adjusted, based on your Restore Point and Recovery Point objectives.</span></span> <span data-ttu-id="f6d76-124">Рекомендуется регулярно периодически создавать моментальные снимки в течение дня.</span><span class="sxs-lookup"><span data-stu-id="f6d76-124">As a best practice, take regular, periodic snapshots throughout the day.</span></span> <span data-ttu-id="f6d76-125">Как правило, полное резервное копирование выполняется каждые 24 часа.</span><span class="sxs-lookup"><span data-stu-id="f6d76-125">Generally, you should perform full backups every 24 hours.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="f6d76-126">См. также</span><span class="sxs-lookup"><span data-stu-id="f6d76-126">See Also</span></span>


[<span data-ttu-id="f6d76-127">Import — CsConfiguration</span><span class="sxs-lookup"><span data-stu-id="f6d76-127">Import-CsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Import-CsConfiguration)  
[<span data-ttu-id="f6d76-128">Export — CsConfiguration</span><span class="sxs-lookup"><span data-stu-id="f6d76-128">Export-CsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Export-CsConfiguration)  
[<span data-ttu-id="f6d76-129">Рекомендации по SQL</span><span class="sxs-lookup"><span data-stu-id="f6d76-129">SQL best practices</span></span>](https://go.microsoft.com/fwlink/p/?linkid=290716)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

