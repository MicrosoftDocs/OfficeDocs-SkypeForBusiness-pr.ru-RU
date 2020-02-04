---
title: 'Lync Server 2013: выполнение и мониторинг резервных копий'
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
ms.openlocfilehash: 3181a266e5792d190186e9f09b2cab5852156cbe
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755269"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="performing-and-monitoring-backups-in-lync-server-2013"></a><span data-ttu-id="d64f7-102">Выполнение и мониторинг резервных копий в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d64f7-102">Performing and monitoring backups in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d64f7-103">_**Тема последнего изменения:** 2014-05-15_</span><span class="sxs-lookup"><span data-stu-id="d64f7-103">_**Topic Last Modified:** 2014-05-15_</span></span>

<span data-ttu-id="d64f7-104">Ваши бизнес-приоритеты должны заключать требования к резервному копированию и восстановлению для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="d64f7-104">Your business priorities should drive the specification of backup and restoration requirements for your organization.</span></span> <span data-ttu-id="d64f7-105">Резервное копирование серверов и данных является первой строкой обороны при планировании аварии.</span><span class="sxs-lookup"><span data-stu-id="d64f7-105">Performing backups of the servers and data is the first line of defense in planning for a disaster.</span></span>

<span data-ttu-id="d64f7-106">Компьютеры, на которых работают службы Lync Server 2013 или серверные роли, должны иметь копию текущей топологии, текущих параметров конфигурации и текущих политик, прежде чем они смогут работать в своей роли.</span><span class="sxs-lookup"><span data-stu-id="d64f7-106">Computers that run Lync Server 2013 services or server roles must have a copy of the current topology, current configuration settings, and current policies before they can function in their appointed role.</span></span> <span data-ttu-id="d64f7-107">Lync Server отвечает за то, что эти сведения передаются на каждый компьютер, на котором она требуется.</span><span class="sxs-lookup"><span data-stu-id="d64f7-107">Lync Server is responsible for making sure that this information is passed along to each computer that needs it.</span></span>

<span data-ttu-id="d64f7-108">Командлеты **Export-ксконфигуратион** и **Import-ксконфигуратион** используются для резервного копирования и восстановления топологии сервера Lync, параметров конфигурации и политик во время обновления центрального хранилища управления.</span><span class="sxs-lookup"><span data-stu-id="d64f7-108">The **Export-CsConfiguration** and **Import-CsConfiguration** cmdlets are used to back up and restore your Lync Server topology, configuration settings, and policies during a Central Management store upgrade.</span></span> <span data-ttu-id="d64f7-109">Командлеты **Export-ксконфигуратион** позволяют экспортировать данные в. ZIP-файл.</span><span class="sxs-lookup"><span data-stu-id="d64f7-109">The **Export-CsConfiguration** cmdlets enable you to export data to a .ZIP file.</span></span> <span data-ttu-id="d64f7-110">Затем можно использовать командлет **Import-ксконфигуратион** для чтения. ZIP-файл и восстановите топологию, параметры конфигурации и политики в хранилище Центрального управления.</span><span class="sxs-lookup"><span data-stu-id="d64f7-110">You can then use the **Import-CsConfiguration** cmdlet to read that .ZIP file and restore the topology, configuration settings, and policies to the Central Management store.</span></span> <span data-ttu-id="d64f7-111">После этого службы репликации Lync Server будут реплицировать восстановленные данные на другие компьютеры, на которых запущены службы Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d64f7-111">After that, the replication services of Lync Server will replicate the restored information to other computers that are running Lync Server services.</span></span>

<span data-ttu-id="d64f7-112">Возможность экспорта и импорта данных конфигурации также используется при начальной настройке компьютеров, расположенных в сети периметра (например, пограничных серверов).</span><span class="sxs-lookup"><span data-stu-id="d64f7-112">The ability to export and import configuration data is also used during the initial configuration of computers that are located in your perimeter network (for example, Edge Servers).</span></span> <span data-ttu-id="d64f7-113">При настройке компьютера в демилитаризованной зоне сначала необходимо выполнить репликацию вручную с помощью командлетов Ксконфигуратион: необходимо экспортировать данные конфигурации с помощью функции **Export-ксконфигуратион** , а затем скопировать. ZIP-файл на компьютер в сети периметра.</span><span class="sxs-lookup"><span data-stu-id="d64f7-113">When configuring a computer in the perimeter network, you must first perform a manual replication using the CsConfiguration cmdlets: you must export the configuration data by using **Export-CsConfiguration** and then copy the .ZIP file to the computer in the perimeter network.</span></span> <span data-ttu-id="d64f7-114">После этого вы можете импортировать данные с помощью параметров **Import-ксконфигуратион** и локалсторе.</span><span class="sxs-lookup"><span data-stu-id="d64f7-114">After that, you can use **Import-CsConfiguration** and the LocalStore parameter to import the data.</span></span> <span data-ttu-id="d64f7-115">Это можно сделать только один раз.</span><span class="sxs-lookup"><span data-stu-id="d64f7-115">You only have to do this one time.</span></span> <span data-ttu-id="d64f7-116">После этого репликация будет выполняться автоматически.</span><span class="sxs-lookup"><span data-stu-id="d64f7-116">After that, replication will occur automatically.</span></span>

<span data-ttu-id="d64f7-117">Кто может запустить этот командлет: по умолчанию членам указанных ниже групп разрешено локальное выполнение командлета **Export-ксконфигуратион** : рткуниверсалсерверадминс.</span><span class="sxs-lookup"><span data-stu-id="d64f7-117">Who can run this cmdlet: By default, members of the following groups are authorized to run the **Export-CsConfiguration** cmdlet locally: RTCUniversalServerAdmins.</span></span> <span data-ttu-id="d64f7-118">Чтобы возвратить список всех ролей RBAC, которому назначен этот командлет (в том числе любые пользовательские роли RBAC, созданные вами), выполните в командной строке Windows PowerShell следующую команду:</span><span class="sxs-lookup"><span data-stu-id="d64f7-118">To return a list of all RBAC roles, this cmdlet is assigned to (including any custom RBAC roles that you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

`Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Export-CsConfiguration"}`

<span data-ttu-id="d64f7-119">Все серверные базы данных SQL 2012 должны быть архивированы в соответствии с рекомендациями [SQL](http://go.microsoft.com/fwlink/p/?linkid=290716).</span><span class="sxs-lookup"><span data-stu-id="d64f7-119">All SQL 2012 Back End databases should be backed up as per [SQL best practices](http://go.microsoft.com/fwlink/p/?linkid=290716).</span></span>

<span data-ttu-id="d64f7-120">Регулярное тестирование плана аварийного восстановления для инфраструктуры Lync Server 2013 следует выполнять в лабораторной среде, насколько это возможно.</span><span class="sxs-lookup"><span data-stu-id="d64f7-120">Regular testing of the Disaster Recovery Plan for your Lync Server 2013 infrastructure should be performed in a lab environment that mimics the production environment as closely as possible.</span></span> <span data-ttu-id="d64f7-121">Дополнительные сведения об испытаниях с аварийным восстановлением можно найти в разделе ежемесячные задачи.</span><span class="sxs-lookup"><span data-stu-id="d64f7-121">Refer to the Monthly Tasks for more information about Disaster Recovery Testing.</span></span>

<span data-ttu-id="d64f7-122">Обратите внимание на то, что периодичность резервного копирования можно настроить в соответствии с целями точки восстановления и точки восстановления.</span><span class="sxs-lookup"><span data-stu-id="d64f7-122">Note that the backup frequency can be adjusted, based on your Restore Point and Recovery Point objectives.</span></span> <span data-ttu-id="d64f7-123">Рекомендуется регулярно периодически создавать моментальные снимки в течение дня.</span><span class="sxs-lookup"><span data-stu-id="d64f7-123">As a best practice, take regular, periodic snapshots throughout the day.</span></span> <span data-ttu-id="d64f7-124">Как правило, создание полных резервных копий выполняется каждые 24 часа.</span><span class="sxs-lookup"><span data-stu-id="d64f7-124">Generally, you should perform full backups every 24 hours.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="d64f7-125">См. также</span><span class="sxs-lookup"><span data-stu-id="d64f7-125">See Also</span></span>


[<span data-ttu-id="d64f7-126">Import-CsConfiguration</span><span class="sxs-lookup"><span data-stu-id="d64f7-126">Import-CsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Import-CsConfiguration)  
[<span data-ttu-id="d64f7-127">Export-CsConfiguration</span><span class="sxs-lookup"><span data-stu-id="d64f7-127">Export-CsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Export-CsConfiguration)  
[<span data-ttu-id="d64f7-128">Рекомендации по SQL</span><span class="sxs-lookup"><span data-stu-id="d64f7-128">SQL best practices</span></span>](http://go.microsoft.com/fwlink/p/?linkid=290716)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

