---
title: 'Lync Server 2013: Настройка параметров сервера сохраняемого чата на глобальном уровне или для пула сервера сохраняемого чата'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure Persistent Chat Server options globally or for Persistent Chat Server pool
ms:assetid: 1e8d5245-cd58-4aad-9a1c-35b24189bc40
ms:mtpsurl: https://technet.microsoft.com/library/JJ204731(v=OCS.15)
ms:contentKeyID: 48183581
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6a9cadd23099dbcaee5c577705ca1c2e4bdf6c00
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48520466"
---
# <a name="configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool-in-lync-server-2013"></a><span data-ttu-id="1536d-102">Настройка параметров сервера сохраняемого чата на глобальном уровне или для пула сервера сохраняемого чата в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1536d-102">Configure Persistent Chat Server options globally or for Persistent Chat Server pool in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1536d-103">_**Последнее изменение темы:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="1536d-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="1536d-104">В панели управления Lync Server 2013 вы можете использовать раздел **Настройка сохраняемого** чата на странице **сохраняемого чата** , чтобы настроить параметры сохраняемого чата глобально, где они применяются ко всем пулам серверов сохраняемого чата, или для определенного пула серверов сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="1536d-104">In Lync Server 2013 Control Panel, you can use the **Persistent Chat Configuration** section of the **Persistent Chat** page to configure Persistent Chat settings globally where it applies to all Persistent Chat Server pools, or for a specific Persistent Chat Server pool.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1536d-105">Чтобы настроить и использовать сервер сохраняемого чата, сначала необходимо использовать построитель топологий, чтобы добавить в топологию поддержку сервера сохраняемого чата, а затем опубликовать топологию.</span><span class="sxs-lookup"><span data-stu-id="1536d-105">To configure and use Persistent Chat Server, you must first use Topology Builder to add Persistent Chat Server support to the topology, and then publish the topology.</span></span> <span data-ttu-id="1536d-106">Дополнительные сведения см. в статье <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Добавление сервера сохраняемого чата в развертывание в Lync Server 2013</A> в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="1536d-106">For details, see <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Adding Persistent Chat Server to your deployment in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="to-configure-persistent-chat-options-globally"></a><span data-ttu-id="1536d-107">Настройка параметров сохраняемого чата на глобальном уровне</span><span class="sxs-lookup"><span data-stu-id="1536d-107">To configure Persistent Chat options globally</span></span>

1.  <span data-ttu-id="1536d-108">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsPersistentChatAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="1536d-108">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="1536d-109">В меню **Пуск** выберите Панель управления Lync Server или откройте окно браузера и введите URL-адрес администрирования.</span><span class="sxs-lookup"><span data-stu-id="1536d-109">From the **Start** menu, select the Lync Server Control Panel or open a browser window, and then enter the Admin URL.</span></span> <span data-ttu-id="1536d-110">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="1536d-110">For details about the different methods that you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="1536d-111">Вы также можете использовать командлеты Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1536d-111">You can also use Windows PowerShell cmdlets.</span></span> <span data-ttu-id="1536d-112">Дополнительные сведения: <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Настройка сервера сохраняемого чата с помощью командлетов Windows PowerShell,</A> описанных в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="1536d-112">For details, see <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Configuring Persistent Chat Server by using Windows PowerShell cmdlets</A> in the Deployment documentation.</span></span>

    
    </div>

3.  <span data-ttu-id="1536d-113">В левой панели навигации щелкните **Сохраняемый чат** и выберите пункт **Настройка сохраняемого чата**.</span><span class="sxs-lookup"><span data-stu-id="1536d-113">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Configuration**.</span></span>

4.  <span data-ttu-id="1536d-114">На странице **Настройка сохраняемого чата** нажмите кнопку **создать** и выберите **Конфигурация сайта**.</span><span class="sxs-lookup"><span data-stu-id="1536d-114">On the **Persistent Chat Configuration** page, click **New,** and then click **Site configuration**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="1536d-115">Выберите этот параметр, если вы хотите применить конфигурацию ко всем пулам серверов сохраняемого чата, развернутым на сайте.</span><span class="sxs-lookup"><span data-stu-id="1536d-115">Choose this option if you want the configuration to be applied to all Persistent Chat Server pools deployed in the site.</span></span> <span data-ttu-id="1536d-116">Щелкните <STRONG>Конфигурация пула</STRONG> , если необходимо применить конфигурацию к определенному пулу серверов сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="1536d-116">Click <STRONG>Pool Configuration</STRONG> if you want the configuration to be applied to a specific Persistent Chat Server pool.</span></span>

    
    </div>

5.  <span data-ttu-id="1536d-117">В разделе **Выбор сайта**выберите сайт, который нужно настроить для конфигурации сайта сервера сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="1536d-117">In **Select a Site**, select the site to be configured for the Persistent Chat Server site configuration.</span></span>

6.  <span data-ttu-id="1536d-118">В окне **Создание конфигурации сохраняемого чата** выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="1536d-118">In **New Persistent Chat Configuration**, do the following:</span></span>
    
      - <span data-ttu-id="1536d-p105">В поле **Имя** введите имя новой конфигурации. По умолчанию имя сайта уже существует.</span><span class="sxs-lookup"><span data-stu-id="1536d-p105">In **Name**, specify a name for the new configuration settings. By default, the site name already exists.</span></span>
    
      - <span data-ttu-id="1536d-p106">В поле **Журнал чата по умолчанию** укажите число сообщений чата, который будут обрабатываться для каждой комнаты по первому запросу. Номер порта по умолчанию — 30. Это глобальный параметр по умолчанию, администраторы могут отключить журнал чата для категории.</span><span class="sxs-lookup"><span data-stu-id="1536d-p106">In **Default chat history**, define the number of chat messages that will be processed for each room upon first request. By default, the number is 30. This is the global default, and administrators can disable chat history per category.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="1536d-124">Сервер сохраняемого чата кэширует эти сообщения в памяти, поэтому при увеличении этого числа будет кэшироваться больше сообщений.</span><span class="sxs-lookup"><span data-stu-id="1536d-124">Persistent Chat Server will cache these messages in memory, so if you increase this number, more messages will be cached.</span></span> <span data-ttu-id="1536d-125">Вы всегда можете получить доступ к историческому контенту с помощью поиска.</span><span class="sxs-lookup"><span data-stu-id="1536d-125">You can always access historical content by search.</span></span> <span data-ttu-id="1536d-126">Число по умолчанию просто определяет максимальное число сообщений, которые изначально отображаются при подключении к комнате чата.</span><span class="sxs-lookup"><span data-stu-id="1536d-126">The default number simply determines the maximum number of messages that you initially see when connecting to a chat room.</span></span>

        
        </div>
    
      - <span data-ttu-id="1536d-p108">В поле **Максимальный размер файла (КБ)** выберите максимальный размер файла журнала каждого чата. Размер файла по умолчанию — 20 МБ (20 000 КБ). Это максимальный размер файла, который можно загрузить в любую комнату чата в системе (для которой загрузка файлов разрешена соответствующим параметром **Категория**).</span><span class="sxs-lookup"><span data-stu-id="1536d-p108">In **Maximum file size (KB)**, select the maximum file size of each chat history. By default, the number is 20 MB (20,000 KB). This is the maximum size for a file that can be uploaded to any chat room in the system (for which file uploads are enabled by its corresponding **Category** setting).</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="1536d-130">Этот параметр применяется на сервере, так как пользовательские приложения или предыдущие клиенты группового чата с помощью Office Communications Server 2007 R2 &nbsp; Group Chat Server или Lync server 2010, группового чата могут отправлять файлы в комнату.</span><span class="sxs-lookup"><span data-stu-id="1536d-130">This setting is enforced on the server because custom applications or previous Group Chat clients using Office Communications Server 2007 R2&nbsp;Group Chat Server or Lync Server 2010, Group Chat can post files to a room.</span></span> <span data-ttu-id="1536d-131">У клиента Lync 2013 нет возможности отправки и загрузки файлов, поэтому при наличии чистого клиента Lync 2013 или Lync 2013 невозможно разместить файлы в комнате чата сервера сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="1536d-131">The Lync 2013 client does not have file upload/download capability, so if you have a pure Lync 2013 deployment or Lync 2013 client, it is not possible to post files in a Persistent Chat Server chat room.</span></span>

        
        </div>
    
      - <span data-ttu-id="1536d-132">В поле **Предельное значение обновления участников** выберите предел для обновления участников.</span><span class="sxs-lookup"><span data-stu-id="1536d-132">In **Participant update limit**, select the limit for participant updates.</span></span> <span data-ttu-id="1536d-133">Сервер сохраняемого чата отправляет сведения о списке (которые подключены к комнате чата) всем участникам до тех пор, пока число подключенных пользователей не достигнет этого числа.</span><span class="sxs-lookup"><span data-stu-id="1536d-133">Persistent Chat Server sends roster information (who is connected to a chat room) to all participants until the number of connected users reaches this number.</span></span> <span data-ttu-id="1536d-134">Значение по умолчанию — 75.</span><span class="sxs-lookup"><span data-stu-id="1536d-134">By default, the number is 75.</span></span> <span data-ttu-id="1536d-135">Это ограничение указывает максимальное число участников в заданном помещении, за исключением которых сервер сохраняемого чата перестает отправлять обновления списка подключенным клиентам о пользователях, присутствующих в комнате.</span><span class="sxs-lookup"><span data-stu-id="1536d-135">This limit indicates the maximum number of participants in a given room beyond which Persistent Chat Server stops sending roster updates to connected clients about who is present in the room.</span></span>
    
      - <span data-ttu-id="1536d-p111">(Необязательно.) В поле **URL-адрес управления комнатой** выберите URL-адрес управления комнатой. Это адрес для веб-управления комнатами. Если вам не нужно настраивать функции управления и вы просто используете параметр по умолчанию, оставьте это поле пустым. После установки URL-адреса он применяется как внешний и внутренний URL-адрес управления комнатой.</span><span class="sxs-lookup"><span data-stu-id="1536d-p111">(Optional.) In **Room management URL**, select the room management URL. This is the URL for a web-based custom room management. If you don’t need to customize room management, and you simply use the default setting, leave this option blank. After the URL is set, it is applied as both the internal and external room management URL.</span></span>
        
        <span data-ttu-id="1536d-140">Если вы хотите настроить интерфейс создания комнаты и включить свой бизнес-процесс, вы можете создать настраиваемое решение для управления комнатами с помощью пакета SDK сервера сохраняемого чата (SDK), разместить его в любом месте и разместить здесь URL-адрес здесь.</span><span class="sxs-lookup"><span data-stu-id="1536d-140">If you want to customize your room creation experience and include your specific business workflow, you can build a custom room management solution by using the Persistent Chat Server Software Development Kit (SDK), host it somewhere, and put the URL here.</span></span> <span data-ttu-id="1536d-141">Он передается клиенту, чтобы, когда пользователи пытались просмотреть или создать комнату, они перенаправлялись в ваше настраиваемое решение.</span><span class="sxs-lookup"><span data-stu-id="1536d-141">This URL is sent down to the client, so that when a user tries to view or create a room, he or she is directed to your custom room management solution.</span></span>

7.  <span data-ttu-id="1536d-142">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="1536d-142">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-configure-persistent-chat-options-for-a-specific-persistent-chat-server-pool"></a><span data-ttu-id="1536d-143">Настройка параметров сохраняемого чата для определенного пула серверов сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="1536d-143">To configure Persistent Chat options for a specific Persistent Chat Server pool</span></span>

1.  <span data-ttu-id="1536d-144">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsPersistentChatAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="1536d-144">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="1536d-145">В меню **Пуск** выберите Панель управления Lync Server или откройте окно браузера и введите URL-адрес администрирования.</span><span class="sxs-lookup"><span data-stu-id="1536d-145">From the **Start** menu, select the Lync Server Control Panel, or open a browser window, and then enter the Admin URL.</span></span> <span data-ttu-id="1536d-146">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="1536d-146">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="1536d-147">Вы также можете использовать командлеты Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1536d-147">You can also use Windows PowerShell cmdlets.</span></span> <span data-ttu-id="1536d-148">Дополнительные сведения: <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Настройка сервера сохраняемого чата с помощью командлетов Windows PowerShell,</A> описанных в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="1536d-148">For details, see <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Configuring Persistent Chat Server by using Windows PowerShell cmdlets</A> in the Deployment documentation.</span></span>

    
    </div>

3.  <span data-ttu-id="1536d-149">В левой панели навигации щелкните **Сохраняемый чат** и выберите пункт **Настройка сохраняемого чата**.</span><span class="sxs-lookup"><span data-stu-id="1536d-149">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Configuration**.</span></span>

4.  <span data-ttu-id="1536d-150">На странице **Настройка сохраняемого чата** нажмите кнопку **Создать** и щелкните **Настройка пула**.</span><span class="sxs-lookup"><span data-stu-id="1536d-150">On the **Persistent Chat Configuration** page, click **New**, and then click **Pool configuration**.</span></span>

5.  <span data-ttu-id="1536d-151">В разделе **Выбор службы**выберите службу, связанную с настроенным пулом серверов сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="1536d-151">In **Select a Service**, select the service associated with the Persistent Chat Server pool to be configured.</span></span>

6.  <span data-ttu-id="1536d-152">В окне **Создание конфигурации сохраняемого чата** выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="1536d-152">In **New Persistent Chat Configuration**, do the following:</span></span>
    
      - <span data-ttu-id="1536d-p115">В поле **Имя** введите имя новой конфигурации. По умолчанию имя пула уже существует.</span><span class="sxs-lookup"><span data-stu-id="1536d-p115">In **Name**, specify a name for the new configuration settings. By default, the site pool name already exists.</span></span>
    
      - <span data-ttu-id="1536d-p116">В поле **Журнал чата по умолчанию** укажите число сообщений чата, который будут обрабатываться для каждой комнаты по первому запросу. Номер порта по умолчанию — 30. Это глобальный параметр по умолчанию, администраторы могут отключить журнал чата для категории.</span><span class="sxs-lookup"><span data-stu-id="1536d-p116">In **Default chat history**, define the number of chat messages that will be processed for each room upon first request. By default, the number is 30. This is the global default, and administrators can disable chat history per category.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="1536d-158">Сервер сохраняемого чата кэширует эти сообщения в памяти, поэтому при увеличении этого числа будет кэшироваться больше сообщений.</span><span class="sxs-lookup"><span data-stu-id="1536d-158">Persistent Chat Server will cache these messages in memory, so if you increase this number, more messages will be cached.</span></span> <span data-ttu-id="1536d-159">Вы всегда можете получить доступ к историческому контенту с помощью поиска.</span><span class="sxs-lookup"><span data-stu-id="1536d-159">You can always access historical content by search.</span></span> <span data-ttu-id="1536d-160">Число по умолчанию просто определяет максимальное число сообщений, которые изначально отображаются при подключении к комнате чата.</span><span class="sxs-lookup"><span data-stu-id="1536d-160">The default number simply determines the maximum number of messages that you initially see when connecting to a chat room.</span></span>

        
        </div>
    
      - <span data-ttu-id="1536d-p118">В поле **Максимальный размер файла (КБ)** выберите максимальный размер файла журнала каждого чата. Размер файла по умолчанию — 20 МБ (20 000 КБ). Это максимальный размер файла, который можно загрузить в любую комнату чата в системе (для которой загрузка файлов разрешена соответствующим параметром **Категория**).</span><span class="sxs-lookup"><span data-stu-id="1536d-p118">In **Maximum file size (KB)**, select the maximum file size of each chat history. By default, the number is 20 MB (20,000 KB). This is the maximum size for a file that can be uploaded to any chat room in the system (for which file uploads are enabled by its corresponding **Category** setting).</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="1536d-164">Этот параметр применяется на сервере, так как пользовательские приложения или предыдущие клиенты группового чата (Office Communications Server 2007 R2 &nbsp; Group Chat Server или Lync server 2010, группового чата) могут отправлять файлы в комнату.</span><span class="sxs-lookup"><span data-stu-id="1536d-164">This setting is enforced on the server because custom applications or previous Group Chat clients (Office Communications Server 2007 R2&nbsp;Group Chat Server or Lync Server 2010, Group Chat) can post files to a room.</span></span> <span data-ttu-id="1536d-165">У клиента Lync 2013 нет возможности отправки и загрузки файлов, поэтому при наличии чистого клиента Lync 2013 или Lync 2013 невозможно разместить файлы в комнате чата сервера сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="1536d-165">The Lync 2013 client does not have file upload/download capability, so if you have a pure Lync 2013 deployment or Lync 2013 client, it is not possible to post files in a Persistent Chat Server chat room.</span></span>

        
        </div>
    
      - <span data-ttu-id="1536d-166">В поле **Предельное значение обновления участников** выберите предел для обновления участников.</span><span class="sxs-lookup"><span data-stu-id="1536d-166">In **Participant update limit**, select the limit for participant updates.</span></span> <span data-ttu-id="1536d-167">Сервер сохраняемого чата отправляет сведения о списке (которые подключены к комнате чата) всем участникам до тех пор, пока число подключенных пользователей не достигнет этого числа.</span><span class="sxs-lookup"><span data-stu-id="1536d-167">Persistent Chat Server sends roster information (who is connected to a chat room) to all participants until the number of connected users reaches this number.</span></span> <span data-ttu-id="1536d-168">Значение по умолчанию — 75.</span><span class="sxs-lookup"><span data-stu-id="1536d-168">By default, the number is 75.</span></span> <span data-ttu-id="1536d-169">Это ограничение указывает максимальное число участников в заданном помещении, за исключением которых сервер сохраняемого чата перестает отправлять обновления списка подключенным клиентам о пользователях, присутствующих в комнате.</span><span class="sxs-lookup"><span data-stu-id="1536d-169">This limit indicates the maximum number of participants in a given room beyond which Persistent Chat Server stops sending roster updates to connected clients about who is present in the room.</span></span>
    
      - <span data-ttu-id="1536d-p121">В поле **URL-адрес управления комнатой** выберите URL-адрес управления комнатой. Это URL-адрес для развертывания веб-управления комнатами. Если вам не нужно настраивать функции управления комнатами и вы просто используете настройку по умолчанию, оставьте это поле пустым.</span><span class="sxs-lookup"><span data-stu-id="1536d-p121">In **Room management URL**, select the room management URL. This is the URL for a web-based room management deployment. If you don’t need to customize room management, and you simply use the default setting, leave this option blank.</span></span>
        
        <span data-ttu-id="1536d-173">Если вы хотите настроить интерфейс создания комнаты и включить свой бизнес-процесс, вы можете создать настраиваемое решение для управления комнатами с помощью пакета SDK сервера сохраняемого чата (SDK), разместить его в любом месте и разместить здесь URL-адрес здесь.</span><span class="sxs-lookup"><span data-stu-id="1536d-173">If you want to customize your room creation experience and include your specific business workflow, you can build a custom room management solution by using the Persistent Chat Server Software Development Kit (SDK), host it somewhere, and put the URL here.</span></span> <span data-ttu-id="1536d-174">Этот URL-адрес отправляется клиенту, чтобы при попытке просмотра или создания комнаты пользователь предлагалось использовать ваше настраиваемое решение для управления комнатами.</span><span class="sxs-lookup"><span data-stu-id="1536d-174">This URL is sent down to the client so that when a user tries to view/create a room, he or she is directed to your custom room management solution.</span></span>

7.  <span data-ttu-id="1536d-175">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="1536d-175">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

