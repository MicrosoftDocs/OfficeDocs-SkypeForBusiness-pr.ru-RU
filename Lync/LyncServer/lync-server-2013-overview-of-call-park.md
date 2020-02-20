---
title: 'Lync Server 2013: Обзор парковки вызовов'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of Call Park
ms:assetid: 985dc326-0aef-4308-b98b-c1d0069311e7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205124(v=OCS.15)
ms:contentKeyID: 48184939
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: acb507ddf7fc47714781e83da0fa77d093f193c0
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153269"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="overview-of-call-park-in-lync-server-2013"></a><span data-ttu-id="35384-102">Обзор парковки вызовов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="35384-102">Overview of Call Park in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="35384-103">_**Последнее изменение темы:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="35384-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="35384-104">Приложение приостановки вызовов Lync Server 2013 позволяет пользователям корпоративной голосовой связи выполнять следующие действия:</span><span class="sxs-lookup"><span data-stu-id="35384-104">The Lync Server 2013 Call Park application lets Enterprise Voice users do any of the following:</span></span>

  - <span data-ttu-id="35384-105">переводить вызов в режим удержания, а затем извлекать вызов на том же или другом телефоне;</span><span class="sxs-lookup"><span data-stu-id="35384-105">Put a call on hold and then retrieve the call from the same phone or another phone.</span></span>

  - <span data-ttu-id="35384-106">переводить вызов в режим удержания для его переадресации в определенный отдел или область (например, в отдел продаж или склад, где есть телефон общего пользования).</span><span class="sxs-lookup"><span data-stu-id="35384-106">Put a call on hold to transfer it to a department or general area (for example, to a sales department or a warehouse where there is a common area phone).</span></span>

  - <span data-ttu-id="35384-107">переводить вызов в режим удержания и освобождать первоначальный телефон для других вызовов.</span><span class="sxs-lookup"><span data-stu-id="35384-107">Put a call on hold and keep the original answering phone free for other calls.</span></span>

<span data-ttu-id="35384-108">Когда пользователь Паркс вызов, Lync Server передает вызов на временный номер, который называется *орбитой*, где вызов удерживается до получения или истечения времени ожидания. Lync Server отправляет орбите пользователю, который приприпаркован вызов.</span><span class="sxs-lookup"><span data-stu-id="35384-108">When a user parks a call, Lync Server transfers the call to a temporary number, called an *orbit*, where the call is held until it is retrieved or it times out. Lync Server sends the orbit to the user who parked the call.</span></span> <span data-ttu-id="35384-109">Чтобы извлечь вызов пользователь может набрать номер орбиты или щелкнуть ссылку орбиты или нажать кнопку в окне беседы.</span><span class="sxs-lookup"><span data-stu-id="35384-109">To retrieve the parked call, the user can dial the orbit number or click the orbit link or button in the Conversation window.</span></span>

<span data-ttu-id="35384-p102">Пользователь, который припарковал вызов, может уведомить кого-то для извлечения вызова с помощью внешнего механизма, например системы обмена мгновенными сообщениями или пейджинговой системы, для передачи номера орбиты другому пользователю. Пользователь, запарковавший вызов, может оставить окно беседы открытым, чтобы получить уведомление при извлечении вызова.</span><span class="sxs-lookup"><span data-stu-id="35384-p102">The user who parked a call can notify someone to retrieve the call by using an external mechanism, such as instant messaging (IM) or a paging system, to communicate the orbit number to someone else. The user who parked the call can leave the Conversation window open to receive notification when the call is retrieved.</span></span>

<span data-ttu-id="35384-112">Так как диапазоны орбит являются глобально уникальными, можно получить вызовы с любого сайта Lync Server или телефон УАТС, если маршрутизация настроена соответствующим образом.</span><span class="sxs-lookup"><span data-stu-id="35384-112">Because orbit ranges are globally unique, it is possible to retrieve calls from any Lync Server site or PBX phone if routing is configured appropriately.</span></span> <span data-ttu-id="35384-113">Если никто не извлекает вызов в течение заданного промежутка времени, вызов возвращается пользователю, который его запарковал.</span><span class="sxs-lookup"><span data-stu-id="35384-113">If no one retrieves the call within a configurable amount of time, the call rings back to the person who parked it.</span></span> <span data-ttu-id="35384-114">Если это лицо не отвечает на вызов, он переадресовывается на резервный номер, например оператору, если это настроено.</span><span class="sxs-lookup"><span data-stu-id="35384-114">If that person does not answer the ringback, the call is transferred to a fallback destination, such as to an operator, if so configured.</span></span> <span data-ttu-id="35384-115">Вы можете настроить число попыток вызова первоначального пользователя от одного до десяти раз.</span><span class="sxs-lookup"><span data-stu-id="35384-115">You can configure the number of times the call rings back before being transferred from one to ten times.</span></span> <span data-ttu-id="35384-116">Если никто не отвечает на переадресованный вызов, он будет разъединен.</span><span class="sxs-lookup"><span data-stu-id="35384-116">If no one answers a transferred call, the call is disconnected.</span></span> <span data-ttu-id="35384-117">Орбита освобождается, когда вызов извлекается или отключается.</span><span class="sxs-lookup"><span data-stu-id="35384-117">The orbit is freed when the call is retrieved or disconnected.</span></span>

<span data-ttu-id="35384-118">При развертывании парковки вызовов необходимо зарезервировать диапазон добавочных номеров для вызовов парковки.</span><span class="sxs-lookup"><span data-stu-id="35384-118">When you deploy Call Park, you need to reserve ranges of extension numbers for parking calls.</span></span> <span data-ttu-id="35384-119">Эти расширения должны быть виртуальными расширениями: расширениями, которым не назначены пользователи или телефоны.</span><span class="sxs-lookup"><span data-stu-id="35384-119">These extensions need to be virtual extensions: extensions that have no user or phone assigned to them.</span></span> <span data-ttu-id="35384-120">Затем необходимо настроить таблицу орбит парковки вызовов с диапазонами добавочных номеров и указать, какая служба приложений размещает приложение парковки вызовов, которое обрабатывает каждый из этих диапазонов.</span><span class="sxs-lookup"><span data-stu-id="35384-120">You then configure the call park orbit table with the ranges of extension numbers and specify which Application service hosts the Call Park application that handles each range.</span></span> <span data-ttu-id="35384-121">Для каждого пула переднего плана имеется таблица парковки вызовов на соответствующем внутреннем сервере, который используется для управления вызовами, приостановленными в пуле.</span><span class="sxs-lookup"><span data-stu-id="35384-121">Each Front End pool has a Call Park table on the corresponding Back End Server that is used to manage calls that are parked on the pool.</span></span> <span data-ttu-id="35384-122">Список диапазонов орбит хранится в центральном хранилище управления и используется для маршрутизации орбит в целевой пул.</span><span class="sxs-lookup"><span data-stu-id="35384-122">The list of orbit ranges is stored in Central Management store and is used to route orbits to the destination pool.</span></span> <span data-ttu-id="35384-123">Каждый пул Lync Server, в котором разворачивается и настраивается приложение парковки вызовов, может иметь один или несколько диапазонов орбиты.</span><span class="sxs-lookup"><span data-stu-id="35384-123">Each Lync Server pool where the Call Park application is deployed and configured can have one or more orbit ranges.</span></span> <span data-ttu-id="35384-124">Диапазоны орбиты должны быть глобально уникальными в развертывании Lync Server.</span><span class="sxs-lookup"><span data-stu-id="35384-124">Orbit ranges must be globally unique across the Lync Server deployment.</span></span>

<span data-ttu-id="35384-p105">Кроме того, вы настраиваете другие параметры парковки вызовов, например вы указываете, перенаправляются ли вызовы при истечении времени ожидания, и слышит ли абонент музыки, когда вызов припаркован. Вы также можете задать указать музыкальный файл, который воспроизводится, пока вызов находится на удержании.</span><span class="sxs-lookup"><span data-stu-id="35384-p105">You also configure other Call Park settings, such as where calls are redirected if they time out and whether the person on the phone hears music while parked. You can also specify the music file to play while the call is on hold.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="35384-127">В процессе аварийного восстановления Lync Server 2013 пользовательские файлы для сохранения на удержании вызовов не архивируются как часть процесса аварийного восстановления Lync Server и будут потеряны, если загруженные в пул файлы повреждены, повреждены или удалены.</span><span class="sxs-lookup"><span data-stu-id="35384-127">Customized music-on-hold files for Call Park are not backed up as part of the Lync Server 2013 disaster recovery process and will be lost if the files uploaded to the pool are damaged, corrupted, or erased.</span></span> <span data-ttu-id="35384-128">Всегда храните отдельную копию настраиваемых файлов музыки для вызовов в режиме удержания, загруженные для парковки вызовов.</span><span class="sxs-lookup"><span data-stu-id="35384-128">Always keep a separate backup copy of the customized music-on-hold files that you have uploaded for Call Park.</span></span>



</div>

<span data-ttu-id="35384-p107">Приложение парковки вызовов является компонентом Enterprise Voice. При развертывании Enterprise Voice приложение парковки вызовов устанавливается и активируется автоматически. Однако перед использованием парковки вызовов администратор должен настроить Enterprise Voice и включить эту функций для пользователей с помощью политики голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="35384-p107">The Call Park application is a component of Enterprise Voice. When you deploy Enterprise Voice, the Call Park application is installed and activated automatically. Before you can use Call Park, however, the Enterprise Voice administrator must configure it and enable it for users through voice policy.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

