---
title: 'Lync Server 2013: Включение и отключение серверного приложения на языке обработки Microsoft SIP (МСПЛ)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enable or disable a Microsoft SIP Processing Language (MSPL) server application
ms:assetid: b20af38d-224a-4459-991d-0b7eabb3ca7c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182573(v=OCS.15)
ms:contentKeyID: 48185145
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: da7ff3379f0e32166ceb263e1dbda46117b6984a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834302"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-a-microsoft-sip-processing-language-mspl-server-application-in-lync-server-2013"></a><span data-ttu-id="6ac16-102">Включение и отключение серверного приложения Microsoft SIP Languageing (МСПЛ) в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6ac16-102">Enable or disable a Microsoft SIP Processing Language (MSPL) server application in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6ac16-103">_**Тема последнего изменения:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="6ac16-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="6ac16-104">С помощью панели управления Lync Server можно включать и отключать серверные приложения Microsoft SIP Language (МСПЛ), которые выполняются в среде Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6ac16-104">You can use Lync Server Control Panel to enable or disable Microsoft SIP Processing Language (MSPL) server applications that run in your Lync Server 2013 environment.</span></span> <span data-ttu-id="6ac16-105">Эти приложения предназначены только для приложений, использующих язык сценариев вместо API Microsoft Lync 2013 Preview.</span><span class="sxs-lookup"><span data-stu-id="6ac16-105">These applications are script-only applications that use a scripting language instead of the Microsoft Lync 2013 Preview API.</span></span>

<span data-ttu-id="6ac16-106">Не все сценарии можно включать и отключать.</span><span class="sxs-lookup"><span data-stu-id="6ac16-106">Not all scripts can be enabled or disabled.</span></span> <span data-ttu-id="6ac16-107">Например, сценарий Дефаултраутинг включается, и этот параметр невозможно изменить для Дефаултраутинг.</span><span class="sxs-lookup"><span data-stu-id="6ac16-107">For instance, the DefaultRouting script is enabled and this option cannot be changed for DefaultRouting.</span></span>

<div>

## <a name="to-enable-or-disable-an-mspl-server-application"></a><span data-ttu-id="6ac16-108">Включение и отключение серверного приложения МСПЛ</span><span class="sxs-lookup"><span data-stu-id="6ac16-108">To enable or disable an MSPL server application</span></span>

1.  <span data-ttu-id="6ac16-109">Войдите в учетную запись пользователя, которая является членом группы Рткуниверсалсерверадминс (или имеет эквивалентные права пользователей) или назначьте роль Кссерверадминистратор или Ксадминистратор, выполните вход на любой компьютер в сети, в которой вы развернули Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6ac16-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="6ac16-110">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6ac16-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="6ac16-111">Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="6ac16-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="6ac16-112">На панели навигации слева выберите пункт топология и щелкните **серверное приложение**. \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="6ac16-112">In the left navigation bar, click **Topology** and then click **Server Application**.</span></span>

4.  <span data-ttu-id="6ac16-113">На странице **серверное приложение** щелкните заголовок столбца, чтобы отсортировать приложения, если необходимо, а затем выберите серверное приложение, которое вы хотите изменить.</span><span class="sxs-lookup"><span data-stu-id="6ac16-113">On the **Server Application** page, click a column heading to sort the applications, if needed, and then click the server application that you want to modify.</span></span>

5.  <span data-ttu-id="6ac16-114">Нажмите кнопку **действие**.</span><span class="sxs-lookup"><span data-stu-id="6ac16-114">Click **Action**.</span></span>

6.  <span data-ttu-id="6ac16-115">Нажмите кнопку **включить приложение** или **отключить приложение** (то есть, если сценарий поддерживает этот параметр).</span><span class="sxs-lookup"><span data-stu-id="6ac16-115">Click **Enable application** or **Disable application** (that is, if the script supports this option).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="6ac16-116">См. также</span><span class="sxs-lookup"><span data-stu-id="6ac16-116">See Also</span></span>


[<span data-ttu-id="6ac16-117">Пометка приложения на языке обработки Microsoft SIP (МСПЛ) как критическое или некритическое в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6ac16-117">Mark a Microsoft SIP Processing Language (MSPL) application as critical or not critical in Lync Server 2013</span></span>](lync-server-2013-mark-a-microsoft-sip-processing-language-mspl-application-as-critical-or-not-critical.md)  


[<span data-ttu-id="6ac16-118">Просмотр серверных приложений Microsoft SIP Processing Language (MSPL) в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6ac16-118">View Microsoft SIP Processing Language (MSPL) server applications in Lync Server 2013</span></span>](lync-server-2013-view-microsoft-sip-processing-language-mspl-server-applications.md)  


[<span data-ttu-id="6ac16-119">Управление топологией Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6ac16-119">Managing the Lync Server 2013 topology</span></span>](lync-server-2013-managing-the-lync-server-topology.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

