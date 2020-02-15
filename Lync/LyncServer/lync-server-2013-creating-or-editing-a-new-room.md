---
title: 'Lync Server 2013: создание или изменение новой комнаты'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Creating or editing a new room
ms:assetid: aa8f4349-cfd9-4036-9c4d-de8fb2c4c8a4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215880(v=OCS.15)
ms:contentKeyID: 48706008
ms.date: 03/19/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c445513cf112b335ce900ab8e39660210f0b5ef4
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048640"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="creating-or-editing-a-new-room-in-lync-server-2013"></a><span data-ttu-id="2eed1-102">Создание или редактирование нового помещения в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2eed1-102">Creating or editing a new room in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2eed1-103">_**Последнее изменение темы:** 2015-03-19_</span><span class="sxs-lookup"><span data-stu-id="2eed1-103">_**Topic Last Modified:** 2015-03-19_</span></span>

<span data-ttu-id="2eed1-104">Настройка комнат сохраняемого чата обычно обрабатывается пользователями; Администратор сохраняемого чата обычно не настраивает и не управляет комнатами чата.</span><span class="sxs-lookup"><span data-stu-id="2eed1-104">Configuring Persistent Chat rooms is commonly handled by users; a Persistent Chat administrator typically does not configure or manage chat rooms.</span></span> <span data-ttu-id="2eed1-105">Командлеты Windows PowerShell для управления комнатами доступны только администраторам **CsPersistentChatAdministrator** .</span><span class="sxs-lookup"><span data-stu-id="2eed1-105">Windows PowerShell cmdlets to manage rooms are available only to **CsPersistentChatAdministrator** Administrators.</span></span>

<span data-ttu-id="2eed1-106">Пользователи, являющиеся **создателями** в любой категории, могут использовать клиент Lync для создания комнат и управления ими.</span><span class="sxs-lookup"><span data-stu-id="2eed1-106">Users who are **Creators** in any given category can use the Lync client to create and manage rooms.</span></span> <span data-ttu-id="2eed1-107">Пользователи, назначенные в качестве управляющих определенной комнаты чата, также могут выполнять текущие задачи управления этой комнатой, например изменять ее свойства или параметры членства.</span><span class="sxs-lookup"><span data-stu-id="2eed1-107">Users who have been designated as managers for a specific chat room can also perform ongoing management of the room, such as editing the room properties or membership.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="2eed1-108">Администраторы сохраняемого чата также могут быть авторами и не подвержены ограничениям, наложенным на авторов.</span><span class="sxs-lookup"><span data-stu-id="2eed1-108">Persistent Chat administrators can also be Creators, and they are not subject to the restrictions placed on Creators.</span></span>



</div>

<span data-ttu-id="2eed1-109">Кроме того, если вы являетесь администратором сохраняемого чата, вы можете использовать пользовательский интерфейс для создания комнат чата и управления ими, а не с помощью командлетов Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2eed1-109">Optionally, if you are a Persistent Chat administrator, you can employ a user interface to create and manage chat rooms instead of using Windows PowerShell cmdlets.</span></span> <span data-ttu-id="2eed1-110">Для этого необходимо включить поддержку SIP для сервера сохраняемого чата, а затем использовать клиент Lync для создания комнат чата и управления ими.</span><span class="sxs-lookup"><span data-stu-id="2eed1-110">To do this, SIP-enable an administrator for Persistent Chat Server, and then use the Lync client to create and manage chat rooms.</span></span>

<span data-ttu-id="2eed1-111">Если вы хотите создать настраиваемый рабочий процесс управления комнатой для пользователей, вы можете задать свойство **румманажементурл** в конфигурации сервера сохраняемого чата, чтобы перенаправить пользователей на ваше решение из клиента Lync.</span><span class="sxs-lookup"><span data-stu-id="2eed1-111">If you want to create a custom room management workflow for your users, you can set the **RoomManagementUrl** property on your Persistent Chat Server configuration to redirect users to your custom solution from the Lync client.</span></span>

<span data-ttu-id="2eed1-112">Дополнительные сведения о настройке комнат чата с помощью интерфейса командной строки Windows PowerShell можно найти в разделе Управление комнатой в разделе [Настройка сервера сохраняемого чата с помощью командлетов Windows PowerShell](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).</span><span class="sxs-lookup"><span data-stu-id="2eed1-112">For details about configuring chat rooms by using the Windows PowerShell command-line interface, see "Room Management" in [Configuring Persistent Chat Server by using Windows PowerShell cmdlets](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).</span></span>

<span data-ttu-id="2eed1-113">Дополнительные сведения о настройке комнат чата приведены в статье [Configure комнаты в Lync Server 2013](lync-server-2013-configure-rooms.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="2eed1-113">For details about configuring chat rooms, see [Configure rooms in Lync Server 2013](lync-server-2013-configure-rooms.md) in the Deployment documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2eed1-114">Сервер сохраняемого чата позволяет пользователям создавать комнаты чата для определенного сайта и управлять ими.</span><span class="sxs-lookup"><span data-stu-id="2eed1-114">Persistent Chat Server lets users create and manage chat room for a specific site.</span></span> <span data-ttu-id="2eed1-115">Однако пользователи не могут создавать комнаты чата и управлять ими на других сайтах в одной и той же топологии.</span><span class="sxs-lookup"><span data-stu-id="2eed1-115">Users cannot, however, create or manage chat rooms on other sites within the same topology.</span></span> <span data-ttu-id="2eed1-116">Не забудьте указать создатели и менеджеры комнаты чата для всех сайтов в Организации.</span><span class="sxs-lookup"><span data-stu-id="2eed1-116">Be sure to specify chat room Creators and Managers for all the sites in your organization.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="2eed1-117">Пользователи, размещенные на устройстве для обеспечения связи в филиалах Lync Server, не могут создавать новые комнаты чата или просматривать карточку комнаты для существующих комнат.</span><span class="sxs-lookup"><span data-stu-id="2eed1-117">Users who are homed on a Lync Server Survivable Branch Appliance are unable to create new chat rooms or view the room card for existing rooms.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

