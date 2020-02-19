---
title: 'Lync Server 2013: определение требований для конференц-связи'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining your requirements for conferencing
ms:assetid: 5c83e268-22bf-42b2-bac3-3237b5e02e03
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204935(v=OCS.15)
ms:contentKeyID: 48184255
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ee3b7631a3c05fb497ee7fcdf37b6db984361845
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137820"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="defining-your-requirements-for-conferencing-in-lync-server-2013"></a><span data-ttu-id="9fe24-102">Определение требований для конференц-связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9fe24-102">Defining your requirements for conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9fe24-103">_**Последнее изменение темы:** 2012-09-30_</span><span class="sxs-lookup"><span data-stu-id="9fe24-103">_**Topic Last Modified:** 2012-09-30_</span></span>

<span data-ttu-id="9fe24-p101">При определении возможностей конференц-связи, которые следует развернуть, следует учитывать компоненты, доступные пользователям, а также пропускную способность сети. Следующий список вопросов помогает выполнить процесс планирования конференц-связи, чтобы определить, какие функции конференц-связи следует разворачивать, исходя из потребностей организации.</span><span class="sxs-lookup"><span data-stu-id="9fe24-p101">When you are determining which conferencing capabilities to deploy, you need to consider the features that you want available to your users and your network bandwidth capabilities. The following list of questions guides you through the conferencing planning process to determine what features of conferencing you should deploy, based on your organization’s requirements.</span></span>

  - <span data-ttu-id="9fe24-106">**Предполагается ли разрешить веб-конференции, которые включают совместную работу с документами и общий доступ к приложениям?**</span><span class="sxs-lookup"><span data-stu-id="9fe24-106">**Do you want to enable web conferencing, which includes document collaboration and application sharing?**</span></span>
    
    <span data-ttu-id="9fe24-107">В этом случае необходимо включить Конференц-связь для интерфейсного пула в Microsoft Lync Server 2013, Planning Tool или в построителе топологий.</span><span class="sxs-lookup"><span data-stu-id="9fe24-107">If so, you must enable conferencing for your Front End pool in the Microsoft Lync Server 2013, Planning Tool or in Topology Builder.</span></span> <span data-ttu-id="9fe24-108">При включении конференц-связи вы включаете как веб-конференции, так и аудио-и видеоконференции.</span><span class="sxs-lookup"><span data-stu-id="9fe24-108">When you enable conferencing, you enable both web conferencing and A/V conferencing.</span></span>
    
    <span data-ttu-id="9fe24-109">Общий доступ к приложениям требует и использует гораздо большую часть пропускной способности сети, чем совместная работа с документами.</span><span class="sxs-lookup"><span data-stu-id="9fe24-109">Application sharing requires and uses more network bandwidth than document collaboration.</span></span> <span data-ttu-id="9fe24-110">Lync Server 2013 предоставляет механизм регулирования для управления каждым сеансом общего доступа к приложениям.</span><span class="sxs-lookup"><span data-stu-id="9fe24-110">Lync Server 2013 provides a throttling mechanism to control each application sharing session.</span></span> <span data-ttu-id="9fe24-111">По умолчанию устанавливается 1,5 КБ/с для каждого сеанса.</span><span class="sxs-lookup"><span data-stu-id="9fe24-111">By default, this is set to 1.5 KB/second for each session.</span></span>
    
    <span data-ttu-id="9fe24-112">Если не планируется разрешать общий доступ к приложениям, но требуется совместная работа с документами, то можно разрешить конференц-связь и с помощью политик собраний отключить общий доступ к приложениям.</span><span class="sxs-lookup"><span data-stu-id="9fe24-112">If you do not want to enable application sharing but you do want document collaboration, you can enable conferencing and use meeting policies to disable application sharing.</span></span> <span data-ttu-id="9fe24-113">Дополнительные сведения о настройке политик собраний приведены [в статье политики конференц-связи в Lync Server 2013](lync-server-2013-conferencing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="9fe24-113">For details about configuring meeting policies, see [Conferencing policies in Lync Server 2013](lync-server-2013-conferencing-policies.md).</span></span>
    
    <span data-ttu-id="9fe24-114">Чтобы предоставить пользователям доступ к презентациям PowerPoint, необходимо настроить сервер Office Web Apps.</span><span class="sxs-lookup"><span data-stu-id="9fe24-114">To enable users to share PowerPoint presentations, you need to configure Office Web Apps Server.</span></span> <span data-ttu-id="9fe24-115">Дополнительные сведения о настройке сервера Office Web Apps приведены [в статье Настройка интеграции с сервером Office Web Apps и Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span><span class="sxs-lookup"><span data-stu-id="9fe24-115">For details about configuring Office Web Apps Server, see [Configuring integration with Office Web Apps Server and Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span></span>

  - <span data-ttu-id="9fe24-116">**Предполагается ли разрешить аудио- и видеоконференции?**</span><span class="sxs-lookup"><span data-stu-id="9fe24-116">**Do you want to enable A/V conferencing?**</span></span>
    
    <span data-ttu-id="9fe24-117">В этом случае необходимо включить Конференц-связь для интерфейсного пула в Lync Server 2013, Planning Tool или в построителе топологий.</span><span class="sxs-lookup"><span data-stu-id="9fe24-117">If so, you must enable conferencing for your Front End pool in the Lync Server 2013, Planning Tool or in Topology Builder.</span></span> <span data-ttu-id="9fe24-118">При включении конференц-связи вы включаете как веб-конференции, так и аудио-и видеоконференции.</span><span class="sxs-lookup"><span data-stu-id="9fe24-118">When you enable conferencing, you enable both web conferencing and A/V conferencing.</span></span>
    
    <span data-ttu-id="9fe24-p107">Аудио- и видеоконференции требуют и используют гораздо большую часть пропускной способности сети, чем веб-конференции (включающие совместную работу с документами и общий доступ к приложениям). Если вы не хотите разрешать аудио- и видеоконференции, то можно разрешить конференц-связь и с помощью политик собраний отключить аудио- и видеоконференции.</span><span class="sxs-lookup"><span data-stu-id="9fe24-p107">A/V conferencing requires and uses more network bandwidth than web conferencing (which includes document collaboration and application sharing). If you do not want to enable A/V conferencing but you do want to enable web conferencing, you can enable conferencing and use meeting policies to disable A/V conferences.</span></span>
    
    <span data-ttu-id="9fe24-p108">Если вы хотите разрешить аудиоконференции, но не видеоконференции, можно разрешить аудио- и видеоконференции, а затем с помощью политик собраний запретить видеоконференции. Кроме того, можно разрешить аудио- и видеоконференции, а затем разрешить инициировать эти конференции или участвовать в них только определенным пользователям.</span><span class="sxs-lookup"><span data-stu-id="9fe24-p108">If you do want to enable audio conferences but not video conferences, you can enable A/V conferencing and use meeting policies to prevent video conferences. Alternatively, you can enable A/V conferencing and enable only certain users to start or participate in A/V conferences.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="9fe24-123">Корпоративная голосовая связь не требуется для использования аудио-и видеоконференций.</span><span class="sxs-lookup"><span data-stu-id="9fe24-123">Enterprise Voice is not required for you to use A/V conferencing.</span></span> <span data-ttu-id="9fe24-124">Если вы включаете аудио-и видеоконференции, пользователи могут добавлять звук в свои конференции, если у них есть звуковые устройства, даже если вы используете УАТС для своего телефонного решения.</span><span class="sxs-lookup"><span data-stu-id="9fe24-124">If you enable A/V conferencing, your users can add audio to their conferences if they have audio devices, even if you use a PBX for your telephone solution.</span></span>

    
    </div>

  - <span data-ttu-id="9fe24-125">**Предполагается ли разрешить пользователям присоединяться к звуковой части конференций с помощью телефона ТСОП?**</span><span class="sxs-lookup"><span data-stu-id="9fe24-125">**Do you want to enable users to join the audio portion of conferences when using a PSTN phone?**</span></span>
    
    <span data-ttu-id="9fe24-p110">Если да, то разверните конференц-связь с телефонным подключением и разрешите ее. После этого приглашенные пользователи, как из организации, так и вне ее, смогут присоединяться к звуковой части конференции с помощью телефона ТСОП.</span><span class="sxs-lookup"><span data-stu-id="9fe24-p110">If so, deploy and enable dial-in conferencing. Invited users, both inside and outside your organization, can then join the audio portion of conferences by using a PSTN phone.</span></span>

  - <span data-ttu-id="9fe24-128">**Хотите ли вы включить внешних пользователей с клиентами Lync Server 2013, чтобы присоединиться к включенным типам конференций?**</span><span class="sxs-lookup"><span data-stu-id="9fe24-128">**Do you want to enable external users with Lync Server 2013 clients to join the types of conferences that you have enabled?**</span></span>
    
    <span data-ttu-id="9fe24-129">В этом случае необходимо развернуть пограничные серверы.</span><span class="sxs-lookup"><span data-stu-id="9fe24-129">If so, you should deploy Edge Servers.</span></span> <span data-ttu-id="9fe24-130">Разрешая внешнее участие в собраниях, вы максимизируя инвестиции в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9fe24-130">By allowing external participation in meetings, you maximize your investment in Lync Server 2013.</span></span> <span data-ttu-id="9fe24-131">Например, пользователи с ноутбуками с Lync Server 2013 могут присоединяться к конференциям из любой точки, дома, в аэропорту или на сайтах клиентов.</span><span class="sxs-lookup"><span data-stu-id="9fe24-131">For example, users with laptops with Lync Server 2013 can join conferences from wherever they are—at home, in the airport, or at customer sites.</span></span>
    
    <span data-ttu-id="9fe24-132">Кроме того, при развертывании пограничных серверов можно создавать федеративные отношения с другими организациями, такими как клиенты или поставщики, и пользователи из этих организаций могут работать совместно с другими пользователями.</span><span class="sxs-lookup"><span data-stu-id="9fe24-132">Additionally, with Edge Servers deployed you can create federated relationships with other organizations-such as your customers or vendors-and users from those organizations can more easily collaborate with your users.</span></span>
    
    <span data-ttu-id="9fe24-133">Дополнительные сведения о развертывании пограничных серверов приведены [в статье Планирование доступа внешних пользователей в Lync server 2013](lync-server-2013-planning-for-external-user-access.md) и [развертывание доступа внешних пользователей в Lync Server 2013](lync-server-2013-deploying-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="9fe24-133">For details about deploying Edge Servers, see [Planning for external user access in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md) and [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md).</span></span> <span data-ttu-id="9fe24-134">Дополнительные сведения о том, как активировать внешний доступ к серверу Office Web Apps, можно узнать [в статье публикация сервера Office Web Apps в Lync server 2013 с помощью обратного прокси-сервера](lync-server-2013-publishing-office-web-apps-server-using-a-reverse-proxy-server.md).</span><span class="sxs-lookup"><span data-stu-id="9fe24-134">For details about enabling external access for Office Web Apps Server, see [Publishing Office Web Apps Server in Lync Server 2013 using a reverse proxy server](lync-server-2013-publishing-office-web-apps-server-using-a-reverse-proxy-server.md).</span></span>

  - <span data-ttu-id="9fe24-135">**Хотите контролировать клиенты, которые могут присоединиться к собраниям Lync Server 2013?**</span><span class="sxs-lookup"><span data-stu-id="9fe24-135">**Do you want to control the clients that can join Lync Server 2013 meetings?**</span></span>
    
    <span data-ttu-id="9fe24-136">Если да, то необходимо настроить страницу присоединения к собраниям, чтобы были доступны только те варианты клиентов, которые вы хотите поддерживать.</span><span class="sxs-lookup"><span data-stu-id="9fe24-136">If so, you should configure the meeting join page so that only the client options that you want to support are available.</span></span> <span data-ttu-id="9fe24-137">Каждый раз, когда пользователь щелкает ссылку для присоединения к запланированному собранию, Lync Server 2013 определяет, установлен ли на компьютере клиент.</span><span class="sxs-lookup"><span data-stu-id="9fe24-137">Each time a user clicks a link to join a scheduled meeting, Lync Server 2013 detects whether a client is already installed on the computer.</span></span> <span data-ttu-id="9fe24-138">Затем он открывает клиент по умолчанию и открывает страницу присоединения к собраниям, на которой имеются ссылки на другие клиенты.</span><span class="sxs-lookup"><span data-stu-id="9fe24-138">It then starts the default client and opens the meeting join page, which contains links for alternate clients.</span></span> <span data-ttu-id="9fe24-139">Страница присоединения к собранию всегда содержит параметр для использования Microsoft Lync Web App.</span><span class="sxs-lookup"><span data-stu-id="9fe24-139">The meeting join page always contains the option to use Microsoft Lync Web App.</span></span> <span data-ttu-id="9fe24-140">Кроме того, вы можете указать, следует ли включать ссылки для участников и предыдущих версий Communicator.</span><span class="sxs-lookup"><span data-stu-id="9fe24-140">In addition to this option, you can decide whether to include links for Attendee and previous versions of Communicator.</span></span> <span data-ttu-id="9fe24-141">Дополнительные сведения: [Настройка страницы присоединения к собранию в Lync Server 2013](lync-server-2013-configuring-the-meeting-join-page.md).</span><span class="sxs-lookup"><span data-stu-id="9fe24-141">For details, see [Configuring the meeting join page in Lync Server 2013](lync-server-2013-configuring-the-meeting-join-page.md).</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="9fe24-142">Содержание</span><span class="sxs-lookup"><span data-stu-id="9fe24-142">In This Section</span></span>

  - [<span data-ttu-id="9fe24-143">Требования к веб-конференциям в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9fe24-143">Web conferencing requirements in Lync Server 2013</span></span>](lync-server-2013-web-conferencing-requirements.md)

  - [<span data-ttu-id="9fe24-144">Требования к аудио-и видеоконференциям в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9fe24-144">A/V conferencing requirements in Lync Server 2013</span></span>](lync-server-2013-a-v-conferencing-requirements.md)

  - [<span data-ttu-id="9fe24-145">Требования к конференц-связи с телефонным подключением в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9fe24-145">Dial-in conferencing requirements in Lync Server 2013</span></span>](lync-server-2013-dial-in-conferencing-requirements.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="9fe24-146">См. также</span><span class="sxs-lookup"><span data-stu-id="9fe24-146">See Also</span></span>


[<span data-ttu-id="9fe24-147">Планирование конференц-связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9fe24-147">Planning for conferencing in Lync Server 2013</span></span>](lync-server-2013-planning-for-conferencing.md)  
[<span data-ttu-id="9fe24-148">Контрольный список развертывания для конференц-связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9fe24-148">Deployment checklist for conferencing in Lync Server 2013</span></span>](lync-server-2013-deployment-checklist-for-conferencing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

