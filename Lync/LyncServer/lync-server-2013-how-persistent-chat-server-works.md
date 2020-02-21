---
title: 'Lync Server 2013: работа сервера сохраняемого чата'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: How Persistent Chat Server works
ms:assetid: 3d04e9a1-3f0c-458e-bcbe-d27c8c464276
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ683096(v=OCS.15)
ms:contentKeyID: 49684643
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4a88bdad2a73022468297d73dd10bff0d26a3fee
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42214755"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="how-persistent-chat-server-works-in-lync-server-2013"></a><span data-ttu-id="de885-102">Принцип работы сервера сохраняемого чата в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="de885-102">How Persistent Chat Server works in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="de885-103">_**Последнее изменение темы:** 2012-11-21_</span><span class="sxs-lookup"><span data-stu-id="de885-103">_**Topic Last Modified:** 2012-11-21_</span></span>

<span data-ttu-id="de885-104">Lync Server 2013, сервер сохраняемого чата позволяет принимать участие в многосторонних беседах на основе тем, которые сохраняются со временем.</span><span class="sxs-lookup"><span data-stu-id="de885-104">Lync Server 2013, Persistent Chat Server enables you to participate in multiparty, topic-based conversations that persist over time.</span></span> <span data-ttu-id="de885-105">Сервер сохраняемого чата поможет вашей организации выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="de885-105">Persistent Chat Server can help your organization do the following:</span></span>

  - <span data-ttu-id="de885-106">Улучшить связь между рабочими группами, которые географически рассредоточены и выполняют разные функции.</span><span class="sxs-lookup"><span data-stu-id="de885-106">Improve communication between geographically dispersed and cross-functional teams</span></span>

  - <span data-ttu-id="de885-107">Расширить доступ к информации и партнерские отношения.</span><span class="sxs-lookup"><span data-stu-id="de885-107">Broaden information awareness and participation</span></span>

  - <span data-ttu-id="de885-108">Улучшить связь в крупной организации.</span><span class="sxs-lookup"><span data-stu-id="de885-108">Improve communication with your extended organization</span></span>

  - <span data-ttu-id="de885-109">Уменьшить информационную нагрузку.</span><span class="sxs-lookup"><span data-stu-id="de885-109">Reduce information overload</span></span>

  - <span data-ttu-id="de885-110">Улучшить информированность.</span><span class="sxs-lookup"><span data-stu-id="de885-110">Improve information awareness</span></span>

  - <span data-ttu-id="de885-111">Увеличить распределение важного знания и информации.</span><span class="sxs-lookup"><span data-stu-id="de885-111">Increase dispersion of important knowledge and information</span></span>

<span data-ttu-id="de885-112">Сервер сохраняемого чата можно развернуть в качестве дополнительной роли с Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="de885-112">You can deploy Persistent Chat Server as an optional role with Lync Server 2013.</span></span> <span data-ttu-id="de885-113">Службы сохраняемого чата выполняются в выделенном пуле, а пул серверов сохраняемого чата зависит от пула Lync Server для маршрутизации сообщений.</span><span class="sxs-lookup"><span data-stu-id="de885-113">Persistent Chat services run on a dedicated pool, and a Persistent Chat Server pool depends on a Lync Server pool to route messages to it.</span></span> <span data-ttu-id="de885-114">Клиенты используют протокол XCCOS (eXtensible Chat Communication Over SIP).</span><span class="sxs-lookup"><span data-stu-id="de885-114">Clients use eXtensible Chat Communication Over SIP (XCCOS).</span></span> <span data-ttu-id="de885-115">Серверы переднего плана Lync Server настраиваются на маршрутизацию трафика в пул серверов сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="de885-115">The Lync Server Front End Servers are configured to route the traffic to a Persistent Chat Server pool.</span></span>

<div>

## <a name="high-level-architecture"></a><span data-ttu-id="de885-116">Высокоуровневая архитектура</span><span class="sxs-lookup"><span data-stu-id="de885-116">High-Level Architecture</span></span>

<span data-ttu-id="de885-117">На следующих схемах представлены высокие уровни архитектуры и служб сервера сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="de885-117">The following diagrams provide high-level perspectives of the Persistent Chat Server architecture and services.</span></span>

<span data-ttu-id="de885-118">**Высокоуровневая архитектура сервера сохраняемого чата**</span><span class="sxs-lookup"><span data-stu-id="de885-118">**Persistent Chat Server High-Level Architecture**</span></span>

<span data-ttu-id="de885-119">![Архитектура сервера сохраняемого чата.](images/JJ683096.5db6f36f-4461-4d87-ba77-463b7ffe609b(OCS.15).jpg "Архитектура сервера сохраняемого чата.")</span><span class="sxs-lookup"><span data-stu-id="de885-119">![Persistent Chat Server architecture.](images/JJ683096.5db6f36f-4461-4d87-ba77-463b7ffe609b(OCS.15).jpg "Persistent Chat Server architecture.")</span></span>

<span data-ttu-id="de885-120">**Высокоуровневые службы сервера сохраняемого чата**</span><span class="sxs-lookup"><span data-stu-id="de885-120">**Persistent Chat Server High-Level Services**</span></span>

<span data-ttu-id="de885-121">![Компоненты сервера сохраняемого чата.](images/JJ683096.b6d743aa-3a86-4081-aaef-4fe3257db4e7(OCS.15).jpg "Компоненты сервера сохраняемого чата.")</span><span class="sxs-lookup"><span data-stu-id="de885-121">![Persistent Chat Server components.](images/JJ683096.b6d743aa-3a86-4081-aaef-4fe3257db4e7(OCS.15).jpg "Persistent Chat Server components.")</span></span>

<span data-ttu-id="de885-122">На серверах переднего плана сервера сохраняемого чата выполняются две службы:</span><span class="sxs-lookup"><span data-stu-id="de885-122">Two services run on the Persistent Chat Server Front End Servers:</span></span>

  - <span data-ttu-id="de885-123">Сохраняемый чат (канал)</span><span class="sxs-lookup"><span data-stu-id="de885-123">Persistent Chat (Channel)</span></span>

  - <span data-ttu-id="de885-124">Соответствие требованиям</span><span class="sxs-lookup"><span data-stu-id="de885-124">Compliance</span></span>

<div>

## <a name="persistent-chat-channel-service"></a><span data-ttu-id="de885-125">Служба сохраняемого чата (канала)</span><span class="sxs-lookup"><span data-stu-id="de885-125">Persistent Chat (Channel) Service</span></span>

<span data-ttu-id="de885-126">Служба сохраняемого чата (Channel) — это основная служба, ответственная за сервер сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="de885-126">The Persistent Chat (Channel) service is the core service responsible for Persistent Chat Server.</span></span> <span data-ttu-id="de885-127">Данная служба предоставляет следующие функции.</span><span class="sxs-lookup"><span data-stu-id="de885-127">This service provides the following functions:</span></span>

  - <span data-ttu-id="de885-128">Принимает входящие сообщения</span><span class="sxs-lookup"><span data-stu-id="de885-128">Accepts incoming messages</span></span>

  - <span data-ttu-id="de885-129">Регистрация и перечисление интерактивных участников в комнате сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="de885-129">Registers and lists online participants within a Persistent Chat room</span></span>

  - <span data-ttu-id="de885-130">Передает сообщения другим подписчикам канала</span><span class="sxs-lookup"><span data-stu-id="de885-130">Retransmits messages to other channel subscribers</span></span>

  - <span data-ttu-id="de885-131">Реализует логику управления каналом, приглашения в комнату чата и уведомлений о появлении нового контента</span><span class="sxs-lookup"><span data-stu-id="de885-131">Implements logic for channel management, chat room invitation, search, and new content notifications</span></span>

<span data-ttu-id="de885-132">Служба сохраняемого чата (канал) хранит и получает доступ к содержимому комнаты чата и другим системным метаданным (правилам авторизации и т. д.) с помощью хранилища сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="de885-132">The Persistent Chat (Channel) service stores and accesses chat room content and other system metadata (authorization rules, and so on) by using the Persistent Chat Store.</span></span> <span data-ttu-id="de885-133">Эта служба хранит файлы, которые отправляются в комнаты чата в хранилище файлов сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="de885-133">This service stores files that are uploaded into chat rooms in the Persistent Chat File Store.</span></span>

</div>

<div>

## <a name="compliance-service"></a><span data-ttu-id="de885-134">Служба соответствия</span><span class="sxs-lookup"><span data-stu-id="de885-134">Compliance Service</span></span>

<span data-ttu-id="de885-135">Служба соответствия является опциональным компонентом сервера сохраняемого чата и отвечает за архивацию содержимого и событий чата в хранилище соответствия сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="de885-135">The Compliance service is an optional component of Persistent Chat Server and is responsible for archiving chat content and events to the Persistent Chat Compliance Store.</span></span> <span data-ttu-id="de885-136">Если в Организации есть нормативы, для которых требуется архивировать действия сохраняемого чата, можно развернуть необязательную службу соответствия сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="de885-136">If your organization has regulations that require Persistent Chat activity to be archived, you can deploy the optional Persistent Chat Compliance service.</span></span> <span data-ttu-id="de885-137">Служба соответствия устанавливается на каждом сервере сохраняемого чата в пуле сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="de885-137">The Compliance service is installed on each Persistent Chat Server in a Persistent Chat pool.</span></span> <span data-ttu-id="de885-138">При настройке сервер сохраняемого чата регистрирует действия пользователя, такие как присоединение к комнатам и выход из них, а также учет и чтение сообщений.</span><span class="sxs-lookup"><span data-stu-id="de885-138">When configured, Persistent Chat Server compliance records user activity such as joining and leaving rooms, and posting and reading of messages.</span></span> <span data-ttu-id="de885-139">Служба соответствия хранит файлы, которые необходимо архивировать в хранилище файлов соответствия сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="de885-139">The Compliance service stores files that need to be archived in the Persistent Chat Compliance File Store.</span></span>

</div>

<div>

## <a name="persistent-chat-web-services"></a><span data-ttu-id="de885-140">Веб-службы сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="de885-140">Persistent Chat Web Services</span></span>

<span data-ttu-id="de885-141">На серверах переднего плана Lync Server запускаются две службы, которые зависят от служб IIS, и реализуются как веб-компоненты:</span><span class="sxs-lookup"><span data-stu-id="de885-141">On the Lync Server Front End Servers, two services run that depend on Internet Information Services (IIS), and are implemented as web components:</span></span>

  - <span data-ttu-id="de885-142">**Веб-службы сохраняемого чата для отправки и загрузки файлов** Отвечает за разноски и получение файлов из комнат чата.</span><span class="sxs-lookup"><span data-stu-id="de885-142">**Persistent Chat Web Services for File Upload/Download** Responsible for posting and retrieving files from chat rooms.</span></span>

  - <span data-ttu-id="de885-143">**Веб-службы сохраняемого чата для управления комнатами чата** Отвечает за предоставление пользователям возможности управления комнатами чата и создания новых комнат чата.</span><span class="sxs-lookup"><span data-stu-id="de885-143">**Persistent Chat Web Services for Chat Room Management** Responsible for providing users the ability to manage their chat rooms, and create new chat rooms.</span></span>

</div>

</div>

<div>

## <a name="how-do-i-start-using-persistent-chat-server"></a><span data-ttu-id="de885-144">Как начать работу с сервером сохраняемого чата?</span><span class="sxs-lookup"><span data-stu-id="de885-144">How Do I Start Using Persistent Chat Server?</span></span>

<span data-ttu-id="de885-145">Сервер сохраняемого чата является необязательной ролью сервера в инфраструктуре Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="de885-145">Persistent Chat Server is an optional server role within the Lync Server 2013 infrastructure.</span></span> <span data-ttu-id="de885-146">При установке роли сервера сохраняемого чата все пользователи, которые были включены с помощью политики администратором, могут использовать сохраняемый чат с клиентом Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="de885-146">If you install the Persistent Chat Server role, any users who have been enabled through policy by an administrator can use Persistent Chat with the Lync 2013 client.</span></span>

<span data-ttu-id="de885-147">Сведения о развертывании сервера сохраняемого чата и о том, как разрешить пользователям использовать возможности с помощью политики, приведены [в разделе Развертывание сервера сохраняемого чата в Lync server 2013](lync-server-2013-deploying-persistent-chat-server.md).</span><span class="sxs-lookup"><span data-stu-id="de885-147">For details about how to deploy Persistent Chat Server and enable users to leverage the capabilities by policy, see [Deploying Persistent Chat Server in Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md).</span></span>

<span data-ttu-id="de885-148">Сведения о настройке параметров развертывания сервера сохраняемого чата [в разделе Развертывание сервера сохраняемого чата в Lync server 2013](lync-server-2013-deploying-persistent-chat-server.md) и [управление Lync Server 2013, сервер сохраняемого чата](managing-lync-server-2013-persistent-chat-server.md).</span><span class="sxs-lookup"><span data-stu-id="de885-148">For details about how to configure settings on your Persistent Chat Server deployment, see [Deploying Persistent Chat Server in Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md) and [Managing Lync Server 2013, Persistent Chat Server](managing-lync-server-2013-persistent-chat-server.md).</span></span>

<span data-ttu-id="de885-149">Сведения о том, как включить пользователям с помощью политики, чтобы использовать функции сохраняемого чата в клиенте Lync 2013, можно узнать в статье [развертывание сервера сохраняемого чата в Lync server 2013](lync-server-2013-deploying-persistent-chat-server.md) и [управление Lync Server 2013, сервер сохраняемого чата](managing-lync-server-2013-persistent-chat-server.md).</span><span class="sxs-lookup"><span data-stu-id="de885-149">For details about how to enable users by policy such that they can leverage Persistent Chat functionality in Lync 2013 client, see [Deploying Persistent Chat Server in Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md) and [Managing Lync Server 2013, Persistent Chat Server](managing-lync-server-2013-persistent-chat-server.md).</span></span>

<span data-ttu-id="de885-150">Если вы развернули соответствие сохраняемого чата, ознакомьтесь со статьей [Управление Lync server 2013, сервер сохраняемого чата](managing-lync-server-2013-persistent-chat-server.md) для получения дополнительных сведений о настройке параметров для обеспечения соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="de885-150">If you deployed Persistent Chat compliance, see [Managing Lync Server 2013, Persistent Chat Server](managing-lync-server-2013-persistent-chat-server.md) for details about how to configure settings for compliance.</span></span>

</div>

<div>

## <a name="persistent-chat-call-flows"></a><span data-ttu-id="de885-151">Потоки вызовов сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="de885-151">Persistent Chat Call Flows</span></span>

<span data-ttu-id="de885-152">Клиент сохраняемого чата обменивается данными со службой сохраняемого чата с помощью XCCOS.</span><span class="sxs-lookup"><span data-stu-id="de885-152">The Persistent Chat client communicates with the Persistent Chat service by using XCCOS.</span></span> <span data-ttu-id="de885-153">В следующих последовательностях описывается процесс входа и типичный сценарий подписки на комнаты и публикации сообщений.</span><span class="sxs-lookup"><span data-stu-id="de885-153">The following sequences describe the sign-in process and a typical room subscription and message post scenario.</span></span>

<div>

## <a name="sign-in"></a><span data-ttu-id="de885-154">Вход</span><span class="sxs-lookup"><span data-stu-id="de885-154">Sign-in</span></span>

<span data-ttu-id="de885-155">Приведенная ниже схема и пошаговые инструкции описывают процесс входа.</span><span class="sxs-lookup"><span data-stu-id="de885-155">The following call flow diagram and steps describe the sign-in process.</span></span>

<span data-ttu-id="de885-156">**Процесс входа клиента сохраняемого чата**</span><span class="sxs-lookup"><span data-stu-id="de885-156">**Persistent Chat Client Sign-in Call Flow**</span></span>

<span data-ttu-id="de885-157">![Схема последовательности вызовов сервера сохраняемого чата.](images/JJ683096.9b3b3c61-caca-42b6-853c-6a09e6ff5c44(OCS.15).jpg "Схема последовательности вызовов сервера сохраняемого чата.")</span><span class="sxs-lookup"><span data-stu-id="de885-157">![Persistent Chat Server call flow diagram.](images/JJ683096.9b3b3c61-caca-42b6-853c-6a09e6ff5c44(OCS.15).jpg "Persistent Chat Server call flow diagram.")</span></span>

1.  <span data-ttu-id="de885-158">Сначала клиент сохраняемого чата отправляет подписку по протоколу SIP, чтобы получить из сервера встроенный документ подготовки.</span><span class="sxs-lookup"><span data-stu-id="de885-158">The Persistent Chat client first sends a SIP SUBSCRIBE to retrieve the in-band provisioning document from the server.</span></span> <span data-ttu-id="de885-159">Этот документ указывает, включено или выключено сохраняемый чат для пользователя и список URI SIP для пула серверов сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="de885-159">This document indicates if Persistent Chat is enabled or disabled for the user and the list of SIP URIs for the Persistent Chat Server pool.</span></span>

2.  <span data-ttu-id="de885-160">Клиент сохраняемого чата отправляет сообщение SIP INVITE в URI SIP сервера сохраняемого чата, полученного на предыдущем шаге.</span><span class="sxs-lookup"><span data-stu-id="de885-160">The Persistent Chat client sends a SIP INVITE message to the SIP URI of the Persistent Chat Server that it obtained in the previous step.</span></span> <span data-ttu-id="de885-161">После последовательного приглашения добавляется 200 ОК и подтверждение, а клиент сохраняемого чата теперь открыл сеанс SIP с конечной точкой сервера сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="de885-161">The INVITE sequence is followed by 200 OK and ACK, and the Persistent Chat client has now opened a SIP session with a Persistent Chat Server endpoint.</span></span> <span data-ttu-id="de885-162">Таким образом, клиент сохраняемого чата обменивается данными с сервером сохраняемого чата, отправляя сообщения SIP INFO, содержащие сообщения или команды чата, которые запрашивают сервер для выполнения действия.</span><span class="sxs-lookup"><span data-stu-id="de885-162">Consequently, the Persistent Chat client communicates with Persistent Chat Server by sending SIP INFO messages that contain either chat messages or commands requesting the server to take an action.</span></span> <span data-ttu-id="de885-163">Все эти сообщения подтверждаются с помощью 200 ОК или 503 Служба недоступна (то есть в случае интенсивной загрузки сервера).</span><span class="sxs-lookup"><span data-stu-id="de885-163">All of these messages are acknowledged with either 200 OK or 503 Service Unavailable (that is, in the event of heavy server load).</span></span> <span data-ttu-id="de885-164">Если клиент получает ответ 503, он повторит попытку отправки сообщения.</span><span class="sxs-lookup"><span data-stu-id="de885-164">If the client receives a 503 response, it will retry the message.</span></span> <span data-ttu-id="de885-165">(Этот пример не включает ответ 503.) Если сервер принимает сообщение или команду и отправляет 200 ОК, он предоставляет ответ клиенту в виде отдельного ИНФОРМАЦИОНного сообщения SIP.</span><span class="sxs-lookup"><span data-stu-id="de885-165">(This example does not include a 503 response.) If the server accepts the message or command and sends 200 OK, it provides a response to the client in the form of a separate SIP INFO message.</span></span> <span data-ttu-id="de885-166">Этот ответ включает ссылку на исходную команду.</span><span class="sxs-lookup"><span data-stu-id="de885-166">This response includes a reference to the originating command.</span></span>

3.  <span data-ttu-id="de885-167">Клиент сохраняемого чата отправляет ИНФОРМАЦИОНное сообщение SIP, содержащее команду XCCOS **жетсерверинфо** .</span><span class="sxs-lookup"><span data-stu-id="de885-167">The Persistent Chat client sends a SIP INFO message that contains the XCCOS **getserverinfo** command.</span></span> <span data-ttu-id="de885-168">Сервер сохраняемого чата отвечает с новым ИНФОРМАЦИОНным сообщением SIP, содержащим сведения о конфигурации службы сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="de885-168">Persistent Chat Server replies with a new SIP INFO message that contains information about the Persistent Chat service configuration.</span></span>

4.  <span data-ttu-id="de885-169">Клиент сохраняемого чата отправляет сообщение SIP INFO, которое **содержит команду XCCOS** .</span><span class="sxs-lookup"><span data-stu-id="de885-169">The Persistent Chat client sends a SIP INFO message that contains the XCCOS **getassociations** command.</span></span> <span data-ttu-id="de885-170">Сервер сохраняемого чата отвечает с новым ИНФОРМАЦИОНным сообщением SIP, содержащим список комнат, участником которых является пользователь.</span><span class="sxs-lookup"><span data-stu-id="de885-170">Persistent Chat Server replies with a new SIP INFO message that contains the list of rooms of which the user is a member.</span></span> <span data-ttu-id="de885-171">Клиент сохраняемого чата повторяет команду, чтобы получить список комнат, в которых пользователь является руководителем.</span><span class="sxs-lookup"><span data-stu-id="de885-171">The Persistent Chat client repeats the command to retrieve the list of rooms of which the user is a manager.</span></span>

5.  <span data-ttu-id="de885-172">Клиент сохраняемого чата получает список отслеживаемых комнат из документа "присутствие", где каждая проданная комната представлена категорией "Румсеттинг".</span><span class="sxs-lookup"><span data-stu-id="de885-172">The Persistent Chat client gets the list of followed rooms from the "presence" document, where each followed room is represented by a "roomSetting" category.</span></span> <span data-ttu-id="de885-173">Присоединение ко всем отслеживаемым комнатам выполняется одним сообщением SIP INFO, содержащим команду XCCOS **bjoin**, содержащую список URI комнат.</span><span class="sxs-lookup"><span data-stu-id="de885-173">All followed rooms are joined by a single SIP INFO message that contains the XCCOS **bjoin** command that contains the list of room URIs.</span></span> <span data-ttu-id="de885-174">Так как список отслеживаемых комнат содержится на сервере, любой клиент на любом компьютере имеет одинаковый список отслеживаемых комнат для URI указанного пользователя.</span><span class="sxs-lookup"><span data-stu-id="de885-174">Because the list of followed rooms is kept on the server, any client on any computer has the same list of followed rooms for the specified user URI.</span></span> <span data-ttu-id="de885-175">Клиент сохраняемого чата также сохраняет список открытых комнат (если этот параметр включен пользователем) в реестре локального компьютера и присоединяется к каждой из этих комнат при входе, отправляя сообщение SIP INFO, которое содержит команду XCCOS **Join** для каждой открытой комнаты.</span><span class="sxs-lookup"><span data-stu-id="de885-175">The Persistent Chat client also keeps the list of opened rooms (if this option is enabled by the user) in the local computer registry, and joins each of these rooms at sign-in by sending a SIP INFO message that contains the XCCOS **join** command for each opened room.</span></span> <span data-ttu-id="de885-176">Так как этот список хранится в реестре, он может различаться на двух клиентах сохраняемого чата, работающих на разных компьютерах.</span><span class="sxs-lookup"><span data-stu-id="de885-176">Because this list is kept in the registry, it can be different on two Persistent Chat clients running on different computers.</span></span>

6.  <span data-ttu-id="de885-177">Для каждой присоединенной комнаты клиент сохраняемого чата отправляет ИНФОРМАЦИОНное сообщение SIP, содержащее команду XCCOS **бкконтекст** .</span><span class="sxs-lookup"><span data-stu-id="de885-177">For each room joined, the Persistent Chat client sends a SIP INFO message that contains the XCCOS **bccontext** command.</span></span> <span data-ttu-id="de885-178">Сервер сохраняемого чата отвечает новым ИНФОРМАЦИОНным сообщением SIP, содержащим Последнее сообщение чата в комнате.</span><span class="sxs-lookup"><span data-stu-id="de885-178">Persistent Chat Server replies with a new SIP INFO message that contains the most recent chat message in the room.</span></span>

7.  <span data-ttu-id="de885-179">Клиент сохраняемого чата отправляет сообщение SIP INFO, содержащее команду XCCOS **жетинв** (то есть получить приглашение), чтобы запросить все новые приглашения на помещение, которые клиент еще не видел.</span><span class="sxs-lookup"><span data-stu-id="de885-179">The Persistent Chat client sends a SIP INFO message that contains a XCCOS **getinv** (that is, get invitation) command to request any new room invitations that the client has not yet seen.</span></span> <span data-ttu-id="de885-180">В отдельном ИНФОРМАЦИОНном сообщении SIP сервер сохраняемого чата возвращает список этих комнат.</span><span class="sxs-lookup"><span data-stu-id="de885-180">In a separate SIP INFO message, Persistent Chat Server returns a list of those rooms.</span></span>

</div>

<div>

## <a name="subscribe-to-a-room-and-post-a-message"></a><span data-ttu-id="de885-181">Подписка на комнату и публикация сообщения</span><span class="sxs-lookup"><span data-stu-id="de885-181">Subscribe to a Room and Post a Message</span></span>

<span data-ttu-id="de885-182">Приведенная ниже схема и пошаговые инструкции описывают типичный сценарий подписки на комнаты и записи сообщений.</span><span class="sxs-lookup"><span data-stu-id="de885-182">The following call flow diagram and steps describe a typical room subscription and message post scenario.</span></span>

<span data-ttu-id="de885-183">**Подписку на помещение клиента сохраняемого чата и отправка сообщений по потребованию**</span><span class="sxs-lookup"><span data-stu-id="de885-183">**Persistent Chat Client Room Subscription and Message Posting Call Flow**</span></span>

<span data-ttu-id="de885-184">![Сценарий подписки на комнаты и записи сообщений.](images/JJ683096.2d3c417e-c91b-42bd-964e-285b72bb2e44(OCS.15).jpg "Сценарий подписки на комнаты и записи сообщений.")</span><span class="sxs-lookup"><span data-stu-id="de885-184">![Room subscription and message post scenario.](images/JJ683096.2d3c417e-c91b-42bd-964e-285b72bb2e44(OCS.15).jpg "Room subscription and message post scenario.")</span></span>

1.  <span data-ttu-id="de885-185">В клиенте сохраняемого чата пользователь user1 щелкает **Присоединение к комнате чата**, щелкает **Поиск**, а затем вводит некоторые условия поиска.</span><span class="sxs-lookup"><span data-stu-id="de885-185">From the Persistent Chat client, User1 clicks **Join a Chat Room**, clicks **Search**, and then enters some search criteria.</span></span> <span data-ttu-id="de885-186">Клиент сохраняемого чата отправляет сообщение SIP INFO, которое содержит команду XCCOS **чансрч** (Поиск комнаты), а также условия поиска.</span><span class="sxs-lookup"><span data-stu-id="de885-186">The Persistent Chat client sends a SIP INFO message that contains the XCCOS **chansrch** (room search) command, along with the search criteria.</span></span> <span data-ttu-id="de885-187">Сервер сохраняемого чата запрашивает внутреннюю базу данных и ответы в новом сообщении SIP INFO, которое содержит список доступных комнат, соответствующих условиям поиска.</span><span class="sxs-lookup"><span data-stu-id="de885-187">Persistent Chat Server queries the back-end database and replies in a new SIP INFO message that contains a list of available rooms that meet the search criteria.</span></span>

2.  <span data-ttu-id="de885-188">Пользователь1 выбирает комнату чата, к которой хочет присоединиться, и щелкает пункт **Подписаться на эту комнату**.</span><span class="sxs-lookup"><span data-stu-id="de885-188">User1 selects the chat room that he or she wants to join, and then clicks **Follow this room**.</span></span> <span data-ttu-id="de885-189">Клиент сохраняемого чата отправляет на сервер сохраняемого чата сообщение информации SIP, содержащее команду **соединения** XCCOS, и идентификатор комнаты чата, выбранная пользователем.</span><span class="sxs-lookup"><span data-stu-id="de885-189">The Persistent Chat client sends Persistent Chat Server a SIP INFO message that contains the XCCOS **join** command and the room ID of the chat room that the user selected.</span></span> <span data-ttu-id="de885-190">Сервер сохраняемого чата отвечает на сообщение SIP INFO, содержащее данные подготовки.</span><span class="sxs-lookup"><span data-stu-id="de885-190">Persistent Chat Server replies with a SIP INFO message that contains the provisioning data.</span></span>

3.  <span data-ttu-id="de885-191">Клиент сохраняемого чата отправляет на сервер сохраняемого чата сообщение сведений SIP, которое содержит команду XCCOS **бкконтекст** (context Chat).</span><span class="sxs-lookup"><span data-stu-id="de885-191">The Persistent Chat client sends Persistent Chat Server a SIP INFO message that contains the XCCOS **bccontext** (backchat context) command.</span></span> <span data-ttu-id="de885-192">Сервер сохраняемого чата извлекает журнал бесед и возвращает его в клиент сохраняемого чата в отдельном ИНФОРМАЦИОНном сообщении SIP.</span><span class="sxs-lookup"><span data-stu-id="de885-192">Persistent Chat Server retrieves the chat history, and returns it to the Persistent Chat client in a separate SIP INFO message.</span></span> <span data-ttu-id="de885-193">На этом этапе пользователь входит в комнату чата, готовый к участию в беседе.</span><span class="sxs-lookup"><span data-stu-id="de885-193">At this point, the user enters the chat room and is ready to participate.</span></span>

4.  <span data-ttu-id="de885-194">Пользователь1 вводит новое сообщение и нажимает кнопку **Отправить**.</span><span class="sxs-lookup"><span data-stu-id="de885-194">User1 enters a new message, and then clicks **Send**.</span></span> <span data-ttu-id="de885-195">Клиент сохраняемого чата отправляет сообщение в комнату чата с помощью команды SIP INFO XCCOS **грпчат** .</span><span class="sxs-lookup"><span data-stu-id="de885-195">The Persistent Chat client posts the message to the chat room in a SIP INFO XCCOS **grpchat** command.</span></span> <span data-ttu-id="de885-196">Сервер сохраняемого чата сохраняет копию этого нового сообщения в фоновой базе данных сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="de885-196">Persistent Chat Server stores a copy of this new message in the Persistent Chat back-end database.</span></span>

5.  <span data-ttu-id="de885-197">Сервер сохраняемого чата отправляет отдельную копию сообщения SIP XCCOS **грпчат** в Пользователь2, который уже ввел комнату чата.</span><span class="sxs-lookup"><span data-stu-id="de885-197">Persistent Chat Server sends a separate copy of the SIP INFO XCCOS **grpchat** message to User2, who has already entered the chat room.</span></span>

</div>

</div>

<div>

## <a name="persistent-chat-compliance-call-flows"></a><span data-ttu-id="de885-198">Потоки вызовов соответствия сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="de885-198">Persistent Chat Compliance Call Flows</span></span>

<span data-ttu-id="de885-199">Сервер сохраняемого чата использует очередь сообщений (также называемую MSMQ) и дополнительную базу данных соответствия (mgccomp) для обработки данных соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="de885-199">Persistent Chat Server uses Message Queuing (also known as MSMQ) and an additional compliance database (mgccomp) to process compliance data.</span></span> <span data-ttu-id="de885-200">Примером обработки событий соответствия является следующая последовательность событий, описывающая обработку события публикации сообщения.</span><span class="sxs-lookup"><span data-stu-id="de885-200">As an example of how compliance events are processed, the following sequence of events describes how a message post event is processed.</span></span>

1.  <span data-ttu-id="de885-201">Пользователь публикует сообщение в комнате.</span><span class="sxs-lookup"><span data-stu-id="de885-201">A user posts a message to a room.</span></span>

2.  <span data-ttu-id="de885-202">Сервер сохраняемого чата размещает сведения, относящиеся к событию в частной очереди Message Queuing.</span><span class="sxs-lookup"><span data-stu-id="de885-202">Persistent Chat Server places information pertaining to the event in a private Message Queuing queue.</span></span>

3.  <span data-ttu-id="de885-203">Сервер соответствия сохраняемого чата читает это событие из очереди и помещает его в базу данных mgccomp для дальнейшей обработки.</span><span class="sxs-lookup"><span data-stu-id="de885-203">Persistent Chat Compliance server reads this event from the queue, and places it into the mgccomp database for processing later.</span></span>

4.  <span data-ttu-id="de885-204">Периодически сервер соответствия сохраняемого чата обрабатывает набор событий в базе данных и отправляет их в адаптер соответствия сохраняемого чата для обработки.</span><span class="sxs-lookup"><span data-stu-id="de885-204">Periodically, the Persistent Chat Compliance server processes a set of events in the database, and sends them to the Persistent Chat Compliance adapter for processing.</span></span>

5.  <span data-ttu-id="de885-205">Если адаптер успешно обрабатывает данные, сервер соответствия сохраняемого чата удаляет события из базы данных mgccomp.</span><span class="sxs-lookup"><span data-stu-id="de885-205">If the adapter successfully processes the data, Persistent Chat Compliance server deletes the events from the mgccomp database.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

