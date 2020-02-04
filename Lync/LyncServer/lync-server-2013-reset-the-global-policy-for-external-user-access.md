---
title: 'Lync Server 2013: сброс глобальной политики для доступа внешних пользователей'
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
ms.openlocfilehash: 971239018f3a8e1bcc92c036f50ed36616256ac7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723759"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="reset-the-global-policy-for-external-user-access-in-lync-server-2013"></a><span data-ttu-id="c4ee6-102">Сброс глобальной политики для доступа внешних пользователей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c4ee6-102">Reset the global policy for external user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c4ee6-103">_**Тема последнего изменения:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="c4ee6-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="c4ee6-104">Вы не можете полностью удалить глобальную политику.</span><span class="sxs-lookup"><span data-stu-id="c4ee6-104">You cannot completely delete a global policy.</span></span> <span data-ttu-id="c4ee6-105">Параметр " **Удалить** " в глобальной политике используется только для сброса глобальной политики в параметры по умолчанию, которые не включают поддержку каких – либо параметров доступа внешних пользователей.</span><span class="sxs-lookup"><span data-stu-id="c4ee6-105">Using the **Delete** option on the global policy only resets the global policy to the default settings, which do not include support for any external user access options.</span></span>

<div>

## <a name="to-reset-the-global-policy-to-the-default-settings"></a><span data-ttu-id="c4ee6-106">Восстановление параметров глобальной политики по умолчанию</span><span class="sxs-lookup"><span data-stu-id="c4ee6-106">To reset the global policy to the default settings</span></span>

1.  <span data-ttu-id="c4ee6-107">Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="c4ee6-107">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="c4ee6-108">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c4ee6-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="c4ee6-109">Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="c4ee6-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="c4ee6-110">На панели навигации слева выберите **внешний пользовательский доступ**и нажмите кнопку **Политика внешних доступа**.</span><span class="sxs-lookup"><span data-stu-id="c4ee6-110">In the left navigation bar, click **External User Access**, click **External Access Policy**.</span></span>

4.  <span data-ttu-id="c4ee6-111">На вкладке **внешняя политика доступа** выберите глобальную политику, нажмите кнопку **изменить**, а затем выберите команду **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="c4ee6-111">On the **External Access Policy** tab, click the global policy, click **Edit**, and then click **Delete**.</span></span>

5.  <span data-ttu-id="c4ee6-112">Когда появится запрос на подтверждение удаления, нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="c4ee6-112">When prompted to confirm the deletion, click **OK**.</span></span> <span data-ttu-id="c4ee6-113">В верхней части страницы появится сообщение о том, что была выполнена сброс глобальной политики.</span><span class="sxs-lookup"><span data-stu-id="c4ee6-113">A message appears at the top of the page informing you that the global policy has been reset.</span></span>

</div>

<div>

## <a name="resetting-the-global-external-access-policy-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="c4ee6-114">Сброс глобальной политики внешнего доступа с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c4ee6-114">Resetting the Global External Access Policy by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="c4ee6-115">Глобальную политику внешнего доступа можно сбросить с помощью Windows PowerShell и командлета Remove-Ксекстерналакцессполици.</span><span class="sxs-lookup"><span data-stu-id="c4ee6-115">The global external access policy can be reset by using Windows PowerShell and the Remove-CsExternalAccessPolicy cmdlet.</span></span> <span data-ttu-id="c4ee6-116">Этот командлет можно выполнить либо из управляющей оболочки Lync Server 2013, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c4ee6-116">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session Windows PowerShell.</span></span> <span data-ttu-id="c4ee6-117">Подробнее об использовании удаленной оболочки Windows PowerShell для подключения к серверу Lync Server можно найти в статье "Краткое руководство по работе с Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" на [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)веб-сервере Lync Server Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c4ee6-117">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-reset-the-global-external-access-policy"></a><span data-ttu-id="c4ee6-118">Сброс глобальной политики внешнего доступа</span><span class="sxs-lookup"><span data-stu-id="c4ee6-118">To reset the global external access policy</span></span>

  - <span data-ttu-id="c4ee6-119">Эта команда сбрасывает глобальную политику внешнего доступа:</span><span class="sxs-lookup"><span data-stu-id="c4ee6-119">This command resets the global external access policy:</span></span>
    
        Remove-CsExternalAccessPolicy -Identity "global"

</div>

<span data-ttu-id="c4ee6-120">Дополнительные сведения можно найти в разделе справки по командлету [Remove-ксекстерналакцессполици](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy) .</span><span class="sxs-lookup"><span data-stu-id="c4ee6-120">For more information, see the help topic for the [Remove-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

