---
title: Перемещение контактных объектов единой системы обмена сообщениями Exchange
description: Перемещение контактных объектов единой системы обмена сообщениями Exchange.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Move Exchange Unified Messaging Contact objects
ms:assetid: 35c7e987-41b5-4798-b617-3303f20e52e3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688022(v=OCS.15)
ms:contentKeyID: 49733612
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e3353427f407523a8778585d27201355714a3085
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48549725"
---
# <a name="move-exchange-unified-messaging-contact-objects"></a><span data-ttu-id="d38e2-103">Перемещение контактных объектов единой системы обмена сообщениями Exchange</span><span class="sxs-lookup"><span data-stu-id="d38e2-103">Move Exchange Unified Messaging Contact objects</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d38e2-104">_**Последнее изменение темы:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="d38e2-104">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="d38e2-105">Для переноса контактных объектов автосекретаря (AA) и абонентского доступа (SA) в новое развертывание Lync Server 2013 сначала необходимо переместить объекты из устаревшего развертывания Office Communications Server 2007 R2 в новое развертывание Lync Server 2013 с помощью командлетов **Get-CsExUmContact** и **Move-CsExUmContact** .</span><span class="sxs-lookup"><span data-stu-id="d38e2-105">To migrate Auto Attendant (AA) and Subscriber Access (SA) contact objects to the new Lync Server 2013 deployment, you first move the objects from the legacy Office Communications Server 2007 R2 deployment to the new the Lync Server 2013 deployment using the **Get-CsExUmContact** and **Move-CsExUmContact** cmdlets.</span></span> <span data-ttu-id="d38e2-106">Затем на сервере Exchange выполните сценарий Windows PowerShell **сценарий ExchUCUtil** , чтобы выполнить следующие действия для вновь развернутого пула Lync:</span><span class="sxs-lookup"><span data-stu-id="d38e2-106">On the Exchange Server, you then run the **ExchUCUtil** Windows PowerShell script to do the following for the newly deployed Lync pool:</span></span>

  - <span data-ttu-id="d38e2-107">Добавить его в шлюз IP единой системы обмена сообщениями.</span><span class="sxs-lookup"><span data-stu-id="d38e2-107">Add it to the Unified Messaging IP gateways.</span></span>

  - <span data-ttu-id="d38e2-108">Добавить его в сервисные группы единой системы обмена сообщениями.</span><span class="sxs-lookup"><span data-stu-id="d38e2-108">Add it to the Unified Messaging hunt groups.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d38e2-p102">Чтобы использовать командлеты <STRONG>Get-CsExUmContact</STRONG> и <STRONG>Move-CsExUmContact</STRONG>, вы должны быть участником группы RTCUniversalUserAdmins и иметь разрешение для подразделения, в котором хранятся контактные объекты. Разрешение для подразделения предоставляется с помощью командлета <STRONG>Grant-OUPermission</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="d38e2-p102">In order to use the <STRONG>Get-CsExUmContact</STRONG> and <STRONG>Move-CsExUmContact</STRONG> cmdlets, you must be a member of the RTCUniversalUserAdmins group and have organizational unit (OU) permission to the OU where the contacts objects are stored. OU permission can be granted using the <STRONG>Grant-OUPermission</STRONG> cmdlet.</span></span>



</div>

<div>

## <a name="to-move-contact-objects-by-using-the-lync-server-management-shell"></a><span data-ttu-id="d38e2-111">Перемещение контактных объектов с помощью командной консоли Lync Server</span><span class="sxs-lookup"><span data-stu-id="d38e2-111">To move contact objects by using the Lync Server Management Shell</span></span>

1.  <span data-ttu-id="d38e2-112">Откройте командную консоль Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d38e2-112">Open the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="d38e2-113">Для каждого пула, зарегистрированного в единой системе обмена сообщениями Exchange (где pool1.contoso.net — это пул из развертывания Office Communications Server 2007 R2 и pool2.contoso.net — это пул из развертывания Lync Server 2013), в командной строке введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="d38e2-113">For each pool registered with Exchange UM (where pool1.contoso.net is a pool from the Office Communications Server 2007 R2 deployment and pool2.contoso.net is the pool from the Lync Server 2013 deployment) at the command line, type the following:</span></span>
    
        Get-CsExUmContact -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsExUmContact -Target pool02.contoso.net
    
    <span data-ttu-id="d38e2-114">Чтобы проверить успешность перемещения контактных объектов, выполните командлет **Get-CsExumContact** и убедитесь, что **RegistrarPool** теперь указывает на новый пул.</span><span class="sxs-lookup"><span data-stu-id="d38e2-114">To verify that the contact objects are moved, run the **Get-CsExumContact** cmdlet and confirm that **RegistrarPool** is now pointing to the new pool.</span></span>

</div>

<div>

## <a name="to-run-the-exchucutil-windows-powershell-script"></a><span data-ttu-id="d38e2-115">Выполнение скрипта ExchUCUtil Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d38e2-115">To run the ExchUCUtil Windows PowerShell script</span></span>

1.  <span data-ttu-id="d38e2-116">Войдите на сервер Exchange Server с единой системой обмена сообщениями как пользователь с привилегиями администратора организации в Exchange.</span><span class="sxs-lookup"><span data-stu-id="d38e2-116">Log on to the Exchange UM Server as a user with Exchange Organization Administrator privileges.</span></span>

2.  <span data-ttu-id="d38e2-117">Перейдите к скрипту Windows PowerShell сценарий ExchUCUtil.</span><span class="sxs-lookup"><span data-stu-id="d38e2-117">Navigate to the ExchUCUtil Windows PowerShell script.</span></span>
    
    <span data-ttu-id="d38e2-118">В Exchange 2007 ExchUCUtil.ps1 находится по адресу: **% Program Files% \\ Microsoft \\ Exchange Server \\ scripting \\ExchUCUtil.ps1**</span><span class="sxs-lookup"><span data-stu-id="d38e2-118">In Exchange 2007, ExchUCUtil.ps1 is located at: **%Program Files%\\Microsoft\\Exchange Server\\Scripts\\ExchUCUtil.ps1**</span></span>
    
    <span data-ttu-id="d38e2-119">В Exchange 2010 ExchUCUtil.ps1 расположен по адресу: **% Program Files% \\ Microsoft \\ Exchange Server \\ V14 \\ Scripts \\ExchUCUtil.ps1**</span><span class="sxs-lookup"><span data-stu-id="d38e2-119">In Exchange 2010, ExchUCUtil.ps1 is located at: **%Program Files%\\Microsoft\\Exchange Server\\V14\\Scripts\\ExchUCUtil.ps1**</span></span>

3.  <span data-ttu-id="d38e2-120">Если Exchange развертывается в одном лесу, введите:</span><span class="sxs-lookup"><span data-stu-id="d38e2-120">If Exchange is deployed in a single forest, type:</span></span>
    
        exchucutil.ps1
    
    <span data-ttu-id="d38e2-121">Если Exchange развертывается в нескольких лесах, введите:</span><span class="sxs-lookup"><span data-stu-id="d38e2-121">Or, if Exchange is deployed in multiple forests, type:</span></span>
    
        exchucutil.ps1 -Forest:" <forest FQDN>"
    
    <span data-ttu-id="d38e2-122">где полное доменное имя леса указывает лес, в котором развернут Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d38e2-122">where forest FQDN specifies the forest in which Lync Server 2013 is deployed.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="d38e2-123">Обязательно перезапустите службу <STRONG>Сервер переднего плана Lync Server</STRONG> (rtcsrv.exe) <EM>после</EM> выполнения скрипта exchucutil.ps1.</span><span class="sxs-lookup"><span data-stu-id="d38e2-123">Be sure to restart the <STRONG>Lync Server Front-End</STRONG> service (rtcsrv.exe) <EM>after</EM> you run exchucutil.ps1.</span></span> <span data-ttu-id="d38e2-124">В противном случае Lync Server 2013 не будет обнаруживать единую систему обмена сообщениями в топологии.</span><span class="sxs-lookup"><span data-stu-id="d38e2-124">Otherwise, Lync Server 2013 will not detect Unified Messaging in the topology.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

