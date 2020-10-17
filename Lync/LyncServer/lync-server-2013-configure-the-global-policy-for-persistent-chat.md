---
title: 'Lync Server 2013: Настройка глобальной политики для сохраняемого чата'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure the global policy for Persistent Chat
ms:assetid: 6176eb5c-19de-4c07-bcc0-2e38f8965966
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204951(v=OCS.15)
ms:contentKeyID: 48184323
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b883a650a4430ee286c4824e49711e47e1509e26
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48520336"
---
# <a name="configure-the-global-policy-for-persistent-chat-in-lync-server-2013"></a><span data-ttu-id="ae185-102">Настройка глобальной политики для сохраняемого чата в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ae185-102">Configure the global policy for Persistent Chat in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ae185-103">_**Последнее изменение темы:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="ae185-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="ae185-104">Вы можете использовать глобальную политику по умолчанию, чтобы включить параметры сохраняемого чата для всех пользователей в развертывании.</span><span class="sxs-lookup"><span data-stu-id="ae185-104">You can use the default global policy by itself to enable Persistent Chat settings for all users in your deployment.</span></span> <span data-ttu-id="ae185-105">Кроме того, можно указать дополнительные политики для сайтов и пользователей, чтобы управлять включением или выключением сохраняемого чата для определенных пользователей и сайтов.</span><span class="sxs-lookup"><span data-stu-id="ae185-105">You can also specify additional policies for sites and users to control whether Persistent Chat is enabled or disabled for specific users and sites.</span></span>

<span data-ttu-id="ae185-106">Глобальную политику удалить невозможно.</span><span class="sxs-lookup"><span data-stu-id="ae185-106">You cannot delete the global policy.</span></span> <span data-ttu-id="ae185-107">Если попытаться сделать это, конфигурация сбрасывается до значений по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="ae185-107">If you attempt to delete it, the configuration resets to the default values.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ae185-108">Чтобы настроить и использовать сервер сохраняемого чата, сначала необходимо использовать построитель топологий, чтобы добавить в топологию поддержку сервера сохраняемого чата, а затем опубликовать топологию.</span><span class="sxs-lookup"><span data-stu-id="ae185-108">To configure and use Persistent Chat Server, you must first use Topology Builder to add Persistent Chat Server support to the topology, and then publish the topology.</span></span> <span data-ttu-id="ae185-109">Дополнительные сведения см. в статье <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Добавление сервера сохраняемого чата в развертывание в Lync Server 2013</A> в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="ae185-109">For details, see <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Adding Persistent Chat Server to your deployment in Lync Server 2013</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="ae185-110">Чтобы настроить параметры конфигурации сервера сохраняемого чата, ознакомьтесь со статьей <A href="lync-server-2013-configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool.md">Настройка параметров сервера сохраняемого чата на глобальном уровне или для пула сервера сохраняемого чата в Lync server 2013</A> в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="ae185-110">To configure Persistent Chat Server configuration settings, see <A href="lync-server-2013-configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool.md">Configure Persistent Chat Server options globally or for Persistent Chat Server pool in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="to-configure-the-global-policy-for-persistent-chat"></a><span data-ttu-id="ae185-111">Настройка глобальной политики для сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="ae185-111">To configure the Global Policy for Persistent Chat</span></span>

1.  <span data-ttu-id="ae185-112">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsPersistentChatAdministrator, CsAdministrator или CsUserAdministrator.</span><span class="sxs-lookup"><span data-stu-id="ae185-112">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="ae185-113">В меню **Пуск** выберите Панель управления Lync Server или откройте окно браузера и введите URL-адрес администрирования.</span><span class="sxs-lookup"><span data-stu-id="ae185-113">From the **Start** menu, select the Lync Server Control Panel or open a browser window, and then enter the Admin URL.</span></span> <span data-ttu-id="ae185-114">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь с [разпрограммным средством администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md) в документации по операциям.</span><span class="sxs-lookup"><span data-stu-id="ae185-114">For details about the different methods that you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md) in the Operations documentation.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="ae185-115">Вы также можете использовать командлеты Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ae185-115">You can also use Windows PowerShell cmdlets.</span></span> <span data-ttu-id="ae185-116">Дополнительные сведения см. в разделе <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Настройка сервера сохраняемого чата с помощью командлетов Windows PowerShell</A> в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="ae185-116">For details, see <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Configuring Persistent Chat Server by using Windows PowerShell cmdlets</A> in Deployment documentation.</span></span>

    
    </div>

3.  <span data-ttu-id="ae185-117">В панели управления Lync Server щелкните **сохраняемый чат**и выберите **Политика сохраняемого чата**.</span><span class="sxs-lookup"><span data-stu-id="ae185-117">In Lync Server Control Panel, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>

4.  <span data-ttu-id="ae185-118">Выберите **Глобальная** в списке политик, нажмите кнопку **Изменить**, а затем нажмите кнопку **Подробнее**.</span><span class="sxs-lookup"><span data-stu-id="ae185-118">Click **Global** in the list of policies, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="ae185-119">В окне **Изменение политики сохраняемого чата — глобальная политика** выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="ae185-119">In **Edit Persistent Chat Policy - Global**, do the following:</span></span>
    
      - <span data-ttu-id="ae185-120">В поле **Имя** введите новое имя глобальной политики, если вы не хотите использовать политику по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="ae185-120">In **Name**, specify a new name for the global policy, if you do not want to use the default of Global.</span></span>
    
      - <span data-ttu-id="ae185-121">В поле **Description (описание**) укажите сведения о пользовательской политике (например, "Глобальная политика для централситенаме").</span><span class="sxs-lookup"><span data-stu-id="ae185-121">In **Description**, provide details about what the user policy is (for example, Global policy for centralSiteName).</span></span>
    
      - <span data-ttu-id="ae185-122">Чтобы управлять сохраняемым чат для всех сайтов и пользователей, которые не контролируются политикой сайта или политикой пользователей, установите или снимите флажок **включить сохраняемый чат** .</span><span class="sxs-lookup"><span data-stu-id="ae185-122">To control Persistent Chat for all sites and users not specifically controlled through a site policy or user policy, select or clear the **Enable Persistent Chat** check box.</span></span>

6.  <span data-ttu-id="ae185-123">Щелкните **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="ae185-123">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

