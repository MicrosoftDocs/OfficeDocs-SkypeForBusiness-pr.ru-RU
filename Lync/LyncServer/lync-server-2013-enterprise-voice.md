---
title: Lync Server 2013 Enterprise Voice
description: Lync Server 2013 Enterprise Voice.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enterprise Voice
ms:assetid: c9da8099-6f4f-4346-ac67-f041bb96072c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg417163(v=OCS.15)
ms:contentKeyID: 48185404
ms.date: 04/08/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e11f2497cf99319317a75b81f02ed0d8ca797fbf
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574235"
---
# <a name="enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="a1cfc-103">Корпоративная голосовая связь в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a1cfc-103">Enterprise Voice in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a1cfc-104">_**Последнее изменение темы:** 2015-04-08_</span><span class="sxs-lookup"><span data-stu-id="a1cfc-104">_**Topic Last Modified:** 2015-04-08_</span></span>

<span data-ttu-id="a1cfc-105">Благодаря корпоративной голосовой связи, Lync Server предоставляет автономное предложение по голосовой связи по протоколу VoIP для расширения или замены традиционных АТС (Private Branch Exchange).</span><span class="sxs-lookup"><span data-stu-id="a1cfc-105">With Enterprise Voice, Lync Server delivers a stand-alone Voice over Internet Protocol (VoIP) offering to enhance or replace traditional private branch exchange (PBX) systems.</span></span> <span data-ttu-id="a1cfc-106">Пользователи корпоративной голосовой связи могут звонить коллегам в сети VoIP или УАТС организации, а также звонить по традиционным телефонным номерам за пресроком вашей организации.</span><span class="sxs-lookup"><span data-stu-id="a1cfc-106">Enterprise Voice users can call colleagues on your organization’s VoIP network or PBX, and they can call traditional phone numbers outside your organization.</span></span> <span data-ttu-id="a1cfc-107">Решение для корпоративной голосовой связи включает в себя распространенные функции вызова, такие как ответ, пересылка, передача, удержание, предоставление, освобождение и парковки, а также расширенный 9-1-1 (E9-1-1) (E9-1-1 доступно только в США). Кроме того, Корпоративная голосовая связь поддерживает широкий спектр текущих и устаревших IP-и USB-устройств.</span><span class="sxs-lookup"><span data-stu-id="a1cfc-107">The Enterprise Voice solution includes common calling features such as answer, forward, transfer, hold, divert, release and park, and Enhanced 9-1-1 (E9-1-1) calling (E9-1-1 is available only in the United States.) Enterprise Voice also supports a broad range of current and older IP and USB devices.</span></span>

<div>

## <a name="placing-and-receiving-calls"></a><span data-ttu-id="a1cfc-108">Размещение и получение вызовов</span><span class="sxs-lookup"><span data-stu-id="a1cfc-108">Placing and Receiving Calls</span></span>

<span data-ttu-id="a1cfc-109">С помощью Lync пользователи могут совершать вызовы, вводя имя или номер телефона на клавиатуре или используя панель набора номера, отображаемую на экране.</span><span class="sxs-lookup"><span data-stu-id="a1cfc-109">Using Lync, users can place calls by typing a name or phone number on their keyboard, or using a dial pad displayed on their screen.</span></span> <span data-ttu-id="a1cfc-110">Пользователи также могут инициировать звонки напрямую из списка контактов.</span><span class="sxs-lookup"><span data-stu-id="a1cfc-110">Users can also initiate calls directly from their Contacts list.</span></span> <span data-ttu-id="a1cfc-111">Вы также можете развертывать устройства Lync Phone Edition, которые являются отдельными устройствами IP-телефонии, предоставляемыми партнерами корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="a1cfc-111">You can also deploy Lync Phone Edition devices, which are stand-alone IP phone devices provided by Microsoft partners.</span></span>

<span data-ttu-id="a1cfc-112">Пользователи могут иметь несколько телефонных устройств, зарегистрированных в Lync Server, и могут легко переключаться между ними.</span><span class="sxs-lookup"><span data-stu-id="a1cfc-112">Users can have multiple phone devices registered with Lync Server, and can switch between them easily.</span></span>

<span data-ttu-id="a1cfc-113">Пользователи получают оповещение о входящих вызовах на всех устройствах одновременно, с настраиваемыми мелодиями звонка на устройствах IP-телефонах и уведомлением, аналогичным мгновенным сообщениям на компьютере.</span><span class="sxs-lookup"><span data-stu-id="a1cfc-113">Users are alerted to incoming calls on all their devices simultaneously, with customizable ringtones on IP phone devices and a notification similar to an instant message on their PC.</span></span>

<span data-ttu-id="a1cfc-114">Пользователи также могут задать один телефонный номер, который подключается к стационарному телефону, компьютеру и мобильному телефону, поэтому они могут быть достижимы независимо от того, где они находятся.</span><span class="sxs-lookup"><span data-stu-id="a1cfc-114">Users can also set a single telephone number that connects to their desk phone, PC and mobile phone, so they can be reached no matter where they are.</span></span>

</div>

<div>

## <a name="basic-call-features"></a><span data-ttu-id="a1cfc-115">Основные функции вызова</span><span class="sxs-lookup"><span data-stu-id="a1cfc-115">Basic Call Features</span></span>

<span data-ttu-id="a1cfc-116">При вызове пользователь может отвечать на дополнительные входящие звонки или инициировать исходящие вызовы, а существующий активный вызов автоматически помещать на удержание.</span><span class="sxs-lookup"><span data-stu-id="a1cfc-116">While on a call, a user can answer additional incoming calls or initiate outgoing calls, and the existing active call is automatically put on hold.</span></span> <span data-ttu-id="a1cfc-117">Звонки могут передаваться от одного пользователя к другому, непосредственно или после того, как первый пользователь будет закрыт для второго пользователя.</span><span class="sxs-lookup"><span data-stu-id="a1cfc-117">Calls can be transferred from one user to another, either directly or after the first user speaks privately with the second user.</span></span> <span data-ttu-id="a1cfc-118">Пользователи также могут переносить вызовы на другое устройство; Например, они могут перенести активный Звонок на мобильный телефон, когда они покажут дверцу своего офиса.</span><span class="sxs-lookup"><span data-stu-id="a1cfc-118">Users can also transfer calls to another device; for example, they could transfer an active call to their mobile phone as they walk out the door of their office.</span></span>

</div>

<div>

## <a name="richer-communications"></a><span data-ttu-id="a1cfc-119">Более широкие возможности общения</span><span class="sxs-lookup"><span data-stu-id="a1cfc-119">Richer Communications</span></span>

<span data-ttu-id="a1cfc-120">При обращении к другому пользователю с помощью Lync пользователи могут легко добавить в вызов текст, видео или общий доступ к рабочему столу.</span><span class="sxs-lookup"><span data-stu-id="a1cfc-120">When talking to another user with Lync, users can easily add text, video, or desktop sharing to the call.</span></span> <span data-ttu-id="a1cfc-121">Функция "Do-not-беспокоить" интегрируется с параметрами присутствия в Lync.</span><span class="sxs-lookup"><span data-stu-id="a1cfc-121">The Do-Not-Disturb feature is integrated with the presence settings in Lync.</span></span>

<span data-ttu-id="a1cfc-122">С помощью единой системы обмена сообщениями Exchange, Lync и Lync Server интегрируются с Microsoft Exchange Server 2013 и Microsoft Outlook 2013.</span><span class="sxs-lookup"><span data-stu-id="a1cfc-122">With Exchange Unified Messaging (UM), Lync and Lync Server integrate with Microsoft Exchange Server 2013 and Microsoft Outlook 2013.</span></span> <span data-ttu-id="a1cfc-123">Пользователи могут видеть, есть ли у них новые сообщения голосовой почты в своем окне Lync и в электронной почте.</span><span class="sxs-lookup"><span data-stu-id="a1cfc-123">Users can see if they have new voice mail both in their Lync window and in email.</span></span> <span data-ttu-id="a1cfc-124">В электронной почте они могут щелкнуть для воспроизведения звукового сообщения голосовой почты в сообщении электронной почты или просмотреть запись сообщения голосовой почты.</span><span class="sxs-lookup"><span data-stu-id="a1cfc-124">While in email they can click to play the voice mail audio in an email message, or view a transcript of the voice mail message.</span></span>

</div>

<div>

## <a name="advanced-calling-features"></a><span data-ttu-id="a1cfc-125">Дополнительные функции звонков</span><span class="sxs-lookup"><span data-stu-id="a1cfc-125">Advanced Calling Features</span></span>

<span data-ttu-id="a1cfc-126">Корпоративная голосовая связь включает в себя несколько дополнительных функций звонков, таких как делегирование вызовов Lync, вызов групп, групповой ответ на звонки и группы ответа.</span><span class="sxs-lookup"><span data-stu-id="a1cfc-126">Enterprise Voice includes several advanced calling features as well, such as Lync call delegation, team calling, Group Call Pickup, and Response Groups.</span></span>

<span data-ttu-id="a1cfc-127">Делегирование вызовов Lync позволяет пользователям делегировать обработку звонков одному или нескольким помощникам, перейдя к разделу **Сервис** \> **Параметры** \> **переадресации звонков**.</span><span class="sxs-lookup"><span data-stu-id="a1cfc-127">Lync call delegation enables users to delegate call handling to one or more assistants, by going to **Tools** \> **Options** \> **Call Forwarding Settings**.</span></span> <span data-ttu-id="a1cfc-128">Делегат может выполнять несколько задач звонка от имени пользователя, включая вызовы для отбора, помещение вызовов и инициализацию конференций.</span><span class="sxs-lookup"><span data-stu-id="a1cfc-128">The delegate can perform multiple calling tasks on behalf of the user, including screening calls, placing calls, and initiating conferences.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="a1cfc-129">Возможно, вы ищете еще одну функцию с похожими именами, делегирование календаря Lync.</span><span class="sxs-lookup"><span data-stu-id="a1cfc-129">You may be looking for another similarly named feature, Lync calendar delegation.</span></span> <span data-ttu-id="a1cfc-130">Для этого не требуется функция корпоративной голосовой связи, которая позволяет пользователям планировать собрания по сети Lync из Outlook.</span><span class="sxs-lookup"><span data-stu-id="a1cfc-130">It doesn't require the Enterprise Voice feature and does allow users to schedule online Lync meetings from Outlook.</span></span> <span data-ttu-id="a1cfc-131">Если вы указали эту информацию, рекомендуем извлечь командлет <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy">Set — CsClientPolicy</A> для получения сведений о включении синхронизации делегатов Exchange.</span><span class="sxs-lookup"><span data-stu-id="a1cfc-131">If you've come here looking for that info, we recommend checking out <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy">Set-CsClientPolicy</A> for information on enabling Exchange delegate sync.</span></span>



</div>

<span data-ttu-id="a1cfc-132">Групповой звонок позволяет пользователю одновременно звонить на телефоны, чтобы все участники группы могли отвечать на звонок.</span><span class="sxs-lookup"><span data-stu-id="a1cfc-132">Team calling enables a user to have incoming calls simultaneously ring the phones of teammates so that anyone on the team can answer the call.</span></span>

<span data-ttu-id="a1cfc-133">Групповой ответ на звонки, новый компонент накопительных обновлений для Lync Server 2013: Февраль 2013, позволяет пользователям отвечать на входящие звонки своих коллег с собственных телефонов.</span><span class="sxs-lookup"><span data-stu-id="a1cfc-133">Group Call Pickup, a new feature in Cumulative Updates for Lync Server 2013: February 2013, lets users answer incoming calls to their colleagues from their own phones.</span></span> <span data-ttu-id="a1cfc-134">Ответ группового вызова отличается от командного вызова в основном в том, что входящий звонок выполняется только на телефоне получателя, но любой другой пользователь может ответить на него с помощью набора номера группы ответа на звонки.</span><span class="sxs-lookup"><span data-stu-id="a1cfc-134">Group Call Pickup differs from team calling primarily in that an incoming call rings only at the intended recipient's phone, but any other user can choose to answer it by dialing a call pickup group number.</span></span>

<span data-ttu-id="a1cfc-135">Группы ответа можно настроить для постановки в очередь и интеллектуального маршрутизации вызовов назначенным агентам.</span><span class="sxs-lookup"><span data-stu-id="a1cfc-135">Response Groups can be set up for queuing and intelligently routing calls to designated agents.</span></span> <span data-ttu-id="a1cfc-136">Распространенные варианты использования включают в себя службу технической поддержки, горячая линия управления персоналом и другие внутренние центры контактов.</span><span class="sxs-lookup"><span data-stu-id="a1cfc-136">Common uses include IT helpdesks, human resources hotlines, and other internal contact centers.</span></span>

</div>

<div>

## <a name="enterprise-voice-administration"></a><span data-ttu-id="a1cfc-137">Администрирование корпоративной голосовой связи</span><span class="sxs-lookup"><span data-stu-id="a1cfc-137">Enterprise Voice Administration</span></span>

<span data-ttu-id="a1cfc-138">Lync Server использует стандарты и опубликованные интерфейсы для взаимодействия с существующей инфраструктурой.</span><span class="sxs-lookup"><span data-stu-id="a1cfc-138">Lync Server uses standards and published interfaces to interoperate with existing infrastructure.</span></span> <span data-ttu-id="a1cfc-139">Он поддерживает параметры шлюза и SIP (такие как магистральная линия SIP) для подключения к системам IP-УАТС и сетям PSTN, чтобы можно было переносить пользователей на корпоративную голосовую связь с течением времени, в то же время сокращая перебои.</span><span class="sxs-lookup"><span data-stu-id="a1cfc-139">It supports both gateway and SIP options (such as SIP trunking) for interconnection to IP PBX systems and the PSTN networks, so that you can migrate users to Enterprise Voice over time, while minimizing disruption.</span></span> <span data-ttu-id="a1cfc-140">Lync Server поддерживает традиционные кодеки, такие как G. 711, G. 722 и G. 723.1 для взаимодействия с традиционными решениями VoIP.</span><span class="sxs-lookup"><span data-stu-id="a1cfc-140">Lync Server supports traditional codecs such as G.711, G.722, and G.723.1 for interoperability with traditional VoIP solutions.</span></span>

<span data-ttu-id="a1cfc-141">С помощью контроля допуска звонков (CAC) администраторы могут устанавливать ограничения на объемы голосовых и видеотрафиков Lync Server, которые передаются по сетевым связям с ограничениями, а также указывать действие, выполняемое при превышении предельного значения для нового вызова.</span><span class="sxs-lookup"><span data-stu-id="a1cfc-141">With call admission control (CAC), administrators can set limits on the amount of Lync Server voice and video traffic carried on constrained network links, and specify the action to be taken if a new call would exceed the limit.</span></span> <span data-ttu-id="a1cfc-142">Действия могут включать маршрутизацию по альтернативному пути или отключать вызов.</span><span class="sxs-lookup"><span data-stu-id="a1cfc-142">The actions could include routing by an alternate path, or refusing the call.</span></span>

<span data-ttu-id="a1cfc-143">Lync Server работает со сторонними устройствами для обеспечения связи в филиалах для предоставления местных телефонных услуг и подключения к PSTN в филиалах, в случае сбоя глобальной сети на центральном сайте.</span><span class="sxs-lookup"><span data-stu-id="a1cfc-143">Lync Server works with third-party Survivable Branch Appliances to provide local calling services and connection to PSTN at branch offices, in case of WAN failure at the central site.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

