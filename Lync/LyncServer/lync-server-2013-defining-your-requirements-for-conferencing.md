---
title: 'Lync Server 2013: определение требований для конференц-связи'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Defining your requirements for conferencing
ms:assetid: 5c83e268-22bf-42b2-bac3-3237b5e02e03
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204935(v=OCS.15)
ms:contentKeyID: 48184255
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 60193673efff29ec877626a9c5c18be23507e6fa
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834702"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-your-requirements-for-conferencing-in-lync-server-2013"></a><span data-ttu-id="8c5d4-102">Определение требований для конференц-связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8c5d4-102">Defining your requirements for conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8c5d4-103">_**Тема последнего изменения:** 2012-09-30_</span><span class="sxs-lookup"><span data-stu-id="8c5d4-103">_**Topic Last Modified:** 2012-09-30_</span></span>

<span data-ttu-id="8c5d4-104">При выборе функциональных возможностей конференц-связи для развертывания следует определить, какие функции требуются пользователям, и учесть полосу пропускания сети.</span><span class="sxs-lookup"><span data-stu-id="8c5d4-104">When you are determining which conferencing capabilities to deploy, you need to consider the features that you want available to your users and your network bandwidth capabilities.</span></span> <span data-ttu-id="8c5d4-105">Ниже приведен список вопросов, которые помогут вам выполнить планирование конференций, чтобы определить, какие функции Конференции следует развернуть, в соответствии с требованиями вашей организации.</span><span class="sxs-lookup"><span data-stu-id="8c5d4-105">The following list of questions guides you through the conferencing planning process to determine what features of conferencing you should deploy, based on your organization’s requirements.</span></span>

  - <span data-ttu-id="8c5d4-106">**Требуется ли проведение веб-конференций для совместной работы с документами и общего доступа к приложениям?**</span><span class="sxs-lookup"><span data-stu-id="8c5d4-106">**Do you want to enable web conferencing, which includes document collaboration and application sharing?**</span></span>
    
    <span data-ttu-id="8c5d4-107">Если это так, необходимо включить Конференц-связь для своего пула переднего плана в Microsoft Lync Server 2013, планирование или в построителе топологии.</span><span class="sxs-lookup"><span data-stu-id="8c5d4-107">If so, you must enable conferencing for your Front End pool in the Microsoft Lync Server 2013, Planning Tool or in Topology Builder.</span></span> <span data-ttu-id="8c5d4-108">При включении конференции вы включаете как веб-конференции, так и конференции.</span><span class="sxs-lookup"><span data-stu-id="8c5d4-108">When you enable conferencing, you enable both web conferencing and A/V conferencing.</span></span>
    
    <span data-ttu-id="8c5d4-109">Для общего доступа к приложениям необходима более широкая полоса пропускания сети, чем для совместной работы с документами.</span><span class="sxs-lookup"><span data-stu-id="8c5d4-109">Application sharing requires and uses more network bandwidth than document collaboration.</span></span> <span data-ttu-id="8c5d4-110">Lync Server 2013 предоставляет механизм регулирования для управления сеансом совместного использования приложений.</span><span class="sxs-lookup"><span data-stu-id="8c5d4-110">Lync Server 2013 provides a throttling mechanism to control each application sharing session.</span></span> <span data-ttu-id="8c5d4-111">По умолчанию для каждого сеанса задано значение 1,5 кбит/с.</span><span class="sxs-lookup"><span data-stu-id="8c5d4-111">By default, this is set to 1.5 KB/second for each session.</span></span>
    
    <span data-ttu-id="8c5d4-112">Если вы не хотите включать общий доступ к приложениям, но вы хотите обеспечить совместную работу с документами, вы можете включить Конференц-связь и использовать политики собраний, чтобы отключить общий доступ к приложениям.</span><span class="sxs-lookup"><span data-stu-id="8c5d4-112">If you do not want to enable application sharing but you do want document collaboration, you can enable conferencing and use meeting policies to disable application sharing.</span></span> <span data-ttu-id="8c5d4-113">Подробнее о настройке политик собраний можно узнать [в статьях политики конференц-связи в Lync Server 2013](lync-server-2013-conferencing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="8c5d4-113">For details about configuring meeting policies, see [Conferencing policies in Lync Server 2013](lync-server-2013-conferencing-policies.md).</span></span>
    
    <span data-ttu-id="8c5d4-114">Если требуется разрешить пользователям предоставлять доступ к презентациям PowerPoint, необходимо настроить сервер Office Web Apps.</span><span class="sxs-lookup"><span data-stu-id="8c5d4-114">To enable users to share PowerPoint presentations, you need to configure Office Web Apps Server.</span></span> <span data-ttu-id="8c5d4-115">Подробнее о настройке Office Web Apps можно узнать в разделе [Настройка интеграции с Office Web Apps Server и Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span><span class="sxs-lookup"><span data-stu-id="8c5d4-115">For details about configuring Office Web Apps Server, see [Configuring integration with Office Web Apps Server and Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span></span>

  - <span data-ttu-id="8c5d4-116">**Вы хотите включить Конференц-связь/V?**</span><span class="sxs-lookup"><span data-stu-id="8c5d4-116">**Do you want to enable A/V conferencing?**</span></span>
    
    <span data-ttu-id="8c5d4-117">Если это так, необходимо включить Конференц-связь для пула переднего плана в Lync Server 2013, Planning Tool или в построителе топологии.</span><span class="sxs-lookup"><span data-stu-id="8c5d4-117">If so, you must enable conferencing for your Front End pool in the Lync Server 2013, Planning Tool or in Topology Builder.</span></span> <span data-ttu-id="8c5d4-118">При включении конференции вы включаете как веб-конференции, так и конференции.</span><span class="sxs-lookup"><span data-stu-id="8c5d4-118">When you enable conferencing, you enable both web conferencing and A/V conferencing.</span></span>
    
    <span data-ttu-id="8c5d4-119">Для проведения видеоконференций/V требуется больше пропускной способности сети, чем для веб-конференций (включая совместную работу с документами и общий доступ к приложениям).</span><span class="sxs-lookup"><span data-stu-id="8c5d4-119">A/V conferencing requires and uses more network bandwidth than web conferencing (which includes document collaboration and application sharing).</span></span> <span data-ttu-id="8c5d4-120">Если вы не хотите включать конференции/V, но вы хотите включить веб-конференции, вы можете включить Конференции и использовать политики собраний, чтобы отключить конференции/V.</span><span class="sxs-lookup"><span data-stu-id="8c5d4-120">If you do not want to enable A/V conferencing but you do want to enable web conferencing, you can enable conferencing and use meeting policies to disable A/V conferences.</span></span>
    
    <span data-ttu-id="8c5d4-121">Если вы хотите включить голосовые конференции, но не видеоконференции, вы можете включить Конференц-связь и использовать политики собраний для предотвращения видеоконференций.</span><span class="sxs-lookup"><span data-stu-id="8c5d4-121">If you do want to enable audio conferences but not video conferences, you can enable A/V conferencing and use meeting policies to prevent video conferences.</span></span> <span data-ttu-id="8c5d4-122">Можно также включить видео- и голосовую конференц-связь и разрешить открытие видео- и голосовых конференций и участие в них только некоторым пользователям.</span><span class="sxs-lookup"><span data-stu-id="8c5d4-122">Alternatively, you can enable A/V conferencing and enable only certain users to start or participate in A/V conferences.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="8c5d4-p109">Для видео- и голосовой конференц-связи не требуется корпоративная голосовая связь. Если видео- и голосовая конференц-связь включена, пользователи при наличии звуковых устройств включать голосовую связь на своих конференциях даже в том случае, если система телефонной связи представляет собой УАТС.</span><span class="sxs-lookup"><span data-stu-id="8c5d4-p109">Enterprise Voice is not required for you to use A/V conferencing. If you enable A/V conferencing, your users can add audio to their conferences if they have audio devices, even if you use a PBX for your telephone solution.</span></span>

    
    </div>

  - <span data-ttu-id="8c5d4-125">**Вы хотите разрешить пользователям присоединяться к звуковой части конференций при использовании телефонной сети PSTN?**</span><span class="sxs-lookup"><span data-stu-id="8c5d4-125">**Do you want to enable users to join the audio portion of conferences when using a PSTN phone?**</span></span>
    
    <span data-ttu-id="8c5d4-p110">Если да, то разверните конференц-связь с телефонным подключением и разрешите ее. После этого приглашенные пользователи, как из организации, так и вне ее, смогут присоединяться к звуковой части конференции с помощью телефона ТСОП.</span><span class="sxs-lookup"><span data-stu-id="8c5d4-p110">If so, deploy and enable dial-in conferencing. Invited users, both inside and outside your organization, can then join the audio portion of conferences by using a PSTN phone.</span></span>

  - <span data-ttu-id="8c5d4-128">**Вы хотите включить внешних пользователей с помощью клиентов Lync Server 2013, чтобы присоединиться к уже установленным конференциям?**</span><span class="sxs-lookup"><span data-stu-id="8c5d4-128">**Do you want to enable external users with Lync Server 2013 clients to join the types of conferences that you have enabled?**</span></span>
    
    <span data-ttu-id="8c5d4-129">Если это так, вы должны развернуть пограничные серверы.</span><span class="sxs-lookup"><span data-stu-id="8c5d4-129">If so, you should deploy Edge Servers.</span></span> <span data-ttu-id="8c5d4-130">Разрешая внешнее участие в собраниях, вы обеспечиваете максимально высокие затраты на Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8c5d4-130">By allowing external participation in meetings, you maximize your investment in Lync Server 2013.</span></span> <span data-ttu-id="8c5d4-131">Например, пользователи с ноутбуками с помощью Lync Server 2013 могут присоединиться к конференциям из любого места, где бы они ни находились — дома, в аэропорту или на сайтах клиентов.</span><span class="sxs-lookup"><span data-stu-id="8c5d4-131">For example, users with laptops with Lync Server 2013 can join conferences from wherever they are—at home, in the airport, or at customer sites.</span></span>
    
    <span data-ttu-id="8c5d4-132">Кроме того, при развертывании пограничных серверов вы можете создавать федеративные связи с другими организациями (например, клиентами или поставщиками), и пользователи из этих организаций смогут легко работать совместно с другими пользователями.</span><span class="sxs-lookup"><span data-stu-id="8c5d4-132">Additionally, with Edge Servers deployed you can create federated relationships with other organizations-such as your customers or vendors-and users from those organizations can more easily collaborate with your users.</span></span>
    
    <span data-ttu-id="8c5d4-133">Подробнее о том, как развертывать пограничные серверы, можно узнать [в разделе Планирование доступа внешних пользователей в Lync server 2013](lync-server-2013-planning-for-external-user-access.md) и [развертывание внешних пользователей в Lync Server 2013](lync-server-2013-deploying-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="8c5d4-133">For details about deploying Edge Servers, see [Planning for external user access in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md) and [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md).</span></span> <span data-ttu-id="8c5d4-134">Подробнее о том, как включить внешний доступ к серверу Office Web Apps, можно узнать [в разделе Публикация сервера Office Web Apps в Lync server 2013 с помощью обратного прокси-сервера](lync-server-2013-publishing-office-web-apps-server-using-a-reverse-proxy-server.md).</span><span class="sxs-lookup"><span data-stu-id="8c5d4-134">For details about enabling external access for Office Web Apps Server, see [Publishing Office Web Apps Server in Lync Server 2013 using a reverse proxy server](lync-server-2013-publishing-office-web-apps-server-using-a-reverse-proxy-server.md).</span></span>

  - <span data-ttu-id="8c5d4-135">**Хотите управлять клиентами, которые могут присоединиться к собраниям Lync Server 2013?**</span><span class="sxs-lookup"><span data-stu-id="8c5d4-135">**Do you want to control the clients that can join Lync Server 2013 meetings?**</span></span>
    
    <span data-ttu-id="8c5d4-136">В таком случае следует настроить страницу присоединения к собранию, чтобы были доступны только те параметры клиента, которые вы хотите поддерживать.</span><span class="sxs-lookup"><span data-stu-id="8c5d4-136">If so, you should configure the meeting join page so that only the client options that you want to support are available.</span></span> <span data-ttu-id="8c5d4-137">Каждый раз, когда пользователь щелкает ссылку для присоединения к запланированному собранию, Lync Server 2013 определяет, установлен ли на компьютере клиент.</span><span class="sxs-lookup"><span data-stu-id="8c5d4-137">Each time a user clicks a link to join a scheduled meeting, Lync Server 2013 detects whether a client is already installed on the computer.</span></span> <span data-ttu-id="8c5d4-138">Затем он запускает клиент по умолчанию и открывает страницу присоединения к собранию, которая содержит ссылки для альтернативных клиентов.</span><span class="sxs-lookup"><span data-stu-id="8c5d4-138">It then starts the default client and opens the meeting join page, which contains links for alternate clients.</span></span> <span data-ttu-id="8c5d4-139">На странице Присоединение к собранию всегда есть возможность использовать Microsoft Lync Web App.</span><span class="sxs-lookup"><span data-stu-id="8c5d4-139">The meeting join page always contains the option to use Microsoft Lync Web App.</span></span> <span data-ttu-id="8c5d4-140">В дополнение к этому параметру вы можете указать, нужно ли включать ссылки для участников и предыдущих версий Communicator.</span><span class="sxs-lookup"><span data-stu-id="8c5d4-140">In addition to this option, you can decide whether to include links for Attendee and previous versions of Communicator.</span></span> <span data-ttu-id="8c5d4-141">Дополнительные сведения можно найти [в разделе Настройка страницы присоединение к собранию в Lync Server 2013](lync-server-2013-configuring-the-meeting-join-page.md).</span><span class="sxs-lookup"><span data-stu-id="8c5d4-141">For details, see [Configuring the meeting join page in Lync Server 2013](lync-server-2013-configuring-the-meeting-join-page.md).</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="8c5d4-142">Содержание</span><span class="sxs-lookup"><span data-stu-id="8c5d4-142">In This Section</span></span>

  - [<span data-ttu-id="8c5d4-143">Требования для веб-конференций в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8c5d4-143">Web conferencing requirements in Lync Server 2013</span></span>](lync-server-2013-web-conferencing-requirements.md)

  - [<span data-ttu-id="8c5d4-144">Требования к Конференции в Lync Server 2013 и т. д.</span><span class="sxs-lookup"><span data-stu-id="8c5d4-144">A/V conferencing requirements in Lync Server 2013</span></span>](lync-server-2013-a-v-conferencing-requirements.md)

  - [<span data-ttu-id="8c5d4-145">Требования к конференц-связи с телефонным подключением в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8c5d4-145">Dial-in conferencing requirements in Lync Server 2013</span></span>](lync-server-2013-dial-in-conferencing-requirements.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="8c5d4-146">См. также</span><span class="sxs-lookup"><span data-stu-id="8c5d4-146">See Also</span></span>


[<span data-ttu-id="8c5d4-147">Планирование конференц-связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8c5d4-147">Planning for conferencing in Lync Server 2013</span></span>](lync-server-2013-planning-for-conferencing.md)  
[<span data-ttu-id="8c5d4-148">Контрольный список развертывания для конференций в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8c5d4-148">Deployment checklist for conferencing in Lync Server 2013</span></span>](lync-server-2013-deployment-checklist-for-conferencing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

