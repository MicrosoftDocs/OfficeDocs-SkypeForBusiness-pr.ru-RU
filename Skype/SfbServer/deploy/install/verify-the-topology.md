---
title: Проверка топологии в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 7/14/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a4f4bad1-fc59-47ce-a3ea-b1b893769db6
description: 'Сводка. Узнайте, как проверить работу топологии Skype для бизнеса Server и серверов Active Directory. Скачайте бесплатную пробную версия Skype для бизнеса Server в Центре оценки Майкрософт по https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server ссылке:'
ms.openlocfilehash: 0c2307f3ad0416a7175d92a1440744dbda9b31d3
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49833839"
---
# <a name="verify-the-topology-in-skype-for-business-server"></a><span data-ttu-id="59b94-104">Проверка топологии в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="59b94-104">Verify the topology in Skype for Business Server</span></span>
 
<span data-ttu-id="59b94-105">**Сводка:** Узнайте, как проверить работу топологии Skype для бизнеса Server и серверов Active Directory.</span><span class="sxs-lookup"><span data-stu-id="59b94-105">**Summary:** Learn how to verify the Skype for Business Server topology and Active Directory servers are working as expected.</span></span> <span data-ttu-id="59b94-106">Скачайте бесплатную пробную версия Skype для бизнеса Server из [Центра оценки Майкрософт.](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)</span><span class="sxs-lookup"><span data-stu-id="59b94-106">Download a free trial of Skype for Business Server from the [Microsoft Evaluation center](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span></span>
  
<span data-ttu-id="59b94-107">После публикации топологии и установки системных компонентов Skype для бизнеса Server на каждом сервере в топологии можно убедиться, что топология работает ожидаемым образом.</span><span class="sxs-lookup"><span data-stu-id="59b94-107">After you have the topology published and the Skype for Business Server system components installed on each of the servers in the topology, you are ready to verify that the topology is working as expected.</span></span> <span data-ttu-id="59b94-108">Это включает проверку распространения конфигурации на все серверы Active Directory, чтобы весь домен знал, что в домене доступен Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="59b94-108">This includes verifying that the configuration has propagated out to all of the Active Directory servers so that the entire domain knows Skype for Business is available in the domain.</span></span> <span data-ttu-id="59b94-109">Шаги 1-5 можно делать в любом порядке.</span><span class="sxs-lookup"><span data-stu-id="59b94-109">You can do steps 1 through 5 in any order.</span></span> <span data-ttu-id="59b94-110">Однако шаги 6, 7 и 8 необходимо делать по порядку и после шагов с 1 по 5, как описано на схеме.</span><span class="sxs-lookup"><span data-stu-id="59b94-110">However, you must do steps 6, 7, and 8 in order, and after steps 1 through 5, as outlined in the diagram.</span></span> <span data-ttu-id="59b94-111">Проверка топологии — шаг 8 из 8.</span><span class="sxs-lookup"><span data-stu-id="59b94-111">Verifying the topology is step 8 of 8.</span></span>
  
![Обзорная схема.](../../media/c8698b53-1282-4978-a9a6-ca3f7a778f60.png)
  
## <a name="test-the-front-end-pool-deployment"></a><span data-ttu-id="59b94-113">Тестирование развертывания пула переднего конца</span><span class="sxs-lookup"><span data-stu-id="59b94-113">Test the Front End pool deployment</span></span>

<span data-ttu-id="59b94-114">Последний этап — тестирование пула переднего входа и подтверждение того, что клиенты Skype для бизнеса могут взаимодействовать друг с другом.</span><span class="sxs-lookup"><span data-stu-id="59b94-114">The final step is to test the Front End pool and confirm that Skype for Business clients can communicate with each other.</span></span> 
  
### <a name="add-users-and-verify-client-connectivity"></a><span data-ttu-id="59b94-115">Добавление пользователей и проверка подключения клиентов</span><span class="sxs-lookup"><span data-stu-id="59b94-115">Add users and verify client connectivity</span></span>

1. <span data-ttu-id="59b94-116">Используйте компьютеры и пользователи Active Directory, чтобы добавить объект пользователя Active Directory роли администратора для развертывания Skype для бизнеса Server (на котором установлена панель управления Skype для бизнеса Server) в группу **CSAdministrator.**</span><span class="sxs-lookup"><span data-stu-id="59b94-116">Use Active Directory Computers and Users to add the Active Directory user object of the administrator role for the Skype for Business Server deployment (on which Skype for Business Server Control Panel is installed) to the **CSAdministrator** group.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="59b94-117">Если в группу CsAdministors не будут добавлены соответствующие пользователи и группы, при откройте панель управления Skype для бизнеса Server с текстом "Unauthorized: Access is denied due to a role-based access control (RBAC) authorization failure".</span><span class="sxs-lookup"><span data-stu-id="59b94-117">If you do not add the appropriate users and groups to the CsAdministors group, you will receive an error when you open Skype for Business Server Control Panel which reads, "Unauthorized: Access is denied due to a role-based access control (RBAC) authorization failure."</span></span> 
  
2. <span data-ttu-id="59b94-118">Если объект-пользователь уже выполнил вход в систему, выйдите из системы, а затем повторите вход, чтобы зарегистрировать назначение новой группы.</span><span class="sxs-lookup"><span data-stu-id="59b94-118">If the user object is currently logged on, log off and then log on again to register the new group assignment.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="59b94-119">Учетная запись пользователя не может быть локальным администратором любого сервера skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="59b94-119">The user account cannot be the local administrator of any server running Skype for Business Server.</span></span> 
  
3. <span data-ttu-id="59b94-120">Используйте учетную запись администратора для входа на компьютер, на котором установлена панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="59b94-120">Use the administrative account to log on to the computer where Skype for Business Server Control Panel is installed.</span></span>
    
4. <span data-ttu-id="59b94-121">Запустите панель управления Skype для бизнеса Server и в случае запроса укайте учетные данные.</span><span class="sxs-lookup"><span data-stu-id="59b94-121">Start Skype for Business Server Control Panel, and then provide credentials, if prompted.</span></span> <span data-ttu-id="59b94-122">На панели управления Skype для бизнеса Server отображаются сведения о развертывании.</span><span class="sxs-lookup"><span data-stu-id="59b94-122">Skype for Business Server Control Panel displays deployment information.</span></span>
    
5. <span data-ttu-id="59b94-123">In the left navigation bar, click **Topology**, and then confirm that the service status shows a computer with a green arrow and that a green check mark for replication status is next to each Skype for Business Server role that has been deployed and brought online.</span><span class="sxs-lookup"><span data-stu-id="59b94-123">In the left navigation bar, click **Topology**, and then confirm that the service status shows a computer with a green arrow and that a green check mark for replication status is next to each Skype for Business Server role that has been deployed and brought online.</span></span> 
    
6. <span data-ttu-id="59b94-124">В левой области навигации щелкните элемент **Пользователи**, а затем **Включить пользователей**.</span><span class="sxs-lookup"><span data-stu-id="59b94-124">In the left navigation bar, click **Users**, and then click **Enable users**.</span></span> 
    
7. <span data-ttu-id="59b94-125">На странице **"Новый пользователь Skype для бизнеса Server"** нажмите кнопку **"Добавить".**</span><span class="sxs-lookup"><span data-stu-id="59b94-125">On the **New Skype for Business Server User** page, click **Add**.</span></span>
    
8. <span data-ttu-id="59b94-126">Чтобы определить параметры поиска для объектов, на странице **Select from Active Directory** (Выбор в Active Directory) можно щелкнуть меню **Поиск** и выбрать пункт **Добавить фильтр** (необязательно).</span><span class="sxs-lookup"><span data-stu-id="59b94-126">To define search parameters for the objects you want to find, on the **Select from Active Directory** page, you can select **Search**, and then optionally click **Add Filter**.</span></span> <span data-ttu-id="59b94-127">Можно также выбрать команду **Поиск LDAP** и ввести выражение LDAP для фильтрации или ограничения числа возвращаемых объектов.</span><span class="sxs-lookup"><span data-stu-id="59b94-127">You can also select **LDAP search** and enter an LDAP expression to filter or limit the objects that will be returned.</span></span> <span data-ttu-id="59b94-128">После выбора параметров поиска нажмите кнопку **"Найти".**</span><span class="sxs-lookup"><span data-stu-id="59b94-128">After you have decided on your Search options, click **Find**.</span></span>
    
9. <span data-ttu-id="59b94-129">В области результатов поиска выберите пользователей, которые нужно добавить, и нажмите кнопку **"ОК".**</span><span class="sxs-lookup"><span data-stu-id="59b94-129">In the Search results pane, select the users you want to add, and then click **OK**.</span></span>
    
10. <span data-ttu-id="59b94-130">On the **New Skype for Business Server User** page, the users you selected are in the **Users** display.</span><span class="sxs-lookup"><span data-stu-id="59b94-130">On the **New Skype for Business Server User** page, the users you selected are in the **Users** display.</span></span> <span data-ttu-id="59b94-131">В **списке "Назначить** пользователей пулу" выберите сервер, на котором должны находиться пользователи.</span><span class="sxs-lookup"><span data-stu-id="59b94-131">In the **Assign users to a pool** list, select the server where the users should reside.</span></span>
    
    <span data-ttu-id="59b94-132">Ниже приводится список параметров, которые можно использовать для настройки объектов.</span><span class="sxs-lookup"><span data-stu-id="59b94-132">The following is a list of options you can use to configure the objects.</span></span>
    
    - <span data-ttu-id="59b94-133">**Создание URI SIP пользователя**</span><span class="sxs-lookup"><span data-stu-id="59b94-133">**Generate user's SIP URI**</span></span>
    
    - <span data-ttu-id="59b94-134">**Телефония**</span><span class="sxs-lookup"><span data-stu-id="59b94-134">**Telephony**</span></span>
    
    - <span data-ttu-id="59b94-135">**Line URI** (URI линии),</span><span class="sxs-lookup"><span data-stu-id="59b94-135">**Line URI**</span></span>
    
    - <span data-ttu-id="59b94-136">**Политика конференц-связи**,</span><span class="sxs-lookup"><span data-stu-id="59b94-136">**Conferencing policy**</span></span>
    
    - <span data-ttu-id="59b94-137">**Политика версий клиентов**,</span><span class="sxs-lookup"><span data-stu-id="59b94-137">**Client version policy**</span></span>
    
    - <span data-ttu-id="59b94-138">**PIN policy** (Политика ПИН-кода),</span><span class="sxs-lookup"><span data-stu-id="59b94-138">**PIN policy**</span></span>
    
    - <span data-ttu-id="59b94-139">**Политика внешнего доступа**,</span><span class="sxs-lookup"><span data-stu-id="59b94-139">**External access policy**</span></span>
    
    - <span data-ttu-id="59b94-140">**Archiving policy** (Политика архивации),</span><span class="sxs-lookup"><span data-stu-id="59b94-140">**Archiving policy**</span></span>
    
    - <span data-ttu-id="59b94-141">**Location policy** (Политика расположения),</span><span class="sxs-lookup"><span data-stu-id="59b94-141">**Location policy**</span></span>
    
    - <span data-ttu-id="59b94-142">**Client policy** (Политика клиента).</span><span class="sxs-lookup"><span data-stu-id="59b94-142">**Client policy**</span></span>
    
    <span data-ttu-id="59b94-143">Чтобы протестировать базовую функциональность, выберите параметр, который вы предпочитаете, для параметра **URI SIP** пользователя (другие параметры в конфигурации используют параметры по умолчанию), а затем нажмите кнопку "Включить", как показано на рисунке.</span><span class="sxs-lookup"><span data-stu-id="59b94-143">To test the basic functionality, select the option you prefer for the **Generate user's SIP URI** setting (the other options in the configuration use default settings), and then click **Enable**, as shown in the figure.</span></span>
    
     ![Включить пользователей в панели управления.](../../media/7ee8717d-9a1f-4864-8f45-71071c88878f.png)
  
11. <span data-ttu-id="59b94-145">Отобразилась страница сводки, на которую  в столбце "Включено" отображается отметка о том, что пользователи настроены.</span><span class="sxs-lookup"><span data-stu-id="59b94-145">A summary page is displayed that shows a check mark in the **Enabled** column to indicate that the users are setup.</span></span> <span data-ttu-id="59b94-146">В столбце **SIP-адрес** будет отображаться адрес, который требуется для настройки входа пользователя.</span><span class="sxs-lookup"><span data-stu-id="59b94-146">The **SIP address** column displays the address you need for the user sign-in configuration.</span></span>
    
     ![Пользователи, добавленные в панель управления Skype для бизнеса Server.](../../media/8960548a-8d6d-44c5-bc01-6f9fb11b7588.png)
  
12. <span data-ttu-id="59b94-148">Войдите в систему одного пользователя на компьютере, который присоединяется к домену, а другой — на другом компьютере в домене.</span><span class="sxs-lookup"><span data-stu-id="59b94-148">Log one user on to a computer that is joined to the domain and another user on to another computer in the domain.</span></span>
    
13. <span data-ttu-id="59b94-149">Установите клиент Skype для бизнеса на каждом из двух клиентских компьютеров, а затем убедитесь, что оба пользователя могут войти в Skype для бизнеса Server и отправлять мгновенные сообщения друг другу.</span><span class="sxs-lookup"><span data-stu-id="59b94-149">Install Skype for Business client on each of the two client computers, and then verify that both users can sign in to Skype for Business Server and can send instant messages to each other.</span></span>
    

