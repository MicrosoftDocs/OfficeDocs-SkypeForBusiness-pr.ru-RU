---
title: 'Lync Server 2013: создание или изменение новой политики версий клиентов'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a new client version policy
ms:assetid: 4be6e449-aa82-4b46-abb1-d31281573a72
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ898476(v=OCS.15)
ms:contentKeyID: 50873756
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bfb78150097fe7bde3b72338b3d1c9c37dc2a9b6
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48506116"
---
# <a name="create-or-modify-a-new-client-version-policy-in-lync-server-2013"></a><span data-ttu-id="3871c-102">Создание или изменение новой политики версий клиентов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3871c-102">Create or modify a new client version policy in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3871c-103">_**Последнее изменение темы:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="3871c-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="3871c-104">Политики версий клиентов можно использовать для указания версий клиентов, которые поддерживаются в вашей среде.</span><span class="sxs-lookup"><span data-stu-id="3871c-104">You can use client version policies to specify the versions of clients that are supported in your environment.</span></span> <span data-ttu-id="3871c-105">С помощью управления версиями клиентов можно сократить затраты, связанные с поддержкой нескольких версий клиентов.</span><span class="sxs-lookup"><span data-stu-id="3871c-105">Using client versioning can help reduce the costs associated with supporting multiple client versions.</span></span> <span data-ttu-id="3871c-106">Кроме того, это может привести к улучшению взаимодействия с пользователем, так как при взаимодействии более ранних и последующих версий клиентов доступные функции могут быть ограничены более ранней версией клиента.</span><span class="sxs-lookup"><span data-stu-id="3871c-106">It can also improve the overall user experience, because when earlier and later versions of clients interact, the available features can be limited by the earlier version of the client.</span></span> <span data-ttu-id="3871c-107">Политики версий клиентов можно создавать и изменять с помощью панели управления Lync Server 2013 или командной консоли Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3871c-107">You can create or modify client version policies from Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span>

<div>

## <a name="to-create-or-modify-client-version-policies-by-using-lync-server-control-panel"></a><span data-ttu-id="3871c-108">Создание или изменение политик версий клиентов с помощью панели управления Lync Server</span><span class="sxs-lookup"><span data-stu-id="3871c-108">To create or modify client version policies by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="3871c-109">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="3871c-109">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="3871c-110">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3871c-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="3871c-111">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="3871c-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="3871c-112">В левой области навигации щелкните элемент **Клиенты**.</span><span class="sxs-lookup"><span data-stu-id="3871c-112">In the left navigation bar, click **Clients**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3871c-113">Окно будет открыто на вкладке <STRONG>Политика версий клиентов</STRONG> по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="3871c-113">The <STRONG>Client Version Policy</STRONG> tab is selected by default.</span></span>

    
    </div>

4.  <span data-ttu-id="3871c-114">На странице **Политика версий клиентов** выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="3871c-114">On the **Client Version Policy** page, do one of the following:</span></span>
    
      - <span data-ttu-id="3871c-115">Чтобы создать политику версий клиентов, нажмите кнопку **создать**, выберите пункт **Политика сайта**, **Политика пула**или **Политика пользователя**, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="3871c-115">To create a client version policy, click **New**, select **Site policy**, **Pool policy**, or **User policy**, and then click **OK**.</span></span>
    
      - <span data-ttu-id="3871c-116">Чтобы изменить глобальную политику или другую существующую политику версий клиентов, выберите политику, нажмите кнопку **изменить**, а затем щелкните **Показать подробности**.</span><span class="sxs-lookup"><span data-stu-id="3871c-116">To modify the global policy or another existing client version policy, select the policy, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="3871c-117">На странице **изменение политики версий клиентов** Создайте или измените правила, как описано в статье [Создание или изменение нового правила политики версий клиентов в Lync Server 2013](lync-server-2013-create-or-modify-a-new-client-version-policy-rule.md).</span><span class="sxs-lookup"><span data-stu-id="3871c-117">On the **Edit Client Version Policy** page, create or modify rules as described in [Create or modify a new client version policy rule in Lync Server 2013](lync-server-2013-create-or-modify-a-new-client-version-policy-rule.md).</span></span>

</div>

<div>

## <a name="creating-or-modifying-client-version-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="3871c-118">Создание или изменение политик версий клиентов с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="3871c-118">Creating or Modifying Client Version Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="3871c-119">Политики версий клиентов можно создавать с помощью командлета **New – CsClientVersionPolicy** и изменять их с помощью командлета **Set – CsClientVersionPolicy** .</span><span class="sxs-lookup"><span data-stu-id="3871c-119">You can create client version policies by using the **New-CsClientVersionPolicy** cmdlet, and modify them by using the **Set-CsClientVersionPolicy** cmdlet.</span></span> <span data-ttu-id="3871c-120">Эти командлеты можно запускать из командной консоли Lync Server 2013 или из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3871c-120">These cmdlets can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="3871c-121">Сведения об использовании удаленной оболочки Windows PowerShell для подключения к Lync Server приведены в статье "Краткое руководство по управлению Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" в статье Lync Server Windows PowerShell в блоге [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="3871c-121">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-create-a-new-site-scoped-client-version-policy"></a><span data-ttu-id="3871c-122">Создание новой политики версий клиентов на уровне сайта</span><span class="sxs-lookup"><span data-stu-id="3871c-122">To create a new site-scoped client version policy</span></span>

  - <span data-ttu-id="3871c-123">Следующая команда создает новую политику версий клиентов, применяемую к сайту Redmond.</span><span class="sxs-lookup"><span data-stu-id="3871c-123">The following command creates a new client version policy applied to the Redmond site.</span></span> <span data-ttu-id="3871c-124">Так как никакие дополнительные параметры не указаны, Новая политика будет использовать параметры версий клиентов по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="3871c-124">Because no additional parameters are specified, the new policy will use the default client version settings.</span></span>
    
        New-CsClientVersionPolicy -Identity "site:Redmond"

</div>

<div>

## <a name="to-create-a-new-per-user-client-version-policy"></a><span data-ttu-id="3871c-125">Создание новой политики версий клиентов на уровне пользователя</span><span class="sxs-lookup"><span data-stu-id="3871c-125">To create a new per-user client version policy</span></span>

  - <span data-ttu-id="3871c-126">Чтобы создать политику на уровне пользователя, используйте команду, аналогичную следующей:</span><span class="sxs-lookup"><span data-stu-id="3871c-126">To create a per-user policy, use a command similar to this:</span></span>
    
        New-CsClientVersionPolicy -Identity "RedmondClientVersionPolicy"

</div>

<span data-ttu-id="3871c-127">Дополнительные сведения можно найти в разделах справки для командлета [New – CsClientVersionPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientVersionPolicy) и командлета [Set – CsClientVersionPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientVersionPolicy) .</span><span class="sxs-lookup"><span data-stu-id="3871c-127">For details, see the Help topics for the [New-CsClientVersionPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientVersionPolicy) cmdlet and the [Set-CsClientVersionPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientVersionPolicy) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

