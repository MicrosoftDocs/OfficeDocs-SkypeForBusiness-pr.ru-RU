---
title: 'Lync Server 2013: публикация ожидающих изменений в конфигурации голосовой маршрутизации'
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
ms.openlocfilehash: aac5c30cb73ef428d0571a1a0fe6853dbf70db4c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724619"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="publish-pending-changes-to-the-voice-routing-configuration-in-lync-server-2013"></a><span data-ttu-id="cf343-102">Публикация ожидающих изменений в конфигурации голосовой маршрутизации в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cf343-102">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cf343-103">_**Тема последнего изменения:** 2012-08-07_</span><span class="sxs-lookup"><span data-stu-id="cf343-103">_**Topic Last Modified:** 2012-08-07_</span></span>

<span data-ttu-id="cf343-104">После внесения изменений в любые параметры конфигурации в группе **Маршрутизация голосовой связи** выполните эту процедуру, чтобы проверить, опубликовать или отменить ожидающие изменения.</span><span class="sxs-lookup"><span data-stu-id="cf343-104">After you make changes to any of the configuration settings in pages in the **Voice Routing** group, perform this procedure to review, publish, or cancel the pending changes.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="cf343-105">Необходимо следить за тем, чтобы одновременно параметры конфигурации маршрутизации голосовых вызовов изменял только один пользователь.</span><span class="sxs-lookup"><span data-stu-id="cf343-105">Be sure that only one user at a time modifies the Voice Routing configuration settings.</span></span><BR><span data-ttu-id="cf343-p101">Все ожидающие изменения необходимо публиковать одновременно, выполнив команду <STRONG>Сохранить все</STRONG>. Ожидающие изменения нельзя публиковать выборочно. Перед публикацией ожидающих изменений выполните команду <STRONG>Проверка несохраненных изменений</STRONG> и отмените изменения конфигурации, которые не требуется публиковать.</span><span class="sxs-lookup"><span data-stu-id="cf343-p101">All pending changes must be published at the same time by running the <STRONG>Commit all</STRONG> command. You cannot selectively publish pending changes. Before you publish pending changes, run the <STRONG>Review uncommitted changes</STRONG> command and cancel any configuration changes that you do not want to publish.</span></span><BR><span data-ttu-id="cf343-109">Если перейти со страницы в группе <STRONG>Маршрутизация голосовой связи</STRONG> до сохранения ожидающих изменений, изменения будут утрачены.</span><span class="sxs-lookup"><span data-stu-id="cf343-109">If you navigate away from the pages in the <STRONG>Voice Routing</STRONG> group before committing pending changes, all pending changes will be lost.</span></span> <span data-ttu-id="cf343-110">Тем не менее, текущую конфигурацию (включая все ожидающие изменения) можно экспортировать в файл конфигурации голосовой связи, а затем импортировать и опубликовать обновленную конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="cf343-110">However, you can export the current configuration (including any pending changes) to a voice configuration file, and then import and publish the updated configuration.</span></span> <span data-ttu-id="cf343-111">Подробности можно найти <A href="lync-server-2013-export-a-voice-route-configuration-file.md">в разделе Экспорт файла конфигурации голосового маршрута в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="cf343-111">For details, see <A href="lync-server-2013-export-a-voice-route-configuration-file.md">Export a voice route configuration file in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-review-publish-or-cancel-voice-routing-configuration-changes"></a><span data-ttu-id="cf343-112">Просмотр, публикация или отмена изменений конфигурации маршрутизации голосовых вызовов</span><span class="sxs-lookup"><span data-stu-id="cf343-112">To review, publish, or cancel voice routing configuration changes</span></span>

1.  <span data-ttu-id="cf343-113">Войдите на компьютер как член группы RTCUniversalServerAdmins или роли CsVoiceAdministrator, CsServerAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="cf343-113">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="cf343-114">Дополнительные сведения можно найти [в разделе Делегирование разрешений на настройку в Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="cf343-114">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="cf343-115">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="cf343-115">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="cf343-116">Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="cf343-116">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="cf343-117">В левой области навигации щелкните элемент **Маршрутизация голосовой связи**.</span><span class="sxs-lookup"><span data-stu-id="cf343-117">In the left navigation bar, click **Voice Routing**.</span></span>

4.  <span data-ttu-id="cf343-118">Внесите необходимые изменения в параметры на каждой странице группы **Маршрутизация голосовой связи**.</span><span class="sxs-lookup"><span data-stu-id="cf343-118">Make the configuration changes you want to the settings on each page of the **Voice Routing** group.</span></span>

5.  <span data-ttu-id="cf343-119">Чтобы просмотреть ожидающие изменения, не публикуя их, в меню **Сохранить** выберите пункт **Проверка несохраненных изменений**.</span><span class="sxs-lookup"><span data-stu-id="cf343-119">To review pending changes without publishing them, select **Review uncommitted changes** from the **Commit** menu.</span></span>

6.  <span data-ttu-id="cf343-120">Чтобы отменить ожидающие изменения, выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="cf343-120">If you want to cancel any of the pending changes, do one of the following:</span></span>
    
      - <span data-ttu-id="cf343-121">В меню **Сохранить** выберите пункт **Отмена всех несохраненных изменений**.</span><span class="sxs-lookup"><span data-stu-id="cf343-121">Select **Cancel all uncommitted changes** from the **Commit** menu.</span></span>
    
      - <span data-ttu-id="cf343-122">Перейдите на вкладку страницы **Маршрутизация голосовой связи** с ожидающими изменениями, которые требуется отменить, выберите элемент с ожидающими изменениями, нажмите кнопку **Сохранить**, а затем **Отмена выбранных изменений**.</span><span class="sxs-lookup"><span data-stu-id="cf343-122">Navigate to the tab of the **Voice Routing** page that has pending changes you want to cancel, select the item with the pending changes, click **Commit**, and then click **Cancel selected changes**.</span></span>

7.  <span data-ttu-id="cf343-123">Просмотрев все ожидающие изменения и отменив те, которые не требуется публиковать, нажмите кнопку **Сохранить**, а затем **Сохранить все**.</span><span class="sxs-lookup"><span data-stu-id="cf343-123">After you have reviewed all pending changes and canceled any that you do not want to publish, click **Commit**, and then click **Commit all**.</span></span>

8.  <span data-ttu-id="cf343-124">В диалоговом окне **Несохраненные параметры конфигурации голосовой связи**, в котором отображается список всех ожидающих изменений, нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="cf343-124">In the **Uncommitted Voice Configuration Settings** dialog box, which displays a list of all of the pending changes, click **OK**.</span></span>
    
    <span data-ttu-id="cf343-125">После фиксации изменений в панели управления Lync Server появится сообщение о том, что в нем **успешно опубликована конфигурация голосовой маршрутизации** .</span><span class="sxs-lookup"><span data-stu-id="cf343-125">When Lync Server Control Panel has committed the changes, the **Successfully published voice routing configuration** message appears.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

