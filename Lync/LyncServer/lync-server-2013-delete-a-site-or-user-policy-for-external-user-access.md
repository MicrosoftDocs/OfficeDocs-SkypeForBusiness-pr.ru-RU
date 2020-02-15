---
title: 'Lync Server 2013: Удаление политики сайта или пользователя для доступа внешних пользователей'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete a site or user policy for external user access
ms:assetid: 6d907507-825b-4354-9c03-337a459f72de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521013(v=OCS.15)
ms:contentKeyID: 48184455
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5c21b58715814b5bf08023662bff61b004b51896
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036137"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-a-site-or-user-policy-for-external-user-access-in-lync-server-2013"></a><span data-ttu-id="4662a-102">Удаление сайта или пользовательской политики для доступа внешних пользователей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4662a-102">Delete a site or user policy for external user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4662a-103">_**Последнее изменение темы:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="4662a-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="4662a-104">Вы можете удалить любую политику сайта или пользователя, указанную в панели управления Lync Server на странице " **Политика внешнего доступа** ".</span><span class="sxs-lookup"><span data-stu-id="4662a-104">You can delete any site or user policy that is listed in Lync Server Control Panel on the **External Access Policy** page.</span></span> <span data-ttu-id="4662a-105">При удалении глобальной политики она на самом деле не удаляется, а восстанавливаются параметры по умолчанию, не включающие поддержку доступа внешних пользователей.</span><span class="sxs-lookup"><span data-stu-id="4662a-105">Deleting the global policy does not actually delete it, but only resets it to the default settings, which do not include support for any external user access options.</span></span> <span data-ttu-id="4662a-106">Дополнительные сведения о сбросе глобальной политики приведены в статье [Reset The Global Policy for External User Access in Lync Server 2013](lync-server-2013-reset-the-global-policy-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="4662a-106">For details about resetting the global policy, see [Reset the global policy for external user access in Lync Server 2013](lync-server-2013-reset-the-global-policy-for-external-user-access.md).</span></span>

<div>

## <a name="to-delete-a-site-or-user-policy-for-external-user-access"></a><span data-ttu-id="4662a-107">Удаление политика узла или пользователя для доступа внешних пользователей</span><span class="sxs-lookup"><span data-stu-id="4662a-107">To delete a site or user policy for external user access</span></span>

1.  <span data-ttu-id="4662a-108">Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначается роли CsAdministrator, войдите на любой компьютер во внутреннем развертывании.</span><span class="sxs-lookup"><span data-stu-id="4662a-108">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="4662a-109">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4662a-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="4662a-110">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="4662a-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="4662a-111">Щелкните **Доступ для внешних пользователей** и выберите **Политика внешнего доступа**.</span><span class="sxs-lookup"><span data-stu-id="4662a-111">Click **External User Access**, click **External Access Policy**.</span></span>

4.  <span data-ttu-id="4662a-112">На вкладке **Политика внешнего доступа** щелкните политику узла или пользователя, которую нужно удалить, нажмите кнопку **Изменить** и затем нажмите **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="4662a-112">On the **External Access Policy** tab, click the site or user policy you want to delete, click **Edit**, and then click **Delete**.</span></span>

5.  <span data-ttu-id="4662a-113">При отображении запроса на подтверждение нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="4662a-113">When prompted to confirm the deletion, click **OK**.</span></span>

</div>

<div>

## <a name="removing-pin-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="4662a-114">Удаление политик ПИН-кодов с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="4662a-114">Removing PIN Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="4662a-115">Политики внешнего доступа можно удалить с помощью Windows PowerShell и командлета Remove – CsExternalAccessPolicy.</span><span class="sxs-lookup"><span data-stu-id="4662a-115">External access policies can be deleted by using Windows PowerShell and the Remove-CsExternalAccessPolicy cmdlet.</span></span> <span data-ttu-id="4662a-116">Этот командлет можно запустить либо из командной консоли Lync Server 2013, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4662a-116">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="4662a-117">Сведения об использовании удаленной оболочки Windows PowerShell для подключения к Lync Server приведены в статье "Краткое руководство по управлению Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" в [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)статье Lync Server Windows PowerShell в блоге.</span><span class="sxs-lookup"><span data-stu-id="4662a-117">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-specific-external-access-policy"></a><span data-ttu-id="4662a-118">Удаление определенной политики внешнего доступа</span><span class="sxs-lookup"><span data-stu-id="4662a-118">To remove a specific external access policy</span></span>

  - <span data-ttu-id="4662a-119">Эта команда удаляет политику внешнего доступа для узла Redmond:</span><span class="sxs-lookup"><span data-stu-id="4662a-119">This command removes the external access policy applied to the Redmond site:</span></span>
    
        Remove-CsExternalAccessPolicy -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-the-external-access-policies-applied-to-the-per-user-scope"></a><span data-ttu-id="4662a-120">Удаление всех политик внешнего доступа, примененных к области "на пользователя"</span><span class="sxs-lookup"><span data-stu-id="4662a-120">To remove all the external access policies applied to the per-user scope</span></span>

  - <span data-ttu-id="4662a-121">Эта команда удаляет все политики внешнего доступа, настроенные на уровне пользователя:</span><span class="sxs-lookup"><span data-stu-id="4662a-121">This command removes all the external access policies configured at the per-user scope:</span></span>
    
        Get-CsExternalAccessPolicy -Filter "tag:*" | Remove-CsExternalAccessPolicy

</div>

<div>

## <a name="to-remove-all-the-external-access-policies-where-outside-user-access-is-disabled"></a><span data-ttu-id="4662a-122">Удаление всех политик внешнего доступа, для которых отключен доступ извне пользователя</span><span class="sxs-lookup"><span data-stu-id="4662a-122">To remove all the external access policies where outside user access is disabled</span></span>

  - <span data-ttu-id="4662a-123">Эта команда удаляет все политики внешнего доступа, в который доступ внешних пользователей отключен:</span><span class="sxs-lookup"><span data-stu-id="4662a-123">This command deletes all the external access policies where outside user access has been disabled:</span></span>
    
        Get-CsExternalAccessPolicy | Where-Object {$_.EnableOutsideAccess -eq $False} | Remove-CsExternalAccessPolicy

</div>

<span data-ttu-id="4662a-124">Для получения дополнительных сведений обратитесь к разделу "Справка" для командлета [Remove – CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy) .</span><span class="sxs-lookup"><span data-stu-id="4662a-124">For more information, see the help topic for the [Remove-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

