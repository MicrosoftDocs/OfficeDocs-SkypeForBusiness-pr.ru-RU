---
title: Проверка топологии в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 'Сводка. сведения о том, как убедиться, что топология сервера Skype для бизнеса и серверы Active Directory работают должным образом. Скачайте бесплатную пробную версию Skype для бизнеса Server из центра оценки Майкрософт по адресу: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server.'
ms.openlocfilehash: aa631e5b08ff8cbe9cb6db17009f286dcc975679
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41791717"
---
# <a name="verify-the-topology-in-skype-for-business-server"></a><span data-ttu-id="1bfc1-104">Проверка топологии в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="1bfc1-104">Verify the topology in Skype for Business Server</span></span>
 
<span data-ttu-id="1bfc1-105">**Сводка:** Сведения о том, как убедиться, что топология сервера Skype для бизнеса и серверы Active Directory работают должным образом.</span><span class="sxs-lookup"><span data-stu-id="1bfc1-105">**Summary:** Learn how to verify the Skype for Business Server topology and Active Directory servers are working as expected.</span></span> <span data-ttu-id="1bfc1-106">Загрузите бесплатную пробную версию Skype для бизнеса Server в [центре оценки Майкрософт](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span><span class="sxs-lookup"><span data-stu-id="1bfc1-106">Download a free trial of Skype for Business Server from the [Microsoft Evaluation center](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span></span>
  
<span data-ttu-id="1bfc1-107">После публикации топологии и компонентов серверных систем Skype для бизнеса на каждом из серверов в топологии вы можете убедиться, что топология работает должным образом.</span><span class="sxs-lookup"><span data-stu-id="1bfc1-107">After you have the topology published and the Skype for Business Server system components installed on each of the servers in the topology, you are ready to verify that the topology is working as expected.</span></span> <span data-ttu-id="1bfc1-108">Сюда входит проверка того, что конфигурация распространялась на все серверы службы каталогов Active Directory, чтобы весь домен знал о доступности Skype для бизнеса в домене.</span><span class="sxs-lookup"><span data-stu-id="1bfc1-108">This includes verifying that the configuration has propagated out to all of the Active Directory servers so that the entire domain knows Skype for Business is available in the domain.</span></span> <span data-ttu-id="1bfc1-109">Шаги с 1 по 5 могут выполняться в произвольном порядке.</span><span class="sxs-lookup"><span data-stu-id="1bfc1-109">You can do steps 1 through 5 in any order.</span></span> <span data-ttu-id="1bfc1-110">Но шаги 6, 7 и 8 должны выполняться в указанном порядке после шагов с 1 по 5, как показано на схеме.</span><span class="sxs-lookup"><span data-stu-id="1bfc1-110">However, you must do steps 6, 7, and 8 in order, and after steps 1 through 5, as outlined in the diagram.</span></span> <span data-ttu-id="1bfc1-111">Проверка топологии — это шаг 8 из 8.</span><span class="sxs-lookup"><span data-stu-id="1bfc1-111">Verifying the topology is step 8 of 8.</span></span>
  
![Обзорная схема.](../../media/c8698b53-1282-4978-a9a6-ca3f7a778f60.png)
  
## <a name="test-the-front-end-pool-deployment"></a><span data-ttu-id="1bfc1-113">Проверка развертывания пула переднего плана</span><span class="sxs-lookup"><span data-stu-id="1bfc1-113">Test the Front End pool deployment</span></span>

<span data-ttu-id="1bfc1-114">Последним шагом является проверка пула переднего плана и подтверждение того, что клиенты Skype для бизнеса могут взаимодействовать друг с другом.</span><span class="sxs-lookup"><span data-stu-id="1bfc1-114">The final step is to test the Front End pool and confirm that Skype for Business clients can communicate with each other.</span></span> 
  
### <a name="add-users-and-verify-client-connectivity"></a><span data-ttu-id="1bfc1-115">Добавление пользователей и проверка возможности подключения клиентов</span><span class="sxs-lookup"><span data-stu-id="1bfc1-115">Add users and verify client connectivity</span></span>

1. <span data-ttu-id="1bfc1-116">С помощью компьютеров и пользователей Active Directory вы можете добавить объект Users Active Directory роли администратора для развертывания Skype для бизнеса Server (на котором установлена панель управления "Skype для бизнеса Server") в группу **ксадминистратор** .</span><span class="sxs-lookup"><span data-stu-id="1bfc1-116">Use Active Directory Computers and Users to add the Active Directory user object of the administrator role for the Skype for Business Server deployment (on which Skype for Business Server Control Panel is installed) to the **CSAdministrator** group.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="1bfc1-117">Если вы не добавите соответствующих пользователей и группы в группу Ксадминисторс, вы получите сообщение об ошибке при попытке открыть панель управления "Skype для бизнеса" на сервере, которая читается, "доступ запрещен: из-за сбоя авторизации управления доступом на основе ролей (RBAC)". ."</span><span class="sxs-lookup"><span data-stu-id="1bfc1-117">If you do not add the appropriate users and groups to the CsAdministors group, you will receive an error when you open Skype for Business Server Control Panel which reads, "Unauthorized: Access is denied due to a role-based access control (RBAC) authorization failure."</span></span> 
  
2. <span data-ttu-id="1bfc1-118">Если объект-пользователь уже выполнил вход в систему, выйдите из системы, а затем повторите вход, чтобы зарегистрировать назначение новой группы.</span><span class="sxs-lookup"><span data-stu-id="1bfc1-118">If the user object is currently logged on, log off and then log on again to register the new group assignment.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="1bfc1-119">Учетная запись пользователя не может быть локальным администратором сервера, на котором работает Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="1bfc1-119">The user account cannot be the local administrator of any server running Skype for Business Server.</span></span> 
  
3. <span data-ttu-id="1bfc1-120">Войдите в систему с помощью учетной записи администратора, чтобы войти в систему на компьютере, на котором установлена панель управления "Skype для бизнеса Server".</span><span class="sxs-lookup"><span data-stu-id="1bfc1-120">Use the administrative account to log on to the computer where Skype for Business Server Control Panel is installed.</span></span>
    
4. <span data-ttu-id="1bfc1-121">Откройте панель управления Skype для бизнеса Server и укажите учетные данные при появлении соответствующего запроса.</span><span class="sxs-lookup"><span data-stu-id="1bfc1-121">Start Skype for Business Server Control Panel, and then provide credentials, if prompted.</span></span> <span data-ttu-id="1bfc1-122">На панели управления Skype для бизнеса Server выводятся сведения о развертывании.</span><span class="sxs-lookup"><span data-stu-id="1bfc1-122">Skype for Business Server Control Panel displays deployment information.</span></span>
    
5. <span data-ttu-id="1bfc1-123">На панели навигации слева выберите пункт **топология**и убедитесь, что состояние службы отображается на компьютере с зеленой стрелкой и рядом с каждой из ролей Skype для Business Server, которая была развернута и переведена в Интернет, отображается зеленая галочка для состояния репликации.</span><span class="sxs-lookup"><span data-stu-id="1bfc1-123">In the left navigation bar, click **Topology**, and then confirm that the service status shows a computer with a green arrow and that a green check mark for replication status is next to each Skype for Business Server role that has been deployed and brought online.</span></span> 
    
6. <span data-ttu-id="1bfc1-124">В левой панели навигации щелкните элемент **Пользователи**, а затем **Включить пользователей**.</span><span class="sxs-lookup"><span data-stu-id="1bfc1-124">In the left navigation bar, click **Users**, and then click **Enable users**.</span></span> 
    
7. <span data-ttu-id="1bfc1-125">На странице **Новый пользователь Skype для бизнеса Server** нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="1bfc1-125">On the **New Skype for Business Server User** page, click **Add**.</span></span>
    
8. <span data-ttu-id="1bfc1-p105">Чтобы определить параметры поиска для объектов, на странице **Выбор из Active Directory** можно щелкнуть меню **Поиск** и выбрать пункт **Добавить фильтр** (необязательно). Можно также выбрать команду **Поиск LDAP** и ввести выражение LDAP для фильтрации или ограничения числа возвращаемых объектов. Настроив все необходимые параметры поиска, нажмите кнопку **Найти**.</span><span class="sxs-lookup"><span data-stu-id="1bfc1-p105">To define search parameters for the objects you want to find, on the **Select from Active Directory** page, you can select **Search**, and then optionally click **Add Filter**. You can also select **LDAP search** and enter an LDAP expression to filter or limit the objects that will be returned. After you have decided on your Search options, click **Find**.</span></span>
    
9. <span data-ttu-id="1bfc1-129">В области результатов поиска выберите добавляемых пользователей и нажмите кнопку **OK**.</span><span class="sxs-lookup"><span data-stu-id="1bfc1-129">In the Search results pane, select the users you want to add, and then click **OK**.</span></span>
    
10. <span data-ttu-id="1bfc1-130">На **новой странице пользователя Skype для бизнеса Server** выбранные пользователи отображаются в списке **Пользователи** .</span><span class="sxs-lookup"><span data-stu-id="1bfc1-130">On the **New Skype for Business Server User** page, the users you selected are in the **Users** display.</span></span> <span data-ttu-id="1bfc1-131">In the **Assign users to a pool** list, select the server where the users should reside.</span><span class="sxs-lookup"><span data-stu-id="1bfc1-131">In the **Assign users to a pool** list, select the server where the users should reside.</span></span>
    
    <span data-ttu-id="1bfc1-132">Ниже приведен список параметров для настройки объектов.</span><span class="sxs-lookup"><span data-stu-id="1bfc1-132">The following is a list of options you can use to configure the objects.</span></span>
    
    - <span data-ttu-id="1bfc1-133">**Генерирование URI SIP пользователя**</span><span class="sxs-lookup"><span data-stu-id="1bfc1-133">**Generate user's SIP URI**</span></span>
    
    - <span data-ttu-id="1bfc1-134">**Телефония**</span><span class="sxs-lookup"><span data-stu-id="1bfc1-134">**Telephony**</span></span>
    
    - <span data-ttu-id="1bfc1-135">**Line URI (URI линии)**,</span><span class="sxs-lookup"><span data-stu-id="1bfc1-135">**Line URI**</span></span>
    
    - <span data-ttu-id="1bfc1-136">**Политика конференц-связи**,</span><span class="sxs-lookup"><span data-stu-id="1bfc1-136">**Conferencing policy**</span></span>
    
    - <span data-ttu-id="1bfc1-137">**Политика версий клиентов**,</span><span class="sxs-lookup"><span data-stu-id="1bfc1-137">**Client version policy**</span></span>
    
    - <span data-ttu-id="1bfc1-138">**Политика ПИН-кода**,</span><span class="sxs-lookup"><span data-stu-id="1bfc1-138">**PIN policy**</span></span>
    
    - <span data-ttu-id="1bfc1-139">**Политика внешнего доступа**,</span><span class="sxs-lookup"><span data-stu-id="1bfc1-139">**External access policy**</span></span>
    
    - <span data-ttu-id="1bfc1-140">**Политика архивации**,</span><span class="sxs-lookup"><span data-stu-id="1bfc1-140">**Archiving policy**</span></span>
    
    - <span data-ttu-id="1bfc1-141">**Политика расположения**,</span><span class="sxs-lookup"><span data-stu-id="1bfc1-141">**Location policy**</span></span>
    
    - <span data-ttu-id="1bfc1-142">**Политика клиента**.</span><span class="sxs-lookup"><span data-stu-id="1bfc1-142">**Client policy**</span></span>
    
    <span data-ttu-id="1bfc1-143">Чтобы проверить основные функциональные возможности, выберите предпочтительный параметр для **идентификатора URI SIP пользователя** (в других параметрах по умолчанию используются параметры), а затем нажмите кнопку **включить**, как показано на рисунке.</span><span class="sxs-lookup"><span data-stu-id="1bfc1-143">To test the basic functionality, select the option you prefer for the **Generate user's SIP URI** setting (the other options in the configuration use default settings), and then click **Enable**, as shown in the figure.</span></span>
    
     ![Включение пользователей на панели управления.](../../media/7ee8717d-9a1f-4864-8f45-71071c88878f.png)
  
11. <span data-ttu-id="1bfc1-p107">На экран будет выведена страница сводки, и в столбце **Включено** будет установлена галочка, указывающая на завершение настройки параметров пользователя. В столбце **SIP-адрес** будет отображаться адрес, который требуется для настройки входа пользователя.</span><span class="sxs-lookup"><span data-stu-id="1bfc1-p107">A summary page is displayed that shows a check mark in the **Enabled** column to indicate that the users are setup. The **SIP address** column displays the address you need for the user sign-in configuration.</span></span>
    
     ![Пользователи, добавленные на панель управления Skype для бизнеса Server.](../../media/8960548a-8d6d-44c5-bc01-6f9fb11b7588.png)
  
12. <span data-ttu-id="1bfc1-148">Выполните вход одного пользователя на компьютер, присоединенный к домену, а другого пользователя — на другой компьютер в домене.</span><span class="sxs-lookup"><span data-stu-id="1bfc1-148">Log one user on to a computer that is joined to the domain and another user on to another computer in the domain.</span></span>
    
13. <span data-ttu-id="1bfc1-149">Установите клиент Skype для бизнеса на каждом из двух клиентских компьютеров, а затем убедитесь, что оба пользователя могут входить в Skype для бизнеса Server и могут обмениваться мгновенными сообщениями.</span><span class="sxs-lookup"><span data-stu-id="1bfc1-149">Install Skype for Business client on each of the two client computers, and then verify that both users can sign in to Skype for Business Server and can send instant messages to each other.</span></span>
    

