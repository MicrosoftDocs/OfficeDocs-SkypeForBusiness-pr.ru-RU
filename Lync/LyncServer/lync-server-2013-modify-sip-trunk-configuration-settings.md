---
title: 'Lync Server 2013: изменение параметров конфигурации магистрали SIP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify SIP trunk configuration settings
ms:assetid: 7d68b09c-9ea0-43bd-997c-df887869d607
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688104(v=OCS.15)
ms:contentKeyID: 49733703
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 356c418c620cbbf38a97da2df652b5767f9fced9
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48515326"
---
# <a name="modify-sip-trunk-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="81c03-102">Изменение параметров конфигурации магистрали SIP в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="81c03-102">Modify SIP trunk configuration settings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="81c03-103">_**Последнее изменение темы:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="81c03-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="81c03-p101">Параметры конфигурации линий связи SIP определяют возможности и связи между сервером-посредником и шлюзом телефонной сети общего пользования (ТСОП), IP-PBX или пограничным контроллером сеансов (SBC) на стороне поставщика услуг. Эти параметры позволяют определить:</span><span class="sxs-lookup"><span data-stu-id="81c03-p101">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the public switched telephone network (PSTN) gateway, an IP-public branch exchange (PBX), or a Session Border Controller (SBC) at the service provider. These settings do such things as specify:</span></span>

  - <span data-ttu-id="81c03-106">Следует ли включить обход медиаданных на линиях связи.</span><span class="sxs-lookup"><span data-stu-id="81c03-106">Whether media bypass should be enabled on the trunks.</span></span>

  - <span data-ttu-id="81c03-107">Условия, при которых передаются пакеты по протоколу RTCP.</span><span class="sxs-lookup"><span data-stu-id="81c03-107">The conditions under which real-time transport control protocol (RTCP) packets are sent.</span></span>

  - <span data-ttu-id="81c03-108">Требуется ли шифрование по протоколу SRTP на каждой магистрали.</span><span class="sxs-lookup"><span data-stu-id="81c03-108">Whether or not secure real-time protocol (SRTP) encryption is required on each trunk.</span></span>

<span data-ttu-id="81c03-109">При установке Microsoft Lync Server 2013 создается глобальная коллекция параметров конфигурации магистрали SIP.</span><span class="sxs-lookup"><span data-stu-id="81c03-109">When you install Microsoft Lync Server 2013, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="81c03-110">Кроме того, администраторы могут создать настраиваемые коллекции параметров в области узла или службы (только для службы шлюза ТСОП).</span><span class="sxs-lookup"><span data-stu-id="81c03-110">In addition, administrators can create custom setting collections at the site scope or at the service scope (for the PSTN gateway service, only).</span></span> <span data-ttu-id="81c03-111">Любую из этих коллекций позже можно будет изменить с помощью панели управления Lync Server или Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="81c03-111">Any of these collections can later be modified using either Lync Server Control Panel or Windows PowerShell.</span></span>

<span data-ttu-id="81c03-112">При изменении параметров конфигурации магистрали SIP с помощью панели управления Lync Server доступны следующие варианты:</span><span class="sxs-lookup"><span data-stu-id="81c03-112">When modifying SIP trunk configuration settings using Lync Server Control Panel, the following options are available to you:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="81c03-113">Параметр пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="81c03-113">UI Setting</span></span></th>
<th><span data-ttu-id="81c03-114">Параметр PowerShell</span><span class="sxs-lookup"><span data-stu-id="81c03-114">PowerShell Parameter</span></span></th>
<th><span data-ttu-id="81c03-115">Описание</span><span class="sxs-lookup"><span data-stu-id="81c03-115">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="81c03-116">Имя</span><span class="sxs-lookup"><span data-stu-id="81c03-116">Name</span></span></p></td>
<td><p><span data-ttu-id="81c03-117">Удостоверение</span><span class="sxs-lookup"><span data-stu-id="81c03-117">Identity</span></span></p></td>
<td><p><span data-ttu-id="81c03-p103">Уникальный идентификатор для коллекции. Это свойство только для чтения; вы не можете изменить идентификатор коллекции параметров настройки магистральной линии связи.</span><span class="sxs-lookup"><span data-stu-id="81c03-p103">Unique identifier for the collection. This property is read-only; you cannot change the Identity of a collection of trunk configuration settings.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="81c03-120">Описание</span><span class="sxs-lookup"><span data-stu-id="81c03-120">Description</span></span></p></td>
<td><p><span data-ttu-id="81c03-121">Описание</span><span class="sxs-lookup"><span data-stu-id="81c03-121">Description</span></span></p></td>
<td><p><span data-ttu-id="81c03-122">Предоставляет администраторам возможность сохранять дополнительную информацию о параметрах (например, сведения о цели настройки магистральной линии связи).</span><span class="sxs-lookup"><span data-stu-id="81c03-122">Provides a way for administrators to store addition information about the settings (for example, the purpose of the trunk configuration).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="81c03-123">Максимальное количество поддерживаемых предварительных диалогов</span><span class="sxs-lookup"><span data-stu-id="81c03-123">Maximum early dialogs supported</span></span></p></td>
<td><p><span data-ttu-id="81c03-124">максеарлидиалогс</span><span class="sxs-lookup"><span data-stu-id="81c03-124">MaxEarlyDialogs</span></span></p></td>
<td><p><span data-ttu-id="81c03-125">Максимальное количество разветвляющихся ответов, которое шлюз ТСОП, IP-PBX или пограничный контроллер сеансов (SBC) на стороне поставщика службы может получить на приглашение, отправленное серверу-посреднику.</span><span class="sxs-lookup"><span data-stu-id="81c03-125">The maximum number of forked responses a PSTN gateway, IP-PBX, or SBC at the service provider can receive to an Invite that it sent to the Mediation Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="81c03-126">Уровень поддержки шифрования</span><span class="sxs-lookup"><span data-stu-id="81c03-126">Encryption support level</span></span></p></td>
<td><p><span data-ttu-id="81c03-127">сртпмоде</span><span class="sxs-lookup"><span data-stu-id="81c03-127">SRTPMode</span></span></p></td>
<td><p><span data-ttu-id="81c03-128">Указывает уровень поддержки для защиты трафика медиаданных между сервером-посредником и шлюзом ТСОП, IP-PBX или пограничным контроллером сеансов на стороне поставщика службы.</span><span class="sxs-lookup"><span data-stu-id="81c03-128">Indicates the level of support for protecting media traffic between the Mediation Server and the PSTN Gateway, IP-PBX, or SBC at the service provider.</span></span> <span data-ttu-id="81c03-129">Для случаев обхода медиаданных это значение должно быть совместимо с параметром EncryptionLevel в настройке медиаданных.</span><span class="sxs-lookup"><span data-stu-id="81c03-129">For media bypass cases, this value must be compatible with the EncryptionLevel setting in the media configuration.</span></span> <span data-ttu-id="81c03-130">Конфигурация мультимедиа задается с помощью командлетов <a href="https://docs.microsoft.com/powershell/module/skype/New-CsMediaConfiguration">New-CsMediaConfiguration</a> и <a href="https://docs.microsoft.com/powershell/module/skype/Set-CsMediaConfiguration">Set-CsMediaConfiguration</a> .</span><span class="sxs-lookup"><span data-stu-id="81c03-130">Media configuration is set by using the <a href="https://docs.microsoft.com/powershell/module/skype/New-CsMediaConfiguration">New-CsMediaConfiguration</a> and <a href="https://docs.microsoft.com/powershell/module/skype/Set-CsMediaConfiguration">Set-CsMediaConfiguration</a> cmdlets.</span></span></p>
<p><span data-ttu-id="81c03-131">Допускаются следующие значения:</span><span class="sxs-lookup"><span data-stu-id="81c03-131">Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="81c03-132">Требуется: должно использоваться шифрование SRTP.</span><span class="sxs-lookup"><span data-stu-id="81c03-132">Required: SRTP encryption must be used.</span></span></p></li>
<li><p><span data-ttu-id="81c03-133">Необязательно: SRTP будет использоваться, если поддерживается шлюзом.</span><span class="sxs-lookup"><span data-stu-id="81c03-133">Optional: SRTP will be used if the gateway supports it.</span></span></p></li>
<li><p><span data-ttu-id="81c03-134">Не поддерживается: шифрование SRTP не поддерживается и поэтому не будет использоваться.</span><span class="sxs-lookup"><span data-stu-id="81c03-134">Not Supported: SRTP encryption is not supported and therefore will not be used.</span></span></p></li>
</ul>
<p><span data-ttu-id="81c03-p105">Параметр SRTPMode используется, только в случае, если шлюз настроен на использование протокола TLS. Если шлюз настроен на использование в качестве транспорта протокола TCP, для параметра SRTPMode внутренним образом задается значение Not Supported.</span><span class="sxs-lookup"><span data-stu-id="81c03-p105">SRTPMode is used only if the gateway is configured to use Transport Layer Security (TLS). If the gateway is configured with Transmission Control Protocol (TCP) as the transport, SRTPMode is internally set to Not Supported.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="81c03-137">Поддержка ссылки</span><span class="sxs-lookup"><span data-stu-id="81c03-137">Refer support</span></span></p></td>
<td><p><span data-ttu-id="81c03-138">Enable3pccRefer</span><span class="sxs-lookup"><span data-stu-id="81c03-138">Enable3pccRefer</span></span></p>
<p><span data-ttu-id="81c03-139">EnableReferSupport</span><span class="sxs-lookup"><span data-stu-id="81c03-139">EnableReferSupport</span></span></p></td>
<td><p><span data-ttu-id="81c03-140">Если задано <strong>Разрешить отправку ссылки шлюзу</strong>, это указывает на то, что магистральная линия связи поддерживает получение запросов ссылки от сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="81c03-140">If set to <strong>Enable sending refer to the gateway</strong>, indicates that the trunk supports receiving Refer requests from the Mediation Server.</span></span></p>
<p><span data-ttu-id="81c03-141">Если задано <strong>Разрешить ссылку с использованием стороннего контроля вызовов</strong>, это указывает на то, что протокол 3pcc может использоваться, чтобы разрешить переключенным звонкам обходить размещенный веб-сайт.</span><span class="sxs-lookup"><span data-stu-id="81c03-141">If set to <strong>Enable refer using third-party call control</strong>, indicates that the 3pcc protocol can be used to allow transferred calls to bypass the hosted site.</span></span> <span data-ttu-id="81c03-142">3pcc также называется &quot; сторонним элементом управления &quot; и возникает, когда третья сторона используется для подключения к абоненту почтовых абонентов (например, оператора, который помещает звонок от человека а к лицу б).</span><span class="sxs-lookup"><span data-stu-id="81c03-142">3pcc is also known as &quot;third party control,&quot; and occurs when a third-party is used to connect a pair of callers (for example, an operator placing a call from person A to person B).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="81c03-143">Разрешить обход мультимедиа</span><span class="sxs-lookup"><span data-stu-id="81c03-143">Enable media bypass</span></span></p></td>
<td><p><span data-ttu-id="81c03-144">Enablebypass задано</span><span class="sxs-lookup"><span data-stu-id="81c03-144">EnableBypass</span></span></p></td>
<td><p><span data-ttu-id="81c03-p107">Указывает, включен обход медиаданных для этой магистральной линии связи. Обход медиаданных может быть включен только в случае, если также включен параметр <strong>Централизованная обработка мультимедиа</strong>.</span><span class="sxs-lookup"><span data-stu-id="81c03-p107">Indicates whether media bypass is enabled for this trunk. Media bypass can only be enabled if <strong>Centralized media processing</strong> is also enabled.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="81c03-147">Централизованная обработка мультимедиа</span><span class="sxs-lookup"><span data-stu-id="81c03-147">Centralized media processing</span></span></p></td>
<td><p><span data-ttu-id="81c03-148">Concentratedtopology задано</span><span class="sxs-lookup"><span data-stu-id="81c03-148">ConcentratedTopology</span></span></p></td>
<td><p><span data-ttu-id="81c03-p108">Enable RTP latching имеется ли известная точка терминирования медиаданных. (Примером известной точки терминирования медиаданных может являться шлюз ТСОП, где у точки терминирования медиаданных такой же IP-адрес, что и у точки терминирования сигналов.)</span><span class="sxs-lookup"><span data-stu-id="81c03-p108">Indicates whether there is a well-known media termination point. (An example of a well-known media termination point would be a PSTN gateway where the media termination has the same IP as the signaling termination.)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="81c03-151">Разрешить блокирование RTP</span><span class="sxs-lookup"><span data-stu-id="81c03-151">Enable RTP latching</span></span></p></td>
<td><p><span data-ttu-id="81c03-152">енаблертплатчинг</span><span class="sxs-lookup"><span data-stu-id="81c03-152">EnableRTPLatching</span></span></p></td>
<td><p><span data-ttu-id="81c03-p109">Указывает, поддерживают ли магистральные линии связи SIP блокирование RTP. Блокирование RTP является технологией, позволяющей выполнять подключение по протоколу RTP/RTCP через устройство NAT (преобразование сетевых адресов) или брандмауэр.</span><span class="sxs-lookup"><span data-stu-id="81c03-p109">Indicates whether or not the SIP trunks support RTP latching. RTP latching is a technology that enables RTP/RTCP connectivity through a NAT (network address translator) device or firewall.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="81c03-155">Включить журнал переадресации звонков</span><span class="sxs-lookup"><span data-stu-id="81c03-155">Enable forward call history</span></span></p></td>
<td><p><span data-ttu-id="81c03-156">форвардкаллхистори</span><span class="sxs-lookup"><span data-stu-id="81c03-156">ForwardCallHistory</span></span></p></td>
<td><p><span data-ttu-id="81c03-157">Означает, будет ли переадресовываться по магистральному каналу сведения о журнале звонков.</span><span class="sxs-lookup"><span data-stu-id="81c03-157">Indicates whether call history information will be forwarded through the trunk.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="81c03-158">Включить данные переадресации P-Asserted-Identity</span><span class="sxs-lookup"><span data-stu-id="81c03-158">Enable forward P-Asserted-Identity data</span></span></p></td>
<td><p><span data-ttu-id="81c03-159">форвардпаи</span><span class="sxs-lookup"><span data-stu-id="81c03-159">ForwardPAI</span></span></p></td>
<td><p><span data-ttu-id="81c03-p110">Указывает, будет ли переадресовываться заголовок P-Asserted-Identity (PAI) одновременно с вызовом. Заголовок PAI предоставляет способ проверки удостоверения абонемента.</span><span class="sxs-lookup"><span data-stu-id="81c03-p110">Indicates whether the P-Asserted-Identity (PAI) header will be forwarded along with the call. The PAI header provides a way to verify the identity of the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="81c03-162">Включить таймер отработки отказа внешней маршрутизации</span><span class="sxs-lookup"><span data-stu-id="81c03-162">Enable outbound routing failover timer</span></span></p></td>
<td><p><span data-ttu-id="81c03-163">енаблефастфаиловертимер</span><span class="sxs-lookup"><span data-stu-id="81c03-163">EnableFastFailoverTimer</span></span></p></td>
<td><p><span data-ttu-id="81c03-p111">Указывает, будут ли вызовы, на которые не был получен ответ от шлюза в течение 10 секунд, маршрутизироваться следующей доступной магистральной линии связи; если дополнительная магистральная линия связи отсутствует, вызов будет автоматически пропущен. В организации с медленными ответами сетей и шлюзов, это может приводить к необязательному пропуску вызовов.</span><span class="sxs-lookup"><span data-stu-id="81c03-p111">Indicates whether outbound calls that are not answered by the gateway within 10 seconds will be routed to the next available trunk; if there are no additional trunks then the call will automatically be dropped. In an organization with slow networks and gateway responses, that could potentially result in calls being dropped unnecessarily.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="81c03-166">Связанные использования ТСОП</span><span class="sxs-lookup"><span data-stu-id="81c03-166">Associated PSTN usages</span></span></p></td>
<td><p><span data-ttu-id="81c03-167">PSTNUsages</span><span class="sxs-lookup"><span data-stu-id="81c03-167">PSTNUsages</span></span></p></td>
<td><p><span data-ttu-id="81c03-168">Коллекция режимов ТСОП, привязываемых к магистральному каналу.</span><span class="sxs-lookup"><span data-stu-id="81c03-168">Collection of PSTN usages assigned to the trunk.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="81c03-169">Преобразованный номер для проверки</span><span class="sxs-lookup"><span data-stu-id="81c03-169">Translated number to test</span></span></p></td>
<td><p><span data-ttu-id="81c03-170">Недоступно</span><span class="sxs-lookup"><span data-stu-id="81c03-170">N/A</span></span></p></td>
<td><p><span data-ttu-id="81c03-171">Телефонный номер, который может использоваться для выполнения специального теста настроек конфигурации магистрали.</span><span class="sxs-lookup"><span data-stu-id="81c03-171">Phone number that can be used to do an ad hoc test of the trunk configuration settings.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="81c03-172">Связанные правила преобразования</span><span class="sxs-lookup"><span data-stu-id="81c03-172">Associated translation rules</span></span></p></td>
<td><p><span data-ttu-id="81c03-173">аутбаундтранслатионрулеслист</span><span class="sxs-lookup"><span data-stu-id="81c03-173">OutboundTranslationRulesList</span></span></p></td>
<td><p><span data-ttu-id="81c03-174">Коллекция правил преобразования телефонных номеров, которые применяются к вызовам, обрабатываемым службой маршрутизации исходящих вызовов (вызовы, направляемые по конечным адресам УАТС или ТСОП).</span><span class="sxs-lookup"><span data-stu-id="81c03-174">Collection of phone number translation rules that apply to calls handled by Outbound Routing (calls routed to PBX or PSTN destinations).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="81c03-175">Правила преобразования вызываемого номера</span><span class="sxs-lookup"><span data-stu-id="81c03-175">Called number translation rules</span></span></p></td>
<td><p><span data-ttu-id="81c03-176">аутбаундкаллингнумбертранслатионрулеслист</span><span class="sxs-lookup"><span data-stu-id="81c03-176">OutboundCallingNumberTranslationRulesList</span></span></p></td>
<td><p><span data-ttu-id="81c03-177">Коллекция правил преобразования исходящих вызовов, привязываемая к магистральному каналу.</span><span class="sxs-lookup"><span data-stu-id="81c03-177">Collection of outbound calling number translation rules assigned to the trunk.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="81c03-178">Проверяемый номер телефона</span><span class="sxs-lookup"><span data-stu-id="81c03-178">Phone number to test</span></span></p></td>
<td><p><span data-ttu-id="81c03-179">Недоступно</span><span class="sxs-lookup"><span data-stu-id="81c03-179">N/A</span></span></p></td>
<td><p><span data-ttu-id="81c03-180">Номер телефона, который может использоваться для выполнения специального теста правил преобразования.</span><span class="sxs-lookup"><span data-stu-id="81c03-180">Phone number that can be used to do an ad hoc test of the translation rules.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="81c03-181">Номер вызывающего абонента</span><span class="sxs-lookup"><span data-stu-id="81c03-181">Calling number</span></span></p></td>
<td><p><span data-ttu-id="81c03-182">Недоступно</span><span class="sxs-lookup"><span data-stu-id="81c03-182">N/A</span></span></p></td>
<td><p><span data-ttu-id="81c03-183">Показывает, что проверяемый номер телефона является номером телефона вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="81c03-183">Indicates that the phone number to test is the phone number of the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="81c03-184">Вызываемый номер</span><span class="sxs-lookup"><span data-stu-id="81c03-184">Called number</span></span></p></td>
<td><p><span data-ttu-id="81c03-185">Недоступно</span><span class="sxs-lookup"><span data-stu-id="81c03-185">N/A</span></span></p></td>
<td><p><span data-ttu-id="81c03-186">Показывает, что проверяемый номер телефона является номером телефона вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="81c03-186">Indicates that the phone number to test is the phone number of the person being called.</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="81c03-187">Командлеты Lync Server CsTrunkConfiguration поддерживают дополнительные свойства, не отображаемые в панели управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="81c03-187">The Lync Server CsTrunkConfiguration cmdlets support additional properties not shown in Lync Server Control Panel.</span></span> <span data-ttu-id="81c03-188">Для получения дополнительных сведений обратитесь к разделу "Справка" для командлета <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsTrunkConfiguration">Set – CsTrunkConfiguration</A> .</span><span class="sxs-lookup"><span data-stu-id="81c03-188">For more information, see the help topic for the <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsTrunkConfiguration">Set-CsTrunkConfiguration</A> cmdlet.</span></span>



</div>

<div>

## <a name="to-modify-sip-trunk-configuration-settings-by-using-lync-server-control-panel"></a><span data-ttu-id="81c03-189">Изменение параметров конфигурации магистрали SIP с помощью панели управления Lync Server</span><span class="sxs-lookup"><span data-stu-id="81c03-189">To modify SIP trunk configuration settings by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="81c03-190">В панели управления Lync Server щелкните **Маршрутизация голосовой связи**, а затем щелкните **Настройка магистрали**.</span><span class="sxs-lookup"><span data-stu-id="81c03-190">In Lync Server Control Panel, click **Voice Routing**, and then click **Trunk Configuration**.</span></span>

2.  <span data-ttu-id="81c03-p113">На вкладке **Конфигурация магистрали** дважды щелкните параметры, которые нужно изменить. Обратите внимание, что можно изменить только одну коллекция настроек за раз. Если вы хотите изменить несколько коллекций, используйте Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="81c03-p113">On the **Trunk Configuration** tab, double-click the trunk configuration settings to be modified. Note that you can only edit one collection of settings at a time. If you would like to make the same changes on multiple collections, use Windows PowerShell instead.</span></span>

3.  <span data-ttu-id="81c03-194">В диалоговом окне **изменение конфигурации магистрали** сделайте соответствующий выбор и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="81c03-194">In the **Edit Trunk Configuration** dialog, make the appropriate selections and then click **OK**.</span></span>

4.  <span data-ttu-id="81c03-p114">Свойство **Состояние** для коллекции будет обновлено до **Незафиксированные**. Чтобы зафиксировать изменения и удалить коллекцию, щелкните **Сохранить**, а затем выберите **Сохранить все**.</span><span class="sxs-lookup"><span data-stu-id="81c03-p114">The **State** property for the collection will be updated to **Uncommitted**. To commit the changes, and to delete the collection, click **Commit** and then click **Commit All**.</span></span>

5.  <span data-ttu-id="81c03-197">В диалоговом окне **Несохраненные параметры настройки голосовой связи** нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="81c03-197">In the **Uncommitted Voice Configuration Settings** dialog box, click **OK**.</span></span>

6.  <span data-ttu-id="81c03-198">В диалоговом окне **Панель управления Microsoft Lync Server 2013** нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="81c03-198">In the **Microsoft Lync Server 2013 Control Panel** dialog box click **OK**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

