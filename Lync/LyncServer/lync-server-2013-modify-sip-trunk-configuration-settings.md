---
title: 'Lync Server 2013: изменение параметров конфигурации магистрали SIP'
description: 'Lync Server 2013: изменение параметров конфигурации магистрали SIP.'
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
ms.openlocfilehash: 42cb213211a11494a96b5a762734a2b5db49dfbb
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562145"
---
# <a name="modify-sip-trunk-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="5601f-103">Изменение параметров конфигурации магистрали SIP в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5601f-103">Modify SIP trunk configuration settings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5601f-104">_**Последнее изменение темы:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="5601f-104">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="5601f-p101">Параметры конфигурации линий связи SIP определяют возможности и связи между сервером-посредником и шлюзом телефонной сети общего пользования (ТСОП), IP-PBX или пограничным контроллером сеансов (SBC) на стороне поставщика услуг. Эти параметры позволяют определить:</span><span class="sxs-lookup"><span data-stu-id="5601f-p101">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the public switched telephone network (PSTN) gateway, an IP-public branch exchange (PBX), or a Session Border Controller (SBC) at the service provider. These settings do such things as specify:</span></span>

  - <span data-ttu-id="5601f-107">Следует ли включить обход медиаданных на линиях связи.</span><span class="sxs-lookup"><span data-stu-id="5601f-107">Whether media bypass should be enabled on the trunks.</span></span>

  - <span data-ttu-id="5601f-108">Условия, при которых передаются пакеты по протоколу RTCP.</span><span class="sxs-lookup"><span data-stu-id="5601f-108">The conditions under which real-time transport control protocol (RTCP) packets are sent.</span></span>

  - <span data-ttu-id="5601f-109">Требуется ли шифрование по протоколу SRTP на каждой магистрали.</span><span class="sxs-lookup"><span data-stu-id="5601f-109">Whether or not secure real-time protocol (SRTP) encryption is required on each trunk.</span></span>

<span data-ttu-id="5601f-110">При установке Microsoft Lync Server 2013 создается глобальная коллекция параметров конфигурации магистрали SIP.</span><span class="sxs-lookup"><span data-stu-id="5601f-110">When you install Microsoft Lync Server 2013, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="5601f-111">Кроме того, администраторы могут создать настраиваемые коллекции параметров в области узла или службы (только для службы шлюза ТСОП).</span><span class="sxs-lookup"><span data-stu-id="5601f-111">In addition, administrators can create custom setting collections at the site scope or at the service scope (for the PSTN gateway service, only).</span></span> <span data-ttu-id="5601f-112">Любую из этих коллекций позже можно будет изменить с помощью панели управления Lync Server или Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5601f-112">Any of these collections can later be modified using either Lync Server Control Panel or Windows PowerShell.</span></span>

<span data-ttu-id="5601f-113">При изменении параметров конфигурации магистрали SIP с помощью панели управления Lync Server доступны следующие варианты:</span><span class="sxs-lookup"><span data-stu-id="5601f-113">When modifying SIP trunk configuration settings using Lync Server Control Panel, the following options are available to you:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5601f-114">Параметр пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="5601f-114">UI Setting</span></span></th>
<th><span data-ttu-id="5601f-115">Параметр PowerShell</span><span class="sxs-lookup"><span data-stu-id="5601f-115">PowerShell Parameter</span></span></th>
<th><span data-ttu-id="5601f-116">Описание</span><span class="sxs-lookup"><span data-stu-id="5601f-116">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5601f-117">Имя</span><span class="sxs-lookup"><span data-stu-id="5601f-117">Name</span></span></p></td>
<td><p><span data-ttu-id="5601f-118">Удостоверение</span><span class="sxs-lookup"><span data-stu-id="5601f-118">Identity</span></span></p></td>
<td><p><span data-ttu-id="5601f-p103">Уникальный идентификатор для коллекции. Это свойство только для чтения; вы не можете изменить идентификатор коллекции параметров настройки магистральной линии связи.</span><span class="sxs-lookup"><span data-stu-id="5601f-p103">Unique identifier for the collection. This property is read-only; you cannot change the Identity of a collection of trunk configuration settings.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5601f-121">Описание</span><span class="sxs-lookup"><span data-stu-id="5601f-121">Description</span></span></p></td>
<td><p><span data-ttu-id="5601f-122">Описание</span><span class="sxs-lookup"><span data-stu-id="5601f-122">Description</span></span></p></td>
<td><p><span data-ttu-id="5601f-123">Предоставляет администраторам возможность сохранять дополнительную информацию о параметрах (например, сведения о цели настройки магистральной линии связи).</span><span class="sxs-lookup"><span data-stu-id="5601f-123">Provides a way for administrators to store addition information about the settings (for example, the purpose of the trunk configuration).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5601f-124">Максимальное количество поддерживаемых предварительных диалогов</span><span class="sxs-lookup"><span data-stu-id="5601f-124">Maximum early dialogs supported</span></span></p></td>
<td><p><span data-ttu-id="5601f-125">максеарлидиалогс</span><span class="sxs-lookup"><span data-stu-id="5601f-125">MaxEarlyDialogs</span></span></p></td>
<td><p><span data-ttu-id="5601f-126">Максимальное количество разветвляющихся ответов, которое шлюз ТСОП, IP-PBX или пограничный контроллер сеансов (SBC) на стороне поставщика службы может получить на приглашение, отправленное серверу-посреднику.</span><span class="sxs-lookup"><span data-stu-id="5601f-126">The maximum number of forked responses a PSTN gateway, IP-PBX, or SBC at the service provider can receive to an Invite that it sent to the Mediation Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5601f-127">Уровень поддержки шифрования</span><span class="sxs-lookup"><span data-stu-id="5601f-127">Encryption support level</span></span></p></td>
<td><p><span data-ttu-id="5601f-128">сртпмоде</span><span class="sxs-lookup"><span data-stu-id="5601f-128">SRTPMode</span></span></p></td>
<td><p><span data-ttu-id="5601f-129">Указывает уровень поддержки для защиты трафика медиаданных между сервером-посредником и шлюзом ТСОП, IP-PBX или пограничным контроллером сеансов на стороне поставщика службы.</span><span class="sxs-lookup"><span data-stu-id="5601f-129">Indicates the level of support for protecting media traffic between the Mediation Server and the PSTN Gateway, IP-PBX, or SBC at the service provider.</span></span> <span data-ttu-id="5601f-130">Для случаев обхода медиаданных это значение должно быть совместимо с параметром EncryptionLevel в настройке медиаданных.</span><span class="sxs-lookup"><span data-stu-id="5601f-130">For media bypass cases, this value must be compatible with the EncryptionLevel setting in the media configuration.</span></span> <span data-ttu-id="5601f-131">Конфигурация мультимедиа задается с помощью командлетов <a href="https://docs.microsoft.com/powershell/module/skype/New-CsMediaConfiguration">New-CsMediaConfiguration</a> и <a href="https://docs.microsoft.com/powershell/module/skype/Set-CsMediaConfiguration">Set-CsMediaConfiguration</a> .</span><span class="sxs-lookup"><span data-stu-id="5601f-131">Media configuration is set by using the <a href="https://docs.microsoft.com/powershell/module/skype/New-CsMediaConfiguration">New-CsMediaConfiguration</a> and <a href="https://docs.microsoft.com/powershell/module/skype/Set-CsMediaConfiguration">Set-CsMediaConfiguration</a> cmdlets.</span></span></p>
<p><span data-ttu-id="5601f-132">Допускаются следующие значения:</span><span class="sxs-lookup"><span data-stu-id="5601f-132">Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="5601f-133">Требуется: должно использоваться шифрование SRTP.</span><span class="sxs-lookup"><span data-stu-id="5601f-133">Required: SRTP encryption must be used.</span></span></p></li>
<li><p><span data-ttu-id="5601f-134">Необязательно: SRTP будет использоваться, если поддерживается шлюзом.</span><span class="sxs-lookup"><span data-stu-id="5601f-134">Optional: SRTP will be used if the gateway supports it.</span></span></p></li>
<li><p><span data-ttu-id="5601f-135">Не поддерживается: шифрование SRTP не поддерживается и поэтому не будет использоваться.</span><span class="sxs-lookup"><span data-stu-id="5601f-135">Not Supported: SRTP encryption is not supported and therefore will not be used.</span></span></p></li>
</ul>
<p><span data-ttu-id="5601f-p105">Параметр SRTPMode используется, только в случае, если шлюз настроен на использование протокола TLS. Если шлюз настроен на использование в качестве транспорта протокола TCP, для параметра SRTPMode внутренним образом задается значение Not Supported.</span><span class="sxs-lookup"><span data-stu-id="5601f-p105">SRTPMode is used only if the gateway is configured to use Transport Layer Security (TLS). If the gateway is configured with Transmission Control Protocol (TCP) as the transport, SRTPMode is internally set to Not Supported.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5601f-138">Поддержка ссылки</span><span class="sxs-lookup"><span data-stu-id="5601f-138">Refer support</span></span></p></td>
<td><p><span data-ttu-id="5601f-139">Enable3pccRefer</span><span class="sxs-lookup"><span data-stu-id="5601f-139">Enable3pccRefer</span></span></p>
<p><span data-ttu-id="5601f-140">EnableReferSupport</span><span class="sxs-lookup"><span data-stu-id="5601f-140">EnableReferSupport</span></span></p></td>
<td><p><span data-ttu-id="5601f-141">Если задано <strong>Разрешить отправку ссылки шлюзу</strong>, это указывает на то, что магистральная линия связи поддерживает получение запросов ссылки от сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="5601f-141">If set to <strong>Enable sending refer to the gateway</strong>, indicates that the trunk supports receiving Refer requests from the Mediation Server.</span></span></p>
<p><span data-ttu-id="5601f-142">Если задано <strong>Разрешить ссылку с использованием стороннего контроля вызовов</strong>, это указывает на то, что протокол 3pcc может использоваться, чтобы разрешить переключенным звонкам обходить размещенный веб-сайт.</span><span class="sxs-lookup"><span data-stu-id="5601f-142">If set to <strong>Enable refer using third-party call control</strong>, indicates that the 3pcc protocol can be used to allow transferred calls to bypass the hosted site.</span></span> <span data-ttu-id="5601f-143">3pcc также называется &quot; сторонним элементом управления &quot; и возникает, когда третья сторона используется для подключения к абоненту почтовых абонентов (например, оператора, который помещает звонок от человека а к лицу б).</span><span class="sxs-lookup"><span data-stu-id="5601f-143">3pcc is also known as &quot;third party control,&quot; and occurs when a third-party is used to connect a pair of callers (for example, an operator placing a call from person A to person B).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5601f-144">Разрешить обход мультимедиа</span><span class="sxs-lookup"><span data-stu-id="5601f-144">Enable media bypass</span></span></p></td>
<td><p><span data-ttu-id="5601f-145">Enablebypass задано</span><span class="sxs-lookup"><span data-stu-id="5601f-145">EnableBypass</span></span></p></td>
<td><p><span data-ttu-id="5601f-p107">Указывает, включен обход медиаданных для этой магистральной линии связи. Обход медиаданных может быть включен только в случае, если также включен параметр <strong>Централизованная обработка мультимедиа</strong>.</span><span class="sxs-lookup"><span data-stu-id="5601f-p107">Indicates whether media bypass is enabled for this trunk. Media bypass can only be enabled if <strong>Centralized media processing</strong> is also enabled.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5601f-148">Централизованная обработка мультимедиа</span><span class="sxs-lookup"><span data-stu-id="5601f-148">Centralized media processing</span></span></p></td>
<td><p><span data-ttu-id="5601f-149">Concentratedtopology задано</span><span class="sxs-lookup"><span data-stu-id="5601f-149">ConcentratedTopology</span></span></p></td>
<td><p><span data-ttu-id="5601f-p108">Enable RTP latching имеется ли известная точка терминирования медиаданных. (Примером известной точки терминирования медиаданных может являться шлюз ТСОП, где у точки терминирования медиаданных такой же IP-адрес, что и у точки терминирования сигналов.)</span><span class="sxs-lookup"><span data-stu-id="5601f-p108">Indicates whether there is a well-known media termination point. (An example of a well-known media termination point would be a PSTN gateway where the media termination has the same IP as the signaling termination.)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5601f-152">Разрешить блокирование RTP</span><span class="sxs-lookup"><span data-stu-id="5601f-152">Enable RTP latching</span></span></p></td>
<td><p><span data-ttu-id="5601f-153">енаблертплатчинг</span><span class="sxs-lookup"><span data-stu-id="5601f-153">EnableRTPLatching</span></span></p></td>
<td><p><span data-ttu-id="5601f-p109">Указывает, поддерживают ли магистральные линии связи SIP блокирование RTP. Блокирование RTP является технологией, позволяющей выполнять подключение по протоколу RTP/RTCP через устройство NAT (преобразование сетевых адресов) или брандмауэр.</span><span class="sxs-lookup"><span data-stu-id="5601f-p109">Indicates whether or not the SIP trunks support RTP latching. RTP latching is a technology that enables RTP/RTCP connectivity through a NAT (network address translator) device or firewall.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5601f-156">Включить журнал переадресации звонков</span><span class="sxs-lookup"><span data-stu-id="5601f-156">Enable forward call history</span></span></p></td>
<td><p><span data-ttu-id="5601f-157">форвардкаллхистори</span><span class="sxs-lookup"><span data-stu-id="5601f-157">ForwardCallHistory</span></span></p></td>
<td><p><span data-ttu-id="5601f-158">Означает, будет ли переадресовываться по магистральному каналу сведения о журнале звонков.</span><span class="sxs-lookup"><span data-stu-id="5601f-158">Indicates whether call history information will be forwarded through the trunk.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5601f-159">Включить данные переадресации P-Asserted-Identity</span><span class="sxs-lookup"><span data-stu-id="5601f-159">Enable forward P-Asserted-Identity data</span></span></p></td>
<td><p><span data-ttu-id="5601f-160">форвардпаи</span><span class="sxs-lookup"><span data-stu-id="5601f-160">ForwardPAI</span></span></p></td>
<td><p><span data-ttu-id="5601f-p110">Указывает, будет ли переадресовываться заголовок P-Asserted-Identity (PAI) одновременно с вызовом. Заголовок PAI предоставляет способ проверки удостоверения абонемента.</span><span class="sxs-lookup"><span data-stu-id="5601f-p110">Indicates whether the P-Asserted-Identity (PAI) header will be forwarded along with the call. The PAI header provides a way to verify the identity of the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5601f-163">Включить таймер отработки отказа внешней маршрутизации</span><span class="sxs-lookup"><span data-stu-id="5601f-163">Enable outbound routing failover timer</span></span></p></td>
<td><p><span data-ttu-id="5601f-164">енаблефастфаиловертимер</span><span class="sxs-lookup"><span data-stu-id="5601f-164">EnableFastFailoverTimer</span></span></p></td>
<td><p><span data-ttu-id="5601f-p111">Указывает, будут ли вызовы, на которые не был получен ответ от шлюза в течение 10 секунд, маршрутизироваться следующей доступной магистральной линии связи; если дополнительная магистральная линия связи отсутствует, вызов будет автоматически пропущен. В организации с медленными ответами сетей и шлюзов, это может приводить к необязательному пропуску вызовов.</span><span class="sxs-lookup"><span data-stu-id="5601f-p111">Indicates whether outbound calls that are not answered by the gateway within 10 seconds will be routed to the next available trunk; if there are no additional trunks then the call will automatically be dropped. In an organization with slow networks and gateway responses, that could potentially result in calls being dropped unnecessarily.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5601f-167">Связанные использования ТСОП</span><span class="sxs-lookup"><span data-stu-id="5601f-167">Associated PSTN usages</span></span></p></td>
<td><p><span data-ttu-id="5601f-168">PSTNUsages</span><span class="sxs-lookup"><span data-stu-id="5601f-168">PSTNUsages</span></span></p></td>
<td><p><span data-ttu-id="5601f-169">Коллекция режимов ТСОП, привязываемых к магистральному каналу.</span><span class="sxs-lookup"><span data-stu-id="5601f-169">Collection of PSTN usages assigned to the trunk.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5601f-170">Преобразованный номер для проверки</span><span class="sxs-lookup"><span data-stu-id="5601f-170">Translated number to test</span></span></p></td>
<td><p><span data-ttu-id="5601f-171">Недоступно</span><span class="sxs-lookup"><span data-stu-id="5601f-171">N/A</span></span></p></td>
<td><p><span data-ttu-id="5601f-172">Телефонный номер, который может использоваться для выполнения специального теста настроек конфигурации магистрали.</span><span class="sxs-lookup"><span data-stu-id="5601f-172">Phone number that can be used to do an ad hoc test of the trunk configuration settings.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5601f-173">Связанные правила преобразования</span><span class="sxs-lookup"><span data-stu-id="5601f-173">Associated translation rules</span></span></p></td>
<td><p><span data-ttu-id="5601f-174">аутбаундтранслатионрулеслист</span><span class="sxs-lookup"><span data-stu-id="5601f-174">OutboundTranslationRulesList</span></span></p></td>
<td><p><span data-ttu-id="5601f-175">Коллекция правил преобразования телефонных номеров, которые применяются к вызовам, обрабатываемым службой маршрутизации исходящих вызовов (вызовы, направляемые по конечным адресам УАТС или ТСОП).</span><span class="sxs-lookup"><span data-stu-id="5601f-175">Collection of phone number translation rules that apply to calls handled by Outbound Routing (calls routed to PBX or PSTN destinations).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5601f-176">Правила преобразования вызываемого номера</span><span class="sxs-lookup"><span data-stu-id="5601f-176">Called number translation rules</span></span></p></td>
<td><p><span data-ttu-id="5601f-177">аутбаундкаллингнумбертранслатионрулеслист</span><span class="sxs-lookup"><span data-stu-id="5601f-177">OutboundCallingNumberTranslationRulesList</span></span></p></td>
<td><p><span data-ttu-id="5601f-178">Коллекция правил преобразования исходящих вызовов, привязываемая к магистральному каналу.</span><span class="sxs-lookup"><span data-stu-id="5601f-178">Collection of outbound calling number translation rules assigned to the trunk.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5601f-179">Проверяемый номер телефона</span><span class="sxs-lookup"><span data-stu-id="5601f-179">Phone number to test</span></span></p></td>
<td><p><span data-ttu-id="5601f-180">Недоступно</span><span class="sxs-lookup"><span data-stu-id="5601f-180">N/A</span></span></p></td>
<td><p><span data-ttu-id="5601f-181">Номер телефона, который может использоваться для выполнения специального теста правил преобразования.</span><span class="sxs-lookup"><span data-stu-id="5601f-181">Phone number that can be used to do an ad hoc test of the translation rules.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5601f-182">Номер вызывающего абонента</span><span class="sxs-lookup"><span data-stu-id="5601f-182">Calling number</span></span></p></td>
<td><p><span data-ttu-id="5601f-183">Недоступно</span><span class="sxs-lookup"><span data-stu-id="5601f-183">N/A</span></span></p></td>
<td><p><span data-ttu-id="5601f-184">Показывает, что проверяемый номер телефона является номером телефона вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="5601f-184">Indicates that the phone number to test is the phone number of the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5601f-185">Вызываемый номер</span><span class="sxs-lookup"><span data-stu-id="5601f-185">Called number</span></span></p></td>
<td><p><span data-ttu-id="5601f-186">Недоступно</span><span class="sxs-lookup"><span data-stu-id="5601f-186">N/A</span></span></p></td>
<td><p><span data-ttu-id="5601f-187">Показывает, что проверяемый номер телефона является номером телефона вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="5601f-187">Indicates that the phone number to test is the phone number of the person being called.</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="5601f-188">Командлеты Lync Server CsTrunkConfiguration поддерживают дополнительные свойства, не отображаемые в панели управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5601f-188">The Lync Server CsTrunkConfiguration cmdlets support additional properties not shown in Lync Server Control Panel.</span></span> <span data-ttu-id="5601f-189">Для получения дополнительных сведений обратитесь к разделу "Справка" для командлета <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsTrunkConfiguration">Set – CsTrunkConfiguration</A> .</span><span class="sxs-lookup"><span data-stu-id="5601f-189">For more information, see the help topic for the <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsTrunkConfiguration">Set-CsTrunkConfiguration</A> cmdlet.</span></span>



</div>

<div>

## <a name="to-modify-sip-trunk-configuration-settings-by-using-lync-server-control-panel"></a><span data-ttu-id="5601f-190">Изменение параметров конфигурации магистрали SIP с помощью панели управления Lync Server</span><span class="sxs-lookup"><span data-stu-id="5601f-190">To modify SIP trunk configuration settings by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="5601f-191">В панели управления Lync Server щелкните **Маршрутизация голосовой связи**, а затем щелкните **Настройка магистрали**.</span><span class="sxs-lookup"><span data-stu-id="5601f-191">In Lync Server Control Panel, click **Voice Routing**, and then click **Trunk Configuration**.</span></span>

2.  <span data-ttu-id="5601f-p113">На вкладке **Конфигурация магистрали** дважды щелкните параметры, которые нужно изменить. Обратите внимание, что можно изменить только одну коллекция настроек за раз. Если вы хотите изменить несколько коллекций, используйте Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5601f-p113">On the **Trunk Configuration** tab, double-click the trunk configuration settings to be modified. Note that you can only edit one collection of settings at a time. If you would like to make the same changes on multiple collections, use Windows PowerShell instead.</span></span>

3.  <span data-ttu-id="5601f-195">В диалоговом окне **изменение конфигурации магистрали** сделайте соответствующий выбор и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="5601f-195">In the **Edit Trunk Configuration** dialog, make the appropriate selections and then click **OK**.</span></span>

4.  <span data-ttu-id="5601f-p114">Свойство **Состояние** для коллекции будет обновлено до **Незафиксированные**. Чтобы зафиксировать изменения и удалить коллекцию, щелкните **Сохранить**, а затем выберите **Сохранить все**.</span><span class="sxs-lookup"><span data-stu-id="5601f-p114">The **State** property for the collection will be updated to **Uncommitted**. To commit the changes, and to delete the collection, click **Commit** and then click **Commit All**.</span></span>

5.  <span data-ttu-id="5601f-198">В диалоговом окне **Несохраненные параметры настройки голосовой связи** нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="5601f-198">In the **Uncommitted Voice Configuration Settings** dialog box, click **OK**.</span></span>

6.  <span data-ttu-id="5601f-199">В диалоговом окне **Панель управления Microsoft Lync Server 2013** нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="5601f-199">In the **Microsoft Lync Server 2013 Control Panel** dialog box click **OK**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

