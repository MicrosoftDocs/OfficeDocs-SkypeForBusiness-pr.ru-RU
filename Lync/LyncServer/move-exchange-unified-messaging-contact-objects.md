---
title: Перемещение объектов контактов единой системы обмена сообщениями Exchange
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Move Exchange Unified Messaging Contact objects
ms:assetid: 35c7e987-41b5-4798-b617-3303f20e52e3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688022(v=OCS.15)
ms:contentKeyID: 49733612
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d79354522675daaf221052579b0863899d1176ee
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756043"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-exchange-unified-messaging-contact-objects"></a><span data-ttu-id="ca5cc-102">Перемещение объектов контактов единой системы обмена сообщениями Exchange</span><span class="sxs-lookup"><span data-stu-id="ca5cc-102">Move Exchange Unified Messaging Contact objects</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ca5cc-103">_**Тема последнего изменения:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="ca5cc-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="ca5cc-104">Для миграции объектов контактов для автосекретаря (AA) и доступа к подписчикам (SA) на новый сервер Lync Server 2013 сначала нужно переместить объекты из устаревшего развертывания Office Communications Server 2007 R2 на новое развертывание Lync Server 2013 с помощью командлетов **Get-ксексумконтакт** и **Move-ксексумконтакт** .</span><span class="sxs-lookup"><span data-stu-id="ca5cc-104">To migrate Auto Attendant (AA) and Subscriber Access (SA) contact objects to the new Lync Server 2013 deployment, you first move the objects from the legacy Office Communications Server 2007 R2 deployment to the new the Lync Server 2013 deployment using the **Get-CsExUmContact** and **Move-CsExUmContact** cmdlets.</span></span> <span data-ttu-id="ca5cc-105">На сервере Exchange Server вы можете запустить сценарий Windows PowerShell **ексчукутил** , чтобы сделать следующее для вновь развернутого пула Lync:</span><span class="sxs-lookup"><span data-stu-id="ca5cc-105">On the Exchange Server, you then run the **ExchUCUtil** Windows PowerShell script to do the following for the newly deployed Lync pool:</span></span>

  - <span data-ttu-id="ca5cc-106">Добавьте его в IP-шлюз единой системы обмена сообщениями.</span><span class="sxs-lookup"><span data-stu-id="ca5cc-106">Add it to the Unified Messaging IP gateways.</span></span>

  - <span data-ttu-id="ca5cc-107">Добавьте его в группу слежения единой системы обмена сообщениями.</span><span class="sxs-lookup"><span data-stu-id="ca5cc-107">Add it to the Unified Messaging hunt groups.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ca5cc-108">Чтобы использовать командлеты <STRONG>Get-ксексумконтакт</STRONG> и <STRONG>Move-ксексумконтакт</STRONG> , вы должны быть участником группы РТКУНИВЕРСАЛУСЕРАДМИНС и иметь разрешение OU на подразделение, в котором хранятся объекты контактов.</span><span class="sxs-lookup"><span data-stu-id="ca5cc-108">In order to use the <STRONG>Get-CsExUmContact</STRONG> and <STRONG>Move-CsExUmContact</STRONG> cmdlets, you must be a member of the RTCUniversalUserAdmins group and have organizational unit (OU) permission to the OU where the contacts objects are stored.</span></span> <span data-ttu-id="ca5cc-109">Разрешение OU можно предоставить с помощью командлета <STRONG>Grant-аупермиссион</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="ca5cc-109">OU permission can be granted using the <STRONG>Grant-OUPermission</STRONG> cmdlet.</span></span>



</div>

<div>

## <a name="to-move-contact-objects-by-using-the-lync-server-management-shell"></a><span data-ttu-id="ca5cc-110">Перемещение объектов контакта с помощью командной консоли Lync Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="ca5cc-110">To move contact objects by using the Lync Server Management Shell</span></span>

1.  <span data-ttu-id="ca5cc-111">Откройте командную консоль Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="ca5cc-111">Open the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="ca5cc-112">Для каждого пула, зарегистрированного в единой системе обмена сообщениями Exchange (где pool1.contoso.net — это пул из конфигурации Office Communications Server 2007 R2 и pool2.contoso.net — это пул из развертывания Lync Server 2013), введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="ca5cc-112">For each pool registered with Exchange UM (where pool1.contoso.net is a pool from the Office Communications Server 2007 R2 deployment and pool2.contoso.net is the pool from the Lync Server 2013 deployment) at the command line, type the following:</span></span>
    
        Get-CsExUmContact -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsExUmContact -Target pool02.contoso.net
    
    <span data-ttu-id="ca5cc-113">Чтобы убедиться в том, что объекты контакта перемещены, выполните командлет **Get-ксексумконтакт** и убедитесь, что в **регистрарпул** указывает на новый пул.</span><span class="sxs-lookup"><span data-stu-id="ca5cc-113">To verify that the contact objects are moved, run the **Get-CsExumContact** cmdlet and confirm that **RegistrarPool** is now pointing to the new pool.</span></span>

</div>

<div>

## <a name="to-run-the-exchucutil-windows-powershell-script"></a><span data-ttu-id="ca5cc-114">Выполнение сценария Windows PowerShell Ексчукутил</span><span class="sxs-lookup"><span data-stu-id="ca5cc-114">To run the ExchUCUtil Windows PowerShell script</span></span>

1.  <span data-ttu-id="ca5cc-115">Войдите на сервер Exchange UM как пользователь с правами администратора организации Exchange.</span><span class="sxs-lookup"><span data-stu-id="ca5cc-115">Log on to the Exchange UM Server as a user with Exchange Organization Administrator privileges.</span></span>

2.  <span data-ttu-id="ca5cc-116">Перейдите на Ексчукутил сценарий Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ca5cc-116">Navigate to the ExchUCUtil Windows PowerShell script.</span></span>
    
    <span data-ttu-id="ca5cc-117">В Exchange 2007 Ексчукутил. ps1 размещается по адресу: **% Program\\Files\\%\\Scripts\\сервера Microsoft Exchange Server ексчукутил. ps1**</span><span class="sxs-lookup"><span data-stu-id="ca5cc-117">In Exchange 2007, ExchUCUtil.ps1 is located at: **%Program Files%\\Microsoft\\Exchange Server\\Scripts\\ExchUCUtil.ps1**</span></span>
    
    <span data-ttu-id="ca5cc-118">В Exchange 2010 Ексчукутил. ps1 расположен по адресу: **% Program Files\\%\\Microsoft Exchange\\Server\\V14\\Scripts ексчукутил. ps1**</span><span class="sxs-lookup"><span data-stu-id="ca5cc-118">In Exchange 2010, ExchUCUtil.ps1 is located at: **%Program Files%\\Microsoft\\Exchange Server\\V14\\Scripts\\ExchUCUtil.ps1**</span></span>

3.  <span data-ttu-id="ca5cc-119">Если Exchange развернут в одном лесе, введите:</span><span class="sxs-lookup"><span data-stu-id="ca5cc-119">If Exchange is deployed in a single forest, type:</span></span>
    
        exchucutil.ps1
    
    <span data-ttu-id="ca5cc-120">Если Exchange развернут в нескольких лесах, введите:</span><span class="sxs-lookup"><span data-stu-id="ca5cc-120">Or, if Exchange is deployed in multiple forests, type:</span></span>
    
        exchucutil.ps1 -Forest:" <forest FQDN>"
    
    <span data-ttu-id="ca5cc-121">где полное доменное имя леса определяет лес, в котором развернут Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ca5cc-121">where forest FQDN specifies the forest in which Lync Server 2013 is deployed.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="ca5cc-122"><EM>После</EM> запуска ексчукутил. ps1 убедитесь в том, что вы перезапустите службу <STRONG>внешнего сервера Lync Server</STRONG> (ртксрв. exe).</span><span class="sxs-lookup"><span data-stu-id="ca5cc-122">Be sure to restart the <STRONG>Lync Server Front-End</STRONG> service (rtcsrv.exe) <EM>after</EM> you run exchucutil.ps1.</span></span> <span data-ttu-id="ca5cc-123">В противном случае Lync Server 2013 не будет определять единую систему обмена сообщениями в топологии.</span><span class="sxs-lookup"><span data-stu-id="ca5cc-123">Otherwise, Lync Server 2013 will not detect Unified Messaging in the topology.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

