---
title: 'Lync Server 2013: как работает сервер сохраняемого чата'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: How Persistent Chat Server works
ms:assetid: 3d04e9a1-3f0c-458e-bcbe-d27c8c464276
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ683096(v=OCS.15)
ms:contentKeyID: 49684643
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0bf6179e1ce24264c2079b3096fa9bb8c539ca1c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834071"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="how-persistent-chat-server-works-in-lync-server-2013"></a><span data-ttu-id="9f867-102">Как работает сервер сохраняемого чата в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9f867-102">How Persistent Chat Server works in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9f867-103">_**Тема последнего изменения:** 2012-11-21_</span><span class="sxs-lookup"><span data-stu-id="9f867-103">_**Topic Last Modified:** 2012-11-21_</span></span>

<span data-ttu-id="9f867-104">Lync Server 2013, сервер сохраняемого чата позволяет принимать участие в многокомпонентных беседах, которые сохраняются с течением времени.</span><span class="sxs-lookup"><span data-stu-id="9f867-104">Lync Server 2013, Persistent Chat Server enables you to participate in multiparty, topic-based conversations that persist over time.</span></span> <span data-ttu-id="9f867-105">Сервер сохраняемого чата может помочь вашей организации выполнять указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="9f867-105">Persistent Chat Server can help your organization do the following:</span></span>

  - <span data-ttu-id="9f867-106">Улучшена связь между географически распределенными и функциональными группами</span><span class="sxs-lookup"><span data-stu-id="9f867-106">Improve communication between geographically dispersed and cross-functional teams</span></span>

  - <span data-ttu-id="9f867-107">Расширение возможностей для информирования о информации и участия в них</span><span class="sxs-lookup"><span data-stu-id="9f867-107">Broaden information awareness and participation</span></span>

  - <span data-ttu-id="9f867-108">Повышение эффективности общения с помощью расширенной Организации</span><span class="sxs-lookup"><span data-stu-id="9f867-108">Improve communication with your extended organization</span></span>

  - <span data-ttu-id="9f867-109">Уменьшить перегрузку данных</span><span class="sxs-lookup"><span data-stu-id="9f867-109">Reduce information overload</span></span>

  - <span data-ttu-id="9f867-110">Улучшенная поддержка информации</span><span class="sxs-lookup"><span data-stu-id="9f867-110">Improve information awareness</span></span>

  - <span data-ttu-id="9f867-111">Повышайте разброса важных знаний и данных</span><span class="sxs-lookup"><span data-stu-id="9f867-111">Increase dispersion of important knowledge and information</span></span>

<span data-ttu-id="9f867-112">Вы можете развернуть сохраняемый сервер чата как необязательную роль в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9f867-112">You can deploy Persistent Chat Server as an optional role with Lync Server 2013.</span></span> <span data-ttu-id="9f867-113">Службы сохраняемого чата выполняются на выделенном пуле, а пул серверов сохраняемого чата зависит от пула сервера Lync Server для маршрутизации сообщений.</span><span class="sxs-lookup"><span data-stu-id="9f867-113">Persistent Chat services run on a dedicated pool, and a Persistent Chat Server pool depends on a Lync Server pool to route messages to it.</span></span> <span data-ttu-id="9f867-114">Клиенты используют расширяемую связь в чате по протоколу SIP (КСККОС).</span><span class="sxs-lookup"><span data-stu-id="9f867-114">Clients use eXtensible Chat Communication Over SIP (XCCOS).</span></span> <span data-ttu-id="9f867-115">Серверы переднего плана Lync Server настроены так, чтобы перенаправлять трафик в пул сервера сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="9f867-115">The Lync Server Front End Servers are configured to route the traffic to a Persistent Chat Server pool.</span></span>

<div>

## <a name="high-level-architecture"></a><span data-ttu-id="9f867-116">Архитектура высокого уровня</span><span class="sxs-lookup"><span data-stu-id="9f867-116">High-Level Architecture</span></span>

<span data-ttu-id="9f867-117">На приведенных ниже схемах представлены точки зрения серверной архитектуры и служб сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="9f867-117">The following diagrams provide high-level perspectives of the Persistent Chat Server architecture and services.</span></span>

<span data-ttu-id="9f867-118">**Высокоуровневая архитектура сервера сохраняемого чата**</span><span class="sxs-lookup"><span data-stu-id="9f867-118">**Persistent Chat Server High-Level Architecture**</span></span>

<span data-ttu-id="9f867-119">![Серверная архитектура сохраняемого чата.] (images/JJ683096.5db6f36f-4461-4d87-ba77-463b7ffe609b(OCS.15).jpg "Серверная архитектура сохраняемого чата.")</span><span class="sxs-lookup"><span data-stu-id="9f867-119">![Persistent Chat Server architecture.](images/JJ683096.5db6f36f-4461-4d87-ba77-463b7ffe609b(OCS.15).jpg "Persistent Chat Server architecture.")</span></span>

<span data-ttu-id="9f867-120">**Высокоуровневые службы сервера сохраняемого чата**</span><span class="sxs-lookup"><span data-stu-id="9f867-120">**Persistent Chat Server High-Level Services**</span></span>

<span data-ttu-id="9f867-121">![Серверные компоненты сохраняемого чата.] (images/JJ683096.b6d743aa-3a86-4081-aaef-4fe3257db4e7(OCS.15).jpg "Серверные компоненты сохраняемого чата.")</span><span class="sxs-lookup"><span data-stu-id="9f867-121">![Persistent Chat Server components.](images/JJ683096.b6d743aa-3a86-4081-aaef-4fe3257db4e7(OCS.15).jpg "Persistent Chat Server components.")</span></span>

<span data-ttu-id="9f867-122">На серверном сервере сохраняемого чата две службы выполняются на серверах клиентского доступа.</span><span class="sxs-lookup"><span data-stu-id="9f867-122">Two services run on the Persistent Chat Server Front End Servers:</span></span>

  - <span data-ttu-id="9f867-123">Сохраняемый чат (канал)</span><span class="sxs-lookup"><span data-stu-id="9f867-123">Persistent Chat (Channel)</span></span>

  - <span data-ttu-id="9f867-124">О</span><span class="sxs-lookup"><span data-stu-id="9f867-124">Compliance</span></span>

<div>

## <a name="persistent-chat-channel-service"></a><span data-ttu-id="9f867-125">Служба сохраняемого чата (канала)</span><span class="sxs-lookup"><span data-stu-id="9f867-125">Persistent Chat (Channel) Service</span></span>

<span data-ttu-id="9f867-126">Служба сохраняемого чата – это основная служба, ответственная за сохраняемый сервер чата.</span><span class="sxs-lookup"><span data-stu-id="9f867-126">The Persistent Chat (Channel) service is the core service responsible for Persistent Chat Server.</span></span> <span data-ttu-id="9f867-127">Эта служба предоставляет следующие функции:</span><span class="sxs-lookup"><span data-stu-id="9f867-127">This service provides the following functions:</span></span>

  - <span data-ttu-id="9f867-128">Принимает входящие сообщения</span><span class="sxs-lookup"><span data-stu-id="9f867-128">Accepts incoming messages</span></span>

  - <span data-ttu-id="9f867-129">Регистрирует участников, подключенных к комнате сохраняемого чата, и выводит их списки</span><span class="sxs-lookup"><span data-stu-id="9f867-129">Registers and lists online participants within a Persistent Chat room</span></span>

  - <span data-ttu-id="9f867-130">Передает сообщения другим подписчикам канала</span><span class="sxs-lookup"><span data-stu-id="9f867-130">Retransmits messages to other channel subscribers</span></span>

  - <span data-ttu-id="9f867-131">Реализация логики управления каналами, приглашением на комнату чата, поиском и новыми уведомлениями о содержимом</span><span class="sxs-lookup"><span data-stu-id="9f867-131">Implements logic for channel management, chat room invitation, search, and new content notifications</span></span>

<span data-ttu-id="9f867-132">Служба сохраняемого чата (канала) хранит и обращается к содержимому комнаты чата и другим системным метаданным (правилам авторизации и т. д.) с помощью хранилища сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="9f867-132">The Persistent Chat (Channel) service stores and accesses chat room content and other system metadata (authorization rules, and so on) by using the Persistent Chat Store.</span></span> <span data-ttu-id="9f867-133">Эта служба хранит файлы, которые отправляются в комнаты чата в хранилище файлов сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="9f867-133">This service stores files that are uploaded into chat rooms in the Persistent Chat File Store.</span></span>

</div>

<div>

## <a name="compliance-service"></a><span data-ttu-id="9f867-134">Служба соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="9f867-134">Compliance Service</span></span>

<span data-ttu-id="9f867-135">Служба соответствия является опциональным компонентом постоянного сервера чатов и отвечает за архивирование содержимого чата и событий в магазине соответствия требованиям в отношении сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="9f867-135">The Compliance service is an optional component of Persistent Chat Server and is responsible for archiving chat content and events to the Persistent Chat Compliance Store.</span></span> <span data-ttu-id="9f867-136">Если организация придерживается нормативных требований, в соответствии с которыми активность на сервере сохраняемого чата должна архивироваться, можно развернуть дополнительную службу соответствия сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="9f867-136">If your organization has regulations that require Persistent Chat activity to be archived, you can deploy the optional Persistent Chat Compliance service.</span></span> <span data-ttu-id="9f867-137">Служба соответствия устанавливается на каждый сервер сохраняемого чата в пуле сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="9f867-137">The Compliance service is installed on each Persistent Chat Server in a Persistent Chat pool.</span></span> <span data-ttu-id="9f867-138">При настройке сохраняемый сервер чата регистрирует действия пользователей, такие как присоединение к комнатам и выход из них, а также отправка и чтение сообщений.</span><span class="sxs-lookup"><span data-stu-id="9f867-138">When configured, Persistent Chat Server compliance records user activity such as joining and leaving rooms, and posting and reading of messages.</span></span> <span data-ttu-id="9f867-139">Служба соответствия хранит файлы, которые должны быть архивированы в хранилище файлов соответствия требованиям сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="9f867-139">The Compliance service stores files that need to be archived in the Persistent Chat Compliance File Store.</span></span>

</div>

<div>

## <a name="persistent-chat-web-services"></a><span data-ttu-id="9f867-140">Веб-службы сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="9f867-140">Persistent Chat Web Services</span></span>

<span data-ttu-id="9f867-141">На серверах переднего плана Lync Server выполняются две службы, которые зависят от служб IIS и реализованы как веб-компоненты.</span><span class="sxs-lookup"><span data-stu-id="9f867-141">On the Lync Server Front End Servers, two services run that depend on Internet Information Services (IIS), and are implemented as web components:</span></span>

  - <span data-ttu-id="9f867-142">**Веб-службы сохраняемого чата для отправки и скачивания файлов** Ответственен за публикацию и получение файлов из комнат чата.</span><span class="sxs-lookup"><span data-stu-id="9f867-142">**Persistent Chat Web Services for File Upload/Download** Responsible for posting and retrieving files from chat rooms.</span></span>

  - <span data-ttu-id="9f867-143">**Веб-службы сохраняемого чата для управления комнатой чата** Ответственность за предоставление пользователям возможности управлять комнатами чатов, а также создавать комнаты чатов.</span><span class="sxs-lookup"><span data-stu-id="9f867-143">**Persistent Chat Web Services for Chat Room Management** Responsible for providing users the ability to manage their chat rooms, and create new chat rooms.</span></span>

</div>

</div>

<div>

## <a name="how-do-i-start-using-persistent-chat-server"></a><span data-ttu-id="9f867-144">Как начать работу с сохраняемым сервером чата?</span><span class="sxs-lookup"><span data-stu-id="9f867-144">How Do I Start Using Persistent Chat Server?</span></span>

<span data-ttu-id="9f867-145">Сервер сохраняемого чата — это необязательная роль сервера в инфраструктуре Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9f867-145">Persistent Chat Server is an optional server role within the Lync Server 2013 infrastructure.</span></span> <span data-ttu-id="9f867-146">Если вы установили серверную роль "сохраняемый чат", все пользователи, которые были включены администратором с помощью политики, могут использовать для клиента Lync 2013 сохраняемый чат.</span><span class="sxs-lookup"><span data-stu-id="9f867-146">If you install the Persistent Chat Server role, any users who have been enabled through policy by an administrator can use Persistent Chat with the Lync 2013 client.</span></span>

<span data-ttu-id="9f867-147">Подробнее о том, как развернуть сервер сохраняемого чата и разрешить пользователям использовать возможности с помощью политики, можно найти [в разделе Развертывание сервера сохраняемого чата в Lync server 2013](lync-server-2013-deploying-persistent-chat-server.md).</span><span class="sxs-lookup"><span data-stu-id="9f867-147">For details about how to deploy Persistent Chat Server and enable users to leverage the capabilities by policy, see [Deploying Persistent Chat Server in Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md).</span></span>

<span data-ttu-id="9f867-148">Подробнее о том, как настроить параметры конфигурации сервера сохраняемого чата, можно найти [в разделе Развертывание сервера сохраняемого чата в Lync server 2013](lync-server-2013-deploying-persistent-chat-server.md) и [Управление сервером Lync Server 2013, сохраняемый сервер чата](managing-lync-server-2013-persistent-chat-server.md).</span><span class="sxs-lookup"><span data-stu-id="9f867-148">For details about how to configure settings on your Persistent Chat Server deployment, see [Deploying Persistent Chat Server in Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md) and [Managing Lync Server 2013, Persistent Chat Server](managing-lync-server-2013-persistent-chat-server.md).</span></span>

<span data-ttu-id="9f867-149">Дополнительные сведения о том, как включить использование функции сохраняемого чата в клиенте Lync 2013, можно найти в разделе [развертывание сервера сохраняемого чата в Lync server 2013](lync-server-2013-deploying-persistent-chat-server.md) и [Управление приложением Lync Server 2013, сохраняемый сервер чата](managing-lync-server-2013-persistent-chat-server.md).</span><span class="sxs-lookup"><span data-stu-id="9f867-149">For details about how to enable users by policy such that they can leverage Persistent Chat functionality in Lync 2013 client, see [Deploying Persistent Chat Server in Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md) and [Managing Lync Server 2013, Persistent Chat Server](managing-lync-server-2013-persistent-chat-server.md).</span></span>

<span data-ttu-id="9f867-150">Если вы развернули постоянную совместимость чата, ознакомьтесь со статьей [Управление сервером Lync server 2013, сохраняемый сервер чата](managing-lync-server-2013-persistent-chat-server.md) для получения подробных сведений о том, как настроить параметры соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="9f867-150">If you deployed Persistent Chat compliance, see [Managing Lync Server 2013, Persistent Chat Server](managing-lync-server-2013-persistent-chat-server.md) for details about how to configure settings for compliance.</span></span>

</div>

<div>

## <a name="persistent-chat-call-flows"></a><span data-ttu-id="9f867-151">Потоки звонков в сохраняемый чат</span><span class="sxs-lookup"><span data-stu-id="9f867-151">Persistent Chat Call Flows</span></span>

<span data-ttu-id="9f867-152">Клиент сохраняемый чат взаимодействует со службой сохраняемого чата с помощью КСККОС.</span><span class="sxs-lookup"><span data-stu-id="9f867-152">The Persistent Chat client communicates with the Persistent Chat service by using XCCOS.</span></span> <span data-ttu-id="9f867-153">Следующие последовательности описывают процесс входа и типичную подписку на комнату и сценарий публикации сообщения.</span><span class="sxs-lookup"><span data-stu-id="9f867-153">The following sequences describe the sign-in process and a typical room subscription and message post scenario.</span></span>

<div>

## <a name="sign-in"></a><span data-ttu-id="9f867-154">Вход в учетную запись</span><span class="sxs-lookup"><span data-stu-id="9f867-154">Sign-in</span></span>

<span data-ttu-id="9f867-155">На приведенном ниже рисунке показано, как пошаговые инструкции описывают процесс входа.</span><span class="sxs-lookup"><span data-stu-id="9f867-155">The following call flow diagram and steps describe the sign-in process.</span></span>

<span data-ttu-id="9f867-156">**Поток звонков для входа клиента в сохраняемый чат**</span><span class="sxs-lookup"><span data-stu-id="9f867-156">**Persistent Chat Client Sign-in Call Flow**</span></span>

<span data-ttu-id="9f867-157">![Схема потока звонка для сервера сохраняемого чата.] (images/JJ683096.9b3b3c61-caca-42b6-853c-6a09e6ff5c44(OCS.15).jpg "Схема потока звонка для сервера сохраняемого чата.")</span><span class="sxs-lookup"><span data-stu-id="9f867-157">![Persistent Chat Server call flow diagram.](images/JJ683096.9b3b3c61-caca-42b6-853c-6a09e6ff5c44(OCS.15).jpg "Persistent Chat Server call flow diagram.")</span></span>

1.  <span data-ttu-id="9f867-158">Клиент сохраняемого чата сначала отправляет абонентскую подписку, чтобы извлечь из сервера документ для подготовки из стандартного диапазона.</span><span class="sxs-lookup"><span data-stu-id="9f867-158">The Persistent Chat client first sends a SIP SUBSCRIBE to retrieve the in-band provisioning document from the server.</span></span> <span data-ttu-id="9f867-159">Этот документ указывает на то, включена или отключена сохраняемый чат для пользователя, а также список URI SIP для пула серверов сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="9f867-159">This document indicates if Persistent Chat is enabled or disabled for the user and the list of SIP URIs for the Persistent Chat Server pool.</span></span>

2.  <span data-ttu-id="9f867-160">Клиент сохраняемого чата отправляет сообщение INVITE по протоколу SIP URI SIP сервера сохраняемого чата, полученного на предыдущем этапе.</span><span class="sxs-lookup"><span data-stu-id="9f867-160">The Persistent Chat client sends a SIP INVITE message to the SIP URI of the Persistent Chat Server that it obtained in the previous step.</span></span> <span data-ttu-id="9f867-161">После последовательного приглашения на приглашение выдается 200 ОК и подтверждение, а клиент сохраняемый чат теперь открыл сеанс SIP с постоянной конечной точкой сервера чата.</span><span class="sxs-lookup"><span data-stu-id="9f867-161">The INVITE sequence is followed by 200 OK and ACK, and the Persistent Chat client has now opened a SIP session with a Persistent Chat Server endpoint.</span></span> <span data-ttu-id="9f867-162">Таким образом, клиент сохраняемый чат будет взаимодействовать с сохраняемым сервером чата, отправив информационные сообщения SIP, которые содержат сообщения или команды чата, требующие от сервера выполнения действия.</span><span class="sxs-lookup"><span data-stu-id="9f867-162">Consequently, the Persistent Chat client communicates with Persistent Chat Server by sending SIP INFO messages that contain either chat messages or commands requesting the server to take an action.</span></span> <span data-ttu-id="9f867-163">Все эти сообщения подтверждаются с помощью 200 ОК или 503 Служба недоступна (то есть в случае высокой нагрузки на сервер).</span><span class="sxs-lookup"><span data-stu-id="9f867-163">All of these messages are acknowledged with either 200 OK or 503 Service Unavailable (that is, in the event of heavy server load).</span></span> <span data-ttu-id="9f867-164">Если клиент получает ответ 503, он попытается повторить сообщение.</span><span class="sxs-lookup"><span data-stu-id="9f867-164">If the client receives a 503 response, it will retry the message.</span></span> <span data-ttu-id="9f867-165">(Этот пример не включает ответ 503.) Если сервер принимает сообщение или команду и отправляет 200 ОК, он предоставляет ответ клиенту в форме отдельного ИНФОРМАЦИОНного сообщения SIP.</span><span class="sxs-lookup"><span data-stu-id="9f867-165">(This example does not include a 503 response.) If the server accepts the message or command and sends 200 OK, it provides a response to the client in the form of a separate SIP INFO message.</span></span> <span data-ttu-id="9f867-166">Этот ответ включает ссылку на команду "источник".</span><span class="sxs-lookup"><span data-stu-id="9f867-166">This response includes a reference to the originating command.</span></span>

3.  <span data-ttu-id="9f867-167">Клиент сохраняемого чата отправляет ИНФОРМАЦИОНное сообщение SIP, содержащее команду КСККОС **жетсерверинфо** .</span><span class="sxs-lookup"><span data-stu-id="9f867-167">The Persistent Chat client sends a SIP INFO message that contains the XCCOS **getserverinfo** command.</span></span> <span data-ttu-id="9f867-168">Сохраняемый сервер чата отправляет ответы с новым ИНФОРМАЦИОНным сообщением SIP, содержащим сведения о конфигурации службы "сохраняемый чат".</span><span class="sxs-lookup"><span data-stu-id="9f867-168">Persistent Chat Server replies with a new SIP INFO message that contains information about the Persistent Chat service configuration.</span></span>

4.  <span data-ttu-id="9f867-169">Клиент сохраняемого чата отправляет ИНФОРМАЦИОНное сообщение SIP, содержащее команду КСККОС \*\*\*\* -Associations.</span><span class="sxs-lookup"><span data-stu-id="9f867-169">The Persistent Chat client sends a SIP INFO message that contains the XCCOS **getassociations** command.</span></span> <span data-ttu-id="9f867-170">Сохраняемый сервер чатов ответы с новым ИНФОРМАЦИОНным сообщением SIP, содержащим список комнат, участником которых является пользователь.</span><span class="sxs-lookup"><span data-stu-id="9f867-170">Persistent Chat Server replies with a new SIP INFO message that contains the list of rooms of which the user is a member.</span></span> <span data-ttu-id="9f867-171">Клиент сохраняемый чат повторяет команду, чтобы получить список комнат, в которых пользователь является руководителем.</span><span class="sxs-lookup"><span data-stu-id="9f867-171">The Persistent Chat client repeats the command to retrieve the list of rooms of which the user is a manager.</span></span>

5.  <span data-ttu-id="9f867-172">Клиент сохраняемого чата получает список отслеживаемых комнат из документа "присутствие", где каждая отслеживаемая комната представлена категорией "Румсеттинг".</span><span class="sxs-lookup"><span data-stu-id="9f867-172">The Persistent Chat client gets the list of followed rooms from the "presence" document, where each followed room is represented by a "roomSetting" category.</span></span> <span data-ttu-id="9f867-173">Все отслеживаемые комнаты будут соединены одним сообщением SIP INFO, содержащим команду КСККОС **bЧтобы присоединиться** , которая включает список URI комнаты.</span><span class="sxs-lookup"><span data-stu-id="9f867-173">All followed rooms are joined by a single SIP INFO message that contains the XCCOS **bjoin** command that contains the list of room URIs.</span></span> <span data-ttu-id="9f867-174">Поскольку список отслеживаемых комнат хранится на сервере, любой клиент на компьютере имеет один и тот же список отслеживаемых комнат для указанного URI пользователя.</span><span class="sxs-lookup"><span data-stu-id="9f867-174">Because the list of followed rooms is kept on the server, any client on any computer has the same list of followed rooms for the specified user URI.</span></span> <span data-ttu-id="9f867-175">Клиент сохраняемый чат также хранит список открытых комнат (если этот параметр включен пользователем) в реестре локального компьютера и присоединяется к каждой из этих комнат при входе, отправляя ИНФОРМАЦИОНное сообщение SIP, содержащее команду КСККОС **Join** для каждой открытой комнаты. .</span><span class="sxs-lookup"><span data-stu-id="9f867-175">The Persistent Chat client also keeps the list of opened rooms (if this option is enabled by the user) in the local computer registry, and joins each of these rooms at sign-in by sending a SIP INFO message that contains the XCCOS **join** command for each opened room.</span></span> <span data-ttu-id="9f867-176">Так как этот список хранится в реестре, он может различаться на двух клиентах с сохраненным разговором, запущенных на разных компьютерах.</span><span class="sxs-lookup"><span data-stu-id="9f867-176">Because this list is kept in the registry, it can be different on two Persistent Chat clients running on different computers.</span></span>

6.  <span data-ttu-id="9f867-177">Для каждой присоединенной комнаты клиент "сохраняемый чат" отправляет сообщение SIP INFO, содержащее команду КСККОС **бкконтекст** .</span><span class="sxs-lookup"><span data-stu-id="9f867-177">For each room joined, the Persistent Chat client sends a SIP INFO message that contains the XCCOS **bccontext** command.</span></span> <span data-ttu-id="9f867-178">Сохраняемый сервер чата отправляет ответы с новым ИНФОРМАЦИОНным сообщением SIP, содержащим Последнее сообщение чата в комнате.</span><span class="sxs-lookup"><span data-stu-id="9f867-178">Persistent Chat Server replies with a new SIP INFO message that contains the most recent chat message in the room.</span></span>

7.  <span data-ttu-id="9f867-179">Клиент сохраняемого чата отправляет ИНФОРМАЦИОНное сообщение SIP, содержащее команду КСККОС **жетинв** (то есть приглашение), чтобы запросить все новые приглашения на конференцию, которые еще не видели клиент.</span><span class="sxs-lookup"><span data-stu-id="9f867-179">The Persistent Chat client sends a SIP INFO message that contains a XCCOS **getinv** (that is, get invitation) command to request any new room invitations that the client has not yet seen.</span></span> <span data-ttu-id="9f867-180">В отдельном ИНФОРМАЦИОНном сообщении SIP сервер сохраняемого чата возвращает список этих комнат.</span><span class="sxs-lookup"><span data-stu-id="9f867-180">In a separate SIP INFO message, Persistent Chat Server returns a list of those rooms.</span></span>

</div>

<div>

## <a name="subscribe-to-a-room-and-post-a-message"></a><span data-ttu-id="9f867-181">Подписка на комнату и публикация сообщения</span><span class="sxs-lookup"><span data-stu-id="9f867-181">Subscribe to a Room and Post a Message</span></span>

<span data-ttu-id="9f867-182">На приведенном ниже рисунке приводится описание типичной подписки на комнату и сценария записи сообщения.</span><span class="sxs-lookup"><span data-stu-id="9f867-182">The following call flow diagram and steps describe a typical room subscription and message post scenario.</span></span>

<span data-ttu-id="9f867-183">**Подписку на клиентскую комнату для сохраняемого чата и отправка сообщения в потоке звонков**</span><span class="sxs-lookup"><span data-stu-id="9f867-183">**Persistent Chat Client Room Subscription and Message Posting Call Flow**</span></span>

<span data-ttu-id="9f867-184">![Подписка на комнату и сценарий публикации сообщения.] (images/JJ683096.2d3c417e-c91b-42bd-964e-285b72bb2e44(OCS.15).jpg "Подписка на комнату и сценарий публикации сообщения.")</span><span class="sxs-lookup"><span data-stu-id="9f867-184">![Room subscription and message post scenario.](images/JJ683096.2d3c417e-c91b-42bd-964e-285b72bb2e44(OCS.15).jpg "Room subscription and message post scenario.")</span></span>

1.  <span data-ttu-id="9f867-185">Из клиента для сохраняемого чата пользователь user1 щелкает присоединиться **к комнате чата**, нажмет кнопку **Поиск**, а затем вводит некоторые условия поиска.</span><span class="sxs-lookup"><span data-stu-id="9f867-185">From the Persistent Chat client, User1 clicks **Join a Chat Room**, clicks **Search**, and then enters some search criteria.</span></span> <span data-ttu-id="9f867-186">Клиент сохраняемого чата отправляет ИНФОРМАЦИОНное сообщение SIP, содержащее команду КСККОС **чансрч** (Поиск комнаты), а также условия поиска.</span><span class="sxs-lookup"><span data-stu-id="9f867-186">The Persistent Chat client sends a SIP INFO message that contains the XCCOS **chansrch** (room search) command, along with the search criteria.</span></span> <span data-ttu-id="9f867-187">Сервер сохраняемого чата отправляет запросы на заполненную базу данных и ответы в новом сообщении SIP INFO, содержащем список доступных комнат, отвечающих условиям поиска.</span><span class="sxs-lookup"><span data-stu-id="9f867-187">Persistent Chat Server queries the back-end database and replies in a new SIP INFO message that contains a list of available rooms that meet the search criteria.</span></span>

2.  <span data-ttu-id="9f867-188">Пользователь1 выберет комнату чата, к которой ей нужно присоединиться, и щелкаем подписаться на **эту комнату**.</span><span class="sxs-lookup"><span data-stu-id="9f867-188">User1 selects the chat room that he or she wants to join, and then clicks **Follow this room**.</span></span> <span data-ttu-id="9f867-189">Клиент сохраняемого чата отправляет на сервер сохраняемого чата сообщение о SIP, содержащее команду "присоединиться **к** ксккос", и код комнаты комнаты чата, в которой выбран пользователь.</span><span class="sxs-lookup"><span data-stu-id="9f867-189">The Persistent Chat client sends Persistent Chat Server a SIP INFO message that contains the XCCOS **join** command and the room ID of the chat room that the user selected.</span></span> <span data-ttu-id="9f867-190">Сохраняемый сервер чата отвечает на сообщение информации SIP, содержащее данные подготовки.</span><span class="sxs-lookup"><span data-stu-id="9f867-190">Persistent Chat Server replies with a SIP INFO message that contains the provisioning data.</span></span>

3.  <span data-ttu-id="9f867-191">Клиент сохраняемого чата отправляет на сервер сохраненного чата сообщение о SIP, содержащее команду КСККОС **бкконтекст** (контекст чата).</span><span class="sxs-lookup"><span data-stu-id="9f867-191">The Persistent Chat client sends Persistent Chat Server a SIP INFO message that contains the XCCOS **bccontext** (backchat context) command.</span></span> <span data-ttu-id="9f867-192">Сервер сохраняемого чата извлекает историю чата и возвращает его в сохраняемый клиент чата в отдельном сообщении SIP INFO.</span><span class="sxs-lookup"><span data-stu-id="9f867-192">Persistent Chat Server retrieves the chat history, and returns it to the Persistent Chat client in a separate SIP INFO message.</span></span> <span data-ttu-id="9f867-193">На этом этапе пользователь вводит комнату чата и готова принять участие.</span><span class="sxs-lookup"><span data-stu-id="9f867-193">At this point, the user enters the chat room and is ready to participate.</span></span>

4.  <span data-ttu-id="9f867-194">Пользователь1 вводит новое сообщение, а затем нажимает кнопку " **Отправить**".</span><span class="sxs-lookup"><span data-stu-id="9f867-194">User1 enters a new message, and then clicks **Send**.</span></span> <span data-ttu-id="9f867-195">Клиент сохраняемый чат отправляет сообщение в комнату чата с помощью команды SIP INFO КСККОС **грпчат** .</span><span class="sxs-lookup"><span data-stu-id="9f867-195">The Persistent Chat client posts the message to the chat room in a SIP INFO XCCOS **grpchat** command.</span></span> <span data-ttu-id="9f867-196">Сохраняемый сервер чата сохраняет копию этого сообщения в базе данных сохраняемого обратного чата.</span><span class="sxs-lookup"><span data-stu-id="9f867-196">Persistent Chat Server stores a copy of this new message in the Persistent Chat back-end database.</span></span>

5.  <span data-ttu-id="9f867-197">Сервер сохраняемого чата отправляет отдельную копию сообщения SIP КСККОС **грпчат** в Пользователь2, который уже ввел в комнату чата.</span><span class="sxs-lookup"><span data-stu-id="9f867-197">Persistent Chat Server sends a separate copy of the SIP INFO XCCOS **grpchat** message to User2, who has already entered the chat room.</span></span>

</div>

</div>

<div>

## <a name="persistent-chat-compliance-call-flows"></a><span data-ttu-id="9f867-198">Потоки звонков для соблюдения требований в отношении сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="9f867-198">Persistent Chat Compliance Call Flows</span></span>

<span data-ttu-id="9f867-199">Сервер сохраняемого чата использует очередь сообщений (также называемую MSMQ) и дополнительную базу данных соответствия (мгккомп) для обработки данных соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="9f867-199">Persistent Chat Server uses Message Queuing (also known as MSMQ) and an additional compliance database (mgccomp) to process compliance data.</span></span> <span data-ttu-id="9f867-200">В качестве примера обработки событий соответствия в приведенной ниже последовательности событий описывается обработка события POST сообщения.</span><span class="sxs-lookup"><span data-stu-id="9f867-200">As an example of how compliance events are processed, the following sequence of events describes how a message post event is processed.</span></span>

1.  <span data-ttu-id="9f867-201">Пользователь отправляет сообщение в комнату.</span><span class="sxs-lookup"><span data-stu-id="9f867-201">A user posts a message to a room.</span></span>

2.  <span data-ttu-id="9f867-202">Сервер сохраняемого чата помещает сведения о событии в частную очередь Message Queuing.</span><span class="sxs-lookup"><span data-stu-id="9f867-202">Persistent Chat Server places information pertaining to the event in a private Message Queuing queue.</span></span>

3.  <span data-ttu-id="9f867-203">Сохраняемый чат сервер для обеспечения соответствия требованиям читает это событие из очереди и помещает его в базу данных мгккомп для дальнейшей обработки.</span><span class="sxs-lookup"><span data-stu-id="9f867-203">Persistent Chat Compliance server reads this event from the queue, and places it into the mgccomp database for processing later.</span></span>

4.  <span data-ttu-id="9f867-204">Периодически сервер соответствия требованиям к чат обрабатывает набор событий в базе данных и отправляет их на постоянный адаптер соответствия чатов для обработки.</span><span class="sxs-lookup"><span data-stu-id="9f867-204">Periodically, the Persistent Chat Compliance server processes a set of events in the database, and sends them to the Persistent Chat Compliance adapter for processing.</span></span>

5.  <span data-ttu-id="9f867-205">Если адаптер успешно обрабатывает данные, сервер соответствия требованиям сохраняемый чат удаляет события из базы данных мгккомп.</span><span class="sxs-lookup"><span data-stu-id="9f867-205">If the adapter successfully processes the data, Persistent Chat Compliance server deletes the events from the mgccomp database.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

