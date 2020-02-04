---
title: 'Lync Server 2013: применение политики сохраняемого чата к пользователю или группе пользователей'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Apply a Persistent Chat policy to a user or user group
ms:assetid: 809ef4e0-8d42-4feb-b7c0-3995f39867a7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205038(v=OCS.15)
ms:contentKeyID: 48184652
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 726fe9a5fa20a52f770cd5bab475de5731562989
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737629"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="apply-a-persistent-chat-policy-to-a-user-or-user-group-in-lync-server-2013"></a><span data-ttu-id="c1597-102">Применение политики сохраняемого чата к пользователю или группе пользователей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c1597-102">Apply a Persistent Chat policy to a user or user group in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c1597-103">_**Тема последнего изменения:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="c1597-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="c1597-104">Если у пользователя есть разрешение на доступ к Lync Server 2013, вы можете применять соответствующие политики к определенным пользователям, чтобы включить или отключить их для постоянного сервера чата.</span><span class="sxs-lookup"><span data-stu-id="c1597-104">If a user has been enabled for Lync Server 2013, you can apply appropriate policies to specific users to enable or disable them for Persistent Chat Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c1597-105">Чтобы настроить и использовать сохраняемый сервер чата, необходимо сначала использовать Topology Builder, чтобы добавить в топологию постоянную поддержку сервера чата, а затем опубликовать топологию.</span><span class="sxs-lookup"><span data-stu-id="c1597-105">To configure and use Persistent Chat Server, you must first use Topology Builder to add Persistent Chat Server support to the topology, and then publish the topology.</span></span> <span data-ttu-id="c1597-106">Подробные сведения о том, <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">как добавить сохраняемый сервер чата в развертывание в среде Lync server 2013, можно</A> найти в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="c1597-106">For details, see <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Adding Persistent Chat Server to your deployment in Lync Server 2013</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="c1597-107">Чтобы настроить параметры конфигурации сервера для сохраняемого чата, ознакомьтесь с <A href="lync-server-2013-configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool.md">Разстройкой параметры сервера сохраняемого чата глобально или для постоянного пула серверов чатов в Lync server 2013</A> в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="c1597-107">To configure Persistent Chat Server configuration settings, see <A href="lync-server-2013-configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool.md">Configure Persistent Chat Server options globally or for Persistent Chat Server pool in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<span data-ttu-id="c1597-108">С помощью описанной в этом разделе процедуры примените ранее созданную политику постоянного чата к одной или нескольким учетным записям пользователей или группам пользователей.</span><span class="sxs-lookup"><span data-stu-id="c1597-108">Use the procedure in this topic to apply a previously created Persistent Chat user policy to one or more user accounts or user groups.</span></span>

<div>

## <a name="to-apply-a-persistent-chat-user-policy-to-a-user-account"></a><span data-ttu-id="c1597-109">Применение политики пользователя сохраняемого чата к учетной записи пользователя</span><span class="sxs-lookup"><span data-stu-id="c1597-109">To apply a Persistent Chat user policy to a user account</span></span>

1.  <span data-ttu-id="c1597-110">Войдите в систему на любом компьютере во внутреннем развертывании с помощью учетной записи пользователя, которому назначена роль CsPersistentChatAdministrator, CsAdministrator или CsUserAdministrator.</span><span class="sxs-lookup"><span data-stu-id="c1597-110">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="c1597-111">В меню **Пуск** выберите Панель управления Lync Server или откройте окно браузера и введите URL-адрес администратора.</span><span class="sxs-lookup"><span data-stu-id="c1597-111">From the **Start** menu, select the Lync Server Control Panel or open a browser window, and then enter the Admin URL.</span></span> <span data-ttu-id="c1597-112">Дополнительные сведения о различных способах запуска панели управления Lync Server можно найти в разделе [Открытие средства администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="c1597-112">For details about the different methods that you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="c1597-113">В левой панели навигации нажмите **Пользователи** и выполните поиск учетной записи, которую вы хотите настроить.</span><span class="sxs-lookup"><span data-stu-id="c1597-113">In the left navigation bar, click **Users**, and then search on the user account that you want to configure.</span></span>

4.  <span data-ttu-id="c1597-114">В таблице с результатами поиска выберите нужную учетную запись, нажмите кнопку **Изменить** и выберите пункт **Показать сведения**.</span><span class="sxs-lookup"><span data-stu-id="c1597-114">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="c1597-115">В диалоговом окне **изменение пользователя Lync Server** в разделе **Политика сохраняемого чата**выберите политику пользователей сохраняемого чата, которую вы хотите применить.</span><span class="sxs-lookup"><span data-stu-id="c1597-115">In **Edit Lync Server User** under **Persistent Chat policy**, select the Persistent Chat user policy that you want to apply.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c1597-116">Автоматические параметры применяются к действующей политике по умолчанию. <STRONG> &lt;&gt; </STRONG></span><span class="sxs-lookup"><span data-stu-id="c1597-116">The <STRONG>&lt;Automatic&gt;</STRONG> settings apply the default effective policy.</span></span> <span data-ttu-id="c1597-117">Данные параметры автоматически применяются сервером.</span><span class="sxs-lookup"><span data-stu-id="c1597-117">These settings are applied automatically by the server.</span></span>

    
    </div>

6.  <span data-ttu-id="c1597-118">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="c1597-118">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

