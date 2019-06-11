---
title: 'Lync Server 2013: делегирование разрешений на установку'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Delegate setup permissions
ms:assetid: 9dca1683-4c69-4534-8ebe-6bd635cbae49
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412735(v=OCS.15)
ms:contentKeyID: 48184997
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e7df00740ac971fd56e289da04ca43abb1619329
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834662"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delegate-setup-permissions-in-lync-server-2013"></a><span data-ttu-id="5f317-102">Делегирование разрешений на установку в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5f317-102">Delegate setup permissions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5f317-103">_**Тема последнего изменения:** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="5f317-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="5f317-104">Если вы не хотите предоставлять членство в группе "Администраторы домена" пользователям или группам, которые развертывают Lync Server 2013, вы можете включить членов группы рткуниверсалсерверадминс для запуска командлета Windows PowerShell **Enable-кстопологи** на серверы, на которых запущен Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5f317-104">If you do not want to grant membership in the Domain Admins group to users or groups who are deploying Lync Server 2013, you can enable members of the RTCUniversalServerAdmins group to run the **Enable-CsTopology** Windows PowerShell cmdlet on servers running Lync Server 2013.</span></span> <span data-ttu-id="5f317-105">По умолчанию участники группы Рткуниверсалсерверадминс не могут выполнять этот командлет.</span><span class="sxs-lookup"><span data-stu-id="5f317-105">By default, members of the RTCUniversalServerAdmins group do not have the ability to run this cmdlet.</span></span> <span data-ttu-id="5f317-106">Вы можете предоставить права администратора и разрешения на запуск команды **Enable-кстопологи** на серверах с Lync Server, используя командлет **Grant-кссетуппермиссион** и УКАЗАВ подразделение (OU), в котором работают объекты-компьютеры для сервера. На нем находятся Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5f317-106">You grant administrator rights and permissions to run **Enable-CsTopology** on servers running Lync Server by using the **Grant-CsSetupPermission** cmdlet and specifying an organizational unit (OU) where computer objects for the server running Lync Server 2013 are located.</span></span>

<span data-ttu-id="5f317-107">Подготовка домена, которая выполняется при установке Lync Server, не добавляет автоматически разрешения, позволяющие членам группы Рткуниверсалсерверадминс запускать командлет Enable-Кстопологи.</span><span class="sxs-lookup"><span data-stu-id="5f317-107">The domain preparation that takes place when you install Lync Server does not automatically add the permissions that enable members of the RTCUniversalServerAdmins group to run the Enable-CsTopology cmdlet.</span></span> <span data-ttu-id="5f317-108">Это означает, что по умолчанию вы должны быть администратором домена, чтобы включить топологию.</span><span class="sxs-lookup"><span data-stu-id="5f317-108">That means that, by default, you must be a domain administrator in order to enable a topology.</span></span> <span data-ttu-id="5f317-109">Чтобы предоставить участникам группы Рткуниверсалсерверадминс право на включение топологии, необходимо запустить командлет Grant-Кссетуппермиссионс.</span><span class="sxs-lookup"><span data-stu-id="5f317-109">To give members of the RTCUniversalServerAdmins group the right to enable a topology you must run the Grant-CsSetupPermissions cmdlet.</span></span> <span data-ttu-id="5f317-110">Кроме того, вам потребуется выполнить этот командлет для каждого контейнера Active Directory, который используется для работы компьютеров с Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5f317-110">In addition, you will need to run this cmdlet against each Active Directory container that houses computers running Lync Server.</span></span>

<span data-ttu-id="5f317-111">Имейте в виду, что этот командлет предоставляет разрешения только группе Рткуниверсалсерверадминс; Этот командлет не может использоваться для предоставления разрешений другим группам безопасности или отдельным пользователям.</span><span class="sxs-lookup"><span data-stu-id="5f317-111">Keep in mind that this cmdlet only grants permissions to the RTCUniversalServerAdmins group; the cmdlet cannot be used to grant permissions to other security groups or to individual users.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5f317-112"><STRONG>Enable-кстопологи</STRONG> — это ключевой командлет, позволяющий членам группы рткуниверсалсерверадминс настраивать и развертывать Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5f317-112"><STRONG>Enable-CsTopology</STRONG> is the key cmdlet to allow the RTCUniversalServerAdmins group members to set up and deploy Lync Server 2013.</span></span>



</div>

<div>

## <a name="to-add-the-ability-to-run-enable-cstopology-to-the-rtcuniversalserveradmins-group"></a><span data-ttu-id="5f317-113">Добавление возможности запуска команды Enable-Кстопологи в группу Рткуниверсалсерверадминс</span><span class="sxs-lookup"><span data-stu-id="5f317-113">To add the ability to run Enable-CsTopology to the RTCUniversalServerAdmins group</span></span>

1.  <span data-ttu-id="5f317-114">Войдите на сервер в качестве участника группы "Администраторы домена" для домена, на котором делегированный пользователь будет выполнять **функцию Enable-кстопологи**.</span><span class="sxs-lookup"><span data-stu-id="5f317-114">Log on to a server as a member of the Domain Admins group for the domain on which the delegated user will run **Enable-CsTopology**.</span></span>

2.  <span data-ttu-id="5f317-115">Откройте консоль управления Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5f317-115">Open the Lync Server 2013 Management Shell.</span></span> <span data-ttu-id="5f317-116">Управляющая консоль Lync Server 2013 автоматически устанавливается на каждый сервер переднего плана или на любой компьютер, на котором установлены средства администрирования Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5f317-116">The Lync Server 2013 Management Shell is automatically installed on each Front End Server or any computer where the Lync Server 2013 administrative tools have been installed.</span></span> <span data-ttu-id="5f317-117">Подробные сведения о командной консоли Lync Server 2013 можно найти в руководстве по [управлению Lync server 2013](lync-server-2013-lync-server-management-shell.md) в документации по эксплуатации.</span><span class="sxs-lookup"><span data-stu-id="5f317-117">For details about the Lync Server 2013 Management Shell, see [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md) in the Operations documentation.</span></span>

3.  <span data-ttu-id="5f317-118">Запустите из командной консоли Lync Server 2013 следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="5f317-118">Run the following cmdlet from the Lync Server 2013 Management Shell:</span></span>
    
        Grant-CsSetupPermission -ComputerOU <DN of the OU> -Domain <Domain FQDN>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="5f317-119">Если подразделение имеет верхний уровень, необходимо указать полное доменное имя.</span><span class="sxs-lookup"><span data-stu-id="5f317-119">If the OU is not top level, you must provide the full domain name.</span></span>

    
    </div>
    
    <span data-ttu-id="5f317-120">В приведенном ниже примере подразделением является "серверы Lync", которые находятся в домене contoso.com.</span><span class="sxs-lookup"><span data-stu-id="5f317-120">In the following example, the OU is “Lync Servers,” which is in the contoso.com domain.</span></span>
    
        Grant-CsSetupPermission -ComputerOU "OU=Lync Servers" -Domain contoso.com

</div>

</div>

<span> </span>

</div>

</div>

</div>

