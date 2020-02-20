---
title: 'Lync Server 2013: Создание политики сайта для сохраняемого чата'
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
ms.openlocfilehash: 29b682191b0170a3915f44d54daa426ca5ce4544
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145558"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-a-site-policy-for-persistent-chat-in-lync-server-2013"></a><span data-ttu-id="bff85-102">Создание политики сайта для сохраняемого чата в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bff85-102">Create a site policy for Persistent Chat in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bff85-103">_**Последнее изменение темы:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="bff85-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="bff85-104">Для каждого развернутого сайта можно создать политику сохраняемого чата для определенных сайтов.</span><span class="sxs-lookup"><span data-stu-id="bff85-104">For each site you have deployed, you can create a site-specific Persistent Chat policy.</span></span>

<span data-ttu-id="bff85-105">Конфигурация в политике сайта переопределяет глобальную политику, но только для того сайта, которому назначена эта политика.</span><span class="sxs-lookup"><span data-stu-id="bff85-105">The configuration in the site policy overrides the global policy, but only for the specific site covered by the site policy.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="bff85-106">Чтобы настроить и использовать сервер сохраняемого чата, сначала необходимо использовать построитель топологий, чтобы добавить в топологию поддержку сервера сохраняемого чата, а затем опубликовать топологию.</span><span class="sxs-lookup"><span data-stu-id="bff85-106">To configure and use Persistent Chat Server, you must first use Topology Builder to add Persistent Chat Server support to the topology, and then publish the topology.</span></span> <span data-ttu-id="bff85-107">Дополнительные сведения см. в статье <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Добавление сервера сохраняемого чата в развертывание в Lync Server 2013</A> в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="bff85-107">For details, see <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Adding Persistent Chat Server to your deployment in Lync Server 2013</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="bff85-108">Чтобы настроить параметры конфигурации сервера сохраняемого чата, ознакомьтесь со статьей <A href="lync-server-2013-configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool.md">Настройка параметров сервера сохраняемого чата на глобальном уровне или для пула сервера сохраняемого чата в Lync server 2013</A> в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="bff85-108">To configure Persistent Chat Server configuration settings, see <A href="lync-server-2013-configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool.md">Configure Persistent Chat Server options globally or for Persistent Chat Server pool in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="to-create-a-persistent-chat-policy-for-a-site"></a><span data-ttu-id="bff85-109">Создание политики сохраняемого чата для сайта</span><span class="sxs-lookup"><span data-stu-id="bff85-109">To create a Persistent Chat policy for a site</span></span>

1.  <span data-ttu-id="bff85-110">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsPersistentChatAdministrator, CsAdministrator или CsUserAdministrator.</span><span class="sxs-lookup"><span data-stu-id="bff85-110">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="bff85-111">В меню **Пуск** выберите Панель управления Lync Server или откройте окно браузера и введите URL-адрес администрирования.</span><span class="sxs-lookup"><span data-stu-id="bff85-111">From the **Start** menu, select the Lync Server Control Panel or open a browser window, and then enter the Admin URL.</span></span> <span data-ttu-id="bff85-112">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="bff85-112">For details about the different methods that you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="bff85-113">В левой панели навигации щелкните **Сохраняемый чат** и выберите пункт **Политика сохраняемого чата**.</span><span class="sxs-lookup"><span data-stu-id="bff85-113">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="bff85-114">Вы также можете использовать командлеты Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bff85-114">You can also use Windows PowerShell cmdlets.</span></span> <span data-ttu-id="bff85-115">Дополнительные сведения: <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Настройка сервера сохраняемого чата с помощью командлетов Windows PowerShell,</A> описанных в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="bff85-115">For details, see <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Configuring Persistent Chat Server by using Windows PowerShell cmdlets</A> in the Deployment documentation.</span></span>

    
    </div>

4.  <span data-ttu-id="bff85-116">Нажмите кнопку **Создать** и щелкните **Политика сайта**.</span><span class="sxs-lookup"><span data-stu-id="bff85-116">Click **New**, and then click **Site policy**.</span></span>

5.  <span data-ttu-id="bff85-117">В окне **Выбор сайта** щелкните сайт, к которому будет применена политика.</span><span class="sxs-lookup"><span data-stu-id="bff85-117">In **Select a Site**, click the site to which the policy is to be applied.</span></span>

6.  <span data-ttu-id="bff85-118">В окне **Создание политики сохраняемого чата** выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="bff85-118">In **New Persistent Chat Policy**, do the following:</span></span>
    
      - <span data-ttu-id="bff85-119">В поле **Имя** введите имя новой политики сайта (например, Redmond).</span><span class="sxs-lookup"><span data-stu-id="bff85-119">In **Name**, specify a name for the new site policy (for example, Redmond).</span></span>
    
      - <span data-ttu-id="bff85-120">В поле **Описание** введите сведения о политике сайта (например, политика комнаты чата для Redmond).</span><span class="sxs-lookup"><span data-stu-id="bff85-120">In **Description**, provide details about what the site policy is (for example, chat room policy for Redmond).</span></span>
    
      - <span data-ttu-id="bff85-121">Чтобы управлять сохраняемым чатом для всех сайтов, которые не контролируются политикой сайта, установите или снимите флажок **Разрешить сохраняемый чат**.</span><span class="sxs-lookup"><span data-stu-id="bff85-121">To control Persistent Chat for all sites not specifically controlled through a site policy, select or clear the **Enable Persistent Chat** check box.</span></span>

7.  <span data-ttu-id="bff85-122">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="bff85-122">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

