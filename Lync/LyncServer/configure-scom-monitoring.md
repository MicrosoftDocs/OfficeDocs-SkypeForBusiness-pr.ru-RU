---
title: Настройка мониторинга SCOM
description: Настройка мониторинга SCOM.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure SCOM monitoring
ms:assetid: 4003d225-2a33-448c-abd9-571750661140
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688033(v=OCS.15)
ms:contentKeyID: 49733624
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c93e10c705a1a1e08972d7534e00a33c472d23a3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542995"
---
# <a name="configure-scom-monitoring"></a><span data-ttu-id="87eee-103">Настройка мониторинга SCOM</span><span class="sxs-lookup"><span data-stu-id="87eee-103">Configure SCOM monitoring</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="87eee-104">_**Последнее изменение темы:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="87eee-104">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="87eee-105">После перехода на Microsoft Lync Server 2013 необходимо выполнить несколько задач, чтобы настроить Lync Server 2013 для работы с System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="87eee-105">After migrating to Microsoft Lync Server 2013, you must complete a few tasks to configure Lync Server 2013 to work with System Center Operations Manager.</span></span>

  - <span data-ttu-id="87eee-106">Применение обновлений Lync Server 2010 к серверу, выбранному для управления логикой центрального обнаружения.</span><span class="sxs-lookup"><span data-stu-id="87eee-106">Apply Lync Server 2010 updates to a server elected to manage the central discovery logic.</span></span>

  - <span data-ttu-id="87eee-107">Обновите раздел реестра потенциального сервера централизованного обнаружения.</span><span class="sxs-lookup"><span data-stu-id="87eee-107">Update the central discovery candidate server registry key.</span></span>

  - <span data-ttu-id="87eee-108">Настройте основной сервер управления System Center Operations Manager, чтобы переопределить узел центра обнаружения кандидатов.</span><span class="sxs-lookup"><span data-stu-id="87eee-108">Configure your primary System Center Operations Manager management server to override the candidate central discovery node.</span></span>

<span data-ttu-id="87eee-109">Инструкции по выполнению каждой задачи приведены ниже.</span><span class="sxs-lookup"><span data-stu-id="87eee-109">Instructions for carrying out each of these tasks are provided below.</span></span>

<span data-ttu-id="87eee-110">**Применение обновлений Lync Server 2010 к серверу, выбранному для управления логикой центрального обнаружения.**</span><span class="sxs-lookup"><span data-stu-id="87eee-110">**Apply Lync Server 2010 updates to a server elected to manage the central discovery logic.**</span></span>

1.  <span data-ttu-id="87eee-111">Выберите сервер, на котором установлены файлы агента System Center Operations Manager и который настроен как потенциальный узел обнаружения.</span><span class="sxs-lookup"><span data-stu-id="87eee-111">Elect a server that has the System Center Operations Manager agent files installed and is configured as a candidate discovery node.</span></span>

2.  <span data-ttu-id="87eee-112">Примените к этому серверу обновления Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="87eee-112">Apply Lync Server 2010 updates to this server.</span></span> <span data-ttu-id="87eee-113">Ознакомьтесь с разделом [Apply The Lync Server 2010 Updates](apply-lync-server-2010-updates.md).</span><span class="sxs-lookup"><span data-stu-id="87eee-113">See the topic [Apply Lync Server 2010 updates](apply-lync-server-2010-updates.md).</span></span>

<span data-ttu-id="87eee-114">**Обновите раздел реестра потенциального сервера централизованного обнаружения.**</span><span class="sxs-lookup"><span data-stu-id="87eee-114">**Update the central discovery candidate server registry key.**</span></span>

1.  <span data-ttu-id="87eee-115">На сервере, выбранном для управления логикой централизованного обнаружения, Откройте командное окно Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="87eee-115">On the server elected to manage the central discovery logic, open a Windows PowerShell command window.</span></span>

2.  <span data-ttu-id="87eee-116">В командной строке введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="87eee-116">At the command line, type the following:</span></span>
    
       ```PowerShell
        New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health"
       ```
    
       ```PowerShell
        New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health\CentralDiscoveryCandidate"
       ```
    
    <div class="">
    

    > [!NOTE]  
    > <span data-ttu-id="87eee-p102">При редактировании реестра может возникнуть ошибка выполнения команды, если раздел реестра уже существует. Эту ошибку можно игнорировать.</span><span class="sxs-lookup"><span data-stu-id="87eee-p102">Whenever you edit the registry, you may experience an error that the command failed if the registry key already exists. If you experience this, you can safely ignore the error.</span></span>

    
    </div>

<span data-ttu-id="87eee-119">**Настройка основного сервера управления System Center Operations Manager для переопределения узла-наблюдателя центра обнаружения кандидатов.**</span><span class="sxs-lookup"><span data-stu-id="87eee-119">**Configure your primary System Center Operations Manager management server to override the candidate central discovery watcher node.**</span></span>

1.  <span data-ttu-id="87eee-120">На компьютере с установленной консолью System Center Operations Manager разверните **Объекты пакета управления** и выберите **Обнаружение объектов**.</span><span class="sxs-lookup"><span data-stu-id="87eee-120">On a computer where the System Center Operations Manager console has been installed, expand **Management Pack Objects** and then select **Object Discoveries**.</span></span>

2.  <span data-ttu-id="87eee-121">Щелкните пункт **Изменение области...**</span><span class="sxs-lookup"><span data-stu-id="87eee-121">Click **Change Scope...**</span></span>

3.  <span data-ttu-id="87eee-122">на странице **Ориентация объектов пакета управления** выберите **LS Discovery Candidate**.</span><span class="sxs-lookup"><span data-stu-id="87eee-122">From the **Scope Management Pack Objects** page, select **LS Discovery Candidate**.</span></span>

4.  <span data-ttu-id="87eee-123">Переопределите **Эффективное значение LS Discovery Candidate**, указав имя сервера, выбранного ранее.</span><span class="sxs-lookup"><span data-stu-id="87eee-123">Override the **LS Discovery Candidate Effective Value** to the name of the candidate server elected in the earlier procedure.</span></span>

<span data-ttu-id="87eee-124">Наконец, чтобы завершить внесение изменений, перезапустите службу работоспособности на корневом сервере управления System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="87eee-124">Lastly, to finalize your changes, restart the health service on the System Center Operations Manager Root Management Server.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

