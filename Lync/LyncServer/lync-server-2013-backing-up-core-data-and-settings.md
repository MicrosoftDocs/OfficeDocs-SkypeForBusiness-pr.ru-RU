---
title: 'Lync Server 2013: резервное копирование основных данных и параметров'
description: 'Lync Server 2013: резервное копирование основных данных и параметров.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Backing up core data and settings
ms:assetid: 278bc95a-7b8d-4e01-a872-a844830459de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202170(v=OCS.15)
ms:contentKeyID: 51541452
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 637eeb950a3b8380f6e756f46a5083f51b5d7e1f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543745"
---
# <a name="backing-up-core-data-and-settings-in-lync-server-2013"></a><span data-ttu-id="a0feb-103">Резервное копирование основных данных и параметров в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a0feb-103">Backing up core data and settings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a0feb-104">_**Последнее изменение темы:** 2014-04-23_</span><span class="sxs-lookup"><span data-stu-id="a0feb-104">_**Topic Last Modified:** 2014-04-23_</span></span>

<span data-ttu-id="a0feb-105">В следующих процедурах используются командлеты командной консоли Lync Server для создания файлов резервных копий параметров и данных для основных служб.</span><span class="sxs-lookup"><span data-stu-id="a0feb-105">The following procedures use Lync Server Management Shell cmdlets to create backup files for settings and data for core services.</span></span> <span data-ttu-id="a0feb-106">Дополнительные сведения о средствах, используемых в этом разделе, в том числе о том, где они находятся, приведены [в статье требования к резервному копированию и восстановлению в Lync Server 2013: Tools and Permissions](lync-server-2013-backup-and-restoration-requirements-tools-and-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="a0feb-106">For details about the tools used in this section, including where they are located, see [Backup and restoration requirements in Lync Server 2013: tools and permissions](lync-server-2013-backup-and-restoration-requirements-tools-and-permissions.md).</span></span> <span data-ttu-id="a0feb-107">Сведения о резервном копировании данных архивации и мониторинга приведены [в статье резервное копирование баз данных архивации и мониторинга в Lync Server 2013](lync-server-2013-backing-up-archiving-and-monitoring-databases.md).</span><span class="sxs-lookup"><span data-stu-id="a0feb-107">For details about backing up Archiving and Monitoring data, see [Backing up Archiving and Monitoring databases in Lync Server 2013](lync-server-2013-backing-up-archiving-and-monitoring-databases.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a0feb-108">Шаг в этом разделе для резервного копирования центрального хранилища управления включает параметры и конфигурацию для архивации и мониторинга.</span><span class="sxs-lookup"><span data-stu-id="a0feb-108">The step in this section to back up the Central Management store includes the settings and configuration for Archiving and Monitoring.</span></span>



</div>

<span data-ttu-id="a0feb-109">Вы можете выполнить командлеты, описанные в этом разделе, локально или удаленно.</span><span class="sxs-lookup"><span data-stu-id="a0feb-109">You can run the cmdlets described in this section locally or remotely.</span></span>

<div>

## <a name="to-back-up-core-data-and-settings"></a><span data-ttu-id="a0feb-110">Резервное копирование основных данных и параметров</span><span class="sxs-lookup"><span data-stu-id="a0feb-110">To back up core data and settings</span></span>

1.  <span data-ttu-id="a0feb-111">Из учетной записи пользователя, входящей в группу RTCUniversalServerAdmins, войдите на любой компьютер во внутреннем развертывании.</span><span class="sxs-lookup"><span data-stu-id="a0feb-111">From a user account that is a member of the RTCUniversalServerAdmins group, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="a0feb-112">Чтобы сохранить резервные копии, созданные в следующих шагах, создайте новую общую папку и обновите путь, на который ссылается **$BACKUP** , на новую общую папку.</span><span class="sxs-lookup"><span data-stu-id="a0feb-112">To store the backups you create in the following steps, create a new shared folder and update the path referenced by **$Backup** to the new shared folder.</span></span>

3.  <span data-ttu-id="a0feb-113">Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="a0feb-113">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

4.  <span data-ttu-id="a0feb-114">Выполните резервное копирование файла конфигурации центрального хранилища управления.</span><span class="sxs-lookup"><span data-stu-id="a0feb-114">Back up the Central Management store configuration file.</span></span> <span data-ttu-id="a0feb-115">В командной строке введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="a0feb-115">At the command line, type the following:</span></span>
    
        Export-CsConfiguration -FileName <path and file name for backup>
    
    <span data-ttu-id="a0feb-116">Пример:</span><span class="sxs-lookup"><span data-stu-id="a0feb-116">For example:</span></span>
    
        Export-CsConfiguration -FileName "C:\Config.zip"
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a0feb-117">На этом этапе выполняется экспорт топологии, политик и параметров конфигурации Lync Server в файл.</span><span class="sxs-lookup"><span data-stu-id="a0feb-117">This step exports your Lync Server topology, policies, and configuration settings to a file.</span></span> <span data-ttu-id="a0feb-118">Для резервного копирования данных топологии не требуется никаких других действий.</span><span class="sxs-lookup"><span data-stu-id="a0feb-118">No other step is required to backup topology data.</span></span>

    
    </div>

5.  <span data-ttu-id="a0feb-119">Скопируйте файл конфигурации резервного хранилища центрального хранилища управления в $Backup \\ .</span><span class="sxs-lookup"><span data-stu-id="a0feb-119">Copy the backed-up Central Management store configuration file to $Backup\\.</span></span>

6.  <span data-ttu-id="a0feb-120">Резервное копирование данных службы сведений о местоположении.</span><span class="sxs-lookup"><span data-stu-id="a0feb-120">Back up Location Information service data.</span></span> <span data-ttu-id="a0feb-121">В командной строке введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="a0feb-121">At the command line, type the following:</span></span>
    
        Export-CsLisConfiguration -FileName <path and file name for backup>
    
    <span data-ttu-id="a0feb-122">Пример:</span><span class="sxs-lookup"><span data-stu-id="a0feb-122">For example:</span></span>
    
        Export-CsLisConfiguration -FileName "C:\E911Config.zip"

7.  <span data-ttu-id="a0feb-123">Скопируйте файл конфигурации службы сведений о расположении резервной копии в $Backup \\ .</span><span class="sxs-lookup"><span data-stu-id="a0feb-123">Copy the backed-up Location Information service configuration file to $Backup\\.</span></span>

8.  <span data-ttu-id="a0feb-124">Создайте резервную копию пользовательских данных для каждой внутренней базы данных интерфейсного пула и каждого сервера Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="a0feb-124">Back up user data on every back-end database of a Front End pool and every Standard Edition server.</span></span> <span data-ttu-id="a0feb-125">В командной строке введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="a0feb-125">At the command line, type the following:</span></span>
    
        Export-CsUserData -PoolFQDN <Fqdn> -FileName <String>
    
    <span data-ttu-id="a0feb-126">Пример:</span><span class="sxs-lookup"><span data-stu-id="a0feb-126">For example:</span></span>
    
        Export-CsUserData -PoolFQDN "atl-cs-001.litwareinc.com" -FileName "C:\Logs\ExportedUserData.zip"

9.  <span data-ttu-id="a0feb-127">Скопируйте резервную копию файла пользователя в $Backup \\ .</span><span class="sxs-lookup"><span data-stu-id="a0feb-127">Copy the backed up user file to $Backup\\.</span></span>

10. <span data-ttu-id="a0feb-128">В каждом пуле, где выполняется приложение группы ответа, создайте резервную копию конфигурации группы ответа.</span><span class="sxs-lookup"><span data-stu-id="a0feb-128">On every pool that runs the Response Group application, back up the Response Group configuration.</span></span> <span data-ttu-id="a0feb-129">Выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="a0feb-129">Do the following:</span></span>
    
    1.  <span data-ttu-id="a0feb-130">В командной строке введите следующую команду.</span><span class="sxs-lookup"><span data-stu-id="a0feb-130">At the command line, type:</span></span>
        
            Export-CsRgsConfiguration -Source "service:ApplicationServer:<pool FQDN>" -FileName <path and file name for backup>
        
        <span data-ttu-id="a0feb-131">Пример:</span><span class="sxs-lookup"><span data-stu-id="a0feb-131">For example:</span></span>
        
            Export-CsRgsConfiguration -Source ApplicationServer:pool01.contoso.com -FileName C:\RgsConfiguration.zip

11. <span data-ttu-id="a0feb-132">Скопируйте файл конфигурации группы ответа с резервной копией в $Backup \\ .</span><span class="sxs-lookup"><span data-stu-id="a0feb-132">Copy the backed up Response Group configuration file to $Backup\\.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

