---
title: 'Lync Server 2013: Настройка среды для веб-портала администрирования системы комнат Lync'
description: 'Lync Server 2013: Настройка среды для веб-портала администрирования системы комнат Lync.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring your environment for the Lync Room System Administrative Web Portal
ms:assetid: 1bf3cc55-cfa8-46ee-a8bc-6dab3bff76b2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn436325(v=OCS.15)
ms:contentKeyID: 56737623
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c942e1db799a7336a3eafb5571e82584694ddbf3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542205"
---
# <a name="configuring-your-lync-server-2013-environment-for-the-lync-room-system-administrative-web-portal"></a><span data-ttu-id="96dc3-103">Настройка среды Lync Server 2013 для веб-портала администрирования системы комнат Lync</span><span class="sxs-lookup"><span data-stu-id="96dc3-103">Configuring your Lync Server 2013 environment for the Lync Room System Administrative Web Portal</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="96dc3-104">_**Последнее изменение темы:** 2014-05-22_</span><span class="sxs-lookup"><span data-stu-id="96dc3-104">_**Topic Last Modified:** 2014-05-22_</span></span>

<span data-ttu-id="96dc3-105">Для использования веб-портала администрирования системы комнат Lync (LRS) необходимо установить или настроить следующие предварительные требования.</span><span class="sxs-lookup"><span data-stu-id="96dc3-105">To use the Lync Room System (LRS) Administrative Web Portal, you will need to install or configure the following prerequisites.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="96dc3-106">Если на сервере настроена проверка подлинности Kerberos и NTLM, а LRS запущен на компьютере, который не присоединен к домену, проверка подлинности Kerberos не будет выполнена, а пользователь не увидит состояние LRS на административном портале.</span><span class="sxs-lookup"><span data-stu-id="96dc3-106">If the server is configured with both Kerberos and NTLM authentication, and LRS is running on a computer that is not joined to the domain, Kerberos authentication will fail and the user will not see the status of LRS in the administrative portal.</span></span> <span data-ttu-id="96dc3-107">Чтобы устранить эту проблему, настройте сервер с проверкой подлинности NTLM или проверкой подлинности NTLM и TLS-ДСК (без Kerberos) или Присоедините компьютер LRS к домену.</span><span class="sxs-lookup"><span data-stu-id="96dc3-107">To resolve this issue, configure the server with NTLM authentication or both NTLM and TLS-DSK authentication (without Kerberos), or join the LRS computer to the domain.</span></span>



</div>

1.  <span data-ttu-id="96dc3-108">Установка накопительных обновлений для Lync Server 2013:2013 июля в топологии Lync Server.</span><span class="sxs-lookup"><span data-stu-id="96dc3-108">Install Lync Server 2013 Cumulative Updates: July 2013 in the Lync Server topology.</span></span>
    
    <span data-ttu-id="96dc3-109">Чтобы получить обновление или просмотреть сведения о том, что входит в состав этого приложения, ознакомьтесь со статьей [Updates for Lync Server 2013](https://go.microsoft.com/fwlink/p/?linkid=323959).</span><span class="sxs-lookup"><span data-stu-id="96dc3-109">To get the update or see what’s included with it, see [Updates for Lync Server 2013](https://go.microsoft.com/fwlink/p/?linkid=323959).</span></span>

2.  <span data-ttu-id="96dc3-110">Создайте пользователя Active Directory с включенной поддержкой SIP.</span><span class="sxs-lookup"><span data-stu-id="96dc3-110">Create a SIP-enabled Active Directory user.</span></span>
    
    <span data-ttu-id="96dc3-111">Веб-портал администрирования LRS использует эти учетные данные для запроса информации из Lync Server.</span><span class="sxs-lookup"><span data-stu-id="96dc3-111">The LRS Administrative Web Portal uses these credentials to query information from Lync Server.</span></span> <span data-ttu-id="96dc3-112">Рекомендуемое имя пользователя — Lrsapp включена поддержка.</span><span class="sxs-lookup"><span data-stu-id="96dc3-112">The recommended username is LRSApp.</span></span>

3.  <span data-ttu-id="96dc3-113">Создайте группу безопасности Active Directory с именем LRSSupportAdminGroup.</span><span class="sxs-lookup"><span data-stu-id="96dc3-113">Create an Active Directory security group with name LRSSupportAdminGroup.</span></span>
    
    <span data-ttu-id="96dc3-114">Создайте группу с областью действия групп в качестве глобальной и типа группы как безопасность.</span><span class="sxs-lookup"><span data-stu-id="96dc3-114">Create the group with Group Scope as Global and Group Type as Security.</span></span> <span data-ttu-id="96dc3-115">Пользователи с включенной поддержкой SIP, добавленные в эту группу, будут авторизованы для просмотра списка помещений и выполнения определенных команд, например сбора журналов.</span><span class="sxs-lookup"><span data-stu-id="96dc3-115">SIP enabled users who are added to this group will be authorized to see the list of rooms and execute certain commands, such as collecting logs.</span></span>

4.  <span data-ttu-id="96dc3-116">Создайте группу безопасности Active Directory с именем LRSFullAccessAdminGroup.</span><span class="sxs-lookup"><span data-stu-id="96dc3-116">Create an Active Directory security group with name LRSFullAccessAdminGroup.</span></span>
    
    <span data-ttu-id="96dc3-117">Создайте группу с областью действия групп в качестве глобальной и типа группы в качестве Security. пользователи с включенной поддержкой SIP, добавленные в эту группу, имеют право на использование всех функций портала администрирования.</span><span class="sxs-lookup"><span data-stu-id="96dc3-117">Create the group with Group Scope as Global and Group Type as Security.SIP enabled users who are added to this group are authorized to use all admin portal functionality.</span></span>
    
     
    
    <span data-ttu-id="96dc3-118">![Список групп администраторов с ролью группы безопасности](images/Dn436325.5d432819-a2e2-452c-bc2a-5d4ee79d8c33(OCS.15).png "Список групп администраторов с ролью группы безопасности")</span><span class="sxs-lookup"><span data-stu-id="96dc3-118">![List of Admin Groups with security group role](images/Dn436325.5d432819-a2e2-452c-bc2a-5d4ee79d8c33(OCS.15).png "List of Admin Groups with security group role")</span></span>  
    
     

5.  <span data-ttu-id="96dc3-119">Добавьте LRSFullAccessAdminGroup в качестве члена LRSSupportAdminGroup.</span><span class="sxs-lookup"><span data-stu-id="96dc3-119">Add LRSFullAccessAdminGroup as a member of LRSSupportAdminGroup.</span></span>
    
    <span data-ttu-id="96dc3-120">![Страница "элементы свойств LRSSupportAdminGroup"](images/Dn436325.91a4a28a-cacf-4ef6-aac1-915ec41c9648(OCS.15).png "Страница "элементы свойств LRSSupportAdminGroup"")</span><span class="sxs-lookup"><span data-stu-id="96dc3-120">![LRSSupportAdminGroup Properties Members page](images/Dn436325.91a4a28a-cacf-4ef6-aac1-915ec41c9648(OCS.15).png "LRSSupportAdminGroup Properties Members page")</span></span>  
    
     

6.  <span data-ttu-id="96dc3-121">Создайте пользователя с включенной поддержкой SIP Active Directory с именем LRSSupport.</span><span class="sxs-lookup"><span data-stu-id="96dc3-121">Create a SIP enabled Active Directory user with name LRSSupport.</span></span> <span data-ttu-id="96dc3-122">Добавьте этого пользователя в LRSSupportAdminGroup.</span><span class="sxs-lookup"><span data-stu-id="96dc3-122">Add this user to LRSSupportAdminGroup.</span></span>
    
    <span data-ttu-id="96dc3-123">![Страница "элементы свойств LRSSupportAdminGroup"](images/Dn436325.7638055d-22ac-4909-914d-1966f5623909(OCS.15).png "Страница "элементы свойств LRSSupportAdminGroup"")</span><span class="sxs-lookup"><span data-stu-id="96dc3-123">![LRSSupportAdminGroup Properties Members page](images/Dn436325.7638055d-22ac-4909-914d-1966f5623909(OCS.15).png "LRSSupportAdminGroup Properties Members page")</span></span>  
    
     

7.  <span data-ttu-id="96dc3-124">Установите ASP.NET MVC 4 для Visual Studio 2010 с пакетом обновления 1 (SP1) и Visual Web Developer 2010 SP1, который доступен в центре загрузки Майкрософт по адресу [https://go.microsoft.com/fwlink/p/?LinkId=323967](https://go.microsoft.com/fwlink/p/?linkid=323967) .</span><span class="sxs-lookup"><span data-stu-id="96dc3-124">Install ASP.NET MVC 4 for Visual Studio 2010 SP1 and Visual Web Developer 2010 SP1, available in the Microsoft Download Center at [https://go.microsoft.com/fwlink/p/?LinkId=323967](https://go.microsoft.com/fwlink/p/?linkid=323967).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

