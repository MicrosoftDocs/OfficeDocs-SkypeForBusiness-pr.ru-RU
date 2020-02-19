---
title: 'Lync Server 2013: Проверка конфигурации сервера Office Web Apps'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Validating the configuration of Office Web Apps Server
ms:assetid: f6e8ecbf-305d-4a13-92d0-b61dbd82b0ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205393(v=OCS.15)
ms:contentKeyID: 48185859
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3c1cabdf03250a056c2fedaeb41e1f6839aea75a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42113412"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="validating-the-configuration-of-office-web-apps-server-in-lync-server-2013"></a><span data-ttu-id="7627a-102">Проверка конфигурации сервера Office Web Apps в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7627a-102">Validating the configuration of Office Web Apps Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7627a-103">_**Последнее изменение темы:** 2014-04-22_</span><span class="sxs-lookup"><span data-stu-id="7627a-103">_**Topic Last Modified:** 2014-04-22_</span></span>

<span data-ttu-id="7627a-104">После добавления сервера Office Web Apps в топологию и после публикации этой топологии в журнале событий Lync Server должны появиться два новых события журнала событий.</span><span class="sxs-lookup"><span data-stu-id="7627a-104">After Office Web Apps Server has been added to the topology, and after that topology has been published, you should see two new event log events in the Lync Server event log.</span></span> <span data-ttu-id="7627a-105">Сначала необходимо добавить событие MCU для данных LS (Event ID 41034); Это событие сообщит о том, что сервер Office Web Apps обнаружен:</span><span class="sxs-lookup"><span data-stu-id="7627a-105">First, an LS Data MCU event (event ID 41034) should be added; this event will report that the Office Web Apps Server has been discovered:</span></span>

<span data-ttu-id="7627a-106">**Сервер веб-конференций сервер Office Web Apps обнаружен, содержимое PowerPoint включено.**</span><span class="sxs-lookup"><span data-stu-id="7627a-106">**Web Conferencing Server Office Web Apps Server is discovered, PowerPoint content is enabled.**</span></span>

<span data-ttu-id="7627a-p102">Кроме того, должно отображаться другое событие LS Data MCU (идентификатор события — 41032), которое отправляют URL-адреса сервера Office Web Apps. Это событие может иметь, например, следующий вид:</span><span class="sxs-lookup"><span data-stu-id="7627a-p102">In addition to that you should see another LS Data MCU event (event ID 41032) that reports back Office Web Apps Server URLs. For example, you should see something similar to this:</span></span>

<span data-ttu-id="7627a-109">**Сервер веб-конференций сервер Office Web Apps обнаружил успешность.**</span><span class="sxs-lookup"><span data-stu-id="7627a-109">**Web Conferencing Server Office Web Apps Server discovery has succeeded.**</span></span>

<span data-ttu-id="7627a-110">**Внутренняя страница выступающего сервера Office Web Apps:https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0\&embed=**</span><span class="sxs-lookup"><span data-stu-id="7627a-110">**Office Web Apps Server internal presenter page: https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0\&embed=**</span></span>

<span data-ttu-id="7627a-111">**Страница внутреннего участника сервера Office Web Apps:https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0\&embed=true&=**</span><span class="sxs-lookup"><span data-stu-id="7627a-111">**Office Web Apps Server internal attendee page: https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0\&embed=true&=**</span></span>

<span data-ttu-id="7627a-112">**Внешняя страница докладчика сервера Office Web Apps:https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0\&embed**</span><span class="sxs-lookup"><span data-stu-id="7627a-112">**Office Web Apps Server external presenter page: https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0\&embed**</span></span>

<span data-ttu-id="7627a-113">**Страница внутреннего участника сервера Office Web Apps:https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0\&embed=true&**</span><span class="sxs-lookup"><span data-stu-id="7627a-113">**Office Web Apps Server internal attendee page: https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0\&embed=true&**</span></span>

<span data-ttu-id="7627a-114">Если событие LS Data MCU отображается с идентификатором события 41033, это означает, что произошел сбой обнаружения сервера Office Web Apps Server.</span><span class="sxs-lookup"><span data-stu-id="7627a-114">If you see an LS Data MCU event with the event ID of 41033 that means that Office Web Apps Server discovery has failed.</span></span> <span data-ttu-id="7627a-115">В этом случае Microsoft Lync Server 2013 будет пытаться попытаться столько раз, сколько необходимо для обнаружения нового настроенного сервера Office Web Apps.</span><span class="sxs-lookup"><span data-stu-id="7627a-115">In that case, Microsoft Lync Server 2013 will try as many times as needed to discover the newly-configured Office Web Apps Server.</span></span> <span data-ttu-id="7627a-116">Если происходит многократный сбой процесса обнаружения, следует удалить сервер Office Web Apps из документа топологии, опубликовать обновленную топологию, а затем снова попробовать добавить сервер Office Web Apps в топологию после устранения неполадок, связанных с подключением.</span><span class="sxs-lookup"><span data-stu-id="7627a-116">If the discovery process fails repeatedly you should remove Office Web Apps Server from your topology document, publish the updated topology, and then try adding Office Web Apps Server back to the topology after the connectivity issues have been resolved.</span></span>

<span data-ttu-id="7627a-117">Если сервер Office Web Apps настроен правильно и распознается процессом обнаружения, можно проверить, что сервер Office Web Apps работает надлежащим образом, выполнив совместное использование презентации PowerPoint между двумя клиентами Microsoft Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="7627a-117">If Office Web Apps Server appears to be configured correctly and has been recognized by the discovery process you can verify that Office Web Apps Server is working as expected by sharing a PowerPoint presentation between a pair of Microsoft Lync 2013 clients.</span></span> <span data-ttu-id="7627a-118">Если пользователь А может загружать и отображать презентацию PowerPoint, а пользователь Б затем может присоединяться к собранию и просматривать презентацию, сервер Office Web Apps функционирует правильно.</span><span class="sxs-lookup"><span data-stu-id="7627a-118">If User A can load and display the PowerPoint presentation and if User B can then join the meeting and see that presentation then Office Web Apps Server is working.</span></span>

<span data-ttu-id="7627a-p105">Даже если кажется, что сервер Office Web Apps настроен правильно, при попытке совместного использования презентации PowerPoint существует вероятность возникновения сообщения об ошибке "Некоторые функции общего доступа недоступны из-за проблем с подключением к серверу". В случае отображения этого сообщения об ошибке следует перезапустить серверы переднего плана, сопоставленные с новым сервером Office Web Apps.</span><span class="sxs-lookup"><span data-stu-id="7627a-p105">Even if Office Web Apps Server appears to be configured correctly, you could potentially receive the error message “Some sharing features are unavailable due to server connectivity issues” when you try sharing a PowerPoint presentation. If you receive that error message you should restart the Front End server (or servers) associated with the new Office Web Apps Server.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

