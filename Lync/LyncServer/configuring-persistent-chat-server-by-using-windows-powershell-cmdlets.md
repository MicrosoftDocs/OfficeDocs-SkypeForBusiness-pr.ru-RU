---
title: Настройка сервера сохраняемого чата с помощью командлетов Windows PowerShell
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Configuring Persistent Chat Server by using Windows PowerShell cmdlets
ms:assetid: 4c1d1ad7-b6bd-476f-9c5b-f0c1756d5aa8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204877(v=OCS.15)
ms:contentKeyID: 48184089
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a9963b918b64e56f87aba6eb243f513c41a87499
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48503126"
---
# <a name="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="27afb-102">Настройка сервера сохраняемого чата с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="27afb-102">Configuring Persistent Chat Server by using Windows PowerShell cmdlets</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="27afb-103">_**Последнее изменение темы:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="27afb-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="27afb-104">Используйте следующие командлеты Windows PowerShell для настройки управления в среде Lync Server 2013 и сервера сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="27afb-104">Use the following Windows PowerShell cmdlets to configure management within Lync Server 2013, Persistent Chat Server.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="27afb-105">Содержание</span><span class="sxs-lookup"><span data-stu-id="27afb-105">In This Section</span></span>

  - [<span data-ttu-id="27afb-106">Управление категориями</span><span class="sxs-lookup"><span data-stu-id="27afb-106">Manage categories</span></span>](manage-categories.md)

  - [<span data-ttu-id="27afb-107">Управление комнатами</span><span class="sxs-lookup"><span data-stu-id="27afb-107">Manage rooms</span></span>](manage-rooms.md)

  - [<span data-ttu-id="27afb-108">Управление надстройками</span><span class="sxs-lookup"><span data-stu-id="27afb-108">Manage add-ins</span></span>](manage-add-ins.md)

  - [<span data-ttu-id="27afb-109">Удаление сообщения</span><span class="sxs-lookup"><span data-stu-id="27afb-109">Remove a message</span></span>](remove-a-message.md)

  - [<span data-ttu-id="27afb-110">Проверка сервера сохраняемого чата с помощью искусственной транзакции</span><span class="sxs-lookup"><span data-stu-id="27afb-110">Test Persistent Chat Server with a synthetic transaction</span></span>](test-persistent-chat-server-with-a-synthetic-transaction.md)

  - [<span data-ttu-id="27afb-111">Выполнение обратной совместимости для сервера сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="27afb-111">Run backward compatibility for Persistent Chat Server</span></span>](run-backward-compatibility-for-persistent-chat-server.md)

  - [<span data-ttu-id="27afb-112">Запуск, предоставление, получение, удаление и установка политики сохраняемого чата в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="27afb-112">Run, grant, get, remove, or set Persistent Chat Policy in Lync Server 2013</span></span>](lync-server-2013-run-grant-get-remove-or-set-persistent-chat-policy.md)

  - [<span data-ttu-id="27afb-113">Настройка сервера сохраняемого чата в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="27afb-113">Configure Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-configure-persistent-chat-server.md)

  - [<span data-ttu-id="27afb-114">Получение доступности пула сервера сохраняемого чата в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="27afb-114">Get Persistent Chat Server pool availability in Lync Server 2013</span></span>](lync-server-2013-get-persistent-chat-server-pool-availability.md)

  - [<span data-ttu-id="27afb-115">Соответствие сохраняемого чата в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="27afb-115">Persistent Chat compliance in Lync Server 2013</span></span>](lync-server-2013-persistent-chat-compliance.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

