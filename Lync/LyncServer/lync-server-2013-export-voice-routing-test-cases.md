---
title: 'Lync Server 2013: экспорт тестовых примеров маршрутизации голосовой связи'
description: 'Lync Server 2013: экспорт тестовых примеров маршрутизации голосовой связи.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Export voice routing test cases
ms:assetid: 489ac472-1a35-4755-b390-48f7cdf31e94
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425957(v=OCS.15)
ms:contentKeyID: 48184050
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 934bd183a17c46cf82fe5bc04faaa55a9bbe4731
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564785"
---
# <a name="export-voice-routing-test-cases-in-lync-server-2013"></a><span data-ttu-id="382c8-103">Экспорт тестовых примеров маршрутизации голосовой связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="382c8-103">Export voice routing test cases in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="382c8-104">_**Последнее изменение темы:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="382c8-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="382c8-105">Тестовые случаи предоставляют способ тестирования маршрутов голосовых вызовов в Организации: вы определяете, как набираемый номер, и используемая абонентская политика и политика голосовой связи, а Lync Server может проверить, что при условии, что предоставленный номер может успешно маршрутизироваться в сеть PSTN.</span><span class="sxs-lookup"><span data-stu-id="382c8-105">Test cases provide a way for you to test voice routes in your organization: you define such things as the number to be dialed and the dial plan and voice policy to be employed, and Lync Server can then verify that, given those conditions, the supplied number can successfully be routed to the PSTN network.</span></span>

<span data-ttu-id="382c8-106">Тестовые случаи, которые можно создать с помощью панели управления Lync Server, обычно сохраняются только на том сервере, где было создано и запущено обращение.</span><span class="sxs-lookup"><span data-stu-id="382c8-106">Test cases, which can be created by using Lync Server Control Panel, are typically saved only on the server where the case was originally created and run.</span></span> <span data-ttu-id="382c8-107">Однако эти тестовые случаи могут экспортироваться в виде XML-файлов (с расширением VTEST), а затем импортироваться на другие серверы.</span><span class="sxs-lookup"><span data-stu-id="382c8-107">However, these test cases can be exported as XML files (with the .vtest extension) and then imported on other servers.</span></span> <span data-ttu-id="382c8-108">Это позволяет запускать одни и те же тесты на различных компьютерах, расположенных в различных точках топологии.</span><span class="sxs-lookup"><span data-stu-id="382c8-108">This enables you to run the same tests on different computers located at different points in your topology.</span></span>

<div>

## <a name="to-export-a-voice-routing-test-case"></a><span data-ttu-id="382c8-109">Экспорт тестового случая маршрутизации голосовой связи</span><span class="sxs-lookup"><span data-stu-id="382c8-109">To export a voice routing test case</span></span>

1.  <span data-ttu-id="382c8-110">В панели управления Lync Server щелкните **Маршрутизация голосовой связи** , а затем щелкните **проверить маршрутизацию голосовых вызовов**.</span><span class="sxs-lookup"><span data-stu-id="382c8-110">In Lync Server Control Panel, click **Voice Routing** and then click **Test Voice Routing**.</span></span>

2.  <span data-ttu-id="382c8-p102">На вкладке **Проверка маршрутизации голосовой связи** выберите один или несколько тестовых случаев, которые следует экспортировать. Чтобы выбрать несколько тестовых случаев, щелкните первый тестовый случай, который следует экспортировать, затем, удерживая нажатой клавишу Ctrl, выберите дополнительные случаи на экспорт.</span><span class="sxs-lookup"><span data-stu-id="382c8-p102">On the **Test Voice Routing** tab, select the test case (or test cases) to be exported. To select multiple test cases, click the first case to be exported, then hold down the Ctrl key and select the additional cases to be exported.</span></span>

3.  <span data-ttu-id="382c8-113">В меню \*\*Действия \*\* щелкните **Экспортировать тестовые случаи**.</span><span class="sxs-lookup"><span data-stu-id="382c8-113">Click **Action**, then click **Export test cases**.</span></span>

4.  <span data-ttu-id="382c8-p103">В диалоговом окне **Сохранить как** выберите папку для сохранения экспортированных тестовых случаев и укажите имя результирующего XML-файла в поле **Имя файла**. Обратите внимание, что при экспорте нескольких тестовых случаев все тестовые случаи будут сохранены в один XML-файл.</span><span class="sxs-lookup"><span data-stu-id="382c8-p103">In the **Save As** dialog box, select a folder to store the exported test cases and type a name for the resulting XML file in the **File name** box. Note that if you are exporting multiple tests cases all of these test cases will be saved to a single XML file.</span></span>

5.  <span data-ttu-id="382c8-116">Чтобы сохранить тестовые случаи, нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="382c8-116">To save the test cases, click **Save**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="382c8-117">См. также</span><span class="sxs-lookup"><span data-stu-id="382c8-117">See Also</span></span>


[<span data-ttu-id="382c8-118">Импорт тестовых примеров маршрутизации голосовой связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="382c8-118">Import voice routing test cases in Lync Server 2013</span></span>](lync-server-2013-import-voice-routing-test-cases.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

