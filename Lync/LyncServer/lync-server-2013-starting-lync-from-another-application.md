---
title: 'Lync Server 2013: запуск Lync из другого приложения'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Starting Lync from another application
ms:assetid: 573b30b1-6590-4b24-8e96-a41be57cb0ef
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398376(v=OCS.15)
ms:contentKeyID: 48184184
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 40e049b2a8a88514b9236ee0172474a5252bfdb1
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42208315"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="starting-lync-from-another-application"></a><span data-ttu-id="fc6ac-102">Запуск Lync из другого приложения</span><span class="sxs-lookup"><span data-stu-id="fc6ac-102">Starting Lync from another application</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fc6ac-103">_**Последнее изменение темы:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="fc6ac-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="fc6ac-104">Вы можете использовать параметры командной строки для быстрого запуска Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="fc6ac-104">You can use command-line parameters to quick-start Lync 2013.</span></span> <span data-ttu-id="fc6ac-105">Например, если пользователь щелкает номер телефона в другом приложении, приложение может запустить экземпляр Lync 2013 и инициировать вызов этого номера.</span><span class="sxs-lookup"><span data-stu-id="fc6ac-105">For example, if a user clicks a phone number in another application, the application can start an instance of Lync 2013 and initiate a call to that number.</span></span>

<span data-ttu-id="fc6ac-106">Lync 2013 также может распознать список имен контактов, разделенных точкой с запятой, для конференц-связи с многоадресной связью.</span><span class="sxs-lookup"><span data-stu-id="fc6ac-106">Lync 2013 can also recognize a semicolon-delimited list of contact names for multiparty conferencing.</span></span>

<span data-ttu-id="fc6ac-107">Если Lync 2013 настроен на автоматический вход при запуске, то при запуске Lync 2013 с параметрами командной строки будет открыто главное окно Lync.</span><span class="sxs-lookup"><span data-stu-id="fc6ac-107">If Lync 2013 is configured to automatically sign in when started, then starting Lync 2013 with command-line parameters will open the Lync main window.</span></span> <span data-ttu-id="fc6ac-108">Если Lync не настроен на автоматический вход при запуске, откроется окно входа.</span><span class="sxs-lookup"><span data-stu-id="fc6ac-108">If Lync is not configured to automatically sign in when started, the sign-in window opens.</span></span>

<span data-ttu-id="fc6ac-109">В следующей таблице приведены доступные параметры.</span><span class="sxs-lookup"><span data-stu-id="fc6ac-109">The following table shows the available parameters.</span></span>

### <a name="lync-2013-command-line-parameters"></a><span data-ttu-id="fc6ac-110">Параметры командной строки Lync 2013</span><span class="sxs-lookup"><span data-stu-id="fc6ac-110">Lync 2013 Command-Line Parameters</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fc6ac-111">Расширение</span><span class="sxs-lookup"><span data-stu-id="fc6ac-111">Extension</span></span></th>
<th><span data-ttu-id="fc6ac-112">Формат данных</span><span class="sxs-lookup"><span data-stu-id="fc6ac-112">Format of Data</span></span></th>
<th><span data-ttu-id="fc6ac-113">Action</span><span class="sxs-lookup"><span data-stu-id="fc6ac-113">Action</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fc6ac-114">Tel</span><span class="sxs-lookup"><span data-stu-id="fc6ac-114">tel:</span></span></p></td>
<td><p><span data-ttu-id="fc6ac-115">универсальный код ресурса (URI) Tel</span><span class="sxs-lookup"><span data-stu-id="fc6ac-115">tel URI</span></span></p></td>
<td><p><span data-ttu-id="fc6ac-116">Открывает окно беседы для голосовой связи, но не набирает указанный номер.</span><span class="sxs-lookup"><span data-stu-id="fc6ac-116">Opens the Conversation window for an audio call but does not dial the specified number.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fc6ac-117">callto</span><span class="sxs-lookup"><span data-stu-id="fc6ac-117">callto:</span></span></p></td>
<td><p><span data-ttu-id="fc6ac-118">Tel:, SIP: или типизированный URI TEL</span><span class="sxs-lookup"><span data-stu-id="fc6ac-118">tel:, sip:, or typeable tel URI</span></span></p></td>
<td><p><span data-ttu-id="fc6ac-119">Открывает окно беседы для голосовой связи, но не набирает указанный номер.</span><span class="sxs-lookup"><span data-stu-id="fc6ac-119">Opens the Conversation window for an audio call but does not dial the specified number.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fc6ac-120">панели</span><span class="sxs-lookup"><span data-stu-id="fc6ac-120">sip:</span></span></p></td>
<td><p><span data-ttu-id="fc6ac-121">Универсальный код ресурса (URI) SIP</span><span class="sxs-lookup"><span data-stu-id="fc6ac-121">SIP URI</span></span></p></td>
<td><p><span data-ttu-id="fc6ac-122">Открывает окно беседы с указанным универсальным кодом ресурса (URI) SIP в списке участников.</span><span class="sxs-lookup"><span data-stu-id="fc6ac-122">Opens the Conversation window with the specified SIP Uniform Resource Identifier (URI) in the participant list.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fc6ac-123">Sips</span><span class="sxs-lookup"><span data-stu-id="fc6ac-123">Sips:</span></span></p></td>
<td><p><span data-ttu-id="fc6ac-124">Универсальный код ресурса (URI) SIP</span><span class="sxs-lookup"><span data-stu-id="fc6ac-124">SIP URI</span></span></p></td>
<td><p><span data-ttu-id="fc6ac-125">Если Lync 2013 настроен для использования протокола TLS, функционирует аналогично SIP:.</span><span class="sxs-lookup"><span data-stu-id="fc6ac-125">If Lync 2013 is configured to use the Transport Layer Security (TLS) protocol, functions exactly like sip:.</span></span> <span data-ttu-id="fc6ac-126">Если протокол TLS не используется, отображается диалоговое окно, которое информирует пользователя о том, что необходим более высокий уровень безопасности.</span><span class="sxs-lookup"><span data-stu-id="fc6ac-126">If TLS is not being used, displays a dialog box informing the user that a higher level of security is required.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fc6ac-127">дает</span><span class="sxs-lookup"><span data-stu-id="fc6ac-127">conf:</span></span></p></td>
<td><p><span data-ttu-id="fc6ac-128">Универсальный код ресурса (URI) SIP конференции для присоединения</span><span class="sxs-lookup"><span data-stu-id="fc6ac-128">SIP URI of conference to join</span></span></p></td>
<td><p><span data-ttu-id="fc6ac-129">Если URI является самостоятельным, он создает фокус и выводит представление только для списка.</span><span class="sxs-lookup"><span data-stu-id="fc6ac-129">If URI is self, instantiates the focus and brings up roster-only view.</span></span> <span data-ttu-id="fc6ac-130">В противном случае отображает представление списка, но не отправляет приглашение.</span><span class="sxs-lookup"><span data-stu-id="fc6ac-130">Otherwise, brings up roster view but does not send INVITE.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fc6ac-131">обмена мгновенными сообщениями</span><span class="sxs-lookup"><span data-stu-id="fc6ac-131">im:</span></span></p></td>
<td><p><span data-ttu-id="fc6ac-132">Универсальный код ресурса (URI) SIP</span><span class="sxs-lookup"><span data-stu-id="fc6ac-132">SIP URI</span></span></p></td>
<td><p><span data-ttu-id="fc6ac-133">Отображает окно беседы с URI SIP только для обмена мгновенными сообщениями.</span><span class="sxs-lookup"><span data-stu-id="fc6ac-133">Displays an instant messaging (IM)-only Conversation window with the SIP URI.</span></span> <span data-ttu-id="fc6ac-134">Принимает несколько URI SIP, указанных внутри угловых&lt;&gt;скобок () без разделителя.</span><span class="sxs-lookup"><span data-stu-id="fc6ac-134">Accepts multiple SIP URIs specified inside angle brackets (&lt;&gt;) without any separator.</span></span></p>
<pre><code>im:&lt;sip:user1@host&gt;&lt;sip:user2@host&gt;</code></pre></td>
</tr>
</tbody>
</table>


<span data-ttu-id="fc6ac-135">В следующей таблице приведены примеры этих параметров командной строки.</span><span class="sxs-lookup"><span data-stu-id="fc6ac-135">The following table provides examples of these command-line parameters.</span></span>

### <a name="command-line-parameter-examples"></a><span data-ttu-id="fc6ac-136">Примеры параметров командной строки</span><span class="sxs-lookup"><span data-stu-id="fc6ac-136">Command-Line Parameter Examples</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fc6ac-137">Экземпляр</span><span class="sxs-lookup"><span data-stu-id="fc6ac-137">Instance</span></span></th>
<th><span data-ttu-id="fc6ac-138">Результаты</span><span class="sxs-lookup"><span data-stu-id="fc6ac-138">Results</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fc6ac-139">Tel: + 14255550101</span><span class="sxs-lookup"><span data-stu-id="fc6ac-139">Tel:+14255550101</span></span></p></td>
<td><p><span data-ttu-id="fc6ac-140">Открывает представление "только телефон" с + 14255550101.</span><span class="sxs-lookup"><span data-stu-id="fc6ac-140">Opens a phone-only view with +14255550101.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fc6ac-141">Callto: Tel: + 14255550101</span><span class="sxs-lookup"><span data-stu-id="fc6ac-141">Callto:tel:+ 14255550101</span></span></p></td>
<td><p><span data-ttu-id="fc6ac-142">Открывает представление "только телефон" с + 14255550101.</span><span class="sxs-lookup"><span data-stu-id="fc6ac-142">Opens a phone-only view with +14255550101.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fc6ac-143">Callto:sip:kazuto@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="fc6ac-143">Callto:sip:kazuto@litwareinc.com</span></span></p></td>
<td><p><span data-ttu-id="fc6ac-144">Открывает только телефонное представление с kazuto@litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="fc6ac-144">Opens a phone-only view with kazuto@litwareinc.com.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fc6ac-145">sip:kazuto@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="fc6ac-145">sip:kazuto@litwareinc.com</span></span></p></td>
<td><p><span data-ttu-id="fc6ac-146">Открывает окно беседы с kazuto@litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="fc6ac-146">Opens a Conversation window with kazuto@litwareinc.com.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fc6ac-147">conf: SIP:https://meet.contoso.com/kazuto/7322994</span><span class="sxs-lookup"><span data-stu-id="fc6ac-147">conf:sip:https://meet.contoso.com/kazuto/7322994</span></span></p></td>
<td><p><span data-ttu-id="fc6ac-148">Открывает окно беседы и отображает варианты присоединения к собранию.</span><span class="sxs-lookup"><span data-stu-id="fc6ac-148">Opens a Conversation window and displays meeting audio join options.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

