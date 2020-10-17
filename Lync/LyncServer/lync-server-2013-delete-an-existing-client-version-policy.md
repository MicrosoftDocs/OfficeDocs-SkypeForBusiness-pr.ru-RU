---
title: 'Lync Server 2013: удаление существующей политики версий клиентов'
description: 'Lync Server 2013: удаление существующей политики версий клиентов.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete an existing client version policy
ms:assetid: b88aaa25-97ff-4eb6-bd34-b97332cd6890
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ923064(v=OCS.15)
ms:contentKeyID: 50675349
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1328d54790b2a7856fa2776bb59feeb515bab1cf
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553665"
---
# <a name="delete-an-existing-client-version-policy-in-lync-server-2013"></a><span data-ttu-id="f6470-103">Удаление существующей политики версий клиентов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f6470-103">Delete an existing client version policy in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f6470-104">_**Последнее изменение темы:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="f6470-104">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="f6470-105">Если вы хотите удалить ранее настроенную политику версий клиентов, вы можете удалить ее из панели управления Lync Server 2013 или командной консоли Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f6470-105">If you want to delete a client version policy that was previously configured, you can delete it from Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span>

<div>

## <a name="to-delete-client-version-policies-by-using-lync-server-control-panel"></a><span data-ttu-id="f6470-106">Удаление политик версий клиентов с помощью панели управления Lync Server</span><span class="sxs-lookup"><span data-stu-id="f6470-106">To delete client version policies by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="f6470-107">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="f6470-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="f6470-108">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f6470-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="f6470-109">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="f6470-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="f6470-110">В левой панели навигации щелкните элемент **Клиенты**, а затем нажмите кнопку навигации для **политики версий клиентов** .</span><span class="sxs-lookup"><span data-stu-id="f6470-110">In the left navigation bar, click **Clients**, and then click the **Client Version Policy** navigation button.</span></span>

4.  <span data-ttu-id="f6470-111">На странице **Политика версий клиентов** выберите политику или политики версий клиентов, которые нужно удалить, нажмите кнопку **изменить**, а затем нажмите кнопку **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="f6470-111">On the **Client Version Policy** page, select the client version policy or policies you want to delete, click **Edit**, and then click **Delete**.</span></span>

</div>

<div>

## <a name="deleting-client-version-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="f6470-112">Удаление политик версий клиентов с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f6470-112">Deleting Client Version Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="f6470-113">Политики версий клиентов можно удалить с помощью командлета **Remove – CsClientVersionPolicy** .</span><span class="sxs-lookup"><span data-stu-id="f6470-113">You can delete client version policies by using the **Remove-CsClientVersionPolicy** cmdlet.</span></span> <span data-ttu-id="f6470-114">Этот командлет можно запустить либо из командной консоли Lync Server 2013, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f6470-114">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="f6470-115">Сведения об использовании удаленной оболочки Windows PowerShell для подключения к Lync Server приведены в статье "Краткое руководство по управлению Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" в статье Lync Server Windows PowerShell в блоге [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="f6470-115">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-specific-client-version-policy"></a><span data-ttu-id="f6470-116">Удаление определенной политики версий клиентов</span><span class="sxs-lookup"><span data-stu-id="f6470-116">To remove a specific client version policy</span></span>

  - <span data-ttu-id="f6470-117">Эта команда удаляет политику версий клиентов, примененную к сайту Redmond:</span><span class="sxs-lookup"><span data-stu-id="f6470-117">This command deletes the client version policy applied to the Redmond site:</span></span>
    
        Remove-CsClientVersionPolicy -Identity site:Redmond

</div>

<div>

## <a name="to-remove-all-the-client-version-policies-applied-to-the-site-scope"></a><span data-ttu-id="f6470-118">Удаление всех политик версий клиентов, примененных к области сайта</span><span class="sxs-lookup"><span data-stu-id="f6470-118">To remove all the client version policies applied to the site scope</span></span>

  - <span data-ttu-id="f6470-119">Эта команда удаляет все политики версий клиентов, настроенные на уровне сайта:</span><span class="sxs-lookup"><span data-stu-id="f6470-119">This command removes all the client version policies configured at the site scope:</span></span>
    
        Get-CsClientVersionPolicy -Fiter "site:*" | Remove-CsClientVersionPolicy

</div>

<div>

## <a name="to-remove-client-version-policies-that-do-not-include-a-specific-user-agent"></a><span data-ttu-id="f6470-120">Удаление политик версий клиентов, не включающих определенный агент пользователя</span><span class="sxs-lookup"><span data-stu-id="f6470-120">To remove client version policies that do not include a specific user agent</span></span>

  - <span data-ttu-id="f6470-121">Эта команда удаляет все политики версий клиентов, которые не включают правило для агента пользователя Windows Phone Lync (Вплинк):</span><span class="sxs-lookup"><span data-stu-id="f6470-121">And this command removes any client version policies that do not include a rule for the Windows Phone Lync (WPLync) user agent:</span></span>
    
        Get-CsClientVersionPolicy | Where-Object {$_.Rules -notmatch "UserAgent=WPLync" | Remove-CsClientVersionPolicy

</div>

<span data-ttu-id="f6470-122">Дополнительные сведения см. в разделе справки для командлета [Remove – CsClientVersionPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsClientVersionPolicy) .</span><span class="sxs-lookup"><span data-stu-id="f6470-122">For details, see the Help topic for the [Remove-CsClientVersionPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsClientVersionPolicy) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

