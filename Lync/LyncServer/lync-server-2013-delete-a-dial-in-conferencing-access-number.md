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
ms.openlocfilehash: 65d461aafd4f111484faf295bef2dd50685e41e6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765227"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-a-dial-in-conferencing-access-number-in-lync-server-2013"></a><span data-ttu-id="fa1c7-102">Удаление номера доступа для конференц-связи с телефонным подключением в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fa1c7-102">Delete a dial-in conferencing access number in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fa1c7-103">_**Тема последнего изменения:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="fa1c7-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="fa1c7-104">Чтобы удалить номер доступа к конференц-связи с телефонным подключением, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="fa1c7-104">Follow these steps to delete a dial-in conferencing access number.</span></span>

<div>

## <a name="to-delete-a-dial-in-conferencing-access-number"></a><span data-ttu-id="fa1c7-105">Удаление номера доступа к конференц-связи с телефонным подключением</span><span class="sxs-lookup"><span data-stu-id="fa1c7-105">To delete a dial-in conferencing access number</span></span>

1.  <span data-ttu-id="fa1c7-106">Войдите в учетную запись пользователя, которая является членом группы Рткуниверсалсерверадминс (или имеет эквивалентные права пользователей) или назначьте роль Кссерверадминистратор или Ксадминистратор, выполните вход на любой компьютер в сети, в которой вы развернули Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fa1c7-106">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="fa1c7-107">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="fa1c7-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="fa1c7-108">Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="fa1c7-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="fa1c7-109">В левой панели навигации выберите **Конференция**, а затем щелкните **Номер для телефонного подключения**.</span><span class="sxs-lookup"><span data-stu-id="fa1c7-109">In the left navigation bar, click **Conferencing**, and then click **Dial-in Access Number**.</span></span>

4.  <span data-ttu-id="fa1c7-110">На странице выберите номер доступа, который нужно удалить, в списке, нажмите кнопку **Изменить**, а затем — **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="fa1c7-110">On the page, click the dial-in number you want to delete in the list, click **Edit**, and then click **Delete**.</span></span>

5.  <span data-ttu-id="fa1c7-111">Нажмите **ОК**.</span><span class="sxs-lookup"><span data-stu-id="fa1c7-111">Click **OK**.</span></span>

</div>

<div>

## <a name="removing-dial-in-conferencing-access-numbers-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="fa1c7-112">Удаление номеров доступа для конференц-связи с телефонным подключением с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="fa1c7-112">Removing Dial-in Conferencing Access Numbers by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="fa1c7-113">Номера доступа для конференц-связи с телефонным подключением можно удалить с помощью Windows PowerShell и командлета **Remove-ксдиалинконференЦингакцесснумбер** .</span><span class="sxs-lookup"><span data-stu-id="fa1c7-113">Dial-in conferencing access numbers can be deleted by using Windows PowerShell and the **Remove-CsDialInConferencingAccessNumber** cmdlet.</span></span> <span data-ttu-id="fa1c7-114">Этот командлет можно выполнить либо из управляющей оболочки Lync Server 2013, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fa1c7-114">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="fa1c7-115">Подробнее об использовании удаленной оболочки Windows PowerShell для подключения к серверу Lync Server можно найти в статье "Краткое руководство по работе с Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" на [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)веб-сервере Lync Server Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fa1c7-115">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-specific-dial-in-conferencing-access-number"></a><span data-ttu-id="fa1c7-116">Чтобы удалить определенный номер доступа к конференц-связи с телефонным подключением</span><span class="sxs-lookup"><span data-stu-id="fa1c7-116">To remove a specific dial-in conferencing access number</span></span>

  - <span data-ttu-id="fa1c7-117">Эта команда удаляет номер доступа к конференц-связи с телефонным подключением с удостоверением sip:RedmondDialInAccess@litwareinc.com:</span><span class="sxs-lookup"><span data-stu-id="fa1c7-117">This command deletes the dial-in conferencing access number with Identity sip:RedmondDialInAccess@litwareinc.com:</span></span>
    
        Remove-CsDialInConferencingAccessNumber -Identity "sip:RedmondDialInAccess@litwareinc.com"

</div>

<div>

## <a name="to-remove-all-the-dial-in-conferencing-access-numbers-assigned-to-a-specific-region"></a><span data-ttu-id="fa1c7-118">Удаление всех номеров доступа для конференц-связи с телефонным подключением, назначенных определенному региону</span><span class="sxs-lookup"><span data-stu-id="fa1c7-118">To remove all the dial-in conferencing access numbers assigned to a specific region</span></span>

  - <span data-ttu-id="fa1c7-119">Эта команда удаляет все номера доступа для конференц-связи с телефонным подключением, связанные с этим регионом:</span><span class="sxs-lookup"><span data-stu-id="fa1c7-119">This command deletes all the dial-in conferencing access numbers associated with the Northwest region:</span></span>
    
        Get-CsDialInConferencingAccessNumber -Region "Northwest" | Remove-CsDialInConferencingAccessNumber

</div>

<div>

## <a name="to-remove-dial-in-conferencing-access-numbers-based-on-primary-language"></a><span data-ttu-id="fa1c7-120">Удаление номеров доступа для конференц-связи с телефонным подключением на основе основного языка</span><span class="sxs-lookup"><span data-stu-id="fa1c7-120">To remove dial-in conferencing access numbers based on primary language</span></span>

  - <span data-ttu-id="fa1c7-121">Эта команда удаляет все номера для конференц-связи с телефонным подключением, где основной язык — итальянский:</span><span class="sxs-lookup"><span data-stu-id="fa1c7-121">This command deletes all the dial-in conferencing access numbers where Italian is the primary language:</span></span>
    
        Get-CsDialInConferencingAccessNumber | Where-Object {$_.PrimaryLanguage -eq "it-IT"} | Remove-CsDialInConferencingAccessNumber

</div>

<span data-ttu-id="fa1c7-122">Дополнительные сведения можно найти в разделе справки по командлету [Remove-ксдиалинконференЦингакцесснумбер](https://docs.microsoft.com/powershell/module/skype/Remove-CsDialInConferencingAccessNumber) .</span><span class="sxs-lookup"><span data-stu-id="fa1c7-122">For more information, see the help topic for the [Remove-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/Remove-CsDialInConferencingAccessNumber) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

