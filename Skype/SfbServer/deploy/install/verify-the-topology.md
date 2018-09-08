---
title: Проверка топологии в Скайп для Business Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 7/14/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a4f4bad1-fc59-47ce-a3ea-b1b893769db6
description: 'Сводка: Узнайте, как проверить Скайп для топологии Business Server и надлежащую работу серверы Active Directory. Загрузить бесплатную пробную версию программы Скайп для Business Server в центре Microsoft оценки по: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server.'
ms.openlocfilehash: ed06860837805886f1d2287f23281edb90c470c1
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "23881975"
---
# <a name="verify-the-topology-in-skype-for-business-server"></a><span data-ttu-id="37309-104">Проверка топологии в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="37309-104">Verify the topology in Skype for Business Server</span></span>
 
<span data-ttu-id="37309-105">**Сводка:** Узнайте, как проверить Скайп для топологии Business Server и надлежащую работу серверы Active Directory.</span><span class="sxs-lookup"><span data-stu-id="37309-105">**Summary:** Learn how to verify the Skype for Business Server topology and Active Directory servers are working as expected.</span></span> <span data-ttu-id="37309-106">Загрузите бесплатную пробную версию программы Скайп для Business Server [Центр оценки Microsoft](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span><span class="sxs-lookup"><span data-stu-id="37309-106">Download a free trial of Skype for Business Server from the [Microsoft Evaluation center](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span></span>
  
<span data-ttu-id="37309-107">После публикации топологии и Скайп для компонентов системы Business Server, установленных на каждом из серверов в топологии, вы готовы к убедитесь, что топология работает как надо.</span><span class="sxs-lookup"><span data-stu-id="37309-107">After you have the topology published and the Skype for Business Server system components installed on each of the servers in the topology, you are ready to verify that the topology is working as expected.</span></span> <span data-ttu-id="37309-108">Включают в себя проверку, конфигурации распространенных из на все серверы Active Directory, чтобы весь домен известно, что Скайп для бизнеса доступна в домене.</span><span class="sxs-lookup"><span data-stu-id="37309-108">This includes verifying that the configuration has propagated out to all of the Active Directory servers so that the entire domain knows Skype for Business is available in the domain.</span></span> <span data-ttu-id="37309-109">Шаги с 1 по 5 могут выполняться в произвольном порядке.</span><span class="sxs-lookup"><span data-stu-id="37309-109">You can do steps 1 through 5 in any order.</span></span> <span data-ttu-id="37309-110">Но шаги 6, 7 и 8 должны выполняться в указанном порядке после шагов с 1 по 5, как показано на схеме.</span><span class="sxs-lookup"><span data-stu-id="37309-110">However, you must do steps 6, 7, and 8 in order, and after steps 1 through 5, as outlined in the diagram.</span></span> <span data-ttu-id="37309-111">Проверка топологии — это шаг 8 из 8.</span><span class="sxs-lookup"><span data-stu-id="37309-111">Verifying the topology is step 8 of 8.</span></span>
  
![Обзорная схема.](../../media/c8698b53-1282-4978-a9a6-ca3f7a778f60.png)
  
## <a name="test-the-front-end-pool-deployment"></a><span data-ttu-id="37309-113">Проверка развертывания пула переднего плана</span><span class="sxs-lookup"><span data-stu-id="37309-113">Test the Front End pool deployment</span></span>

<span data-ttu-id="37309-114">Последний этап — тестирование пула переднего плана и убедитесь, что Скайп пользователей могут взаимодействовать друг с другом.</span><span class="sxs-lookup"><span data-stu-id="37309-114">The final step is to test the Front End pool and confirm that Skype for Business clients can communicate with each other.</span></span> 
  
### <a name="add-users-and-verify-client-connectivity"></a><span data-ttu-id="37309-115">Добавление пользователей и проверка возможности подключения клиентов</span><span class="sxs-lookup"><span data-stu-id="37309-115">Add users and verify client connectivity</span></span>

1. <span data-ttu-id="37309-116">Используйте — пользователи и компьютеры Active Directory добавьте объект пользователя Active Directory роли администратора для Скайп для развертывания Business Server (на котором установлена Скайп для панели управления Business Server) в группу **CSAdministrator** .</span><span class="sxs-lookup"><span data-stu-id="37309-116">Use Active Directory Computers and Users to add the Active Directory user object of the administrator role for the Skype for Business Server deployment (on which Skype for Business Server Control Panel is installed) to the **CSAdministrator** group.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="37309-117">Если не добавить пользователей и группы в группу CsAdministors, при открытии Скайп для панели управления Business Server, который считывает, появится сообщение об ошибке «не санкционировано: доступ запрещен из-за сбоя доступом на основе ролей (RBAC) элемента управления авторизации ."</span><span class="sxs-lookup"><span data-stu-id="37309-117">If you do not add the appropriate users and groups to the CsAdministors group, you will receive an error when you open Skype for Business Server Control Panel which reads, "Unauthorized: Access is denied due to a role-based access control (RBAC) authorization failure."</span></span> 
  
2. <span data-ttu-id="37309-118">Если объект-пользователь уже выполнил вход в систему, выйдите из системы, а затем повторите вход, чтобы зарегистрировать назначение новой группы.</span><span class="sxs-lookup"><span data-stu-id="37309-118">If the user object is currently logged on, log off and then log on again to register the new group assignment.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="37309-119">Учетная запись пользователя не может быть локальным администратором любого сервера под управлением Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="37309-119">The user account cannot be the local administrator of any server running Skype for Business Server.</span></span> 
  
3. <span data-ttu-id="37309-120">Используйте учетную запись администратора войдите в систему компьютера, установленными Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="37309-120">Use the administrative account to log on to the computer where Skype for Business Server Control Panel is installed.</span></span>
    
4. <span data-ttu-id="37309-121">Запустите Скайп для панели управления Business Server и укажите учетные данные, если запрос.</span><span class="sxs-lookup"><span data-stu-id="37309-121">Start Skype for Business Server Control Panel, and then provide credentials, if prompted.</span></span> <span data-ttu-id="37309-122">Скайп для панели управления сервера Business отображает сведения о развертывании.</span><span class="sxs-lookup"><span data-stu-id="37309-122">Skype for Business Server Control Panel displays deployment information.</span></span>
    
5. <span data-ttu-id="37309-123">В левой панели навигации щелкните **Топология**и подтвердите показывает, что состояние службы компьютера с зеленой стрелкой, и что для состояние репликации зеленая галочка рядом с каждой Скайп для Business Server role, который был развернут и в оперативный режим.</span><span class="sxs-lookup"><span data-stu-id="37309-123">In the left navigation bar, click **Topology**, and then confirm that the service status shows a computer with a green arrow and that a green check mark for replication status is next to each Skype for Business Server role that has been deployed and brought online.</span></span> 
    
6. <span data-ttu-id="37309-124">В левой панели навигации щелкните элемент **Пользователи**, а затем **Включить пользователей**.</span><span class="sxs-lookup"><span data-stu-id="37309-124">In the left navigation bar, click **Users**, and then click **Enable users**.</span></span> 
    
7. <span data-ttu-id="37309-125">На странице " **Новый Скайп для бизнес-пользователя сервера** " нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="37309-125">On the **New Skype for Business Server User** page, click **Add**.</span></span>
    
8. <span data-ttu-id="37309-p105">Чтобы определить параметры поиска для объектов, на странице **Выбор из Active Directory** можно щелкнуть меню **Поиск** и выбрать пункт **Добавить фильтр** (необязательно). Можно также выбрать команду **Поиск LDAP** и ввести выражение LDAP для фильтрации или ограничения числа возвращаемых объектов. Настроив все необходимые параметры поиска, нажмите кнопку **Найти**.</span><span class="sxs-lookup"><span data-stu-id="37309-p105">To define search parameters for the objects you want to find, on the **Select from Active Directory** page, you can select **Search**, and then optionally click **Add Filter**. You can also select **LDAP search** and enter an LDAP expression to filter or limit the objects that will be returned. After you have decided on your Search options, click **Find**.</span></span>
    
9. <span data-ttu-id="37309-129">В области результатов поиска выберите добавляемых пользователей и нажмите кнопку **OK**.</span><span class="sxs-lookup"><span data-stu-id="37309-129">In the Search results pane, select the users you want to add, and then click **OK**.</span></span>
    
10. <span data-ttu-id="37309-130">На странице **Новый Скайп для пользователя Business Server** выбранных пользователей находятся в отображения **пользователей** .</span><span class="sxs-lookup"><span data-stu-id="37309-130">On the **New Skype for Business Server User** page, the users you selected are in the **Users** display.</span></span> <span data-ttu-id="37309-131">В списке **Назначение пользователей для пула** выберите сервер для размещения пользователей.</span><span class="sxs-lookup"><span data-stu-id="37309-131">In the **Assign users to a pool** list, select the server where the users should reside.</span></span>
    
    <span data-ttu-id="37309-132">Ниже приведен список параметров для настройки объектов.</span><span class="sxs-lookup"><span data-stu-id="37309-132">The following is a list of options you can use to configure the objects.</span></span>
    
    - <span data-ttu-id="37309-133">**Создать URI SIP пользователя**</span><span class="sxs-lookup"><span data-stu-id="37309-133">**Generate user's SIP URI**</span></span>
    
    - <span data-ttu-id="37309-134">**Телефония**</span><span class="sxs-lookup"><span data-stu-id="37309-134">**Telephony**</span></span>
    
    - <span data-ttu-id="37309-135">**Line URI (URI линии)**,</span><span class="sxs-lookup"><span data-stu-id="37309-135">**Line URI**</span></span>
    
    - <span data-ttu-id="37309-136">**Политика конференц-связи**,</span><span class="sxs-lookup"><span data-stu-id="37309-136">**Conferencing policy**</span></span>
    
    - <span data-ttu-id="37309-137">**Политика версий клиентов**,</span><span class="sxs-lookup"><span data-stu-id="37309-137">**Client version policy**</span></span>
    
    - <span data-ttu-id="37309-138">**Политика ПИН-кода**,</span><span class="sxs-lookup"><span data-stu-id="37309-138">**PIN policy**</span></span>
    
    - <span data-ttu-id="37309-139">**Политика внешнего доступа**,</span><span class="sxs-lookup"><span data-stu-id="37309-139">**External access policy**</span></span>
    
    - <span data-ttu-id="37309-140">**Политика архивации**,</span><span class="sxs-lookup"><span data-stu-id="37309-140">**Archiving policy**</span></span>
    
    - <span data-ttu-id="37309-141">**Политика расположения**,</span><span class="sxs-lookup"><span data-stu-id="37309-141">**Location policy**</span></span>
    
    - <span data-ttu-id="37309-142">**Политика клиента**.</span><span class="sxs-lookup"><span data-stu-id="37309-142">**Client policy**</span></span>
    
    <span data-ttu-id="37309-143">Чтобы проверить основные функциональные возможности, выберите параметр предпочитают для параметра **URI SIP пользователя Generate** (другие параметры конфигурации параметры по умолчанию) и нажмите кнопку **Включить**, как показано на рисунке.</span><span class="sxs-lookup"><span data-stu-id="37309-143">To test the basic functionality, select the option you prefer for the **Generate user's SIP URI** setting (the other options in the configuration use default settings), and then click **Enable**, as shown in the figure.</span></span>
    
     ![Включение пользователей на панели управления.](../../media/7ee8717d-9a1f-4864-8f45-71071c88878f.png)
  
11. <span data-ttu-id="37309-p107">На экран будет выведена страница сводки, и в столбце **Включено** будет установлена галочка, указывающая на завершение настройки параметров пользователя. В столбце **SIP-адрес** будет отображаться адрес, который требуется для настройки входа пользователя.</span><span class="sxs-lookup"><span data-stu-id="37309-p107">A summary page is displayed that shows a check mark in the **Enabled** column to indicate that the users are setup. The **SIP address** column displays the address you need for the user sign-in configuration.</span></span>
    
     ![Пользователи, добавленные на панель управления Skype для бизнеса Server.](../../media/8960548a-8d6d-44c5-bc01-6f9fb11b7588.png)
  
12. <span data-ttu-id="37309-148">Выполните вход одного пользователя на компьютер, присоединенный к домену, а другого пользователя — на другой компьютер в домене.</span><span class="sxs-lookup"><span data-stu-id="37309-148">Log one user on to a computer that is joined to the domain and another user on to another computer in the domain.</span></span>
    
13. <span data-ttu-id="37309-149">Установка Скайп для клиента Business на двух клиентских компьютерах и затем убедитесь, что оба пользователя могут войти в систему Скайп, Business Server и отправлять мгновенные сообщения друг с другом.</span><span class="sxs-lookup"><span data-stu-id="37309-149">Install Skype for Business client on each of the two client computers, and then verify that both users can sign in to Skype for Business Server and can send instant messages to each other.</span></span>
    

