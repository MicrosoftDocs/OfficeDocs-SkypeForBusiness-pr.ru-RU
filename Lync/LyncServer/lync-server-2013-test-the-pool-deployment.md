---
title: 'Lync Server 2013: тестирование развертывания пула'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test the pool deployment
ms:assetid: ffd80617-155a-4041-bbeb-74503e7938dd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413092(v=OCS.15)
ms:contentKeyID: 48185976
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a808eb575dcccbce45e24f089b41721b41623b13
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48519066"
---
# <a name="test-the-pool-deployment-in-lync-server-2013"></a><span data-ttu-id="dee13-102">Тестирование развертывания пула в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dee13-102">Test the pool deployment in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dee13-103">_**Последнее изменение темы:** 2013-09-25_</span><span class="sxs-lookup"><span data-stu-id="dee13-103">_**Topic Last Modified:** 2013-09-25_</span></span>

<span data-ttu-id="dee13-104">В следующей процедуре описывается тестирование развертывания пула переднего плана.</span><span class="sxs-lookup"><span data-stu-id="dee13-104">The following procedure describes how to test the deployment of the Front End pool.</span></span>

<div>

## <a name="to-test-the-pool-deployment"></a><span data-ttu-id="dee13-105">To test the pool deployment</span><span class="sxs-lookup"><span data-stu-id="dee13-105">To test the pool deployment</span></span>

1.  <span data-ttu-id="dee13-106">Используйте "пользователи и компьютеры Active Directory", чтобы добавить объект пользователя Active Directory роли администратора для развертывания Lync Server 2013 (на котором установлена панель управления Lync Server 2013) в группу **CSAdministrator** .</span><span class="sxs-lookup"><span data-stu-id="dee13-106">Use Active Directory Computers and Users to add the Active Directory user object of the administrator role for the Lync Server 2013 deployment (on which Lync Server 2013 Control Panel is installed) to the **CSAdministrator** group.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="dee13-107">Если вы не добавите соответствующих пользователей и группы в группу Ксадминисторс, вы получите сообщение об ошибке при открытии панели управления Lync Server, в котором указано, что "несанкционированный доступ запрещен" из-за сбоя авторизации управления доступом на основе ролей (RBAC). "</span><span class="sxs-lookup"><span data-stu-id="dee13-107">If you do not add the appropriate users and groups to the CsAdministors group, you will receive an error when opening Lync Server Control Panel, which states that “Unauthorized: Access is denied due to a role-based access control (RBAC) authorization failure.”</span></span>

    
    </div>

2.  <span data-ttu-id="dee13-108">Если объект-пользователь уже выполнил вход в систему, выйдите из системы, а затем повторите вход, чтобы зарегистрировать назначение новой группы.</span><span class="sxs-lookup"><span data-stu-id="dee13-108">If the user object is currently logged on, log off and then log on again to register the new group assignment.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="dee13-109">Учетная запись пользователя не может быть локальным администратором любого сервера, на котором работает Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="dee13-109">The user account cannot be the local administrator of any server running Lync Server 2013.</span></span>

    
    </div>

3.  <span data-ttu-id="dee13-110">Используйте учетную запись администратора, чтобы войти на компьютер, на котором установлена панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="dee13-110">Use the administrative account to log on to the computer where Lync Server Control Panel is installed.</span></span>

4.  <span data-ttu-id="dee13-111">Запустите Панель управления Lync Server и при необходимости укажите учетные данные.</span><span class="sxs-lookup"><span data-stu-id="dee13-111">Start Lync Server Control Panel, and then provide credentials, if prompted.</span></span> <span data-ttu-id="dee13-112">В панели управления Lync Server отображаются сведения о развертывании.</span><span class="sxs-lookup"><span data-stu-id="dee13-112">Lync Server Control Panel displays deployment information.</span></span>

5.  <span data-ttu-id="dee13-113">В левой панели навигации щелкните Topology ( **топология**), а затем убедитесь, что состояние службы показывает компьютер с зеленой стрелкой и что возле каждой роли сервера Lync Server, которая была развернута и переведена в оперативный режим, отображается зеленая галочка для состояния репликации.</span><span class="sxs-lookup"><span data-stu-id="dee13-113">In the left navigation bar, click **Topology**, and then confirm that the service status shows a computer with a green arrow and that a green check mark for replication status is next to each Lync Server server role that has been deployed and brought online.</span></span>

6.  <span data-ttu-id="dee13-114">В левой области навигации щелкните элемент **Пользователи**, а затем **Включить пользователей**.</span><span class="sxs-lookup"><span data-stu-id="dee13-114">In the left navigation bar, click **Users**, and then click **Enable users**.</span></span>

7.  <span data-ttu-id="dee13-115">На странице **New Lync Server User** (Создание пользователя Lync Server) нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="dee13-115">On the **New Lync Server User** page, click **Add**.</span></span>

8.  <span data-ttu-id="dee13-p102">Чтобы определить параметры поиска для объектов, на странице **Select from Active Directory** (Выбор в Active Directory) можно щелкнуть меню **Поиск** и выбрать пункт **Добавить фильтр** (необязательно). Можно также выбрать команду **Поиск LDAP** и ввести выражение LDAP для фильтрации или ограничения числа возвращаемых объектов. Настроив все необходимые параметры поиска, нажмите кнопку **Найти**.</span><span class="sxs-lookup"><span data-stu-id="dee13-p102">To define search parameters for the objects you want to find, on the **Select from Active Directory** page, you can select **Search**, and then optionally click **Add Filter**. You can also select **LDAP search** and enter an LDAP expression to filter or limit the objects that will be returned. After you have decided on your Search options, clink **Find**.</span></span>

9.  <span data-ttu-id="dee13-119">В области результатов поиска выберите все объекты для данного сеанса поиска, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="dee13-119">In the Search results pane, select all the objects for this search session, and then click **OK**.</span></span>

10. <span data-ttu-id="dee13-p103">На странице **Создание пользователя Lync Server** выбранные объекты будут отображаться в разделе **Пользователи**. В списке **Assign users to a pool** (Назначить пользователей пулу) выберите сервер для размещения объектов.</span><span class="sxs-lookup"><span data-stu-id="dee13-p103">On the **New Lync Server User** page, the object or objects you selected are in the **Users** display. In the **Assign users to a pool** list, select the server where the objects should be homed.</span></span>
    
    <span data-ttu-id="dee13-122">Ниже приводятся параметры для настройки объектов:</span><span class="sxs-lookup"><span data-stu-id="dee13-122">Following are a number of options for configuring the objects.</span></span>
    
      - <span data-ttu-id="dee13-123">**Generate user\rquote s SIP URI** (Создать URI SIP пользователя),</span><span class="sxs-lookup"><span data-stu-id="dee13-123">**Generate user’s SIP URI**</span></span>
    
      - <span data-ttu-id="dee13-124">**Телефонии**</span><span class="sxs-lookup"><span data-stu-id="dee13-124">**Telephony**</span></span>
    
      - <span data-ttu-id="dee13-125">**Line URI** (URI линии),</span><span class="sxs-lookup"><span data-stu-id="dee13-125">**Line URI**</span></span>
    
      - <span data-ttu-id="dee13-126">**Политика конференц-связи**,</span><span class="sxs-lookup"><span data-stu-id="dee13-126">**Conferencing policy**</span></span>
    
      - <span data-ttu-id="dee13-127">**Политика версий клиентов**,</span><span class="sxs-lookup"><span data-stu-id="dee13-127">**Client version policy**</span></span>
    
      - <span data-ttu-id="dee13-128">**PIN policy** (Политика ПИН-кода),</span><span class="sxs-lookup"><span data-stu-id="dee13-128">**PIN policy**</span></span>
    
      - <span data-ttu-id="dee13-129">**Политика внешнего доступа**,</span><span class="sxs-lookup"><span data-stu-id="dee13-129">**External access policy**</span></span>
    
      - <span data-ttu-id="dee13-130">**Archiving policy** (Политика архивации),</span><span class="sxs-lookup"><span data-stu-id="dee13-130">**Archiving policy**</span></span>
    
      - <span data-ttu-id="dee13-131">**Location policy** (Политика расположения),</span><span class="sxs-lookup"><span data-stu-id="dee13-131">**Location policy**</span></span>
    
      - <span data-ttu-id="dee13-132">**Client policy** (Политика клиента).</span><span class="sxs-lookup"><span data-stu-id="dee13-132">**Client policy**</span></span>
    
    <span data-ttu-id="dee13-133">В целях проверки общей функциональности выберите нужный вариант для параметра **Создать URI SIP пользователя** (для других параметров в конфигурации будут использоваться значения по умолчанию), а затем нажмите кнопку **Включить**.</span><span class="sxs-lookup"><span data-stu-id="dee13-133">For the purposes of testing the basic functionality, select the option you prefer for the **Generate user’s SIP URI** setting (the other options in the configuration will use default settings), and then click **Enable**.</span></span>

11. <span data-ttu-id="dee13-p104">На экран будет выведена страница сводки, и в столбце **Включено**будет установлена галочка, указывающая на готовность объекта к использованию. В столбце **SIP-адрес** будет отображаться адрес, который требуется для настройки входа пользователя.</span><span class="sxs-lookup"><span data-stu-id="dee13-p104">A summary page is displayed that shows a check mark in the **Enabled** column to indicate that the objects are now ready for use. The **SIP address** column displays the address you need for the user sign-in configuration.</span></span>

12. <span data-ttu-id="dee13-136">Выполните вход одного пользователя на компьютер, присоединенный к домену, а другого ? на другой компьютер в домене.</span><span class="sxs-lookup"><span data-stu-id="dee13-136">Log one user on to a computer that is joined to the domain, and another user on to another computer in the domain.</span></span>

13. <span data-ttu-id="dee13-137">Установите Lync 2013 на каждом из двух клиентских компьютеров, а затем убедитесь, что оба пользователя могут войти в Lync Server 2013 и обмениваться мгновенными сообщениями.</span><span class="sxs-lookup"><span data-stu-id="dee13-137">Install Lync 2013 on each of the two client computers, and then verify that both users can sign in to Lync Server 2013 and can send instant messages to each other.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="dee13-138">См. также</span><span class="sxs-lookup"><span data-stu-id="dee13-138">See Also</span></span>


[<span data-ttu-id="dee13-139">Развертывание клиентов и устройств в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dee13-139">Deploying clients and devices in Lync Server 2013</span></span>](lync-server-2013-deploying-clients-and-devices.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

