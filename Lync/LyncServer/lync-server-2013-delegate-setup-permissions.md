---
title: 'Lync Server 2013: Делегирование разрешений на установку'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delegate setup permissions
ms:assetid: 9dca1683-4c69-4534-8ebe-6bd635cbae49
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412735(v=OCS.15)
ms:contentKeyID: 48184997
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 453da166895c79cafe9f9637163e93a63ebccd75
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48504286"
---
# <a name="delegate-setup-permissions-in-lync-server-2013"></a><span data-ttu-id="54eea-102">Делегирование разрешений на установку в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="54eea-102">Delegate setup permissions in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="54eea-103">_**Последнее изменение темы:** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="54eea-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="54eea-104">Если вы не хотите предоставлять членство в группе "Администраторы домена" пользователям или группам, которые развертывают Lync Server 2013, можно включить членов группы RTCUniversalServerAdmins для запуска командлета Windows PowerShell **Enable – CsTopology**   на серверах, на которых работает Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="54eea-104">If you do not want to grant membership in the Domain Admins group to users or groups who are deploying Lync Server 2013, you can enable members of the RTCUniversalServerAdmins group to run the **Enable-CsTopology** Windows PowerShell cmdlet on servers running Lync Server 2013.</span></span> <span data-ttu-id="54eea-105">По умолчанию члены группы RTCUniversalServerAdmins не имеют прав на выполнение этого командлета.</span><span class="sxs-lookup"><span data-stu-id="54eea-105">By default, members of the RTCUniversalServerAdmins group do not have the ability to run this cmdlet.</span></span> <span data-ttu-id="54eea-106">Права и разрешения администратора предоставляются для запуска командлета **Enable-CsTopology** на серверах, работающих под управлением Lync Server, с помощью командлета **Grant-CsSetupPermission** и указания подразделения, в котором расположены объекты-компьютеры для сервера, на котором работает Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="54eea-106">You grant administrator rights and permissions to run **Enable-CsTopology** on servers running Lync Server by using the **Grant-CsSetupPermission** cmdlet and specifying an organizational unit (OU) where computer objects for the server running Lync Server 2013 are located.</span></span>

<span data-ttu-id="54eea-107">Подготовка домена, которая выполняется при установке Lync Server, не добавляет разрешения, которые позволяют членам группы RTCUniversalServerAdmins выполнять командлет Enable-CsTopology.</span><span class="sxs-lookup"><span data-stu-id="54eea-107">The domain preparation that takes place when you install Lync Server does not automatically add the permissions that enable members of the RTCUniversalServerAdmins group to run the Enable-CsTopology cmdlet.</span></span> <span data-ttu-id="54eea-108">Это значит, что по умолчанию нужны права администратора домена для включения топологии.</span><span class="sxs-lookup"><span data-stu-id="54eea-108">That means that, by default, you must be a domain administrator in order to enable a topology.</span></span> <span data-ttu-id="54eea-109">Чтобы дать членам группы RTCUniversalServerAdmins право включать топологию, следует запустить командлет Grant-CsSetupPermissions.</span><span class="sxs-lookup"><span data-stu-id="54eea-109">To give members of the RTCUniversalServerAdmins group the right to enable a topology you must run the Grant-CsSetupPermissions cmdlet.</span></span> <span data-ttu-id="54eea-110">Кроме того, этот командлет необходимо выполнить для каждого контейнера Active Directory, в котором разработаны компьютеры, работающие под управлением Lync Server.</span><span class="sxs-lookup"><span data-stu-id="54eea-110">In addition, you will need to run this cmdlet against each Active Directory container that houses computers running Lync Server.</span></span>

<span data-ttu-id="54eea-111">Помните, что данный командлет дает права только членам группы RTCUniversalServerAdmins; права не могут быть предоставлены другим группам безопасности или отдельным пользователям.</span><span class="sxs-lookup"><span data-stu-id="54eea-111">Keep in mind that this cmdlet only grants permissions to the RTCUniversalServerAdmins group; the cmdlet cannot be used to grant permissions to other security groups or to individual users.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="54eea-112"><STRONG>Enable-CsTopology</STRONG> — это ключевой командлет, позволяющий членам группы RTCUniversalServerAdmins настраивать и развертывать Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="54eea-112"><STRONG>Enable-CsTopology</STRONG> is the key cmdlet to allow the RTCUniversalServerAdmins group members to set up and deploy Lync Server 2013.</span></span>



</div>

<div>

## <a name="to-add-the-ability-to-run-enable-cstopology-to-the-rtcuniversalserveradmins-group"></a><span data-ttu-id="54eea-113">Добавление возможности выполнения командлета Enable-CsTopology группе RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="54eea-113">To add the ability to run Enable-CsTopology to the RTCUniversalServerAdmins group</span></span>

1.  <span data-ttu-id="54eea-114">Войдите на сервер как член группы администраторов домена того домена, в котором делегированный пользователь будет выполнять командлет **Enable-CsTopology**.</span><span class="sxs-lookup"><span data-stu-id="54eea-114">Log on to a server as a member of the Domain Admins group for the domain on which the delegated user will run **Enable-CsTopology**.</span></span>

2.  <span data-ttu-id="54eea-115">Откройте консоль управления Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="54eea-115">Open the Lync Server 2013 Management Shell.</span></span> <span data-ttu-id="54eea-116">Командная консоль Lync Server 2013 автоматически устанавливается на каждом сервере переднего плана или на любом компьютере, на котором установлены средства администрирования Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="54eea-116">The Lync Server 2013 Management Shell is automatically installed on each Front End Server or any computer where the Lync Server 2013 administrative tools have been installed.</span></span> <span data-ttu-id="54eea-117">Подробные сведения о командной консоли Lync Server 2013 можно найти в документации по [управлению Lync server 2013](lync-server-2013-lync-server-management-shell.md) в документации по операциям.</span><span class="sxs-lookup"><span data-stu-id="54eea-117">For details about the Lync Server 2013 Management Shell, see [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md) in the Operations documentation.</span></span>

3.  <span data-ttu-id="54eea-118">Выполните следующий командлет из консоли управления Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="54eea-118">Run the following cmdlet from the Lync Server 2013 Management Shell:</span></span>
    
        Grant-CsSetupPermission -ComputerOU <DN of the OU> -Domain <Domain FQDN>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="54eea-119">Если подразделение находится не на верхнем уровне, необходимо предоставить полное доменное имя.</span><span class="sxs-lookup"><span data-stu-id="54eea-119">If the OU is not top level, you must provide the full domain name.</span></span>

    
    </div>
    
    <span data-ttu-id="54eea-120">В следующем примере подразделение — это “Lync Servers”, и находится оно в домене contoso.com.</span><span class="sxs-lookup"><span data-stu-id="54eea-120">In the following example, the OU is “Lync Servers,” which is in the contoso.com domain.</span></span>
    
        Grant-CsSetupPermission -ComputerOU "OU=Lync Servers" -Domain contoso.com

</div>

</div>

<span> </span>

</div>

</div>

</div>

