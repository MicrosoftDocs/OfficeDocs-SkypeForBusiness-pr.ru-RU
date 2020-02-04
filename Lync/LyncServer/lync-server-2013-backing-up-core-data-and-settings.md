---
title: 'Lync Server 2013: резервное копирование основных данных и параметров'
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
ms.openlocfilehash: 4185c02bc85077b0f68ca76d83fd48203e0e5fd9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727919"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backing-up-core-data-and-settings-in-lync-server-2013"></a><span data-ttu-id="b3dca-102">Резервное копирование основных данных и параметров в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b3dca-102">Backing up core data and settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b3dca-103">_**Тема последнего изменения:** 2014-04-23_</span><span class="sxs-lookup"><span data-stu-id="b3dca-103">_**Topic Last Modified:** 2014-04-23_</span></span>

<span data-ttu-id="b3dca-104">Следующие процедуры используют командлеты командной консоли Lync Server для создания резервных файлов для параметров и данных основных служб.</span><span class="sxs-lookup"><span data-stu-id="b3dca-104">The following procedures use Lync Server Management Shell cmdlets to create backup files for settings and data for core services.</span></span> <span data-ttu-id="b3dca-105">Дополнительные сведения о средствах, используемых в этом разделе, в том числе о том, где они находятся, приведены [в статье требования к резервному копированию и восстановлению в Lync Server 2013: инструменты и разрешения](lync-server-2013-backup-and-restoration-requirements-tools-and-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="b3dca-105">For details about the tools used in this section, including where they are located, see [Backup and restoration requirements in Lync Server 2013: tools and permissions](lync-server-2013-backup-and-restoration-requirements-tools-and-permissions.md).</span></span> <span data-ttu-id="b3dca-106">Подробнее об архивации и мониторинге данных можно найти в разделе [резервное копирование архивации и мониторинг баз данных в Lync Server 2013](lync-server-2013-backing-up-archiving-and-monitoring-databases.md).</span><span class="sxs-lookup"><span data-stu-id="b3dca-106">For details about backing up Archiving and Monitoring data, see [Backing up Archiving and Monitoring databases in Lync Server 2013](lync-server-2013-backing-up-archiving-and-monitoring-databases.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b3dca-107">В этом разделе описывается создание резервной копии центрального хранилища, включая параметры и конфигурацию для архивации и мониторинга.</span><span class="sxs-lookup"><span data-stu-id="b3dca-107">The step in this section to back up the Central Management store includes the settings and configuration for Archiving and Monitoring.</span></span>



</div>

<span data-ttu-id="b3dca-108">Командлеты, описанные в этом разделе, можно выполнять локально или удаленно.</span><span class="sxs-lookup"><span data-stu-id="b3dca-108">You can run the cmdlets described in this section locally or remotely.</span></span>

<div>

## <a name="to-back-up-core-data-and-settings"></a><span data-ttu-id="b3dca-109">Создание резервной копии основных данных и параметров</span><span class="sxs-lookup"><span data-stu-id="b3dca-109">To back up core data and settings</span></span>

1.  <span data-ttu-id="b3dca-110">Войдите в свою учетную запись пользователя, которая входит в группу Рткуниверсалсерверадминс, на любой компьютер во внутренней среде.</span><span class="sxs-lookup"><span data-stu-id="b3dca-110">From a user account that is a member of the RTCUniversalServerAdmins group, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="b3dca-111">Чтобы сохранить резервные копии, созданные с помощью описанных ниже действий, создайте новую общую папку и обновите путь, на который ссылается **$BACKUP** , в новую общую папку.</span><span class="sxs-lookup"><span data-stu-id="b3dca-111">To store the backups you create in the following steps, create a new shared folder and update the path referenced by **$Backup** to the new shared folder.</span></span>

3.  <span data-ttu-id="b3dca-112">Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="b3dca-112">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

4.  <span data-ttu-id="b3dca-113">Создавайте резервную копию файла конфигурации центрального хранилища.</span><span class="sxs-lookup"><span data-stu-id="b3dca-113">Back up the Central Management store configuration file.</span></span> <span data-ttu-id="b3dca-114">В командной строке введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="b3dca-114">At the command line, type the following:</span></span>
    
        Export-CsConfiguration -FileName <path and file name for backup>
    
    <span data-ttu-id="b3dca-115">Например:</span><span class="sxs-lookup"><span data-stu-id="b3dca-115">For example:</span></span>
    
        Export-CsConfiguration -FileName "C:\Config.zip"
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b3dca-116">На этом этапе в файл экспортируются топология сервера Lync, политики и параметры конфигурации.</span><span class="sxs-lookup"><span data-stu-id="b3dca-116">This step exports your Lync Server topology, policies, and configuration settings to a file.</span></span> <span data-ttu-id="b3dca-117">Для резервного копирования данных топологии не требуется выполнять другие действия.</span><span class="sxs-lookup"><span data-stu-id="b3dca-117">No other step is required to backup topology data.</span></span>

    
    </div>

5.  <span data-ttu-id="b3dca-118">Скопируйте резервную копию файла конфигурации центрального хранилища для $Backup\\.</span><span class="sxs-lookup"><span data-stu-id="b3dca-118">Copy the backed-up Central Management store configuration file to $Backup\\.</span></span>

6.  <span data-ttu-id="b3dca-119">Резервное копирование данных службы сведений о расположении.</span><span class="sxs-lookup"><span data-stu-id="b3dca-119">Back up Location Information service data.</span></span> <span data-ttu-id="b3dca-120">В командной строке введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="b3dca-120">At the command line, type the following:</span></span>
    
        Export-CsLisConfiguration -FileName <path and file name for backup>
    
    <span data-ttu-id="b3dca-121">Например:</span><span class="sxs-lookup"><span data-stu-id="b3dca-121">For example:</span></span>
    
        Export-CsLisConfiguration -FileName "C:\E911Config.zip"

7.  <span data-ttu-id="b3dca-122">Скопируйте файл конфигурации службы сведений о расположении из резервной копии в\\$Backup.</span><span class="sxs-lookup"><span data-stu-id="b3dca-122">Copy the backed-up Location Information service configuration file to $Backup\\.</span></span>

8.  <span data-ttu-id="b3dca-123">Создавайте резервные копии данных пользователей для каждой серверной базы данных в пуле переднего плана и на каждом стандартном сервере выпуске.</span><span class="sxs-lookup"><span data-stu-id="b3dca-123">Back up user data on every back-end database of a Front End pool and every Standard Edition server.</span></span> <span data-ttu-id="b3dca-124">В командной строке введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="b3dca-124">At the command line, type the following:</span></span>
    
        Export-CsUserData -PoolFQDN <Fqdn> -FileName <String>
    
    <span data-ttu-id="b3dca-125">Например:</span><span class="sxs-lookup"><span data-stu-id="b3dca-125">For example:</span></span>
    
        Export-CsUserData -PoolFQDN "atl-cs-001.litwareinc.com" -FileName "C:\Logs\ExportedUserData.zip"

9.  <span data-ttu-id="b3dca-126">Скопируйте резервную копию файла пользователя в $Backup\\.</span><span class="sxs-lookup"><span data-stu-id="b3dca-126">Copy the backed up user file to $Backup\\.</span></span>

10. <span data-ttu-id="b3dca-127">В каждом пуле, где запущено приложение группы ответа, создавайте резервные копии конфигурации группы ответа.</span><span class="sxs-lookup"><span data-stu-id="b3dca-127">On every pool that runs the Response Group application, back up the Response Group configuration.</span></span> <span data-ttu-id="b3dca-128">Выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="b3dca-128">Do the following:</span></span>
    
    1.  <span data-ttu-id="b3dca-129">В командной строке введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="b3dca-129">At the command line, type:</span></span>
        
            Export-CsRgsConfiguration -Source "service:ApplicationServer:<pool FQDN>" -FileName <path and file name for backup>
        
        <span data-ttu-id="b3dca-130">Например:</span><span class="sxs-lookup"><span data-stu-id="b3dca-130">For example:</span></span>
        
            Export-CsRgsConfiguration -Source ApplicationServer:pool01.contoso.com -FileName C:\RgsConfiguration.zip

11. <span data-ttu-id="b3dca-131">Скопируйте резервную копию файла конфигурации группы ответов в $Backup\\.</span><span class="sxs-lookup"><span data-stu-id="b3dca-131">Copy the backed up Response Group configuration file to $Backup\\.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

