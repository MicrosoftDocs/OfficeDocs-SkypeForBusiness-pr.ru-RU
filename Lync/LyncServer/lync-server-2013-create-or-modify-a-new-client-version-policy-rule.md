---
title: 'Lync Server 2013: создание или изменение нового правила политики для версии клиента'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify a new client version policy rule
ms:assetid: 6f879d99-8401-41e0-a562-195c890d63ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ898478(v=OCS.15)
ms:contentKeyID: 50873758
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aa5f9074f928a9bec20ca275487806b790a0226b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834785"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-new-client-version-policy-rule-in-lync-server-2013"></a><span data-ttu-id="4dde4-102">Создание или изменение правила политики для новой версии клиента в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4dde4-102">Create or modify a new client version policy rule in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4dde4-103">_**Тема последнего изменения:** 2013-01-21_</span><span class="sxs-lookup"><span data-stu-id="4dde4-103">_**Topic Last Modified:** 2013-01-21_</span></span>

<span data-ttu-id="4dde4-104">Правила политики клиентской версии определяют действия, которые должны выполняться при попытке входа пользователя в систему с определенными клиентами и клиентскими версиями.</span><span class="sxs-lookup"><span data-stu-id="4dde4-104">Client version policy rules define the actions that should be taken when users attempt to log on with specific clients and client versions.</span></span> <span data-ttu-id="4dde4-105">Вы можете создавать и изменять индивидуальные правила для политики версии клиента с помощью панели управления Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4dde4-105">You can create or modify individual rules for a client version policy from Lync Server 2013 Control Panel.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="4dde4-106">Правила перечислены в порядке приоритета.</span><span class="sxs-lookup"><span data-stu-id="4dde4-106">Rules are listed in order of precedence.</span></span> <span data-ttu-id="4dde4-107">Например, если у вас есть правило, разрешающее клиентам с установленной версией 1,5, а затем правило, которое блокирует работу клиентов, использующих более раннюю версию, чем 2,0, правило имеет приоритет, а клиенты с версией 1,5 могут подключаться.</span><span class="sxs-lookup"><span data-stu-id="4dde4-107">For example, if you have a rule that allows clients running version 1.5 to connect, followed by a rule that blocks clients running a version earlier than 2.0, the first rule takes precedence, and clients running version 1.5 are allowed to connect.</span></span>



</div>

<div>

## <a name="to-create-or-modify-client-version-policy-rules-with-lync-server-control-panel"></a><span data-ttu-id="4dde4-108">Создание или изменение правил политики версий клиента с помощью панели управления Lync Server</span><span class="sxs-lookup"><span data-stu-id="4dde4-108">To create or modify client version policy rules with Lync Server Control Panel</span></span>

1.  <span data-ttu-id="4dde4-109">[Создавайте и изменяйте новую политику версии клиента в Lync server 2013](lync-server-2013-create-or-modify-a-new-client-version-policy.md) с помощью панели управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4dde4-109">[Create or modify a new client version policy in Lync Server 2013](lync-server-2013-create-or-modify-a-new-client-version-policy.md) with Lync Server Control Panel.</span></span>

2.  <span data-ttu-id="4dde4-110">На странице **изменение политики версии клиента** выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="4dde4-110">On the **Edit Client Version Policy** page, do one of the following:</span></span>
    
      - <span data-ttu-id="4dde4-111">Нажмите кнопку **создать** , чтобы создать новое правило для версии клиента.</span><span class="sxs-lookup"><span data-stu-id="4dde4-111">Click **New** to create a new client version rule.</span></span>
    
      - <span data-ttu-id="4dde4-112">Выберите в списке один из определенных типов клиентов и нажмите кнопку **Показать подробности**.</span><span class="sxs-lookup"><span data-stu-id="4dde4-112">Click one of the defined client types in the list, and then click **Show details**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="4dde4-113">Вы можете использовать подстановочные знаки, чтобы указать тип клиента.</span><span class="sxs-lookup"><span data-stu-id="4dde4-113">You can use wildcards to indicate the client type.</span></span>

    
    </div>

3.  <span data-ttu-id="4dde4-114">В **агенте пользователя**выберите тип клиента.</span><span class="sxs-lookup"><span data-stu-id="4dde4-114">In **User agent**, select a client type.</span></span>

4.  <span data-ttu-id="4dde4-115">В разделе **номер версии**выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="4dde4-115">Under **Version number**, do the following:</span></span>
    
      - <span data-ttu-id="4dde4-116">В поле **основная версия**введите номер, соответствующий главному выпуску клиента.</span><span class="sxs-lookup"><span data-stu-id="4dde4-116">In **Major version**, type the number that corresponds to the major release of the client.</span></span>
    
      - <span data-ttu-id="4dde4-117">В поле **Дополнительная версия**введите номер, соответствующий вспомогательному выпуску клиента.</span><span class="sxs-lookup"><span data-stu-id="4dde4-117">In **Minor version**, type the number that corresponds to the minor release of the client.</span></span>
    
      - <span data-ttu-id="4dde4-118">В поле **Сборка**введите номер, соответствующий основной и вспомогательной выпуску клиента.</span><span class="sxs-lookup"><span data-stu-id="4dde4-118">In **Build**, type the number that corresponds to the major and minor release of the client.</span></span>
    
      - <span data-ttu-id="4dde4-119">В поле **Обновление**введите номер, соответствующий обновленному выпуску клиента.</span><span class="sxs-lookup"><span data-stu-id="4dde4-119">In **Update**, type the number that corresponds to the updated release of the client.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="4dde4-120">Вы можете использовать подстановочные знаки, чтобы указать номер версии клиента.</span><span class="sxs-lookup"><span data-stu-id="4dde4-120">You can use wildcards to indicate the client version number.</span></span>

    
    </div>

5.  <span data-ttu-id="4dde4-121">Чтобы указать операцию сопоставления для версии клиента, указанной на предыдущих шагах, в **операции сравнения**выберите один из указанных ниже вариантов.</span><span class="sxs-lookup"><span data-stu-id="4dde4-121">To specify the matching operation for the client version you specified in the preceding steps, in **Comparison operation**, click one of the following:</span></span>
    
      - <span data-ttu-id="4dde4-122">**Cовпадает с**</span><span class="sxs-lookup"><span data-stu-id="4dde4-122">**Same as**</span></span>
    
      - <span data-ttu-id="4dde4-123">**Не является**</span><span class="sxs-lookup"><span data-stu-id="4dde4-123">**Is not**</span></span>
    
      - <span data-ttu-id="4dde4-124">**Новее**</span><span class="sxs-lookup"><span data-stu-id="4dde4-124">**Newer than**</span></span>
    
      - <span data-ttu-id="4dde4-125">**Новее или совпадает с**</span><span class="sxs-lookup"><span data-stu-id="4dde4-125">**Newer than or same as**</span></span>
    
      - <span data-ttu-id="4dde4-126">**Старше**</span><span class="sxs-lookup"><span data-stu-id="4dde4-126">**Older than**</span></span>
    
      - <span data-ttu-id="4dde4-127">**Старше или совпадает с**</span><span class="sxs-lookup"><span data-stu-id="4dde4-127">**Older than or same as**</span></span>

6.  <span data-ttu-id="4dde4-128">Чтобы указать действие, которое будет выполняться при выполнении условий, описанных в предыдущих шагах, выберите один из указанных ниже **действий**.</span><span class="sxs-lookup"><span data-stu-id="4dde4-128">To specify the action to perform when the criteria in the preceding steps are met, click one of the following in **Action**:</span></span>
    
      - <span data-ttu-id="4dde4-129">Чтобы разрешить клиенту вход, нажмите кнопку **Разрешить**.</span><span class="sxs-lookup"><span data-stu-id="4dde4-129">To allow the client to log on, click **Allow**.</span></span>
    
      - <span data-ttu-id="4dde4-130">Чтобы разрешить клиенту входить и получать обновления из службы обновления Windows Server Update Service или центра обновления Майкрософт, нажмите кнопку **Разрешить и обновить**.</span><span class="sxs-lookup"><span data-stu-id="4dde4-130">To allow the client to log on and receive updates from Windows Server Update Service or Microsoft Update, click **Allow and Upgrade**.</span></span> <span data-ttu-id="4dde4-131">Это действие доступно только в том случае, если выбран агент пользователя **OC** .</span><span class="sxs-lookup"><span data-stu-id="4dde4-131">This action is available only when user agent **OC** is selected.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="4dde4-132">При выборе этого действия уведомление появляется при следующем входе в Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="4dde4-132">Selecting this action causes a notification to appear the next time users sign in to Lync 2013.</span></span> <span data-ttu-id="4dde4-133">В уведомлении говорится, что обновление доступно, даже если они еще не были выпущены в службе обновления Windows Server или Microsoft Update.</span><span class="sxs-lookup"><span data-stu-id="4dde4-133">The notification states that an update is available, even if updates have not yet been released to Windows Server Update Service or Microsoft Update.</span></span> <span data-ttu-id="4dde4-134">Чтобы избежать путаницы, выбирайте это действие только после того, как обновления станут доступны.</span><span class="sxs-lookup"><span data-stu-id="4dde4-134">To avoid confusion, you should choose this action only after updates become available.</span></span>

        
        </div>
    
      - <span data-ttu-id="4dde4-135">Чтобы разрешить клиенту вход в систему и отобразить сообщение о том, где нужно скачать другую версию клиента, выберите **Разрешить с URL-адресом**.</span><span class="sxs-lookup"><span data-stu-id="4dde4-135">To allow the client to log on and display a message about where to download another client version, click **Allow with URL**.</span></span> <span data-ttu-id="4dde4-136">Вы задаете URL-адрес позже в этой процедуре.</span><span class="sxs-lookup"><span data-stu-id="4dde4-136">You specify the URL later in this procedure.</span></span>
    
      - <span data-ttu-id="4dde4-137">Чтобы запретить клиенту входить в систему, нажмите кнопку **блокировать**.</span><span class="sxs-lookup"><span data-stu-id="4dde4-137">To prevent the client from logging on, click **Block**.</span></span>
    
      - <span data-ttu-id="4dde4-138">Чтобы запретить клиенту входить в систему и разрешить клиенту получать обновления из службы Windows Server Update Service или центра обновления Майкрософт, нажмите кнопку **заблокировать и обновить**.</span><span class="sxs-lookup"><span data-stu-id="4dde4-138">To prevent the client from logging on and allow the client to receive updates from Windows Server Update Service or Microsoft Update, click **Block and Upgrade**.</span></span> <span data-ttu-id="4dde4-139">Это действие доступно только в том случае, если выбран агент пользователя **OC** .</span><span class="sxs-lookup"><span data-stu-id="4dde4-139">This action is available only when user agent **OC** is selected.</span></span>
    
      - <span data-ttu-id="4dde4-140">Чтобы запретить клиенту входить в систему и отобразить сообщение о том, куда можно скачать другую версию клиента, нажмите кнопку **блокировать с URL-адресом**.</span><span class="sxs-lookup"><span data-stu-id="4dde4-140">To prevent the client from logging on and display a message about where to download another client version, click **Block with URL**.</span></span> <span data-ttu-id="4dde4-141">Вы задаете URL-адрес позже в этой процедуре.</span><span class="sxs-lookup"><span data-stu-id="4dde4-141">You specify the URL later in this procedure.</span></span>

7.  <span data-ttu-id="4dde4-142">Необязательно Если вы щелкните **Разрешить с URL-** адресом или **блоком с URL-адресом** на предыдущем шаге, введите URL-адрес скачивания клиента для включения в сообщение **URL**-адрес.</span><span class="sxs-lookup"><span data-stu-id="4dde4-142">(Optional) If you clicked **Allow with URL** or **Block with URL** in the previous step, type the client download URL to include in the message in **URL**.</span></span>

8.  <span data-ttu-id="4dde4-143">Нажмите кнопку **ОК**, а затем — **Commit (сохранить**).</span><span class="sxs-lookup"><span data-stu-id="4dde4-143">Click **OK**, and then click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

