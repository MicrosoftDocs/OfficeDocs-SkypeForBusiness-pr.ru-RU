---
title: 'Lync Server 2013: прежде чем приступить к переносу пользователей из Lync Online в локальную среду Lync, выполните указанные ниже действия.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: First steps before you start migrating users from Lync Online to Lync on-premises
ms:assetid: 98245b04-ded4-4186-8da3-ba1c554b5c39
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn689118(v=OCS.15)
ms:contentKeyID: 62258123
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8065d1c09ab48b1b3a874fd11d7f8fcad298bfcb
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48500846"
---
# <a name="first-steps-before-you-start-migrating-users-from-lync-online-to-lync-on-premises-in-lync-server-2013"></a><span data-ttu-id="d66b8-102">Прежде чем приступить к переносу пользователей из Lync Online в локальную среду Lync в Lync Server 2013, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="d66b8-102">First steps before you start migrating users from Lync Online to Lync on-premises in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d66b8-103">_**Последнее изменение темы:** 2014-05-08_</span><span class="sxs-lookup"><span data-stu-id="d66b8-103">_**Topic Last Modified:** 2014-05-08_</span></span>

<span data-ttu-id="d66b8-104">Перед перемещением пользователей Lync Online в локальную среду убедитесь, что выполняются все перечисленные ниже условия.</span><span class="sxs-lookup"><span data-stu-id="d66b8-104">Before you start moving Lync Online users to your on-premises environment, check that all of the following are true:</span></span>

  - <span data-ttu-id="d66b8-105">Локальная среда Lync Server должна быть полностью развернута и проверена.</span><span class="sxs-lookup"><span data-stu-id="d66b8-105">Your Lync Server on-premises environment must be fully deployed and validated.</span></span> <span data-ttu-id="d66b8-106">Дополнительные сведения см. в статье [deploy Lync Server 2013](lync-server-2013-deploying-lync-server.md).</span><span class="sxs-lookup"><span data-stu-id="d66b8-106">For more information, see [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md).</span></span>

  - <span data-ttu-id="d66b8-107">Для клиента Lync Online необходимо настроить доступ к удаленной оболочке PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d66b8-107">Your Lync Online tenant must be configured for remote PowerShell Access.</span></span>
    
    <span data-ttu-id="d66b8-108">Для этого сначала установите модуль Lync Online для Windows PowerShell, который вы можете скачать здесь: [https://go.microsoft.com/fwlink/p/?LinkId=391911](https://go.microsoft.com/fwlink/p/?linkid=391911) .</span><span class="sxs-lookup"><span data-stu-id="d66b8-108">To do this, first install the Lync Online module for Windows PowerShell, which you can get here: [https://go.microsoft.com/fwlink/p/?LinkId=391911](https://go.microsoft.com/fwlink/p/?linkid=391911).</span></span>
    
    <span data-ttu-id="d66b8-109">После установки модуля можно установить удаленный сеанс, введя следующие командлеты в командной консоли Lync Server:</span><span class="sxs-lookup"><span data-stu-id="d66b8-109">After you install the module, you can establish a remote session by typing the following cmdlets in the Lync Server Management Shell:</span></span>
    
       ```PowerShell
        Import-Module LyncOnlineConnector
       ```  
    
       ```PowerShell
        $cred = Get-Credential
       ``` 
    
       ```PowerShell
        $CSSession = New-CsOnlineSession -Credential $cred
       ```
    
       ```PowerShell
        Import-PSSession $CSSession -AllowClobber
       ```
    
    <span data-ttu-id="d66b8-110">Дополнительные сведения о том, как установить удаленный сеанс PowerShell с помощью Lync Online, можно узнать [в статье подключение к Lync Online с помощью Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="d66b8-110">For more information about how to establish a remote PowerShell session with Lync Online, see [Connecting to Lync Online by using Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>
  
    <span data-ttu-id="d66b8-111">Более подробную информацию об использовании модуля Lync Online PowerShell можно узнать [в статье Использование Windows PowerShell для управления Lync Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="d66b8-111">For more information about using the Lync Online PowerShell module, see [Using Windows PowerShell to manage Lync Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>

  - <span data-ttu-id="d66b8-112">Необходимо настроить Lync Online для общего адресного пространства SIP.</span><span class="sxs-lookup"><span data-stu-id="d66b8-112">Your Lync Online must be configured for Shared SIP Address Space.</span></span> <span data-ttu-id="d66b8-113">Для этого сначала запустите удаленный сеанс PowerShell с Lync Online.</span><span class="sxs-lookup"><span data-stu-id="d66b8-113">To do this, first start a remote Powershell session with Lync Online.</span></span> <span data-ttu-id="d66b8-114">Затем выполните следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="d66b8-114">Then run the following cmdlet:</span></span>
    
        Set-CsTenantFederationConfiguration -SharedSipAddressSpace $True

<span data-ttu-id="d66b8-115">После выполнения этих действий вы можете перейти к [переходу пользователей Lync Online в локальную среду Lync в Lync Server 2013](lync-server-2013-migrating-lync-online-users-to-lync-on-premises.md).</span><span class="sxs-lookup"><span data-stu-id="d66b8-115">After you’ve finished these steps, you can move on to [Migrating Lync Online users to Lync on-premises in Lync Server 2013](lync-server-2013-migrating-lync-online-users-to-lync-on-premises.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

