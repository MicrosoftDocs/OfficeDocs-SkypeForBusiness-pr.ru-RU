---
title: 'Lync Server 2013: Импорт тестовых примеров маршрутизации голосовой связи'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Import voice routing test cases
ms:assetid: 6546e24c-9ad2-428b-92b2-63948ed0f884
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398460(v=OCS.15)
ms:contentKeyID: 48184325
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 742bb5d8e8f29edf0397c9bb9fa12592087ea517
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038721"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="import-voice-routing-test-cases-in-lync-server-2013"></a><span data-ttu-id="e5b49-102">Импорт тестовых примеров маршрутизации голосовой связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e5b49-102">Import voice routing test cases in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e5b49-103">_**Последнее изменение темы:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="e5b49-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="e5b49-104">Тестовые случаи предоставляют способ тестирования маршрутов голосовых вызовов в Организации: вы определяете, как набираемый номер, и используемая абонентская политика и политика голосовой связи, а Lync Server 2013 может проверить, что при условии, что предоставленный номер может сукцес сфулли направляется в сеть PSTN.</span><span class="sxs-lookup"><span data-stu-id="e5b49-104">Test cases provide a way for you to test voice routes in your organization: you define such things as the number to be dialed and the dial plan and voice policy to be employed, and Lync Server 2013 can then verify that, given those conditions, the supplied number can successfully be routed to the PSTN network.</span></span>

<span data-ttu-id="e5b49-105">Тестовые случаи, которые можно создать с помощью панели управления Lync Server, обычно сохраняются только на том сервере, где было создано и запущено обращение.</span><span class="sxs-lookup"><span data-stu-id="e5b49-105">Test cases, which can be created by using Lync Server Control Panel, are typically saved only on the server where the case was originally created and run.</span></span> <span data-ttu-id="e5b49-106">Однако эти тестовые случаи могут экспортироваться в виде XML-файлов (с расширением VTEST), а затем импортироваться на другие серверы.</span><span class="sxs-lookup"><span data-stu-id="e5b49-106">However, these test cases can be exported as XML files (with the .vtest extension) and then imported on other servers.</span></span> <span data-ttu-id="e5b49-107">Это позволяет запускать одни и те же тесты на различных компьютерах, расположенных в различных точках топологии.</span><span class="sxs-lookup"><span data-stu-id="e5b49-107">This enables you to run the same tests on different computers located at different points in your topology.</span></span>

<div>

## <a name="to-import-a-voice-routing-test-case"></a><span data-ttu-id="e5b49-108">Импорта случая тестирования маршрутизации голосовой связи</span><span class="sxs-lookup"><span data-stu-id="e5b49-108">To import a voice routing test case</span></span>

1.  <span data-ttu-id="e5b49-109">Войдите на компьютер как член группы RTCUniversalServerAdmins или роли CsVoiceAdministrator, CsServerAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="e5b49-109">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="e5b49-110">Дополнительные сведения см [в разделе Делегирование разрешений на установку в Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="e5b49-110">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="e5b49-111">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e5b49-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="e5b49-112">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="e5b49-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="e5b49-113">На левой панели навигации щелкните **Маршрутизация голосовой связи**.</span><span class="sxs-lookup"><span data-stu-id="e5b49-113">In the left navigation bar, click **Voice Routing**.</span></span>

4.  <span data-ttu-id="e5b49-114">В меню **Действия** щелкните **Импорт тестовых случаев**.</span><span class="sxs-lookup"><span data-stu-id="e5b49-114">On the **Actions** menu, click **Import test cases**.</span></span>

5.  <span data-ttu-id="e5b49-115">Найти файл тестового случая (.vtest), который необходимо импортировать, а затем щелкните **Открыть**.</span><span class="sxs-lookup"><span data-stu-id="e5b49-115">Find the test case file (.vtest) that you want to import, and then click **Open**.</span></span>

6.  <span data-ttu-id="e5b49-116">Щелкните **Исполнить**, а затем щелкните **Исполнить все**.</span><span class="sxs-lookup"><span data-stu-id="e5b49-116">Click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e5b49-117">При импорте файла. втест необходимо выполнить команду <STRONG>commit all</STRONG> , чтобы опубликовать тестовый случай.</span><span class="sxs-lookup"><span data-stu-id="e5b49-117">Whenever you import a .vtest file, you must run the <STRONG>Commit all</STRONG> command to publish the test case.</span></span> <span data-ttu-id="e5b49-118">Дополнительные сведения см в статье <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Публикация ожидающих изменений в конфигурации маршрутизации голосовой связи в Lync Server 2013</A> в документации по операциям.</span><span class="sxs-lookup"><span data-stu-id="e5b49-118">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e5b49-119">См. также</span><span class="sxs-lookup"><span data-stu-id="e5b49-119">See Also</span></span>


[<span data-ttu-id="e5b49-120">Экспорт тестовых примеров маршрутизации голосовой связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e5b49-120">Export voice routing test cases in Lync Server 2013</span></span>](lync-server-2013-export-voice-routing-test-cases.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

