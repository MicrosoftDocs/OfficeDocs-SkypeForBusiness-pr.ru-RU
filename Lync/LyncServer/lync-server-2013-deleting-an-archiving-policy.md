---
title: 'Lync Server 2013: Удаление политики архивации'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting an Archiving policy
ms:assetid: 4739a691-41cc-4128-8bb8-6d5a4c02107a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520989(v=OCS.15)
ms:contentKeyID: 48184043
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 926cc7e45fe3e57c189b01ff92da49342506dc2b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763077"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deleting-an-archiving-policy-in-lync-server-2013"></a><span data-ttu-id="55157-102">Удаление политики архивации в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="55157-102">Deleting an Archiving policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="55157-103">_**Тема последнего изменения:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="55157-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="55157-104">Вы можете удалить политику пользователей или политику сайта.</span><span class="sxs-lookup"><span data-stu-id="55157-104">You can delete a user policy or site policy.</span></span> <span data-ttu-id="55157-105">Невозможно удалить глобальную политику.</span><span class="sxs-lookup"><span data-stu-id="55157-105">The global policy cannot be removed.</span></span> <span data-ttu-id="55157-106">Если вы попытаетесь удалить глобальную политику, Lync Server 2013 автоматически восстанавливает значения по умолчанию для этой политики.</span><span class="sxs-lookup"><span data-stu-id="55157-106">If you try to delete the global policy, Lync Server 2013 automatically resets the policy to the default values.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="55157-107">Если вы включили интеграцию Microsoft Exchange для развертывания, политики Exchange определяют, разрешено ли архивирование для пользователей, использующих Exchange 2013, и почтовые ящики, которые помещаются на хранение на месте.</span><span class="sxs-lookup"><span data-stu-id="55157-107">If you enabled Microsoft Exchange integration for your deployment, Exchange policies control whether archiving is enabled for the users who are homed on Exchange 2013 and have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="55157-108">Подробности можно найти в разделе <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Настройка политик архивации в Lync server 2013 при использовании интеграции с Exchange Server</A> в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="55157-108">For details, see <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Setting up policies for Archiving in Lync Server 2013 when using Exchange Server integration</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="to-delete-a-user-or-site-policy-for-archiving"></a><span data-ttu-id="55157-109">Удаление политики пользователя или сайта для архивации</span><span class="sxs-lookup"><span data-stu-id="55157-109">To delete a user or site policy for archiving</span></span>

1.  <span data-ttu-id="55157-110">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsArchivingAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="55157-110">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="55157-111">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="55157-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="55157-112">Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="55157-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="55157-113">На левой панели навигации щелкните **Мониторинг и архивация**, а затем щелкните **Политика архивации**.</span><span class="sxs-lookup"><span data-stu-id="55157-113">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>

4.  <span data-ttu-id="55157-114">В списке политик архивации щелкните политику пользователей или сайта, которую следует удалить, щелкните **Изменить**, затем **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="55157-114">In the list of archiving policies, click the user or site policy that you want to delete, click **Edit**, and then click **Delete**.</span></span>

5.  <span data-ttu-id="55157-115">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="55157-115">Click **Commit**.</span></span>

</div>

<div>

## <a name="removing-archiving-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="55157-116">Удаление политик архивации с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="55157-116">Removing Archiving Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="55157-117">Политики архивации можно удалить с помощью Windows PowerShell и командлета **Remove-ксарчивингполици** .</span><span class="sxs-lookup"><span data-stu-id="55157-117">Archiving policies can be deleted by using Windows PowerShell and the **Remove-CsArchivingPolicy** cmdlet.</span></span> <span data-ttu-id="55157-118">Этот командлет можно выполнить либо из управляющей оболочки Lync Server 2013, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="55157-118">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="55157-119">Подробнее об использовании удаленной оболочки Windows PowerShell для подключения к серверу Lync Server можно найти в статье "Краткое руководство по работе с Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" на [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)веб-сервере Lync Server Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="55157-119">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-specified-archiving-policy"></a><span data-ttu-id="55157-120">Удаление указанной политики архивации</span><span class="sxs-lookup"><span data-stu-id="55157-120">To remove a specified archiving policy</span></span>

  - <span data-ttu-id="55157-121">Например, **Remove-ксарчивингполици** удаляет политику с сайтом удостоверений: Redmond.</span><span class="sxs-lookup"><span data-stu-id="55157-121">As an example, **Remove-CsArchivingPolicy** deletes the policy with the Identity site:Redmond.</span></span> <span data-ttu-id="55157-122">Обратите внимание на то, что при удалении политики сайта Политика сайта автоматически управляется пользователями, которые раньше настроили политикой для архивации.</span><span class="sxs-lookup"><span data-stu-id="55157-122">Note that, when a policy configured at the site scope is deleted, users previously managed by the site policy will automatically be governed by the global archiving policy instead.</span></span> <span data-ttu-id="55157-123">Следующая команда удаляет архивирование, примененное к сайту Redmond.</span><span class="sxs-lookup"><span data-stu-id="55157-123">The following command removes the archiving applied to the Redmond site:</span></span>
    
        Remove-CsArchivingPolicy -Identity site:Redmond

</div>

<div>

## <a name="to-remove-all-the-archiving-policies-applied-to-the-per-user-scope"></a><span data-ttu-id="55157-124">Удаление всех политик архивации, примененных к области "на пользователя"</span><span class="sxs-lookup"><span data-stu-id="55157-124">To remove all the archiving policies applied to the per-user scope</span></span>

  - <span data-ttu-id="55157-125">Эта команда удаляет все политики архивации, примененные к области "на пользователя".</span><span class="sxs-lookup"><span data-stu-id="55157-125">This command removes all the archiving policies applied to the per-user scope:</span></span>
    
        Get-CsArchivingPolicy -Filter "tag:*" | Remove-CsArchivingPolicy

</div>

<div>

## <a name="to-remove-all-the-archiving-policies-that-disable-internal-archiving"></a><span data-ttu-id="55157-126">Удаление всех политик архивации, исключающих внутреннее архивирование</span><span class="sxs-lookup"><span data-stu-id="55157-126">To remove all the archiving policies that disable internal archiving</span></span>

  - <span data-ttu-id="55157-127">Данная команда удаляет все политики архивации, в которых отключена внутренняя архивация:</span><span class="sxs-lookup"><span data-stu-id="55157-127">This command removes all the archiving policies where internal archiving has been disabled:</span></span>
    
        Get-CsArchivingPolicy | Where-Object {$_.ArchiveInternal -eq $False} | Remove-CsArchivingPolicy

</div>

<span data-ttu-id="55157-128">Дополнительные сведения можно найти в разделе справки по командлету [Remove-ксарчивингполици](https://docs.microsoft.com/powershell/module/skype/Remove-CsArchivingPolicy) .</span><span class="sxs-lookup"><span data-stu-id="55157-128">For more information, see the help topic for the [Remove-CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsArchivingPolicy) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="55157-129">См. также</span><span class="sxs-lookup"><span data-stu-id="55157-129">See Also</span></span>


[<span data-ttu-id="55157-130">Управление архивированием внутренней и внешней связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="55157-130">Managing the Archiving of internal and external communications in Lync Server 2013</span></span>](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

