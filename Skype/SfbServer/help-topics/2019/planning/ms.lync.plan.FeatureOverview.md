---
title: Обзор возможностей (средство планирования)
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.plan.FeatureOverview
- ms.lync.plan.FeatureOverview
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 44783b37-c87f-41f2-9de1-39176f1856ab
ROBOTS: NOINDEX, NOFOLLOW
description: Скайп для сервера планирования
ms.openlocfilehash: 22f14c0d31eaed5a6518263b15a9962e4bd136d0
ms.sourcegitcommit: 1f7299f535ec6b34f92301b4abc14d8922492eeb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2018
ms.locfileid: "21082610"
---
# <a name="feature-overview-planning-tool"></a><span data-ttu-id="c25da-103">Обзор возможностей (средство планирования)</span><span class="sxs-lookup"><span data-stu-id="c25da-103">Feature Overview (Planning Tool)</span></span>
 
<span data-ttu-id="c25da-104">Скайп для сервера планирования</span><span class="sxs-lookup"><span data-stu-id="c25da-104">Skype for Business Server Planning Tool</span></span>
  
<span data-ttu-id="c25da-105">Страница **Центральные узлы** средства планирования для разработки Скайп для развертывания Business Server.</span><span class="sxs-lookup"><span data-stu-id="c25da-105">You can use the **Central Sites** page of the Planning Tool to design the Skype for Business Server deployment.</span></span> <span data-ttu-id="c25da-106">Можно создать два либо централизованного или распределенного развертывания.</span><span class="sxs-lookup"><span data-stu-id="c25da-106">You can create two either a centralized or distributed deployment.</span></span> <span data-ttu-id="c25da-107">Централизованное развертывание имеет только один центральный сайт, который домов все Скайп для бизнес-пользователей в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="c25da-107">A centralized deployment only has one central site, which homes all Skype for Business users in your organization.</span></span> <span data-ttu-id="c25da-108">Распределенное развертывание имеет более одного центрального сайта.</span><span class="sxs-lookup"><span data-stu-id="c25da-108">A distributed deployment has more than one central site.</span></span> <span data-ttu-id="c25da-109">При развертывании Скайп для Business Server в нескольких центральных сайтов, в средстве планирования будет введите количество пользователей в каждом центральном сайте.</span><span class="sxs-lookup"><span data-stu-id="c25da-109">If you deploy Skype for Business Server at multiple central sites, then you will enter the number of users at each central site in the Planning Tool.</span></span>
  
<span data-ttu-id="c25da-110">Чтобы полностью выполнить определение центрального сайта, сначала необходимо предоставить следующие сведения.</span><span class="sxs-lookup"><span data-stu-id="c25da-110">To complete the definition of the central site, you first need to provide the following information:</span></span>
  
- <span data-ttu-id="c25da-111">**Имя сайта** — введите имя центрального сайта.</span><span class="sxs-lookup"><span data-stu-id="c25da-111">**Site Name** Enter the name of the Central Site.</span></span>
    
- <span data-ttu-id="c25da-112">**Число пользователей** — укажите число пользователей, включая пользователей сайтов филиалов, которые входят в центральный сайт.</span><span class="sxs-lookup"><span data-stu-id="c25da-112">**Number of Users** Enter the number of users, including users at branch sites who are homed into the central site.</span></span>
    
- <span data-ttu-id="c25da-113">**Облако, размещенных пользователей** Введите число пользователей, которые размещаются в центральном узле из Скайп для бизнеса в Интернет.</span><span class="sxs-lookup"><span data-stu-id="c25da-113">**Cloud Homed Users** Enter the number of users that are homed into the central site from Skype for Business Online.</span></span>
    
## <a name="ui-elements"></a><span data-ttu-id="c25da-114">Элементы пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="c25da-114">UI Elements</span></span>

<span data-ttu-id="c25da-115">Остальные элементы заполняются вашими ответами на вопросы в мастере **начальной настройки**, а если мастер был пропущен, то эти элементы автоматически заполняются средством планирования.</span><span class="sxs-lookup"><span data-stu-id="c25da-115">The remaining elements have either been populated with the answers you provided to the questions presented in the **Get Started** wizard, or, if you skipped the wizard, automatically populated by the planning tool.</span></span>
  
### <a name="online-collaboration"></a><span data-ttu-id="c25da-116">Совместная работа в сети</span><span class="sxs-lookup"><span data-stu-id="c25da-116">Online Collaboration</span></span>

 <span data-ttu-id="c25da-117">В разделе **Совместная работа в сети** имеются следующие возможности.</span><span class="sxs-lookup"><span data-stu-id="c25da-117">**Online Collaboration** contains the following options:</span></span>
  
- <span data-ttu-id="c25da-118">**Обмен мгновенными сообщениями и сведениями о присутствии**</span><span class="sxs-lookup"><span data-stu-id="c25da-118">**IM and Presence**</span></span>
    
    <span data-ttu-id="c25da-119">Обмен мгновенными сообщениями (IM) предоставляет пользователям возможность взаимодействия друг с другом в режиме реального времени на своих компьютерах с помощью текстовых сообщений.</span><span class="sxs-lookup"><span data-stu-id="c25da-119">Instant Messaging (IM) enables users to communicate with each other in real time on their computers using text-based messages.</span></span> <span data-ttu-id="c25da-120">Поддерживаются как двусторонние, так и многосторонние сеансы обмена мгновенными сообщениями.</span><span class="sxs-lookup"><span data-stu-id="c25da-120">Both two-party and multiparty IM sessions are supported.</span></span> <span data-ttu-id="c25da-121">Функция присутствия предоставляет пользователям сведения о состоянии других пользователей в сети.</span><span class="sxs-lookup"><span data-stu-id="c25da-121">Presence provides information to users about the status of others on the network.</span></span> <span data-ttu-id="c25da-122">Состояние присутствия пользователя содержит сведения, которые позволят другим пользователям определить, является ли пользователь находится в сети и как лучше всего связаться с пользователем.</span><span class="sxs-lookup"><span data-stu-id="c25da-122">A user's presence status provides information to help others determine whether the user is online and how to best contact the user.</span></span> <span data-ttu-id="c25da-123">Например, с пользователем, который находится на собрании, лучше всего связаться по электронной почте.</span><span class="sxs-lookup"><span data-stu-id="c25da-123">For example, a user who is in a meeting is best contacted by email.</span></span>
    
- <span data-ttu-id="c25da-124">**Аудио- и видеоконференции**</span><span class="sxs-lookup"><span data-stu-id="c25da-124">**Audio and Video Conferencing**</span></span>
    
    <span data-ttu-id="c25da-125">Аудио- и видеоконференции позволяют проводить аудио- и видеоконференции в режиме реального времени.</span><span class="sxs-lookup"><span data-stu-id="c25da-125">Audio/Video (A/V) conferencing enables real-time audio and video conferences.</span></span>
    
- <span data-ttu-id="c25da-126">**Конференц-связь с телефонным подключением**</span><span class="sxs-lookup"><span data-stu-id="c25da-126">**Dial-in Conferencing**</span></span>
    
    <span data-ttu-id="c25da-p103">Конференц-связь с телефонным подключением предоставляет пользователям возможность присоединяться к аудио- и видеоконференциям с помощью телефона в ТСОП. Для конференц-связи с телефонным подключением требуется развертывание приложений "Помощник по конференц-связи" и "Служба оповещения для конференц-связи".</span><span class="sxs-lookup"><span data-stu-id="c25da-p103">Dial-in conferencing enables users to join an A/V from a telephone on the PSTN. Dial-in conferencing requires that you deploy the Conferencing Attendant and Conferencing Announcement Service applications.</span></span>
    
- <span data-ttu-id="c25da-129">**Веб-конференции**</span><span class="sxs-lookup"><span data-stu-id="c25da-129">**Web Conferencing**</span></span>
    
    <span data-ttu-id="c25da-130">С помощью веб-конференций корпоративные пользователи, находящиеся как внутри, так и вне брандмауэра, могут создавать конференции в режиме реального времени с размещением на внутренних серверах и присоединяться к ним.</span><span class="sxs-lookup"><span data-stu-id="c25da-130">Web conferencing enables enterprise users inside and outside of the firewall to create and join real-time conferences that are hosted on your internal servers.</span></span>
    
- <span data-ttu-id="c25da-131">**сохраняемый сеанс беседы**</span><span class="sxs-lookup"><span data-stu-id="c25da-131">**Persistent Chat**</span></span>
    
    <span data-ttu-id="c25da-p104">Сохраняемый чат предоставляет возможность нескольким пользователям принимать участие в беседах, в которых они публикуют контент по определенным темам, включая текст, ссылки и файлы, а также получают доступ к такому контенту. Хотя пользователи в течение сеанса могут взаимодействовать в режиме реального времени, контент каждого сеанса сохраняется и остается доступным после окончания сеанса.</span><span class="sxs-lookup"><span data-stu-id="c25da-p104">Persistent Chat enables multiple users to participate in conversations in which they post and access content about specific topics, including text, links, and files. Although users can communicate in real time during a session, the content of each session is persistent, which means it continues to be available after a session ends.</span></span>

    > [!NOTE] 
    > <span data-ttu-id="c25da-134">Сохраняемый чат доступна в Скайп для Business Server 2015, но больше не поддерживается в Скайп для Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="c25da-134">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="c25da-135">Те же функциональные возможности доступны в группах.</span><span class="sxs-lookup"><span data-stu-id="c25da-135">The same functionality is available in Teams.</span></span> <span data-ttu-id="c25da-136">Дополнительные сведения содержатся в разделе [обновление Скайп для бизнеса для групп Майкрософт](https://docs.microsoft.com/MicrosoftTeams/journey-skypeforbusiness-teams).</span><span class="sxs-lookup"><span data-stu-id="c25da-136">For more information, see [Skype for Business to Microsoft Teams upgrade](https://docs.microsoft.com/MicrosoftTeams/journey-skypeforbusiness-teams).</span></span> <span data-ttu-id="c25da-137">Если необходимо использовать сохраняемого чата, возможны перенос пользователей, которым требуется эта функция группам или продолжить использование Скайп для Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="c25da-137">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams or continue using Skype for Business Server 2015.</span></span>
    
### <a name="users"></a><span data-ttu-id="c25da-138">Пользователи</span><span class="sxs-lookup"><span data-stu-id="c25da-138">Users</span></span>

 <span data-ttu-id="c25da-139">В разделе **Пользователи** содержатся следующие варианты.</span><span class="sxs-lookup"><span data-stu-id="c25da-139">**Users** contains the following options:</span></span>
  
- <span data-ttu-id="c25da-140">**Внутренняя организация**</span><span class="sxs-lookup"><span data-stu-id="c25da-140">**Internal organization**</span></span>
    
- <span data-ttu-id="c25da-141">**Федерация с другими организациями**</span><span class="sxs-lookup"><span data-stu-id="c25da-141">**Federation with other organizations**</span></span>
    
- <span data-ttu-id="c25da-142">**Федерация с предыдущими версиями**</span><span class="sxs-lookup"><span data-stu-id="c25da-142">**Federation with previous versions**</span></span>
    
- <span data-ttu-id="c25da-p106">**Федерация с общедоступными поставщиками услуг обмена мгновенными сообщениями** — предоставляет пользователям в организации возможность установки соединения с общедоступными поставщиками услуг обмена мгновенными сообщениями, такими как MSN, Yahoo! и AOL. Для установки федерации с общедоступными сетями обмена мгновенными сообщениями требуется отдельная лицензия.</span><span class="sxs-lookup"><span data-stu-id="c25da-p106">**Federation with public IM services providers** Allows users in your organization to establish communication with public instant messaging service providers such as MSN, Yahoo!, and AOL. A separate license is required to establish federation with public instant messaging networks.</span></span>
    
- <span data-ttu-id="c25da-145">**Федерация с поставщиком услуг по протоколу XMPP**</span><span class="sxs-lookup"><span data-stu-id="c25da-145">**Federation with XMPP-based service provider**</span></span>
    
    <span data-ttu-id="c25da-146">Скайп для Business Server 2015 введен полностью интегрированный прокси-сервера XMPP (развертывается на пограничных серверах) и шлюз XMPP, развернутого на серверах переднего плана.</span><span class="sxs-lookup"><span data-stu-id="c25da-146">Skype for Business Server 2015 introduced a fully integrated XMPP proxy (deployed on the Edge Servers) and an XMPP gateway deployed on your Front End Servers.</span></span> <span data-ttu-id="c25da-147">Можно развернуть Добавление и настройка прокси-сервера XMPP и шлюза XMPP позволяет Скайп Business Server пользователям добавлять контакты партнеров XMPP, обмена мгновенными сообщениями обмена Мгновенными сообщениями и присутствия.</span><span class="sxs-lookup"><span data-stu-id="c25da-147">You can deploy Adding and configuring the XMPP proxy and XMPP gateway will allow your Skype for Business Server users to add contacts from XMPP-based partners for instant messaging (IM) and presence.</span></span>
    
- <span data-ttu-id="c25da-148">**Мобильность**</span><span class="sxs-lookup"><span data-stu-id="c25da-148">**Mobility**</span></span>
    
    <span data-ttu-id="c25da-149">При развертывании Скайп для службы Mobility Business Server, пользователи могут использовать поддерживаемые Apple iOS, Android (en), Windows Phone и Nokia мобильных устройств для выполнения действий, таких как отправка и получение мгновенных сообщений, Просмотр контактов и просмотр сведений о присутствии.</span><span class="sxs-lookup"><span data-stu-id="c25da-149">When you deploy the Skype for Business Server Mobility Service, users can use supported Apple iOS, Android, Windows Phone, or Nokia mobile devices to perform such activities as sending and receiving instant messages, viewing contacts, and viewing presence.</span></span>
    
- <span data-ttu-id="c25da-150">**Почтовый ящик W15 Exchange**</span><span class="sxs-lookup"><span data-stu-id="c25da-150">**W15 Exchange mailbox**</span></span>
    
    <span data-ttu-id="c25da-151">Скайп для Business Server позволяет иметь сообщения голосовой почты, хранящиеся в Exchange единой системы обмена сообщениями (UM); Эти сообщения голосовой почты появится в виде сообщения электронной почты в почтовые ящики пользователей.</span><span class="sxs-lookup"><span data-stu-id="c25da-151">Skype for Business Server enables you to have voicemail messages stored in Exchange Unified Messaging (UM); those voicemail messages will then appear as email messages in your users' Inboxes.</span></span>

    > [!NOTE]
    > <span data-ttu-id="c25da-152">Единая система обмена сообщениями Exchange ранее известных как больше недоступен в Exchange 2019, но можно использовать телефонной системой для записи голосовых сообщений и оставьте записи в почтовый ящик Exchange пользователя.</span><span class="sxs-lookup"><span data-stu-id="c25da-152">Exchange Unified Messaging as previously known is no longer available in Exchange 2019, but you can still use Phone System to record voicemail messages and then leave the recording in a user's Exchange mailbox.</span></span> <span data-ttu-id="c25da-153">[Планирование голосовой почты облачной службы](../../../../SfBServer2019/hybrid/plan-cloud-voicemail.md) более подробные сведения.</span><span class="sxs-lookup"><span data-stu-id="c25da-153">See [Plan Cloud Voicemail service](../../../../SfBServer2019/hybrid/plan-cloud-voicemail.md) for more information.</span></span>
    
### <a name="voice"></a><span data-ttu-id="c25da-154">Голосовая связь</span><span class="sxs-lookup"><span data-stu-id="c25da-154">Voice</span></span>

 <span data-ttu-id="c25da-155">В разделе **Голосовая связь** имеются следующие возможности.</span><span class="sxs-lookup"><span data-stu-id="c25da-155">**Voice** contains the following options:</span></span>
  
- <span data-ttu-id="c25da-156">**корпоративной голосовой связи**</span><span class="sxs-lookup"><span data-stu-id="c25da-156">**Enterprise Voice**</span></span>
    
    <span data-ttu-id="c25da-157">Корпоративной голосовой связи — решение программные средства VoIP в Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="c25da-157">Enterprise voice is Microsft's software-powered VoIP solution.</span></span> <span data-ttu-id="c25da-158">Корпоративная голосовая связь позволяет пользователям использовать Скайп для бизнеса на звонок со своего компьютера.</span><span class="sxs-lookup"><span data-stu-id="c25da-158">Enterprise voice enables users to use Skype for Business to place a phone call from their computer.</span></span>
    
- <span data-ttu-id="c25da-159">**Единая система обмена сообщениями Exchange**</span><span class="sxs-lookup"><span data-stu-id="c25da-159">**Exchange Unified Messaging**</span></span>
    
    <span data-ttu-id="c25da-160">Exchange единой системе обмена СООБЩЕНИЯМИ объединяет голосовой почты и адрес электронной почты в составе единой инфраструктуры обмена сообщениями.</span><span class="sxs-lookup"><span data-stu-id="c25da-160">Exchange Unified Messaging (UM) combines voice mail and email into a single messaging infrastructure.</span></span> <span data-ttu-id="c25da-161">Скайп для Business Server 2015 использует обмена СООБЩЕНИЯМИ Exchange для предоставления ответа на вызовы абонентского доступа, уведомления о пропущенных звонках и служб auto attendant.</span><span class="sxs-lookup"><span data-stu-id="c25da-161">Skype for Business Server 2015 uses Exchange UM to provide call answering, subscriber access, call notification, and auto attendant services.</span></span> <span data-ttu-id="c25da-162">Если вы используете эти службы, необходимо интегрировать Exchange единой системы обмена СООБЩЕНИЯМИ и Скайп для Business Server в общей топологии Active Directory.</span><span class="sxs-lookup"><span data-stu-id="c25da-162">If you use these services, you will need to integrate Exchange UM and Skype for Business Server in a shared Active Directory topology.</span></span>

    > [!NOTE]
    > <span data-ttu-id="c25da-163">Единая система обмена сообщениями Exchange ранее известных как больше недоступен в Exchange 2019, но можно использовать телефонной системой для записи голосовых сообщений и оставьте записи в почтовый ящик Exchange пользователя.</span><span class="sxs-lookup"><span data-stu-id="c25da-163">Exchange Unified Messaging as previously known is no longer available in Exchange 2019, but you can still use Phone System to record voicemail messages and then leave the recording in a user's Exchange mailbox.</span></span> <span data-ttu-id="c25da-164">[Планирование голосовой почты облачной службы](../../../../SfBServer2019/hybrid/plan-cloud-voicemail.md) более подробные сведения.</span><span class="sxs-lookup"><span data-stu-id="c25da-164">See [Plan Cloud Voicemail service](../../../../SfBServer2019/hybrid/plan-cloud-voicemail.md) for more information.</span></span>
    
### <a name="additional-deployment-options"></a><span data-ttu-id="c25da-165">Дополнительные параметры развертывания</span><span class="sxs-lookup"><span data-stu-id="c25da-165">Additional Deployment Options</span></span>

 <span data-ttu-id="c25da-166">В разделе **Дополнительные параметры развертывания** имеются следующие возможности.</span><span class="sxs-lookup"><span data-stu-id="c25da-166">**Additional Deployment Options** contains the following options:</span></span>
  
- <span data-ttu-id="c25da-167">**Высокий уровень доступности**</span><span class="sxs-lookup"><span data-stu-id="c25da-167">**High Availability**</span></span>
    
    <span data-ttu-id="c25da-168">Для обеспечения высокого уровня доступности разрешается использование резервных серверов для поддержки отработки отказа.</span><span class="sxs-lookup"><span data-stu-id="c25da-168">High availability enables standby servers for failover support.</span></span>
    
- <span data-ttu-id="c25da-169">**Аварийное восстановление**</span><span class="sxs-lookup"><span data-stu-id="c25da-169">**Disaster Recovery**</span></span>
    
    <span data-ttu-id="c25da-170">Аварийное восстановление меры позволяют пары пулов переднего плана, расположенный в двух центров обработки данных.</span><span class="sxs-lookup"><span data-stu-id="c25da-170">Disaster recovery measures enable you to pair Front End pools located in two datacenters.</span></span>
    
- <span data-ttu-id="c25da-171">**Мониторинг**</span><span class="sxs-lookup"><span data-stu-id="c25da-171">**Monitoring**</span></span>
    
    <span data-ttu-id="c25da-172">Мониторинг захватывает записи регистрации вызовов, связанные с сеансов связи.</span><span class="sxs-lookup"><span data-stu-id="c25da-172">Monitoring captures call detail records related to communication sessions.</span></span> <span data-ttu-id="c25da-173">Он также собирает метрики от сеансов аудио- и видеоконференций на участников конечные точки.</span><span class="sxs-lookup"><span data-stu-id="c25da-173">It also collects metrics from audio and video sessions at the participant endpoints.</span></span> <span data-ttu-id="c25da-174">Сервер мониторинга предоставляет статистику использования, тенденции и статистику качества мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="c25da-174">Monitoring Server provides usage statistics, trends, and media quality statistics.</span></span>
    
- <span data-ttu-id="c25da-175">**Архивирование**</span><span class="sxs-lookup"><span data-stu-id="c25da-175">**Archiving**</span></span>
    
    <span data-ttu-id="c25da-176">Архивация сохраняет беседы в виде обмена мгновенными сообщениями и конференции.</span><span class="sxs-lookup"><span data-stu-id="c25da-176">Archiving stores instant messaging conversations and conferences.</span></span>
    
- <span data-ttu-id="c25da-177">**Интеграция архивации Exchange**</span><span class="sxs-lookup"><span data-stu-id="c25da-177">**Exchange Archiving Integration**</span></span>
    
    <span data-ttu-id="c25da-178">Если у вас есть пользователи, которые размещаются на сервере Exchange и их почтовые ящики находятся на хранение на месте, можно выбрать параметр для интеграции Скайп хранилища сервера Business с хранилищем Exchange.</span><span class="sxs-lookup"><span data-stu-id="c25da-178">If you have users who are homed on Exchange and their mailboxes have been put on In-Place Hold, you can select the option to integrate Skype for Business Server storage with Exchange storage.</span></span>
    
- <span data-ttu-id="c25da-179">**IPv4**</span><span class="sxs-lookup"><span data-stu-id="c25da-179">**IPv4**</span></span>
    
    <span data-ttu-id="c25da-p113">Адреса IPv4 — 32-разрядные адреса, которые позволяют компьютеру осуществлять взаимодействие через Интернет. В связи с увеличением числа устройств по всему миру доступные адреса IPv4 закончились. В связи с этим многие устройства переходят на использование адресов IPv6.</span><span class="sxs-lookup"><span data-stu-id="c25da-p113">IPv4 addresses are 32-bit addresses that allow a computer to communicate over the Internet. Due to the increasing number of devices worldwide, the available IPv4 addresses have run out. Because of this, many new devices are moving to using IPv6 addresses.</span></span>
    
- <span data-ttu-id="c25da-182">**IP версии 6**</span><span class="sxs-lookup"><span data-stu-id="c25da-182">**IPv6**</span></span>
    
    <span data-ttu-id="c25da-p114">Адреса IPv6 выполняют ту же задачу, что и адреса IPv4 (с некоторыми дополнительными возможностями), но вместо использования 32 бит в адресах IPv6 используется 128 бит. Это не только предоставляет новый набор адресов, но существенно увеличивает их количество.</span><span class="sxs-lookup"><span data-stu-id="c25da-p114">IPv6 addresses perform the same function as IPv4 addresses (with some additional features), but instead of using only 32-bits, IPv6 addresses use 128-bits. This provides not only a new set of addresses, but also a much larger number of them.</span></span>
    
- <span data-ttu-id="c25da-185">**обновления устройств**</span><span class="sxs-lookup"><span data-stu-id="c25da-185">**Device Update Web service**</span></span>
    
    <span data-ttu-id="c25da-186">Обновление веб-службе устройств обеспечение автоматического для обновления всех устройствах, таких как Скайп для бизнеса для Windows Phone, развернутых за пределами вашей организации.</span><span class="sxs-lookup"><span data-stu-id="c25da-186">The Device Update Web service provides an automated way to update all devices, such as Skype for Business for Windows Phone, that are deployed outside of your organization.</span></span>
    
### <a name="server-applications"></a><span data-ttu-id="c25da-187">Серверные приложения</span><span class="sxs-lookup"><span data-stu-id="c25da-187">Server Applications</span></span>

 <span data-ttu-id="c25da-188">В разделе **Серверные приложения** имеются следующие возможности.</span><span class="sxs-lookup"><span data-stu-id="c25da-188">**Server Applications** contains the following options:</span></span>
  
- <span data-ttu-id="c25da-189">**"Группа ответа"**</span><span class="sxs-lookup"><span data-stu-id="c25da-189">**Response Group**</span></span>
    
    <span data-ttu-id="c25da-190">Приложение группы ответа автоматически отвечает и распространять вызовы к агенту доступные служба технической поддержки.</span><span class="sxs-lookup"><span data-stu-id="c25da-190">The Response Group application automatically answers and distributes calls to an available helpdesk agent.</span></span>
    
- <span data-ttu-id="c25da-191">**Информационное сообщение**</span><span class="sxs-lookup"><span data-stu-id="c25da-191">**Announcement**</span></span>
    
    <span data-ttu-id="c25da-192">Если планируется развертывание корпоративной голосовой связи, можно включить могли настроить как телефонные звонки обрабатываются, если набранный номер является допустимым, но не назначено общего доступа пользователей.</span><span class="sxs-lookup"><span data-stu-id="c25da-192">If you plan to deploy Enterprise Voice, you might want to be able to configure how phone calls are handled if the dialed number is valid but not assigned to a user common area.</span></span> <span data-ttu-id="c25da-193">Администраторы могут настроить службы оповещения, чтобы перенести в заданное место назначения (номер телефона или SIP URI) или воспроизвести звуковое сообщение или оба эти вызовы.</span><span class="sxs-lookup"><span data-stu-id="c25da-193">Administrators can configure Announcement Service so that these calls transfer to a predetermined destination (phone number or SIP URI) or play an audio announcement or both.</span></span> <span data-ttu-id="c25da-194">С помощью службы оповещения позволяет избежать ситуации, в которой вызывающего misdials и слышит занята или SIP клиент получает сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="c25da-194">Using Announcement Service avoids the situation in which a caller misdials and hears a busy tone or the SIP client receives an error message.</span></span> <span data-ttu-id="c25da-195">Функциональные возможности службы оповещения является компонентом обычной УАТС.</span><span class="sxs-lookup"><span data-stu-id="c25da-195">Announcement Service functionality is a typical PBX feature.</span></span> 
    
- <span data-ttu-id="c25da-196">**Приостановка вызовов**</span><span class="sxs-lookup"><span data-stu-id="c25da-196">**Call Park**</span></span>
    
    <span data-ttu-id="c25da-197">Включает приложения парковки вызовов корпоративной голосовой связи пользователю переводить вызов в удержание из одного телефона и затем принять звонок с другого телефона, не занимая ресурсы на телефоне, принявшего звонок.</span><span class="sxs-lookup"><span data-stu-id="c25da-197">Call Park application enables an Enterprise Voice user to put a call on hold from one telephone, and then receive the call from another telephone without tying up resources on the phone that received the call.</span></span> <span data-ttu-id="c25da-198">Приложение парковки вызовов полезен, когда пользователю требуется переключить звонок, но неизвестно определенного получателя.</span><span class="sxs-lookup"><span data-stu-id="c25da-198">Call Park application is useful when a user needs to transfer a call, but the specific recipient is unknown.</span></span> 
    
- <span data-ttu-id="c25da-199">**Помощник по конференц-связи**</span><span class="sxs-lookup"><span data-stu-id="c25da-199">**Conference Attendant**</span></span>
    
    <span data-ttu-id="c25da-200">Помощника по конференц-связи предоставляет возможности аудиоконференций пользователям телефона без службы поставщика аудиоконференций сторонних производителей.</span><span class="sxs-lookup"><span data-stu-id="c25da-200">Conferencing Attendant application provides audio conferencing capabilities to phone users without the service of a third-party audio conferencing provider.</span></span>
    
- <span data-ttu-id="c25da-201">**Оповещения для конференц-связи**</span><span class="sxs-lookup"><span data-stu-id="c25da-201">**Conferencing Announcement**</span></span>
    
    <span data-ttu-id="c25da-202">Объявление конференц-связи, что приложения создает мелодии, которые сообщают, когда пользователи введите или оставьте конференц-связи, а также уведомления о телефона пользователям при их выключен ли или ничего.</span><span class="sxs-lookup"><span data-stu-id="c25da-202">Conferencing Announcement application produces tones that signal when users enter or leave a conference, as well as notifications to phone users when they are muted or unmuted.</span></span>
    
- <span data-ttu-id="c25da-203">**Контроль допуска звонков**</span><span class="sxs-lookup"><span data-stu-id="c25da-203">**Call Admission Control**</span></span>
    
    <span data-ttu-id="c25da-204">Контроль допуска звонков (CAC), который также называется управлением пропускной способностью WAN, помогает предотвратить падение качества взаимодействия пользователей в перегруженных сетях, разрешая или запрещая новые сеансы взаимодействия в режиме реального времени исходя из доступной пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="c25da-204">Call Admission Control (CAC), also known as WAN bandwidth management, helps to prevent poor quality of experience for users on congested networks by determining, based on available bandwidth, whether to allow and new real-time communications sessions to be established.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="c25da-205">CAC только управляет трафиком в режиме реального времени и не влияет на трафик данных.</span><span class="sxs-lookup"><span data-stu-id="c25da-205">CAC only controls real-time traffic and does not affect data traffic.</span></span> 
  
    <span data-ttu-id="c25da-206">Если новый аудио- или видеосеанс превышает ограничения пропускной способности, установленные в WAN, то этот сеанс либо блокируется, либо (только в случае телефонных вызовов) перенаправляется в ТСОП.</span><span class="sxs-lookup"><span data-stu-id="c25da-206">If a new voice or video session exceeds the bandwidth limits that you have allocated on a WAN, the session is either blocked or (for phone calls only) rerouted to the PSTN.</span></span>
    

