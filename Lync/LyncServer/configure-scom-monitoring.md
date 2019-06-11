---
title: Настройка мониторинга SCOM
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Configure SCOM monitoring
ms:assetid: 4003d225-2a33-448c-abd9-571750661140
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688033(v=OCS.15)
ms:contentKeyID: 49733624
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b73bbf1ae1a487f8e6dcf8560e37cf5c7a73ba04
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841087"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-scom-monitoring"></a><span data-ttu-id="53e1d-102">Настройка мониторинга SCOM</span><span class="sxs-lookup"><span data-stu-id="53e1d-102">Configure SCOM monitoring</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="53e1d-103">_**Тема последнего изменения:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="53e1d-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="53e1d-104">После перехода на Microsoft Lync Server 2013 необходимо выполнить несколько задач, чтобы настроить Lync Server 2013 для работы с System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="53e1d-104">After migrating to Microsoft Lync Server 2013, you must complete a few tasks to configure Lync Server 2013 to work with System Center Operations Manager.</span></span>

  - <span data-ttu-id="53e1d-105">Примените к серверу Lync Server 2010 обновлений, выбранных для управления логикой центрального обнаружения.</span><span class="sxs-lookup"><span data-stu-id="53e1d-105">Apply Lync Server 2010 updates to a server elected to manage the central discovery logic.</span></span>

  - <span data-ttu-id="53e1d-106">Обновите раздел реестра для основного сервера поиска кандидатов.</span><span class="sxs-lookup"><span data-stu-id="53e1d-106">Update the central discovery candidate server registry key.</span></span>

  - <span data-ttu-id="53e1d-107">Настройка основного сервера System Center Operations Manager для переопределения узла центра обнаружения кандидатов.</span><span class="sxs-lookup"><span data-stu-id="53e1d-107">Configure your primary System Center Operations Manager management server to override the candidate central discovery node.</span></span>

<span data-ttu-id="53e1d-108">Ниже приведены инструкции по переносу каждой из этих задач.</span><span class="sxs-lookup"><span data-stu-id="53e1d-108">Instructions for carrying out each of these tasks are provided below.</span></span>

<span data-ttu-id="53e1d-109">**Примените к серверу Lync Server 2010 обновлений, выбранных для управления логикой центрального обнаружения.**</span><span class="sxs-lookup"><span data-stu-id="53e1d-109">**Apply Lync Server 2010 updates to a server elected to manage the central discovery logic.**</span></span>

1.  <span data-ttu-id="53e1d-110">Выровняйте сервер, на котором установлены файлы агента System Center Operations Manager и настроен как узел обнаружения кандидатов.</span><span class="sxs-lookup"><span data-stu-id="53e1d-110">Elect a server that has the System Center Operations Manager agent files installed and is configured as a candidate discovery node.</span></span>

2.  <span data-ttu-id="53e1d-111">Примените к этому серверу обновления Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="53e1d-111">Apply Lync Server 2010 updates to this server.</span></span> <span data-ttu-id="53e1d-112">Ознакомьтесь с разделом [применение обновлений Lync Server 2010](apply-lync-server-2010-updates.md).</span><span class="sxs-lookup"><span data-stu-id="53e1d-112">See the topic [Apply Lync Server 2010 updates](apply-lync-server-2010-updates.md).</span></span>

<span data-ttu-id="53e1d-113">**Обновите раздел реестра для основного сервера поиска кандидатов.**</span><span class="sxs-lookup"><span data-stu-id="53e1d-113">**Update the central discovery candidate server registry key.**</span></span>

1.  <span data-ttu-id="53e1d-114">На сервере, выбранном для управления логикой центрального обнаружения, Откройте командное окно Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="53e1d-114">On the server elected to manage the central discovery logic, open a Windows PowerShell command window.</span></span>

2.  <span data-ttu-id="53e1d-115">В командной строке введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="53e1d-115">At the command line, type the following:</span></span>
    
       ```
        New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health"
       ```
    
       ```
        New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health\CentralDiscoveryCandidate"
       ```
    
    <div class="">
    

    > [!NOTE]  
    > <span data-ttu-id="53e1d-116">При внесении изменений в реестр может возникнуть сообщение о том, что команда завершилась сбоем, если раздел реестра уже существует.</span><span class="sxs-lookup"><span data-stu-id="53e1d-116">Whenever you edit the registry, you may experience an error that the command failed if the registry key already exists.</span></span> <span data-ttu-id="53e1d-117">Если вы столкнетесь с этим, вы можете спокойно проигнорировать ошибку.</span><span class="sxs-lookup"><span data-stu-id="53e1d-117">If you experience this, you can safely ignore the error.</span></span>

    
    </div>

<span data-ttu-id="53e1d-118">**Настройка основного сервера System Center Operations Manager для переопределения узла наблюдения за центральным обнаружением.**</span><span class="sxs-lookup"><span data-stu-id="53e1d-118">**Configure your primary System Center Operations Manager management server to override the candidate central discovery watcher node.**</span></span>

1.  <span data-ttu-id="53e1d-119">На компьютере с установленной консолью System Center Operations Manager разверните **объект пакета управления** , а затем выберите пункт **Обнаружение объектов**.</span><span class="sxs-lookup"><span data-stu-id="53e1d-119">On a computer where the System Center Operations Manager console has been installed, expand **Management Pack Objects** and then select **Object Discoveries**.</span></span>

2.  <span data-ttu-id="53e1d-120">Выберите команду **изменить область...**</span><span class="sxs-lookup"><span data-stu-id="53e1d-120">Click **Change Scope...**</span></span>

3.  <span data-ttu-id="53e1d-121">На странице " **объекты пакета управления областью** " выберите **кандидат на обнаружение Ls**.</span><span class="sxs-lookup"><span data-stu-id="53e1d-121">From the **Scope Management Pack Objects** page, select **LS Discovery Candidate**.</span></span>

4.  <span data-ttu-id="53e1d-122">Переопределение **действующего значения-кандидата на обнаружение Ls** на имя сервера-кандидата, выбранное в предыдущей процедуре.</span><span class="sxs-lookup"><span data-stu-id="53e1d-122">Override the **LS Discovery Candidate Effective Value** to the name of the candidate server elected in the earlier procedure.</span></span>

<span data-ttu-id="53e1d-123">Наконец, чтобы завершить изменения, перезапустите службу работоспособности на корневом сервере управления System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="53e1d-123">Lastly, to finalize your changes, restart the health service on the System Center Operations Manager Root Management Server.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

