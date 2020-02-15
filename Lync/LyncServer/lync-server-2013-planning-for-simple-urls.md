---
title: 'Lync Server 2013: планирование для простых URL-адресов'
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
ms.openlocfilehash: d36e730aeef637c12102fbf425c04235d72eb382
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045201"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-simple-urls-in-lync-server-2013"></a><span data-ttu-id="b8f8e-102">Планирование простых URL-адресов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b8f8e-102">Planning for simple URLs in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b8f8e-103">_**Последнее изменение темы:** 2015-12-11_</span><span class="sxs-lookup"><span data-stu-id="b8f8e-103">_**Topic Last Modified:** 2015-12-11_</span></span>

<span data-ttu-id="b8f8e-104">Простые URL-адреса упрощают присоединение к собраниям для пользователей и упрощают работу средств администрирования Lync Server для администраторов.</span><span class="sxs-lookup"><span data-stu-id="b8f8e-104">Simple URLs make joining meetings easier for your users, and make getting to Lync Server administrative tools easier for your administrators.</span></span>

<span data-ttu-id="b8f8e-105">Lync Server поддерживает три простых URL-адреса:</span><span class="sxs-lookup"><span data-stu-id="b8f8e-105">Lync Server supports three simple URLs:</span></span>

  - <span data-ttu-id="b8f8e-106">URL-адрес **собраний** (meet) используется в качестве основного URL-адреса для всех конференций на сайте или в организации.</span><span class="sxs-lookup"><span data-stu-id="b8f8e-106">**Meet** is used as the base URL for all conferences in the site or organization.</span></span> <span data-ttu-id="b8f8e-107">Пример простого URL-адреса для удовлетворения https://meet.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="b8f8e-107">An example of a Meet simple URL is https://meet.contoso.com.</span></span> <span data-ttu-id="b8f8e-108">URL-адрес для определенного собрания может быть https://meet.contoso.com/равен *username*/7322994.</span><span class="sxs-lookup"><span data-stu-id="b8f8e-108">A URL for a particular meeting might be https://meet.contoso.com/*username*/7322994.</span></span>
    
    <span data-ttu-id="b8f8e-109">Простой URL-адрес собраний делает ссылки на присоединение к собраниям более понятными и удобными для обмена и распространения.</span><span class="sxs-lookup"><span data-stu-id="b8f8e-109">With the Meet simple URL, links to join meetings are easy to comprehend, and easy to communicate and distribute.</span></span>

  - <span data-ttu-id="b8f8e-110">С помощью **телефонного подключения** вы можете получить доступ к веб-странице параметров конференц-связи с телефонным подключением.</span><span class="sxs-lookup"><span data-stu-id="b8f8e-110">**Dial-in** enables access to the Dial-in Conferencing Settings webpage.</span></span> <span data-ttu-id="b8f8e-111">На этой странице отображаются номера конференц-связи с доступными языками, назначены сведения о конференциях (то есть для собраний, которые не нуждаются в планировании), а также входящие в систему управления DTMF и поддерживают управление персональным идентификационным номером ( ПИН-код) и назначенные сведения о конференциях.</span><span class="sxs-lookup"><span data-stu-id="b8f8e-111">This page displays conference dial-in numbers with their available languages, assigned conference information (that is, for meetings that do not need to be scheduled), and in-conference DTMF controls, and supports management of personal identification number (PIN) and assigned conferencing information.</span></span> <span data-ttu-id="b8f8e-112">Простой URL-адрес для телефонного подключения включается во все приглашения на собрания, чтобы пользователи, которые хотят звонить на собрание, могли получить доступ к требуемому номеру телефона и ПИН-код.</span><span class="sxs-lookup"><span data-stu-id="b8f8e-112">The Dial-in simple URL is included in all meeting invitations so that users who want to dial in to the meeting can access the necessary phone number and PIN information.</span></span> <span data-ttu-id="b8f8e-113">Пример простого URL-адреса для телефонного подключения: https://dialin.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="b8f8e-113">An example of the Dial-in simple URL is https://dialin.contoso.com.</span></span>

  - <span data-ttu-id="b8f8e-114">**Администратор** обеспечивает быстрый доступ к панели управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b8f8e-114">**Admin** enables quick access to the Lync Server Control Panel.</span></span> <span data-ttu-id="b8f8e-115">С любого компьютера, входящего в брандмауэры Организации, администратор может открыть панель управления Lync Server, введя простой URL-адрес администратора в браузере.</span><span class="sxs-lookup"><span data-stu-id="b8f8e-115">From any computer within your organization’s firewalls, an admin can open the Lync Server Control Panel by typing the Admin simple URL into a browser.</span></span> <span data-ttu-id="b8f8e-116">Этот URL-адрес используется внутри организации.</span><span class="sxs-lookup"><span data-stu-id="b8f8e-116">The Admin simple URL is internal to your organization.</span></span> <span data-ttu-id="b8f8e-117">Пример простого URL-адреса администратораhttps://admin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="b8f8e-117">An example of the Admin simple URL is https://admin.contoso.com</span></span>

<div>

## <a name="simple-url-scope"></a><span data-ttu-id="b8f8e-118">Область URL-адресов</span><span class="sxs-lookup"><span data-stu-id="b8f8e-118">Simple URL Scope</span></span>

<span data-ttu-id="b8f8e-119">Вы можете настроить для простых URL-адресов глобальную область действия или задать разные простые URL-адреса для каждого центрального узла в организации.</span><span class="sxs-lookup"><span data-stu-id="b8f8e-119">You can configure your simple URLs to have global scope, or you can specify different simple URLs for each central site in your organization.</span></span> <span data-ttu-id="b8f8e-120">Если указаны как простой URL-адрес глобальной области, так и простой URL-адрес области сайта, то простой URL-адрес области сайта имеет приоритет.</span><span class="sxs-lookup"><span data-stu-id="b8f8e-120">If both a global scope simple URL and a site scope simple URL are specified, the site scope simple URL has precedence.</span></span>

<span data-ttu-id="b8f8e-p105">В большинстве случаев мы рекомендуем задавать простые URL-адреса только на глобальном уровне, чтобы простой URL-адрес собрания пользователя не изменялся при перемещении из одного узла в другой. Исключением являются организации, в которых требуются различные номера телефонного подключения для пользователей в разных узлах. Обратите внимание на то, что если вы зададите один простой URL-адрес (например, простой URL-адрес телефонного подключения) в узле как простой URL-адрес на уровне узла, вам также нужно задать другие простые URL-адреса как адреса на уровне узла.</span><span class="sxs-lookup"><span data-stu-id="b8f8e-p105">In most cases, we recommend that you set simple URLs only at the global level, so that a user’s Meet simple URL does not change if they move from one site to another. The exception would be organizations that need to use different telephone numbers for dial-in users at different sites. Note that if you set one simple URL (such as the Dial-in simple URL) at a site to be a site-level simple URL, you must also set the other simple URLs at that site to be site-level as well.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b8f8e-124">Если вы решили использовать простые URL-адреса на уровне сайта, пользователи не смогут перемещаться между интерфейсными пулами на разных сайтах без необходимости перепланировать все запланированные собрания, так как простые URL-адреса собраний различаются для разных сайтов.</span><span class="sxs-lookup"><span data-stu-id="b8f8e-124">If you choose to use site scoped simple URLs, your users won't be able to move between Front-End pools in different sites without those users rescheduling all of their scheduled meetings as the meeting simple URLs are different between sites.</span></span> <span data-ttu-id="b8f8e-125">Сюда входят сценарии со отказом, в которых пулы в связях резервного копирования находятся на разных сайтах.</span><span class="sxs-lookup"><span data-stu-id="b8f8e-125">This includes fail-over scenarios where pools in backup relationships are in separate sites.</span></span> <span data-ttu-id="b8f8e-126">Если требуется отработка отказа между сайтами, на которых развернуты простые URL-адреса на уровне сайта, пользователи не смогут присоединиться к собраниям из-за области для URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="b8f8e-126">When you need to fail-over between sites where site scoped simple URLs are deployed, users won't be able to join their meetings because of the scope for URL.</span></span> <span data-ttu-id="b8f8e-127">Для получения дополнительных сведений проверьте <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsSimpleUrlConfiguration">Get – CsSimpleUrlConfiguration</A>.</span><span class="sxs-lookup"><span data-stu-id="b8f8e-127">For further information, check <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsSimpleUrlConfiguration">Get-CsSimpleUrlConfiguration</A>.</span></span>



</div>

<span data-ttu-id="b8f8e-128">Вы можете задать глобальные простые URL-адреса в построителе топологий.</span><span class="sxs-lookup"><span data-stu-id="b8f8e-128">You can set global simple URLs in Topology Builder.</span></span> <span data-ttu-id="b8f8e-129">Чтобы задать простой URL-адрес на уровне узла, воспользуйтесь командлетом Set-CsSimpleURLConfiguration.</span><span class="sxs-lookup"><span data-stu-id="b8f8e-129">To set a simple URL at the site level, you must use the Set-CsSimpleURLConfiguration cmdlet.</span></span>

</div>

<div>

## <a name="naming-your-simple-urls"></a><span data-ttu-id="b8f8e-130">Задание имен простых URL-адресов</span><span class="sxs-lookup"><span data-stu-id="b8f8e-130">Naming Your Simple URLs</span></span>

<span data-ttu-id="b8f8e-p108">Существует три рекомендованных способа задания имен простых URL-адресов. Выбираемый способ косвенно зависит от способа настройки записей A DNS и сертификатов для поддержки простых URL-адресов. В любом случае вам нужно настроить один простой URL-адрес собраний для каждого домена SIP в организации.</span><span class="sxs-lookup"><span data-stu-id="b8f8e-p108">There are three recommended options for naming your simple URLs. Which option you choose has implications for how you set up your DNS A records and certificates which support simple URLs. In each option, you must configure one Meet simple URL for each SIP domain in your organization.</span></span>

<span data-ttu-id="b8f8e-134">В любом случае в организации требуется только один простой URL-адрес для телефонного подключения и один URL-адрес администратора вне зависимости от количества доменов SIP.</span><span class="sxs-lookup"><span data-stu-id="b8f8e-134">You always need just one simple URL in your whole organization for Dial-in, and one for Admin, no matter how many SIP domains you have.</span></span>

<span data-ttu-id="b8f8e-135">Сведения о необходимых записях и сертификатах DNS можно найти [в статье требования к DNS для простых URL-адресов в Lync server 2013](lync-server-2013-dns-requirements-for-simple-urls.md) и [требования к сертификатам для внутренних серверов в Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="b8f8e-135">For details about the necessary DNS A records and certificates, see [DNS requirements for simple URLs in Lync Server 2013](lync-server-2013-dns-requirements-for-simple-urls.md) and [Certificate requirements for internal servers in Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md) in the Planning documentation.</span></span>

<span data-ttu-id="b8f8e-136">В первом случае вам нужно создать имя домена SIP для каждого простого URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="b8f8e-136">In Option 1, you create a new SIP domain name for each simple URL.</span></span>

<span data-ttu-id="b8f8e-137">В этом случае для каждого простого URL-адреса требуется отдельная запись A DNS, а каждый простой URL-адрес собрания должен быть поименован в сертификатах</span><span class="sxs-lookup"><span data-stu-id="b8f8e-137">If you use this option, you need a separate DNS A record for each simple URL, and each Meet simple URL must be named in your certificates.</span></span>

### <a name="simple-url-naming-option-1"></a><span data-ttu-id="b8f8e-138">Вариант именования простых URL-адресов 1</span><span class="sxs-lookup"><span data-stu-id="b8f8e-138">Simple URL Naming Option 1</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b8f8e-139"><strong>Простой URL-адрес</strong></span><span class="sxs-lookup"><span data-stu-id="b8f8e-139"><strong>Simple URL</strong></span></span></p></td>
<td><p><span data-ttu-id="b8f8e-140"><strong>Пример</strong></span><span class="sxs-lookup"><span data-stu-id="b8f8e-140"><strong>Example</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b8f8e-141">Согласно</span><span class="sxs-lookup"><span data-stu-id="b8f8e-141">Meet</span></span></p></td>
<td><p><span data-ttu-id="b8f8e-142">https://meet.contoso.com, https://meet.fabrikam.comи так далее (по одному для каждого домена SIP в организации).</span><span class="sxs-lookup"><span data-stu-id="b8f8e-142">https://meet.contoso.com, https://meet.fabrikam.com, and so on (one for each SIP domain in your organization)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b8f8e-143">Телефонное подключение</span><span class="sxs-lookup"><span data-stu-id="b8f8e-143">Dial-in</span></span></p></td>
<td><p>https://dialin.contoso.com</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b8f8e-144">Администратор</span><span class="sxs-lookup"><span data-stu-id="b8f8e-144">Admin</span></span></p></td>
<td><p>https://admin.contoso.com</p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="b8f8e-p109">При использовании второго варианта простые URL-адреса основаны на имени домена lync.contoso.com. Поэтому вам нужна только одна запись A DNS, которая позволяет использовать все три типа простых URL-адресов. Эта запись A DNS ссылается на адрес lync.contoso.com. Кроме того, вам требуются отдельные записи A DNS для других доменов SIP в организации.</span><span class="sxs-lookup"><span data-stu-id="b8f8e-p109">With Option 2, simple URLs are based on the domain name lync.contoso.com. Therefore, you need only one DNS A record which enables all three types of simple URLs. This DNS A record references lync.contoso.com. Additionally, you still need separate DNS A records for other SIP domains in your organization.</span></span>

### <a name="simple-url-naming-option-2"></a><span data-ttu-id="b8f8e-149">Вариант именования простых URL-адресов 2</span><span class="sxs-lookup"><span data-stu-id="b8f8e-149">Simple URL Naming Option 2</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b8f8e-150"><strong>Простой URL-адрес</strong></span><span class="sxs-lookup"><span data-stu-id="b8f8e-150"><strong>Simple URL</strong></span></span></p></td>
<td><p><span data-ttu-id="b8f8e-151"><strong>Пример</strong></span><span class="sxs-lookup"><span data-stu-id="b8f8e-151"><strong>Example</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b8f8e-152">Согласно</span><span class="sxs-lookup"><span data-stu-id="b8f8e-152">Meet</span></span></p></td>
<td><p><span data-ttu-id="b8f8e-153">https://lync.contoso.com/Meet, https://lync.fabrikam.com/Meetи так далее (по одному для каждого домена SIP в организации).</span><span class="sxs-lookup"><span data-stu-id="b8f8e-153">https://lync.contoso.com/Meet, https://lync.fabrikam.com/Meet, and so on (one for each SIP domain in your organization)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b8f8e-154">Телефонное подключение</span><span class="sxs-lookup"><span data-stu-id="b8f8e-154">Dial-in</span></span></p></td>
<td><p>https://lync.contoso.com/Dialin</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b8f8e-155">Администратор</span><span class="sxs-lookup"><span data-stu-id="b8f8e-155">Admin</span></span></p></td>
<td><p>https://lync.contoso.com/Admin</p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="b8f8e-156">Вариант 3 лучше всего подходит в том случае, если у вас много доменов SIP и вы хотите, чтобы у них были отдельные URL-адреса собраний, но в то же время хотите сократить потребности в записях DNS и сертификатах для этих простых URL-адресов.</span><span class="sxs-lookup"><span data-stu-id="b8f8e-156">Option 3 is most useful if you have many SIP domains, and you want them to have separate Meet simple URLs but want to minimize the DNS record and certificate requirements for these simple URLs.</span></span>

### <a name="simple-url-naming-option-3"></a><span data-ttu-id="b8f8e-157">Вариант именования простых URL-адресов 3</span><span class="sxs-lookup"><span data-stu-id="b8f8e-157">Simple URL Naming Option 3</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b8f8e-158"><strong>Простой URL-адрес</strong></span><span class="sxs-lookup"><span data-stu-id="b8f8e-158"><strong>Simple URL</strong></span></span></p></td>
<td><p><span data-ttu-id="b8f8e-159"><strong>Пример</strong></span><span class="sxs-lookup"><span data-stu-id="b8f8e-159"><strong>Example</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b8f8e-160">Согласно</span><span class="sxs-lookup"><span data-stu-id="b8f8e-160">Meet</span></span></p></td>
<td><p>https://lync.contoso.com/contosoSIPdomain/Meet</p>
<p>https://lync.contoso.com/fabrikamSIPdomain/Meet</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b8f8e-161">Телефонное подключение</span><span class="sxs-lookup"><span data-stu-id="b8f8e-161">Dial-in</span></span></p></td>
<td><p>https://lync.contoso.com/Dialin</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b8f8e-162">Администратор</span><span class="sxs-lookup"><span data-stu-id="b8f8e-162">Admin</span></span></p></td>
<td><p>https://lync.contoso.com/Admin</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="simple-url-naming-and-validation-rules"></a><span data-ttu-id="b8f8e-163">Правила именования и проверки простых URL-адресов</span><span class="sxs-lookup"><span data-stu-id="b8f8e-163">Simple URL Naming and Validation Rules</span></span>

<span data-ttu-id="b8f8e-164">В построителе топологий и командлетах командной консоли Lync Server для простых URL-адресов применяются несколько правил проверки.</span><span class="sxs-lookup"><span data-stu-id="b8f8e-164">Topology Builder and the Lync Server Management Shell cmdlets enforce several validation rules for your simple URLs.</span></span> <span data-ttu-id="b8f8e-165">Вы должны задать простые URL-адреса для собраний и телефонного подключения, однако задавать URL-адрес администратора необязательно.</span><span class="sxs-lookup"><span data-stu-id="b8f8e-165">You are required to set simple URLs for Meet and Dialin, but setting one for Admin is optional.</span></span> <span data-ttu-id="b8f8e-166">Для каждого домена SIP требуется отдельный простой URL-адрес собраний, однако для всей организации нужен только один простой URL-адрес телефонного подключения и URL-адрес администратора.</span><span class="sxs-lookup"><span data-stu-id="b8f8e-166">Each SIP domain must have a separate Meet simple URL, but you need only one Dialin simple URL and one Admin simple URL for your whole organization.</span></span>

<span data-ttu-id="b8f8e-167">Каждый простой URL-адрес в организации должен иметь уникальное имя и не может являться префиксом другого простого URL-адреса (например, нельзя задать адрес lync.contoso.com/Meet в качестве простого URL-адреса собраний, а адрес lync.contoso.com/Meet/Dialin — в качестве простого URL-адреса телефонного подключения).</span><span class="sxs-lookup"><span data-stu-id="b8f8e-167">Each simple URL in your organization must have a unique name, and cannot be a prefix of another simple URL (for example, you could not set lync.contoso.com/Meet as your Meet simple URL and lync.contoso.com/Meet/Dialin as your Dialin simple URL).</span></span> <span data-ttu-id="b8f8e-168">Имена простых URL-адресов не могут содержать полное доменное имя какого-либо пула или сведения о порте https://FQDN:88/meet (например, не разрешены).</span><span class="sxs-lookup"><span data-stu-id="b8f8e-168">Simple URL names cannot contain the FQDN of any of your pools, or any port information (for example, https://FQDN:88/meet is not allowed).</span></span> <span data-ttu-id="b8f8e-169">Простые URL-адреса должны начинаться с префикса https://.</span><span class="sxs-lookup"><span data-stu-id="b8f8e-169">All simple URLs must start with the https:// prefix.</span></span>

<span data-ttu-id="b8f8e-p112">Простые URL-адреса могут содержать только буквы и цифры (a–z, A–Z, 0–9), а также точки (.). При использовании других символов простые URL-адреса могут работать неправильно.</span><span class="sxs-lookup"><span data-stu-id="b8f8e-p112">Simple URLs can contain only alphanumeric characters (that is, a-z, A-Z, 0-9, and the period (.). If you use other characters, the simple URLs might not work as expected.</span></span>

</div>

<div>

## <a name="changing-simple-urls-after-deployment"></a><span data-ttu-id="b8f8e-172">Изменение простых URL-адресов после развертывания</span><span class="sxs-lookup"><span data-stu-id="b8f8e-172">Changing Simple URLs after Deployment</span></span>

<span data-ttu-id="b8f8e-173">Если вы изменяете простой URL-адрес после развертывания, вам следует учесть, как это изменение повлияет на записи DNS и сертификаты для простых URL-адресов.</span><span class="sxs-lookup"><span data-stu-id="b8f8e-173">If you change a simple URL after initial deployment, you must be aware of how the change impacts your DNS records and certificates for simple URLs.</span></span> <span data-ttu-id="b8f8e-174">Если изменяется базовый адрес простого URL-адреса, то вам следует изменить соответствующим образом записи DNS и сертификаты.</span><span class="sxs-lookup"><span data-stu-id="b8f8e-174">If the base of a simple URL changes, then you must change the DNS records and certificates as well.</span></span> <span data-ttu-id="b8f8e-175">Например, изменение с https://lync.contoso.com/Meet для https://meet.contoso.com изменения базового URL-адреса с Lync.contoso.com на Meet.contoso.com, поэтому необходимо изменить записи DNS и сертификаты, чтобы они ссылались на Meet.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="b8f8e-175">For example, changing from https://lync.contoso.com/Meet to https://meet.contoso.com changes the base URL from lync.contoso.com to meet.contoso.com, so you would need to change the DNS records and certificates to refer to meet.contoso.com.</span></span> <span data-ttu-id="b8f8e-176">Если вы изменили простой URL- https://lync.contoso.com/Meet адрес https://lync.contoso.com/Meetingsс на, то базовый URL-адрес Lync.contoso.com остается прежним, поэтому не требуются изменения DNS или сертификата.</span><span class="sxs-lookup"><span data-stu-id="b8f8e-176">If you changed the simple URL from https://lync.contoso.com/Meet to https://lync.contoso.com/Meetings, the base URL of lync.contoso.com stays the same, so no DNS or certificate changes are needed.</span></span>

<span data-ttu-id="b8f8e-177">Однако при изменении простого URL-адреса необходимо выполнить командлет **Enable-CsComputer** на каждом директоре и сервере переднего плана, чтобы зарегистрировать изменение.</span><span class="sxs-lookup"><span data-stu-id="b8f8e-177">Whenever you change a simple URL name, however, you must run **Enable-CsComputer** on each Director and Front End Server to register the change.</span></span>

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b8f8e-178">См. также</span><span class="sxs-lookup"><span data-stu-id="b8f8e-178">See Also</span></span>


[<span data-ttu-id="b8f8e-179">Требования DNS для простых URL-адресов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b8f8e-179">DNS requirements for simple URLs in Lync Server 2013</span></span>](lync-server-2013-dns-requirements-for-simple-urls.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

