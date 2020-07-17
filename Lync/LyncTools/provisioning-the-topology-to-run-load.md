---
title: Подготовка топологии для запуска загрузки
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Provisioning the Topology to Run Load
ms:assetid: 6fba03df-3914-4d2a-8208-e252ad993aff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945598(v=OCS.15)
ms:contentKeyID: 51541424
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a3e08a66397e5c6e7fb5b6111fbdcf6d11d3632a
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2020
ms.locfileid: "44756880"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="provisioning-the-topology-to-run-load"></a><span data-ttu-id="68cf6-102">Подготовка топологии для запуска загрузки</span><span class="sxs-lookup"><span data-stu-id="68cf6-102">Provisioning the Topology to Run Load</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="68cf6-103">_**Последнее изменение темы:** 2013-02-04_</span><span class="sxs-lookup"><span data-stu-id="68cf6-103">_**Topic Last Modified:** 2013-02-04_</span></span>

<div>

## <a name="provisioning-the-topology-to-run-load"></a><span data-ttu-id="68cf6-104">Подготовка топологии для запуска загрузки</span><span class="sxs-lookup"><span data-stu-id="68cf6-104">Provisioning the Topology to Run Load</span></span>

<span data-ttu-id="68cf6-105">В зависимости от имеющихся параметров и конфигурации Lync Server 2013 в среде может потребоваться внести следующие изменения:</span><span class="sxs-lookup"><span data-stu-id="68cf6-105">Depending on your existing settings and configuration of Lync Server 2013, you may need to make the following changes in your environment:</span></span>

1.  <span data-ttu-id="68cf6-106">Присвойте политике выполнения Windows PowerShell неограниченный доступ.</span><span class="sxs-lookup"><span data-stu-id="68cf6-106">Set the Windows PowerShell execution policy to Unrestricted.</span></span> <span data-ttu-id="68cf6-107">Чтобы проверить параметры политики выполнения, откройте консоль управления Lync Server и выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="68cf6-107">To check your execution policy settings, open the Lync Server Management Shell and run the following command:</span></span>

    ``` powershell
        Get-ExecutionPolicy
    ```        

    <span data-ttu-id="68cf6-108">Если эта команда не возвращает значение Unrestricted, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="68cf6-108">If this command does not return the value Unrestricted, run this command:</span></span>

    ``` powershell
        Set-ExecutionPolicy -Unrestricted
    ```

2.  <span data-ttu-id="68cf6-109">Чтобы эффективно настроить Lync Server 2013, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="68cf6-109">To effectively configure Lync Server 2013, you will need to:</span></span>
    
      - <span data-ttu-id="68cf6-110">Знакомство с топологией Lync Server 2013 (например, именами компьютеров, экземплярами служб, именами сайтов и политиками).</span><span class="sxs-lookup"><span data-stu-id="68cf6-110">Be familiar with Lync Server 2013 topology (for example, computer names, service instances, site names, and policies).</span></span>
    
      - <span data-ttu-id="68cf6-111">Назначьте некоторые пользователи, созданные для групп, например группы слежения группы ответа (например, URI SIP).</span><span class="sxs-lookup"><span data-stu-id="68cf6-111">Assign some of the users that were created to groups, such as Response Group hunt groups (for example, SIP URIs).</span></span>

3.  <span data-ttu-id="68cf6-112">Чтобы запустить скрипт из командной строки, можно использовать:</span><span class="sxs-lookup"><span data-stu-id="68cf6-112">To run the script from the command line, you may use:</span></span>

    ``` powershell
        Powershell.exe -file <path to the file>
    ```
    
4.  <span data-ttu-id="68cf6-113">Как правило, после выполнения одного из сценариев в этом пакете результаты трассировки из скрипта будут храниться в файле, который был вызван с помощью сценария с именем \<scriptname\> $h $ m $s.txt.</span><span class="sxs-lookup"><span data-stu-id="68cf6-113">Typically, after one of the scripts in this package runs, the resulting traces from the script will be stored in a file in the same path from which the script was invoked, named \<scriptname\>$h$m$s.txt.</span></span> <span data-ttu-id="68cf6-114">Например, выполнение ArchivingPolicy.ps1 в 12:15 P.M.</span><span class="sxs-lookup"><span data-stu-id="68cf6-114">For example, running ArchivingPolicy.ps1 at 12:15 P.M.</span></span> <span data-ttu-id="68cf6-115">создаст файл журнала, например ArchivingPolicy121500.txt.</span><span class="sxs-lookup"><span data-stu-id="68cf6-115">will generate a log file such as ArchivingPolicy121500.txt.</span></span>

5.  <span data-ttu-id="68cf6-116">Наконец, обратите внимание, что хотя мы предоставили примеры для настройки сервера, вы несете ответственность за изменение или удаление конфигурации после завершения загрузки.</span><span class="sxs-lookup"><span data-stu-id="68cf6-116">Finally, note that although we have provided examples to configure the server, you are responsible for modifying or deleting the configuration after you have finished running the load.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

