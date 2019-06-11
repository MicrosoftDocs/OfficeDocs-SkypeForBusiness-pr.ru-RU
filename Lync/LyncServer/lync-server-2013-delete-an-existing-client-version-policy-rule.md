---
title: 'Lync Server 2013: удаление существующего правила политики для версии клиента'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Delete an existing client version policy rule
ms:assetid: 2fe351c4-d78b-47d5-af49-d47ee5e0fe42
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ923066(v=OCS.15)
ms:contentKeyID: 50675352
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: daad18b29a9c6b124093c1770da0db9c19757b2b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834623"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-an-existing-client-version-policy-rule-in-lync-server-2013"></a><span data-ttu-id="ab3d3-102">Удаление существующего правила политики для версии клиента в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ab3d3-102">Delete an existing client version policy rule in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ab3d3-103">_**Тема последнего изменения:** 2013-01-21_</span><span class="sxs-lookup"><span data-stu-id="ab3d3-103">_**Topic Last Modified:** 2013-01-21_</span></span>

<span data-ttu-id="ab3d3-104">Политика клиентской версии состоит из набора правил политики клиентской версии.</span><span class="sxs-lookup"><span data-stu-id="ab3d3-104">A client version policy is made up of a set of client version policy rules.</span></span> <span data-ttu-id="ab3d3-105">Эти правила определяют действия, которые следует предпринять при попытке пользователей выполнить вход с использованием определенных клиентов и их версий.</span><span class="sxs-lookup"><span data-stu-id="ab3d3-105">These rules define the actions that should be taken when users attempt to log on with specific clients and client versions.</span></span> <span data-ttu-id="ab3d3-106">Вы можете удалить отдельные правила из политики версии клиента с помощью панели управления Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ab3d3-106">You can delete individual rules from a client version policy from Lync Server 2013 Control Panel.</span></span>

<div>

## <a name="to-delete-client-version-policy-rules-with-lync-server-control-panel"></a><span data-ttu-id="ab3d3-107">Удаление правил политики версий клиента с помощью панели управления Lync Server</span><span class="sxs-lookup"><span data-stu-id="ab3d3-107">To delete client version policy rules with Lync Server Control Panel</span></span>

1.  <span data-ttu-id="ab3d3-108">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="ab3d3-108">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="ab3d3-109">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ab3d3-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="ab3d3-110">Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="ab3d3-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="ab3d3-111">На панели навигации слева выберите пункт **Клиенты**и нажмите кнопку Переход на **политику версии клиента** .</span><span class="sxs-lookup"><span data-stu-id="ab3d3-111">In the left navigation bar, click **Clients**, and then click the **Client Version Policy** navigation button.</span></span>

4.  <span data-ttu-id="ab3d3-112">На странице **политики Client Version** дважды щелкните политику версии клиента для правила, которое вы хотите удалить.</span><span class="sxs-lookup"><span data-stu-id="ab3d3-112">On the **Client Version Policy** page, double-click the client version policy for the rule you want to delete.</span></span>

5.  <span data-ttu-id="ab3d3-113">Правила отображаются на странице " **изменение политики версии клиента** ".</span><span class="sxs-lookup"><span data-stu-id="ab3d3-113">The rules appear on the **Edit Client Version Policy** page.</span></span> <span data-ttu-id="ab3d3-114">Для удаления правила выберите правило и нажмите кнопку **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="ab3d3-114">To delete a rule, select the rule, and then click **Remove**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

