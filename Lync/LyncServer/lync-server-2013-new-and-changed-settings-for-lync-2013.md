---
title: 'Lync Server 2013: новые и измененные параметры Lync 2013'
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
ms.openlocfilehash: fb5366f7e3d4c2aba81b5b8b25873ea22d54c3a6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765850"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-and-changed-settings-for-lync-2013"></a><span data-ttu-id="911a3-102">Новые и измененные параметры для Lync 2013</span><span class="sxs-lookup"><span data-stu-id="911a3-102">New and changed settings for Lync 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="911a3-103">_**Тема последнего изменения:** 2014-12-05_</span><span class="sxs-lookup"><span data-stu-id="911a3-103">_**Topic Last Modified:** 2014-12-05_</span></span>

<span data-ttu-id="911a3-104">В этом разделе рассматриваются изменения командлетов командной консоли Lync Server, которые непосредственно связаны с управлением клиентом.</span><span class="sxs-lookup"><span data-stu-id="911a3-104">This topic discusses changes to Lync Server Management Shell cmdlets that relate directly to client management.</span></span> <span data-ttu-id="911a3-105">Lync Server 2013 предлагает несколько новых параметров и устаревшие параметры для функций, которые можно настроить с помощью других средств.</span><span class="sxs-lookup"><span data-stu-id="911a3-105">Lync Server 2013 introduces several new parameters, and deprecates parameters for features that can be configured through other means.</span></span>

<div>

## <a name="new-client-management-parameters"></a><span data-ttu-id="911a3-106">Новые параметры управления клиентом</span><span class="sxs-lookup"><span data-stu-id="911a3-106">New Client Management Parameters</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="911a3-107">Новые функции</span><span class="sxs-lookup"><span data-stu-id="911a3-107">New</span></span></th>
<th><span data-ttu-id="911a3-108">Командлет командной консоли Lync Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="911a3-108">Lync Server Management Shell Cmdlet</span></span></th>
<th><span data-ttu-id="911a3-109">Описание</span><span class="sxs-lookup"><span data-stu-id="911a3-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="911a3-110">траЦинглевел</span><span class="sxs-lookup"><span data-stu-id="911a3-110">TracingLevel</span></span></p></td>
<td><p><span data-ttu-id="911a3-111">CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="911a3-111">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="911a3-112">Если установлено значение true, трассировка программного обеспечения будет включена в Lync; Если задано значение false, трассировка программного обеспечения будет отключена.</span><span class="sxs-lookup"><span data-stu-id="911a3-112">When set to True, software tracing will be enabled in Lync; when set to False, software tracing will be disabled.</span></span> <span data-ttu-id="911a3-113">Отслеживание программного обеспечения включает в себя хранение подробной информации о всех функциях программы (в том числе о вызовах API отслеживания).</span><span class="sxs-lookup"><span data-stu-id="911a3-113">Software tracing involves keeping a detailed record of everything that a program does (including tracking API calls).</span></span> <span data-ttu-id="911a3-114">Трассировка особенно полезна разработчикам и сотрудникам службы поддержки приложений. Этот параметр аналогичен параметру &quot;групповой политики Communications Server 2007 R2 включить трассировку для Communicator. &quot; Ниже указаны параметры.</span><span class="sxs-lookup"><span data-stu-id="911a3-114">Tracing is mostly useful to developers and to application support personnel.This setting is equivalent to the Communications Server 2007 R2 Group Policy setting &quot;Turn on tracing for Communicator.&quot; The settings are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="911a3-115">Off = трассировка отключена, и пользователь не может изменить этот параметр.</span><span class="sxs-lookup"><span data-stu-id="911a3-115">Off = Tracing is disabled and the user cannot change this setting.</span></span></p></li>
<li><p><span data-ttu-id="911a3-116">Light = выполняется минимальная трассировка, и пользователь не может изменить этот параметр.</span><span class="sxs-lookup"><span data-stu-id="911a3-116">Light = Minimal tracing is performed, and the user cannot change this setting.</span></span></p></li>
<li><p><span data-ttu-id="911a3-117">On = подробный трассировка выполняется, и пользователь не может изменить этот параметр.</span><span class="sxs-lookup"><span data-stu-id="911a3-117">On = Verbose tracing is performed, and the user cannot change this setting.</span></span></p></li>
</ul>
<p><span data-ttu-id="911a3-118">По умолчанию для ТраЦинглевел задано значение null.</span><span class="sxs-lookup"><span data-stu-id="911a3-118">By default TracingLevel is set to a null value.</span></span> <span data-ttu-id="911a3-119">Это означает, что выполняется минимальная трассировка, но пользователь может включить или отключить эту минимальную трассировку.</span><span class="sxs-lookup"><span data-stu-id="911a3-119">That means that minimal tracing is performed, but the user can enable or disable this minimal tracing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="911a3-120">енаблемедиаредиректион</span><span class="sxs-lookup"><span data-stu-id="911a3-120">EnableMediaRedirection</span></span></p></td>
<td><p><span data-ttu-id="911a3-121">CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="911a3-121">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="911a3-122">Если для этого параметра установлено значение true ($True), звуковые и видеопотоки можно отделить от другого сетевого трафика, в свою очередь это позволяет клиентским устройствам кодировать и декодировать аудио-и видеофайлы локально.</span><span class="sxs-lookup"><span data-stu-id="911a3-122">When set to True ($True) allows audio and video streams to be separated from other network traffic, In turn, this allows client devices to do encoding and decoding of audio and video locally.</span></span> <span data-ttu-id="911a3-123">Перенаправление мультимедиа обычно приводит к снижению использования пропускной способности, повышенной масштабируемости сервера и более удобному взаимодействию с пользователем по сравнению с похожими методиками, такими как удаленное взаимодействие устройств или кодек кодирования кодека.</span><span class="sxs-lookup"><span data-stu-id="911a3-123">Media redirection typically results in lower bandwidth usage, higher server scalability, and a more-optimal user experience compared to similar techniques such as device remoting or codec compression.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="911a3-124">AllowLargeMeetings</span><span class="sxs-lookup"><span data-stu-id="911a3-124">AllowLargeMeetings</span></span></p></td>
<td><p><span data-ttu-id="911a3-125">ксконференЦинг</span><span class="sxs-lookup"><span data-stu-id="911a3-125">CsConferencing</span></span></p></td>
<td><p><span data-ttu-id="911a3-126">Если установлено значение true, все собрания Lync обрабатываются &quot;как большие собрания. &quot; С большим собранием ограничения размещаются на количестве уведомлений, которые отправляются участникам, в дополнение к размеру списка собраний, который передается по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="911a3-126">When set to True, all Lync Meetings are treated as &quot;large meetings.&quot; With a large meeting, restrictions are placed on the number of notifications that are sent to participants, in addition to the size of the meeting roster that is transmitted by default.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="911a3-127">DisablePowerPointAnnotations</span><span class="sxs-lookup"><span data-stu-id="911a3-127">DisablePowerPointAnnotations</span></span></p></td>
<td><p><span data-ttu-id="911a3-128">ксконференЦинг</span><span class="sxs-lookup"><span data-stu-id="911a3-128">CsConferencing</span></span></p></td>
<td><p><span data-ttu-id="911a3-129">Если установлено значение true ($True), пользователи не смогут добавлять примечания к слайдам PowerPoint, используемым на Конференции.</span><span class="sxs-lookup"><span data-stu-id="911a3-129">When set to True ($True) users won’t be able to add annotations to PowerPoint slides used in a conference.</span></span> <span data-ttu-id="911a3-130">Тем не менее (в зависимости от значения свойства Аллованнотатионс) пользователи по-прежнему имеют доступ к другим функциям доски.</span><span class="sxs-lookup"><span data-stu-id="911a3-130">However (depending on the value of the AllowAnnotations property), users will still have access to other whiteboarding features.</span></span> <span data-ttu-id="911a3-131">По умолчанию используется значение false, означающее, что заметки PowerPoint разрешены.</span><span class="sxs-lookup"><span data-stu-id="911a3-131">The default value is False, meaning that PowerPoint annotations are allowed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="911a3-132">AllowSharedNotes</span><span class="sxs-lookup"><span data-stu-id="911a3-132">AllowSharedNotes</span></span></p></td>
<td><p><span data-ttu-id="911a3-133">ксконференЦинг</span><span class="sxs-lookup"><span data-stu-id="911a3-133">CsConferencing</span></span></p></td>
<td><p><span data-ttu-id="911a3-134">Если задано значение true (по умолчанию), все открытые записные книжки OneNote, связанные с конференции, автоматически обновляются данными, например участниками Конференции, и сведения о содержимом, доступном во время конференции.</span><span class="sxs-lookup"><span data-stu-id="911a3-134">When set to True (the default value) any open OneNote notebooks linked to the conference will automatically be updated with information such as conference participants and details about content shared during the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="911a3-135">енаблеинвитекустомизатион</span><span class="sxs-lookup"><span data-stu-id="911a3-135">EnableInviteCustomization</span></span></p></td>
<td><p><span data-ttu-id="911a3-136">ксмитингконфигуратион</span><span class="sxs-lookup"><span data-stu-id="911a3-136">CsMeetingConfiguration</span></span></p></td>
<td><p><span data-ttu-id="911a3-137">Используется вместе с другими новыми параметрами Ксмитингконфигуратион для настройки приглашений на собрания, созданных с помощью надстройки "собрание по сети" для Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="911a3-137">Used along with the other new CsMeetingConfiguration parameters to customize the meeting invitations generated by the Online Meeting Add-in for Lync 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="911a3-138">логаурл</span><span class="sxs-lookup"><span data-stu-id="911a3-138">LogoURL</span></span></p></td>
<td><p><span data-ttu-id="911a3-139">ксмитингконфигуратион</span><span class="sxs-lookup"><span data-stu-id="911a3-139">CsMeetingConfiguration</span></span></p></td>
<td><p><span data-ttu-id="911a3-140">Добавляет логотип организации ко всем приглашениям, созданным с помощью надстройки "собрание по сети" для Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="911a3-140">Adds your organization’s logo to all invitations generated by the Online Meeting Add-in for Lync 2013.</span></span> <span data-ttu-id="911a3-141">Вы задаете URL-адрес изображения в формате GIF или JPG.</span><span class="sxs-lookup"><span data-stu-id="911a3-141">You specify the URL of a GIF or JPG image.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="911a3-142">хелпурл</span><span class="sxs-lookup"><span data-stu-id="911a3-142">HelpURL</span></span></p></td>
<td><p><span data-ttu-id="911a3-143">ксмитингконфигуратион</span><span class="sxs-lookup"><span data-stu-id="911a3-143">CsMeetingConfiguration</span></span></p></td>
<td><p><span data-ttu-id="911a3-144">Добавляет URL-адрес справки или поддержки вашей организации во все приглашения, созданные надстройкой "собрание по сети" для Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="911a3-144">Adds your organization’s help or support URL to all invitations generated by the Online Meeting Add-in for Lync 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="911a3-145">легалурл</span><span class="sxs-lookup"><span data-stu-id="911a3-145">LegalURL</span></span></p></td>
<td><p><span data-ttu-id="911a3-146">ксмитингконфигуратион</span><span class="sxs-lookup"><span data-stu-id="911a3-146">CsMeetingConfiguration</span></span></p></td>
<td><p><span data-ttu-id="911a3-147">Добавление юридического текста или текста отказа во все приглашения, созданные с помощью надстройки "собрание по сети" для Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="911a3-147">Adds legal text or disclaimer text to all invitations generated by the Online Meeting Add-in for Lync 2013.</span></span> <span data-ttu-id="911a3-148">Вы задаете URL-адрес расположения текста.</span><span class="sxs-lookup"><span data-stu-id="911a3-148">You specify the URL for the location of the text.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="911a3-149">кустомфутертекст</span><span class="sxs-lookup"><span data-stu-id="911a3-149">CustomFooterText</span></span></p></td>
<td><p><span data-ttu-id="911a3-150">ксмитингконфигуратион</span><span class="sxs-lookup"><span data-stu-id="911a3-150">CsMeetingConfiguration</span></span></p></td>
<td><p><span data-ttu-id="911a3-151">Добавление настраиваемого нижнего колонтитула ко всем приглашениям, созданным с помощью надстройки "собрание по сети" для Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="911a3-151">Adds a custom footer to all invitations generated by the Online Meeting Add-in for Lync 2013.</span></span> <span data-ttu-id="911a3-152">Вы задаете URL-адрес для расположения настраиваемого текста нижнего колонтитула.</span><span class="sxs-lookup"><span data-stu-id="911a3-152">You specify the URL for the location of the custom footer text.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="deprecated-client-management-parameters"></a><span data-ttu-id="911a3-153">Устаревшие параметры управления клиентом</span><span class="sxs-lookup"><span data-stu-id="911a3-153">Deprecated Client Management Parameters</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="911a3-154">Параметр</span><span class="sxs-lookup"><span data-stu-id="911a3-154">Parameter</span></span></th>
<th><span data-ttu-id="911a3-155">Командлет командной консоли Lync Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="911a3-155">Lync Server Management Shell Cmdlet</span></span></th>
<th><span data-ttu-id="911a3-156">Описание</span><span class="sxs-lookup"><span data-stu-id="911a3-156">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="911a3-157">кустомизедхелпурл</span><span class="sxs-lookup"><span data-stu-id="911a3-157">CustomizedHelpUrl</span></span></p></td>
<td><p><span data-ttu-id="911a3-158">CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="911a3-158">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="911a3-159">Этот параметр не рекомендуется использовать с Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="911a3-159">This parameter has been deprecated for use with Lync Server 2013.</span></span> <span data-ttu-id="911a3-160">При использовании в сочетании с Енаблинтерприсекустомизедхелп этот параметр позволил Организации указать URL-адрес, чтобы при нажатии пользователем пункта меню Справка в Lync отображалась настроенная Справка.</span><span class="sxs-lookup"><span data-stu-id="911a3-160">When used in conjunction with EnableEnterpriseCustomizedHelp, this parameter enabled an organization to specify a URL so that when users clicked the Help menu in Lync, customized help would display.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="911a3-161">енаблинтерприсекустомизедхелп</span><span class="sxs-lookup"><span data-stu-id="911a3-161">EnableEnterpriseCustomizedHelp</span></span></p></td>
<td><p><span data-ttu-id="911a3-162">CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="911a3-162">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="911a3-163">Этот параметр не рекомендуется использовать с Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="911a3-163">This parameter has been deprecated for use with Lync Server 2013.</span></span> <span data-ttu-id="911a3-164">При использовании в сочетании с Кустомизедхелпурл этот параметр позволяет организациям отображать настроенную справку.</span><span class="sxs-lookup"><span data-stu-id="911a3-164">When used in conjunction with CustomizedHelpUrl, this parameter enabled organizations to display customized help.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="911a3-165">енаблескмдата</span><span class="sxs-lookup"><span data-stu-id="911a3-165">EnableSQMData</span></span></p></td>
<td><p><span data-ttu-id="911a3-166">CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="911a3-166">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="911a3-167">Параметр Енаблескмдата командлета Set-CSClientPolicy был удален в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="911a3-167">The EnableSQMData parameter of the Set-CSClientPolicy cmdlet has been removed in Lync Server 2013.</span></span> <span data-ttu-id="911a3-168">Вместо этого вы можете использовать параметр общей групповой политики для данных управления качеством программ (SQM), чтобы определить пользовательский интерфейс для параметра улучшения качества по на странице Общие параметры клиента Lync.</span><span class="sxs-lookup"><span data-stu-id="911a3-168">Instead, you can use the shared Group Policy setting for Software Quality Management (SQM) data to determine the user interface for the Customer Experience Improvement option in the Lync client General options page:</span></span></p>
<p><span data-ttu-id="911a3-169">HKEY_CURRENT_USER \Софтваре\полиЦиес\микрософт\оффице\коммон\кменабле</span><span class="sxs-lookup"><span data-stu-id="911a3-169">HKEY_CURRENT_USER\Software\Policies\Microsoft\Office\Common\QMEnable</span></span></p>
<p><span data-ttu-id="911a3-170">Данные</span><span class="sxs-lookup"><span data-stu-id="911a3-170">Values:</span></span></p>
<p><span data-ttu-id="911a3-171">1 = Отображение и установка флажка (пользователь может снять флажок)</span><span class="sxs-lookup"><span data-stu-id="911a3-171">1 = Display and select the check box (the user can clear the check box)</span></span></p>
<p><span data-ttu-id="911a3-172">0 = отключить и отключить флажок (пользователь не может переопределить)</span><span class="sxs-lookup"><span data-stu-id="911a3-172">0 = Turn off and disable the check box (user can't override)</span></span></p>
<p><span data-ttu-id="911a3-173">NULL = значение определяется программой установки Office, и этот флажок отображается, чтобы пользователи могли задать его по мере выбора.</span><span class="sxs-lookup"><span data-stu-id="911a3-173">Null = The value is determined by Office setup, and the check box is displayed for users to set as they choose</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="911a3-174">алловексчанжеконтактсторе</span><span class="sxs-lookup"><span data-stu-id="911a3-174">AllowExchangeContactStore</span></span></p></td>
<td><p><span data-ttu-id="911a3-175">CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="911a3-175">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="911a3-176">Этот параметр удален.</span><span class="sxs-lookup"><span data-stu-id="911a3-176">This parameter has been removed.</span></span> <span data-ttu-id="911a3-177">Вместо этого при развертывании сервера Lync Server 2013 и публикации топологии единое хранилище контактов включается для всех пользователей по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="911a3-177">Instead, when you deploy Lync Server 2013 and publish the topology, unified contact store is enabled for all users by default.</span></span> <span data-ttu-id="911a3-178">Это означает, что все контакты пользователя хранятся в Exchange и доступны в Lync, Outlook и Outlook Web Access.</span><span class="sxs-lookup"><span data-stu-id="911a3-178">This means that all a user’s contacts are kept in Exchange and are available in Lync, Outlook, and Outlook Web Access.</span></span> <span data-ttu-id="911a3-179">Вы можете использовать командлет Set-Ксусерсервицесполици, чтобы настроить, какие пользователи имеют единое хранилище контактов.</span><span class="sxs-lookup"><span data-stu-id="911a3-179">You can use the Set-CsUserServicesPolicy cmdlet to customize which users have unified contact store available.</span></span> <span data-ttu-id="911a3-180">Вы можете включить пользователей глобально, по сайту, по клиенту или по отдельным пользователям или группам пользователей.</span><span class="sxs-lookup"><span data-stu-id="911a3-180">You can enable users globally, by site, by tenant, or by individuals or groups of individuals.</span></span> <span data-ttu-id="911a3-181">Дополнительные сведения можно найти <a href="lync-server-2013-enable-users-for-unified-contact-store.md">в разделе Включение пользователей единого магазина контактов в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="911a3-181">For details, see <a href="lync-server-2013-enable-users-for-unified-contact-store.md">Enable users for unified contact store in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="911a3-182">мапиполлинтервал</span><span class="sxs-lookup"><span data-stu-id="911a3-182">MAPIPollInterval</span></span></p></td>
<td><p><span data-ttu-id="911a3-183">CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="911a3-183">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="911a3-184">Этот параметр не используется в Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="911a3-184">This parameter is not used by Lync 2013.</span></span> <span data-ttu-id="911a3-185">В предыдущих выпусках этот параметр указывает, как часто клиент извлекает данные MAPI из общедоступных папок Exchange.</span><span class="sxs-lookup"><span data-stu-id="911a3-185">In previous releases, this parameter specified how often the client retrieved MAPI data from Exchange public folders</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="911a3-186">дисаблеице</span><span class="sxs-lookup"><span data-stu-id="911a3-186">DisableICE</span></span></p></td>
<td><p><span data-ttu-id="911a3-187">CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="911a3-187">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="911a3-188">Этот параметр устарел в Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="911a3-188">This parameter was deprecated in Lync 2013.</span></span></p></td>
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

