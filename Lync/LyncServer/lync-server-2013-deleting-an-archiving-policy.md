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
ms.openlocfilehash: a09e06925f414782ce516091383381a44cb80c2c
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42206985"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deleting-an-archiving-policy-in-lync-server-2013"></a><span data-ttu-id="dcfd9-102">Удаление политики архивации в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dcfd9-102">Deleting an Archiving policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dcfd9-103">_**Последнее изменение темы:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="dcfd9-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="dcfd9-104">Можно удалить политику пользователей или сайта.</span><span class="sxs-lookup"><span data-stu-id="dcfd9-104">You can delete a user policy or site policy.</span></span> <span data-ttu-id="dcfd9-105">Глобальную политику удалить невозможно.</span><span class="sxs-lookup"><span data-stu-id="dcfd9-105">The global policy cannot be removed.</span></span> <span data-ttu-id="dcfd9-106">Если вы попытаетесь удалить глобальную политику, Lync Server 2013 автоматически сбрасывает ее до значений по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="dcfd9-106">If you try to delete the global policy, Lync Server 2013 automatically resets the policy to the default values.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="dcfd9-107">Если для развертывания включена интеграция с Microsoft Exchange, политики Exchange контролируют, включена ли архивация для пользователей, размещенных в Exchange 2013 и почтовые ящики, которые помещаются на удержание на месте.</span><span class="sxs-lookup"><span data-stu-id="dcfd9-107">If you enabled Microsoft Exchange integration for your deployment, Exchange policies control whether archiving is enabled for the users who are homed on Exchange 2013 and have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="dcfd9-108">Дополнительные сведения: <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Настройка политик архивации в Lync server 2013 при использовании интеграции с Exchange Server</A> в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="dcfd9-108">For details, see <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Setting up policies for Archiving in Lync Server 2013 when using Exchange Server integration</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="to-delete-a-user-or-site-policy-for-archiving"></a><span data-ttu-id="dcfd9-109">Удаление политики архивации для пользователей или сайта</span><span class="sxs-lookup"><span data-stu-id="dcfd9-109">To delete a user or site policy for archiving</span></span>

1.  <span data-ttu-id="dcfd9-110">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsArchivingAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="dcfd9-110">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="dcfd9-111">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="dcfd9-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="dcfd9-112">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="dcfd9-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="dcfd9-113">В левой панели навигации щелкните **мониторинг и архивация**, а затем щелкните **Политика архивации**.</span><span class="sxs-lookup"><span data-stu-id="dcfd9-113">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>

4.  <span data-ttu-id="dcfd9-114">В списке политик архивации щелкните политику пользователей или сайта, которую следует удалить, щелкните **Изменить**, затем **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="dcfd9-114">In the list of archiving policies, click the user or site policy that you want to delete, click **Edit**, and then click **Delete**.</span></span>

5.  <span data-ttu-id="dcfd9-115">Щелкните **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="dcfd9-115">Click **Commit**.</span></span>

</div>

<div>

## <a name="removing-archiving-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="dcfd9-116">Удаление политик архивации с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="dcfd9-116">Removing Archiving Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="dcfd9-117">Политики архивации можно удалить с помощью Windows PowerShell и командлета **Remove – CsArchivingPolicy** .</span><span class="sxs-lookup"><span data-stu-id="dcfd9-117">Archiving policies can be deleted by using Windows PowerShell and the **Remove-CsArchivingPolicy** cmdlet.</span></span> <span data-ttu-id="dcfd9-118">Этот командлет можно запустить либо из командной консоли Lync Server 2013, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="dcfd9-118">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="dcfd9-119">Сведения об использовании удаленной оболочки Windows PowerShell для подключения к Lync Server приведены в статье "Краткое руководство по управлению Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" в [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)статье Lync Server Windows PowerShell в блоге.</span><span class="sxs-lookup"><span data-stu-id="dcfd9-119">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-specified-archiving-policy"></a><span data-ttu-id="dcfd9-120">Удаление указанной политики архивации</span><span class="sxs-lookup"><span data-stu-id="dcfd9-120">To remove a specified archiving policy</span></span>

  - <span data-ttu-id="dcfd9-p105">В качестве примера командлет **Remove-CsArchivingPolicy** удаляет политику с использованием параметра Identity site:Redmond. Обратите внимание, что при удалении политики, настроенной на уровне сайта, пользователи, которые раньше управлялись политикой сайта, автоматически станут управляться глобальной политикой архивирования. Следующая команда удаляет параметры конфигурации архивации в сайте Redmond:</span><span class="sxs-lookup"><span data-stu-id="dcfd9-p105">As an example, **Remove-CsArchivingPolicy** deletes the policy with the Identity site:Redmond. Note that, when a policy configured at the site scope is deleted, users previously managed by the site policy will automatically be governed by the global archiving policy instead. The following command removes the archiving applied to the Redmond site:</span></span>
    
        Remove-CsArchivingPolicy -Identity site:Redmond

</div>

<div>

## <a name="to-remove-all-the-archiving-policies-applied-to-the-per-user-scope"></a><span data-ttu-id="dcfd9-124">Удаление всех политик архивации, примененных к области "на пользователя"</span><span class="sxs-lookup"><span data-stu-id="dcfd9-124">To remove all the archiving policies applied to the per-user scope</span></span>

  - <span data-ttu-id="dcfd9-125">Данная команда удаляет все политики архивации, примененные на уровне пользователей:</span><span class="sxs-lookup"><span data-stu-id="dcfd9-125">This command removes all the archiving policies applied to the per-user scope:</span></span>
    
        Get-CsArchivingPolicy -Filter "tag:*" | Remove-CsArchivingPolicy

</div>

<div>

## <a name="to-remove-all-the-archiving-policies-that-disable-internal-archiving"></a><span data-ttu-id="dcfd9-126">Удаление всех политик архивации, в которых отключена внутренняя Архивация</span><span class="sxs-lookup"><span data-stu-id="dcfd9-126">To remove all the archiving policies that disable internal archiving</span></span>

  - <span data-ttu-id="dcfd9-127">Данная команда удаляет все политики архивации, в которых отключена внутренняя архивация:</span><span class="sxs-lookup"><span data-stu-id="dcfd9-127">This command removes all the archiving policies where internal archiving has been disabled:</span></span>
    
        Get-CsArchivingPolicy | Where-Object {$_.ArchiveInternal -eq $False} | Remove-CsArchivingPolicy

</div>

<span data-ttu-id="dcfd9-128">Для получения дополнительных сведений обратитесь к разделу "Справка" для командлета [Remove – CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsArchivingPolicy) .</span><span class="sxs-lookup"><span data-stu-id="dcfd9-128">For more information, see the help topic for the [Remove-CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsArchivingPolicy) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="dcfd9-129">См. также</span><span class="sxs-lookup"><span data-stu-id="dcfd9-129">See Also</span></span>


[<span data-ttu-id="dcfd9-130">Управление архивацией внутренних и внешних коммуникаций в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dcfd9-130">Managing the Archiving of internal and external communications in Lync Server 2013</span></span>](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

