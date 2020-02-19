---
title: 'Lync Server 2013: Проверка маршрутизации голосовой связи'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test voice routing
ms:assetid: d3aae909-fef6-440f-b144-0b62dc82bf5d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398915(v=OCS.15)
ms:contentKeyID: 48185444
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eff0d59de7822f738cc7e2253cf728690dd45b50
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141565"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="test-voice-routing-in-lync-server-2013"></a><span data-ttu-id="67c1e-102">Проверка маршрутизации голосовой связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="67c1e-102">Test voice routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="67c1e-103">_**Последнее изменение темы:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="67c1e-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="67c1e-104">Вы можете настроить сценарии тестовых примеров с помощью вкладки " **Тестовая Маршрутизация голосовой связи** " в панели управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="67c1e-104">You can use the Lync Server Control Panel **Test Voice Routing** tab to configure test case scenarios.</span></span> <span data-ttu-id="67c1e-105">Чтобы задать тестовый случай, следует указать абонентскую группу, политику голосовой связи, вариант использования PSTN и маршрут голосовой связи, применительно к которому следует выполнять тестирование указанного номера телефона.</span><span class="sxs-lookup"><span data-stu-id="67c1e-105">To define a test case, you specify the dial plan, voice policy, PSTN usage, and voice route against which to test a specified phone number.</span></span>

<span data-ttu-id="67c1e-106">Перед фактическим развертыванием конфигурации маршрутизации голосовых вызовов рекомендуется протестировать ее на различных телефонных номерах, чтобы убедиться в том, что результаты являются ожидаемыми.</span><span class="sxs-lookup"><span data-stu-id="67c1e-106">Before you actually deploy your voice routing configuration, we recommend that you test it on various phone numbers to make sure that the results are what you're expecting.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="67c1e-107">Можно использовать команды <STRONG>Экспорт тестовых случаев</STRONG> и <STRONG>Импорт тестовых случаев</STRONG> для сохранения случаев тестирования маршрутизации голосовой связи и их импорта для использования на другом компьютере.</span><span class="sxs-lookup"><span data-stu-id="67c1e-107">You can use the <STRONG>Export test cases</STRONG> and <STRONG>Import test cases</STRONG> commands to save voice routing test cases and import them for use on another computer.</span></span>



</div>

<div>


> [!WARNING]  
> <span data-ttu-id="67c1e-108">Если вы удаляете какую-либо часть конфигурации маршрутизации голосовой связи, например абонентскую группу, политику голосовой связи, маршрут голосовой связи или вариант использования телефона, следует просмотреть и обновить случаи тестирования маршрутизации голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="67c1e-108">If you delete any part of your voice routing configuration, such as a dial plan, voice policy, voice route, or phone usage, you should review and update your voice routing test cases.</span></span> <span data-ttu-id="67c1e-109">Панель управления Lync Server не предупреждает о тестовых случаях, которые больше не являются допустимыми из-за изменения конфигурации.</span><span class="sxs-lookup"><span data-stu-id="67c1e-109">The Lync Server Control Panel will not alert you to test cases that are no longer valid due to changed configurations.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="67c1e-110">Содержание</span><span class="sxs-lookup"><span data-stu-id="67c1e-110">In This Section</span></span>

  - [<span data-ttu-id="67c1e-111">Создание тестового случая маршрутизации голосовой связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="67c1e-111">Create a voice routing test case in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-routing-test-case.md)

  - [<span data-ttu-id="67c1e-112">Экспорт тестовых примеров маршрутизации голосовой связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="67c1e-112">Export voice routing test cases in Lync Server 2013</span></span>](lync-server-2013-export-voice-routing-test-cases.md)

  - [<span data-ttu-id="67c1e-113">Импорт тестовых примеров маршрутизации голосовой связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="67c1e-113">Import voice routing test cases in Lync Server 2013</span></span>](lync-server-2013-import-voice-routing-test-cases.md)

  - [<span data-ttu-id="67c1e-114">Выполнение тестов маршрутизации голосовой связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="67c1e-114">Running voice routing tests in Lync Server 2013</span></span>](lync-server-2013-running-voice-routing-tests.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

