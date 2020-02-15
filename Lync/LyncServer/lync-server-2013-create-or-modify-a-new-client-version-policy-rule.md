---
title: 'Lync Server 2013: создание или изменение нового правила политики версий клиентов'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a new client version policy rule
ms:assetid: 6f879d99-8401-41e0-a562-195c890d63ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ898478(v=OCS.15)
ms:contentKeyID: 50873758
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ae209caef3910ad08d09391cb13de4e1e0ceb7a2
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046002"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-new-client-version-policy-rule-in-lync-server-2013"></a><span data-ttu-id="57f09-102">Создание или изменение нового правила политики версий клиентов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="57f09-102">Create or modify a new client version policy rule in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="57f09-103">_**Последнее изменение темы:** 2013-01-21_</span><span class="sxs-lookup"><span data-stu-id="57f09-103">_**Topic Last Modified:** 2013-01-21_</span></span>

<span data-ttu-id="57f09-104">Правила политики версий клиентов определяют действия, которые должны выполняться при попытке пользователей войти в систему с определенными клиентами и версиями клиентов.</span><span class="sxs-lookup"><span data-stu-id="57f09-104">Client version policy rules define the actions that should be taken when users attempt to log on with specific clients and client versions.</span></span> <span data-ttu-id="57f09-105">Вы можете создавать или изменять индивидуальные правила для политики версий клиентов с помощью панели управления Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="57f09-105">You can create or modify individual rules for a client version policy from Lync Server 2013 Control Panel.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="57f09-106">Правила перечислены в порядке приоритета.</span><span class="sxs-lookup"><span data-stu-id="57f09-106">Rules are listed in order of precedence.</span></span> <span data-ttu-id="57f09-107">Например, если у вас есть правило, которое разрешает клиентам с версией 1,5 подключаться, за которым следует правило, блокирующее клиенты с версией, предшествующей 2,0, первое правило имеет приоритет, а клиенты с версией 1,5 могут подключаться.</span><span class="sxs-lookup"><span data-stu-id="57f09-107">For example, if you have a rule that allows clients running version 1.5 to connect, followed by a rule that blocks clients running a version earlier than 2.0, the first rule takes precedence, and clients running version 1.5 are allowed to connect.</span></span>



</div>

<div>

## <a name="to-create-or-modify-client-version-policy-rules-with-lync-server-control-panel"></a><span data-ttu-id="57f09-108">Создание или изменение правил политики версий клиентов с помощью панели управления Lync Server</span><span class="sxs-lookup"><span data-stu-id="57f09-108">To create or modify client version policy rules with Lync Server Control Panel</span></span>

1.  <span data-ttu-id="57f09-109">[Создание или изменение новой политики версий клиентов в Lync server 2013](lync-server-2013-create-or-modify-a-new-client-version-policy.md) с помощью панели управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="57f09-109">[Create or modify a new client version policy in Lync Server 2013](lync-server-2013-create-or-modify-a-new-client-version-policy.md) with Lync Server Control Panel.</span></span>

2.  <span data-ttu-id="57f09-110">На странице " **изменение политики версий клиентов** " выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="57f09-110">On the **Edit Client Version Policy** page, do one of the following:</span></span>
    
      - <span data-ttu-id="57f09-111">Нажмите кнопку **Создать**, чтобы создать новое правило версий клиентов.</span><span class="sxs-lookup"><span data-stu-id="57f09-111">Click **New** to create a new client version rule.</span></span>
    
      - <span data-ttu-id="57f09-112">Выберите один из заданных типов клиентов в списке, а затем щелкните **Показать подробности...**.</span><span class="sxs-lookup"><span data-stu-id="57f09-112">Click one of the defined client types in the list, and then click **Show details**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="57f09-113">Чтобы указать тип клиента, можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="57f09-113">You can use wildcards to indicate the client type.</span></span>

    
    </div>

3.  <span data-ttu-id="57f09-114">В поле **Агент пользователя** выберите тип клиента.</span><span class="sxs-lookup"><span data-stu-id="57f09-114">In **User agent**, select a client type.</span></span>

4.  <span data-ttu-id="57f09-115">В области **Номер версии** выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="57f09-115">Under **Version number**, do the following:</span></span>
    
      - <span data-ttu-id="57f09-116">В поле **Основной номер версии** введите число, соответствующее основной версии клиента.</span><span class="sxs-lookup"><span data-stu-id="57f09-116">In **Major version**, type the number that corresponds to the major release of the client.</span></span>
    
      - <span data-ttu-id="57f09-117">В поле **Дополнительный номер версии** введите число, соответствующее вспомогательной версии клиента.</span><span class="sxs-lookup"><span data-stu-id="57f09-117">In **Minor version**, type the number that corresponds to the minor release of the client.</span></span>
    
      - <span data-ttu-id="57f09-118">В поле **Построение** введите число, которое соответствует основной и дополнительной версии клиента.</span><span class="sxs-lookup"><span data-stu-id="57f09-118">In **Build**, type the number that corresponds to the major and minor release of the client.</span></span>
    
      - <span data-ttu-id="57f09-119">В поле **Обновление** введите число, соответствующее обновленной версии клиента.</span><span class="sxs-lookup"><span data-stu-id="57f09-119">In **Update**, type the number that corresponds to the updated release of the client.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="57f09-120">Чтобы указать версию клиента, можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="57f09-120">You can use wildcards to indicate the client version number.</span></span>

    
    </div>

5.  <span data-ttu-id="57f09-121">Чтобы указать операцию сопоставления для версии клиента, указанной в предыдущих действиях, в поле **Операция сравнения** выберите один из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="57f09-121">To specify the matching operation for the client version you specified in the preceding steps, in **Comparison operation**, click one of the following:</span></span>
    
      - <span data-ttu-id="57f09-122">**Равняется**,</span><span class="sxs-lookup"><span data-stu-id="57f09-122">**Same as**</span></span>
    
      - <span data-ttu-id="57f09-123">**Не является**</span><span class="sxs-lookup"><span data-stu-id="57f09-123">**Is not**</span></span>
    
      - <span data-ttu-id="57f09-124">**Новее**</span><span class="sxs-lookup"><span data-stu-id="57f09-124">**Newer than**</span></span>
    
      - <span data-ttu-id="57f09-125">**Новее или совпадает с**</span><span class="sxs-lookup"><span data-stu-id="57f09-125">**Newer than or same as**</span></span>
    
      - <span data-ttu-id="57f09-126">**Старее**</span><span class="sxs-lookup"><span data-stu-id="57f09-126">**Older than**</span></span>
    
      - <span data-ttu-id="57f09-127">**Не новее чем**.</span><span class="sxs-lookup"><span data-stu-id="57f09-127">**Older than or same as**</span></span>

6.  <span data-ttu-id="57f09-128">Чтобы указать действие, которое будет выполняться при удовлетворении условий предыдущего действия, в области **Действия** выберите один из вариантов.</span><span class="sxs-lookup"><span data-stu-id="57f09-128">To specify the action to perform when the criteria in the preceding steps are met, click one of the following in **Action**:</span></span>
    
      - <span data-ttu-id="57f09-129">Чтобы разрешить клиенту вход в систему, выберите вариант **Разрешить**.</span><span class="sxs-lookup"><span data-stu-id="57f09-129">To allow the client to log on, click **Allow**.</span></span>
    
      - <span data-ttu-id="57f09-p103">Чтобы разрешить клиенту вход в систему и получение обновлений из Центра обновления Windows Server Update Service или Центра обновления Майкрософт, выберите **Разрешить и обновить**. Это действие доступно, только если выбрано приложение **OC** агента пользователя.</span><span class="sxs-lookup"><span data-stu-id="57f09-p103">To allow the client to log on and receive updates from Windows Server Update Service or Microsoft Update, click **Allow and Upgrade**. This action is available only when user agent **OC** is selected.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="57f09-132">При выборе этого действия в следующий раз при входе пользователей в Lync 2013 появится уведомление.</span><span class="sxs-lookup"><span data-stu-id="57f09-132">Selecting this action causes a notification to appear the next time users sign in to Lync 2013.</span></span> <span data-ttu-id="57f09-133">Уведомление указывает на то, что обновление доступно, даже если они еще не были выпущены в службе обновлений Windows Server или центра обновления Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="57f09-133">The notification states that an update is available, even if updates have not yet been released to Windows Server Update Service or Microsoft Update.</span></span> <span data-ttu-id="57f09-134">Чтобы избежать путаницы, необходимо выбрать это действие только после появления обновлений.</span><span class="sxs-lookup"><span data-stu-id="57f09-134">To avoid confusion, you should choose this action only after updates become available.</span></span>

        
        </div>
    
      - <span data-ttu-id="57f09-p105">Чтобы разрешить клиенту выполнять вход в систему и выводить на экран сообщение о расположении для загрузки новой версии клиента, выберите вариант **Разрешить с URL-адресом**. URL-адрес указывается позднее в этой процедуре.</span><span class="sxs-lookup"><span data-stu-id="57f09-p105">To allow the client to log on and display a message about where to download another client version, click **Allow with URL**. You specify the URL later in this procedure.</span></span>
    
      - <span data-ttu-id="57f09-137">Чтобы запретить клиенту вход в систему, выберите вариант **Блокировать**.</span><span class="sxs-lookup"><span data-stu-id="57f09-137">To prevent the client from logging on, click **Block**.</span></span>
    
      - <span data-ttu-id="57f09-p106">Чтобы запретить клиенту вход в систему и разрешить получение обновлений из службы Windows Server Update Service или Центра обновления Майкрософт, выберите вариант **Блокировать и обновлять**. Это действие доступно, только если выбрано приложение **OC** агента пользователя.</span><span class="sxs-lookup"><span data-stu-id="57f09-p106">To prevent the client from logging on and allow the client to receive updates from Windows Server Update Service or Microsoft Update, click **Block and Upgrade**. This action is available only when user agent **OC** is selected.</span></span>
    
      - <span data-ttu-id="57f09-p107">Чтобы запретить клиенту выполнять вход в систему и выводить на экран сообщение о расположении для загрузки новой версии клиента, выберите вариант **Блокировать с URL-адресом**. URL-адрес указывается позднее в этой процедуре.</span><span class="sxs-lookup"><span data-stu-id="57f09-p107">To prevent the client from logging on and display a message about where to download another client version, click **Block with URL**. You specify the URL later in this procedure.</span></span>

7.  <span data-ttu-id="57f09-142">(Дополнительно). Если выбран вариант **Разрешить с URL-адресом** или **Блокировать с URL-адресом** в предыдущем действии, в поле **URL-адрес** введите URL-адрес для загрузки клиента, чтобы включить его в сообщение.</span><span class="sxs-lookup"><span data-stu-id="57f09-142">(Optional) If you clicked **Allow with URL** or **Block with URL** in the previous step, type the client download URL to include in the message in **URL**.</span></span>

8.  <span data-ttu-id="57f09-143">Нажмите кнопку **ОК**, а затем **Фиксировать**.</span><span class="sxs-lookup"><span data-stu-id="57f09-143">Click **OK**, and then click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

