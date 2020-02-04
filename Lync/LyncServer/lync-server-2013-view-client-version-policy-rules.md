---
title: 'Lync Server 2013: Просмотр правил политики версии клиента'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View client version policy rules
ms:assetid: f3a0215f-f72f-4e9b-a07b-25858dc4203a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ923060(v=OCS.15)
ms:contentKeyID: 50675350
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b64dce1b74be8ed1aed0c5d1f515910341f57c52
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757473"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-client-version-policy-rules-in-lync-server-2013"></a><span data-ttu-id="74830-102">Просмотр правил политики версии клиента в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="74830-102">View client version policy rules in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="74830-103">_**Тема последнего изменения:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="74830-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="74830-104">Политика клиентской версии состоит из набора правил политики клиентской версии.</span><span class="sxs-lookup"><span data-stu-id="74830-104">A client version policy is made up of a set of client version policy rules.</span></span> <span data-ttu-id="74830-105">Эти правила определяют действия, которые следует предпринять при попытке пользователей выполнить вход с использованием определенных клиентов и их версий.</span><span class="sxs-lookup"><span data-stu-id="74830-105">These rules define the actions that should be taken when users attempt to log on with specific clients and client versions.</span></span> <span data-ttu-id="74830-106">Вы можете просматривать правила политики версии клиента из панели управления Lync Server 2013 или оболочки управления Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="74830-106">You can view client version policy rules from Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span>

<div>

## <a name="to-view-client-version-policy-rules-by-using-lync-server-control-panel"></a><span data-ttu-id="74830-107">Просмотр правил политики версии клиента с помощью панели управления Lync Server</span><span class="sxs-lookup"><span data-stu-id="74830-107">To view client version policy rules by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="74830-108">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="74830-108">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="74830-109">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="74830-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="74830-110">Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="74830-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="74830-111">На панели навигации слева выберите пункт **Клиенты**и нажмите кнопку Переход на **политику версии клиента** .</span><span class="sxs-lookup"><span data-stu-id="74830-111">In the left navigation bar, click **Clients**, and then click the **Client Version Policy** navigation button.</span></span>

4.  <span data-ttu-id="74830-112">На странице **политики Client Version** дважды щелкните политику версии клиента, которую вы хотите просмотреть.</span><span class="sxs-lookup"><span data-stu-id="74830-112">On the **Client Version Policy** page, double-click a client version policy you want to view.</span></span>

5.  <span data-ttu-id="74830-113">Правила отображаются на странице " **изменение политики версии клиента** ".</span><span class="sxs-lookup"><span data-stu-id="74830-113">The rules appear on the **Edit Client Version Policy** page.</span></span> <span data-ttu-id="74830-114">Чтобы просмотреть сведения о правиле, выберите правило и нажмите кнопку **Показать подробности**.</span><span class="sxs-lookup"><span data-stu-id="74830-114">To view the details for a rule, select the rule, and then click **Show details**.</span></span>

</div>

<div>

## <a name="viewing-client-version-policy-rules-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="74830-115">Просмотр правил политики версий клиента с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="74830-115">Viewing Client Version Policy Rules by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="74830-116">Вы можете просматривать правила политики версии клиента с помощью командной консоли Lync Server Management Shell и командлета **Get-ксклиентверсионполицируле** .</span><span class="sxs-lookup"><span data-stu-id="74830-116">You can view client version policy rules by using Lync Server Management Shell and the **Get-CsClientVersionPolicyRule** cmdlet.</span></span> <span data-ttu-id="74830-117">Этот командлет можно выполнить либо из управляющей оболочки Lync Server 2013, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="74830-117">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="74830-118">Подробнее об использовании удаленной оболочки Windows PowerShell для подключения к серверу Lync Server можно найти в статье "Краткое руководство по работе с Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" на [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)веб-сервере Lync Server Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="74830-118">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-client-version-policy-rules"></a><span data-ttu-id="74830-119">Просмотр правил политики версии клиента</span><span class="sxs-lookup"><span data-stu-id="74830-119">To view client version policy rules</span></span>

  - <span data-ttu-id="74830-120">Чтобы просмотреть правила политики клиентской версии, введите в командной консоли Lync Server указанную ниже команду и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="74830-120">To view the client version policy rules, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsClientVersionPolicyRule
    
    <span data-ttu-id="74830-121">Будут возвращены следующие сведения для каждого настроенного правила:</span><span class="sxs-lookup"><span data-stu-id="74830-121">That will return information similar to this for each configured rule:</span></span>
    
        Identity          : Global/2336c611-a243-4c5d-994b-eea8a524d0e4
        Priority          : 0
        RuleId            : 2336c611-a243-4c5d-994b-eea8a524d0e4
        Description       :
        Action            : Block
        ActionUrl         :
        MajorVersion      : 1
        MinorVersion      : 3
        BuildNumber       :
        QfeNumber         :
        UserAgent         : RTC
        UserAgentFullName :
        Enabled           : True
        CompareOp         : LEQ

</div>

<span data-ttu-id="74830-122">Дополнительные сведения можно найти в разделе справки по командлету [Get-ксклиентверсионполицируле](https://docs.microsoft.com/powershell/module/skype/Get-CsClientVersionPolicyRule) .</span><span class="sxs-lookup"><span data-stu-id="74830-122">For details, see the help topic for the [Get-CsClientVersionPolicyRule](https://docs.microsoft.com/powershell/module/skype/Get-CsClientVersionPolicyRule) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

