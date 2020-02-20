---
title: 'Lync Server 2013: удаление существующего правила политики версий клиентов'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete an existing client version policy rule
ms:assetid: 2fe351c4-d78b-47d5-af49-d47ee5e0fe42
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ923066(v=OCS.15)
ms:contentKeyID: 50675352
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5287086c22d2e8e743239139e744ecdcbf344cc0
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147632"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="delete-an-existing-client-version-policy-rule-in-lync-server-2013"></a><span data-ttu-id="ac004-102">Удаление существующего правила политики версий клиентов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ac004-102">Delete an existing client version policy rule in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ac004-103">_**Последнее изменение темы:** 2013-01-21_</span><span class="sxs-lookup"><span data-stu-id="ac004-103">_**Topic Last Modified:** 2013-01-21_</span></span>

<span data-ttu-id="ac004-104">Политика версий клиентов состоит из набора правил политики версий клиентов.</span><span class="sxs-lookup"><span data-stu-id="ac004-104">A client version policy is made up of a set of client version policy rules.</span></span> <span data-ttu-id="ac004-105">Эти правила определяют действия, которые следует предпринять при попытке пользователей выполнить вход с использованием определенных клиентов и их версий.</span><span class="sxs-lookup"><span data-stu-id="ac004-105">These rules define the actions that should be taken when users attempt to log on with specific clients and client versions.</span></span> <span data-ttu-id="ac004-106">Вы можете удалять отдельные правила из политики версий клиентов из панели управления Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ac004-106">You can delete individual rules from a client version policy from Lync Server 2013 Control Panel.</span></span>

<div>

## <a name="to-delete-client-version-policy-rules-with-lync-server-control-panel"></a><span data-ttu-id="ac004-107">Удаление правил политики версий клиентов с помощью панели управления Lync Server</span><span class="sxs-lookup"><span data-stu-id="ac004-107">To delete client version policy rules with Lync Server Control Panel</span></span>

1.  <span data-ttu-id="ac004-108">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="ac004-108">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="ac004-109">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ac004-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="ac004-110">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="ac004-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="ac004-111">В левой панели навигации щелкните элемент **Клиенты**, а затем нажмите кнопку навигации для **политики версий клиентов** .</span><span class="sxs-lookup"><span data-stu-id="ac004-111">In the left navigation bar, click **Clients**, and then click the **Client Version Policy** navigation button.</span></span>

4.  <span data-ttu-id="ac004-112">На странице **Политика версий клиентов** дважды щелкните политику версий клиентов для правила, которое необходимо удалить.</span><span class="sxs-lookup"><span data-stu-id="ac004-112">On the **Client Version Policy** page, double-click the client version policy for the rule you want to delete.</span></span>

5.  <span data-ttu-id="ac004-113">Правила отображаются на странице **изменение политики версий клиентов** .</span><span class="sxs-lookup"><span data-stu-id="ac004-113">The rules appear on the **Edit Client Version Policy** page.</span></span> <span data-ttu-id="ac004-114">Чтобы удалить правило, выберите это правило и нажмите кнопку **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="ac004-114">To delete a rule, select the rule, and then click **Remove**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

