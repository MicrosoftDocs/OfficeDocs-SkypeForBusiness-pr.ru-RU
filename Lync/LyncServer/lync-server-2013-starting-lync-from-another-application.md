---
title: 'Lync Server 2013: запуск Lync из другого приложения'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Starting Lync from another application
ms:assetid: 573b30b1-6590-4b24-8e96-a41be57cb0ef
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398376(v=OCS.15)
ms:contentKeyID: 48184184
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 35e2d28a8083a7e7f1e693ddf55c5cfe3e758e96
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849617"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="starting-lync-from-another-application"></a><span data-ttu-id="4d41d-102">Запуск Lync из другого приложения</span><span class="sxs-lookup"><span data-stu-id="4d41d-102">Starting Lync from another application</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4d41d-103">_**Тема последнего изменения:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="4d41d-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="4d41d-104">Вы можете использовать параметры командной строки для быстрого запуска Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="4d41d-104">You can use command-line parameters to quick-start Lync 2013.</span></span> <span data-ttu-id="4d41d-105">Например, если пользователь щелкает номер телефона в другом приложении, приложение может запустить экземпляр Lync 2013 и инициировать Звонок на этот номер.</span><span class="sxs-lookup"><span data-stu-id="4d41d-105">For example, if a user clicks a phone number in another application, the application can start an instance of Lync 2013 and initiate a call to that number.</span></span>

<span data-ttu-id="4d41d-106">Lync 2013 также может распознать список имен контактов, разделенных точкой с запятой, для односторонних конференций.</span><span class="sxs-lookup"><span data-stu-id="4d41d-106">Lync 2013 can also recognize a semicolon-delimited list of contact names for multiparty conferencing.</span></span>

<span data-ttu-id="4d41d-107">Если Lync 2013 настроен на автоматический вход при запуске, то при запуске Lync 2013 с параметрами командной строки откроется главное окно Lync.</span><span class="sxs-lookup"><span data-stu-id="4d41d-107">If Lync 2013 is configured to automatically sign in when started, then starting Lync 2013 with command-line parameters will open the Lync main window.</span></span> <span data-ttu-id="4d41d-108">Если Lync не настроен для автоматического входа при запуске, откроется окно входа.</span><span class="sxs-lookup"><span data-stu-id="4d41d-108">If Lync is not configured to automatically sign in when started, the sign-in window opens.</span></span>

<span data-ttu-id="4d41d-109">В приведенной ниже таблице показаны доступные параметры.</span><span class="sxs-lookup"><span data-stu-id="4d41d-109">The following table shows the available parameters.</span></span>

### <a name="lync-2013-command-line-parameters"></a><span data-ttu-id="4d41d-110">Параметры командной строки Lync 2013</span><span class="sxs-lookup"><span data-stu-id="4d41d-110">Lync 2013 Command-Line Parameters</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4d41d-111">Добавоч</span><span class="sxs-lookup"><span data-stu-id="4d41d-111">Extension</span></span></th>
<th><span data-ttu-id="4d41d-112">Формат данных</span><span class="sxs-lookup"><span data-stu-id="4d41d-112">Format of Data</span></span></th>
<th><span data-ttu-id="4d41d-113">Действие</span><span class="sxs-lookup"><span data-stu-id="4d41d-113">Action</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4d41d-114">Tel</span><span class="sxs-lookup"><span data-stu-id="4d41d-114">tel:</span></span></p></td>
<td><p><span data-ttu-id="4d41d-115">универсальный код ресурса (URI) Tel</span><span class="sxs-lookup"><span data-stu-id="4d41d-115">tel URI</span></span></p></td>
<td><p><span data-ttu-id="4d41d-116">Открытие окна беседы для голосовой связи, но не набирает указанный номер.</span><span class="sxs-lookup"><span data-stu-id="4d41d-116">Opens the Conversation window for an audio call but does not dial the specified number.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4d41d-117">тегом "callto</span><span class="sxs-lookup"><span data-stu-id="4d41d-117">callto:</span></span></p></td>
<td><p><span data-ttu-id="4d41d-118">URI TEL:, SIP: или Type Tel</span><span class="sxs-lookup"><span data-stu-id="4d41d-118">tel:, sip:, or typeable tel URI</span></span></p></td>
<td><p><span data-ttu-id="4d41d-119">Открытие окна беседы для голосовой связи, но не набирает указанный номер.</span><span class="sxs-lookup"><span data-stu-id="4d41d-119">Opens the Conversation window for an audio call but does not dial the specified number.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4d41d-120">Установка</span><span class="sxs-lookup"><span data-stu-id="4d41d-120">sip:</span></span></p></td>
<td><p><span data-ttu-id="4d41d-121">Универсальный код ресурса SIP</span><span class="sxs-lookup"><span data-stu-id="4d41d-121">SIP URI</span></span></p></td>
<td><p><span data-ttu-id="4d41d-122">Открытие окна беседы с указанным универсальным кодом ресурса (URI) SIP в списке участников.</span><span class="sxs-lookup"><span data-stu-id="4d41d-122">Opens the Conversation window with the specified SIP Uniform Resource Identifier (URI) in the participant list.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4d41d-123">Протоколов</span><span class="sxs-lookup"><span data-stu-id="4d41d-123">Sips:</span></span></p></td>
<td><p><span data-ttu-id="4d41d-124">Универсальный код ресурса SIP</span><span class="sxs-lookup"><span data-stu-id="4d41d-124">SIP URI</span></span></p></td>
<td><p><span data-ttu-id="4d41d-125">Если Lync 2013 настроен на использование протокола TLS, функция работает точно так же, как SIP:.</span><span class="sxs-lookup"><span data-stu-id="4d41d-125">If Lync 2013 is configured to use the Transport Layer Security (TLS) protocol, functions exactly like sip:.</span></span> <span data-ttu-id="4d41d-126">Если TLS не используется, откроется диалоговое окно с уведомлением о том, что требуется более высокий уровень безопасности.</span><span class="sxs-lookup"><span data-stu-id="4d41d-126">If TLS is not being used, displays a dialog box informing the user that a higher level of security is required.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4d41d-127">CONF</span><span class="sxs-lookup"><span data-stu-id="4d41d-127">conf:</span></span></p></td>
<td><p><span data-ttu-id="4d41d-128">Универсальный код ресурса (URI) для присоединения к Конференции</span><span class="sxs-lookup"><span data-stu-id="4d41d-128">SIP URI of conference to join</span></span></p></td>
<td><p><span data-ttu-id="4d41d-129">Если URI является самосозданием, он создает фокус и выводит представление только для списка.</span><span class="sxs-lookup"><span data-stu-id="4d41d-129">If URI is self, instantiates the focus and brings up roster-only view.</span></span> <span data-ttu-id="4d41d-130">В противном случае выводится представление списка, но приглашение не отправляется.</span><span class="sxs-lookup"><span data-stu-id="4d41d-130">Otherwise, brings up roster view but does not send INVITE.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4d41d-131">бесед</span><span class="sxs-lookup"><span data-stu-id="4d41d-131">im:</span></span></p></td>
<td><p><span data-ttu-id="4d41d-132">Универсальный код ресурса SIP</span><span class="sxs-lookup"><span data-stu-id="4d41d-132">SIP URI</span></span></p></td>
<td><p><span data-ttu-id="4d41d-133">Отображается окно беседы с помощью URI SIP (только для обмена мгновенными сообщениями).</span><span class="sxs-lookup"><span data-stu-id="4d41d-133">Displays an instant messaging (IM)-only Conversation window with the SIP URI.</span></span> <span data-ttu-id="4d41d-134">Принимает несколько URI SIP, указанных в угловых&lt;&gt;скобках () без разделителя.</span><span class="sxs-lookup"><span data-stu-id="4d41d-134">Accepts multiple SIP URIs specified inside angle brackets (&lt;&gt;) without any separator.</span></span></p>
<pre><code>im:&lt;sip:user1@host&gt;&lt;sip:user2@host&gt;</code></pre></td>
</tr>
</tbody>
</table>


<span data-ttu-id="4d41d-135">В таблице ниже приведены примеры этих параметров командной строки.</span><span class="sxs-lookup"><span data-stu-id="4d41d-135">The following table provides examples of these command-line parameters.</span></span>

### <a name="command-line-parameter-examples"></a><span data-ttu-id="4d41d-136">Примеры параметров командной строки</span><span class="sxs-lookup"><span data-stu-id="4d41d-136">Command-Line Parameter Examples</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4d41d-137">Примеру</span><span class="sxs-lookup"><span data-stu-id="4d41d-137">Instance</span></span></th>
<th><span data-ttu-id="4d41d-138">Поиска</span><span class="sxs-lookup"><span data-stu-id="4d41d-138">Results</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4d41d-139">Tel: + 14255550101</span><span class="sxs-lookup"><span data-stu-id="4d41d-139">Tel:+14255550101</span></span></p></td>
<td><p><span data-ttu-id="4d41d-140">Открытие представления "только для телефона" с + 14255550101.</span><span class="sxs-lookup"><span data-stu-id="4d41d-140">Opens a phone-only view with +14255550101.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4d41d-141">Тегом "callto: Tel: + 14255550101</span><span class="sxs-lookup"><span data-stu-id="4d41d-141">Callto:tel:+ 14255550101</span></span></p></td>
<td><p><span data-ttu-id="4d41d-142">Открытие представления "только для телефона" с + 14255550101.</span><span class="sxs-lookup"><span data-stu-id="4d41d-142">Opens a phone-only view with +14255550101.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4d41d-143">Callto:sip:kazuto@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="4d41d-143">Callto:sip:kazuto@litwareinc.com</span></span></p></td>
<td><p><span data-ttu-id="4d41d-144">Открытие представления "только для телефона" с kazuto@litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="4d41d-144">Opens a phone-only view with kazuto@litwareinc.com.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4d41d-145">sip:kazuto@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="4d41d-145">sip:kazuto@litwareinc.com</span></span></p></td>
<td><p><span data-ttu-id="4d41d-146">Открытие окна беседы с помощью kazuto@litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="4d41d-146">Opens a Conversation window with kazuto@litwareinc.com.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4d41d-147">conf: SIP:https://meet.contoso.com/kazuto/7322994</span><span class="sxs-lookup"><span data-stu-id="4d41d-147">conf:sip:https://meet.contoso.com/kazuto/7322994</span></span></p></td>
<td><p><span data-ttu-id="4d41d-148">Открытие окна беседы и отображение параметров присоединения к звуковому каналу собрания.</span><span class="sxs-lookup"><span data-stu-id="4d41d-148">Opens a Conversation window and displays meeting audio join options.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

