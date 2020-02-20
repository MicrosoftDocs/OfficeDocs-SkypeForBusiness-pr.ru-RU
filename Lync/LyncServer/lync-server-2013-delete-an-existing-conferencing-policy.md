---
title: 'Lync Server 2013: удаление существующей политики конференц-связи'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete an existing conferencing policy
ms:assetid: 709ed771-790f-4bf1-a4de-b37ca5168688
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688089(v=OCS.15)
ms:contentKeyID: 49733688
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bcdbb4ec3c7ea59b17fed97990190881997e6602
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154471"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="delete-an-existing-conferencing-policy-in-lync-server-2013"></a><span data-ttu-id="fbfc9-102">Удаление существующей политики конференц-связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fbfc9-102">Delete an existing conferencing policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fbfc9-103">_**Последнее изменение темы:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="fbfc9-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="fbfc9-104">Выполните приведенные действия, чтобы удалить политику конференц-связи уровня пользователя или уровня сайта.</span><span class="sxs-lookup"><span data-stu-id="fbfc9-104">Follow these steps to delete a user-level or a site-level conferencing policy.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="fbfc9-105">Вы не можете удалить глобальную политику конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="fbfc9-105">You cannot delete the global conferencing policy.</span></span>



</div>

<div>

## <a name="to-delete-a-site-or-user-conferencing-policy"></a><span data-ttu-id="fbfc9-106">Удаление политики конференц-связи для узла или пользователя</span><span class="sxs-lookup"><span data-stu-id="fbfc9-106">To delete a site or user conferencing policy</span></span>

1.  <span data-ttu-id="fbfc9-107">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="fbfc9-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="fbfc9-108">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="fbfc9-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="fbfc9-109">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="fbfc9-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="fbfc9-110">В левой панели навигации щелкните **Конференция**, а затем выберите **Политика конференц-связи**.</span><span class="sxs-lookup"><span data-stu-id="fbfc9-110">In the left navigation bar, click **Conferencing** and then click **Conferencing Policy**.</span></span>

4.  <span data-ttu-id="fbfc9-111">В списке политик конференций выберите политику сайта или пользователя, которую нужно удалить, нажмите кнопку **изменить**, а затем нажмите кнопку **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="fbfc9-111">In the list of conferencing policies, click the site or user policy that you want to delete, click **Edit**, and then click **Delete**.</span></span>

</div>

<div>

## <a name="removing-conferencing-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="fbfc9-112">Удаление политик конференц-связи с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="fbfc9-112">Removing Conferencing Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="fbfc9-113">Политики конференц-связи можно удалить с помощью командной консоли Lync Server и командлета **Remove-CsConferencingPolicy** .</span><span class="sxs-lookup"><span data-stu-id="fbfc9-113">You can delete conferencing policies by using Lync Server Management Shell and the **Remove-CsConferencingPolicy** cmdlet.</span></span> <span data-ttu-id="fbfc9-114">Этот командлет можно выполнить из командной консоли Lync Server 2013 или из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fbfc9-114">You can run this cmdlet from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="fbfc9-115">Сведения об использовании удаленной оболочки Windows PowerShell для подключения к Lync Server приведены в статье "Краткое руководство по управлению Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" в [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)статье Lync Server Windows PowerShell в блоге.</span><span class="sxs-lookup"><span data-stu-id="fbfc9-115">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-specified-conferencing-policy"></a><span data-ttu-id="fbfc9-116">Удаление указанной политики конференц-связи</span><span class="sxs-lookup"><span data-stu-id="fbfc9-116">To remove a specified conferencing policy</span></span>

  - <span data-ttu-id="fbfc9-117">Следующая команда удаляет политику конференц-связи с идентификатором RedmondConferencingPolicy:</span><span class="sxs-lookup"><span data-stu-id="fbfc9-117">The following command removes the conferencing policy with the Identity RedmondConferencingPolicy:</span></span>
    
        Remove-CsConferencingPolicy -Identity "RedmondConferencingPolicy"

</div>

<div>

## <a name="to-remove-all-of-the-conferencing-policies-applied-to-the-per-user-scope"></a><span data-ttu-id="fbfc9-118">Удаление всех политик конференц-связи, применяемых на уровне пользователя</span><span class="sxs-lookup"><span data-stu-id="fbfc9-118">To remove all of the conferencing policies applied to the per-user scope</span></span>

  - <span data-ttu-id="fbfc9-119">Следующая команда удаляет все политики конференц-связи, настроенные на уровне пользователя:</span><span class="sxs-lookup"><span data-stu-id="fbfc9-119">The following command removes all the conferencing policies configured at the per-user scope:</span></span>
    
        Get-CsConferencingPolicy -Filter "tag:*" | Remove-CsConferencingPolicy

</div>

<div>

## <a name="to-remove-all-of-the-conferencing-polices-that-allow-recording-by-external-users"></a><span data-ttu-id="fbfc9-120">Удаление всех политик конференц-связи, разрешающих запись внешними пользователями</span><span class="sxs-lookup"><span data-stu-id="fbfc9-120">To remove all of the conferencing polices that allow recording by external users</span></span>

  - <span data-ttu-id="fbfc9-121">Следующая команда удаляет все политики конференц-связи, разрешающие внешним пользователям записывать конференцию:</span><span class="sxs-lookup"><span data-stu-id="fbfc9-121">The following command deletes any conferencing policies that allow external users to record the conference:</span></span>
    
        Get-CsConferencingPolicy | Where-Object {$_.AllowExternalUsersToRecordMeetings -eq $True} | Remove-CsConferencingPolicy

</div>

<span data-ttu-id="fbfc9-122">Дополнительные сведения см. в разделе [Remove – CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsConferencingPolicy).</span><span class="sxs-lookup"><span data-stu-id="fbfc9-122">For details, see [Remove-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsConferencingPolicy).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

