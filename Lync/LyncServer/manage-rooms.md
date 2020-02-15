---
title: Управление комнатами
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Manage rooms
ms:assetid: d4835cf4-cd09-4769-a08e-e92706861b64
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205292(v=OCS.15)
ms:contentKeyID: 48185505
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 32185d1f6124109bd957b0af4440ee054e872f54
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048283"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="manage-rooms"></a><span data-ttu-id="1adb1-102">Управление комнатами</span><span class="sxs-lookup"><span data-stu-id="1adb1-102">Manage rooms</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1adb1-103">_**Последнее изменение темы:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="1adb1-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="1adb1-104">Создание новой почтовой комнаты для сервера сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="1adb1-104">To create a new Persistent Chat Server room</span></span>

    New-CsPersistentChatRoom -Name Foo1 -PersistentChatPoolFqdn client.contoso.com -Category client.contoso.com\Foo [other parameters]

<div>


> [!IMPORTANT]  
> <span data-ttu-id="1adb1-105">Параметр -PersistentChatPoolFqdn не требуется, если справедливо одно из следующих условий:</span><span class="sxs-lookup"><span data-stu-id="1adb1-105">-PersistentChatPoolFqdn is not needed if one of the following is true:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="1adb1-106">Существует только один пул серверов сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="1adb1-106">There is only one Persistent Chat Server pool.</span></span></P>
> <LI>
> <P><span data-ttu-id="1adb1-107">для категории указано полное доменное имя пула;</span><span class="sxs-lookup"><span data-stu-id="1adb1-107">You provide a pool FQDN to the category.</span></span></P>
> <LI>
> <P><span data-ttu-id="1adb1-108">для добавления комнаты указывается полное доменное имя пула.</span><span class="sxs-lookup"><span data-stu-id="1adb1-108">You provide a pool FQDN to adding the room.</span></span></P></LI></UL>



</div>

<span data-ttu-id="1adb1-109">Внесение изменений в существующую комнату сервера сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="1adb1-109">To make changes to an existing Persistent Chat Server room</span></span>

    Set-CsPersistentChatRoom -Identity testCat -Members @{Add="sip:user1@contoso.com", "CN=container,DC=contoso,DC=com"}
    Set-CsPersistentChatRoom -Identity testCat -Managers @{Add="sip:user2@contoso.com"}
    Set-CsPersistentChatRoom -Identity testCat -Presenters @{Add="sip:user1@contoso.com"}

<span data-ttu-id="1adb1-110">Windows PowerShell: участники, руководители и докладчики могут быть заданы одновременно.</span><span class="sxs-lookup"><span data-stu-id="1adb1-110">Windows PowerShell: Members, Managers and Presenters can be set simultaneously.</span></span> <span data-ttu-id="1adb1-111">Все они должны принадлежать к одному подмножеству AllowedMembers за исключением DeniedMembers главной категории.</span><span class="sxs-lookup"><span data-stu-id="1adb1-111">They all should be the subset of AllowedMembers minus DeniedMembers of the host Category.</span></span> <span data-ttu-id="1adb1-112">Комната с типом type=normal не может включать выступающих.</span><span class="sxs-lookup"><span data-stu-id="1adb1-112">A room that is type=normal cannot include Presenters.</span></span>

<div>

## <a name="create-get-set-clear-or-remove-a-room"></a><span data-ttu-id="1adb1-113">Создание, получение, задание, очистка или удаление комнаты</span><span class="sxs-lookup"><span data-stu-id="1adb1-113">Create, Get, Set, Clear, or Remove a Room</span></span>

<span data-ttu-id="1adb1-114">Создание новой комнаты</span><span class="sxs-lookup"><span data-stu-id="1adb1-114">To create a new room</span></span>

    New-CsPersistentChatRoom -Name <String> [-PersistentChatPoolFqdn <String>]-Category <String> [-Description <String>] [-Disabled <Switch Parameter>] [-Type <Normal | Auditorium>] [-AddIn <String>] [-Privacy <ChatRoomPrivacy> {Open | Closed | Secret}] [-Invitations <Switch Parameter>]

<span data-ttu-id="1adb1-115">Задание комнаты</span><span class="sxs-lookup"><span data-stu-id="1adb1-115">To set a room</span></span>

    Set-CsPersistentChatRoom -Identity <String> [-Name <String>] [-Category <String>] [-Description <String>] [-Disabled <boolean>] [-Type <Normal | Auditorium>] [-AddIn <String>] [-Privacy <ChatRoomPrivacy> {Open | Closed | Secret}] [-Invitations <Enum>] [-Members <PSListModifier<String>>] [-Managers <PSListModifier<String>>] [-Presenters <PSListModifier<String>>] [-Force < Switch Parameter >] [-Confirm <Switch Parameter>][-WhatIf <Switch Parameter>]

<span data-ttu-id="1adb1-116">Получение комнаты</span><span class="sxs-lookup"><span data-stu-id="1adb1-116">To get a room</span></span>

    Get-CsPersistentChatRoom -Identity <String>

<span data-ttu-id="1adb1-117">или</span><span class="sxs-lookup"><span data-stu-id="1adb1-117">or</span></span>

    Get-CsPersistentChatRoom -filter <String> [-PersistentChatPoolFqdn <String>] [-SearchDescription] [-Member <String>] [-Manager <string>] [-Category <string>] [-Addin <string>] [-Disabled <bool>] [-Privacy <ChatRoomPrivacy> {Open | Closed | Secret}] [-Type <ChatRoomType> {Normal | Auditorium}] [-Invitations <ChatRoomInvitations> {False | Inherit}] [-ChatContentExceedsMB <int>] [-ResultSize <int>]

<span data-ttu-id="1adb1-118">где параметр –filter поддерживает только имя и описание и позволяет находить комнаты, имя и описание которых соответствуют строке с ключевым словом.</span><span class="sxs-lookup"><span data-stu-id="1adb1-118">where –filter supports only Name and Description and helps you find rooms whose Name/Description matches the keyword string.</span></span> <span data-ttu-id="1adb1-119">PoolFqdn выполняет поиск в заданном пуле серверов сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="1adb1-119">PoolFqdn searches in a given Persistent Chat Server pool.</span></span>

<span data-ttu-id="1adb1-120">Очистка комнаты и очистка сообщений в комнате</span><span class="sxs-lookup"><span data-stu-id="1adb1-120">To clear a room and clear messages from a room</span></span>

    Clear-CsPersistentChatRoom [-Identity] <string> -EndDate <DateTime> [-WhatIf] [-Confirm]  [<CommonParameters>]

<span data-ttu-id="1adb1-121">или</span><span class="sxs-lookup"><span data-stu-id="1adb1-121">or</span></span>

    Clear-CsPersistentChatRoom [-Instance] <ChatRoomObject> -EndDate <DateTime> [-WhatIf] [-Confirm] [<CommonParameters>]

<span data-ttu-id="1adb1-122">Удаление комнаты</span><span class="sxs-lookup"><span data-stu-id="1adb1-122">To remove a room</span></span>

    Remove-CsPersistentChatRoom [-Identity] <string> [-Force] [-WhatIf] [-Confirm]  [<CommonParameters>]

<span data-ttu-id="1adb1-123">или</span><span class="sxs-lookup"><span data-stu-id="1adb1-123">or</span></span>

    Remove-CsPersistentChatRoom [-Instance] <ChatRoomObject> [-Force] [-WhatIf] [-Confirm]  [<CommonParameters>]

</div>

</div>

<span> </span>

</div>

</div>

</div>

