---
title: 'Lync Server 2013: Настройка политик начальной загрузки клиентов'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring client bootstrapping policies
ms:assetid: 45042eca-b845-4207-b12f-b8b7f5d44bdf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425941(v=OCS.15)
ms:contentKeyID: 48184031
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c0a917364c31da4a944f41da586b53bc6a59b6ef
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42203155"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-client-bootstrapping-policies-in-lync-server-2013"></a><span data-ttu-id="8010a-102">Настройка политик начальной загрузки клиентов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8010a-102">Configuring client bootstrapping policies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8010a-103">_**Последнее изменение темы:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="8010a-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="8010a-104">Консоль управления групповыми политиками и редактор объектов групповой политики являются инструментами, которые используются для управления групповой политикой.</span><span class="sxs-lookup"><span data-stu-id="8010a-104">The Group Policy Management Console (GPMC) and the Group Policy Object Editor are tools that you use to manage Group Policy.</span></span> <span data-ttu-id="8010a-105">В административный шаблон групповой политики Office включены административные шаблоны Lync 2013. ADMX (ADMX) и. ADML (ADML), которые содержат параметры политики на основе реестра, которые вы настроили для объектов групповой политики в домене.</span><span class="sxs-lookup"><span data-stu-id="8010a-105">Included with the Office Group Policy Administrative Template are Lync 2013.admx (ADMX) and .adml (ADML) Administrative Templates, which contain the registry-based policy settings that you configure for Group Policy objects in the domain.</span></span> <span data-ttu-id="8010a-106">ADML-файлы являются дополнениями ADMX-файлов для определенных языков.</span><span class="sxs-lookup"><span data-stu-id="8010a-106">ADML files are language-specific complements to ADMX files.</span></span> <span data-ttu-id="8010a-107">Каждый ADMX-файл или ADML-файл содержит параметры политики для одного приложения Office.</span><span class="sxs-lookup"><span data-stu-id="8010a-107">Each ADMX and ADML file contains the policy settings for a single Office application.</span></span> <span data-ttu-id="8010a-108">Дополнительные сведения можно найти в статье "файлы административных шаблонов Office 2013 (ADMX, ADML)" в документации по Office 2013 <https://go.microsoft.com/fwlink/p/?linkid=267516>по адресу.</span><span class="sxs-lookup"><span data-stu-id="8010a-108">For more information, see “Office 2013 Administrative Template files (ADMX, ADML)” in the Office 2013 documentation at <https://go.microsoft.com/fwlink/p/?linkid=267516>.</span></span>

<span data-ttu-id="8010a-109">Для Lync 2013 существует несколько политик начальной загрузки клиентов, которые необходимо настроить перед первым входом пользователей на сервер.</span><span class="sxs-lookup"><span data-stu-id="8010a-109">For Lync 2013, there are several client bootstrapping policies that you should consider configuring before users sign in to the server for the first time.</span></span> <span data-ttu-id="8010a-110">Например, можно настроить серверы по умолчанию и режим безопасности, который должен использоваться клиентом до завершения процесса входа.</span><span class="sxs-lookup"><span data-stu-id="8010a-110">For example, the default servers and security mode that the client should use until sign-in is complete.</span></span> <span data-ttu-id="8010a-111">С помощью групповых политик можно установить эти параметры в реестрах компьютеров пользователей до того, как они войдут и начнут получать от сервера параметры подготовки штатного канала.</span><span class="sxs-lookup"><span data-stu-id="8010a-111">You can use Group Policy to establish these settings in users’ computer registries before they sign in and begin receiving in-band provisioning settings from the server.</span></span> <span data-ttu-id="8010a-112">В следующей таблице перечислены параметры групповой политики, доступные для Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="8010a-112">The following table lists the Group Policy settings that are available for Lync 2013.</span></span>

### <a name="group-policy-settings-for-lync-2013"></a><span data-ttu-id="8010a-113">Параметры групповой политики для Lync 2013</span><span class="sxs-lookup"><span data-stu-id="8010a-113">Group Policy Settings for Lync 2013</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8010a-114">Параметр групповой политики</span><span class="sxs-lookup"><span data-stu-id="8010a-114">Group Policy setting</span></span></th>
<th><span data-ttu-id="8010a-115">Описание</span><span class="sxs-lookup"><span data-stu-id="8010a-115">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8010a-116">Укажите сервер</span><span class="sxs-lookup"><span data-stu-id="8010a-116">Specify Server</span></span><br />
<span data-ttu-id="8010a-117">ConfigurationMode</span><span class="sxs-lookup"><span data-stu-id="8010a-117">(ConfigurationMode)</span></span></p></td>
<td><p><span data-ttu-id="8010a-118">Указывает, как Lync 2013 определяет транспортный сервер и сервер для использования при входе.</span><span class="sxs-lookup"><span data-stu-id="8010a-118">Specifies how Lync 2013 identifies the transport and server to use during sign-in.</span></span> <span data-ttu-id="8010a-119">В этом параметре задаются следующие значения.</span><span class="sxs-lookup"><span data-stu-id="8010a-119">Within this setting, you specify the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="8010a-120">ServerAddressExternal: указывает имя или IP-адрес сервера, используемого клиентами и федеративными контактами при подключении за пределами внешнего брандмауэра.</span><span class="sxs-lookup"><span data-stu-id="8010a-120">ServerAddressExternal: Specifies the server name or IP address used by clients and federated contacts when connecting from outside the external firewall.</span></span></p></li>
<li><p><span data-ttu-id="8010a-121">ServerAddressInternal: указывает имя или IP-адрес сервера, используемого клиентами при подключении внутри брандмауэра организации.</span><span class="sxs-lookup"><span data-stu-id="8010a-121">ServerAddressInternal: Specifies the server name or IP address used when clients connect from inside the organization’s firewall.</span></span></p></li>
<li><p><span data-ttu-id="8010a-122">Transport: указывает протокол TCP (Transmission Control Protocol) или протокол TLS (Transport Layer Security).</span><span class="sxs-lookup"><span data-stu-id="8010a-122">Transport: Specifies either Transmission Control Protocol (TCP) or Transport Layer Security (TLS).</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8010a-123">Поддерживаемые дополнительные версии серверов</span><span class="sxs-lookup"><span data-stu-id="8010a-123">Additional server versions supported</span></span><br />
<span data-ttu-id="8010a-124">ConfiguredServerCheckValues</span><span class="sxs-lookup"><span data-stu-id="8010a-124">(ConfiguredServerCheckValues)</span></span></p></td>
<td><p><span data-ttu-id="8010a-125">Задает список имен версий сервера, разделенных точками с запятой, в которые Lync Server 2013 будет выполнять вход, в дополнение к версиям сервера, поддерживаемым по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="8010a-125">Specifies a list of server version names separated by semi-colons that Lync Server 2013 will log on to, in addition to the server versions that are supported by default.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8010a-126">Отключает автоматическое обновление журналов сбоев при входе (DisableAutomaticSendTracing)</span><span class="sxs-lookup"><span data-stu-id="8010a-126">Disable automatic upload of sign-in failure logs (DisableAutomaticSendTracing)</span></span></p></td>
<td><p><span data-ttu-id="8010a-127">Автоматически отправляет журналы сбоев при входе в Lync Server для анализа.</span><span class="sxs-lookup"><span data-stu-id="8010a-127">Automatically uploads sign-in failure logs to Lync Server for analysis.</span></span> <span data-ttu-id="8010a-128">Журналы не загружаются автоматически, если вход выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="8010a-128">No logs are automatically uploaded if sign-in is successful.</span></span> <span data-ttu-id="8010a-129">Если эта политика не настроена, происходит следующее.</span><span class="sxs-lookup"><span data-stu-id="8010a-129">If this policy is not configured, the following happens:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="8010a-130">Для пользователей Lync Online: журналы сбоев при входе автоматически отправляются.</span><span class="sxs-lookup"><span data-stu-id="8010a-130">For Lync Online users: Sign-in failure logs are automatically uploaded.</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="8010a-131">Для локальных пользователей Lync: пользователю отображается диалоговое окно подтверждения перед отправкой.</span><span class="sxs-lookup"><span data-stu-id="8010a-131">For Lync on-premises users: A confirmation dialog box is shown to the user before upload.</span></span></p>
</dd>
</dl>
<p><span data-ttu-id="8010a-132">Если этот параметр отключен, журналы входа автоматически отправляются на сервер Lync как для локальных пользователей Lync, так и для пользователей Lync Online.</span><span class="sxs-lookup"><span data-stu-id="8010a-132">When this setting is disabled, sign-in logs are automatically uploaded to the Lync Server for both Lync on-premises and Lync Online users.</span></span> <span data-ttu-id="8010a-133">Если этот параметр включен, журналы входа никогда не загружаются автоматически.</span><span class="sxs-lookup"><span data-stu-id="8010a-133">When this setting is enabled, sign-in logs are never uploaded automatically.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8010a-134">Отключение резервного HTTP-подключения для SIP-подключения</span><span class="sxs-lookup"><span data-stu-id="8010a-134">Disable HTTP fallback for SIP connection</span></span><br />
<span data-ttu-id="8010a-135">DisableHttpConnect</span><span class="sxs-lookup"><span data-stu-id="8010a-135">(DisableHttpConnect)</span></span></p></td>
<td><p><span data-ttu-id="8010a-136">Запрещает Lync Server пытаться подключиться к серверу с помощью HTTP, если протокол TLS или TCP недоступен.</span><span class="sxs-lookup"><span data-stu-id="8010a-136">Prevents Lync Server from trying to connect to the server by using HTTP, if TLS or TCP are unavailable.</span></span> <span data-ttu-id="8010a-137">По умолчанию Lync сначала пытается подключиться к серверу с помощью протокола TLS или TCP и, если ни один из этих методов транспорта не будет успешным, Lync пытается подключиться с помощью HTTP.</span><span class="sxs-lookup"><span data-stu-id="8010a-137">By default, Lync first attempts to connect to the server by using TLS or TCP and, if neither of these transport methods is successful, Lync tries to connect by using HTTP.</span></span> <span data-ttu-id="8010a-138">С помощью этой политики можно отключить попытки резервного использования HTTP.</span><span class="sxs-lookup"><span data-stu-id="8010a-138">Use this policy to disable the fallback HTTP connection attempt.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8010a-139">Требовать учетные данные для входа</span><span class="sxs-lookup"><span data-stu-id="8010a-139">Require logon credentials</span></span><br />
<span data-ttu-id="8010a-140">DisableNTCredentials</span><span class="sxs-lookup"><span data-stu-id="8010a-140">(DisableNTCredentials)</span></span></p></td>
<td><p><span data-ttu-id="8010a-141">Пользователю необходимо предоставить учетные данные для входа в Lync вместо автоматического использования учетных данных Windows при входе на сервер SIP.</span><span class="sxs-lookup"><span data-stu-id="8010a-141">Requires the user to provide logon credentials for Lync rather than automatically using Windows credentials during sign-in to a SIP server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8010a-142">Отключить проверку версии сервера</span><span class="sxs-lookup"><span data-stu-id="8010a-142">Disable server version check</span></span><br />
<span data-ttu-id="8010a-143">DisableServerCheck</span><span class="sxs-lookup"><span data-stu-id="8010a-143">(DisableServerCheck)</span></span></p></td>
<td><p><span data-ttu-id="8010a-144">Если для этой политики установлено значение 1, то не позволяет Lync проверять имя и версию сервера перед входом.</span><span class="sxs-lookup"><span data-stu-id="8010a-144">If you set this policy to 1, prevents Lync from checking the server name and version before signing in.</span></span> <span data-ttu-id="8010a-145">По умолчанию Lync выполняет эти проверки перед входом.</span><span class="sxs-lookup"><span data-stu-id="8010a-145">By default, Lync makes these checks before signing in.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8010a-146">Разрешить использование BITS для загрузки файлов службы адресной книги</span><span class="sxs-lookup"><span data-stu-id="8010a-146">Enable using BITS to download Address Book Service files</span></span><br />
<span data-ttu-id="8010a-147">EnableBitsForGalDownload</span><span class="sxs-lookup"><span data-stu-id="8010a-147">(EnableBitsForGalDownload)</span></span></p></td>
<td><p><span data-ttu-id="8010a-148">Позволяет Lync использовать фоновую интеллектуальную службу передачи (BITS) для загрузки файлов службы адресной книги.</span><span class="sxs-lookup"><span data-stu-id="8010a-148">Enables Lync to use Background Intelligent Transfer Service (BITS) to download the Address Book Services files.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8010a-149">Настройка режима безопасности SIP</span><span class="sxs-lookup"><span data-stu-id="8010a-149">Configure SIP security mode</span></span><br />
<span data-ttu-id="8010a-150">EnableSIPHighSecurityMode</span><span class="sxs-lookup"><span data-stu-id="8010a-150">(EnableSIPHighSecurityMode)</span></span></p></td>
<td><p><span data-ttu-id="8010a-151">Обеспечивает безопасную отправку и получение мгновенных сообщений в Lync.</span><span class="sxs-lookup"><span data-stu-id="8010a-151">Enables Lync to send and receive instant messages more securely.</span></span> <span data-ttu-id="8010a-152">Эта политика не оказывает влияние на службы Windows .NET или Microsoft Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="8010a-152">This policy has no effect on Windows .NET or Microsoft Exchange Server services.</span></span></p>
<p><span data-ttu-id="8010a-153">Если вы не настраиваете этот параметр политики, Lync может использовать любой транспорт.</span><span class="sxs-lookup"><span data-stu-id="8010a-153">If you do not configure this policy setting, Lync can use any transport.</span></span> <span data-ttu-id="8010a-154">Но если он не использует TLS и если сервер выполняет проверку подлинности пользователей, Lync должен использовать проверку подлинности NTLM или Kerberos.</span><span class="sxs-lookup"><span data-stu-id="8010a-154">But if it does not use TLS and if the server authenticates users, Lync must use either NTLM or Kerberos authentication.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8010a-155">Начальная задержка загрузки глобальной адресной книги</span><span class="sxs-lookup"><span data-stu-id="8010a-155">Global Address Book Download Initial Delay</span></span><br />
<span data-ttu-id="8010a-156">GalDownloadInitialDelay</span><span class="sxs-lookup"><span data-stu-id="8010a-156">(GalDownloadInitialDelay)</span></span></p></td>
<td><p><span data-ttu-id="8010a-p110">Задает период времени перед загрузкой глобального списка адресов (GAL). Значение по умолчанию — 60 минут, что означает, что сервер задерживает загрузку файла глобального списка адресов на произвольное время от 0 до 60 минут.</span><span class="sxs-lookup"><span data-stu-id="8010a-p110">Specifies the time period before a download of the global address list (GAL) occurs. The default value is 60 minutes, which means the server delays the download of GAL file for a random period of between 0 and 60 minutes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8010a-159">Запретить пользователям запускать Microsoft Lync</span><span class="sxs-lookup"><span data-stu-id="8010a-159">Prevent users from running Microsoft Lync</span></span><br />
<span data-ttu-id="8010a-160">PreventRun</span><span class="sxs-lookup"><span data-stu-id="8010a-160">(PreventRun)</span></span></p></td>
<td><p><span data-ttu-id="8010a-161">Запрещает пользователям запускать Lync.</span><span class="sxs-lookup"><span data-stu-id="8010a-161">Prevents users from running Lync.</span></span> <span data-ttu-id="8010a-162">Этот параметр политики можно настраивать как в конфигурации компьютера, так и в конфигурации пользователя, однако преимущество имеет параметр политики, заданный в конфигурации компьютера.</span><span class="sxs-lookup"><span data-stu-id="8010a-162">You can configure this policy setting under both Computer Configuration and User Configuration, but the policy setting under Computer Configuration takes precedence.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8010a-163">Разрешить хранение паролей пользователей</span><span class="sxs-lookup"><span data-stu-id="8010a-163">Allow storage of user passwords</span></span><br />
<span data-ttu-id="8010a-164">SavePassword</span><span class="sxs-lookup"><span data-stu-id="8010a-164">(SavePassword)</span></span></p></td>
<td><p><span data-ttu-id="8010a-165">Позволяет Lync хранить пароли.</span><span class="sxs-lookup"><span data-stu-id="8010a-165">Enables Lync to store passwords.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8010a-166">Настройка режима сжатия SIP</span><span class="sxs-lookup"><span data-stu-id="8010a-166">Configure SIP compression mode</span></span><br />
<span data-ttu-id="8010a-167">SipCompression</span><span class="sxs-lookup"><span data-stu-id="8010a-167">(SipCompression)</span></span></p></td>
<td><p><span data-ttu-id="8010a-p112">Указывает, когда следует включать сжатие SIP. По умолчанию сжатие SIP включается в зависимости от скорости адаптера. Следует учитывать, что установка этого параметра может привести к увеличению времени, затрачиваемого на вход.</span><span class="sxs-lookup"><span data-stu-id="8010a-p112">Specifies when to turn on SIP compression. By default, SIP compression is enabled based on the adapter speed. Note that setting this policy might cause an increase in sign-in time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8010a-171">Список доверенных доменов</span><span class="sxs-lookup"><span data-stu-id="8010a-171">Trusted Domain List</span></span><br />
<span data-ttu-id="8010a-172">TrustModelData</span><span class="sxs-lookup"><span data-stu-id="8010a-172">(TrustModelData)</span></span></p></td>
<td><p><span data-ttu-id="8010a-173">перечисляет доверенные домены, не соответствующие префиксу домена SIP клиента.</span><span class="sxs-lookup"><span data-stu-id="8010a-173">Lists the trusted domains that do not match the prefix of the customer SIP domain.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="8010a-p113">Политики, настроенные на сервере, имеют преимущество перед параметрами групповой политики и параметрами клиентов, настроенными пользователем. В следующей таблице приводится порядок приоритетов в случае возникновения конфликта.</span><span class="sxs-lookup"><span data-stu-id="8010a-p113">Policies configured on the server take precedence over Group Policy settings and client options configured by the user. The following table summarizes the order in which settings take precedence when a conflict occurs.</span></span>

### <a name="group-policy-precedence"></a><span data-ttu-id="8010a-176">Приоритет групповой политики</span><span class="sxs-lookup"><span data-stu-id="8010a-176">Group Policy Precedence</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8010a-177">Больший</span><span class="sxs-lookup"><span data-stu-id="8010a-177">Precedence</span></span></th>
<th><span data-ttu-id="8010a-178">Место или способ установки</span><span class="sxs-lookup"><span data-stu-id="8010a-178">Location or Method of Setting</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8010a-179">1,1</span><span class="sxs-lookup"><span data-stu-id="8010a-179">1</span></span></p></td>
<td><p><span data-ttu-id="8010a-180">Наполнение данными по стандарту Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8010a-180">Lync Server 2013 in-band provisioning</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8010a-181">2</span><span class="sxs-lookup"><span data-stu-id="8010a-181">2</span></span></p></td>
<td><p><span data-ttu-id="8010a-182">HKEY_LOCAL_MACHINE \SOFTWARE\Policies\Microsoft\Office\15.0\Lync</span><span class="sxs-lookup"><span data-stu-id="8010a-182">HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\15.0\Lync</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8010a-183">4</span><span class="sxs-lookup"><span data-stu-id="8010a-183">3</span></span></p></td>
<td><p><span data-ttu-id="8010a-184">HKEY_CURRENT_USER \SOFTWARE\Policies\Microsoft\Office\15.0\Lync</span><span class="sxs-lookup"><span data-stu-id="8010a-184">HKEY_CURRENT_USER\SOFTWARE\Policies\Microsoft\Office\15.0\Lync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8010a-185">SP4</span><span class="sxs-lookup"><span data-stu-id="8010a-185">4</span></span></p></td>
<td><p><span data-ttu-id="8010a-186">Диалоговое окно Lync — параметры в Lync 2013</span><span class="sxs-lookup"><span data-stu-id="8010a-186">The Lync - Options dialog box in Lync 2013</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-define-group-policy-settings-by-using-the-lync-2013-administrative-template-files"></a><span data-ttu-id="8010a-187">Определение параметров групповой политики с помощью файлов административных шаблонов Lync 2013</span><span class="sxs-lookup"><span data-stu-id="8010a-187">To define Group Policy settings by using the Lync 2013 administrative template files</span></span>

1.  <span data-ttu-id="8010a-p114">Создайте на корневом уровне папку для хранения всех не зависящих от языка ADMX-файлов. Например, создайте корневую папку для центрального хранилища в контроллере домена в следующем расположении:</span><span class="sxs-lookup"><span data-stu-id="8010a-p114">Create a root-level folder to contain all language-neutral ADMX files. For example, create the root folder for the central store on your domain controller at this location:</span></span>
    
    `%systemroot%\sysvol\domain\policies\PolicyDefinitions`
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="8010a-p115">В данной процедуре предполагается, что требуется управление несколькими компьютерами в домене. В таком случае шаблоны сохраняются в центральном хранилище в папке Sysvol основного контроллера домена. Это обеспечивает реплицируемое расположение центрального хранилища для административных шаблонов домена.</span><span class="sxs-lookup"><span data-stu-id="8010a-p115">This procedure assumes that you want to manage multiple computers in your domain. In this case, you store the templates in a central store in the Sysvol folder on the primary domain controller. This provides a replicated central storage location for domain Administrative Templates.</span></span>

    
    </div>

2.  <span data-ttu-id="8010a-p116">Создайте по вложенной папке для каждого используемого языка. Эти вложенные папки будут содержать зависящие от языка ADML-файлы ресурсов. Например, создайте вложенную папку для американского английского (EN-US) в следующем расположении:</span><span class="sxs-lookup"><span data-stu-id="8010a-p116">Create a subfolder for each language that you’ll use. These subfolders will contain the language-specific ADML resource files. For example, create a subfolder for United States English (EN-US) at this location:</span></span>
    
    `%systemroot%\sysvol\domain\policies\PolicyDefinitions\EN-US`

</div>

</div>

<span> </span>

</div>

</div>

</div>

