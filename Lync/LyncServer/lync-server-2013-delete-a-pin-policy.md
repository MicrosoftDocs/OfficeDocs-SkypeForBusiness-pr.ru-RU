---
title: 'Lync Server 2013: Удаление политики ПИН-кода'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Delete a PIN policy
ms:assetid: 7c378927-2e41-418e-9721-327021bd2e45
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521020(v=OCS.15)
ms:contentKeyID: 48184609
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 85b8f77056c61fbeed32ab06f6ce4296bc32105f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834645"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-a-pin-policy-in-lync-server-2013"></a><span data-ttu-id="a2a0b-102">Удаление политики ПИН-кода в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a2a0b-102">Delete a PIN policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a2a0b-103">_**Тема последнего изменения:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="a2a0b-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="a2a0b-104">Чтобы удалить политику персональных идентификационных номеров (политику ПИН-кодов), выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="a2a0b-104">Follow these steps to delete a personal identification number (PIN) policy.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a2a0b-105">Глобальную политику ПИН-кодов удалить нельзя.</span><span class="sxs-lookup"><span data-stu-id="a2a0b-105">You cannot delete the global PIN policy.</span></span>



</div>

<div>

## <a name="to-delete-a-pin-policy-in-lync-server-2013-control-panel"></a><span data-ttu-id="a2a0b-106">Удаление политики ПИН-кода в Lync Server 2013 панели управления</span><span class="sxs-lookup"><span data-stu-id="a2a0b-106">To delete a PIN policy in Lync Server 2013 Control Panel</span></span>

1.  <span data-ttu-id="a2a0b-107">Войдите в учетную запись пользователя, которая является членом группы Рткуниверсалсерверадминс (или имеет эквивалентные права пользователей) или назначьте роль Кссерверадминистратор или Ксадминистратор, выполните вход на любой компьютер в сети, в которой вы развернули Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a2a0b-107">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="a2a0b-108">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a2a0b-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="a2a0b-109">Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="a2a0b-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="a2a0b-110">В левой панели навигации последовательно выберите пункты **Безопасность** и **Политика ПИН-кода**.</span><span class="sxs-lookup"><span data-stu-id="a2a0b-110">In the left navigation bar, click **Security** and then click **PIN Policy**.</span></span>

4.  <span data-ttu-id="a2a0b-111">На странице **Политика ПИН-кода** в поле поиска полностью или частично введите имя политики, которую требуется удалить.</span><span class="sxs-lookup"><span data-stu-id="a2a0b-111">On the **PIN Policy** page, and in the search field, type all or part of the name of the policy you want to delete.</span></span>

5.  <span data-ttu-id="a2a0b-112">В списке политик выберите необходимую политику, щелкните **Правка**, затем выберите **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="a2a0b-112">In the list of policies, click the policy that you want, click **Edit**, and then click **Delete**.</span></span>

6.  <span data-ttu-id="a2a0b-113">Нажмите **ОК**.</span><span class="sxs-lookup"><span data-stu-id="a2a0b-113">Click **OK**.</span></span>

</div>

<div>

## <a name="removing-pin-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="a2a0b-114">Удаление политик закрепления с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a2a0b-114">Removing PIN Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="a2a0b-115">Вы можете удалять политики закрепления с помощью Windows PowerShell и командлета Remove-Кспинполици.</span><span class="sxs-lookup"><span data-stu-id="a2a0b-115">You can delete PIN policies by using Windows PowerShell and the Remove-CsPinPolicy cmdlet.</span></span> <span data-ttu-id="a2a0b-116">Этот командлет можно выполнить либо из управляющей оболочки Lync Server 2013, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a2a0b-116">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="a2a0b-117">Подробнее об использовании удаленной оболочки Windows PowerShell для подключения к серверу Lync Server можно найти в статье "Краткое руководство по работе с Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" на [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)веб-сервере Lync Server Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a2a0b-117">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-specific-pin-policy"></a><span data-ttu-id="a2a0b-118">Удаление определенной политики ПИН-кода</span><span class="sxs-lookup"><span data-stu-id="a2a0b-118">To remove a specific PIN policy</span></span>

  - <span data-ttu-id="a2a0b-119">Эта команда удаляет политику ПИН-кода с идентификатором RedmondPinPolicy:</span><span class="sxs-lookup"><span data-stu-id="a2a0b-119">This command removes the PIN policy with the Identity RedmondPinPolicy:</span></span>
    
        Remove-CsPinPolicy -Identity "RedmondPinPolicy"

</div>

<div>

## <a name="to-remove-all-the-pin-policies-applied-to-the-site-scope"></a><span data-ttu-id="a2a0b-120">Порядок применения всех политик ПИН-кода, применяемых на уровне сайта</span><span class="sxs-lookup"><span data-stu-id="a2a0b-120">To remove all the PIN policies applied to the site scope</span></span>

  - <span data-ttu-id="a2a0b-121">Эта команда удаляет все политики ПИН-кода, настроенные в области действия сайта:</span><span class="sxs-lookup"><span data-stu-id="a2a0b-121">This command removes all the PIN policies configured at the site scope:</span></span>
    
        Get-CsPinPolicy -Filter "site:*" | Remove-CsPinPolicy

</div>

<div>

## <a name="to-remove-all-the-pin-policies-that-allow-the-use-of-common-patterns"></a><span data-ttu-id="a2a0b-122">Удаление всех политик ПИН-кодов, позволяющих использовать общие шаблоны</span><span class="sxs-lookup"><span data-stu-id="a2a0b-122">To remove all the PIN policies that allow the use of common patterns</span></span>

  - <span data-ttu-id="a2a0b-123">А эта команда удаляет все политики ПИН-кодов, допускающие использование общих шаблонов:</span><span class="sxs-lookup"><span data-stu-id="a2a0b-123">And this one removes all the PIN policies that allow the use of common patterns:G</span></span>
    
        et-CsPinPolicy | Where-Object {$_.AllowCommonPatterns -eq $True} | Remove-CsPinPolicy

</div>

<span data-ttu-id="a2a0b-124">Дополнительные сведения можно найти в разделе справки по командлету [Remove-кспинполици](https://docs.microsoft.com/powershell/module/skype/Remove-CsPinPolicy) .</span><span class="sxs-lookup"><span data-stu-id="a2a0b-124">For more information, see the help topic for the [Remove-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsPinPolicy) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

