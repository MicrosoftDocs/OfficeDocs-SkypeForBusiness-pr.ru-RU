---
title: Обзор функций (средство планирования)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 4/6/2016
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.plan.FeatureOverview
- ms.lync.plan.FeatureOverview
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 44783b37-c87f-41f2-9de1-39176f1856ab
description: Средство планирования Skype для бизнеса Server 2015
ms.openlocfilehash: 7f408de792672445c727b107a7e4050ef1502259
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49800289"
---
# <a name="feature-overview-planning-tool"></a><span data-ttu-id="b7fad-103">Обзор функций (средство планирования)</span><span class="sxs-lookup"><span data-stu-id="b7fad-103">Feature Overview (Planning Tool)</span></span>
 
<span data-ttu-id="b7fad-104">Средство планирования Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="b7fad-104">Skype for Business Server 2015 Planning Tool</span></span>
  
<span data-ttu-id="b7fad-105">Для разработки **развертывания** Skype для бизнеса Server можно использовать страницу "Центральные сайты" средства планирования.</span><span class="sxs-lookup"><span data-stu-id="b7fad-105">You can use the **Central Sites** page of the Planning Tool to design the Skype for Business Server deployment.</span></span> <span data-ttu-id="b7fad-106">Можно создать два централизованного или распределенного развертывания.</span><span class="sxs-lookup"><span data-stu-id="b7fad-106">You can create two either a centralized or distributed deployment.</span></span> <span data-ttu-id="b7fad-107">Централизованное развертывание имеет только один центральный сайт, на котором размещены все пользователи Skype для бизнеса в организации.</span><span class="sxs-lookup"><span data-stu-id="b7fad-107">A centralized deployment only has one central site, which homes all Skype for Business users in your organization.</span></span> <span data-ttu-id="b7fad-108">В распределенной развертывании имеется несколько центральных сайтов.</span><span class="sxs-lookup"><span data-stu-id="b7fad-108">A distributed deployment has more than one central site.</span></span> <span data-ttu-id="b7fad-109">При развертывании Skype для бизнеса Server на нескольких центральных сайтах в средстве планирования будет вводиться количество пользователей на каждом центральном сайте.</span><span class="sxs-lookup"><span data-stu-id="b7fad-109">If you deploy Skype for Business Server at multiple central sites, then you will enter the number of users at each central site in the Planning Tool.</span></span>
  
<span data-ttu-id="b7fad-110">Чтобы завершить определение центрального сайта, сначала необходимо предоставить следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="b7fad-110">To complete the definition of the central site, you first need to provide the following information:</span></span>
  
- <span data-ttu-id="b7fad-111">**Имя сайта** Введите имя центрального сайта.</span><span class="sxs-lookup"><span data-stu-id="b7fad-111">**Site Name** Enter the name of the Central Site.</span></span>
    
- <span data-ttu-id="b7fad-112">**Количество пользователей** Введите количество пользователей, в том числе пользователей на сайтах филиалов, которые находятся на центральном сайте.</span><span class="sxs-lookup"><span data-stu-id="b7fad-112">**Number of Users** Enter the number of users, including users at branch sites who are homed into the central site.</span></span>
    
- <span data-ttu-id="b7fad-113">**Пользователи, для дома в облаке** Введите количество пользователей, которые находятся на центральном сайте в Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="b7fad-113">**Cloud Homed Users** Enter the number of users that are homed into the central site from Skype for Business Online.</span></span>
    
## <a name="ui-elements"></a><span data-ttu-id="b7fad-114">Элементы пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="b7fad-114">UI Elements</span></span>

<span data-ttu-id="b7fad-115">Оставшиеся элементы были либо заполнены ответами на вопросы, представленные в мастере начала работы, либо, если вы пропустили мастер, автоматически заполнялись средством планирования. </span><span class="sxs-lookup"><span data-stu-id="b7fad-115">The remaining elements have either been populated with the answers you provided to the questions presented in the **Get Started** wizard, or, if you skipped the wizard, automatically populated by the planning tool.</span></span>
  
### <a name="online-collaboration"></a><span data-ttu-id="b7fad-116">Совместная работа по сети</span><span class="sxs-lookup"><span data-stu-id="b7fad-116">Online Collaboration</span></span>

 <span data-ttu-id="b7fad-117">**Совместная работа по** сети содержит следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="b7fad-117">**Online Collaboration** contains the following options:</span></span>
  
- <span data-ttu-id="b7fad-118">**IM and Presence**</span><span class="sxs-lookup"><span data-stu-id="b7fad-118">**IM and Presence**</span></span>
    
    <span data-ttu-id="b7fad-119">Обмен мгновенными сообщениями позволяет пользователям взаимодействовать друг с другом в режиме реального времени на своих компьютерах с помощью текстовых сообщений.</span><span class="sxs-lookup"><span data-stu-id="b7fad-119">Instant Messaging (IM) enables users to communicate with each other in real time on their computers using text-based messages.</span></span> <span data-ttu-id="b7fad-120">Поддерживаются как двухсторонние, так и многосторонние сеансы обмена мгновенными сообщениями.</span><span class="sxs-lookup"><span data-stu-id="b7fad-120">Both two-party and multiparty IM sessions are supported.</span></span> <span data-ttu-id="b7fad-121">Сведения о присутствии предоставляют пользователям сведения о состоянии других пользователей в сети.</span><span class="sxs-lookup"><span data-stu-id="b7fad-121">Presence provides information to users about the status of others on the network.</span></span> <span data-ttu-id="b7fad-122">Состояние присутствия пользователя предоставляет сведения, которые помогают другим пользователям определить, находится ли пользователь в сети и как лучше всего связаться с пользователем.</span><span class="sxs-lookup"><span data-stu-id="b7fad-122">A user's presence status provides information to help others determine whether the user is online and how to best contact the user.</span></span> <span data-ttu-id="b7fad-123">Например, с пользователем, который находится на собрании, лучше всего связаться по электронной почте.</span><span class="sxs-lookup"><span data-stu-id="b7fad-123">For example, a user who is in a meeting is best contacted by email.</span></span>
    
- <span data-ttu-id="b7fad-124">**Аудио- и видеоконференции**</span><span class="sxs-lookup"><span data-stu-id="b7fad-124">**Audio and Video Conferencing**</span></span>
    
    <span data-ttu-id="b7fad-125">Аудио- и видеоконференции обеспечивают аудио- и видеоконференции в режиме реального времени.</span><span class="sxs-lookup"><span data-stu-id="b7fad-125">Audio/Video (A/V) conferencing enables real-time audio and video conferences.</span></span>
    
- <span data-ttu-id="b7fad-126">**Конференц-связь с телефонным подключением**</span><span class="sxs-lookup"><span data-stu-id="b7fad-126">**Dial-in Conferencing**</span></span>
    
    <span data-ttu-id="b7fad-127">С помощью телефонной связи пользователи могут присоединяться к видео- и видеоконференциям с телефона в STN.</span><span class="sxs-lookup"><span data-stu-id="b7fad-127">Dial-in conferencing enables users to join an A/V from a telephone on the PSTN.</span></span> <span data-ttu-id="b7fad-128">Для работы с видеоконференцией необходимо развернуть приложения помощника по конференцию и службу извещающих сообщений.</span><span class="sxs-lookup"><span data-stu-id="b7fad-128">Dial-in conferencing requires that you deploy the Conferencing Attendant and Conferencing Announcement Service applications.</span></span>
    
- <span data-ttu-id="b7fad-129">**Веб-конференции**</span><span class="sxs-lookup"><span data-stu-id="b7fad-129">**Web Conferencing**</span></span>
    
    <span data-ttu-id="b7fad-130">Веб-конференции позволяют корпоративным пользователям внутри и за пределами брандмауэра создавать конференции в режиме реального времени, которые находятся на внутренних серверах, и присоединяться к ним.</span><span class="sxs-lookup"><span data-stu-id="b7fad-130">Web conferencing enables enterprise users inside and outside of the firewall to create and join real-time conferences that are hosted on your internal servers.</span></span>
    
- <span data-ttu-id="b7fad-131">**Сохраняемый чат**</span><span class="sxs-lookup"><span data-stu-id="b7fad-131">**Persistent Chat**</span></span>
    
    <span data-ttu-id="b7fad-132">Сохраняемая беседа позволяет нескольким пользователям участвовать в беседах, в которых они могут размещать и получать доступ к контенту по определенным темам, включая текст, ссылки и файлы.</span><span class="sxs-lookup"><span data-stu-id="b7fad-132">Persistent Chat enables multiple users to participate in conversations in which they post and access content about specific topics, including text, links, and files.</span></span> <span data-ttu-id="b7fad-133">Хотя пользователи в течение сеанса могут взаимодействовать в режиме реального времени, контент каждого сеанса является постоянным, и доступен после окончания сеанса.</span><span class="sxs-lookup"><span data-stu-id="b7fad-133">Although users can communicate in real time during a session, the content of each session is persistent, which means it continues to be available after a session ends.</span></span>
    
### <a name="users"></a><span data-ttu-id="b7fad-134">Пользователи</span><span class="sxs-lookup"><span data-stu-id="b7fad-134">Users</span></span>

 <span data-ttu-id="b7fad-135">**Пользователи** содержат следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="b7fad-135">**Users** contains the following options:</span></span>
  
- <span data-ttu-id="b7fad-136">**Внутренняя организация**</span><span class="sxs-lookup"><span data-stu-id="b7fad-136">**Internal organization**</span></span>
    
- <span data-ttu-id="b7fad-137">**Федерация с другими организациями**</span><span class="sxs-lookup"><span data-stu-id="b7fad-137">**Federation with other organizations**</span></span>
    
- <span data-ttu-id="b7fad-138">**Федерация с предыдущими версиями**</span><span class="sxs-lookup"><span data-stu-id="b7fad-138">**Federation with previous versions**</span></span>
    
- <span data-ttu-id="b7fad-139">**Федерация с общедоступными поставщиками услуг im** Позволяет пользователям организации устанавливать связь с общедоступными поставщиками услуг обмена мгновенными сообщениями, такими как MSN, Yahoo!и AOL.</span><span class="sxs-lookup"><span data-stu-id="b7fad-139">**Federation with public IM services providers** Allows users in your organization to establish communication with public instant messaging service providers such as MSN, Yahoo!, and AOL.</span></span> <span data-ttu-id="b7fad-140">Для установления федерации с общедоступными сетями обмена мгновенными сообщениями необходима отдельная лицензия.</span><span class="sxs-lookup"><span data-stu-id="b7fad-140">A separate license is required to establish federation with public instant messaging networks.</span></span>
    
- <span data-ttu-id="b7fad-141">**Федерация с поставщиком услуг на основе XMPP**</span><span class="sxs-lookup"><span data-stu-id="b7fad-141">**Federation with XMPP-based service provider**</span></span>
    
    <span data-ttu-id="b7fad-142">В Skype для бизнеса Server 2015 реализован полностью интегрированный прокси-сервер XMPP (развернутый на edge-серверах) и шлюз XMPP, развернутый на серверах переднего сервера.</span><span class="sxs-lookup"><span data-stu-id="b7fad-142">Skype for Business Server 2015 introduces a fully integrated XMPP proxy (deployed on the Edge Servers) and an XMPP gateway deployed on your Front End Servers.</span></span> <span data-ttu-id="b7fad-143">Добавление и настройка прокси-сервера XMPP и шлюза XMPP позволяют пользователям Skype для бизнеса Server 2015 добавлять контакты от партнеров на основе XMPP для обмена мгновенными сообщениями и присутствия.</span><span class="sxs-lookup"><span data-stu-id="b7fad-143">You can deploy Adding and configuring the XMPP proxy and XMPP gateway will allow your Skype for Business Server 2015 users to add contacts from XMPP-based partners for instant messaging (IM) and presence.</span></span>
    
- <span data-ttu-id="b7fad-144">**Мобильность**</span><span class="sxs-lookup"><span data-stu-id="b7fad-144">**Mobility**</span></span>
    
    <span data-ttu-id="b7fad-145">При развертывании службы Skype для бизнеса Server 2015 Mobility Service пользователи могут использовать поддерживаемые мобильные устройства Apple iOS, Android, Windows Phone или Nokia для выполнения таких действий, как отправка и получение мгновенных сообщений, просмотр контактов и просмотр присутствия.</span><span class="sxs-lookup"><span data-stu-id="b7fad-145">When you deploy the Skype for Business Server 2015 Mobility Service, users can use supported Apple iOS, Android, Windows Phone, or Nokia mobile devices to perform such activities as sending and receiving instant messages, viewing contacts, and viewing presence.</span></span>
    
- <span data-ttu-id="b7fad-146">**Почтовый ящик W15 Exchange**</span><span class="sxs-lookup"><span data-stu-id="b7fad-146">**W15 Exchange mailbox**</span></span>
    
    <span data-ttu-id="b7fad-147">Skype для бизнеса Server 2015 позволяет хранить сообщения голосовой почты в единой системы обмена сообщениями Exchange; эти сообщения голосовой почты будут отображаться в почтовых ящиках пользователей в качестве сообщений электронной почты.</span><span class="sxs-lookup"><span data-stu-id="b7fad-147">Skype for Business Server 2015 enables you to have voicemail messages stored in Exchange Unified Messaging (UM); those voicemail messages will then appear as email messages in your users' Inboxes.</span></span>
    
### <a name="voice"></a><span data-ttu-id="b7fad-148">Голос</span><span class="sxs-lookup"><span data-stu-id="b7fad-148">Voice</span></span>

 <span data-ttu-id="b7fad-149">**Голосовая** почта содержит следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="b7fad-149">**Voice** contains the following options:</span></span>
  
- <span data-ttu-id="b7fad-150">**Корпоративная голосовая связь**</span><span class="sxs-lookup"><span data-stu-id="b7fad-150">**Enterprise Voice**</span></span>
    
    <span data-ttu-id="b7fad-151">Корпоративная голосовая почта — это программное решение VoIP компании Microsft.</span><span class="sxs-lookup"><span data-stu-id="b7fad-151">Enterprise voice is Microsft's software-powered VoIP solution.</span></span> <span data-ttu-id="b7fad-152">Корпоративная голосовая почта позволяет пользователям использовать Skype для бизнеса для телефонного звонка со своего компьютера.</span><span class="sxs-lookup"><span data-stu-id="b7fad-152">Enterprise voice enables users to use Skype for Business to place a phone call from their computer.</span></span>
    
- <span data-ttu-id="b7fad-153">**Единая система обмена сообщениями Exchange**</span><span class="sxs-lookup"><span data-stu-id="b7fad-153">**Exchange Unified Messaging**</span></span>
    
    <span data-ttu-id="b7fad-154">Единая система обмена сообщениями Exchange объединяет голосовую почту и электронную почту в единую инфраструктуру обмена сообщениями.</span><span class="sxs-lookup"><span data-stu-id="b7fad-154">Exchange Unified Messaging (UM) combines voice mail and email into a single messaging infrastructure.</span></span> <span data-ttu-id="b7fad-155">Skype для бизнеса Server 2015 использует exchange UM для предоставления автоотвещений, абонентского доступа, уведомлений о вызовах и автослужб.</span><span class="sxs-lookup"><span data-stu-id="b7fad-155">Skype for Business Server 2015 uses Exchange UM to provide call answering, subscriber access, call notification, and auto attendant services.</span></span> <span data-ttu-id="b7fad-156">Если вы используете эти службы, вам потребуется интегрировать exchange UM и Skype для бизнеса Server в общую топологию Active Directory.</span><span class="sxs-lookup"><span data-stu-id="b7fad-156">If you use these services, you will need to integrate Exchange UM and Skype for Business Server in a shared Active Directory topology.</span></span>
    
### <a name="additional-deployment-options"></a><span data-ttu-id="b7fad-157">Дополнительные параметры развертывания</span><span class="sxs-lookup"><span data-stu-id="b7fad-157">Additional Deployment Options</span></span>

 <span data-ttu-id="b7fad-158">**Дополнительные параметры** развертывания содержат следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="b7fad-158">**Additional Deployment Options** contains the following options:</span></span>
  
- <span data-ttu-id="b7fad-159">**Высокая доступность**</span><span class="sxs-lookup"><span data-stu-id="b7fad-159">**High Availability**</span></span>
    
    <span data-ttu-id="b7fad-160">Высокая доступность обеспечивает поддержку от сбойов серверов в режиме ожидания.</span><span class="sxs-lookup"><span data-stu-id="b7fad-160">High availability enables standby servers for failover support.</span></span>
    
- <span data-ttu-id="b7fad-161">**Аварийное восстановление**</span><span class="sxs-lookup"><span data-stu-id="b7fad-161">**Disaster Recovery**</span></span>
    
    <span data-ttu-id="b7fad-162">Меры аварийного восстановления позволяют спарить пулы переднего входа, расположенные в двух центрах обработки данных.</span><span class="sxs-lookup"><span data-stu-id="b7fad-162">Disaster recovery measures enable you to pair Front End pools located in two datacenters.</span></span>
    
- <span data-ttu-id="b7fad-163">**Мониторинг**</span><span class="sxs-lookup"><span data-stu-id="b7fad-163">**Monitoring**</span></span>
    
    <span data-ttu-id="b7fad-164">При мониторинге записываются записи о вызовах, связанные с сеансами связи.</span><span class="sxs-lookup"><span data-stu-id="b7fad-164">Monitoring captures call detail records related to communication sessions.</span></span> <span data-ttu-id="b7fad-165">Кроме того, он собирает метрики из аудио- и видеосвязи в конечных точках участников.</span><span class="sxs-lookup"><span data-stu-id="b7fad-165">It also collects metrics from audio and video sessions at the participant endpoints.</span></span> <span data-ttu-id="b7fad-166">Сервер мониторинга предоставляет статистику использования, тенденции и статистику качества мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="b7fad-166">Monitoring Server provides usage statistics, trends, and media quality statistics.</span></span>
    
- <span data-ttu-id="b7fad-167">**Архивация**</span><span class="sxs-lookup"><span data-stu-id="b7fad-167">**Archiving**</span></span>
    
    <span data-ttu-id="b7fad-168">В архиве хранится обмен мгновенными сообщениями и конференции.</span><span class="sxs-lookup"><span data-stu-id="b7fad-168">Archiving stores instant messaging conversations and conferences.</span></span>
    
- <span data-ttu-id="b7fad-169">**Интеграция архивации Exchange**</span><span class="sxs-lookup"><span data-stu-id="b7fad-169">**Exchange Archiving Integration**</span></span>
    
    <span data-ttu-id="b7fad-170">Если у вас есть пользователи, которые находятся в Exchange 2013 и их почтовые ящики были поставлены на удержание In-Place, можно выбрать вариант интеграции хранилища Skype для бизнеса Server 2015 с хранилищем Exchange.</span><span class="sxs-lookup"><span data-stu-id="b7fad-170">If you have users who are homed on Exchange 2013 and their mailboxes have been put on In-Place Hold, you can select the option to integrate Skype for Business Server 2015 storage with Exchange storage.</span></span>
    
- <span data-ttu-id="b7fad-171">**IPv4**</span><span class="sxs-lookup"><span data-stu-id="b7fad-171">**IPv4**</span></span>
    
    <span data-ttu-id="b7fad-172">Адреса IPv4 — 32-разрядные адреса, которые позволяют компьютеру осуществлять взаимодействие через Интернет.</span><span class="sxs-lookup"><span data-stu-id="b7fad-172">IPv4 addresses are 32-bit addresses that allow a computer to communicate over the Internet.</span></span> <span data-ttu-id="b7fad-173">Из-за увеличения числа устройств по всему миру доступные IPv4-адреса стали недоступны. По этой причине многие новые устройства переходят на использование IPv6-адресов.</span><span class="sxs-lookup"><span data-stu-id="b7fad-173">Due to the increasing number of devices worldwide, the available IPv4 addresses have run out. Because of this, many new devices are moving to using IPv6 addresses.</span></span>
    
- <span data-ttu-id="b7fad-174">**IPv6**</span><span class="sxs-lookup"><span data-stu-id="b7fad-174">**IPv6**</span></span>
    
    <span data-ttu-id="b7fad-175">Адреса IPv6 выполняют ту же задачу, что и адреса IPv4 (с некоторыми дополнительными возможностями), но вместо использования 32 бит в адресах IPv6 используется 128 бит.</span><span class="sxs-lookup"><span data-stu-id="b7fad-175">IPv6 addresses perform the same function as IPv4 addresses (with some additional features), but instead of using only 32-bits, IPv6 addresses use 128-bits.</span></span> <span data-ttu-id="b7fad-176">Это не только предоставляет новый набор адресов, но существенно увеличивает их количество.</span><span class="sxs-lookup"><span data-stu-id="b7fad-176">This provides not only a new set of addresses, but also a much larger number of them.</span></span>
    
- <span data-ttu-id="b7fad-177">**Веб-служба обновления устройств**</span><span class="sxs-lookup"><span data-stu-id="b7fad-177">**Device Update Web service**</span></span>
    
    <span data-ttu-id="b7fad-178">Веб-служба обновления устройств предоставляет автоматический способ обновления всех устройств, таких как Skype для бизнеса для Windows Phone, развернутых за пределами организации.</span><span class="sxs-lookup"><span data-stu-id="b7fad-178">The Device Update Web service provides an automated way to update all devices, such as Skype for Business for Windows Phone, that are deployed outside of your organization.</span></span>
    
### <a name="server-applications"></a><span data-ttu-id="b7fad-179">Серверные приложения</span><span class="sxs-lookup"><span data-stu-id="b7fad-179">Server Applications</span></span>

 <span data-ttu-id="b7fad-180">**Серверные приложения** содержат следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="b7fad-180">**Server Applications** contains the following options:</span></span>
  
- <span data-ttu-id="b7fad-181">**Группа ответа**</span><span class="sxs-lookup"><span data-stu-id="b7fad-181">**Response Group**</span></span>
    
    <span data-ttu-id="b7fad-182">Приложение группы ответа автоматически отвечает на вызовы и распределяет их среди доступных агентов поддержки.</span><span class="sxs-lookup"><span data-stu-id="b7fad-182">The Response Group application automatically answers and distributes calls to an available helpdesk agent.</span></span>
    
- <span data-ttu-id="b7fad-183">**Объявление**</span><span class="sxs-lookup"><span data-stu-id="b7fad-183">**Announcement**</span></span>
    
    <span data-ttu-id="b7fad-184">Если планируется развертывание Корпоративная голосовая связь, может потребоваться настроить обработку телефонных звонков, если набираемый номер действителен, но не назначен общему пользовательскому региону.</span><span class="sxs-lookup"><span data-stu-id="b7fad-184">If you plan to deploy Enterprise Voice, you might want to be able to configure how phone calls are handled if the dialed number is valid but not assigned to a user common area.</span></span> <span data-ttu-id="b7fad-185">Администраторы могут настроить службу объявлений таким образом, чтобы эти вызовы перенапрались в заранее указанный пункт назначения (номер телефона или URI SIP) или воспроизведения звукового сообщения или и того, и другое.</span><span class="sxs-lookup"><span data-stu-id="b7fad-185">Administrators can configure Announcement Service so that these calls transfer to a predetermined destination (phone number or SIP URI) or play an audio announcement or both.</span></span> <span data-ttu-id="b7fad-186">Использование службы извещение позволяет избежать ситуаций, когда звоня извещение и слышит сигнал занятости или клиент SIP получает сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="b7fad-186">Using Announcement Service avoids the situation in which a caller misdials and hears a busy tone or the SIP client receives an error message.</span></span> <span data-ttu-id="b7fad-187">Функциональность службы объявлений является типичной функцией УАПС.</span><span class="sxs-lookup"><span data-stu-id="b7fad-187">Announcement Service functionality is a typical PBX feature.</span></span> 
    
- <span data-ttu-id="b7fad-188">**Приостановка звонков**</span><span class="sxs-lookup"><span data-stu-id="b7fad-188">**Call Park**</span></span>
    
    <span data-ttu-id="b7fad-189">Приложение парковки вызовов позволяет пользователю Корпоративная голосовая связь поставить звонок на удержание с одного телефона, а затем принимать вызов с другого телефона, не привявшись к ресурсам на телефоне, который принял вызов.</span><span class="sxs-lookup"><span data-stu-id="b7fad-189">Call Park application enables an Enterprise Voice user to put a call on hold from one telephone, and then receive the call from another telephone without tying up resources on the phone that received the call.</span></span> <span data-ttu-id="b7fad-190">Приложение парковки вызовов удобно использовать, когда пользователю необходимо переводить вызов, но конкретный получатель неизвестен.</span><span class="sxs-lookup"><span data-stu-id="b7fad-190">Call Park application is useful when a user needs to transfer a call, but the specific recipient is unknown.</span></span> 
    
- <span data-ttu-id="b7fad-191">**Помощник по конференц-залам**</span><span class="sxs-lookup"><span data-stu-id="b7fad-191">**Conference Attendant**</span></span>
    
    <span data-ttu-id="b7fad-192">Приложение помощника по аудиоконференциям предоставляет возможности аудиоконференций пользователям телефонов без услуги стороннее поставщика аудиоконференций.</span><span class="sxs-lookup"><span data-stu-id="b7fad-192">Conferencing Attendant application provides audio conferencing capabilities to phone users without the service of a third-party audio conferencing provider.</span></span>
    
- <span data-ttu-id="b7fad-193">**Извещание оглавлении для видеоконференций**</span><span class="sxs-lookup"><span data-stu-id="b7fad-193">**Conferencing Announcement**</span></span>
    
    <span data-ttu-id="b7fad-194">Приложение "Оповещение для конференц-связи" создает звуковые сигналы, сигнализющие о входе или выходе пользователей из конференции, а также уведомления пользователям телефонов, когда они отключены или отключены.</span><span class="sxs-lookup"><span data-stu-id="b7fad-194">Conferencing Announcement application produces tones that signal when users enter or leave a conference, as well as notifications to phone users when they are muted or unmuted.</span></span>
    
- <span data-ttu-id="b7fad-195">**Контроль допуска звонков**</span><span class="sxs-lookup"><span data-stu-id="b7fad-195">**Call Admission Control**</span></span>
    
    <span data-ttu-id="b7fad-196">Контроль допуска вызовов (CAC), также известный как управление пропускной способностью WAN, помогает предотвратить низкое качество взаимодействия для пользователей в захламляющих сетях, определяя, следует ли разрешить или установить новые сеансы связи в режиме реального времени на основе доступной пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="b7fad-196">Call Admission Control (CAC), also known as WAN bandwidth management, helps to prevent poor quality of experience for users on congested networks by determining, based on available bandwidth, whether to allow and new real-time communications sessions to be established.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="b7fad-197">CAC управляет только трафиком в режиме реального времени и не влияет на трафик данных.</span><span class="sxs-lookup"><span data-stu-id="b7fad-197">CAC only controls real-time traffic and does not affect data traffic.</span></span> 
  
    <span data-ttu-id="b7fad-198">Если новый сеанс голосовой связи или видеосвязи превышает ограничения пропускной способности, выделенные в сети WAN, сеанс либо блокируется, либо (только для телефонных звонков) перенапорязается в STN.</span><span class="sxs-lookup"><span data-stu-id="b7fad-198">If a new voice or video session exceeds the bandwidth limits that you have allocated on a WAN, the session is either blocked or (for phone calls only) rerouted to the PSTN.</span></span>
    

