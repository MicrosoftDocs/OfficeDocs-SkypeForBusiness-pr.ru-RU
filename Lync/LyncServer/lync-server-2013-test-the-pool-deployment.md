---
title: 'Lync Server 2013: тестирование развертывания пула'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Test the pool deployment
ms:assetid: ffd80617-155a-4041-bbeb-74503e7938dd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413092(v=OCS.15)
ms:contentKeyID: 48185976
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 70a1dc68b8dbe6285cdf4b7e9c21c873caaf730d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849416"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-the-pool-deployment-in-lync-server-2013"></a><span data-ttu-id="d08ad-102">Тестирование развертывания пула в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d08ad-102">Test the pool deployment in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d08ad-103">_**Тема последнего изменения:** 2013-09-25_</span><span class="sxs-lookup"><span data-stu-id="d08ad-103">_**Topic Last Modified:** 2013-09-25_</span></span>

<span data-ttu-id="d08ad-104">Ниже описана процедура проверки развертывания пула переднего плана.</span><span class="sxs-lookup"><span data-stu-id="d08ad-104">The following procedure describes how to test the deployment of the Front End pool.</span></span>

<div>

## <a name="to-test-the-pool-deployment"></a><span data-ttu-id="d08ad-105">Проверка развертывания пула</span><span class="sxs-lookup"><span data-stu-id="d08ad-105">To test the pool deployment</span></span>

1.  <span data-ttu-id="d08ad-106">С помощью оснасток "пользователи и компьютеры Active Directory" можно добавить объект "пользователи Active Directory" роли "Администратор" для развертывания Lync Server 2013 (на котором установлена панель управления Lync Server 2013) в группу **ксадминистратор** .</span><span class="sxs-lookup"><span data-stu-id="d08ad-106">Use Active Directory Computers and Users to add the Active Directory user object of the administrator role for the Lync Server 2013 deployment (on which Lync Server 2013 Control Panel is installed) to the **CSAdministrator** group.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="d08ad-107">Если вы не добавите соответствующих пользователей и группы в группу Ксадминисторс, то при открытии панели управления Lync Server появляется сообщение об ошибке, в котором говорится о том, что отказано в доступе из-за сбоя авторизации управления доступом на основе ролей (RBAC).</span><span class="sxs-lookup"><span data-stu-id="d08ad-107">If you do not add the appropriate users and groups to the CsAdministors group, you will receive an error when opening Lync Server Control Panel, which states that “Unauthorized: Access is denied due to a role-based access control (RBAC) authorization failure.”</span></span>

    
    </div>

2.  <span data-ttu-id="d08ad-108">Если объект-пользователь уже выполнил вход в систему, выйдите из системы, а затем повторите вход, чтобы зарегистрировать назначение новой группы.</span><span class="sxs-lookup"><span data-stu-id="d08ad-108">If the user object is currently logged on, log off and then log on again to register the new group assignment.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d08ad-109">Учетная запись пользователя не может быть локальным администратором любого сервера, на котором работает Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d08ad-109">The user account cannot be the local administrator of any server running Lync Server 2013.</span></span>

    
    </div>

3.  <span data-ttu-id="d08ad-110">Войдите в систему с помощью учетной записи администратора на компьютере, на котором установлена панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d08ad-110">Use the administrative account to log on to the computer where Lync Server Control Panel is installed.</span></span>

4.  <span data-ttu-id="d08ad-111">Откройте панель управления Lync Server и укажите учетные данные при появлении соответствующего запроса.</span><span class="sxs-lookup"><span data-stu-id="d08ad-111">Start Lync Server Control Panel, and then provide credentials, if prompted.</span></span> <span data-ttu-id="d08ad-112">На панели управления сервера Lync Server выводятся сведения о развертывании.</span><span class="sxs-lookup"><span data-stu-id="d08ad-112">Lync Server Control Panel displays deployment information.</span></span>

5.  <span data-ttu-id="d08ad-113">На панели навигации слева выберите пункт **топология**и убедитесь, что состояние службы отображается на компьютере с зеленой стрелкой и рядом с каждой ролью сервера Lync Server, которая была развернута и переведена в сеть, находится зеленая галочка для состояния репликации.</span><span class="sxs-lookup"><span data-stu-id="d08ad-113">In the left navigation bar, click **Topology**, and then confirm that the service status shows a computer with a green arrow and that a green check mark for replication status is next to each Lync Server server role that has been deployed and brought online.</span></span>

6.  <span data-ttu-id="d08ad-114">В левой панели навигации щелкните элемент **Пользователи**, а затем **Включить пользователей**.</span><span class="sxs-lookup"><span data-stu-id="d08ad-114">In the left navigation bar, click **Users**, and then click **Enable users**.</span></span>

7.  <span data-ttu-id="d08ad-115">На странице **Новый пользователь Lync Server** нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="d08ad-115">On the **New Lync Server User** page, click **Add**.</span></span>

8.  <span data-ttu-id="d08ad-116">Чтобы определить параметры поиска для объектов, на странице **Выбор из Active Directory** можно щелкнуть меню **Поиск** и выбрать пункт **Добавить фильтр** (необязательно).</span><span class="sxs-lookup"><span data-stu-id="d08ad-116">To define search parameters for the objects you want to find, on the **Select from Active Directory** page, you can select **Search**, and then optionally click **Add Filter**.</span></span> <span data-ttu-id="d08ad-117">Можно также выбрать команду **Поиск LDAP** и ввести выражение LDAP для фильтрации или ограничения числа возвращаемых объектов.</span><span class="sxs-lookup"><span data-stu-id="d08ad-117">You can also select **LDAP search** and enter an LDAP expression to filter or limit the objects that will be returned.</span></span> <span data-ttu-id="d08ad-118">Определив параметры поиска, Клинк **найти**.</span><span class="sxs-lookup"><span data-stu-id="d08ad-118">After you have decided on your Search options, clink **Find**.</span></span>

9.  <span data-ttu-id="d08ad-119">В области результаты поиска выберите все объекты для этого сеанса поиска, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="d08ad-119">In the Search results pane, select all the objects for this search session, and then click **OK**.</span></span>

10. <span data-ttu-id="d08ad-120">На странице **нового пользователя Lync Server** выделенные объекты отображаются в окне **Пользователи** .</span><span class="sxs-lookup"><span data-stu-id="d08ad-120">On the **New Lync Server User** page, the object or objects you selected are in the **Users** display.</span></span> <span data-ttu-id="d08ad-121">В списке **Назначение пользователей группе** выберите сервер, на котором должны быть размещены объекты.</span><span class="sxs-lookup"><span data-stu-id="d08ad-121">In the **Assign users to a pool** list, select the server where the objects should be homed.</span></span>
    
    <span data-ttu-id="d08ad-122">Ниже приведены некоторые параметры для настройки объектов.</span><span class="sxs-lookup"><span data-stu-id="d08ad-122">Following are a number of options for configuring the objects.</span></span>
    
      - <span data-ttu-id="d08ad-123">**Создать пользовательский URI для SIP**,</span><span class="sxs-lookup"><span data-stu-id="d08ad-123">**Generate user’s SIP URI**</span></span>
    
      - <span data-ttu-id="d08ad-124">**Телефония**</span><span class="sxs-lookup"><span data-stu-id="d08ad-124">**Telephony**</span></span>
    
      - <span data-ttu-id="d08ad-125">**Line URI (URI линии)**,</span><span class="sxs-lookup"><span data-stu-id="d08ad-125">**Line URI**</span></span>
    
      - <span data-ttu-id="d08ad-126">**Политика конференц-связи**,</span><span class="sxs-lookup"><span data-stu-id="d08ad-126">**Conferencing policy**</span></span>
    
      - <span data-ttu-id="d08ad-127">**Политика версий клиентов**,</span><span class="sxs-lookup"><span data-stu-id="d08ad-127">**Client version policy**</span></span>
    
      - <span data-ttu-id="d08ad-128">**Политика ПИН-кода**,</span><span class="sxs-lookup"><span data-stu-id="d08ad-128">**PIN policy**</span></span>
    
      - <span data-ttu-id="d08ad-129">**Политика внешнего доступа**,</span><span class="sxs-lookup"><span data-stu-id="d08ad-129">**External access policy**</span></span>
    
      - <span data-ttu-id="d08ad-130">**Политика архивации**,</span><span class="sxs-lookup"><span data-stu-id="d08ad-130">**Archiving policy**</span></span>
    
      - <span data-ttu-id="d08ad-131">**Политика расположения**,</span><span class="sxs-lookup"><span data-stu-id="d08ad-131">**Location policy**</span></span>
    
      - <span data-ttu-id="d08ad-132">**Политика клиента**.</span><span class="sxs-lookup"><span data-stu-id="d08ad-132">**Client policy**</span></span>
    
    <span data-ttu-id="d08ad-133">Для целей тестирования основных функций выберите предпочтительный параметр для URI-адресу для **пользовательского** интерфейса (другие параметры в конфигурации будут использовать параметры по умолчанию), а затем нажмите кнопку **включить**.</span><span class="sxs-lookup"><span data-stu-id="d08ad-133">For the purposes of testing the basic functionality, select the option you prefer for the **Generate user’s SIP URI** setting (the other options in the configuration will use default settings), and then click **Enable**.</span></span>

11. <span data-ttu-id="d08ad-134">Откроется страница со сводкой, на которой показан флажок в столбце **Enabled** , указывающий на то, что объекты теперь готовы к использованию.</span><span class="sxs-lookup"><span data-stu-id="d08ad-134">A summary page is displayed that shows a check mark in the **Enabled** column to indicate that the objects are now ready for use.</span></span> <span data-ttu-id="d08ad-135">В столбце **SIP-адрес** будет отображаться адрес, который требуется для настройки входа пользователя.</span><span class="sxs-lookup"><span data-stu-id="d08ad-135">The **SIP address** column displays the address you need for the user sign-in configuration.</span></span>

12. <span data-ttu-id="d08ad-136">Зарегистрируйте одного пользователя на компьютере, который присоединен к домену, а также на другом компьютере домена.</span><span class="sxs-lookup"><span data-stu-id="d08ad-136">Log one user on to a computer that is joined to the domain, and another user on to another computer in the domain.</span></span>

13. <span data-ttu-id="d08ad-137">Установите Lync 2013 на каждом из двух клиентских компьютеров, а затем убедитесь, что оба пользователя могут входить в Lync Server 2013 и обмениваться мгновенными сообщениями друг с другом.</span><span class="sxs-lookup"><span data-stu-id="d08ad-137">Install Lync 2013 on each of the two client computers, and then verify that both users can sign in to Lync Server 2013 and can send instant messages to each other.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d08ad-138">См. также</span><span class="sxs-lookup"><span data-stu-id="d08ad-138">See Also</span></span>


[<span data-ttu-id="d08ad-139">Развертывание клиентов и устройств в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d08ad-139">Deploying clients and devices in Lync Server 2013</span></span>](lync-server-2013-deploying-clients-and-devices.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

