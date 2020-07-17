---
title: Настройка мониторинга SCOM
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
ms.openlocfilehash: 95bc54defed596dfa8a8d801908b281abf06ead3
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754527"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-scom-monitoring"></a><span data-ttu-id="8b154-102">Настройка мониторинга SCOM</span><span class="sxs-lookup"><span data-stu-id="8b154-102">Configure SCOM monitoring</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8b154-103">_**Последнее изменение темы:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="8b154-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="8b154-104">После перехода на Microsoft Lync Server 2013 необходимо выполнить несколько задач, чтобы настроить Lync Server 2013 для работы с System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="8b154-104">After migrating to Microsoft Lync Server 2013, you must complete a few tasks to configure Lync Server 2013 to work with System Center Operations Manager.</span></span>

  - <span data-ttu-id="8b154-105">Применение обновлений Lync Server 2010 к серверу, выбранному для управления логикой центрального обнаружения.</span><span class="sxs-lookup"><span data-stu-id="8b154-105">Apply Lync Server 2010 updates to a server elected to manage the central discovery logic.</span></span>

  - <span data-ttu-id="8b154-106">Обновите раздел реестра потенциального сервера централизованного обнаружения.</span><span class="sxs-lookup"><span data-stu-id="8b154-106">Update the central discovery candidate server registry key.</span></span>

  - <span data-ttu-id="8b154-107">Настройте основной сервер управления System Center Operations Manager, чтобы переопределить узел центра обнаружения кандидатов.</span><span class="sxs-lookup"><span data-stu-id="8b154-107">Configure your primary System Center Operations Manager management server to override the candidate central discovery node.</span></span>

<span data-ttu-id="8b154-108">Инструкции по выполнению каждой задачи приведены ниже.</span><span class="sxs-lookup"><span data-stu-id="8b154-108">Instructions for carrying out each of these tasks are provided below.</span></span>

<span data-ttu-id="8b154-109">**Применение обновлений Lync Server 2010 к серверу, выбранному для управления логикой центрального обнаружения.**</span><span class="sxs-lookup"><span data-stu-id="8b154-109">**Apply Lync Server 2010 updates to a server elected to manage the central discovery logic.**</span></span>

1.  <span data-ttu-id="8b154-110">Выберите сервер, на котором установлены файлы агента System Center Operations Manager и который настроен как потенциальный узел обнаружения.</span><span class="sxs-lookup"><span data-stu-id="8b154-110">Elect a server that has the System Center Operations Manager agent files installed and is configured as a candidate discovery node.</span></span>

2.  <span data-ttu-id="8b154-111">Примените к этому серверу обновления Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="8b154-111">Apply Lync Server 2010 updates to this server.</span></span> <span data-ttu-id="8b154-112">Ознакомьтесь с разделом [Apply The Lync Server 2010 Updates](apply-lync-server-2010-updates.md).</span><span class="sxs-lookup"><span data-stu-id="8b154-112">See the topic [Apply Lync Server 2010 updates](apply-lync-server-2010-updates.md).</span></span>

<span data-ttu-id="8b154-113">**Обновите раздел реестра потенциального сервера централизованного обнаружения.**</span><span class="sxs-lookup"><span data-stu-id="8b154-113">**Update the central discovery candidate server registry key.**</span></span>

1.  <span data-ttu-id="8b154-114">На сервере, выбранном для управления логикой централизованного обнаружения, Откройте командное окно Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8b154-114">On the server elected to manage the central discovery logic, open a Windows PowerShell command window.</span></span>

2.  <span data-ttu-id="8b154-115">В командной строке введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="8b154-115">At the command line, type the following:</span></span>
    
       ```PowerShell
        New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health"
       ```
    
       ```PowerShell
        New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health\CentralDiscoveryCandidate"
       ```
    
    <div class="">
    

    > [!NOTE]  
    > <span data-ttu-id="8b154-p102">При редактировании реестра может возникнуть ошибка выполнения команды, если раздел реестра уже существует. Эту ошибку можно игнорировать.</span><span class="sxs-lookup"><span data-stu-id="8b154-p102">Whenever you edit the registry, you may experience an error that the command failed if the registry key already exists. If you experience this, you can safely ignore the error.</span></span>

    
    </div>

<span data-ttu-id="8b154-118">**Настройка основного сервера управления System Center Operations Manager для переопределения узла-наблюдателя центра обнаружения кандидатов.**</span><span class="sxs-lookup"><span data-stu-id="8b154-118">**Configure your primary System Center Operations Manager management server to override the candidate central discovery watcher node.**</span></span>

1.  <span data-ttu-id="8b154-119">На компьютере с установленной консолью System Center Operations Manager разверните **Объекты пакета управления** и выберите **Обнаружение объектов**.</span><span class="sxs-lookup"><span data-stu-id="8b154-119">On a computer where the System Center Operations Manager console has been installed, expand **Management Pack Objects** and then select **Object Discoveries**.</span></span>

2.  <span data-ttu-id="8b154-120">Щелкните пункт **Изменение области...**</span><span class="sxs-lookup"><span data-stu-id="8b154-120">Click **Change Scope...**</span></span>

3.  <span data-ttu-id="8b154-121">на странице **Ориентация объектов пакета управления** выберите **LS Discovery Candidate**.</span><span class="sxs-lookup"><span data-stu-id="8b154-121">From the **Scope Management Pack Objects** page, select **LS Discovery Candidate**.</span></span>

4.  <span data-ttu-id="8b154-122">Переопределите **Эффективное значение LS Discovery Candidate**, указав имя сервера, выбранного ранее.</span><span class="sxs-lookup"><span data-stu-id="8b154-122">Override the **LS Discovery Candidate Effective Value** to the name of the candidate server elected in the earlier procedure.</span></span>

<span data-ttu-id="8b154-123">Наконец, чтобы завершить внесение изменений, перезапустите службу работоспособности на корневом сервере управления System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="8b154-123">Lastly, to finalize your changes, restart the health service on the System Center Operations Manager Root Management Server.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

