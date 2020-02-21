---
title: 'Lync Server 2013: новые и измененные параметры для Lync 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New and changed settings for Lync 2013
ms:assetid: bb13789c-7eda-461c-a387-02ea8ca4dabe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205204(v=OCS.15)
ms:contentKeyID: 48185241
ms.date: 12/08/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: de4a1a82dbefb5a7f55a4c5872a6702933af08c7
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42184586"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="new-and-changed-settings-for-lync-2013"></a><span data-ttu-id="3d149-102">Новые и измененные параметры для Lync 2013</span><span class="sxs-lookup"><span data-stu-id="3d149-102">New and changed settings for Lync 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3d149-103">_**Последнее изменение темы:** 2014-12-05_</span><span class="sxs-lookup"><span data-stu-id="3d149-103">_**Topic Last Modified:** 2014-12-05_</span></span>

<span data-ttu-id="3d149-104">В этом разделе обсуждаются изменения командлетов командной консоли Lync Server, которые относятся непосредственно к управлению клиентами.</span><span class="sxs-lookup"><span data-stu-id="3d149-104">This topic discusses changes to Lync Server Management Shell cmdlets that relate directly to client management.</span></span> <span data-ttu-id="3d149-105">Lync Server 2013 содержит несколько новых параметров, а также устаревшие параметры для функций, которые можно настроить с помощью других средств.</span><span class="sxs-lookup"><span data-stu-id="3d149-105">Lync Server 2013 introduces several new parameters, and deprecates parameters for features that can be configured through other means.</span></span>

<div>

## <a name="new-client-management-parameters"></a><span data-ttu-id="3d149-106">Новые параметры управления клиентами</span><span class="sxs-lookup"><span data-stu-id="3d149-106">New Client Management Parameters</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3d149-107">Создать</span><span class="sxs-lookup"><span data-stu-id="3d149-107">New</span></span></th>
<th><span data-ttu-id="3d149-108">Командлет командной консоли Lync Server</span><span class="sxs-lookup"><span data-stu-id="3d149-108">Lync Server Management Shell Cmdlet</span></span></th>
<th><span data-ttu-id="3d149-109">Описание</span><span class="sxs-lookup"><span data-stu-id="3d149-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3d149-110">траЦинглевел</span><span class="sxs-lookup"><span data-stu-id="3d149-110">TracingLevel</span></span></p></td>
<td><p><span data-ttu-id="3d149-111">CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="3d149-111">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="3d149-112">Если задано значение true, трассировка программного обеспечения будет включена в Lync; Если задано значение false, трассировка программного обеспечения будет отключена.</span><span class="sxs-lookup"><span data-stu-id="3d149-112">When set to True, software tracing will be enabled in Lync; when set to False, software tracing will be disabled.</span></span> <span data-ttu-id="3d149-113">Отслеживание программного обеспечения включает в себя хранение подробных сведений обо всех действиях, которые выполняет программа (включая вызовы API отслеживания).</span><span class="sxs-lookup"><span data-stu-id="3d149-113">Software tracing involves keeping a detailed record of everything that a program does (including tracking API calls).</span></span> <span data-ttu-id="3d149-114">Трассировка в основном полезна разработчикам и сотрудникам службы поддержки приложений. Этот параметр эквивалентен параметру &quot;групповой политики Communications Server 2007 R2 включить трассировку для Communicator. &quot; Используются следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="3d149-114">Tracing is mostly useful to developers and to application support personnel.This setting is equivalent to the Communications Server 2007 R2 Group Policy setting &quot;Turn on tracing for Communicator.&quot; The settings are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="3d149-115">\* Off — трассировка отключена (пользователь не может изменить этот параметр­);</span><span class="sxs-lookup"><span data-stu-id="3d149-115">Off = Tracing is disabled and the user cannot change this setting.</span></span></p></li>
<li><p><span data-ttu-id="3d149-116">\* Light — минимальная трассировка (пользователь не может изменить этот параметр);</span><span class="sxs-lookup"><span data-stu-id="3d149-116">Light = Minimal tracing is performed, and the user cannot change this setting.</span></span></p></li>
<li><p><span data-ttu-id="3d149-117">\* On — подробная трассировка (пользователь не может изменить этот параметр).</span><span class="sxs-lookup"><span data-stu-id="3d149-117">On = Verbose tracing is performed, and the user cannot change this setting.</span></span></p></li>
</ul>
<p><span data-ttu-id="3d149-p103">По умолчанию параметр TracingLevel имеет значение NULL. Это означает, что выполняется минимальная трассировка, но пользователь может включить или отключить ее.</span><span class="sxs-lookup"><span data-stu-id="3d149-p103">By default TracingLevel is set to a null value. That means that minimal tracing is performed, but the user can enable or disable this minimal tracing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3d149-120">EnableMediaRedirection</span><span class="sxs-lookup"><span data-stu-id="3d149-120">EnableMediaRedirection</span></span></p></td>
<td><p><span data-ttu-id="3d149-121">CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="3d149-121">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="3d149-p104">Значение True ($True) позволяет отделять видео и аудиопотоки от остального сетевого трафика. Например, это позволяет клиентским устройствам локально кодировать и декодировать видео и звук. Перенаправление мультимедиа позволяет уменьшить используемую полосу пропускания сети, повысить масштабирование сервера и обеспечить более оптимальное взаимодействие с пользователем по сравнению с аналогичными технологиями, такими как удаленное взаимодействие или сжатие с помощью кодека.</span><span class="sxs-lookup"><span data-stu-id="3d149-p104">When set to True ($True) allows audio and video streams to be separated from other network traffic, In turn, this allows client devices to do encoding and decoding of audio and video locally. Media redirection typically results in lower bandwidth usage, higher server scalability, and a more-optimal user experience compared to similar techniques such as device remoting or codec compression.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3d149-124">алловларжемитингс</span><span class="sxs-lookup"><span data-stu-id="3d149-124">AllowLargeMeetings</span></span></p></td>
<td><p><span data-ttu-id="3d149-125">ксконференЦинг</span><span class="sxs-lookup"><span data-stu-id="3d149-125">CsConferencing</span></span></p></td>
<td><p><span data-ttu-id="3d149-126">Если задано значение true, все собрания Lync обрабатываются как &quot;крупные собрания. &quot; При большом количестве собраний ограничения накладываются на число уведомлений, отправляемых участникам, а также размер списка собраний, который передается по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="3d149-126">When set to True, all Lync Meetings are treated as &quot;large meetings.&quot; With a large meeting, restrictions are placed on the number of notifications that are sent to participants, in addition to the size of the meeting roster that is transmitted by default.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3d149-127">дисаблеповерпоинтаннотатионс</span><span class="sxs-lookup"><span data-stu-id="3d149-127">DisablePowerPointAnnotations</span></span></p></td>
<td><p><span data-ttu-id="3d149-128">ксконференЦинг</span><span class="sxs-lookup"><span data-stu-id="3d149-128">CsConferencing</span></span></p></td>
<td><p><span data-ttu-id="3d149-p105">При установке значения True ($True) пользователи не смогут добавлять аннотации к слайдам PowerPoint, используемым в конференции. Однако (в зависимости от значения свойства AllowAnnotations) у пользователей останется доступ к другим функциям доски. Значение по умолчанию — False, что означает, что аннотирование слайдов PowerPoint разрешено.</span><span class="sxs-lookup"><span data-stu-id="3d149-p105">When set to True ($True) users won’t be able to add annotations to PowerPoint slides used in a conference. However (depending on the value of the AllowAnnotations property), users will still have access to other whiteboarding features. The default value is False, meaning that PowerPoint annotations are allowed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3d149-132">алловшареднотес</span><span class="sxs-lookup"><span data-stu-id="3d149-132">AllowSharedNotes</span></span></p></td>
<td><p><span data-ttu-id="3d149-133">ксконференЦинг</span><span class="sxs-lookup"><span data-stu-id="3d149-133">CsConferencing</span></span></p></td>
<td><p><span data-ttu-id="3d149-134">При установке значения True (значение по умолчанию) в открытые записные книжки OneNote, подключенные к конференции, будет автоматически добавлена такая информация, как список участников конференции и сведения об общем содержимом конференции.</span><span class="sxs-lookup"><span data-stu-id="3d149-134">When set to True (the default value) any open OneNote notebooks linked to the conference will automatically be updated with information such as conference participants and details about content shared during the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3d149-135">енаблеинвитекустомизатион</span><span class="sxs-lookup"><span data-stu-id="3d149-135">EnableInviteCustomization</span></span></p></td>
<td><p><span data-ttu-id="3d149-136">CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="3d149-136">CsMeetingConfiguration</span></span></p></td>
<td><p><span data-ttu-id="3d149-137">Используется вместе с другими новыми параметрами CsMeetingConfiguration для настройки приглашений на собрание, созданных с помощью надстройки "собрание по сети" для Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="3d149-137">Used along with the other new CsMeetingConfiguration parameters to customize the meeting invitations generated by the Online Meeting Add-in for Lync 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3d149-138">логаурл</span><span class="sxs-lookup"><span data-stu-id="3d149-138">LogoURL</span></span></p></td>
<td><p><span data-ttu-id="3d149-139">CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="3d149-139">CsMeetingConfiguration</span></span></p></td>
<td><p><span data-ttu-id="3d149-140">Добавляет логотип организации во все приглашения, созданные надстройкой "собрание по сети" для Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="3d149-140">Adds your organization’s logo to all invitations generated by the Online Meeting Add-in for Lync 2013.</span></span> <span data-ttu-id="3d149-141">Вы указываете URL-адрес изображения в формате GIF или JPG.</span><span class="sxs-lookup"><span data-stu-id="3d149-141">You specify the URL of a GIF or JPG image.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3d149-142">хелпурл</span><span class="sxs-lookup"><span data-stu-id="3d149-142">HelpURL</span></span></p></td>
<td><p><span data-ttu-id="3d149-143">CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="3d149-143">CsMeetingConfiguration</span></span></p></td>
<td><p><span data-ttu-id="3d149-144">Добавляет URL-адрес справки или поддержки вашей организации для всех приглашений, созданных с помощью надстройки "собрание по сети" для Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="3d149-144">Adds your organization’s help or support URL to all invitations generated by the Online Meeting Add-in for Lync 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3d149-145">легалурл</span><span class="sxs-lookup"><span data-stu-id="3d149-145">LegalURL</span></span></p></td>
<td><p><span data-ttu-id="3d149-146">CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="3d149-146">CsMeetingConfiguration</span></span></p></td>
<td><p><span data-ttu-id="3d149-147">Добавление юридического текста или текста заявления об отказе во все приглашения, созданные надстройкой "собрание по сети" для Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="3d149-147">Adds legal text or disclaimer text to all invitations generated by the Online Meeting Add-in for Lync 2013.</span></span> <span data-ttu-id="3d149-148">Вы указываете URL-адрес расположения текста.</span><span class="sxs-lookup"><span data-stu-id="3d149-148">You specify the URL for the location of the text.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3d149-149">кустомфутертекст</span><span class="sxs-lookup"><span data-stu-id="3d149-149">CustomFooterText</span></span></p></td>
<td><p><span data-ttu-id="3d149-150">CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="3d149-150">CsMeetingConfiguration</span></span></p></td>
<td><p><span data-ttu-id="3d149-151">Добавление настраиваемого нижнего колонтитула ко всем приглашениям, созданным с помощью надстройки "собрание по сети" для Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="3d149-151">Adds a custom footer to all invitations generated by the Online Meeting Add-in for Lync 2013.</span></span> <span data-ttu-id="3d149-152">Вы указываете URL-адрес расположения текста этого нижнего колонтитула.</span><span class="sxs-lookup"><span data-stu-id="3d149-152">You specify the URL for the location of the custom footer text.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="deprecated-client-management-parameters"></a><span data-ttu-id="3d149-153">Устаревшие параметры управления клиентами</span><span class="sxs-lookup"><span data-stu-id="3d149-153">Deprecated Client Management Parameters</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3d149-154">Параметр</span><span class="sxs-lookup"><span data-stu-id="3d149-154">Parameter</span></span></th>
<th><span data-ttu-id="3d149-155">Командлет командной консоли Lync Server</span><span class="sxs-lookup"><span data-stu-id="3d149-155">Lync Server Management Shell Cmdlet</span></span></th>
<th><span data-ttu-id="3d149-156">Описание</span><span class="sxs-lookup"><span data-stu-id="3d149-156">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3d149-157">кустомизедхелпурл</span><span class="sxs-lookup"><span data-stu-id="3d149-157">CustomizedHelpUrl</span></span></p></td>
<td><p><span data-ttu-id="3d149-158">CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="3d149-158">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="3d149-159">Этот параметр устарел для использования с Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3d149-159">This parameter has been deprecated for use with Lync Server 2013.</span></span> <span data-ttu-id="3d149-160">При использовании в сочетании с Енаблинтерприсекустомизедхелп этот параметр включает организацию для указания URL-адреса, чтобы при нажатии пользователем меню Справка в Lync отображалась настраиваемая Справка.</span><span class="sxs-lookup"><span data-stu-id="3d149-160">When used in conjunction with EnableEnterpriseCustomizedHelp, this parameter enabled an organization to specify a URL so that when users clicked the Help menu in Lync, customized help would display.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3d149-161">енаблинтерприсекустомизедхелп</span><span class="sxs-lookup"><span data-stu-id="3d149-161">EnableEnterpriseCustomizedHelp</span></span></p></td>
<td><p><span data-ttu-id="3d149-162">CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="3d149-162">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="3d149-163">Этот параметр устарел для использования с Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3d149-163">This parameter has been deprecated for use with Lync Server 2013.</span></span> <span data-ttu-id="3d149-164">При использовании вместе с Кустомизедхелпурл эти параметры позволяют организациям отображать настроенную справку.</span><span class="sxs-lookup"><span data-stu-id="3d149-164">When used in conjunction with CustomizedHelpUrl, this parameter enabled organizations to display customized help.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3d149-165">енаблескмдата</span><span class="sxs-lookup"><span data-stu-id="3d149-165">EnableSQMData</span></span></p></td>
<td><p><span data-ttu-id="3d149-166">CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="3d149-166">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="3d149-167">Параметр Енаблескмдата командлета Set – CSClientPolicy был удален в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3d149-167">The EnableSQMData parameter of the Set-CSClientPolicy cmdlet has been removed in Lync Server 2013.</span></span> <span data-ttu-id="3d149-168">Вместо него можно с помощью общего параметра групповой политики для данных управления качеством программного обеспечения (SQM) определить пользовательский интерфейс для параметра "Customer Experience Improvement" (Улучшение качества программного обеспечения) на странице общих параметров клиента Lync:</span><span class="sxs-lookup"><span data-stu-id="3d149-168">Instead, you can use the shared Group Policy setting for Software Quality Management (SQM) data to determine the user interface for the Customer Experience Improvement option in the Lync client General options page:</span></span></p>
<p><span data-ttu-id="3d149-169">HKEY_CURRENT_USER \Софтваре\полиЦиес\микрософт\оффице\коммон\кменабле</span><span class="sxs-lookup"><span data-stu-id="3d149-169">HKEY_CURRENT_USER\Software\Policies\Microsoft\Office\Common\QMEnable</span></span></p>
<p><span data-ttu-id="3d149-170">Значений</span><span class="sxs-lookup"><span data-stu-id="3d149-170">Values:</span></span></p>
<p><span data-ttu-id="3d149-171">1 — отображать и установить флажок (пользователь может снять этот флажок);</span><span class="sxs-lookup"><span data-stu-id="3d149-171">1 = Display and select the check box (the user can clear the check box)</span></span></p>
<p><span data-ttu-id="3d149-172">0 — отключить и снять флажок (пользователь не может переопределить это значение);</span><span class="sxs-lookup"><span data-stu-id="3d149-172">0 = Turn off and disable the check box (user can't override)</span></span></p>
<p><span data-ttu-id="3d149-173">Null — значение определяется программой установки Office, и флажок отображается пользователям, чтобы они могли установить его по своему выбору.</span><span class="sxs-lookup"><span data-stu-id="3d149-173">Null = The value is determined by Office setup, and the check box is displayed for users to set as they choose</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3d149-174">алловексчанжеконтактсторе</span><span class="sxs-lookup"><span data-stu-id="3d149-174">AllowExchangeContactStore</span></span></p></td>
<td><p><span data-ttu-id="3d149-175">CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="3d149-175">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="3d149-176">Этот параметр был удален.</span><span class="sxs-lookup"><span data-stu-id="3d149-176">This parameter has been removed.</span></span> <span data-ttu-id="3d149-177">Вместо этого при развертывании Lync Server 2013 и публикации топологии единое хранилище контактов включено для всех пользователей по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="3d149-177">Instead, when you deploy Lync Server 2013 and publish the topology, unified contact store is enabled for all users by default.</span></span> <span data-ttu-id="3d149-178">Это означает, что все контакты пользователя сохраняются в Exchange и доступны в Lync, Outlook и Outlook Web Access.</span><span class="sxs-lookup"><span data-stu-id="3d149-178">This means that all a user’s contacts are kept in Exchange and are available in Lync, Outlook, and Outlook Web Access.</span></span> <span data-ttu-id="3d149-179">Для настройки пользователей, которым доступно единое хранилище контактов, можно использовать командлет Set-CsUserServicesPolicy.</span><span class="sxs-lookup"><span data-stu-id="3d149-179">You can use the Set-CsUserServicesPolicy cmdlet to customize which users have unified contact store available.</span></span> <span data-ttu-id="3d149-180">Пользователей можно включать глобально, по сайту, по клиенту, а также группами или по-отдельности.</span><span class="sxs-lookup"><span data-stu-id="3d149-180">You can enable users globally, by site, by tenant, or by individuals or groups of individuals.</span></span> <span data-ttu-id="3d149-181">Дополнительные сведения см. <a href="lync-server-2013-enable-users-for-unified-contact-store.md">в статье Включение пользователей для единого хранилища контактов в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="3d149-181">For details, see <a href="lync-server-2013-enable-users-for-unified-contact-store.md">Enable users for unified contact store in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3d149-182">мапиполлинтервал</span><span class="sxs-lookup"><span data-stu-id="3d149-182">MAPIPollInterval</span></span></p></td>
<td><p><span data-ttu-id="3d149-183">CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="3d149-183">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="3d149-184">Этот параметр не используется в Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="3d149-184">This parameter is not used by Lync 2013.</span></span> <span data-ttu-id="3d149-185">В предыдущих версиях он определял частоту извлечения клиентом данных MAPI из общедоступных папок Exchange.</span><span class="sxs-lookup"><span data-stu-id="3d149-185">In previous releases, this parameter specified how often the client retrieved MAPI data from Exchange public folders</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3d149-186">дисаблеице</span><span class="sxs-lookup"><span data-stu-id="3d149-186">DisableICE</span></span></p></td>
<td><p><span data-ttu-id="3d149-187">CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="3d149-187">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="3d149-188">Этот параметр устарел в Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="3d149-188">This parameter was deprecated in Lync 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

