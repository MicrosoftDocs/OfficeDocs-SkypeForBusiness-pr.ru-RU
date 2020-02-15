---
title: 'Lync Server 2013: тестирование сервера Standard Edition'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test the Standard Edition server
ms:assetid: b6ef67bb-9665-43e4-b8b3-eac8898eebf6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412890(v=OCS.15)
ms:contentKeyID: 48185220
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4145740f09557c8f39830dce689fa122456a28f8
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42018980"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-the-standard-edition-server-in-lync-server-2013"></a><span data-ttu-id="70553-102">Тестирование сервера Standard Edition в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="70553-102">Test the Standard Edition server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="70553-103">_**Последнее изменение темы:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="70553-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="70553-104">В следующей процедуре описывается тестирование развертывания сервера Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="70553-104">The following procedure describes how to test the deployment of a Standard Edition server.</span></span>

<div>

## <a name="to-test-the-deployment-of-a-standard-edition-server"></a><span data-ttu-id="70553-105">Проверка развертывания сервера выпуска Standard Edition</span><span class="sxs-lookup"><span data-stu-id="70553-105">To test the deployment of a Standard Edition Server</span></span>

1.  <span data-ttu-id="70553-106">Используйте "пользователи и компьютеры Active Directory", чтобы добавить объект пользователя Active Directory роли администратора для развертывания Lync Server 2013 (на котором установлена панель управления Lync Server) в группу **CSAdministrator** .</span><span class="sxs-lookup"><span data-stu-id="70553-106">Use Active Directory Computers and Users to add the Active Directory user object of the administrator role for the Lync Server 2013 deployment (on which Lync Server Control Panel is installed) to the **CSAdministrator** group.</span></span>

2.  <span data-ttu-id="70553-107">Если объект-пользователь уже выполнил вход в систему, выйдите из системы, а затем повторите вход, чтобы зарегистрировать назначение новой группы.</span><span class="sxs-lookup"><span data-stu-id="70553-107">If the user object is currently logged on, log off and then log on again to register the new group assignment.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="70553-108">Учетная запись пользователя не может быть локальным администратором сервера Lync Server 2013, Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="70553-108">The user account cannot be the local administrator of the server running Lync Server 2013, Standard Edition.</span></span> <span data-ttu-id="70553-109">Если вы не добавите соответствующих пользователей и группы в группу Ксадминисторс, вы получите сообщение об ошибке при открытии панели управления Lync Server 2013, в котором указано, что "несанкционированный доступ запрещен" из-за сбоя авторизации управления доступом на основе ролей (RBAC). "</span><span class="sxs-lookup"><span data-stu-id="70553-109">If you do not add the appropriate users and groups to the CsAdministors group, you will receive an error when opening Lync Server 2013 Control Panel, which states that “Unauthorized: Access is denied due to a role-based access control (RBAC) authorization failure.”</span></span>

    
    </div>

3.  <span data-ttu-id="70553-110">Используйте учетную запись администратора, чтобы войти на компьютер, на котором установлена панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="70553-110">Use the administrative account to log on to the computer where Lync Server Control Panel is installed.</span></span>

4.  <span data-ttu-id="70553-111">Запустите Панель управления Lync Server и при необходимости укажите учетные данные.</span><span class="sxs-lookup"><span data-stu-id="70553-111">Start Lync Server Control Panel and provide credentials, if prompted.</span></span> <span data-ttu-id="70553-112">В панели управления Lync Server 2013 отображаются сведения о развертывании.</span><span class="sxs-lookup"><span data-stu-id="70553-112">Lync Server 2013 Control Panel displays deployment information.</span></span>

5.  <span data-ttu-id="70553-113">В левой панели навигации щелкните Topology ( **топология**) и убедитесь, что состояние службы — значок компьютера с зеленой стрелкой, а рядом с каждой ролью сервера Lync Server, которая была развернута и переведена в оперативный режим, отображается зеленая галочка.</span><span class="sxs-lookup"><span data-stu-id="70553-113">In the left navigation bar, click **Topology**, and then confirm that the service status is a computer icon with a green arrow and there is a green check mark next to each Lync Server server role that has been deployed and brought online.</span></span>

6.  <span data-ttu-id="70553-114">В левой панели навигации щелкните **Пользователи**, а затем включите два пользователя для Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="70553-114">In the left navigation bar, click **Users**, and then enable the two users for Lync Server 2013.</span></span>

7.  <span data-ttu-id="70553-115">Выполните вход с учетной записью одного пользователя на компьютер, присоединенный к домену, а с учетной записью другого пользователя — на другой компьютер домена.</span><span class="sxs-lookup"><span data-stu-id="70553-115">Log one user on to a computer that is joined to the domain, and the other user on to another computer in the domain.</span></span>

8.  <span data-ttu-id="70553-116">Установите Lync Server 2013 на каждом из двух клиентских компьютеров, а затем убедитесь, что оба пользователя могут войти в Lync Server 2013 и обмениваться мгновенными сообщениями друг с другом.</span><span class="sxs-lookup"><span data-stu-id="70553-116">Install Lync Server 2013 on each of the two client computers, and then verify that both users can sign in to Lync Server 2013 and can send instant messages to each other.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="70553-117">См. также</span><span class="sxs-lookup"><span data-stu-id="70553-117">See Also</span></span>


[<span data-ttu-id="70553-118">Развертывание клиентов и устройств в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="70553-118">Deploying clients and devices in Lync Server 2013</span></span>](lync-server-2013-deploying-clients-and-devices.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

