---
title: 'Lync Server 2013: Включение или отключение серверного приложения Microsoft SIP Processing Language (MSPL)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable or disable a Microsoft SIP Processing Language (MSPL) server application
ms:assetid: b20af38d-224a-4459-991d-0b7eabb3ca7c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182573(v=OCS.15)
ms:contentKeyID: 48185145
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c19f9918aa1740c8ac80e2c2a51466f5bf2022b7
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42190652"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-a-microsoft-sip-processing-language-mspl-server-application-in-lync-server-2013"></a><span data-ttu-id="632ad-102">Включение и отключение серверного приложения Microsoft SIP Processing Language (MSPL) в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="632ad-102">Enable or disable a Microsoft SIP Processing Language (MSPL) server application in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="632ad-103">_**Последнее изменение темы:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="632ad-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="632ad-104">С помощью панели управления Lync Server можно включать и отключать серверные приложения Microsoft SIP Processing Language (MSPL), выполняемые в среде Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="632ad-104">You can use Lync Server Control Panel to enable or disable Microsoft SIP Processing Language (MSPL) server applications that run in your Lync Server 2013 environment.</span></span> <span data-ttu-id="632ad-105">Эти приложения представляют собой приложения на основе сценариев, которые вместо Microsoft Lync 2013 Preview API используют язык сценариев.</span><span class="sxs-lookup"><span data-stu-id="632ad-105">These applications are script-only applications that use a scripting language instead of the Microsoft Lync 2013 Preview API.</span></span>

<span data-ttu-id="632ad-p102">Не все сценарии могут быть включены или отключены. Например, сценарий DefaultRouting включен и это значение нельзя изменить.</span><span class="sxs-lookup"><span data-stu-id="632ad-p102">Not all scripts can be enabled or disabled. For instance, the DefaultRouting script is enabled and this option cannot be changed for DefaultRouting.</span></span>

<div>

## <a name="to-enable-or-disable-an-mspl-server-application"></a><span data-ttu-id="632ad-108">Включение или отключение серверного приложения MSPL</span><span class="sxs-lookup"><span data-stu-id="632ad-108">To enable or disable an MSPL server application</span></span>

1.  <span data-ttu-id="632ad-109">Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначается роли CsServerAdministrator или CsAdministrator, войдите на любой компьютер в сети, в которой развернут Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="632ad-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="632ad-110">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="632ad-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="632ad-111">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="632ad-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="632ad-112">В левой панели навигации щелкните **Topology** (Топология) и затем щелкните **Server Application** (Серверное приложение).</span><span class="sxs-lookup"><span data-stu-id="632ad-112">In the left navigation bar, click **Topology** and then click **Server Application**.</span></span>

4.  <span data-ttu-id="632ad-113">На странице **Server Application** (Серверное приложение) щелкните заголовок столбца, чтобы отсортировать приложения при необходимости, и затем выберите серверное приложение, которое нужно изменить.</span><span class="sxs-lookup"><span data-stu-id="632ad-113">On the **Server Application** page, click a column heading to sort the applications, if needed, and then click the server application that you want to modify.</span></span>

5.  <span data-ttu-id="632ad-114">Щелкните меню **Action** (Действие).</span><span class="sxs-lookup"><span data-stu-id="632ad-114">Click **Action**.</span></span>

6.  <span data-ttu-id="632ad-115">Щелкните **Enable application** (Включить приложение) или **Disable application** (Отключить приложение) (если сценарий поддерживает этот параметр).</span><span class="sxs-lookup"><span data-stu-id="632ad-115">Click **Enable application** or **Disable application** (that is, if the script supports this option).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="632ad-116">См. также</span><span class="sxs-lookup"><span data-stu-id="632ad-116">See Also</span></span>


[<span data-ttu-id="632ad-117">Помечает приложение Microsoft SIP Process Language (MSPL) как критическое или некритическое в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="632ad-117">Mark a Microsoft SIP Processing Language (MSPL) application as critical or not critical in Lync Server 2013</span></span>](lync-server-2013-mark-a-microsoft-sip-processing-language-mspl-application-as-critical-or-not-critical.md)  


[<span data-ttu-id="632ad-118">Просмотр серверных приложений Microsoft SIP Processing Language (MSPL) в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="632ad-118">View Microsoft SIP Processing Language (MSPL) server applications in Lync Server 2013</span></span>](lync-server-2013-view-microsoft-sip-processing-language-mspl-server-applications.md)  


[<span data-ttu-id="632ad-119">Управление топологией Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="632ad-119">Managing the Lync Server 2013 topology</span></span>](lync-server-2013-managing-the-lync-server-topology.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

