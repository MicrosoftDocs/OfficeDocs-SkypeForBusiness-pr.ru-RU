---
title: 'Lync Server 2013: Удаление номера доступа к конференц-связи с телефонным подключением'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete a dial-in conferencing access number
ms:assetid: 199c5d9c-0489-4ad5-a7f1-ca59fe0e6ac7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520956(v=OCS.15)
ms:contentKeyID: 48183522
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ef5d0e51486ed6dca7c9ac17a991b0154c2f1135
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42187972"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="delete-a-dial-in-conferencing-access-number-in-lync-server-2013"></a><span data-ttu-id="d0f5c-102">Удаление номера доступа к конференц-связи с телефонным подключением в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d0f5c-102">Delete a dial-in conferencing access number in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d0f5c-103">_**Последнее изменение темы:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="d0f5c-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="d0f5c-104">Выполните следующие действия, чтобы удалить номер доступа к конференции с телефонным подключением.</span><span class="sxs-lookup"><span data-stu-id="d0f5c-104">Follow these steps to delete a dial-in conferencing access number.</span></span>

<div>

## <a name="to-delete-a-dial-in-conferencing-access-number"></a><span data-ttu-id="d0f5c-105">Удаление номера доступа к конференции с телефонным подключением</span><span class="sxs-lookup"><span data-stu-id="d0f5c-105">To delete a dial-in conferencing access number</span></span>

1.  <span data-ttu-id="d0f5c-106">Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначается роли CsServerAdministrator или CsAdministrator, войдите на любой компьютер в сети, в которой развернут Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d0f5c-106">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="d0f5c-107">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d0f5c-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="d0f5c-108">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="d0f5c-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="d0f5c-109">В левой панели навигации выберите **Конференции**, а затем щелкните **Удаленный доступ (через телефонную сеть)**.</span><span class="sxs-lookup"><span data-stu-id="d0f5c-109">In the left navigation bar, click **Conferencing**, and then click **Dial-in Access Number**.</span></span>

4.  <span data-ttu-id="d0f5c-110">На странице выберите номер доступа, который нужно удалить, в списке, нажмите кнопку **Изменить**, а затем нажмите **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="d0f5c-110">On the page, click the dial-in number you want to delete in the list, click **Edit**, and then click **Delete**.</span></span>

5.  <span data-ttu-id="d0f5c-111">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="d0f5c-111">Click **OK**.</span></span>

</div>

<div>

## <a name="removing-dial-in-conferencing-access-numbers-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="d0f5c-112">Удаление номеров доступа к конференц-связи с телефонным подключением с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d0f5c-112">Removing Dial-in Conferencing Access Numbers by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="d0f5c-113">Номера доступа к конференц-связи с телефонным подключением можно удалить с помощью Windows PowerShell и командлета **Remove-CsDialInConferencingAccessNumber** .</span><span class="sxs-lookup"><span data-stu-id="d0f5c-113">Dial-in conferencing access numbers can be deleted by using Windows PowerShell and the **Remove-CsDialInConferencingAccessNumber** cmdlet.</span></span> <span data-ttu-id="d0f5c-114">Этот командлет можно запустить либо из командной консоли Lync Server 2013, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d0f5c-114">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="d0f5c-115">Сведения об использовании удаленной оболочки Windows PowerShell для подключения к Lync Server приведены в статье "Краткое руководство по управлению Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" в [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)статье Lync Server Windows PowerShell в блоге.</span><span class="sxs-lookup"><span data-stu-id="d0f5c-115">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-specific-dial-in-conferencing-access-number"></a><span data-ttu-id="d0f5c-116">Удаление определенного номера доступа к конференц-связи с телефонным подключением</span><span class="sxs-lookup"><span data-stu-id="d0f5c-116">To remove a specific dial-in conferencing access number</span></span>

  - <span data-ttu-id="d0f5c-117">Эта команда служит для удаления номера доступа к конференц-связи с телефонным подключением с идентификатором sip:RedmondDialInAccess@litwareinc.com:</span><span class="sxs-lookup"><span data-stu-id="d0f5c-117">This command deletes the dial-in conferencing access number with Identity sip:RedmondDialInAccess@litwareinc.com:</span></span>
    
        Remove-CsDialInConferencingAccessNumber -Identity "sip:RedmondDialInAccess@litwareinc.com"

</div>

<div>

## <a name="to-remove-all-the-dial-in-conferencing-access-numbers-assigned-to-a-specific-region"></a><span data-ttu-id="d0f5c-118">Удаление всех номеров доступа к конференц-связи с телефонным подключением, назначенных определенному региону</span><span class="sxs-lookup"><span data-stu-id="d0f5c-118">To remove all the dial-in conferencing access numbers assigned to a specific region</span></span>

  - <span data-ttu-id="d0f5c-119">Эта команда служит для удаления всех номеров доступа к конференц-связи с телефонным подключением, связанных с регионом "Северо-запад":</span><span class="sxs-lookup"><span data-stu-id="d0f5c-119">This command deletes all the dial-in conferencing access numbers associated with the Northwest region:</span></span>
    
        Get-CsDialInConferencingAccessNumber -Region "Northwest" | Remove-CsDialInConferencingAccessNumber

</div>

<div>

## <a name="to-remove-dial-in-conferencing-access-numbers-based-on-primary-language"></a><span data-ttu-id="d0f5c-120">Удаление номеров доступа к конференц-связи с телефонным подключением на основе основного языка</span><span class="sxs-lookup"><span data-stu-id="d0f5c-120">To remove dial-in conferencing access numbers based on primary language</span></span>

  - <span data-ttu-id="d0f5c-121">Эта команда удаляет все номера доступа к конференц-связи с телефонным подключением, где основной язык — итальянский:</span><span class="sxs-lookup"><span data-stu-id="d0f5c-121">This command deletes all the dial-in conferencing access numbers where Italian is the primary language:</span></span>
    
        Get-CsDialInConferencingAccessNumber | Where-Object {$_.PrimaryLanguage -eq "it-IT"} | Remove-CsDialInConferencingAccessNumber

</div>

<span data-ttu-id="d0f5c-122">Для получения дополнительных сведений обратитесь к разделу "Справка" для командлета [Remove – CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/Remove-CsDialInConferencingAccessNumber) .</span><span class="sxs-lookup"><span data-stu-id="d0f5c-122">For more information, see the help topic for the [Remove-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/Remove-CsDialInConferencingAccessNumber) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

