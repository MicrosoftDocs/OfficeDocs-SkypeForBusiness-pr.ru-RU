---
title: Обновление или переход на сервер Standard Edition
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Upgrade or update a Back End Server or Standard Edition server
ms:assetid: f95f8d3a-e039-484e-97bd-d727db21a12b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721942(v=OCS.15)
ms:contentKeyID: 49733879
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6b9d5ffba604ed5e32109ed5f1a2020b1e083b22
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849318"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="upgrade-or-update-a-back-end-server-or-standard-edition-server-in-lync-server-2013"></a><span data-ttu-id="5b174-102">Обновление или обновление серверного сервера или стандартного выпуска Standard в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5b174-102">Upgrade or update a Back End Server or Standard Edition server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5b174-103">_**Тема последнего изменения:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="5b174-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="5b174-104">В этой статье объясняется, как установить обновление на обратном сервере Enterprise Edition или стандартном сервере Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="5b174-104">This topic explains how to install an update on an Enterprise Edition Back End Server or a Standard Edition server.</span></span>

<span data-ttu-id="5b174-105">Если сервер выходит за частоту не менее 30 минут после его обновления, пользователи могут перейти в режим устойчивости.</span><span class="sxs-lookup"><span data-stu-id="5b174-105">If a Back End Server is down for at least 30 minutes while you are upgrading it, users may then go into resiliency mode.</span></span> <span data-ttu-id="5b174-106">После завершения обновления и повторного подключения серверов к внешним серверам из пула пользователи будут возвращены в полную функциональность.</span><span class="sxs-lookup"><span data-stu-id="5b174-106">When the upgrade is finished and the Back End Servers has again connected with the Front End Servers in the pool, users are returned to full functionality.</span></span> <span data-ttu-id="5b174-107">Если обновление занимает менее 30 минут, оно никак не затронет работу пользователей.</span><span class="sxs-lookup"><span data-stu-id="5b174-107">If the upgrade takes less than 30 minutes, users will not be affected.</span></span>

<div>

## <a name="to-update-a-back-end-server-or-standard-edition-server"></a><span data-ttu-id="5b174-108">Обновление внутреннего сервера или сервера Standard Edition</span><span class="sxs-lookup"><span data-stu-id="5b174-108">To update a back end server or Standard Edition server</span></span>

1.  <span data-ttu-id="5b174-109">Выполните вход на обновляемый сервер в качестве члена роли CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="5b174-109">Log on to the server you are upgrading as a member of the CsAdministrator role.</span></span>

2.  <span data-ttu-id="5b174-110">Загрузите обновление и извлеките его на локальный жесткий диск.</span><span class="sxs-lookup"><span data-stu-id="5b174-110">Download the update and extract it to the local hard disk.</span></span>

3.  <span data-ttu-id="5b174-111">Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="5b174-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

4.  <span data-ttu-id="5b174-112">Остановите службы Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5b174-112">Stop Lync Server services.</span></span> <span data-ttu-id="5b174-113">В командной строке выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="5b174-113">At the command line, type:</span></span>
    
        Stop-CsWindowsService

5.  <span data-ttu-id="5b174-114">Остановите службу Интернета.</span><span class="sxs-lookup"><span data-stu-id="5b174-114">Stop the World Wide Web service.</span></span> <span data-ttu-id="5b174-115">В командной строке выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="5b174-115">At the command line, type:</span></span>
    
        net stop w3svc

6.  <span data-ttu-id="5b174-116">Закройте все окна команд Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="5b174-116">Close all Lync Server Management Shell windows.</span></span>

7.  <span data-ttu-id="5b174-117">Установите обновление.</span><span class="sxs-lookup"><span data-stu-id="5b174-117">Install the update.</span></span>

8.  <span data-ttu-id="5b174-118">Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="5b174-118">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

9.  <span data-ttu-id="5b174-119">Снова остановите службы Lync Server, чтобы перехватить сборки глобального кэша сборок (GAC) – d.</span><span class="sxs-lookup"><span data-stu-id="5b174-119">Stop Lync Server services again to catch Global Assembly Cache (GAC) –d assemblies.</span></span> <span data-ttu-id="5b174-120">В командной строке выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="5b174-120">At the command line, type:</span></span>
    
        Stop-CsWindowsService

10. <span data-ttu-id="5b174-121">Перезапустите службу Интернета.</span><span class="sxs-lookup"><span data-stu-id="5b174-121">Restart the World Wide Web service.</span></span> <span data-ttu-id="5b174-122">В командной строке выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="5b174-122">At the command line, type:</span></span>
    
        net start w3svc

11. <span data-ttu-id="5b174-123">Примените изменения, внесенные Линксерверупдатеинсталлер. exe, в базу данных SQL Server, выполнив одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="5b174-123">Apply the changes made by LyncServerUpdateInstaller.exe to the SQL Server databases by doing one of the following:</span></span>
    
      - <span data-ttu-id="5b174-124">Если это сервер выпуска Enterprise Edition и на нем нет размещенных на нем баз данных, таких как архивация и мониторинг баз данных, введите в командной строке следующую команду:</span><span class="sxs-lookup"><span data-stu-id="5b174-124">If this is an Enterprise Edition Back End Server and there are no collocated databases on this server, such as Archiving or Monitoring databases, then type the following at a command line:</span></span>
        
            Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>
    
      - <span data-ttu-id="5b174-125">Если этот сервер выпуска Enterprise Edition и на нем есть размещенные на сервере базы данных, введите в командной строке следующее:</span><span class="sxs-lookup"><span data-stu-id="5b174-125">If this is an Enterprise Edition Back End Server and there are collocated databases on this server, then type the following at a command line:</span></span>
        
            Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>  -ExcludeCollocatedStores
    
      - <span data-ttu-id="5b174-126">Если это сервер Standard Edition, введите в командной строке следующее:</span><span class="sxs-lookup"><span data-stu-id="5b174-126">If this is an Standard Edition server, type the following at a command line:</span></span>
        
            Install-CsDatabase -Update -LocalDatabases

</div>

</div>

<span> </span>

</div>

</div>

</div>

