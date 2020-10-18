---
title: 'Lync Server 2013: сброс глобальной политики для доступа внешних пользователей'
description: 'Lync Server 2013: сбросьте глобальную политику для доступа внешних пользователей.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Reset the global policy for external user access
ms:assetid: 8207e1b1-de9e-461f-975f-fcc5c526849a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182545(v=OCS.15)
ms:contentKeyID: 48184675
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 061f86fd454cea851a8e8cfbd4f40921daeecd98
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577835"
---
# <a name="reset-the-global-policy-for-external-user-access-in-lync-server-2013"></a><span data-ttu-id="7adbf-103">Сброс глобальной политики для доступа внешних пользователей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7adbf-103">Reset the global policy for external user access in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7adbf-104">_**Последнее изменение темы:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="7adbf-104">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="7adbf-p101">Вы не можете полностью удалить глобальную политику. При использовании команды **Удалить** для глобальной политики восстанавливаются параметры по умолчанию, не поддерживающие какие-либо параметры доступа внешних пользователей.</span><span class="sxs-lookup"><span data-stu-id="7adbf-p101">You cannot completely delete a global policy. Using the **Delete** option on the global policy only resets the global policy to the default settings, which do not include support for any external user access options.</span></span>

<div>

## <a name="to-reset-the-global-policy-to-the-default-settings"></a><span data-ttu-id="7adbf-107">Восстановление параметров глобальной политики по умолчанию</span><span class="sxs-lookup"><span data-stu-id="7adbf-107">To reset the global policy to the default settings</span></span>

1.  <span data-ttu-id="7adbf-108">Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначается роли CsAdministrator, войдите на любой компьютер во внутреннем развертывании.</span><span class="sxs-lookup"><span data-stu-id="7adbf-108">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="7adbf-109">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7adbf-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="7adbf-110">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="7adbf-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="7adbf-111">В левой панели навигации щелкните элемент **Доступ внешних пользователей**, а затем выберите **Политика внешнего доступа**.</span><span class="sxs-lookup"><span data-stu-id="7adbf-111">In the left navigation bar, click **External User Access**, click **External Access Policy**.</span></span>

4.  <span data-ttu-id="7adbf-112">На вкладке **Политика внешнего доступа** щелкните глобальную политику, нажмите кнопку **Изменить** (Изменить) и затем нажмите **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="7adbf-112">On the **External Access Policy** tab, click the global policy, click **Edit**, and then click **Delete**.</span></span>

5.  <span data-ttu-id="7adbf-p103">При отображении запроса на подтверждение нажмите кнопку **ОК**. В верхней части страницы появится сообщение о сбросе глобальной политики.</span><span class="sxs-lookup"><span data-stu-id="7adbf-p103">When prompted to confirm the deletion, click **OK**. A message appears at the top of the page informing you that the global policy has been reset.</span></span>

</div>

<div>

## <a name="resetting-the-global-external-access-policy-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="7adbf-115">Сброс глобальной политики внешнего доступа с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="7adbf-115">Resetting the Global External Access Policy by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="7adbf-116">Глобальную политику внешнего доступа можно сбросить с помощью Windows PowerShell и командлета Remove-CsExternalAccessPolicy.</span><span class="sxs-lookup"><span data-stu-id="7adbf-116">The global external access policy can be reset by using Windows PowerShell and the Remove-CsExternalAccessPolicy cmdlet.</span></span> <span data-ttu-id="7adbf-117">Этот командлет можно запустить из командной консоли Lync Server 2013 или из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7adbf-117">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session Windows PowerShell.</span></span> <span data-ttu-id="7adbf-118">Сведения об использовании удаленной оболочки Windows PowerShell для подключения к Lync Server приведены в статье "Краткое руководство по управлению Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" в статье Lync Server Windows PowerShell в блоге [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="7adbf-118">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-reset-the-global-external-access-policy"></a><span data-ttu-id="7adbf-119">Сброс глобальной политики внешнего доступа</span><span class="sxs-lookup"><span data-stu-id="7adbf-119">To reset the global external access policy</span></span>

  - <span data-ttu-id="7adbf-120">Следующая команда сбрасывает глобальную политику внешнего доступа:</span><span class="sxs-lookup"><span data-stu-id="7adbf-120">This command resets the global external access policy:</span></span>
    
        Remove-CsExternalAccessPolicy -Identity "global"

</div>

<span data-ttu-id="7adbf-121">Для получения дополнительных сведений обратитесь к разделу "Справка" для командлета [Remove – CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy) .</span><span class="sxs-lookup"><span data-stu-id="7adbf-121">For more information, see the help topic for the [Remove-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

