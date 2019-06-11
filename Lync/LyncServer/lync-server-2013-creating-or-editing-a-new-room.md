---
title: 'Lync Server 2013: создание или редактирование нового чата'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Creating or editing a new room
ms:assetid: aa8f4349-cfd9-4036-9c4d-de8fb2c4c8a4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215880(v=OCS.15)
ms:contentKeyID: 48706008
ms.date: 03/19/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1442454b2afb129fda50d98ed17ccdc2c7ba35c2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834753"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="creating-or-editing-a-new-room-in-lync-server-2013"></a><span data-ttu-id="e995a-102">Создание или редактирование нового чата в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e995a-102">Creating or editing a new room in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e995a-103">_**Тема последнего изменения:** 2015-03-19_</span><span class="sxs-lookup"><span data-stu-id="e995a-103">_**Topic Last Modified:** 2015-03-19_</span></span>

<span data-ttu-id="e995a-104">Настройка постоянных комнат чатов обычно обрабатывают пользователи; Администратор сохраняемого чата обычно не настраивает комнаты чата и не управляет ими.</span><span class="sxs-lookup"><span data-stu-id="e995a-104">Configuring Persistent Chat rooms is commonly handled by users; a Persistent Chat administrator typically does not configure or manage chat rooms.</span></span> <span data-ttu-id="e995a-105">Командлеты Windows PowerShell для управления помещениями доступны только для администраторов **ксперсистентчатадминистратор** .</span><span class="sxs-lookup"><span data-stu-id="e995a-105">Windows PowerShell cmdlets to manage rooms are available only to **CsPersistentChatAdministrator** Administrators.</span></span>

<span data-ttu-id="e995a-106">Пользователи, являющиеся **создателями** в любой определенной категории, могут использовать клиент Lync для создания комнат и управления ими.</span><span class="sxs-lookup"><span data-stu-id="e995a-106">Users who are **Creators** in any given category can use the Lync client to create and manage rooms.</span></span> <span data-ttu-id="e995a-107">Пользователи, которые назначены руководителям для определенной комнаты чата, могут также выполнять текущее управление комнатой, например изменять свойства комнаты или членство.</span><span class="sxs-lookup"><span data-stu-id="e995a-107">Users who have been designated as managers for a specific chat room can also perform ongoing management of the room, such as editing the room properties or membership.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="e995a-108">Администраторам сохраняемого чата также могут быть создатели, и они не распространяются на ограничения, накладываемые на создателя.</span><span class="sxs-lookup"><span data-stu-id="e995a-108">Persistent Chat administrators can also be Creators, and they are not subject to the restrictions placed on Creators.</span></span>



</div>

<span data-ttu-id="e995a-109">Кроме того, если вы являетесь администратором постоянного чата, вы можете использовать пользовательский интерфейс для создания комнат чата и управления ими, а не с помощью командлетов Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e995a-109">Optionally, if you are a Persistent Chat administrator, you can employ a user interface to create and manage chat rooms instead of using Windows PowerShell cmdlets.</span></span> <span data-ttu-id="e995a-110">Для этого SIP-Включите администратора для постоянного сервера чата, а затем используйте клиент Lync для создания комнат чата и управления ими.</span><span class="sxs-lookup"><span data-stu-id="e995a-110">To do this, SIP-enable an administrator for Persistent Chat Server, and then use the Lync client to create and manage chat rooms.</span></span>

<span data-ttu-id="e995a-111">Если вы хотите создать настраиваемый рабочий процесс управления комнатой для пользователей, вы можете настроить свойство **румманажементурл** в конфигурации сервера сохраняемого чата, чтобы перенаправить пользователей на свое собственное решение из клиента Lync.</span><span class="sxs-lookup"><span data-stu-id="e995a-111">If you want to create a custom room management workflow for your users, you can set the **RoomManagementUrl** property on your Persistent Chat Server configuration to redirect users to your custom solution from the Lync client.</span></span>

<span data-ttu-id="e995a-112">Дополнительные сведения о настройке комнат чата с помощью интерфейса командной строки Windows PowerShell можно найти в разделе Управление комнатой на странице [Настройка сохраняемого сервера чата с помощью командлетов Windows PowerShell](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).</span><span class="sxs-lookup"><span data-stu-id="e995a-112">For details about configuring chat rooms by using the Windows PowerShell command-line interface, see "Room Management" in [Configuring Persistent Chat Server by using Windows PowerShell cmdlets](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).</span></span>

<span data-ttu-id="e995a-113">Дополнительные сведения о настройке комнат чатов можно найти в разделе [Настройка комнат в Lync Server 2013](lync-server-2013-configure-rooms.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="e995a-113">For details about configuring chat rooms, see [Configure rooms in Lync Server 2013](lync-server-2013-configure-rooms.md) in the Deployment documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e995a-114">Сервер сохраняемого чата позволяет пользователям создавать и управлять комнатой чата для определенного сайта.</span><span class="sxs-lookup"><span data-stu-id="e995a-114">Persistent Chat Server lets users create and manage chat room for a specific site.</span></span> <span data-ttu-id="e995a-115">Тем не менее, пользователи не могут создавать комнаты чата и управлять ими на других сайтах в пределах одной и той же топологии.</span><span class="sxs-lookup"><span data-stu-id="e995a-115">Users cannot, however, create or manage chat rooms on other sites within the same topology.</span></span> <span data-ttu-id="e995a-116">Не забудьте указать создатели и руководителей комнаты чата для всех сайтов в Организации.</span><span class="sxs-lookup"><span data-stu-id="e995a-116">Be sure to specify chat room Creators and Managers for all the sites in your organization.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="e995a-117">Пользователи, расположенные на устройстве с бесперебойной подразделением Lync Server, не могут создавать новые комнаты чата и просматривать открытку для существующих комнат.</span><span class="sxs-lookup"><span data-stu-id="e995a-117">Users who are homed on a Lync Server Survivable Branch Appliance are unable to create new chat rooms or view the room card for existing rooms.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

