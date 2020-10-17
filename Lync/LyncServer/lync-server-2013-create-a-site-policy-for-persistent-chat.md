---
title: 'Lync Server 2013: Создание политики сайта для сохраняемого чата'
description: 'Lync Server 2013: Создание политики сайта для сохраняемого чата.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a site policy for Persistent Chat
ms:assetid: 1327ff5c-b859-4010-a240-e0b2b084b5bd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204693(v=OCS.15)
ms:contentKeyID: 48183470
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0f1cfbcffd98e7bdb813a4113345abf17f5b37e5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553225"
---
# <a name="create-a-site-policy-for-persistent-chat-in-lync-server-2013"></a><span data-ttu-id="cf6b8-103">Создание политики сайта для сохраняемого чата в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cf6b8-103">Create a site policy for Persistent Chat in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cf6b8-104">_**Последнее изменение темы:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="cf6b8-104">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="cf6b8-105">Для каждого развернутого сайта можно создать политику сохраняемого чата для определенных сайтов.</span><span class="sxs-lookup"><span data-stu-id="cf6b8-105">For each site you have deployed, you can create a site-specific Persistent Chat policy.</span></span>

<span data-ttu-id="cf6b8-106">Конфигурация в политике сайта переопределяет глобальную политику, но только для того сайта, которому назначена эта политика.</span><span class="sxs-lookup"><span data-stu-id="cf6b8-106">The configuration in the site policy overrides the global policy, but only for the specific site covered by the site policy.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="cf6b8-107">Чтобы настроить и использовать сервер сохраняемого чата, сначала необходимо использовать построитель топологий, чтобы добавить в топологию поддержку сервера сохраняемого чата, а затем опубликовать топологию.</span><span class="sxs-lookup"><span data-stu-id="cf6b8-107">To configure and use Persistent Chat Server, you must first use Topology Builder to add Persistent Chat Server support to the topology, and then publish the topology.</span></span> <span data-ttu-id="cf6b8-108">Дополнительные сведения см. в статье <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Добавление сервера сохраняемого чата в развертывание в Lync Server 2013</A> в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="cf6b8-108">For details, see <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Adding Persistent Chat Server to your deployment in Lync Server 2013</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="cf6b8-109">Чтобы настроить параметры конфигурации сервера сохраняемого чата, ознакомьтесь со статьей <A href="lync-server-2013-configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool.md">Настройка параметров сервера сохраняемого чата на глобальном уровне или для пула сервера сохраняемого чата в Lync server 2013</A> в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="cf6b8-109">To configure Persistent Chat Server configuration settings, see <A href="lync-server-2013-configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool.md">Configure Persistent Chat Server options globally or for Persistent Chat Server pool in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="to-create-a-persistent-chat-policy-for-a-site"></a><span data-ttu-id="cf6b8-110">Создание политики сохраняемого чата для сайта</span><span class="sxs-lookup"><span data-stu-id="cf6b8-110">To create a Persistent Chat policy for a site</span></span>

1.  <span data-ttu-id="cf6b8-111">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsPersistentChatAdministrator, CsAdministrator или CsUserAdministrator.</span><span class="sxs-lookup"><span data-stu-id="cf6b8-111">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="cf6b8-112">В меню **Пуск** выберите Панель управления Lync Server или откройте окно браузера и введите URL-адрес администрирования.</span><span class="sxs-lookup"><span data-stu-id="cf6b8-112">From the **Start** menu, select the Lync Server Control Panel or open a browser window, and then enter the Admin URL.</span></span> <span data-ttu-id="cf6b8-113">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="cf6b8-113">For details about the different methods that you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="cf6b8-114">В левой панели навигации щелкните **Сохраняемый чат** и выберите пункт **Политика сохраняемого чата**.</span><span class="sxs-lookup"><span data-stu-id="cf6b8-114">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="cf6b8-115">Вы также можете использовать командлеты Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cf6b8-115">You can also use Windows PowerShell cmdlets.</span></span> <span data-ttu-id="cf6b8-116">Дополнительные сведения: <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Настройка сервера сохраняемого чата с помощью командлетов Windows PowerShell,</A> описанных в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="cf6b8-116">For details, see <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Configuring Persistent Chat Server by using Windows PowerShell cmdlets</A> in the Deployment documentation.</span></span>

    
    </div>

4.  <span data-ttu-id="cf6b8-117">Нажмите кнопку **Создать** и щелкните **Политика сайта**.</span><span class="sxs-lookup"><span data-stu-id="cf6b8-117">Click **New**, and then click **Site policy**.</span></span>

5.  <span data-ttu-id="cf6b8-118">В окне **Выбор сайта** щелкните сайт, к которому будет применена политика.</span><span class="sxs-lookup"><span data-stu-id="cf6b8-118">In **Select a Site**, click the site to which the policy is to be applied.</span></span>

6.  <span data-ttu-id="cf6b8-119">В окне **Создание политики сохраняемого чата** выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="cf6b8-119">In **New Persistent Chat Policy**, do the following:</span></span>
    
      - <span data-ttu-id="cf6b8-120">В поле **Имя** введите имя новой политики сайта (например, Redmond).</span><span class="sxs-lookup"><span data-stu-id="cf6b8-120">In **Name**, specify a name for the new site policy (for example, Redmond).</span></span>
    
      - <span data-ttu-id="cf6b8-121">В поле **Описание** введите сведения о политике сайта (например, политика комнаты чата для Redmond).</span><span class="sxs-lookup"><span data-stu-id="cf6b8-121">In **Description**, provide details about what the site policy is (for example, chat room policy for Redmond).</span></span>
    
      - <span data-ttu-id="cf6b8-122">Чтобы управлять сохраняемым чатом для всех сайтов, которые не контролируются политикой сайта, установите или снимите флажок **Разрешить сохраняемый чат**.</span><span class="sxs-lookup"><span data-stu-id="cf6b8-122">To control Persistent Chat for all sites not specifically controlled through a site policy, select or clear the **Enable Persistent Chat** check box.</span></span>

7.  <span data-ttu-id="cf6b8-123">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="cf6b8-123">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

