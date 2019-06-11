---
title: 'Lync Server 2013: настройка среды для работы с веб-порталом администрирования системы комнат Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring your environment for the Lync Room System Administrative Web Portal
ms:assetid: 1bf3cc55-cfa8-46ee-a8bc-6dab3bff76b2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn436325(v=OCS.15)
ms:contentKeyID: 56737623
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0ef7596e65c44f871da8c26a0526a389dde72a45
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841143"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-your-lync-server-2013-environment-for-the-lync-room-system-administrative-web-portal"></a><span data-ttu-id="82468-102">Configuring your Lync Server 2013 environment for the Lync Room System Administrative Web Portal</span><span class="sxs-lookup"><span data-stu-id="82468-102">Configuring your Lync Server 2013 environment for the Lync Room System Administrative Web Portal</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="82468-103">_**Тема последнего изменения:** 2014-05-22_</span><span class="sxs-lookup"><span data-stu-id="82468-103">_**Topic Last Modified:** 2014-05-22_</span></span>

<span data-ttu-id="82468-104">Чтобы использовать веб-портал для управления комнатой на Lync (ЛРС), необходимо установить или настроить следующие необходимые компоненты.</span><span class="sxs-lookup"><span data-stu-id="82468-104">To use the Lync Room System (LRS) Administrative Web Portal, you will need to install or configure the following prerequisites.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="82468-105">Если сервер настроен на проверку подлинности Kerberos и NTLM и ЛРС запущен на компьютере, который не подключен к домену, проверка подлинности Kerberos не будет выполнена, и пользователь не увидит состояние ЛРС на административном портале.</span><span class="sxs-lookup"><span data-stu-id="82468-105">If the server is configured with both Kerberos and NTLM authentication, and LRS is running on a computer that is not joined to the domain, Kerberos authentication will fail and the user will not see the status of LRS in the administrative portal.</span></span> <span data-ttu-id="82468-106">Чтобы устранить эту проблему, настройте сервер для проверки подлинности NTLM либо проверки подлинности NTLM и TLS-ДСК (без Kerberos) либо Присоедините компьютер ЛРС к домену.</span><span class="sxs-lookup"><span data-stu-id="82468-106">To resolve this issue, configure the server with NTLM authentication or both NTLM and TLS-DSK authentication (without Kerberos), or join the LRS computer to the domain.</span></span>



</div>

1.  <span data-ttu-id="82468-107">Установка накопительных обновлений для Lync Server 2013: Июль 2013 в топологии Lync Server.</span><span class="sxs-lookup"><span data-stu-id="82468-107">Install Lync Server 2013 Cumulative Updates: July 2013 in the Lync Server topology.</span></span>
    
    <span data-ttu-id="82468-108">Чтобы получить обновление или просмотреть сведения о том, что входит в состав этого приложения, ознакомьтесь со статьей [Обновление для Lync Server 2013](http://go.microsoft.com/fwlink/p/?linkid=323959).</span><span class="sxs-lookup"><span data-stu-id="82468-108">To get the update or see what’s included with it, see [Updates for Lync Server 2013](http://go.microsoft.com/fwlink/p/?linkid=323959).</span></span>

2.  <span data-ttu-id="82468-109">Создайте учетную запись пользователя Active Directory с включенной поддержкой SIP.</span><span class="sxs-lookup"><span data-stu-id="82468-109">Create a SIP-enabled Active Directory user.</span></span>
    
    <span data-ttu-id="82468-110">На веб-портале ЛРС администрирования эти учетные данные используются для запроса данных с сервера Lync Server.</span><span class="sxs-lookup"><span data-stu-id="82468-110">The LRS Administrative Web Portal uses these credentials to query information from Lync Server.</span></span> <span data-ttu-id="82468-111">Рекомендуемое имя пользователя — Лрсапп.</span><span class="sxs-lookup"><span data-stu-id="82468-111">The recommended username is LRSApp.</span></span>

3.  <span data-ttu-id="82468-112">Создайте группу безопасности Active Directory с именем LRSSupportAdminGroup.</span><span class="sxs-lookup"><span data-stu-id="82468-112">Create an Active Directory security group with name LRSSupportAdminGroup.</span></span>
    
    <span data-ttu-id="82468-p103">Создайте группу с глобальной областью действия и типом "Безопасность". Пользователи с включенной поддержкой SIP, добавляемые в эту группу, будут автоматически получать разрешения на просмотр списка комнат и выполнение определенных команд, таких как ведение журналов.</span><span class="sxs-lookup"><span data-stu-id="82468-p103">Create the group with Group Scope as Global and Group Type as Security. SIP enabled users who are added to this group will be authorized to see the list of rooms and execute certain commands, such as collecting logs.</span></span>

4.  <span data-ttu-id="82468-115">Создайте группу безопасности Active Directory с именем LRSFullAccessAdminGroup. </span><span class="sxs-lookup"><span data-stu-id="82468-115">Create an Active Directory security group with name LRSFullAccessAdminGroup.</span></span>
    
    <span data-ttu-id="82468-116">Создание группы с областью группировки в качестве глобальных и группового типа как "безопасность". Пользователи, добавленные в эту группу, имеют разрешение на использование всех функций портала администрирования.</span><span class="sxs-lookup"><span data-stu-id="82468-116">Create the group with Group Scope as Global and Group Type as Security.SIP enabled users who are added to this group are authorized to use all admin portal functionality.</span></span>
    
     
    
    <span data-ttu-id="82468-117">![Список групп администраторов с ролью "Группа безопасности"] (images/Dn436325.5d432819-a2e2-452c-bc2a-5d4ee79d8c33(OCS.15).png "Список групп администраторов с ролью \"Группа безопасности\"")</span><span class="sxs-lookup"><span data-stu-id="82468-117">![List of Admin Groups with security group role](images/Dn436325.5d432819-a2e2-452c-bc2a-5d4ee79d8c33(OCS.15).png "List of Admin Groups with security group role")</span></span>  
    
     

5.  <span data-ttu-id="82468-118">Добавьте Лрсфуллакцессадминграуп в качестве участника Лрссуппортадминграуп.</span><span class="sxs-lookup"><span data-stu-id="82468-118">Add LRSFullAccessAdminGroup as a member of LRSSupportAdminGroup.</span></span>
    
    <span data-ttu-id="82468-119">![Страница свойств лрссуппортадминграуп "участники] " (images/Dn436325.91a4a28a-cacf-4ef6-aac1-915ec41c9648(OCS.15).png "Страница свойств лрссуппортадминграуп \"участники") "</span><span class="sxs-lookup"><span data-stu-id="82468-119">![LRSSupportAdminGroup Properties Members page](images/Dn436325.91a4a28a-cacf-4ef6-aac1-915ec41c9648(OCS.15).png "LRSSupportAdminGroup Properties Members page")</span></span>  
    
     

6.  <span data-ttu-id="82468-120">Создайте пользователя Active Directory с поддержкой возможностей SIP и именем LRSSupport.</span><span class="sxs-lookup"><span data-stu-id="82468-120">Create a SIP enabled Active Directory user with name LRSSupport.</span></span> <span data-ttu-id="82468-121">Добавьте его в группу LRSSupportAdminGroup.</span><span class="sxs-lookup"><span data-stu-id="82468-121">Add this user to LRSSupportAdminGroup.</span></span>
    
    <span data-ttu-id="82468-122">![Страница свойств лрссуппортадминграуп "участники] " (images/Dn436325.7638055d-22ac-4909-914d-1966f5623909(OCS.15).png "Страница свойств лрссуппортадминграуп \"участники") "</span><span class="sxs-lookup"><span data-stu-id="82468-122">![LRSSupportAdminGroup Properties Members page](images/Dn436325.7638055d-22ac-4909-914d-1966f5623909(OCS.15).png "LRSSupportAdminGroup Properties Members page")</span></span>  
    
     

7.  <span data-ttu-id="82468-123">Установите ASP.NET MVC 4 для Visual Studio 2010 с пакетом обновления 1 (SP1) и Visual Web Developer 2010 SP1, [http://go.microsoft.com/fwlink/p/?LinkId=323967](http://go.microsoft.com/fwlink/p/?linkid=323967)который можно найти в центре загрузки Майкрософт по адресу.</span><span class="sxs-lookup"><span data-stu-id="82468-123">Install ASP.NET MVC 4 for Visual Studio 2010 SP1 and Visual Web Developer 2010 SP1, available in the Microsoft Download Center at [http://go.microsoft.com/fwlink/p/?LinkId=323967](http://go.microsoft.com/fwlink/p/?linkid=323967).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

