---
title: 'Lync Server 2013: настройка категорий'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure categories
ms:assetid: 4547f514-f0c0-404d-890f-092ddeeac852
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204859(v=OCS.15)
ms:contentKeyID: 48184033
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bf7b7b3ceb24e3b5bffb307cdde048e7a0cabb8c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757763"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-categories-in-lync-server-2013"></a><span data-ttu-id="389f4-102">Настройка категорий в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="389f4-102">Configure categories in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="389f4-103">_**Тема последнего изменения:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="389f4-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="389f4-104">В панели управления Lync Server 2013 можно настроить категории с помощью раздела **Категория** на странице **сохраняемый чат** .</span><span class="sxs-lookup"><span data-stu-id="389f4-104">In Lync Server 2013 Control Panel, you can use the **Category** section of the **Persistent Chat** page to configure categories.</span></span> <span data-ttu-id="389f4-105">Категория сохраняемой комнаты чата — это логическая структура Организации чатов.</span><span class="sxs-lookup"><span data-stu-id="389f4-105">A Persistent Chat room category is a logical structure for organizing chat rooms.</span></span> <span data-ttu-id="389f4-106">Категория определяет набор списков управления доступом (ACL) по умолчанию для управления пользователями и группами пользователей, которые могут создавать комнаты чата или присоединяться к ним.</span><span class="sxs-lookup"><span data-stu-id="389f4-106">A category defines a default set of access control lists (ACLs) for controlling the users and user groups who may create or join the chat rooms.</span></span> <span data-ttu-id="389f4-107">Категории можно использовать для применения этических границ между различными подразделениями в организациях.</span><span class="sxs-lookup"><span data-stu-id="389f4-107">You can use categories enforce ethical walls between different subdivisions within their organizations.</span></span>

<span data-ttu-id="389f4-108">Категории комнат чата могут содержать комнаты чата, но не другие категории.</span><span class="sxs-lookup"><span data-stu-id="389f4-108">Chat room categories may contain chat rooms, but not other categories.</span></span> <span data-ttu-id="389f4-109">Каждая категория описывает свое содержимое с помощью метаданных, таких как имя и описание.</span><span class="sxs-lookup"><span data-stu-id="389f4-109">Each category describes its contents with metadata, such as Name and Description.</span></span> <span data-ttu-id="389f4-110">Кроме того, у категории есть свойства, которые можно задать для управления поведением комнат чата этой категории, например для разрешения Invitations, File Uploads или ведения Chat History.</span><span class="sxs-lookup"><span data-stu-id="389f4-110">In addition, the category has properties which can be set to control the behavior of the chat rooms belonging to it, such as if the chat rooms allow Invitations or File Uploads, or contain Chat History.</span></span>

<div>

## <a name="to-configure-categories-for-chat-rooms"></a><span data-ttu-id="389f4-111">Настройка категорий для комнат чата</span><span class="sxs-lookup"><span data-stu-id="389f4-111">To configure categories for chat rooms</span></span>

1.  <span data-ttu-id="389f4-112">Из учетной записи пользователя, назначенной роли CsPersistentChatAdministrator или CsAdministrator, выполните вход на любой компьютер во внутреннем развертывании.</span><span class="sxs-lookup"><span data-stu-id="389f4-112">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="389f4-113">В меню **Пуск** выберите Панель управления Lync Server или откройте окно браузера и введите URL-адрес администратора.</span><span class="sxs-lookup"><span data-stu-id="389f4-113">From the **Start** menu, select the Lync Server Control Panel or open a browser window, and then enter the Admin URL.</span></span> <span data-ttu-id="389f4-114">Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="389f4-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="389f4-115">Вы также можете использовать командлеты Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="389f4-115">You can also use Windows PowerShell cmdlets.</span></span> <span data-ttu-id="389f4-116">Дополнительные сведения можно найти в разделе <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Настройка сервера сохраняемого чата с помощью командлетов Windows PowerShell</A> в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="389f4-116">For details, see <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Configuring Persistent Chat Server by using Windows PowerShell cmdlets</A> in the Deployment documentation.</span></span>

    
    </div>

3.  <span data-ttu-id="389f4-117">В левой панели навигации нажмите **Сохраняемый чат** и выберите пункт **Категория**.</span><span class="sxs-lookup"><span data-stu-id="389f4-117">In the left navigation bar, click **Persistent Chat**, and then click **Category**.</span></span>
    
    <span data-ttu-id="389f4-118">Для нескольких развертываний пула серверов с постоянным подключением выберите нужный пул из раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="389f4-118">For multiple Persistent Chat Server pool deployments, select the appropriate pool from the drop-down list.</span></span>

4.  <span data-ttu-id="389f4-119">На странице **Категория** нажмите **Создать** или **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="389f4-119">On the **Category** page, click **New** or **Edit**.</span></span>

5.  <span data-ttu-id="389f4-120">В окне **Выбор службы**выберите службу, соответствующую пулу серверов сохраняемого чата, в котором нужно создать категорию.</span><span class="sxs-lookup"><span data-stu-id="389f4-120">In **Select a Service**, select the service corresponding to the Persistent Chat Server pool on which the category needs to be created.</span></span> <span data-ttu-id="389f4-121">Служба является пулом серверов сохраняемого чата, который используется сохраняемым чат (клиентом) для определения пула, которому принадлежит Категория.</span><span class="sxs-lookup"><span data-stu-id="389f4-121">The service is the Persistent Chat Server pool that the Persistent Chat (client) uses to identify which pool the category belongs to.</span></span> <span data-ttu-id="389f4-122">Категория может состоять только из одного пула серверов сохраняемого чата, и его нельзя переместить на другой или совместно с другим пулом.</span><span class="sxs-lookup"><span data-stu-id="389f4-122">A category can belong to only one Persistent Chat Server pool, and cannot be moved to another one, or shared with another pool.</span></span>

6.  <span data-ttu-id="389f4-123">На странице **Новая категория** выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="389f4-123">In **New Category**, do the following:</span></span>
    
    1.  <span data-ttu-id="389f4-124">В поле **Имя** укажите имя новой категории комнат чата.</span><span class="sxs-lookup"><span data-stu-id="389f4-124">In **Name**, specify a name for the new room category.</span></span>
    
    2.  <span data-ttu-id="389f4-125">В поле **Описание** введите подробные сведения о категории комнат (например, категории комнат для компании Contoso).</span><span class="sxs-lookup"><span data-stu-id="389f4-125">In **Description**, provide a detailed description for the room category (for example, a room category for Contoso).</span></span>
    
    3.  <span data-ttu-id="389f4-126">Чтобы настроить возможность включения приглашений для комнат чатов, принадлежащих к этой категории, установите или снимите флажок **включить приглашения** .</span><span class="sxs-lookup"><span data-stu-id="389f4-126">To control whether invitations can be enabled for chat rooms that belong to this category, select or clear the **Enable invitations** check box.</span></span> <span data-ttu-id="389f4-127">Если этот флажок установлен, для помещения в этой категории могут быть настроены и отключены приглашения; Если флажок снят, у комнат в этой категории не может быть приглашений.</span><span class="sxs-lookup"><span data-stu-id="389f4-127">If selected, rooms in this category may have invitations on or off; if cleared, the rooms in this category are not allowed to have invitations.</span></span> <span data-ttu-id="389f4-128">Если комната поступила с приглашением, при добавлении нового участника в комнату он получает уведомление о новой комнате в его постоянном клиенте чата.</span><span class="sxs-lookup"><span data-stu-id="389f4-128">If a room has invitations on, when a new member is added to a room, he or she gets a notification of the new room in their Persistent Chat client.</span></span>
    
    4.  <span data-ttu-id="389f4-p107">Чтобы контролировать загрузку файлов в комнатах чата этой категории, установите или снимите флажок **Разрешить загрузку файлов**. Если этот флажок установлен, комнаты этой категории могут включать или отключать загрузку файлов. Если он снят, загрузка файлов для этой категории отключена.</span><span class="sxs-lookup"><span data-stu-id="389f4-p107">To control file uploads in chat rooms belonging to this category, select or clear the **Enable file upload** check box. If selected, the rooms of this category can enable or disable file uploads; if cleared, the rooms of this category are not allowed to have file uploads.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="389f4-131">Этот параметр принудительно применяется на сервере, так как пользовательские приложения или предыдущие клиенты группового чата, использующие Office Communications Server&nbsp;2007 R2 Group Chat Server или Lync Server 2010, могут публиковать файлы в комнате с помощью группового чата.</span><span class="sxs-lookup"><span data-stu-id="389f4-131">This setting is enforced on the server because custom applications or previous Group Chat clients that use Office Communications Server 2007 R2&nbsp;Group Chat Server or Lync Server 2010, Group Chat can post files to a room.</span></span> <span data-ttu-id="389f4-132">В клиенте Lync 2013 не предусмотрена возможность отправки и загрузки файлов, поэтому если у вас есть чистый клиент Lync 2013 или Lync 2013, вы не сможете отправлять файлы в записную комнату чата на сервере.</span><span class="sxs-lookup"><span data-stu-id="389f4-132">The Lync 2013 client does not have file upload/download capability, so if you have a pure Lync 2013 deployment or Lync 2013 client, it is not possible to post files in a Persistent Chat Server chat room.</span></span>

        
        </div>
    
    5.  <span data-ttu-id="389f4-133">Чтобы управлять историей чата, установите или снимите флажок **включить историю чата** .</span><span class="sxs-lookup"><span data-stu-id="389f4-133">To control chat history, select or clear the **Enable chat history** check box.</span></span> <span data-ttu-id="389f4-134">Если этот флажок установлен, беседы комнаты будут постоянными; в противном случае сообщения чата не сохраняются.</span><span class="sxs-lookup"><span data-stu-id="389f4-134">If selected, room chats become persistent; otherwise, chat messages are not persisted.</span></span> <span data-ttu-id="389f4-135">Если включено соответствие, разговоры в комнате будут сохраняться в соответствии с требованиями, но пользователи не смогут получать доступ к старым сообщениям.</span><span class="sxs-lookup"><span data-stu-id="389f4-135">If compliance is enabled, room chats will be saved in compliance, but users will not be able to access older messages.</span></span> <span data-ttu-id="389f4-136">Этот параметр можно использовать для комнат, предназначенных для совместной работы в реальном времени, которые не нуждаются в истории чата.</span><span class="sxs-lookup"><span data-stu-id="389f4-136">This option can be used for rooms designated for real-time, ad hoc collaborations that don’t need chat history to be persisted.</span></span>

7.  <span data-ttu-id="389f4-137">На странице **Изменить категорию** выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="389f4-137">In **Edit Category**, do the following:</span></span>
    
      - <span data-ttu-id="389f4-138">В разделе **Разрешенные участники** добавьте или удалите пользователей и других участников доменных служб Active Directory (пользователей, группы рассылки, подразделения и т. д. **), которые**разрешено добавлять в качестве членов комнат чата, принадлежащих к категории.</span><span class="sxs-lookup"><span data-stu-id="389f4-138">In **Membership**, in the **Allowed members** section, add or remove users and other Active Directory Domain Services principals (users, distribution groups, organizational units, and so on) that are permitted to be added as members of chat rooms belonging to the category.</span></span> <span data-ttu-id="389f4-139">Разрешенные в категории субъекты могут выполнять поиск комнат в этой категории (если только комната не является скрытой — такую комнату могут искать в каталоге только ее участники).</span><span class="sxs-lookup"><span data-stu-id="389f4-139">Principals permitted by a category can search for the rooms in the category (unless the room is hidden, in which case only members of the room can search for it in the directory).</span></span>
    
      - <span data-ttu-id="389f4-140">В разделе "участие в группе" **члены** **группы**"участники" добавляют и удаляют пользователей и других участников Active Directory, связанных с участниками, которые отклоняются из комнаты.</span><span class="sxs-lookup"><span data-stu-id="389f4-140">In **Membership**, in the **Denied members** section, add or remove users and other Active Directory principals associated with members being denied from the room.</span></span>
    
      - <span data-ttu-id="389f4-141">В разделе " **участие**" в группе " **Создатели** " добавьте или удалите пользователей и других участников Active Directory, связанных с создателями для этой категории.</span><span class="sxs-lookup"><span data-stu-id="389f4-141">In **Membership**, in the **Creators** section, add or remove users and other Active Directory principals associated with creators for the category.</span></span> <span data-ttu-id="389f4-142">Автор — это пользователь, обладающий разрешениями на создание комнат чата и назначение их диспетчеров и участников.</span><span class="sxs-lookup"><span data-stu-id="389f4-142">A creator is a user who has permissions to create chat rooms and assign chat room managers and members.</span></span>

8.  <span data-ttu-id="389f4-143">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="389f4-143">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

