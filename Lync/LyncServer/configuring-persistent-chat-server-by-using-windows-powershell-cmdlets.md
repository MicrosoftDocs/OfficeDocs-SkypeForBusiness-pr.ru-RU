---
title: Настройка сервера сохраняемого сеанса беседы с помощью командлетов Windows PowerShell
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Configuring Persistent Chat Server by using Windows PowerShell cmdlets
ms:assetid: 4c1d1ad7-b6bd-476f-9c5b-f0c1756d5aa8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204877(v=OCS.15)
ms:contentKeyID: 48184089
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c18111987d7f0c567eab0cab8bad60934ec7d36d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841841"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="efccd-102">Настройка сервера сохраняемого сеанса беседы с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="efccd-102">Configuring Persistent Chat Server by using Windows PowerShell cmdlets</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="efccd-103">_**Тема последнего изменения:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="efccd-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="efccd-104">Используйте указанные ниже командлеты Windows PowerShell для настройки управления в Lync Server 2013, который является сервером сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="efccd-104">Use the following Windows PowerShell cmdlets to configure management within Lync Server 2013, Persistent Chat Server.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="efccd-105">Содержание</span><span class="sxs-lookup"><span data-stu-id="efccd-105">In This Section</span></span>

  - [<span data-ttu-id="efccd-106">Manage categories</span><span class="sxs-lookup"><span data-stu-id="efccd-106">Manage categories</span></span>](manage-categories.md)

  - [<span data-ttu-id="efccd-107">Управление чатами</span><span class="sxs-lookup"><span data-stu-id="efccd-107">Manage rooms</span></span>](manage-rooms.md)

  - [<span data-ttu-id="efccd-108">Управление надстройками</span><span class="sxs-lookup"><span data-stu-id="efccd-108">Manage add-ins</span></span>](manage-add-ins.md)

  - [<span data-ttu-id="efccd-109">Удаление сообщения</span><span class="sxs-lookup"><span data-stu-id="efccd-109">Remove a message</span></span>](remove-a-message.md)

  - [<span data-ttu-id="efccd-110">Проверка сервера сохраняемого чата с помощью искусственной транзакции</span><span class="sxs-lookup"><span data-stu-id="efccd-110">Test Persistent Chat Server with a synthetic transaction</span></span>](test-persistent-chat-server-with-a-synthetic-transaction.md)

  - [<span data-ttu-id="efccd-111">Организация обратной совместимости для сервера сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="efccd-111">Run backward compatibility for Persistent Chat Server</span></span>](run-backward-compatibility-for-persistent-chat-server.md)

  - [<span data-ttu-id="efccd-112">Запуск, предоставление, получение, удаление и установка политики сохраняемого чата в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="efccd-112">Run, grant, get, remove, or set Persistent Chat Policy in Lync Server 2013</span></span>](lync-server-2013-run-grant-get-remove-or-set-persistent-chat-policy.md)

  - [<span data-ttu-id="efccd-113">Настройка сервера сохраняемого сеанса беседы в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="efccd-113">Configure Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-configure-persistent-chat-server.md)

  - [<span data-ttu-id="efccd-114">Получение сведений о доступности пула сервера сохраняемого чата в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="efccd-114">Get Persistent Chat Server pool availability in Lync Server 2013</span></span>](lync-server-2013-get-persistent-chat-server-pool-availability.md)

  - [<span data-ttu-id="efccd-115">Соблюдение норм в сохряняемом чате в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="efccd-115">Persistent Chat compliance in Lync Server 2013</span></span>](lync-server-2013-persistent-chat-compliance.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

