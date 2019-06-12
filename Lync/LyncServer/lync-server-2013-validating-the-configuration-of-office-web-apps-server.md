---
title: 'Lync Server 2013: Проверка конфигурации сервера Office Web Apps'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Validating the configuration of Office Web Apps Server
ms:assetid: f6e8ecbf-305d-4a13-92d0-b61dbd82b0ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205393(v=OCS.15)
ms:contentKeyID: 48185859
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 35844ae2ae73937d6840e480dc57393b91d13eaf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849199"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="validating-the-configuration-of-office-web-apps-server-in-lync-server-2013"></a><span data-ttu-id="0418a-102">Проверка конфигурации сервера Office Web Apps в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0418a-102">Validating the configuration of Office Web Apps Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0418a-103">_**Тема последнего изменения:** 2014-04-22_</span><span class="sxs-lookup"><span data-stu-id="0418a-103">_**Topic Last Modified:** 2014-04-22_</span></span>

<span data-ttu-id="0418a-104">После добавления сервера Office Web Apps в топологию и после публикации этой топологии вы должны увидеть два новых события журнала событий в журнале событий Lync Server.</span><span class="sxs-lookup"><span data-stu-id="0418a-104">After Office Web Apps Server has been added to the topology, and after that topology has been published, you should see two new event log events in the Lync Server event log.</span></span> <span data-ttu-id="0418a-105">First, an LS Data MCU event (event ID 41034) should be added; this event will report that the Office Web Apps Server has been discovered:</span><span class="sxs-lookup"><span data-stu-id="0418a-105">First, an LS Data MCU event (event ID 41034) should be added; this event will report that the Office Web Apps Server has been discovered:</span></span>

<span data-ttu-id="0418a-106">**Сервер веб-конференций обнаружил сервер Office Web Apps Server, содержимое PowerPoint включено.**</span><span class="sxs-lookup"><span data-stu-id="0418a-106">**Web Conferencing Server Office Web Apps Server is discovered, PowerPoint content is enabled.**</span></span>

<span data-ttu-id="0418a-p102">Кроме того, должно отображаться другое событие LS Data MCU (идентификатор события — 41032), которое отправляют URL-адреса сервера Office Web Apps. Это событие может иметь, например, следующий вид:</span><span class="sxs-lookup"><span data-stu-id="0418a-p102">In addition to that you should see another LS Data MCU event (event ID 41032) that reports back Office Web Apps Server URLs. For example, you should see something similar to this:</span></span>

<span data-ttu-id="0418a-109">**Обнаружение Office Web Apps Server (WAC) сервера веб-конференций выполнено успешно.**</span><span class="sxs-lookup"><span data-stu-id="0418a-109">**Web Conferencing Server Office Web Apps Server discovery has succeeded.**</span></span>

<span data-ttu-id="0418a-110">**Страница внутренней выступающего сервера Office Web Apps:https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0\&embed=**</span><span class="sxs-lookup"><span data-stu-id="0418a-110">**Office Web Apps Server internal presenter page: https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0\&embed=**</span></span>

<span data-ttu-id="0418a-111">**Страница внутреннего участника на сервере Office Web Apps:https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0\&embed=true&=**</span><span class="sxs-lookup"><span data-stu-id="0418a-111">**Office Web Apps Server internal attendee page: https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0\&embed=true&=**</span></span>

<span data-ttu-id="0418a-112">**Страница внешнего выступающего сервера Office Web Apps:https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0\&embed**</span><span class="sxs-lookup"><span data-stu-id="0418a-112">**Office Web Apps Server external presenter page: https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0\&embed**</span></span>

<span data-ttu-id="0418a-113">**Страница внутреннего участника на сервере Office Web Apps:https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0\&embed=true&**</span><span class="sxs-lookup"><span data-stu-id="0418a-113">**Office Web Apps Server internal attendee page: https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0\&embed=true&**</span></span>

<span data-ttu-id="0418a-114">Если вы видите событие LS Data MCU с кодом события 41033, это означает, что не удалось обнаружить сервер Office Web Apps.</span><span class="sxs-lookup"><span data-stu-id="0418a-114">If you see an LS Data MCU event with the event ID of 41033 that means that Office Web Apps Server discovery has failed.</span></span> <span data-ttu-id="0418a-115">В этом случае Microsoft Lync Server 2013 попытается выполнить столько раз, сколько нужно, чтобы найти только что настроенный сервер Office Web Apps.</span><span class="sxs-lookup"><span data-stu-id="0418a-115">In that case, Microsoft Lync Server 2013 will try as many times as needed to discover the newly-configured Office Web Apps Server.</span></span> <span data-ttu-id="0418a-116">Если процесс обнаружения завершается сбоем, необходимо удалить сервер Office Web Apps из документа топологии, опубликовать обновленную топологию и попробовать добавить сервер Office Web Apps обратно в топологию после устранения проблем с подключением.</span><span class="sxs-lookup"><span data-stu-id="0418a-116">If the discovery process fails repeatedly you should remove Office Web Apps Server from your topology document, publish the updated topology, and then try adding Office Web Apps Server back to the topology after the connectivity issues have been resolved.</span></span>

<span data-ttu-id="0418a-117">Если сервер Office Web Apps правильно настроен и обнаружен в процессе обнаружения, вы можете проверить правильность работы сервера Office Web Apps с помощью демонстрации презентации PowerPoint между парой клиентов Microsoft Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="0418a-117">If Office Web Apps Server appears to be configured correctly and has been recognized by the discovery process you can verify that Office Web Apps Server is working as expected by sharing a PowerPoint presentation between a pair of Microsoft Lync 2013 clients.</span></span> <span data-ttu-id="0418a-118">Если пользователь A может загрузить и отобразить презентацию PowerPoint, а затем пользователь B может присоединиться к собранию и просмотреть эту презентацию, будет ли работать сервер Office Web Apps.</span><span class="sxs-lookup"><span data-stu-id="0418a-118">If User A can load and display the PowerPoint presentation and if User B can then join the meeting and see that presentation then Office Web Apps Server is working.</span></span>

<span data-ttu-id="0418a-119">Даже если сервер Office Web Apps настроен правильно, может быть получено сообщение об ошибке "некоторые функции общего доступа недоступны из-за проблем с подключением к серверу" при попытке предоставить общий доступ к презентации PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="0418a-119">Even if Office Web Apps Server appears to be configured correctly, you could potentially receive the error message “Some sharing features are unavailable due to server connectivity issues” when you try sharing a PowerPoint presentation.</span></span> <span data-ttu-id="0418a-120">Если появится сообщение об ошибке, необходимо перезапустить сервер переднего плана (или серверы), связанный с новым сервером Office Web Apps.</span><span class="sxs-lookup"><span data-stu-id="0418a-120">If you receive that error message you should restart the Front End server (or servers) associated with the new Office Web Apps Server.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

