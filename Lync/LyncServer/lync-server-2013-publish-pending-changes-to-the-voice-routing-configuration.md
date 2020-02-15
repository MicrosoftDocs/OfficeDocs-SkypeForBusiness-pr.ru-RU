---
title: 'Lync Server 2013: публикация ожидающих изменений в конфигурации маршрутизации голосовой связи'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Publish pending changes to the voice routing configuration
ms:assetid: ff941d0b-fb4b-47d2-b866-6d990ac66b81
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413088(v=OCS.15)
ms:contentKeyID: 48185974
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eec5236f6b40d332617e2e2a5dedeb6a77d752b9
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2020
ms.locfileid: "41987364"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="publish-pending-changes-to-the-voice-routing-configuration-in-lync-server-2013"></a><span data-ttu-id="1b79d-102">Публикация ожидающих изменений в конфигурации маршрутизации голосовой связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1b79d-102">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1b79d-103">_**Последнее изменение темы:** 2012-08-07_</span><span class="sxs-lookup"><span data-stu-id="1b79d-103">_**Topic Last Modified:** 2012-08-07_</span></span>

<span data-ttu-id="1b79d-104">После внесения изменений в любые параметры конфигурации в группе **Маршрутизация голосовых вызовов** выполните эту процедуру, чтобы проверить, опубликовать или отменить ожидающие изменения.</span><span class="sxs-lookup"><span data-stu-id="1b79d-104">After you make changes to any of the configuration settings in pages in the **Voice Routing** group, perform this procedure to review, publish, or cancel the pending changes.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="1b79d-105">Необходимо следить за тем, чтобы одновременно параметры конфигурации маршрутизации голосовых вызовов изменял только один пользователь.</span><span class="sxs-lookup"><span data-stu-id="1b79d-105">Be sure that only one user at a time modifies the Voice Routing configuration settings.</span></span><BR><span data-ttu-id="1b79d-p101">Все ожидающие изменения необходимо публиковать одновременно, выполнив команду <STRONG>Фиксировать все</STRONG>. Ожидающие изменения нельзя публиковать выборочно. Перед публикацией ожидающих изменений выполните команду <STRONG>Review uncommitted changes</STRONG> (Проверка несохраненных изменений) и отмените изменения конфигурации, которые не требуется публиковать.</span><span class="sxs-lookup"><span data-stu-id="1b79d-p101">All pending changes must be published at the same time by running the <STRONG>Commit all</STRONG> command. You cannot selectively publish pending changes. Before you publish pending changes, run the <STRONG>Review uncommitted changes</STRONG> command and cancel any configuration changes that you do not want to publish.</span></span><BR><span data-ttu-id="1b79d-109">Если перейти со страницы в группе <STRONG>Маршрутизация голосовых вызовов</STRONG> до фиксации ожидающих изменений, изменения будут утрачены.</span><span class="sxs-lookup"><span data-stu-id="1b79d-109">If you navigate away from the pages in the <STRONG>Voice Routing</STRONG> group before committing pending changes, all pending changes will be lost.</span></span> <span data-ttu-id="1b79d-110">Тем не менее, текущую конфигурацию (включая все ожидающие изменения) можно экспортировать в файл конфигурации голосовой связи, а затем импортировать и опубликовать обновленную конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="1b79d-110">However, you can export the current configuration (including any pending changes) to a voice configuration file, and then import and publish the updated configuration.</span></span> <span data-ttu-id="1b79d-111">Дополнительную информацию можно узнать <A href="lync-server-2013-export-a-voice-route-configuration-file.md">в статье экспорт файла конфигурации маршрута голосовых вызовов в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="1b79d-111">For details, see <A href="lync-server-2013-export-a-voice-route-configuration-file.md">Export a voice route configuration file in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-review-publish-or-cancel-voice-routing-configuration-changes"></a><span data-ttu-id="1b79d-112">Просмотр, публикация или отмена изменений конфигурации маршрутизации голосовых вызовов</span><span class="sxs-lookup"><span data-stu-id="1b79d-112">To review, publish, or cancel voice routing configuration changes</span></span>

1.  <span data-ttu-id="1b79d-113">Войдите на компьютер как член группы RTCUniversalServerAdmins или роли CsVoiceAdministrator, CsServerAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="1b79d-113">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="1b79d-114">Дополнительные сведения см [в разделе Делегирование разрешений на установку в Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="1b79d-114">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="1b79d-115">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1b79d-115">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="1b79d-116">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="1b79d-116">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="1b79d-117">В левой области навигации щелкните элемент **Voice Routing** (Маршрутизация голосовых вызовов).</span><span class="sxs-lookup"><span data-stu-id="1b79d-117">In the left navigation bar, click **Voice Routing**.</span></span>

4.  <span data-ttu-id="1b79d-118">Внесите необходимые изменения в параметры на каждой странице группы **Маршрутизация голосовых вызовов**.</span><span class="sxs-lookup"><span data-stu-id="1b79d-118">Make the configuration changes you want to the settings on each page of the **Voice Routing** group.</span></span>

5.  <span data-ttu-id="1b79d-119">Чтобы просмотреть ожидающие изменения, не публикуя их, в меню **Зафиксировать** выберите пункт **Проверка несохраненных изменений**.</span><span class="sxs-lookup"><span data-stu-id="1b79d-119">To review pending changes without publishing them, select **Review uncommitted changes** from the **Commit** menu.</span></span>

6.  <span data-ttu-id="1b79d-120">Чтобы отменить ожидающие изменения, выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="1b79d-120">If you want to cancel any of the pending changes, do one of the following:</span></span>
    
      - <span data-ttu-id="1b79d-121">В меню **Зафиксировать** выберите пункт **Cancel all uncommitted changes** (Отмена всех незафиксированных изменений).</span><span class="sxs-lookup"><span data-stu-id="1b79d-121">Select **Cancel all uncommitted changes** from the **Commit** menu.</span></span>
    
      - <span data-ttu-id="1b79d-122">Перейдите на вкладку страницы **Маршрутизация голосовых вызовов** с ожидающими изменениями, которые требуется отменить, выберите элемент с ожидающими изменениями, нажмите кнопку **Зафиксировать**, а затем **Cancel selected changes** (Отмена выбранных изменений).</span><span class="sxs-lookup"><span data-stu-id="1b79d-122">Navigate to the tab of the **Voice Routing** page that has pending changes you want to cancel, select the item with the pending changes, click **Commit**, and then click **Cancel selected changes**.</span></span>

7.  <span data-ttu-id="1b79d-123">Просмотрев все ожидающие изменения и отменив те, которые не требуется публиковать, нажмите кнопку **Зафиксировать**, а затем **Фиксировать все**.</span><span class="sxs-lookup"><span data-stu-id="1b79d-123">After you have reviewed all pending changes and canceled any that you do not want to publish, click **Commit**, and then click **Commit all**.</span></span>

8.  <span data-ttu-id="1b79d-124">В диалоговом окне **Uncommitted Voice Configuration Settings** (Незафиксированные параметры конфигурации голосовой связи), в котором отображается список всех ожидающих изменений, нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="1b79d-124">In the **Uncommitted Voice Configuration Settings** dialog box, which displays a list of all of the pending changes, click **OK**.</span></span>
    
    <span data-ttu-id="1b79d-125">После сохранения изменений в панели управления Lync Server отображается сообщение о **настройке маршрутизации голосовой связи успешно Опубликовано** .</span><span class="sxs-lookup"><span data-stu-id="1b79d-125">When Lync Server Control Panel has committed the changes, the **Successfully published voice routing configuration** message appears.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

