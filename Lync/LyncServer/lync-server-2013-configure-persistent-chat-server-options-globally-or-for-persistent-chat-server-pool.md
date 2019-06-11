---
title: 'Lync Server 2013: настройка параметров сервера сохраняемого чата на глобальном уровне или для пула сервера сохраняемого чата'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure Persistent Chat Server options globally or for Persistent Chat Server pool
ms:assetid: 1e8d5245-cd58-4aad-9a1c-35b24189bc40
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204731(v=OCS.15)
ms:contentKeyID: 48183581
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ed79d1144c1ccb7abeac8dcf7d1f4d44c63e93e5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841355"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool-in-lync-server-2013"></a><span data-ttu-id="50f1b-102">Настройка параметров сервера сохраняемого чата на глобальном уровне или для пула сервера сохраняемого чата в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="50f1b-102">Configure Persistent Chat Server options globally or for Persistent Chat Server pool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="50f1b-103">_**Тема последнего изменения:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="50f1b-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="50f1b-104">В панели управления Lync Server 2013 вы можете использовать раздел **Настройка сохраняемого чата** на странице **сохраняемый чат** , чтобы настроить параметры сохраняемого чата, в которых они применяются ко всем пулам серверов для сохраняемого чата, или для определенного Пул серверов сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="50f1b-104">In Lync Server 2013 Control Panel, you can use the **Persistent Chat Configuration** section of the **Persistent Chat** page to configure Persistent Chat settings globally where it applies to all Persistent Chat Server pools, or for a specific Persistent Chat Server pool.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="50f1b-105">Чтобы настроить и использовать сохраняемый сервер чата, необходимо сначала использовать Topology Builder, чтобы добавить в топологию постоянную поддержку сервера чата, а затем опубликовать топологию.</span><span class="sxs-lookup"><span data-stu-id="50f1b-105">To configure and use Persistent Chat Server, you must first use Topology Builder to add Persistent Chat Server support to the topology, and then publish the topology.</span></span> <span data-ttu-id="50f1b-106">Подробные сведения о том, <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">как добавить сохраняемый сервер чата в развертывание в среде Lync server 2013, можно</A> найти в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="50f1b-106">For details, see <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Adding Persistent Chat Server to your deployment in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="to-configure-persistent-chat-options-globally"></a><span data-ttu-id="50f1b-107">Как настроить параметры сохраняемого чата глобально</span><span class="sxs-lookup"><span data-stu-id="50f1b-107">To configure Persistent Chat options globally</span></span>

1.  <span data-ttu-id="50f1b-108">Из учетной записи пользователя, назначенной роли CsPersistentChatAdministrator или CsAdministrator, выполните вход на любой компьютер во внутреннем развертывании.</span><span class="sxs-lookup"><span data-stu-id="50f1b-108">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="50f1b-109">В меню **Пуск** выберите Панель управления Lync Server или откройте окно браузера и введите URL-адрес администратора.</span><span class="sxs-lookup"><span data-stu-id="50f1b-109">From the **Start** menu, select the Lync Server Control Panel or open a browser window, and then enter the Admin URL.</span></span> <span data-ttu-id="50f1b-110">Дополнительные сведения о различных способах запуска панели управления Lync Server можно найти в разделе [Открытие средства администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="50f1b-110">For details about the different methods that you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="50f1b-111">Вы также можете использовать командлеты Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="50f1b-111">You can also use Windows PowerShell cmdlets.</span></span> <span data-ttu-id="50f1b-112">Дополнительные сведения можно найти в разделе <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Настройка сервера сохраняемого чата с помощью командлетов Windows PowerShell</A> в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="50f1b-112">For details, see <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Configuring Persistent Chat Server by using Windows PowerShell cmdlets</A> in the Deployment documentation.</span></span>

    
    </div>

3.  <span data-ttu-id="50f1b-113">В левой панели навигации нажмите **Сохраняемый чат** и выберите пункт **Настройка сохраняемого чата**.</span><span class="sxs-lookup"><span data-stu-id="50f1b-113">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Configuration**.</span></span>

4.  <span data-ttu-id="50f1b-114">На странице **Конфигурация сохраняемого чата** нажмите кнопку **создать** и выберите пункт **Конфигурация сайта**.</span><span class="sxs-lookup"><span data-stu-id="50f1b-114">On the **Persistent Chat Configuration** page, click **New,** and then click **Site configuration**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="50f1b-115">Выберите этот параметр, если вы хотите, чтобы конфигурация была применена ко всем пулам серверов для постоянного чата, развернутым на сайте.</span><span class="sxs-lookup"><span data-stu-id="50f1b-115">Choose this option if you want the configuration to be applied to all Persistent Chat Server pools deployed in the site.</span></span> <span data-ttu-id="50f1b-116">Нажмите кнопку <STRONG>Конфигурация пула</STRONG> , чтобы настроить конфигурацию для определенного пула серверов сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="50f1b-116">Click <STRONG>Pool Configuration</STRONG> if you want the configuration to be applied to a specific Persistent Chat Server pool.</span></span>

    
    </div>

5.  <span data-ttu-id="50f1b-117">В списке **выберите сайт**выберите сайт, который нужно настроить для конфигурации сервера сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="50f1b-117">In **Select a Site**, select the site to be configured for the Persistent Chat Server site configuration.</span></span>

6.  <span data-ttu-id="50f1b-118">В окне **Создание конфигурации сохраняемого чата** выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="50f1b-118">In **New Persistent Chat Configuration**, do the following:</span></span>
    
      - <span data-ttu-id="50f1b-p105">В разделе **Имя** укажите имя новых параметров конфигурации. Имя сайта уже задано по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="50f1b-p105">In **Name**, specify a name for the new configuration settings. By default, the site name already exists.</span></span>
    
      - <span data-ttu-id="50f1b-p106">В разделе **Журнал сообщений чата** задайте количество сообщений чата, которые будут обрабатываться по первому запросу для каждой комнаты. По умолчанию задано значение 30. Это глобальное значение по умолчанию; администраторы могут отключать журнал сообщений чата по категориям.</span><span class="sxs-lookup"><span data-stu-id="50f1b-p106">In **Default chat history**, define the number of chat messages that will be processed for each room upon first request. By default, the number is 30. This is the global default, and administrators can disable chat history per category.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="50f1b-124">Сервер сохраняемого чата кэширует эти сообщения в памяти, поэтому, если увеличить этот номер, будет кэшировано больше сообщений.</span><span class="sxs-lookup"><span data-stu-id="50f1b-124">Persistent Chat Server will cache these messages in memory, so if you increase this number, more messages will be cached.</span></span> <span data-ttu-id="50f1b-125">Вы всегда можете получить доступ к историческому контенту с помощью поиска.</span><span class="sxs-lookup"><span data-stu-id="50f1b-125">You can always access historical content by search.</span></span> <span data-ttu-id="50f1b-126">Число по умолчанию просто определяет максимальное число сообщений, которые изначально отображаются при подключении к комнате чата.</span><span class="sxs-lookup"><span data-stu-id="50f1b-126">The default number simply determines the maximum number of messages that you initially see when connecting to a chat room.</span></span>

        
        </div>
    
      - <span data-ttu-id="50f1b-p108">В разделе **Максимальный размер файла (КБ)** выберите максимальный размер файла для каждого журнала сообщений чата. По умолчанию установлено значение 20 МБ (20 000 КБ). Это максимальный размер файла, который можно отправить в любую комнату чата в системе (для которой разрешена загрузка файлов по соответствующему параметру **Категория**).</span><span class="sxs-lookup"><span data-stu-id="50f1b-p108">In **Maximum file size (KB)**, select the maximum file size of each chat history. By default, the number is 20 MB (20,000 KB). This is the maximum size for a file that can be uploaded to any chat room in the system (for which file uploads are enabled by its corresponding **Category** setting).</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="50f1b-130">Этот параметр принудительно применяется на сервере, так как пользовательские приложения или предыдущие клиенты группового чата используют Office Communications Server&nbsp;2007 R2 Group Chat Server или Lync Server 2010, групповой чат может публиковать файлы в комнате.</span><span class="sxs-lookup"><span data-stu-id="50f1b-130">This setting is enforced on the server because custom applications or previous Group Chat clients using Office Communications Server 2007 R2&nbsp;Group Chat Server or Lync Server 2010, Group Chat can post files to a room.</span></span> <span data-ttu-id="50f1b-131">В клиенте Lync 2013 не предусмотрена возможность отправки и загрузки файлов, поэтому если у вас есть чистый клиент Lync 2013 или Lync 2013, вы не сможете отправлять файлы в записную комнату чата на сервере.</span><span class="sxs-lookup"><span data-stu-id="50f1b-131">The Lync 2013 client does not have file upload/download capability, so if you have a pure Lync 2013 deployment or Lync 2013 client, it is not possible to post files in a Persistent Chat Server chat room.</span></span>

        
        </div>
    
      - <span data-ttu-id="50f1b-132">В разделе **Лимит для обновлений участников** выберите значение лимита для обновлений участников.</span><span class="sxs-lookup"><span data-stu-id="50f1b-132">In **Participant update limit**, select the limit for participant updates.</span></span> <span data-ttu-id="50f1b-133">Сервер сохраняемого чата отправляет сведения о себе (кто подключен к комнате чата) всем участникам, пока количество подключенных пользователей не достигнет этого номера.</span><span class="sxs-lookup"><span data-stu-id="50f1b-133">Persistent Chat Server sends roster information (who is connected to a chat room) to all participants until the number of connected users reaches this number.</span></span> <span data-ttu-id="50f1b-134">По умолчанию установлено значение 75.</span><span class="sxs-lookup"><span data-stu-id="50f1b-134">By default, the number is 75.</span></span> <span data-ttu-id="50f1b-135">Этот предел указывает на максимальное количество участников в заданной комнате, помимо которых сервер сохраняемого чата прекращает отправлять обновления списка подключенным клиентам о том, кто присутствует в комнате.</span><span class="sxs-lookup"><span data-stu-id="50f1b-135">This limit indicates the maximum number of participants in a given room beyond which Persistent Chat Server stops sending roster updates to connected clients about who is present in the room.</span></span>
    
      - <span data-ttu-id="50f1b-p111">(Необязательно.) В поле **URL-адрес управления комнатой** выберите URL-адрес управления комнатой. Это адрес для веб-управления комнатами. Если вам не нужно настраивать функции управления и вы просто используете параметр по умолчанию, оставьте это поле пустым. После установки URL-адреса он применяется как внешний и внутренний URL-адрес управления комнатой.</span><span class="sxs-lookup"><span data-stu-id="50f1b-p111">(Optional.) In **Room management URL**, select the room management URL. This is the URL for a web-based custom room management. If you don’t need to customize room management, and you simply use the default setting, leave this option blank. After the URL is set, it is applied as both the internal and external room management URL.</span></span>
        
        <span data-ttu-id="50f1b-140">Если вы хотите настроить интерфейс создания комнаты и включить свой бизнес-процесс, вы можете создать собственное решение для управления комнатой, используя пакет средств разработки программного обеспечения (SDK) сервера сохраняемого чата, разместить его где угодно и поместить здесь URL-адрес.</span><span class="sxs-lookup"><span data-stu-id="50f1b-140">If you want to customize your room creation experience and include your specific business workflow, you can build a custom room management solution by using the Persistent Chat Server Software Development Kit (SDK), host it somewhere, and put the URL here.</span></span> <span data-ttu-id="50f1b-141">Этот URL-адрес отправляется клиенту, чтобы при попытке просмотра или создания комнаты пользователю предлагалось использовать ваше настраиваемое решение для управления комнатами.</span><span class="sxs-lookup"><span data-stu-id="50f1b-141">This URL is sent down to the client, so that when a user tries to view or create a room, he or she is directed to your custom room management solution.</span></span>

7.  <span data-ttu-id="50f1b-142">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="50f1b-142">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-configure-persistent-chat-options-for-a-specific-persistent-chat-server-pool"></a><span data-ttu-id="50f1b-143">Настройка параметров сохраняемого чата для определенного пула серверов сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="50f1b-143">To configure Persistent Chat options for a specific Persistent Chat Server pool</span></span>

1.  <span data-ttu-id="50f1b-144">Из учетной записи пользователя, назначенной роли CsPersistentChatAdministrator или CsAdministrator, выполните вход на любой компьютер во внутреннем развертывании.</span><span class="sxs-lookup"><span data-stu-id="50f1b-144">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="50f1b-145">В меню **Пуск** выберите Панель управления Lync Server или откройте окно браузера и введите URL-адрес администратора.</span><span class="sxs-lookup"><span data-stu-id="50f1b-145">From the **Start** menu, select the Lync Server Control Panel, or open a browser window, and then enter the Admin URL.</span></span> <span data-ttu-id="50f1b-146">Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="50f1b-146">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="50f1b-147">Вы также можете использовать командлеты Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="50f1b-147">You can also use Windows PowerShell cmdlets.</span></span> <span data-ttu-id="50f1b-148">Дополнительные сведения можно найти в разделе <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Настройка сервера сохраняемого чата с помощью командлетов Windows PowerShell</A> в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="50f1b-148">For details, see <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Configuring Persistent Chat Server by using Windows PowerShell cmdlets</A> in the Deployment documentation.</span></span>

    
    </div>

3.  <span data-ttu-id="50f1b-149">В левой панели навигации нажмите **Сохраняемый чат** и выберите пункт **Настройка сохраняемого чата**.</span><span class="sxs-lookup"><span data-stu-id="50f1b-149">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Configuration**.</span></span>

4.  <span data-ttu-id="50f1b-150">На странице **Настройка сохраняемого чата** нажмите кнопку **Создать** и выберите **Настройка пула**.</span><span class="sxs-lookup"><span data-stu-id="50f1b-150">On the **Persistent Chat Configuration** page, click **New**, and then click **Pool configuration**.</span></span>

5.  <span data-ttu-id="50f1b-151">В окне **Выбор службы**выберите службу, связанную с пулом серверов сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="50f1b-151">In **Select a Service**, select the service associated with the Persistent Chat Server pool to be configured.</span></span>

6.  <span data-ttu-id="50f1b-152">В окне **Создание конфигурации сохраняемого чата** выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="50f1b-152">In **New Persistent Chat Configuration**, do the following:</span></span>
    
      - <span data-ttu-id="50f1b-p115">В поле **Имя** введите имя новой конфигурации параметров. По умолчанию имя пула уже существует.</span><span class="sxs-lookup"><span data-stu-id="50f1b-p115">In **Name**, specify a name for the new configuration settings. By default, the site pool name already exists.</span></span>
    
      - <span data-ttu-id="50f1b-p116">В разделе **Журнал сообщений чата** задайте количество сообщений чата, которые будут обрабатываться по первому запросу для каждой комнаты. По умолчанию задано значение 30. Это глобальное значение по умолчанию; администраторы могут отключать журнал сообщений чата по категориям.</span><span class="sxs-lookup"><span data-stu-id="50f1b-p116">In **Default chat history**, define the number of chat messages that will be processed for each room upon first request. By default, the number is 30. This is the global default, and administrators can disable chat history per category.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="50f1b-158">Сервер сохраняемого чата кэширует эти сообщения в памяти, поэтому, если увеличить этот номер, будет кэшировано больше сообщений.</span><span class="sxs-lookup"><span data-stu-id="50f1b-158">Persistent Chat Server will cache these messages in memory, so if you increase this number, more messages will be cached.</span></span> <span data-ttu-id="50f1b-159">Вы всегда можете получить доступ к историческому контенту с помощью поиска.</span><span class="sxs-lookup"><span data-stu-id="50f1b-159">You can always access historical content by search.</span></span> <span data-ttu-id="50f1b-160">Число по умолчанию просто определяет максимальное число сообщений, которые изначально отображаются при подключении к комнате чата.</span><span class="sxs-lookup"><span data-stu-id="50f1b-160">The default number simply determines the maximum number of messages that you initially see when connecting to a chat room.</span></span>

        
        </div>
    
      - <span data-ttu-id="50f1b-p118">В разделе **Максимальный размер файла (КБ)** выберите максимальный размер файла для каждого журнала сообщений чата. По умолчанию установлено значение 20 МБ (20 000 КБ). Это максимальный размер файла, который можно отправить в любую комнату чата в системе (для которой разрешена загрузка файлов по соответствующему параметру **Категория**).</span><span class="sxs-lookup"><span data-stu-id="50f1b-p118">In **Maximum file size (KB)**, select the maximum file size of each chat history. By default, the number is 20 MB (20,000 KB). This is the maximum size for a file that can be uploaded to any chat room in the system (for which file uploads are enabled by its corresponding **Category** setting).</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="50f1b-164">Этот параметр принудительно применяется на сервере, поскольку пользовательские приложения или предыдущие клиенты группового чата (Office Communications Server 2007&nbsp;R2 Group Chat Server или Lync Server 2010, групповой чат) могут публиковать файлы в комнате.</span><span class="sxs-lookup"><span data-stu-id="50f1b-164">This setting is enforced on the server because custom applications or previous Group Chat clients (Office Communications Server 2007 R2&nbsp;Group Chat Server or Lync Server 2010, Group Chat) can post files to a room.</span></span> <span data-ttu-id="50f1b-165">В клиенте Lync 2013 не предусмотрена возможность отправки и загрузки файлов, поэтому если у вас есть чистый клиент Lync 2013 или Lync 2013, вы не сможете отправлять файлы в записную комнату чата на сервере.</span><span class="sxs-lookup"><span data-stu-id="50f1b-165">The Lync 2013 client does not have file upload/download capability, so if you have a pure Lync 2013 deployment or Lync 2013 client, it is not possible to post files in a Persistent Chat Server chat room.</span></span>

        
        </div>
    
      - <span data-ttu-id="50f1b-166">В разделе **Лимит для обновлений участников** выберите значение лимита для обновлений участников.</span><span class="sxs-lookup"><span data-stu-id="50f1b-166">In **Participant update limit**, select the limit for participant updates.</span></span> <span data-ttu-id="50f1b-167">Сервер сохраняемого чата отправляет сведения о себе (кто подключен к комнате чата) всем участникам, пока количество подключенных пользователей не достигнет этого номера.</span><span class="sxs-lookup"><span data-stu-id="50f1b-167">Persistent Chat Server sends roster information (who is connected to a chat room) to all participants until the number of connected users reaches this number.</span></span> <span data-ttu-id="50f1b-168">По умолчанию установлено значение 75.</span><span class="sxs-lookup"><span data-stu-id="50f1b-168">By default, the number is 75.</span></span> <span data-ttu-id="50f1b-169">Этот предел указывает на максимальное количество участников в заданной комнате, помимо которых сервер сохраняемого чата прекращает отправлять обновления списка подключенным клиентам о том, кто присутствует в комнате.</span><span class="sxs-lookup"><span data-stu-id="50f1b-169">This limit indicates the maximum number of participants in a given room beyond which Persistent Chat Server stops sending roster updates to connected clients about who is present in the room.</span></span>
    
      - <span data-ttu-id="50f1b-p121">В поле **URL-адрес управления комнатой** выберите URL-адрес управления комнатой. Это URL-адрес для развертывания веб-управления комнатами. Если вам не нужно настраивать функции управления комнатами и вы просто используете настройку по умолчанию, оставьте это поле пустым.</span><span class="sxs-lookup"><span data-stu-id="50f1b-p121">In **Room management URL**, select the room management URL. This is the URL for a web-based room management deployment. If you don’t need to customize room management, and you simply use the default setting, leave this option blank.</span></span>
        
        <span data-ttu-id="50f1b-173">Если вы хотите настроить интерфейс создания комнаты и включить свой бизнес-процесс, вы можете создать собственное решение для управления комнатой, используя пакет средств разработки программного обеспечения (SDK) сервера сохраняемого чата, разместить его где угодно и поместить здесь URL-адрес.</span><span class="sxs-lookup"><span data-stu-id="50f1b-173">If you want to customize your room creation experience and include your specific business workflow, you can build a custom room management solution by using the Persistent Chat Server Software Development Kit (SDK), host it somewhere, and put the URL here.</span></span> <span data-ttu-id="50f1b-174">Этот URL-адрес отправляется клиенту, чтобы при попытке просмотра или создания комнаты пользователю предлагалось использовать ваше настраиваемое решение для управления комнатами.</span><span class="sxs-lookup"><span data-stu-id="50f1b-174">This URL is sent down to the client so that when a user tries to view/create a room, he or she is directed to your custom room management solution.</span></span>

7.  <span data-ttu-id="50f1b-175">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="50f1b-175">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

