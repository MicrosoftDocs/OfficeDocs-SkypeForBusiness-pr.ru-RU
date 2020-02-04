---
title: 'Lync Server 2013: создание новой коллекции параметров конфигурации магистрали'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a new collection of trunk configuration settings
ms:assetid: 4ebd710c-38cd-4cff-9a45-df029d424580
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688054(v=OCS.15)
ms:contentKeyID: 49733647
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dc29d75fc90156516751ad53712b53f4848ab5bb
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740419"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-new-collection-of-trunk-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="a685b-102">Создание нового набора параметров конфигурации магистрали в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a685b-102">Create a new collection of trunk configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a685b-103">_**Тема последнего изменения:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="a685b-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="a685b-104">Параметры конфигурации магистральной магистрали SIP определяют связь и возможности между сервером-посредником и шлюзом коммутируемой телефонной сети (PSTN), Интернет-ПРОТОКОЛом (УАТС) или контроллером границ сеанса (SBC) в поставщике услуг.</span><span class="sxs-lookup"><span data-stu-id="a685b-104">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the public switched telephone network (PSTN) gateway, an IP-public branch exchange (PBX), or a Session Border Controller (SBC) at the service provider.</span></span> <span data-ttu-id="a685b-105">Эти параметры, в частности, определяют следующее:</span><span class="sxs-lookup"><span data-stu-id="a685b-105">These settings do such things as specify:</span></span>

  - <span data-ttu-id="a685b-106">следует включать ли обход сервера-посредника на магистралях;</span><span class="sxs-lookup"><span data-stu-id="a685b-106">Whether media bypass should be enabled on the trunks.</span></span>

  - <span data-ttu-id="a685b-107">Условия, при которых отправляются пакеты протокола управления транспортом в реальном времени (РТКП).</span><span class="sxs-lookup"><span data-stu-id="a685b-107">The conditions under which real-time transport control protocol (RTCP) packets are sent.</span></span>

  - <span data-ttu-id="a685b-108">Требуется ли шифрование на всех магистральах в режиме реального времени (SRTP).</span><span class="sxs-lookup"><span data-stu-id="a685b-108">Whether or not secure real-time protocol (SRTP) encryption is required on each trunk.</span></span>

<span data-ttu-id="a685b-109">При установке Microsoft Lync Server 2013 создается глобальная коллекция параметров конфигурации магистральной магистрали SIP.</span><span class="sxs-lookup"><span data-stu-id="a685b-109">When you install Microsoft Lync Server 2013, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="a685b-110">Кроме того, администраторы могут создавать пользовательские коллекции настроек на уровне сайта или службы (только для службы шлюза ТСОП).</span><span class="sxs-lookup"><span data-stu-id="a685b-110">In addition, administrators can create custom setting collections at the site scope or at the service scope (for the PSTN gateway service, only).</span></span>

<span data-ttu-id="a685b-111">При создании параметров конфигурации магистральной магистрали SIP с помощью панели управления Lync Server вы можете воспользоваться следующими параметрами:</span><span class="sxs-lookup"><span data-stu-id="a685b-111">When creating SIP trunk configuration settings using Lync Server Control Panel, the following options are available to you:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a685b-112">Параметр пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="a685b-112">UI Setting</span></span></th>
<th><span data-ttu-id="a685b-113">Параметр PowerShell</span><span class="sxs-lookup"><span data-stu-id="a685b-113">PowerShell Parameter</span></span></th>
<th><span data-ttu-id="a685b-114">Описание</span><span class="sxs-lookup"><span data-stu-id="a685b-114">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a685b-115">Имя</span><span class="sxs-lookup"><span data-stu-id="a685b-115">Name</span></span></p></td>
<td><p><span data-ttu-id="a685b-116">Identity</span><span class="sxs-lookup"><span data-stu-id="a685b-116">Identity</span></span></p></td>
<td><p><span data-ttu-id="a685b-p103">Уникальный идентификатор для коллекции. Это свойство только для чтения; вы не можете изменить идентификатор коллекции параметров настройки магистральной линии связи.</span><span class="sxs-lookup"><span data-stu-id="a685b-p103">Unique identifier for the collection. This property is read-only; you cannot change the Identity of a collection of trunk configuration settings.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a685b-119">Описание</span><span class="sxs-lookup"><span data-stu-id="a685b-119">Description</span></span></p></td>
<td><p><span data-ttu-id="a685b-120">Описание</span><span class="sxs-lookup"><span data-stu-id="a685b-120">Description</span></span></p></td>
<td><p><span data-ttu-id="a685b-121">Предоставляет администраторам возможность сохранять дополнительную информацию о параметрах (например, сведения о цели настройки магистральной линии связи).</span><span class="sxs-lookup"><span data-stu-id="a685b-121">Provides a way for administrators to store addition information about the settings (for example, the purpose of the trunk configuration).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a685b-122">Максимальное количество поддерживаемых предварительных диалогов</span><span class="sxs-lookup"><span data-stu-id="a685b-122">Maximum early dialogs supported</span></span></p></td>
<td><p><span data-ttu-id="a685b-123">MaxEarlyDialogs</span><span class="sxs-lookup"><span data-stu-id="a685b-123">MaxEarlyDialogs</span></span></p></td>
<td><p><span data-ttu-id="a685b-124">Максимальное количество разветвляющихся ответов, которое шлюз ТСОП, IP-PBX или пограничный контроллер сеансов (SBC) на стороне поставщика службы может получить на приглашение, отправленное серверу-посреднику.</span><span class="sxs-lookup"><span data-stu-id="a685b-124">The maximum number of forked responses a PSTN gateway, IP-PBX, or SBC at the service provider can receive to an Invite that it sent to the Mediation Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a685b-125">Уровень поддержки шифрования</span><span class="sxs-lookup"><span data-stu-id="a685b-125">Encryption support level</span></span></p></td>
<td><p><span data-ttu-id="a685b-126">SRTPMode</span><span class="sxs-lookup"><span data-stu-id="a685b-126">SRTPMode</span></span></p></td>
<td><p><span data-ttu-id="a685b-127">Указывает уровень поддержки для защиты трафика сервера-посредника между сервером-посредником и шлюзом ТСОП, IP-PBX или пограничным контроллером сеансов на стороне поставщика службы.</span><span class="sxs-lookup"><span data-stu-id="a685b-127">Indicates the level of support for protecting media traffic between the Mediation Server and the PSTN Gateway, IP-PBX, or SBC at the service provider.</span></span> <span data-ttu-id="a685b-128">Для случаев обхода сервера-посредника это значение должно быть совместимо с параметром EncryptionLevel в настройке сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="a685b-128">For media bypass cases, this value must be compatible with the EncryptionLevel setting in the media configuration.</span></span> <span data-ttu-id="a685b-129">Настройка мультимедиа задается с помощью командлетов <a href="https://docs.microsoft.com/powershell/module/skype/New-CsMediaConfiguration">New-ксмедиаконфигуратион</a> и <a href="https://docs.microsoft.com/powershell/module/skype/Set-CsMediaConfiguration">Set-ксмедиаконфигуратион</a> .</span><span class="sxs-lookup"><span data-stu-id="a685b-129">Media configuration is set by using the <a href="https://docs.microsoft.com/powershell/module/skype/New-CsMediaConfiguration">New-CsMediaConfiguration</a> and <a href="https://docs.microsoft.com/powershell/module/skype/Set-CsMediaConfiguration">Set-CsMediaConfiguration</a> cmdlets.</span></span></p>
<p><span data-ttu-id="a685b-130">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="a685b-130">Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="a685b-131">Требуется: должно использоваться шифрование SRTP.</span><span class="sxs-lookup"><span data-stu-id="a685b-131">Required: SRTP encryption must be used.</span></span></p></li>
<li><p><span data-ttu-id="a685b-132">Необязательно: SRTP будет использоваться, если поддерживается шлюзом.</span><span class="sxs-lookup"><span data-stu-id="a685b-132">Optional: SRTP will be used if the gateway supports it.</span></span></p></li>
<li><p><span data-ttu-id="a685b-133">Не поддерживается: шифрование SRTP не поддерживается и поэтому не будет использоваться.</span><span class="sxs-lookup"><span data-stu-id="a685b-133">Not Supported: SRTP encryption is not supported and therefore will not be used.</span></span></p></li>
</ul>
<p><span data-ttu-id="a685b-p105">Параметр SRTPMode используется, только в случае, если шлюз настроен на использование протокола TLS. Если шлюз настроен на использование в качестве транспорта протокола TCP, для параметра SRTPMode внутренним образом задается значение Not Supported.</span><span class="sxs-lookup"><span data-stu-id="a685b-p105">SRTPMode is used only if the gateway is configured to use Transport Layer Security (TLS). If the gateway is configured with Transmission Control Protocol (TCP) as the transport, SRTPMode is internally set to Not Supported.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a685b-136">Поддержка ссылки</span><span class="sxs-lookup"><span data-stu-id="a685b-136">Refer support</span></span></p></td>
<td><p><span data-ttu-id="a685b-137">Enable3pccRefer</span><span class="sxs-lookup"><span data-stu-id="a685b-137">Enable3pccRefer</span></span></p>
<p><span data-ttu-id="a685b-138">EnableReferSupport</span><span class="sxs-lookup"><span data-stu-id="a685b-138">EnableReferSupport</span></span></p></td>
<td><p><span data-ttu-id="a685b-139">Если задано <strong>Разрешить отправку ссылки шлюзу</strong>, это указывает на то, что магистральная линия связи поддерживает получение запросов ссылки от сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="a685b-139">If set to <strong>Enable sending refer to the gateway</strong>, indicates that the trunk supports receiving Refer requests from the Mediation Server.</span></span></p>
<p><span data-ttu-id="a685b-140">Если задано <strong>Разрешить ссылку с использованием стороннего контроля вызовов</strong>, это указывает на то, что протокол 3pcc может использоваться, чтобы разрешить переключенным звонкам обходить размещенный веб-сайт.</span><span class="sxs-lookup"><span data-stu-id="a685b-140">If set to <strong>Enable refer using third-party call control</strong>, indicates that the 3pcc protocol can be used to allow transferred calls to bypass the hosted site.</span></span> <span data-ttu-id="a685b-141">3pcc также называется &quot;третьим элементом управления и происходит&quot; , когда третья сторона используется для подключения к паре вызывающих абонентов (например, оператором, который помещает звонок от человека к человеку B).</span><span class="sxs-lookup"><span data-stu-id="a685b-141">3pcc is also known as &quot;third party control,&quot; and occurs when a third-party is used to connect a pair of callers (for example, an operator placing a call from person A to person B).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a685b-142">Разрешить обход сервера-посредника</span><span class="sxs-lookup"><span data-stu-id="a685b-142">Enable media bypass</span></span></p></td>
<td><p><span data-ttu-id="a685b-143">EnableBypass</span><span class="sxs-lookup"><span data-stu-id="a685b-143">EnableBypass</span></span></p></td>
<td><p><span data-ttu-id="a685b-p107">Указывает, включен обход сервера-посредника для этой магистральной линии связи. Обход сервера-посредника может быть включен только в случае, если также включен параметр <strong>Централизованная обработка мультимедиа</strong>.</span><span class="sxs-lookup"><span data-stu-id="a685b-p107">Indicates whether media bypass is enabled for this trunk. Media bypass can only be enabled if <strong>Centralized media processing</strong> is also enabled.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a685b-146">Централизованная обработка мультимедиа</span><span class="sxs-lookup"><span data-stu-id="a685b-146">Centralized media processing</span></span></p></td>
<td><p><span data-ttu-id="a685b-147">ConcentratedTopology</span><span class="sxs-lookup"><span data-stu-id="a685b-147">ConcentratedTopology</span></span></p></td>
<td><p><span data-ttu-id="a685b-p108">Enable RTP latching имеется ли известная точка терминирования медиаданных. (Примером известной точки терминирования медиаданных может являться шлюз ТСОП, где у точки терминирования медиаданных такой же IP-адрес, что и у точки терминирования сигналов.)</span><span class="sxs-lookup"><span data-stu-id="a685b-p108">Indicates whether there is a well-known media termination point. (An example of a well-known media termination point would be a PSTN gateway where the media termination has the same IP as the signaling termination.)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a685b-150">Разрешить блокирование RTP</span><span class="sxs-lookup"><span data-stu-id="a685b-150">Enable RTP latching</span></span></p></td>
<td><p><span data-ttu-id="a685b-151">EnableRTPLatching</span><span class="sxs-lookup"><span data-stu-id="a685b-151">EnableRTPLatching</span></span></p></td>
<td><p><span data-ttu-id="a685b-p109">Указывает, поддерживают ли магистральные линии связи SIP блокирование RTP. Блокирование RTP является технологией, позволяющей выполнять подключение по протоколу RTP/RTCP через устройство NAT (преобразование сетевых адресов) или брандмауэр.</span><span class="sxs-lookup"><span data-stu-id="a685b-p109">Indicates whether or not the SIP trunks support RTP latching. RTP latching is a technology that enables RTP/RTCP connectivity through a NAT (network address translator) device or firewall.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a685b-154">Включить журнал переадресации звонков</span><span class="sxs-lookup"><span data-stu-id="a685b-154">Enable forward call history</span></span></p></td>
<td><p><span data-ttu-id="a685b-155">ForwardCallHistory</span><span class="sxs-lookup"><span data-stu-id="a685b-155">ForwardCallHistory</span></span></p></td>
<td><p><span data-ttu-id="a685b-156">Означает, будет ли переадресовываться по магистральному каналу сведения о журнале звонков.</span><span class="sxs-lookup"><span data-stu-id="a685b-156">Indicates whether call history information will be forwarded through the trunk.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a685b-157">Включить данные переадресации P-Asserted-Identity</span><span class="sxs-lookup"><span data-stu-id="a685b-157">Enable forward P-Asserted-Identity data</span></span></p></td>
<td><p><span data-ttu-id="a685b-158">ForwardPAI</span><span class="sxs-lookup"><span data-stu-id="a685b-158">ForwardPAI</span></span></p></td>
<td><p><span data-ttu-id="a685b-p110">Указывает, будет ли переадресовываться заголовок P-Asserted-Identity (PAI) одновременно с вызовом. Заголовок PAI предоставляет способ проверки удостоверения абонемента.</span><span class="sxs-lookup"><span data-stu-id="a685b-p110">Indicates whether the P-Asserted-Identity (PAI) header will be forwarded along with the call. The PAI header provides a way to verify the identity of the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a685b-161">Включить таймер отработки отказа внешней маршрутизации</span><span class="sxs-lookup"><span data-stu-id="a685b-161">Enable outbound routing failover timer</span></span></p></td>
<td><p><span data-ttu-id="a685b-162">EnableFastFailoverTimer</span><span class="sxs-lookup"><span data-stu-id="a685b-162">EnableFastFailoverTimer</span></span></p></td>
<td><p><span data-ttu-id="a685b-p111">Указывает, будут ли вызовы, на которые не был получен ответ от шлюза в течение 10 секунд, маршрутизироваться следующей доступной магистральной линии связи; если дополнительная магистральная линия связи отсутствует, вызов будет автоматически пропущен. В организации с медленными ответами сетей и шлюзов, это может приводить к необязательному пропуску вызовов.</span><span class="sxs-lookup"><span data-stu-id="a685b-p111">Indicates whether outbound calls that are not answered by the gateway within 10 seconds will be routed to the next available trunk; if there are no additional trunks then the call will automatically be dropped. In an organization with slow networks and gateway responses, that could potentially result in calls being dropped unnecessarily.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a685b-165">Связанные использования ТСОП</span><span class="sxs-lookup"><span data-stu-id="a685b-165">Associated PSTN usages</span></span></p></td>
<td><p><span data-ttu-id="a685b-166">PSTNUsages</span><span class="sxs-lookup"><span data-stu-id="a685b-166">PSTNUsages</span></span></p></td>
<td><p><span data-ttu-id="a685b-167">Коллекция режимов PSTN, привязываемых к магистральному каналу.</span><span class="sxs-lookup"><span data-stu-id="a685b-167">Collection of PSTN usages assigned to the trunk.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a685b-168">Преобразованный номер для проверки</span><span class="sxs-lookup"><span data-stu-id="a685b-168">Translated number to test</span></span></p></td>
<td><p><span data-ttu-id="a685b-169">Н/Д</span><span class="sxs-lookup"><span data-stu-id="a685b-169">N/A</span></span></p></td>
<td><p><span data-ttu-id="a685b-170">Телефонный номер, который может использоваться для выполнения специального теста настроек конфигурации магистрали.</span><span class="sxs-lookup"><span data-stu-id="a685b-170">Phone number that can be used to do an ad hoc test of the trunk configuration settings.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a685b-171">Связанные правила преобразования</span><span class="sxs-lookup"><span data-stu-id="a685b-171">Associated translation rules</span></span></p></td>
<td><p><span data-ttu-id="a685b-172">OutboundTranslationRulesList</span><span class="sxs-lookup"><span data-stu-id="a685b-172">OutboundTranslationRulesList</span></span></p></td>
<td><p><span data-ttu-id="a685b-173">Коллекция правил преобразования телефонных номеров, которые применяются к вызовам, обрабатываемым службой маршрутизации исходящих вызовов (вызовы, направляемые по конечным адресам УАТС или ТСОП).</span><span class="sxs-lookup"><span data-stu-id="a685b-173">Collection of phone number translation rules that apply to calls handled by Outbound Routing (calls routed to PBX or PSTN destinations).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a685b-174">Правила преобразования вызываемого номера</span><span class="sxs-lookup"><span data-stu-id="a685b-174">Called number translation rules</span></span></p></td>
<td><p><span data-ttu-id="a685b-175">OutboundCallingNumberTranslationRulesList</span><span class="sxs-lookup"><span data-stu-id="a685b-175">OutboundCallingNumberTranslationRulesList</span></span></p></td>
<td><p><span data-ttu-id="a685b-176">Коллекция правил преобразования исходящих вызовов, привязываемая к магистральному каналу.</span><span class="sxs-lookup"><span data-stu-id="a685b-176">Collection of outbound calling number translation rules assigned to the trunk.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a685b-177">Проверяемый номер телефона</span><span class="sxs-lookup"><span data-stu-id="a685b-177">Phone number to test</span></span></p></td>
<td><p><span data-ttu-id="a685b-178">Н/Д</span><span class="sxs-lookup"><span data-stu-id="a685b-178">N/A</span></span></p></td>
<td><p><span data-ttu-id="a685b-179">Номер телефона, который может использоваться для выполнения специального теста правил преобразования.</span><span class="sxs-lookup"><span data-stu-id="a685b-179">Phone number that can be used to do an ad hoc test of the translation rules.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a685b-180">Номер вызывающего абонента</span><span class="sxs-lookup"><span data-stu-id="a685b-180">Calling number</span></span></p></td>
<td><p><span data-ttu-id="a685b-181">Н/Д</span><span class="sxs-lookup"><span data-stu-id="a685b-181">N/A</span></span></p></td>
<td><p><span data-ttu-id="a685b-182">Показывает, что проверяемый номер телефона является номером телефона вызывающего абонента.</span><span class="sxs-lookup"><span data-stu-id="a685b-182">Indicates that the phone number to test is the phone number of the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a685b-183">Вызываемый номер</span><span class="sxs-lookup"><span data-stu-id="a685b-183">Called number</span></span></p></td>
<td><p><span data-ttu-id="a685b-184">Н/Д</span><span class="sxs-lookup"><span data-stu-id="a685b-184">N/A</span></span></p></td>
<td><p><span data-ttu-id="a685b-185">Показывает, что проверяемый номер телефона является номером телефона вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="a685b-185">Indicates that the phone number to test is the phone number of the person being called.</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="a685b-186">Командлеты Lync Server CsTrunkConfiguration поддерживают дополнительные свойства, не отображаемые на панели управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a685b-186">The Lync Server CsTrunkConfiguration cmdlets support additional properties not shown in Lync Server Control Panel.</span></span> <span data-ttu-id="a685b-187">Дополнительные сведения можно найти в разделе справки по командлету <A href="https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration">New-CsTrunkConfiguration</A> .</span><span class="sxs-lookup"><span data-stu-id="a685b-187">For more information, see the help topic for the <A href="https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration">New-CsTrunkConfiguration</A> cmdlet.</span></span>



</div>

<div>

## <a name="to-create-new-trunk-configuration-settings-by-using-lync-server-control-panel"></a><span data-ttu-id="a685b-188">Создание новых параметров конфигурации канала с помощью панели управления Lync Server</span><span class="sxs-lookup"><span data-stu-id="a685b-188">To create new trunk configuration settings by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="a685b-189">На панели управления Lync Server нажмите кнопку **Маршрутизация голоса**и выберите пункт **Настройка магистрали**.</span><span class="sxs-lookup"><span data-stu-id="a685b-189">In Lync Server Control Panel, click **Voice Routing**, and then click **Trunk Configuration**.</span></span>

2.  <span data-ttu-id="a685b-190">На вкладке **Настройка линии связи** щелкните **Создать**, затем — **Магистральная линия связи сайта** для создания новых параметров на уровне сайта, или щелкните **Магистральная линия связи пула** для создания новых параметров на уровне службы.</span><span class="sxs-lookup"><span data-stu-id="a685b-190">On the **Trunk Configuration** tab, click **New**, and then click **Site trunk** to create the new settings at the site scope, or **Pool trunk** to create the new settings at the service scope.</span></span>

3.  <span data-ttu-id="a685b-p113">В диалоговом окне **Выбор сайта** или **Выбор службы** (отображаемое диалоговое окно зависит от того, определяются ли параметры на уровне сайта или на уровне службы) выберите местоположение новых параметров конфигурации, затем нажмите кнопку **ОК**. Пустое диалоговое окно означает, что нет места для создания новых параметров. Например, пустое диалоговое окно **Выбор сайта** означает, что всем сайтам уже была назначена коллекция сайтов конфигурации магистральной линии и каждый сайт (а также каждая служба) теперь может содержать одну подобную коллекцию. В этом случае можно или удалить существующую коллекцию и создать новую, или просто изменить существующую коллекцию.</span><span class="sxs-lookup"><span data-stu-id="a685b-p113">In the **Select a Site** or the **Select a Service** dialog box (the dialog box that appears will depend on whether you are creating site-scoped or service-scoped settings) select the location for the new configuration settings and then click **OK**. If the dialog box is blank, that means there is no place to create the new settings; for example, if the **Select a Site** dialog box is blank that means that all of your sites have already been assigned a collection of trunk configuration sites, and each site (and each service) can only host one such collection. In that case, you can either delete the existing collection and create a new collection, or simply modify the existing collection.</span></span>

4.  <span data-ttu-id="a685b-194">В диалоговом окне **Новая конфигурация магистральной линии** внесите необходимые изменения и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="a685b-194">In the **New Trunk Configuration** dialog, make the appropriate selections and then click **OK**.</span></span>

5.  <span data-ttu-id="a685b-p114">Свойство **Состояние** для коллекции будет обновлено до **Незафиксированные**. Чтобы зафиксировать изменения и удалить коллекцию, щелкните **Сохранить**, а затем выберите **Сохранить все**.</span><span class="sxs-lookup"><span data-stu-id="a685b-p114">The **State** property for the collection will be updated to **Uncommitted**. To commit the changes, and to delete the collection, click **Commit** and then click **Commit All**.</span></span>

6.  <span data-ttu-id="a685b-197">В диалоговом окне **Несохраненные параметры настройки голосовой связи** нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="a685b-197">In the **Uncommitted Voice Configuration Settings** dialog box, click **OK**.</span></span>

7.  <span data-ttu-id="a685b-198">В диалоговом окне " **Панель управления" Microsoft Lync Server 2013** нажмите кнопку " **ОК**".</span><span class="sxs-lookup"><span data-stu-id="a685b-198">In the **Microsoft Lync Server 2013 Control Panel** dialog box click **OK**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

