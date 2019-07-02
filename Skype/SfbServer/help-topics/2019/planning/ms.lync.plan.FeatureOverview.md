---
title: Feature Overview (Planning Tool)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.plan.FeatureOverview
- ms.lync.plan.FeatureOverview
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 44783b37-c87f-41f2-9de1-39176f1856ab
ROBOTS: NOINDEX, NOFOLLOW
description: Средство планирования в Skype для бизнеса Server
ms.openlocfilehash: 90970dd3e82ffe401294307c09f356beca883c3b
ms.sourcegitcommit: d4248fefd706616bd3ccc5b510a6696303fa88e1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2019
ms.locfileid: "35418586"
---
# <a name="feature-overview-planning-tool"></a><span data-ttu-id="c3302-103">Feature Overview (Planning Tool)</span><span class="sxs-lookup"><span data-stu-id="c3302-103">Feature Overview (Planning Tool)</span></span>
 
<span data-ttu-id="c3302-104">Средство планирования в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="c3302-104">Skype for Business Server Planning Tool</span></span>
  
<span data-ttu-id="c3302-105">Вы можете спроектировать развертывание в Skype для бизнеса Server с помощью страницы " **центральный сайт** " средства "планирование".</span><span class="sxs-lookup"><span data-stu-id="c3302-105">You can use the **Central Sites** page of the Planning Tool to design the Skype for Business Server deployment.</span></span> <span data-ttu-id="c3302-106">You can create two either a centralized or distributed deployment.</span><span class="sxs-lookup"><span data-stu-id="c3302-106">You can create two either a centralized or distributed deployment.</span></span> <span data-ttu-id="c3302-107">Централизованное развертывание имеет только один центральный сайт, который позволяет всем пользователям Skype для бизнеса в Организации.</span><span class="sxs-lookup"><span data-stu-id="c3302-107">A centralized deployment only has one central site, which homes all Skype for Business users in your organization.</span></span> <span data-ttu-id="c3302-108">A distributed deployment has more than one central site.</span><span class="sxs-lookup"><span data-stu-id="c3302-108">A distributed deployment has more than one central site.</span></span> <span data-ttu-id="c3302-109">Если вы выполняете развертывание Skype для бизнеса Server на нескольких центральных сайтах, вы вводите количество пользователей на каждом центральном сайте в инструменте "планирование".</span><span class="sxs-lookup"><span data-stu-id="c3302-109">If you deploy Skype for Business Server at multiple central sites, then you will enter the number of users at each central site in the Planning Tool.</span></span>
  
<span data-ttu-id="c3302-110">Чтобы полностью выполнить определение центрального сайта, сначала необходимо предоставить следующие сведения.</span><span class="sxs-lookup"><span data-stu-id="c3302-110">To complete the definition of the central site, you first need to provide the following information:</span></span>
  
- <span data-ttu-id="c3302-111">**Имя сайта** — введите имя центрального сайта.</span><span class="sxs-lookup"><span data-stu-id="c3302-111">**Site Name** Enter the name of the Central Site.</span></span>
    
- <span data-ttu-id="c3302-112">**Число пользователей** — укажите число пользователей, включая пользователей сайтов филиалов, которые входят в центральный сайт.</span><span class="sxs-lookup"><span data-stu-id="c3302-112">**Number of Users** Enter the number of users, including users at branch sites who are homed into the central site.</span></span>
    
- <span data-ttu-id="c3302-113">**Пользователи облачного сетевого облака** Введите количество пользователей, которые подключены к центральному сайту из Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="c3302-113">**Cloud Homed Users** Enter the number of users that are homed into the central site from Skype for Business Online.</span></span>
    
## <a name="ui-elements"></a><span data-ttu-id="c3302-114">Элементы пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="c3302-114">UI Elements</span></span>

<span data-ttu-id="c3302-115">Остальные элементы заполняются вашими ответами на вопросы в мастере **начальной настройки**, а если мастер был пропущен, то эти элементы автоматически заполняются средством планирования.</span><span class="sxs-lookup"><span data-stu-id="c3302-115">The remaining elements have either been populated with the answers you provided to the questions presented in the **Get Started** wizard, or, if you skipped the wizard, automatically populated by the planning tool.</span></span>
  
### <a name="online-collaboration"></a><span data-ttu-id="c3302-116">Совместная работа в сети</span><span class="sxs-lookup"><span data-stu-id="c3302-116">Online Collaboration</span></span>

 <span data-ttu-id="c3302-117">В разделе **Совместная работа в сети** имеются следующие возможности.</span><span class="sxs-lookup"><span data-stu-id="c3302-117">**Online Collaboration** contains the following options:</span></span>
  
- <span data-ttu-id="c3302-118">**Обмен мгновенными сообщениями и сведениями о присутствии**</span><span class="sxs-lookup"><span data-stu-id="c3302-118">**IM and Presence**</span></span>
    
    <span data-ttu-id="c3302-119">Обмен мгновенными сообщениями (IM) предоставляет пользователям возможность взаимодействия друг с другом в режиме реального времени на своих компьютерах с помощью текстовых сообщений.</span><span class="sxs-lookup"><span data-stu-id="c3302-119">Instant Messaging (IM) enables users to communicate with each other in real time on their computers using text-based messages.</span></span> <span data-ttu-id="c3302-120">Поддерживаются как двусторонние, так и многосторонние сеансы обмена мгновенными сообщениями.</span><span class="sxs-lookup"><span data-stu-id="c3302-120">Both two-party and multiparty IM sessions are supported.</span></span> <span data-ttu-id="c3302-121">Функция присутствия предоставляет пользователям сведения о состоянии других пользователей в сети.</span><span class="sxs-lookup"><span data-stu-id="c3302-121">Presence provides information to users about the status of others on the network.</span></span> <span data-ttu-id="c3302-122">Состояние присутствия пользователя предоставляет сведения, которые помогают другим пользователям определить, находится ли пользователь в сети, и как лучше общаться с пользователем.</span><span class="sxs-lookup"><span data-stu-id="c3302-122">A user's presence status provides information to help others determine whether the user is online and how to best contact the user.</span></span> <span data-ttu-id="c3302-123">Например, с пользователем, который находится на собрании, лучше всего связаться по электронной почте.</span><span class="sxs-lookup"><span data-stu-id="c3302-123">For example, a user who is in a meeting is best contacted by email.</span></span>
    
- <span data-ttu-id="c3302-124">**Аудио- и видеоконференции**</span><span class="sxs-lookup"><span data-stu-id="c3302-124">**Audio and Video Conferencing**</span></span>
    
    <span data-ttu-id="c3302-125">Аудио- и видеоконференции позволяют проводить аудио- и видеоконференции в режиме реального времени.</span><span class="sxs-lookup"><span data-stu-id="c3302-125">Audio/Video (A/V) conferencing enables real-time audio and video conferences.</span></span>
    
- <span data-ttu-id="c3302-126">**Конференц-связь с телефонным подключением**</span><span class="sxs-lookup"><span data-stu-id="c3302-126">**Dial-in Conferencing**</span></span>
    
    <span data-ttu-id="c3302-p103">Конференц-связь с телефонным подключением предоставляет пользователям возможность присоединяться к аудио- и видеоконференциям с помощью телефона в ТСОП. Для конференц-связи с телефонным подключением требуется развертывание приложений "Помощник по конференц-связи" и "Служба оповещения для конференц-связи".</span><span class="sxs-lookup"><span data-stu-id="c3302-p103">Dial-in conferencing enables users to join an A/V from a telephone on the PSTN. Dial-in conferencing requires that you deploy the Conferencing Attendant and Conferencing Announcement Service applications.</span></span>
    
- <span data-ttu-id="c3302-129">**Веб-конференции**</span><span class="sxs-lookup"><span data-stu-id="c3302-129">**Web Conferencing**</span></span>
    
    <span data-ttu-id="c3302-130">С помощью веб-конференций корпоративные пользователи, находящиеся как внутри, так и вне брандмауэра, могут создавать конференции в режиме реального времени с размещением на внутренних серверах и присоединяться к ним.</span><span class="sxs-lookup"><span data-stu-id="c3302-130">Web conferencing enables enterprise users inside and outside of the firewall to create and join real-time conferences that are hosted on your internal servers.</span></span>
    
- <span data-ttu-id="c3302-131">**сохраняемый сеанс беседы**</span><span class="sxs-lookup"><span data-stu-id="c3302-131">**Persistent Chat**</span></span>
    
    <span data-ttu-id="c3302-p104">Сохраняемый чат предоставляет возможность нескольким пользователям принимать участие в беседах, в которых они публикуют контент по определенным темам, включая текст, ссылки и файлы, а также получают доступ к такому контенту. Хотя пользователи в течение сеанса могут взаимодействовать в режиме реального времени, контент каждого сеанса сохраняется и остается доступным после окончания сеанса.</span><span class="sxs-lookup"><span data-stu-id="c3302-p104">Persistent Chat enables multiple users to participate in conversations in which they post and access content about specific topics, including text, links, and files. Although users can communicate in real time during a session, the content of each session is persistent, which means it continues to be available after a session ends.</span></span>

    > [!NOTE] 
    > <span data-ttu-id="c3302-134">Сохраняемый чат доступен в Skype для бизнеса Server 2015, но больше не поддерживается в Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="c3302-134">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="c3302-135">Эта функция доступна в Teams.</span><span class="sxs-lookup"><span data-stu-id="c3302-135">The same functionality is available in Teams.</span></span> <span data-ttu-id="c3302-136">Дополнительные сведения можно найти [в разделе Skype для бизнеса и Microsoft Teams Upgrade](https://docs.microsoft.com/MicrosoftTeams/upgrade-start-here).</span><span class="sxs-lookup"><span data-stu-id="c3302-136">For more information, see [Skype for Business to Microsoft Teams upgrade](https://docs.microsoft.com/MicrosoftTeams/upgrade-start-here).</span></span> <span data-ttu-id="c3302-137">Если вы хотите использовать сохраняемый чат, вы можете либо перенести пользователей, которым нужны эти функции, в Teams, либо продолжить работу в Skype для бизнеса Server 2015.</span><span class="sxs-lookup"><span data-stu-id="c3302-137">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams or continue using Skype for Business Server 2015.</span></span>
    
### <a name="users"></a><span data-ttu-id="c3302-138">Пользователи</span><span class="sxs-lookup"><span data-stu-id="c3302-138">Users</span></span>

 <span data-ttu-id="c3302-139">В разделе **Пользователи** содержатся следующие варианты.</span><span class="sxs-lookup"><span data-stu-id="c3302-139">**Users** contains the following options:</span></span>
  
- <span data-ttu-id="c3302-140">**Внутренняя организация**</span><span class="sxs-lookup"><span data-stu-id="c3302-140">**Internal organization**</span></span>
    
- <span data-ttu-id="c3302-141">**Федерация с другими организациями**</span><span class="sxs-lookup"><span data-stu-id="c3302-141">**Federation with other organizations**</span></span>
    
- <span data-ttu-id="c3302-142">**Федерация с предыдущими версиями**</span><span class="sxs-lookup"><span data-stu-id="c3302-142">**Federation with previous versions**</span></span>
    
- <span data-ttu-id="c3302-p106">**Федерация с общедоступными поставщиками услуг обмена мгновенными сообщениями** — предоставляет пользователям в организации возможность установки соединения с общедоступными поставщиками услуг обмена мгновенными сообщениями, такими как MSN, Yahoo! и AOL. Для установки федерации с общедоступными сетями обмена мгновенными сообщениями требуется отдельная лицензия.</span><span class="sxs-lookup"><span data-stu-id="c3302-p106">**Federation with public IM services providers** Allows users in your organization to establish communication with public instant messaging service providers such as MSN, Yahoo!, and AOL. A separate license is required to establish federation with public instant messaging networks.</span></span>
    
- <span data-ttu-id="c3302-145">**Федерация с поставщиком услуг по протоколу XMPP**</span><span class="sxs-lookup"><span data-stu-id="c3302-145">**Federation with XMPP-based service provider**</span></span>
    
    <span data-ttu-id="c3302-146">В Skype для бизнеса Server 2015 появился полностью интегрированный прокси-сервер КСМПП (развернутый на пограничном сервере) и шлюз КСМПП, развернутый на серверах переднего плана.</span><span class="sxs-lookup"><span data-stu-id="c3302-146">Skype for Business Server 2015 introduced a fully integrated XMPP proxy (deployed on the Edge Servers) and an XMPP gateway deployed on your Front End Servers.</span></span> <span data-ttu-id="c3302-147">Вы можете развернуть Добавление и настройку шлюза КСМПП proxy и КСМПП, чтобы пользователи Skype для бизнеса сервера могли добавлять контакты из партнеров на основе КСМПП для обмена мгновенными сообщениями и их присутствия.</span><span class="sxs-lookup"><span data-stu-id="c3302-147">You can deploy Adding and configuring the XMPP proxy and XMPP gateway will allow your Skype for Business Server users to add contacts from XMPP-based partners for instant messaging (IM) and presence.</span></span>
    
- <span data-ttu-id="c3302-148">**Мобильность**</span><span class="sxs-lookup"><span data-stu-id="c3302-148">**Mobility**</span></span>
    
    <span data-ttu-id="c3302-149">При развертывании службы Mobility Service в Skype для бизнеса Server пользователи могут использовать поддерживаемые мобильные устройства Apple iOS, Android, Windows Phone или Nokia для выполнения таких операций, как отправка и получение мгновенных сообщений, просмотр контактов и Просмотр сведений о присутствии.</span><span class="sxs-lookup"><span data-stu-id="c3302-149">When you deploy the Skype for Business Server Mobility Service, users can use supported Apple iOS, Android, Windows Phone, or Nokia mobile devices to perform such activities as sending and receiving instant messages, viewing contacts, and viewing presence.</span></span>
    
- <span data-ttu-id="c3302-150">**Почтовый ящик W15 Exchange**</span><span class="sxs-lookup"><span data-stu-id="c3302-150">**W15 Exchange mailbox**</span></span>
    
    <span data-ttu-id="c3302-151">Skype для бизнеса Server позволяет использовать голосовые сообщения, хранящиеся в единой системе обмена сообщениями Exchange (UM). Эти голосовые сообщения будут отображаться как сообщения электронной почты в ящиках пользователей.</span><span class="sxs-lookup"><span data-stu-id="c3302-151">Skype for Business Server enables you to have voicemail messages stored in Exchange Unified Messaging (UM); those voicemail messages will then appear as email messages in your users' Inboxes.</span></span>

    > [!NOTE]
    > <span data-ttu-id="c3302-152">Единая система обмена сообщениями Exchange, которая ранее известна, больше не доступна в Exchange 2019, но вы по-прежнему можете использовать телефонную систему для записи голосовых сообщений, а затем оставить запись в почтовом ящике Exchange пользователя.</span><span class="sxs-lookup"><span data-stu-id="c3302-152">Exchange Unified Messaging as previously known is no longer available in Exchange 2019, but you can still use Phone System to record voicemail messages and then leave the recording in a user's Exchange mailbox.</span></span> <span data-ttu-id="c3302-153">Дополнительные сведения приведены в разделе [планирование облачной службы голосовой почты](../../../../sfbhybrid/hybrid/plan-cloud-voicemail.md) .</span><span class="sxs-lookup"><span data-stu-id="c3302-153">See [Plan Cloud Voicemail service](../../../../sfbhybrid/hybrid/plan-cloud-voicemail.md) for more information.</span></span>
    
### <a name="voice"></a><span data-ttu-id="c3302-154">Голосовая связь</span><span class="sxs-lookup"><span data-stu-id="c3302-154">Voice</span></span>

 <span data-ttu-id="c3302-155">В разделе **Голосовая связь** имеются следующие возможности.</span><span class="sxs-lookup"><span data-stu-id="c3302-155">**Voice** contains the following options:</span></span>
  
- <span data-ttu-id="c3302-156">**корпоративной голосовой связи**</span><span class="sxs-lookup"><span data-stu-id="c3302-156">**Enterprise Voice**</span></span>
    
    <span data-ttu-id="c3302-157">Корпоративная голосовая связь — это решение для Микросфт на базе программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="c3302-157">Enterprise voice is Microsft's software-powered VoIP solution.</span></span> <span data-ttu-id="c3302-158">Корпоративная голосовая связь позволяет пользователям использовать Skype для бизнеса для звонков с компьютера.</span><span class="sxs-lookup"><span data-stu-id="c3302-158">Enterprise voice enables users to use Skype for Business to place a phone call from their computer.</span></span>
    
- <span data-ttu-id="c3302-159">**Единая система обмена сообщениями Exchange**</span><span class="sxs-lookup"><span data-stu-id="c3302-159">**Exchange Unified Messaging**</span></span>
    
    <span data-ttu-id="c3302-160">Единая система обмена сообщениями Exchange объединяет голосовую почту и электронную почту в единую инфраструктуру для обмена сообщениями.</span><span class="sxs-lookup"><span data-stu-id="c3302-160">Exchange Unified Messaging (UM) combines voice mail and email into a single messaging infrastructure.</span></span> <span data-ttu-id="c3302-161">Skype для бизнеса Server 2015 использует Exchange UM для обеспечения ответа на звонки, доступа абонента, уведомления о звонке и служб автосекретаря.</span><span class="sxs-lookup"><span data-stu-id="c3302-161">Skype for Business Server 2015 uses Exchange UM to provide call answering, subscriber access, call notification, and auto attendant services.</span></span> <span data-ttu-id="c3302-162">Если вы используете эти службы, вам нужно будет интегрировать Exchange UM и Skype для бизнеса Server в общей топологии службы каталогов Active Directory.</span><span class="sxs-lookup"><span data-stu-id="c3302-162">If you use these services, you will need to integrate Exchange UM and Skype for Business Server in a shared Active Directory topology.</span></span>

    > [!NOTE]
    > <span data-ttu-id="c3302-163">Единая система обмена сообщениями Exchange, которая ранее известна, больше не доступна в Exchange 2019, но вы по-прежнему можете использовать телефонную систему для записи голосовых сообщений, а затем оставить запись в почтовом ящике Exchange пользователя.</span><span class="sxs-lookup"><span data-stu-id="c3302-163">Exchange Unified Messaging as previously known is no longer available in Exchange 2019, but you can still use Phone System to record voicemail messages and then leave the recording in a user's Exchange mailbox.</span></span> <span data-ttu-id="c3302-164">Дополнительные сведения приведены в разделе [планирование облачной службы голосовой почты](../../../../sfbhybrid/hybrid/plan-cloud-voicemail.md) .</span><span class="sxs-lookup"><span data-stu-id="c3302-164">See [Plan Cloud Voicemail service](../../../../sfbhybrid/hybrid/plan-cloud-voicemail.md) for more information.</span></span>
    
### <a name="additional-deployment-options"></a><span data-ttu-id="c3302-165">Дополнительные параметры развертывания</span><span class="sxs-lookup"><span data-stu-id="c3302-165">Additional Deployment Options</span></span>

 <span data-ttu-id="c3302-166">В разделе **Дополнительные параметры развертывания** имеются следующие возможности.</span><span class="sxs-lookup"><span data-stu-id="c3302-166">**Additional Deployment Options** contains the following options:</span></span>
  
- <span data-ttu-id="c3302-167">**Высокий уровень доступности**</span><span class="sxs-lookup"><span data-stu-id="c3302-167">**High Availability**</span></span>
    
    <span data-ttu-id="c3302-168">Для обеспечения высокого уровня доступности разрешается использование резервных серверов для поддержки отработки отказа.</span><span class="sxs-lookup"><span data-stu-id="c3302-168">High availability enables standby servers for failover support.</span></span>
    
- <span data-ttu-id="c3302-169">**Аварийное восстановление**</span><span class="sxs-lookup"><span data-stu-id="c3302-169">**Disaster Recovery**</span></span>
    
    <span data-ttu-id="c3302-170">Меры аварийного восстановления позволяют связывать пулы интерфейсов, расположенные в двух центрах обработки данных.</span><span class="sxs-lookup"><span data-stu-id="c3302-170">Disaster recovery measures enable you to pair Front End pools located in two datacenters.</span></span>
    
- <span data-ttu-id="c3302-171">**Мониторинг**</span><span class="sxs-lookup"><span data-stu-id="c3302-171">**Monitoring**</span></span>
    
    <span data-ttu-id="c3302-172">Monitoring captures call detail records related to communication sessions.</span><span class="sxs-lookup"><span data-stu-id="c3302-172">Monitoring captures call detail records related to communication sessions.</span></span> <span data-ttu-id="c3302-173">It also collects metrics from audio and video sessions at the participant endpoints.</span><span class="sxs-lookup"><span data-stu-id="c3302-173">It also collects metrics from audio and video sessions at the participant endpoints.</span></span> <span data-ttu-id="c3302-174">Сервер мониторинга обеспечивает статистику использования, тенденции и статистику качества мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="c3302-174">Monitoring Server provides usage statistics, trends, and media quality statistics.</span></span>
    
- <span data-ttu-id="c3302-175">**Архивирование**</span><span class="sxs-lookup"><span data-stu-id="c3302-175">**Archiving**</span></span>
    
    <span data-ttu-id="c3302-176">Архивация сохраняет беседы в виде обмена мгновенными сообщениями и конференции.</span><span class="sxs-lookup"><span data-stu-id="c3302-176">Archiving stores instant messaging conversations and conferences.</span></span>
    
- <span data-ttu-id="c3302-177">**Интеграция архивации Exchange**</span><span class="sxs-lookup"><span data-stu-id="c3302-177">**Exchange Archiving Integration**</span></span>
    
    <span data-ttu-id="c3302-178">Если у вас есть пользователи, которые подключены к Exchange и их почтовые ящики помещены на хранение на месте, вы можете выбрать параметр для интеграции хранилища Skype для бизнеса Server с хранилищем Exchange.</span><span class="sxs-lookup"><span data-stu-id="c3302-178">If you have users who are homed on Exchange and their mailboxes have been put on In-Place Hold, you can select the option to integrate Skype for Business Server storage with Exchange storage.</span></span>
    
- <span data-ttu-id="c3302-179">**IPv4**</span><span class="sxs-lookup"><span data-stu-id="c3302-179">**IPv4**</span></span>
    
    <span data-ttu-id="c3302-p113">Адреса IPv4 — 32-разрядные адреса, которые позволяют компьютеру осуществлять взаимодействие через Интернет. В связи с увеличением числа устройств по всему миру доступные адреса IPv4 закончились. В связи с этим многие устройства переходят на использование адресов IPv6.</span><span class="sxs-lookup"><span data-stu-id="c3302-p113">IPv4 addresses are 32-bit addresses that allow a computer to communicate over the Internet. Due to the increasing number of devices worldwide, the available IPv4 addresses have run out. Because of this, many new devices are moving to using IPv6 addresses.</span></span>
    
- <span data-ttu-id="c3302-182">**IPv6**</span><span class="sxs-lookup"><span data-stu-id="c3302-182">**IPv6**</span></span>
    
    <span data-ttu-id="c3302-p114">Адреса IPv6 выполняют ту же задачу, что и адреса IPv4 (с некоторыми дополнительными возможностями), но вместо использования 32 бит в адресах IPv6 используется 128 бит. Это не только предоставляет новый набор адресов, но существенно увеличивает их количество.</span><span class="sxs-lookup"><span data-stu-id="c3302-p114">IPv6 addresses perform the same function as IPv4 addresses (with some additional features), but instead of using only 32-bits, IPv6 addresses use 128-bits. This provides not only a new set of addresses, but also a much larger number of them.</span></span>
    
- <span data-ttu-id="c3302-185">**обновления устройств**</span><span class="sxs-lookup"><span data-stu-id="c3302-185">**Device Update Web service**</span></span>
    
    <span data-ttu-id="c3302-186">Веб-служба обновления устройств предоставляет автоматический способ обновления всех устройств, таких как Skype для бизнеса для Windows Phone, которые развертываются за пределами вашей организации.</span><span class="sxs-lookup"><span data-stu-id="c3302-186">The Device Update Web service provides an automated way to update all devices, such as Skype for Business for Windows Phone, that are deployed outside of your organization.</span></span>
    
### <a name="server-applications"></a><span data-ttu-id="c3302-187">Серверные приложения</span><span class="sxs-lookup"><span data-stu-id="c3302-187">Server Applications</span></span>

 <span data-ttu-id="c3302-188">В разделе **Серверные приложения** имеются следующие возможности.</span><span class="sxs-lookup"><span data-stu-id="c3302-188">**Server Applications** contains the following options:</span></span>
  
- <span data-ttu-id="c3302-189">**"Группа ответа"**</span><span class="sxs-lookup"><span data-stu-id="c3302-189">**Response Group**</span></span>
    
    <span data-ttu-id="c3302-190">Приложение "группа ответа" автоматически отвечает на запросы и распространяет звонки на доступ к агенту службы поддержки.</span><span class="sxs-lookup"><span data-stu-id="c3302-190">The Response Group application automatically answers and distributes calls to an available helpdesk agent.</span></span>
    
- <span data-ttu-id="c3302-191">**Объявление**</span><span class="sxs-lookup"><span data-stu-id="c3302-191">**Announcement**</span></span>
    
    <span data-ttu-id="c3302-192">Если вы планируете развернуть корпоративный голосовой стандарт, вы можете настроить способ обработки телефонных номеров, если номер набора номера действителен, но не назначен в общую область пользователя.</span><span class="sxs-lookup"><span data-stu-id="c3302-192">If you plan to deploy Enterprise Voice, you might want to be able to configure how phone calls are handled if the dialed number is valid but not assigned to a user common area.</span></span> <span data-ttu-id="c3302-193">Administrators can configure Announcement Service so that these calls transfer to a predetermined destination (phone number or SIP URI) or play an audio announcement or both.</span><span class="sxs-lookup"><span data-stu-id="c3302-193">Administrators can configure Announcement Service so that these calls transfer to a predetermined destination (phone number or SIP URI) or play an audio announcement or both.</span></span> <span data-ttu-id="c3302-194">Using Announcement Service avoids the situation in which a caller misdials and hears a busy tone or the SIP client receives an error message.</span><span class="sxs-lookup"><span data-stu-id="c3302-194">Using Announcement Service avoids the situation in which a caller misdials and hears a busy tone or the SIP client receives an error message.</span></span> <span data-ttu-id="c3302-195">Announcement Service functionality is a typical PBX feature.</span><span class="sxs-lookup"><span data-stu-id="c3302-195">Announcement Service functionality is a typical PBX feature.</span></span> 
    
- <span data-ttu-id="c3302-196">**Приостановка вызовов**</span><span class="sxs-lookup"><span data-stu-id="c3302-196">**Call Park**</span></span>
    
    <span data-ttu-id="c3302-197">Приложение для приема звонков позволяет корпоративному голосовому пользователю перевести звонок на удержание с одного телефона, а затем звонить с другого телефона, не поднимая ресурсы на телефоне, который получил звонок.</span><span class="sxs-lookup"><span data-stu-id="c3302-197">Call Park application enables an Enterprise Voice user to put a call on hold from one telephone, and then receive the call from another telephone without tying up resources on the phone that received the call.</span></span> <span data-ttu-id="c3302-198">Приложение для переадресации звонков полезно, когда пользователю необходимо передать звонок, но конкретный получатель неизвестен.</span><span class="sxs-lookup"><span data-stu-id="c3302-198">Call Park application is useful when a user needs to transfer a call, but the specific recipient is unknown.</span></span> 
    
- <span data-ttu-id="c3302-199">**Помощник по конференц-связи**</span><span class="sxs-lookup"><span data-stu-id="c3302-199">**Conference Attendant**</span></span>
    
    <span data-ttu-id="c3302-200">Приложение "Конференц-связь" обеспечивает возможности голосовой конференции для пользователей телефонной связи без услуги стороннего поставщика голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="c3302-200">Conferencing Attendant application provides audio conferencing capabilities to phone users without the service of a third-party audio conferencing provider.</span></span>
    
- <span data-ttu-id="c3302-201">**Оповещения для конференц-связи**</span><span class="sxs-lookup"><span data-stu-id="c3302-201">**Conferencing Announcement**</span></span>
    
    <span data-ttu-id="c3302-202">Приложение "объявление Конференции" создает звуки, предупреждающие о входе или выходе пользователей из конференции, а также уведомления для пользователей телефонии, когда они отключены или отключены.</span><span class="sxs-lookup"><span data-stu-id="c3302-202">Conferencing Announcement application produces tones that signal when users enter or leave a conference, as well as notifications to phone users when they are muted or unmuted.</span></span>
    
- <span data-ttu-id="c3302-203">**Контроль допуска звонков**</span><span class="sxs-lookup"><span data-stu-id="c3302-203">**Call Admission Control**</span></span>
    
    <span data-ttu-id="c3302-204">Контроль допуска звонков (CAC), который также называется управлением пропускной способностью WAN, помогает предотвратить падение качества взаимодействия пользователей в перегруженных сетях, разрешая или запрещая новые сеансы взаимодействия в режиме реального времени исходя из доступной пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="c3302-204">Call Admission Control (CAC), also known as WAN bandwidth management, helps to prevent poor quality of experience for users on congested networks by determining, based on available bandwidth, whether to allow and new real-time communications sessions to be established.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="c3302-205">CAC только управляет трафиком в режиме реального времени и не влияет на трафик данных.</span><span class="sxs-lookup"><span data-stu-id="c3302-205">CAC only controls real-time traffic and does not affect data traffic.</span></span> 
  
    <span data-ttu-id="c3302-206">Если новый аудио- или видеосеанс превышает ограничения пропускной способности, установленные в WAN, то этот сеанс либо блокируется, либо (только в случае телефонных вызовов) перенаправляется в ТСОП.</span><span class="sxs-lookup"><span data-stu-id="c3302-206">If a new voice or video session exceeds the bandwidth limits that you have allocated on a WAN, the session is either blocked or (for phone calls only) rerouted to the PSTN.</span></span>
    

