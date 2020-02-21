---
title: 'Lync Server 2013: создание пользовательской политики для сохраняемого чата'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a user policy for Persistent Chat
ms:assetid: aa3774af-d442-4206-8a68-2fbb9102e9d6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205170(v=OCS.15)
ms:contentKeyID: 48185103
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 40e992bbbd5d2559619e2ebe5a0d67c83102e546
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42195882"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-a-user-policy-for-persistent-chat-in-lync-server-2013"></a><span data-ttu-id="90584-102">Создание пользовательской политики для сохраняемого чата в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="90584-102">Create a user policy for Persistent Chat in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="90584-103">_**Последнее изменение темы:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="90584-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="90584-104">В панели управления Lync Server определяются политики пользователей, которые можно назначить пользователям в разделе **Пользователи**.</span><span class="sxs-lookup"><span data-stu-id="90584-104">In the Lync Server Control Panel, you define user policies that can be assigned to users in **Users**.</span></span>

<span data-ttu-id="90584-105">Пользовательская политики переопределяет глобальную политику и политики сайта, но только для пользователей, которым назначена эта политика.</span><span class="sxs-lookup"><span data-stu-id="90584-105">The user policy overrides the global policy and site policies, but only for the specific users who are assigned the user policy.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="90584-106">Чтобы настроить и использовать сервер сохраняемого чата, сначала необходимо использовать построитель топологий, чтобы добавить в топологию поддержку сервера сохраняемого чата, а затем опубликовать топологию.</span><span class="sxs-lookup"><span data-stu-id="90584-106">To configure and use Persistent Chat Server, you must first use Topology Builder to add Persistent Chat Server support to the topology, and then publish the topology.</span></span> <span data-ttu-id="90584-107">Дополнительные сведения см. в статье <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Добавление сервера сохраняемого чата в развертывание в Lync Server 2013</A> в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="90584-107">For details, see <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Adding Persistent Chat Server to your deployment in Lync Server 2013</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="90584-108">Чтобы настроить параметры конфигурации сервера сохраняемого чата, ознакомьтесь со статьей <A href="lync-server-2013-configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool.md">Настройка параметров сервера сохраняемого чата на глобальном уровне или для пула сервера сохраняемого чата в Lync server 2013</A> в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="90584-108">To configure Persistent Chat Server configuration settings, see <A href="lync-server-2013-configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool.md">Configure Persistent Chat Server options globally or for Persistent Chat Server pool in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="to-create-a-user-policy-for-persistent-chat"></a><span data-ttu-id="90584-109">Создание пользовательской политики для сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="90584-109">To create a user policy for Persistent Chat</span></span>

1.  <span data-ttu-id="90584-110">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsPersistentChatAdministrator, CsAdministrator или CsUserAdministrator.</span><span class="sxs-lookup"><span data-stu-id="90584-110">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="90584-111">В меню **Пуск** выберите Панель управления Lync Server или откройте окно браузера и введите URL-адрес администрирования.</span><span class="sxs-lookup"><span data-stu-id="90584-111">From the **Start** menu, select the Lync Server Control Panel or open a browser window, and then enter the Admin URL.</span></span> <span data-ttu-id="90584-112">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="90584-112">For details about the different methods that you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="90584-113">Вы также можете использовать командлеты Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="90584-113">You can also use Windows PowerShell cmdlets.</span></span> <span data-ttu-id="90584-114">Обратитесь к разделу <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Настройка сервера сохраняемого чата с помощью командлетов Windows PowerShell,</A> приведенных в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="90584-114">See <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Configuring Persistent Chat Server by using Windows PowerShell cmdlets</A> in the Deployment documentation.</span></span>

    
    </div>

3.  <span data-ttu-id="90584-115">В левой панели навигации щелкните **Сохраняемый чат** и выберите пункт **Политика сохраняемого чата**.</span><span class="sxs-lookup"><span data-stu-id="90584-115">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>

4.  <span data-ttu-id="90584-116">Нажмите кнопку **Создать** и щелкните **Политика пользователя**.</span><span class="sxs-lookup"><span data-stu-id="90584-116">Click **New**, and then click **User policy**.</span></span>

5.  <span data-ttu-id="90584-117">В окне **Создание политики сохраняемого чата** выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="90584-117">In **New Persistent Chat Policy**, do the following:</span></span>
    
      - <span data-ttu-id="90584-118">В поле **Имя** введите имя новой пользовательской политики.</span><span class="sxs-lookup"><span data-stu-id="90584-118">In **Name**, specify a name for the new user policy.</span></span>
    
      - <span data-ttu-id="90584-119">В поле **Description (описание**) укажите сведения о политике пользователя (например, политика сохраняемого чата для определенного пользователя).</span><span class="sxs-lookup"><span data-stu-id="90584-119">In **Description**, provide details about what the user policy is (for example, Persistent Chat policy for specific user).</span></span>
    
      - <span data-ttu-id="90584-120">Чтобы управлять сохраняемым чат для всех пользователей, которые не контролируются политикой пользователя, установите или снимите флажок **включить сохраняемый чат** .</span><span class="sxs-lookup"><span data-stu-id="90584-120">To control Persistent Chat for all users who are not specifically controlled through a user policy, select or clear the **Enable Persistent Chat** check box.</span></span>

6.  <span data-ttu-id="90584-121">Щелкните **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="90584-121">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

