---
title: 'Lync Server 2013: импорт тестовых примеров маршрутизации голосовой связи'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Import voice routing test cases
ms:assetid: 6546e24c-9ad2-428b-92b2-63948ed0f884
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398460(v=OCS.15)
ms:contentKeyID: 48184325
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d8b1aba05447904d4515df7ab6137743edb52ea7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834024"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="import-voice-routing-test-cases-in-lync-server-2013"></a><span data-ttu-id="1ac07-102">Импорт тестовых примеров маршрутизации голосовой связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1ac07-102">Import voice routing test cases in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1ac07-103">_**Тема последнего изменения:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="1ac07-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="1ac07-104">С помощью тестовых случаев вы можете проверить Голосовые маршруты в вашей организации: вы определяете, как набранный номер, а также с помощью абонентской группы и политики голосовой связи, и Lync Server 2013 может проверить, что при условии, что указанные номера могут сукцес. сфулли перенаправляться в сеть PSTN.</span><span class="sxs-lookup"><span data-stu-id="1ac07-104">Test cases provide a way for you to test voice routes in your organization: you define such things as the number to be dialed and the dial plan and voice policy to be employed, and Lync Server 2013 can then verify that, given those conditions, the supplied number can successfully be routed to the PSTN network.</span></span>

<span data-ttu-id="1ac07-105">Тестовые случаи, которые можно создать с помощью панели управления Lync Server, обычно сохраняются только на сервере, где они были созданы и запущены.</span><span class="sxs-lookup"><span data-stu-id="1ac07-105">Test cases, which can be created by using Lync Server Control Panel, are typically saved only on the server where the case was originally created and run.</span></span> <span data-ttu-id="1ac07-106">Однако эти тестовые случаи можно экспортировать как XML-файлы (с расширением втест), а затем импортировать на другие серверы.</span><span class="sxs-lookup"><span data-stu-id="1ac07-106">However, these test cases can be exported as XML files (with the .vtest extension) and then imported on other servers.</span></span> <span data-ttu-id="1ac07-107">Это позволяет выполнять одни и те же тесты на разных компьютерах, расположенных в разных точках топологии.</span><span class="sxs-lookup"><span data-stu-id="1ac07-107">This enables you to run the same tests on different computers located at different points in your topology.</span></span>

<div>

## <a name="to-import-a-voice-routing-test-case"></a><span data-ttu-id="1ac07-108">Импорт тестового случая голосовой маршрутизации</span><span class="sxs-lookup"><span data-stu-id="1ac07-108">To import a voice routing test case</span></span>

1.  <span data-ttu-id="1ac07-109">Войдите на компьютер как член группы RTCUniversalServerAdmins или роли CsVoiceAdministrator, CsServerAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="1ac07-109">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="1ac07-110">Дополнительные сведения можно найти [в разделе Делегирование разрешений на настройку в Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="1ac07-110">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="1ac07-111">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1ac07-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="1ac07-112">Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="1ac07-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="1ac07-113">В левой области навигации щелкните элемент **Маршрутизация голосовой связи**.</span><span class="sxs-lookup"><span data-stu-id="1ac07-113">In the left navigation bar, click **Voice Routing**.</span></span>

4.  <span data-ttu-id="1ac07-114">В меню **действия** выберите команду **Импорт тестовых случаев**.</span><span class="sxs-lookup"><span data-stu-id="1ac07-114">On the **Actions** menu, click **Import test cases**.</span></span>

5.  <span data-ttu-id="1ac07-115">Найдите файл тестового случая (втест), который вы хотите импортировать, и нажмите кнопку **Открыть**.</span><span class="sxs-lookup"><span data-stu-id="1ac07-115">Find the test case file (.vtest) that you want to import, and then click **Open**.</span></span>

6.  <span data-ttu-id="1ac07-116">Нажмите кнопку **Сохранить**, а затем нажмите кнопку **Сохранить все**.</span><span class="sxs-lookup"><span data-stu-id="1ac07-116">Click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1ac07-117">Каждый раз, когда вы импортируете втест-файл, необходимо выполнить команду <STRONG>commit all</STRONG> для публикации тестового случая.</span><span class="sxs-lookup"><span data-stu-id="1ac07-117">Whenever you import a .vtest file, you must run the <STRONG>Commit all</STRONG> command to publish the test case.</span></span> <span data-ttu-id="1ac07-118">Дополнительные сведения можно найти в разделе <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Публикация ожидающих изменений в конфигурации голосовой маршрутизации в Lync Server 2013</A> в документации по эксплуатации.</span><span class="sxs-lookup"><span data-stu-id="1ac07-118">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="1ac07-119">См. также</span><span class="sxs-lookup"><span data-stu-id="1ac07-119">See Also</span></span>


[<span data-ttu-id="1ac07-120">Экспорт тестовых примеров маршрутизации голосовой связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1ac07-120">Export voice routing test cases in Lync Server 2013</span></span>](lync-server-2013-export-voice-routing-test-cases.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

