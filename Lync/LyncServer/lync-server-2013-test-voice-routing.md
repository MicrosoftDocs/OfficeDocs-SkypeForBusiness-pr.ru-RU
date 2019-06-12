---
title: 'Lync Server 2013: тестирование голосовой маршрутизации'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Test voice routing
ms:assetid: d3aae909-fef6-440f-b144-0b62dc82bf5d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398915(v=OCS.15)
ms:contentKeyID: 48185444
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0ac9fdac24178bfec7ebce97cbdfdd15707913d1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849425"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-voice-routing-in-lync-server-2013"></a><span data-ttu-id="73597-102">Тестирование голосовой маршрутизации в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="73597-102">Test voice routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="73597-103">_**Тема последнего изменения:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="73597-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="73597-104">Вы можете настроить сценарии тестовых случаев с помощью панели управления Lync Server на странице **Проверка маршрутизации голосовых сообщений** .</span><span class="sxs-lookup"><span data-stu-id="73597-104">You can use the Lync Server Control Panel **Test Voice Routing** tab to configure test case scenarios.</span></span> <span data-ttu-id="73597-105">Для определения тестового случая Вы можете указать абонентскую группу, политику голосовой связи, использование КТСОП и голосовой маршрут, с помощью которых можно протестировать указанный номер телефона.</span><span class="sxs-lookup"><span data-stu-id="73597-105">To define a test case, you specify the dial plan, voice policy, PSTN usage, and voice route against which to test a specified phone number.</span></span>

<span data-ttu-id="73597-106">Прежде чем приступить к развертыванию конфигурации голосовой маршрутизации, мы рекомендуем проверить ее на различных телефонных номерах, чтобы убедиться в том, что результаты ожидаются.</span><span class="sxs-lookup"><span data-stu-id="73597-106">Before you actually deploy your voice routing configuration, we recommend that you test it on various phone numbers to make sure that the results are what you're expecting.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="73597-107">С помощью команд <STRONG>экспорта тестовых случаев</STRONG> и <STRONG>импорта тестовых случаев</STRONG> можно сохранять тестовые случаи голосовой маршрутизации и импортировать их для использования на другом компьютере.</span><span class="sxs-lookup"><span data-stu-id="73597-107">You can use the <STRONG>Export test cases</STRONG> and <STRONG>Import test cases</STRONG> commands to save voice routing test cases and import them for use on another computer.</span></span>



</div>

<div>


> [!WARNING]  
> <span data-ttu-id="73597-108">Если вы удалите все части конфигурации голосовой связи, такие как абонентская группа, политика голосовой связи, маршрут голосовой связи или использование телефона, необходимо просмотреть и изменить тестовые случаи для маршрутизации голосовых сообщений.</span><span class="sxs-lookup"><span data-stu-id="73597-108">If you delete any part of your voice routing configuration, such as a dial plan, voice policy, voice route, or phone usage, you should review and update your voice routing test cases.</span></span> <span data-ttu-id="73597-109">На панели управления Lync Server не выводится предупреждение о том, что они больше не действительны из-за измененных конфигураций.</span><span class="sxs-lookup"><span data-stu-id="73597-109">The Lync Server Control Panel will not alert you to test cases that are no longer valid due to changed configurations.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="73597-110">Содержание</span><span class="sxs-lookup"><span data-stu-id="73597-110">In This Section</span></span>

  - [<span data-ttu-id="73597-111">Создание тестового примера маршрутизации голосовой связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="73597-111">Create a voice routing test case in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-routing-test-case.md)

  - [<span data-ttu-id="73597-112">Экспорт тестовых примеров маршрутизации голосовой связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="73597-112">Export voice routing test cases in Lync Server 2013</span></span>](lync-server-2013-export-voice-routing-test-cases.md)

  - [<span data-ttu-id="73597-113">Импорт тестовых примеров маршрутизации голосовой связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="73597-113">Import voice routing test cases in Lync Server 2013</span></span>](lync-server-2013-import-voice-routing-test-cases.md)

  - [<span data-ttu-id="73597-114">Проведение тестов маршрутизации голосовой связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="73597-114">Running voice routing tests in Lync Server 2013</span></span>](lync-server-2013-running-voice-routing-tests.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

