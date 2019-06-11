---
title: 'Lync Server 2013: создание и изменение новой политики версии клиента'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify a new client version policy
ms:assetid: 4be6e449-aa82-4b46-abb1-d31281573a72
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ898476(v=OCS.15)
ms:contentKeyID: 50873756
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 64e9d9d2879d4633b1775f8934186b8b01992d13
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834779"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-new-client-version-policy-in-lync-server-2013"></a><span data-ttu-id="5ff54-102">Создание или изменение новой политики версии клиента в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5ff54-102">Create or modify a new client version policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5ff54-103">_**Тема последнего изменения:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="5ff54-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="5ff54-104">Вы можете использовать политики версии клиента, чтобы указать версии клиентов, которые поддерживаются в вашей среде.</span><span class="sxs-lookup"><span data-stu-id="5ff54-104">You can use client version policies to specify the versions of clients that are supported in your environment.</span></span> <span data-ttu-id="5ff54-105">Использование клиентских версий помогает сократить затраты, связанные с поддержкой нескольких клиентских версий.</span><span class="sxs-lookup"><span data-stu-id="5ff54-105">Using client versioning can help reduce the costs associated with supporting multiple client versions.</span></span> <span data-ttu-id="5ff54-106">Кроме того, это может улучшить взаимодействие с пользователем, так как при взаимодействии более ранних и более поздних версий клиентов доступные функции могут быть ограничены более ранней версией клиента.</span><span class="sxs-lookup"><span data-stu-id="5ff54-106">It can also improve the overall user experience, because when earlier and later versions of clients interact, the available features can be limited by the earlier version of the client.</span></span> <span data-ttu-id="5ff54-107">Вы можете создавать и изменять политики версий клиентов из панели управления Lync Server 2013 или оболочки управления Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5ff54-107">You can create or modify client version policies from Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span>

<div>

## <a name="to-create-or-modify-client-version-policies-by-using-lync-server-control-panel"></a><span data-ttu-id="5ff54-108">Создание и изменение политик версий клиента с помощью панели управления Lync Server</span><span class="sxs-lookup"><span data-stu-id="5ff54-108">To create or modify client version policies by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="5ff54-109">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="5ff54-109">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="5ff54-110">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5ff54-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="5ff54-111">Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="5ff54-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="5ff54-112">На панели навигации слева выберите пункт **Клиенты**.</span><span class="sxs-lookup"><span data-stu-id="5ff54-112">In the left navigation bar, click **Clients**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="5ff54-113">По умолчанию выбрана вкладка <STRONG>политика Client Version</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="5ff54-113">The <STRONG>Client Version Policy</STRONG> tab is selected by default.</span></span>

    
    </div>

4.  <span data-ttu-id="5ff54-114">На странице **политики версия клиента** выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="5ff54-114">On the **Client Version Policy** page, do one of the following:</span></span>
    
      - <span data-ttu-id="5ff54-115">Чтобы создать политику версии клиента, нажмите кнопку **создать**, выберите пункт **Политика сайта**, **Политика пула**или **Политика пользователя**, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="5ff54-115">To create a client version policy, click **New**, select **Site policy**, **Pool policy**, or **User policy**, and then click **OK**.</span></span>
    
      - <span data-ttu-id="5ff54-116">Чтобы изменить глобальную политику или другую существующую, выберите ее и нажмите кнопку **изменить**, а затем выберите команду **Показать подробности**.</span><span class="sxs-lookup"><span data-stu-id="5ff54-116">To modify the global policy or another existing client version policy, select the policy, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="5ff54-117">На странице **изменение политики версии клиента** Создайте или измените правила, как описано в разделе [Создание или изменение нового правила политики для версий клиентов в Lync Server 2013](lync-server-2013-create-or-modify-a-new-client-version-policy-rule.md).</span><span class="sxs-lookup"><span data-stu-id="5ff54-117">On the **Edit Client Version Policy** page, create or modify rules as described in [Create or modify a new client version policy rule in Lync Server 2013](lync-server-2013-create-or-modify-a-new-client-version-policy-rule.md).</span></span>

</div>

<div>

## <a name="creating-or-modifying-client-version-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="5ff54-118">Создание и изменение политик версий клиента с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="5ff54-118">Creating or Modifying Client Version Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="5ff54-119">Вы можете создавать политики версии клиента с помощью командлета **New-ксклиентверсионполици** и изменять их с помощью командлета **Set-ксклиентверсионполици** .</span><span class="sxs-lookup"><span data-stu-id="5ff54-119">You can create client version policies by using the **New-CsClientVersionPolicy** cmdlet, and modify them by using the **Set-CsClientVersionPolicy** cmdlet.</span></span> <span data-ttu-id="5ff54-120">Эти командлеты можно запускать либо из командной консоли Lync Server 2013, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5ff54-120">These cmdlets can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="5ff54-121">Подробнее об использовании удаленной оболочки Windows PowerShell для подключения к серверу Lync Server можно найти в статье "Краткое руководство по работе с Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" на [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)веб-сервере Lync Server Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5ff54-121">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-create-a-new-site-scoped-client-version-policy"></a><span data-ttu-id="5ff54-122">Создание политики версии клиента уровня сайта</span><span class="sxs-lookup"><span data-stu-id="5ff54-122">To create a new site-scoped client version policy</span></span>

  - <span data-ttu-id="5ff54-123">Следующая команда создает новую политику версии клиента, примененную к сайту Redmond.</span><span class="sxs-lookup"><span data-stu-id="5ff54-123">The following command creates a new client version policy applied to the Redmond site.</span></span> <span data-ttu-id="5ff54-124">Так как никакие дополнительные параметры не указаны, Новая политика будет использовать параметры версии клиента по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="5ff54-124">Because no additional parameters are specified, the new policy will use the default client version settings.</span></span>
    
        New-CsClientVersionPolicy -Identity "site:Redmond"

</div>

<div>

## <a name="to-create-a-new-per-user-client-version-policy"></a><span data-ttu-id="5ff54-125">Создание новой политики клиентской версии для пользователей</span><span class="sxs-lookup"><span data-stu-id="5ff54-125">To create a new per-user client version policy</span></span>

  - <span data-ttu-id="5ff54-126">Чтобы создать политику для пользователя, используйте следующую команду:</span><span class="sxs-lookup"><span data-stu-id="5ff54-126">To create a per-user policy, use a command similar to this:</span></span>
    
        New-CsClientVersionPolicy -Identity "RedmondClientVersionPolicy"

</div>

<span data-ttu-id="5ff54-127">Подробные сведения можно найти в разделах справки по командлетам [New-ксклиентверсионполици](https://docs.microsoft.com/powershell/module/skype/New-CsClientVersionPolicy) и командлету [Set-ксклиентверсионполици](https://docs.microsoft.com/powershell/module/skype/Set-CsClientVersionPolicy) .</span><span class="sxs-lookup"><span data-stu-id="5ff54-127">For details, see the Help topics for the [New-CsClientVersionPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientVersionPolicy) cmdlet and the [Set-CsClientVersionPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientVersionPolicy) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

