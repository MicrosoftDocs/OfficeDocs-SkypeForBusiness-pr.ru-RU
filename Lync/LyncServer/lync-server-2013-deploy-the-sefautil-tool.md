---
title: 'Lync Server 2013: развертывание средства SEFAUtil'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploy the SEFAUtil tool
ms:assetid: fb556e50-88dd-4404-a3d5-be36f5ba41e6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945659(v=OCS.15)
ms:contentKeyID: 51541534
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c37108d8429567c2653174e4d5a9d0510278e4f3
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42214325"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploy-the-sefautil-tool-in-lync-server-2013"></a><span data-ttu-id="e7077-102">Развертывание средства SEFAUtil в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e7077-102">Deploy the SEFAUtil tool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e7077-103">_**Последнее изменение темы:** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="e7077-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="e7077-104">Для развертывания и управления групповой отправке звонков необходимо использовать средство SEFAUtil Resource Kit.</span><span class="sxs-lookup"><span data-stu-id="e7077-104">To deploy and manage Group Call Pickup, you need to use the SEFAUtil resource kit tool.</span></span> <span data-ttu-id="e7077-105">Средство является частью средств набора ресурсов Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e7077-105">The tool is part of the Lync Server 2013 resource kit tools.</span></span> <span data-ttu-id="e7077-106">Перед установкой SEFAUtil необходимо включить в топологию доверенный пул приложений, указать SEFAUtil в качестве доверенного приложения и включить топологию.</span><span class="sxs-lookup"><span data-stu-id="e7077-106">Before you can install SEFAUtil, you must have a trusted application pool in your topology, specify SEFAUtil as a trusted application, and enable the topology.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="e7077-107">Пакет SDK для Microsoft Unified Communications Managed API (UCMA) 3,0 необходимо установить на любой компьютер, на котором планируется запустить средство SEFAUtil.</span><span class="sxs-lookup"><span data-stu-id="e7077-107">Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK must be installed on any computer where you plan to run the SEFAUtil tool.</span></span>



</div>

<span data-ttu-id="e7077-108">Вы можете запустить SEFAUtil в любом пуле переднего плана в своем развертывании.</span><span class="sxs-lookup"><span data-stu-id="e7077-108">You can run the SEFAUtil in any Front End pool in your deployment.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e7077-109">Дополнительные сведения о запуске SEFAUtil можно найти в статье блог TechNet "как получить SEFAutil?"</span><span class="sxs-lookup"><span data-stu-id="e7077-109">For more details about running SEFAUtil, see the Technet blog article, "How to get SEFAutil running?"</span></span> <span data-ttu-id="e7077-110">по <A href="https://go.microsoft.com/fwlink/?linkid=278940">https://go.microsoft.com/fwlink/?LinkId=278940</A>адресу.</span><span class="sxs-lookup"><span data-stu-id="e7077-110">at <A href="https://go.microsoft.com/fwlink/?linkid=278940">https://go.microsoft.com/fwlink/?LinkId=278940</A>.</span></span>



</div>

<div>

## <a name="to-deploy-sefautil"></a><span data-ttu-id="e7077-111">Развертывание SEFAUtil</span><span class="sxs-lookup"><span data-stu-id="e7077-111">To deploy SEFAUtil</span></span>

1.  <span data-ttu-id="e7077-112">Выполните вход на компьютер, на котором установлена командная консоль Lync Server, в качестве члена группы RTCUniversalServerAdmins или с необходимыми правами пользователя, как описано в разделе [Делегирование разрешений на установку в Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="e7077-112">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="e7077-113">Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="e7077-113">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="e7077-114">Средство SEFAUtil можно запускать только на компьютере, входящем в пул доверенных приложений.</span><span class="sxs-lookup"><span data-stu-id="e7077-114">The SEFAUtil tool can be run only on a computer that is part of a trusted application pool.</span></span> <span data-ttu-id="e7077-115">При необходимости определите доверенный пул приложений для пула переднего плана, где планируется запускать SEFAUtil.</span><span class="sxs-lookup"><span data-stu-id="e7077-115">If needed, define a trusted application pool for the Front End pool where you plan to run SEFAUtil.</span></span> <span data-ttu-id="e7077-116">В командной строке выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="e7077-116">At the command line, run:</span></span>
    
        New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>

4.  <span data-ttu-id="e7077-117">Определите средство SEFAUtil в качестве доверенного приложения.</span><span class="sxs-lookup"><span data-stu-id="e7077-117">Define the SEFAUtil tool as a trusted application.</span></span> <span data-ttu-id="e7077-118">В командной строке выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="e7077-118">At the command line, run:</span></span>
    
        New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN>  -Port 7489
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e7077-119">При необходимости можно использовать другой порт.</span><span class="sxs-lookup"><span data-stu-id="e7077-119">You can use a different port if needed.</span></span>

    
    </div>

5.  <span data-ttu-id="e7077-120">Включите топологию с изменениями.</span><span class="sxs-lookup"><span data-stu-id="e7077-120">Enable the topology with your changes.</span></span> <span data-ttu-id="e7077-121">В командной строке выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="e7077-121">At the command line, run:</span></span>
    
        Enable-CsTopology

6.  <span data-ttu-id="e7077-122">Установите средства набора ресурсов Lync Server 2013 на сервере переднего плана, который находится в пуле доверенных приложений, созданном на шаге 3.</span><span class="sxs-lookup"><span data-stu-id="e7077-122">Install the Lync Server 2013 resource kit tools on a Front End Server that is in the trusted application pool that you created in step 3.</span></span>

7.  <span data-ttu-id="e7077-123">Убедитесь, что средство SEFAUtil работает правильно, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="e7077-123">Verify that the SEFAUtil tool is running correctly, as follows:</span></span>
    
    1.  <span data-ttu-id="e7077-124">Запустите средство из командной строки Windows с правами администратора, чтобы отобразить параметры переадресации звонков пользователя в развертывании.</span><span class="sxs-lookup"><span data-stu-id="e7077-124">Run the tool from the Windows command prompt with administrator privileges to display the call forwarding settings of a user in your deployment.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="e7077-125">Средство находится на сайте \Program Files\Microsoft Lync Server 2013 \ reskit.</span><span class="sxs-lookup"><span data-stu-id="e7077-125">The tool is located at \Program Files\Microsoft Lync Server 2013\Reskit.</span></span>

        
        </div>
    
    2.  <span data-ttu-id="e7077-126">Отображение параметров переадресации звонков пользователя.</span><span class="sxs-lookup"><span data-stu-id="e7077-126">Display the call forwarding settings of a user.</span></span> <span data-ttu-id="e7077-127">В командной строке выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="e7077-127">At the command line, run:</span></span>
        
            SEFAUtil.exe <user SIP address> /server:<Lync Server/Pool FQDN>
        
        <span data-ttu-id="e7077-128">Будут отображены параметры переадресации звонков для пользователя.</span><span class="sxs-lookup"><span data-stu-id="e7077-128">The call forwarding settings for the user will be displayed.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

