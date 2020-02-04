---
title: 'Lync Server 2013: планирование простых URL-адресов'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for simple URLs
ms:assetid: 20e4f4b6-b7ff-4297-b00d-d1211ee800ac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398287(v=OCS.15)
ms:contentKeyID: 48183610
ms.date: 12/12/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 224ca0315aff2618500182398cfe792c9626b883
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41750469"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-simple-urls-in-lync-server-2013"></a><span data-ttu-id="72cad-102">Планирование простых URL-адресов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="72cad-102">Planning for simple URLs in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="72cad-103">_**Тема последнего изменения:** 2015-12-11_</span><span class="sxs-lookup"><span data-stu-id="72cad-103">_**Topic Last Modified:** 2015-12-11_</span></span>

<span data-ttu-id="72cad-104">Простые URL-адреса упрощают присоединение к собраниям пользователей и упрощают работу с администрированием Lync Server для администраторов.</span><span class="sxs-lookup"><span data-stu-id="72cad-104">Simple URLs make joining meetings easier for your users, and make getting to Lync Server administrative tools easier for your administrators.</span></span>

<span data-ttu-id="72cad-105">Lync Server поддерживает три простых URL-адреса:</span><span class="sxs-lookup"><span data-stu-id="72cad-105">Lync Server supports three simple URLs:</span></span>

  - <span data-ttu-id="72cad-106">" **Встреча** " используется в качестве базового URL-адреса для всех конференций на сайте или в Организации.</span><span class="sxs-lookup"><span data-stu-id="72cad-106">**Meet** is used as the base URL for all conferences in the site or organization.</span></span> <span data-ttu-id="72cad-107">Примером простого URL-адреса можно достичь https://meet.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="72cad-107">An example of a Meet simple URL is https://meet.contoso.com.</span></span> <span data-ttu-id="72cad-108">URL-адресом для определенного собрания может https://meet.contoso.com/быть *username*/7322994.</span><span class="sxs-lookup"><span data-stu-id="72cad-108">A URL for a particular meeting might be https://meet.contoso.com/*username*/7322994.</span></span>
    
    <span data-ttu-id="72cad-109">С помощью простого URL-адреса вы можете легко усвоеновать ссылки на собрания, а также легко и распространены.</span><span class="sxs-lookup"><span data-stu-id="72cad-109">With the Meet simple URL, links to join meetings are easy to comprehend, and easy to communicate and distribute.</span></span>

  - <span data-ttu-id="72cad-110">С помощью **телефонного подключения** можно получить доступ к веб-странице параметров конференций с телефонным подключением.</span><span class="sxs-lookup"><span data-stu-id="72cad-110">**Dial-in** enables access to the Dial-in Conferencing Settings webpage.</span></span> <span data-ttu-id="72cad-111">Эта страница отображает номера для телефонного подключения к конференции с доступными языками, сведениями о назначенных конференциях (т. е. о собраниях, не требующих планирования) и элементами управления DTMF в ходе конференции; поддерживается также управление личными идентификационными номерами (ПИН-кодами) и сведениями о назначенных конференциях.</span><span class="sxs-lookup"><span data-stu-id="72cad-111">This page displays conference dial-in numbers with their available languages, assigned conference information (that is, for meetings that do not need to be scheduled), and in-conference DTMF controls, and supports management of personal identification number (PIN) and assigned conferencing information.</span></span> <span data-ttu-id="72cad-112">Простой URL-адрес телефонного подключения включается во все приглашения на собрания. Таким образом пользователи, которые хотят подключиться к собранию по телефону, могут найти в нем необходимый номер телефона и ПИН-код.</span><span class="sxs-lookup"><span data-stu-id="72cad-112">The Dial-in simple URL is included in all meeting invitations so that users who want to dial in to the meeting can access the necessary phone number and PIN information.</span></span> <span data-ttu-id="72cad-113">Пример простого URL-адреса с телефонным подключением https://dialin.contoso.com:</span><span class="sxs-lookup"><span data-stu-id="72cad-113">An example of the Dial-in simple URL is https://dialin.contoso.com.</span></span>

  - <span data-ttu-id="72cad-114">**Администратор** обеспечивает быстрый доступ к панели управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="72cad-114">**Admin** enables quick access to the Lync Server Control Panel.</span></span> <span data-ttu-id="72cad-115">С любого компьютера в брандмауэре организации администратор может открыть панель управления Lync Server, введя простой URL-адрес администратора в браузере.</span><span class="sxs-lookup"><span data-stu-id="72cad-115">From any computer within your organization’s firewalls, an admin can open the Lync Server Control Panel by typing the Admin simple URL into a browser.</span></span> <span data-ttu-id="72cad-116">Этот URL-адрес используется внутри организации.</span><span class="sxs-lookup"><span data-stu-id="72cad-116">The Admin simple URL is internal to your organization.</span></span> <span data-ttu-id="72cad-117">Пример простого URL-адреса администратораhttps://admin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="72cad-117">An example of the Admin simple URL is https://admin.contoso.com</span></span>

<div>

## <a name="simple-url-scope"></a><span data-ttu-id="72cad-118">Простая область URL-адресов</span><span class="sxs-lookup"><span data-stu-id="72cad-118">Simple URL Scope</span></span>

<span data-ttu-id="72cad-119">Вы можете настроить для простых URL-адресов глобальную область или указать разные простые URL-адреса для каждого центрального сайта в Организации.</span><span class="sxs-lookup"><span data-stu-id="72cad-119">You can configure your simple URLs to have global scope, or you can specify different simple URLs for each central site in your organization.</span></span> <span data-ttu-id="72cad-120">Если указаны как простой URL-адрес глобальной области, так и простой URL-адрес области сайта, приоритет имеет простой URL-адрес.</span><span class="sxs-lookup"><span data-stu-id="72cad-120">If both a global scope simple URL and a site scope simple URL are specified, the site scope simple URL has precedence.</span></span>

<span data-ttu-id="72cad-121">В большинстве случаев рекомендуется задавать простые URL-адреса только на глобальном уровне, чтобы при переходе с одного сайта на другой не изменялся простой URL-адрес пользователя.</span><span class="sxs-lookup"><span data-stu-id="72cad-121">In most cases, we recommend that you set simple URLs only at the global level, so that a user’s Meet simple URL does not change if they move from one site to another.</span></span> <span data-ttu-id="72cad-122">Исключением являются организации, которым необходимо использовать разные номера телефонов для пользователей с телефонным подключением на разных сайтах.</span><span class="sxs-lookup"><span data-stu-id="72cad-122">The exception would be organizations that need to use different telephone numbers for dial-in users at different sites.</span></span> <span data-ttu-id="72cad-123">Обратите внимание, что если задать простой URL-адрес на уровне сайта (например, простой URL-адрес с телефонным подключением), необходимо также настроить для других простых URL-адресов на этом сайте, чтобы он также был установлен на уровне сайта.</span><span class="sxs-lookup"><span data-stu-id="72cad-123">Note that if you set one simple URL (such as the Dial-in simple URL) at a site to be a site-level simple URL, you must also set the other simple URLs at that site to be site-level as well.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="72cad-124">Если вы хотите использовать простые URL-адреса с областью действия сайта, пользователи не смогут перемещаться между интерфейсами переднего плана на разных сайтах, если они не переносят все запланированные собрания, так как простые URL-адреса собраний различаются для разных сайтов.</span><span class="sxs-lookup"><span data-stu-id="72cad-124">If you choose to use site scoped simple URLs, your users won't be able to move between Front-End pools in different sites without those users rescheduling all of their scheduled meetings as the meeting simple URLs are different between sites.</span></span> <span data-ttu-id="72cad-125">Сюда входят сценарии со сбоями, в которых пулы в связях резервного копирования находятся на разных сайтах.</span><span class="sxs-lookup"><span data-stu-id="72cad-125">This includes fail-over scenarios where pools in backup relationships are in separate sites.</span></span> <span data-ttu-id="72cad-126">Если вам нужно переключиться между сайтами, на которых развернуты простые URL-адреса с областью сайта, пользователи не смогут присоединиться к собраниям из-за области URL.</span><span class="sxs-lookup"><span data-stu-id="72cad-126">When you need to fail-over between sites where site scoped simple URLs are deployed, users won't be able to join their meetings because of the scope for URL.</span></span> <span data-ttu-id="72cad-127">Дополнительные сведения можно найти в <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsSimpleUrlConfiguration">статьях Get-кссимплеурлконфигуратион</A>.</span><span class="sxs-lookup"><span data-stu-id="72cad-127">For further information, check <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsSimpleUrlConfiguration">Get-CsSimpleUrlConfiguration</A>.</span></span>



</div>

<span data-ttu-id="72cad-128">Вы можете настроить глобальные простые URL-адреса в построителе топологии.</span><span class="sxs-lookup"><span data-stu-id="72cad-128">You can set global simple URLs in Topology Builder.</span></span> <span data-ttu-id="72cad-129">Чтобы установить простой URL-адрес на уровне сайта, необходимо использовать командлет Set-Кссимплеурлконфигуратион.</span><span class="sxs-lookup"><span data-stu-id="72cad-129">To set a simple URL at the site level, you must use the Set-CsSimpleURLConfiguration cmdlet.</span></span>

</div>

<div>

## <a name="naming-your-simple-urls"></a><span data-ttu-id="72cad-130">Присвоение имен простым URL-адресам</span><span class="sxs-lookup"><span data-stu-id="72cad-130">Naming Your Simple URLs</span></span>

<span data-ttu-id="72cad-131">Для именования простых URL-адресов рекомендуется использовать три варианта.</span><span class="sxs-lookup"><span data-stu-id="72cad-131">There are three recommended options for naming your simple URLs.</span></span> <span data-ttu-id="72cad-132">Выбор варианта влияет на способ настройки записей и сертификатов DNS, которые поддерживают простые URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="72cad-132">Which option you choose has implications for how you set up your DNS A records and certificates which support simple URLs.</span></span> <span data-ttu-id="72cad-133">В каждом параметре необходимо настроить один из них, чтобы он соответствовал простому URL-адресу для каждого домена SIP в Организации.</span><span class="sxs-lookup"><span data-stu-id="72cad-133">In each option, you must configure one Meet simple URL for each SIP domain in your organization.</span></span>

<span data-ttu-id="72cad-134">Вам всегда нужен только один простой URL-адрес во всей Организации для подключения к телефонной связи, и один для администратора, независимо от того, сколько доменов SIP у вас есть.</span><span class="sxs-lookup"><span data-stu-id="72cad-134">You always need just one simple URL in your whole organization for Dial-in, and one for Admin, no matter how many SIP domains you have.</span></span>

<span data-ttu-id="72cad-135">Подробные сведения о необходимых записях и сертификатах DNS можно найти [в разделе Требования к DNS для простых URL-адресов в Lync server 2013](lync-server-2013-dns-requirements-for-simple-urls.md) и [требования к сертификатам для внутренних серверов в Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="72cad-135">For details about the necessary DNS A records and certificates, see [DNS requirements for simple URLs in Lync Server 2013](lync-server-2013-dns-requirements-for-simple-urls.md) and [Certificate requirements for internal servers in Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md) in the Planning documentation.</span></span>

<span data-ttu-id="72cad-136">В варианте 1 вы создаете новое доменное имя SIP для каждого простого URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="72cad-136">In Option 1, you create a new SIP domain name for each simple URL.</span></span>

<span data-ttu-id="72cad-137">При использовании этого параметра вам понадобится отдельная запись DNS A для каждого простого URL-адреса, и каждый такой простой URL-адрес должен называться в своих сертификатах.</span><span class="sxs-lookup"><span data-stu-id="72cad-137">If you use this option, you need a separate DNS A record for each simple URL, and each Meet simple URL must be named in your certificates.</span></span>

### <a name="simple-url-naming-option-1"></a><span data-ttu-id="72cad-138">Простой параметр именования URL-адресов 1</span><span class="sxs-lookup"><span data-stu-id="72cad-138">Simple URL Naming Option 1</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="72cad-139"><strong>Простой URL-адрес</strong></span><span class="sxs-lookup"><span data-stu-id="72cad-139"><strong>Simple URL</strong></span></span></p></td>
<td><p><span data-ttu-id="72cad-140"><strong>Пример</strong></span><span class="sxs-lookup"><span data-stu-id="72cad-140"><strong>Example</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="72cad-141">Подходит</span><span class="sxs-lookup"><span data-stu-id="72cad-141">Meet</span></span></p></td>
<td><p><span data-ttu-id="72cad-142">https://meet.contoso.com, https://meet.fabrikam.comи т. д. (для каждого домена SIP в вашей организации)</span><span class="sxs-lookup"><span data-stu-id="72cad-142">https://meet.contoso.com, https://meet.fabrikam.com, and so on (one for each SIP domain in your organization)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="72cad-143">Телефонные подключения</span><span class="sxs-lookup"><span data-stu-id="72cad-143">Dial-in</span></span></p></td>
<td><p>https://dialin.contoso.com</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="72cad-144">RAS</span><span class="sxs-lookup"><span data-stu-id="72cad-144">Admin</span></span></p></td>
<td><p>https://admin.contoso.com</p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="72cad-145">В параметре 2 простые URL-адреса основываются на lync.contoso.com доменных имен.</span><span class="sxs-lookup"><span data-stu-id="72cad-145">With Option 2, simple URLs are based on the domain name lync.contoso.com.</span></span> <span data-ttu-id="72cad-146">Поэтому требуется только одна запись DNS A, включающая все три типа простых URL-адресов.</span><span class="sxs-lookup"><span data-stu-id="72cad-146">Therefore, you need only one DNS A record which enables all three types of simple URLs.</span></span> <span data-ttu-id="72cad-147">Эта запись DNS A ссылается на lync.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="72cad-147">This DNS A record references lync.contoso.com.</span></span> <span data-ttu-id="72cad-148">Кроме того, вам по-прежнему нужны отдельные записи DNS A для других доменов SIP в Организации.</span><span class="sxs-lookup"><span data-stu-id="72cad-148">Additionally, you still need separate DNS A records for other SIP domains in your organization.</span></span>

### <a name="simple-url-naming-option-2"></a><span data-ttu-id="72cad-149">Параметр именования простого URL-адреса 2</span><span class="sxs-lookup"><span data-stu-id="72cad-149">Simple URL Naming Option 2</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="72cad-150"><strong>Простой URL-адрес</strong></span><span class="sxs-lookup"><span data-stu-id="72cad-150"><strong>Simple URL</strong></span></span></p></td>
<td><p><span data-ttu-id="72cad-151"><strong>Пример</strong></span><span class="sxs-lookup"><span data-stu-id="72cad-151"><strong>Example</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="72cad-152">Подходит</span><span class="sxs-lookup"><span data-stu-id="72cad-152">Meet</span></span></p></td>
<td><p><span data-ttu-id="72cad-153">https://lync.contoso.com/Meet, https://lync.fabrikam.com/Meetи т. д. (для каждого домена SIP в вашей организации)</span><span class="sxs-lookup"><span data-stu-id="72cad-153">https://lync.contoso.com/Meet, https://lync.fabrikam.com/Meet, and so on (one for each SIP domain in your organization)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="72cad-154">Телефонные подключения</span><span class="sxs-lookup"><span data-stu-id="72cad-154">Dial-in</span></span></p></td>
<td><p>https://lync.contoso.com/Dialin</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="72cad-155">RAS</span><span class="sxs-lookup"><span data-stu-id="72cad-155">Admin</span></span></p></td>
<td><p>https://lync.contoso.com/Admin</p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="72cad-156">Вариант 3 полезен, если у вас много доменов SIP, и вы хотите, чтобы они выделяют простые URL-адреса, но хотели минимизировать требования к DNS-записям и сертификатам для этих простых URL-адресов.</span><span class="sxs-lookup"><span data-stu-id="72cad-156">Option 3 is most useful if you have many SIP domains, and you want them to have separate Meet simple URLs but want to minimize the DNS record and certificate requirements for these simple URLs.</span></span>

### <a name="simple-url-naming-option-3"></a><span data-ttu-id="72cad-157">Параметр именования простого URL-адреса 3</span><span class="sxs-lookup"><span data-stu-id="72cad-157">Simple URL Naming Option 3</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="72cad-158"><strong>Простой URL-адрес</strong></span><span class="sxs-lookup"><span data-stu-id="72cad-158"><strong>Simple URL</strong></span></span></p></td>
<td><p><span data-ttu-id="72cad-159"><strong>Пример</strong></span><span class="sxs-lookup"><span data-stu-id="72cad-159"><strong>Example</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="72cad-160">Подходит</span><span class="sxs-lookup"><span data-stu-id="72cad-160">Meet</span></span></p></td>
<td><p>https://lync.contoso.com/contosoSIPdomain/Meet</p>
<p>https://lync.contoso.com/fabrikamSIPdomain/Meet</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="72cad-161">Телефонные подключения</span><span class="sxs-lookup"><span data-stu-id="72cad-161">Dial-in</span></span></p></td>
<td><p>https://lync.contoso.com/Dialin</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="72cad-162">RAS</span><span class="sxs-lookup"><span data-stu-id="72cad-162">Admin</span></span></p></td>
<td><p>https://lync.contoso.com/Admin</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="simple-url-naming-and-validation-rules"></a><span data-ttu-id="72cad-163">Простые правила именования URL и проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="72cad-163">Simple URL Naming and Validation Rules</span></span>

<span data-ttu-id="72cad-164">В построителе топологии и командлетах командной консоли Lync Server используются некоторые правила проверки для простых URL-адресов.</span><span class="sxs-lookup"><span data-stu-id="72cad-164">Topology Builder and the Lync Server Management Shell cmdlets enforce several validation rules for your simple URLs.</span></span> <span data-ttu-id="72cad-165">Вы должны задать простые URL-адреса для "Встреча" и "набор номера", но задать для администратора необязательно.</span><span class="sxs-lookup"><span data-stu-id="72cad-165">You are required to set simple URLs for Meet and Dialin, but setting one for Admin is optional.</span></span> <span data-ttu-id="72cad-166">Каждому домену SIP должен соответствовать отдельный простой URL-адрес, но для всей Организации нужен только один простой URL-адрес для набора номера и один простой URL-адрес администратора.</span><span class="sxs-lookup"><span data-stu-id="72cad-166">Each SIP domain must have a separate Meet simple URL, but you need only one Dialin simple URL and one Admin simple URL for your whole organization.</span></span>

<span data-ttu-id="72cad-167">Каждый простой URL-адрес в вашей организации должен иметь уникальное имя и не может быть префиксом другого простого URL-адреса (например, не удалось установить lync.contoso.com/Meet в качестве простого URL-адреса и lync.contoso.com/Meet/Dialin в качестве простого URL-адреса для набора номера).</span><span class="sxs-lookup"><span data-stu-id="72cad-167">Each simple URL in your organization must have a unique name, and cannot be a prefix of another simple URL (for example, you could not set lync.contoso.com/Meet as your Meet simple URL and lync.contoso.com/Meet/Dialin as your Dialin simple URL).</span></span> <span data-ttu-id="72cad-168">Простые URL-имена не могут содержать полное доменное имя любого из ваших пулов или сведения о порте ( https://FQDN:88/meet например, не разрешены).</span><span class="sxs-lookup"><span data-stu-id="72cad-168">Simple URL names cannot contain the FQDN of any of your pools, or any port information (for example, https://FQDN:88/meet is not allowed).</span></span> <span data-ttu-id="72cad-169">Все простые URL-адреса должны начинаться с префикса https://.</span><span class="sxs-lookup"><span data-stu-id="72cad-169">All simple URLs must start with the https:// prefix.</span></span>

<span data-ttu-id="72cad-170">Простые URL-адреса могут состоять только из букв и цифр (a-z, A-Z, 0-9 и точки (.).</span><span class="sxs-lookup"><span data-stu-id="72cad-170">Simple URLs can contain only alphanumeric characters (that is, a-z, A-Z, 0-9, and the period (.).</span></span> <span data-ttu-id="72cad-171">Если вы используете другие символы, простые URL-адреса могут не работать должным образом.</span><span class="sxs-lookup"><span data-stu-id="72cad-171">If you use other characters, the simple URLs might not work as expected.</span></span>

</div>

<div>

## <a name="changing-simple-urls-after-deployment"></a><span data-ttu-id="72cad-172">Изменение простых URL-адресов после развертывания</span><span class="sxs-lookup"><span data-stu-id="72cad-172">Changing Simple URLs after Deployment</span></span>

<span data-ttu-id="72cad-173">При изменении простого URL-адреса после первоначального развертывания необходимо учитывать, как это изменение влияет на записи DNS и сертификаты для простых URL-адресов.</span><span class="sxs-lookup"><span data-stu-id="72cad-173">If you change a simple URL after initial deployment, you must be aware of how the change impacts your DNS records and certificates for simple URLs.</span></span> <span data-ttu-id="72cad-174">Если база простого URL-адреса изменяется, необходимо также изменить записи DNS и сертификаты.</span><span class="sxs-lookup"><span data-stu-id="72cad-174">If the base of a simple URL changes, then you must change the DNS records and certificates as well.</span></span> <span data-ttu-id="72cad-175">Например, https://lync.contoso.com/Meet чтобы https://meet.contoso.com изменить базовый URL-адрес с Lync.contoso.com на Meet.contoso.com, измените его, чтобы он ссылался на Meet.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="72cad-175">For example, changing from https://lync.contoso.com/Meet to https://meet.contoso.com changes the base URL from lync.contoso.com to meet.contoso.com, so you would need to change the DNS records and certificates to refer to meet.contoso.com.</span></span> <span data-ttu-id="72cad-176">Если вы изменили простой URL- https://lync.contoso.com/Meet адрес https://lync.contoso.com/Meetingsс "на", то основной URL-адрес Lync.contoso.com остается таким же, поэтому изменения DNS или сертификата не требуются.</span><span class="sxs-lookup"><span data-stu-id="72cad-176">If you changed the simple URL from https://lync.contoso.com/Meet to https://lync.contoso.com/Meetings, the base URL of lync.contoso.com stays the same, so no DNS or certificate changes are needed.</span></span>

<span data-ttu-id="72cad-177">Однако каждый раз, когда вы изменяете простое имя URL-адреса, вы должны выполнить команду **Enable-кскомпутер** для каждого директора и сервера переднего плана для регистрации изменения.</span><span class="sxs-lookup"><span data-stu-id="72cad-177">Whenever you change a simple URL name, however, you must run **Enable-CsComputer** on each Director and Front End Server to register the change.</span></span>

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="72cad-178">См. также</span><span class="sxs-lookup"><span data-stu-id="72cad-178">See Also</span></span>


[<span data-ttu-id="72cad-179">Требования DNS для простых URL-адресов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="72cad-179">DNS requirements for simple URLs in Lync Server 2013</span></span>](lync-server-2013-dns-requirements-for-simple-urls.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

