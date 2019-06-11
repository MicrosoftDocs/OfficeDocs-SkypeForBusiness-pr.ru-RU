---
title: 'Lync Server 2013: удаление существующей политики версии клиента'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Delete an existing client version policy
ms:assetid: b88aaa25-97ff-4eb6-bd34-b97332cd6890
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ923064(v=OCS.15)
ms:contentKeyID: 50675349
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0adc3ab47b3b441eff900c6a9202a782e524c22c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834622"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-an-existing-client-version-policy-in-lync-server-2013"></a><span data-ttu-id="6d02c-102">Удаление существующей политики версии клиента в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6d02c-102">Delete an existing client version policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6d02c-103">_**Тема последнего изменения:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="6d02c-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="6d02c-104">Если вы хотите удалить политику версии клиента, настроенную ранее, вы можете удалить ее из панели управления Lync Server 2013 или оболочки управления Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6d02c-104">If you want to delete a client version policy that was previously configured, you can delete it from Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span>

<div>

## <a name="to-delete-client-version-policies-by-using-lync-server-control-panel"></a><span data-ttu-id="6d02c-105">Удаление политик версий клиента с помощью панели управления Lync Server</span><span class="sxs-lookup"><span data-stu-id="6d02c-105">To delete client version policies by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="6d02c-106">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="6d02c-106">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="6d02c-107">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6d02c-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="6d02c-108">Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="6d02c-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="6d02c-109">На панели навигации слева выберите пункт **Клиенты**и нажмите кнопку Переход на **политику версии клиента** .</span><span class="sxs-lookup"><span data-stu-id="6d02c-109">In the left navigation bar, click **Clients**, and then click the **Client Version Policy** navigation button.</span></span>

4.  <span data-ttu-id="6d02c-110">На странице **политики версия клиента** выберите политику или политики, которые вы хотите удалить, и нажмите кнопку **изменить**, а затем — **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="6d02c-110">On the **Client Version Policy** page, select the client version policy or policies you want to delete, click **Edit**, and then click **Delete**.</span></span>

</div>

<div>

## <a name="deleting-client-version-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="6d02c-111">Удаление политик версий клиента с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="6d02c-111">Deleting Client Version Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="6d02c-112">Вы можете удалить политики версии клиента с помощью командлета **Remove-ксклиентверсионполици** .</span><span class="sxs-lookup"><span data-stu-id="6d02c-112">You can delete client version policies by using the **Remove-CsClientVersionPolicy** cmdlet.</span></span> <span data-ttu-id="6d02c-113">Этот командлет можно выполнить либо из управляющей оболочки Lync Server 2013, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6d02c-113">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="6d02c-114">Подробнее об использовании удаленной оболочки Windows PowerShell для подключения к серверу Lync Server можно найти в статье "Краткое руководство по работе с Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" на [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)веб-сервере Lync Server Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6d02c-114">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-specific-client-version-policy"></a><span data-ttu-id="6d02c-115">Удаление политики для определенной версии клиента</span><span class="sxs-lookup"><span data-stu-id="6d02c-115">To remove a specific client version policy</span></span>

  - <span data-ttu-id="6d02c-116">Эта команда удаляет политику версии клиента, примененную к сайту Redmond.</span><span class="sxs-lookup"><span data-stu-id="6d02c-116">This command deletes the client version policy applied to the Redmond site:</span></span>
    
        Remove-CsClientVersionPolicy -Identity site:Redmond

</div>

<div>

## <a name="to-remove-all-the-client-version-policies-applied-to-the-site-scope"></a><span data-ttu-id="6d02c-117">Удаление всех политик версии клиента, примененных к области сайта</span><span class="sxs-lookup"><span data-stu-id="6d02c-117">To remove all the client version policies applied to the site scope</span></span>

  - <span data-ttu-id="6d02c-118">Эта команда удаляет все политики версии клиента, настроенные на уровне сайта.</span><span class="sxs-lookup"><span data-stu-id="6d02c-118">This command removes all the client version policies configured at the site scope:</span></span>
    
        Get-CsClientVersionPolicy -Fiter "site:*" | Remove-CsClientVersionPolicy

</div>

<div>

## <a name="to-remove-client-version-policies-that-do-not-include-a-specific-user-agent"></a><span data-ttu-id="6d02c-119">Удаление политик версий клиентов, которые не включают определенный агент пользователя</span><span class="sxs-lookup"><span data-stu-id="6d02c-119">To remove client version policies that do not include a specific user agent</span></span>

  - <span data-ttu-id="6d02c-120">И эта команда удаляет все политики версий клиентов, которые не включают правило для агента пользователя Windows Phone Lync (Вплинк):</span><span class="sxs-lookup"><span data-stu-id="6d02c-120">And this command removes any client version policies that do not include a rule for the Windows Phone Lync (WPLync) user agent:</span></span>
    
        Get-CsClientVersionPolicy | Where-Object {$_.Rules -notmatch "UserAgent=WPLync" | Remove-CsClientVersionPolicy

</div>

<span data-ttu-id="6d02c-121">Дополнительные сведения можно найти в разделе справки по командлету [Remove-ксклиентверсионполици](https://docs.microsoft.com/powershell/module/skype/Remove-CsClientVersionPolicy) .</span><span class="sxs-lookup"><span data-stu-id="6d02c-121">For details, see the Help topic for the [Remove-CsClientVersionPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsClientVersionPolicy) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

