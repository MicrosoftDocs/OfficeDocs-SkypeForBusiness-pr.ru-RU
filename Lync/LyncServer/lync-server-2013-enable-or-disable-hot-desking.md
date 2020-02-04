---
title: 'Lync Server 2013: Включение и отключение поддержки горячей замены'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable or disable hot desking
ms:assetid: 93a7fed6-f61a-4b41-9336-a8320afa87cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994057(v=OCS.15)
ms:contentKeyID: 51803968
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7c56d7ae13be9afa3af7e4732242a86f4be4c458
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736039"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-hot-desking-in-lync-server-2013"></a><span data-ttu-id="f919a-102">Включение и отключение функции поддержки горячей замены в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f919a-102">Enable or disable hot desking in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f919a-103">_**Тема последнего изменения:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="f919a-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="f919a-104">Вы можете настроить стандартные телефоны как *стационарные телефоны*.</span><span class="sxs-lookup"><span data-stu-id="f919a-104">You can set up common area phones as *hot-desk phones*.</span></span> <span data-ttu-id="f919a-105">С помощью стационарных телефонов пользователи могут входить в свою учетную запись пользователя и после входа в нее использовать возможности сервера Lync и собственные параметры профиля пользователя.</span><span class="sxs-lookup"><span data-stu-id="f919a-105">With hot-desk phones, users can log on to their own user account, and, after they are logged on, use Lync Server features and their own user profile settings.</span></span> <span data-ttu-id="f919a-106">Управление горячим подключением осуществляется с помощью политик клиента: чтобы включить или отключить функцию горячей замены, необходимо изменить политики клиента, используемые вашими стандартными телефонами.</span><span class="sxs-lookup"><span data-stu-id="f919a-106">Hot desking is managed by using client policies: to enable or disable hot desking, you need to modify the client policies that are used by your common area phones.</span></span> <span data-ttu-id="f919a-107">Подробные сведения о том, как определить политики конференц-связи, назначенные на обычные телефоны, можно найти [в статьях Просмотр сведений о телефонах в Lync Server 2013](lync-server-2013-view-common-area-phone-information.md).</span><span class="sxs-lookup"><span data-stu-id="f919a-107">For details about how to determine the conferencing policies that have been assigned to your common area phones, see [View common area phone information in Lync Server 2013](lync-server-2013-view-common-area-phone-information.md).</span></span>

<span data-ttu-id="f919a-108">Вы можете использовать параметр Енаблехотдескинг командлета **New-CSClientPolicy** или командлет **Set-CSClientPolicy** , чтобы включить или отключить функцию горячей замены на телефоне, как описано ниже.</span><span class="sxs-lookup"><span data-stu-id="f919a-108">You use the EnableHotdesking parameter of the **New-CSClientPolicy** cmdlet or the **Set-CSClientPolicy** cmdlet to enable or disable hot desking on a phone, as follows.</span></span> <span data-ttu-id="f919a-109">Выполните эти командлеты либо из командной консоли Lync Server 2013, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f919a-109">Run these cmdlets from either the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="f919a-110">Подробнее об использовании удаленной оболочки Windows PowerShell для подключения к серверу Lync Server можно найти в статье "Краткое руководство по работе с Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" на [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)веб-сервере Lync Server Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f919a-110">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>


<div>

## <a name="enabling-hot-desking"></a><span data-ttu-id="f919a-111">Включение поддержки горячей замены</span><span class="sxs-lookup"><span data-stu-id="f919a-111">Enabling hot desking</span></span>

  - <span data-ttu-id="f919a-112">Чтобы включить функцию горячего подключения для обычного телефонного телефона, необходимо изменить политику клиента, назначенную этому телефону (или набору телефонов).</span><span class="sxs-lookup"><span data-stu-id="f919a-112">To enable hot desking for a common area phone, you must modify the client policy that has been assigned to that phone (or collection of phones).</span></span>
    
    <span data-ttu-id="f919a-113">После того как вы определили политику, которую необходимо изменить, далее следует использовать командлет **Set-CsClientPolicy** , чтобы установить для параметра Енаблехотдескинг значение true.</span><span class="sxs-lookup"><span data-stu-id="f919a-113">After you have identified the policy that needs to be modified, the next step is to use the **Set-CsClientPolicy** cmdlet to set the EnableHotdesking parameter to True.</span></span> <span data-ttu-id="f919a-114">Например:</span><span class="sxs-lookup"><span data-stu-id="f919a-114">For example:</span></span>
    
        Set-CsClientPolicy -Identity "CommonAreaPhonePolicy" - EnableHotdesking $True

  - <span data-ttu-id="f919a-115">Кроме того, вы можете использовать командлет **New-CsClientPolicy** для создания новой политики клиента, обеспечивающей поддержку горячего рабочего стола.</span><span class="sxs-lookup"><span data-stu-id="f919a-115">Alternatively, you can use the **New-CsClientPolicy** cmdlet to create a new client policy that enables hot desking.</span></span> <span data-ttu-id="f919a-116">Например:</span><span class="sxs-lookup"><span data-stu-id="f919a-116">For example:</span></span>
    
        New-CsClientPolicy -Identity "NewCommonAreaPhonePolicy" - EnableHotdesking $True

</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="f919a-117">После того как эта политика создана, вы должны назначить ее соответствующим телефонам.</span><span class="sxs-lookup"><span data-stu-id="f919a-117">After this policy has been created, you must assign it to the appropriate common area phones.</span></span> <span data-ttu-id="f919a-118">Подробности можно найти <A href="lync-server-2013-assign-policies-to-a-common-area-phone.md">в разделе назначение политик в Lync Server 2013 на общем телефоне с областями</A>.</span><span class="sxs-lookup"><span data-stu-id="f919a-118">For details, see <A href="lync-server-2013-assign-policies-to-a-common-area-phone.md">Assign policies in Lync Server 2013 to a common area phone</A>.</span></span>



</div>

<div>

## <a name="disabling-hot-desking"></a><span data-ttu-id="f919a-119">Отключение поддержки горячей замены</span><span class="sxs-lookup"><span data-stu-id="f919a-119">Disabling hot desking</span></span>

  - <span data-ttu-id="f919a-120">Чтобы отключить функцию горячего подключения для обычного телефонного телефона, сбросьте параметр Енаблехотдескинг командлета **Set-CsClientPolicy** в значение по умолчанию, равное false.</span><span class="sxs-lookup"><span data-stu-id="f919a-120">To disable hot desking for a common area phone, reset the EnableHotdesking parameter of the **Set-CsClientPolicy** cmdlet to the default value of False.</span></span> <span data-ttu-id="f919a-121">Например:</span><span class="sxs-lookup"><span data-stu-id="f919a-121">For example:</span></span>
    
        Set-CsClientPolicy -Identity "CommonAreaPhonePolicy" - EnableHotdesking $False

</div>

<span data-ttu-id="f919a-122">Подробные сведения можно найти в разделах справки по командлетам [New-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy) и командлету [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy) .</span><span class="sxs-lookup"><span data-stu-id="f919a-122">For details, see the Help topics for the [New-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy) cmdlet and the [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

