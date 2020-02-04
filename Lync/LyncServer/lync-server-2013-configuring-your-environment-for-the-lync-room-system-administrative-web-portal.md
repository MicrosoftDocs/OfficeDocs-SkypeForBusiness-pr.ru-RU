---
title: 'Lync Server 2013: настройка среды для работы с веб-порталом администрирования системы комнат Lync'
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
ms.openlocfilehash: 4f0f415cfeca5b798a1e29ac6ebe09105fbf08b4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740589"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-your-lync-server-2013-environment-for-the-lync-room-system-administrative-web-portal"></a><span data-ttu-id="f8a0a-102">Configuring your Lync Server 2013 environment for the Lync Room System Administrative Web Portal</span><span class="sxs-lookup"><span data-stu-id="f8a0a-102">Configuring your Lync Server 2013 environment for the Lync Room System Administrative Web Portal</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f8a0a-103">_**Тема последнего изменения:** 2014-05-22_</span><span class="sxs-lookup"><span data-stu-id="f8a0a-103">_**Topic Last Modified:** 2014-05-22_</span></span>

<span data-ttu-id="f8a0a-104">Чтобы использовать веб-портал для управления комнатой на Lync (ЛРС), необходимо установить или настроить следующие необходимые компоненты.</span><span class="sxs-lookup"><span data-stu-id="f8a0a-104">To use the Lync Room System (LRS) Administrative Web Portal, you will need to install or configure the following prerequisites.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="f8a0a-105">Если сервер настроен на проверку подлинности Kerberos и NTLM и ЛРС запущен на компьютере, который не подключен к домену, проверка подлинности Kerberos не будет выполнена, и пользователь не увидит состояние ЛРС на административном портале.</span><span class="sxs-lookup"><span data-stu-id="f8a0a-105">If the server is configured with both Kerberos and NTLM authentication, and LRS is running on a computer that is not joined to the domain, Kerberos authentication will fail and the user will not see the status of LRS in the administrative portal.</span></span> <span data-ttu-id="f8a0a-106">Чтобы устранить эту проблему, настройте сервер для проверки подлинности NTLM либо проверки подлинности NTLM и TLS-ДСК (без Kerberos) либо Присоедините компьютер ЛРС к домену.</span><span class="sxs-lookup"><span data-stu-id="f8a0a-106">To resolve this issue, configure the server with NTLM authentication or both NTLM and TLS-DSK authentication (without Kerberos), or join the LRS computer to the domain.</span></span>



</div>

1.  <span data-ttu-id="f8a0a-107">Установка накопительных обновлений для Lync Server 2013: Июль 2013 в топологии Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f8a0a-107">Install Lync Server 2013 Cumulative Updates: July 2013 in the Lync Server topology.</span></span>
    
    <span data-ttu-id="f8a0a-108">Чтобы получить обновление или просмотреть сведения о том, что входит в состав этого приложения, ознакомьтесь со статьей [Обновление для Lync Server 2013](http://go.microsoft.com/fwlink/p/?linkid=323959).</span><span class="sxs-lookup"><span data-stu-id="f8a0a-108">To get the update or see what’s included with it, see [Updates for Lync Server 2013](http://go.microsoft.com/fwlink/p/?linkid=323959).</span></span>

2.  <span data-ttu-id="f8a0a-109">Создайте учетную запись пользователя Active Directory с включенной поддержкой SIP.</span><span class="sxs-lookup"><span data-stu-id="f8a0a-109">Create a SIP-enabled Active Directory user.</span></span>
    
    <span data-ttu-id="f8a0a-110">На веб-портале ЛРС администрирования эти учетные данные используются для запроса данных с сервера Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f8a0a-110">The LRS Administrative Web Portal uses these credentials to query information from Lync Server.</span></span> <span data-ttu-id="f8a0a-111">Рекомендуемое имя пользователя — Лрсапп.</span><span class="sxs-lookup"><span data-stu-id="f8a0a-111">The recommended username is LRSApp.</span></span>

3.  <span data-ttu-id="f8a0a-112">Создайте группу безопасности Active Directory с именем LRSSupportAdminGroup.</span><span class="sxs-lookup"><span data-stu-id="f8a0a-112">Create an Active Directory security group with name LRSSupportAdminGroup.</span></span>
    
    <span data-ttu-id="f8a0a-p103">Создайте группу с глобальной областью действия и типом "Безопасность". Пользователи с включенной поддержкой SIP, добавляемые в эту группу, будут автоматически получать разрешения на просмотр списка комнат и выполнение определенных команд, таких как ведение журналов.</span><span class="sxs-lookup"><span data-stu-id="f8a0a-p103">Create the group with Group Scope as Global and Group Type as Security. SIP enabled users who are added to this group will be authorized to see the list of rooms and execute certain commands, such as collecting logs.</span></span>

4.  <span data-ttu-id="f8a0a-115">Создайте группу безопасности Active Directory с именем LRSFullAccessAdminGroup. </span><span class="sxs-lookup"><span data-stu-id="f8a0a-115">Create an Active Directory security group with name LRSFullAccessAdminGroup.</span></span>
    
    <span data-ttu-id="f8a0a-116">Создание группы с областью группировки в качестве глобальных и группового типа как "безопасность". Пользователи, добавленные в эту группу, имеют разрешение на использование всех функций портала администрирования.</span><span class="sxs-lookup"><span data-stu-id="f8a0a-116">Create the group with Group Scope as Global and Group Type as Security.SIP enabled users who are added to this group are authorized to use all admin portal functionality.</span></span>
    
     
    
    <span data-ttu-id="f8a0a-117">![Список групп администрирования с ролью группы безопасности](images/Dn436325.5d432819-a2e2-452c-bc2a-5d4ee79d8c33(OCS.15).png "Список групп администрирования с ролью группы безопасности")</span><span class="sxs-lookup"><span data-stu-id="f8a0a-117">![List of Admin Groups with security group role](images/Dn436325.5d432819-a2e2-452c-bc2a-5d4ee79d8c33(OCS.15).png "List of Admin Groups with security group role")</span></span>  
    
     

5.  <span data-ttu-id="f8a0a-118">Добавьте Лрсфуллакцессадминграуп в качестве участника Лрссуппортадминграуп.</span><span class="sxs-lookup"><span data-stu-id="f8a0a-118">Add LRSFullAccessAdminGroup as a member of LRSSupportAdminGroup.</span></span>
    
    <span data-ttu-id="f8a0a-119">![Свойства LRSSupportAdminGroup, страница участников](images/Dn436325.91a4a28a-cacf-4ef6-aac1-915ec41c9648(OCS.15).png "Свойства LRSSupportAdminGroup, страница участников")</span><span class="sxs-lookup"><span data-stu-id="f8a0a-119">![LRSSupportAdminGroup Properties Members page](images/Dn436325.91a4a28a-cacf-4ef6-aac1-915ec41c9648(OCS.15).png "LRSSupportAdminGroup Properties Members page")</span></span>  
    
     

6.  <span data-ttu-id="f8a0a-120">Создайте пользователя Active Directory с поддержкой возможностей SIP и именем LRSSupport.</span><span class="sxs-lookup"><span data-stu-id="f8a0a-120">Create a SIP enabled Active Directory user with name LRSSupport.</span></span> <span data-ttu-id="f8a0a-121">Добавьте его в группу LRSSupportAdminGroup.</span><span class="sxs-lookup"><span data-stu-id="f8a0a-121">Add this user to LRSSupportAdminGroup.</span></span>
    
    <span data-ttu-id="f8a0a-122">![Свойства LRSSupportAdminGroup, страница участников](images/Dn436325.7638055d-22ac-4909-914d-1966f5623909(OCS.15).png "Свойства LRSSupportAdminGroup, страница участников")</span><span class="sxs-lookup"><span data-stu-id="f8a0a-122">![LRSSupportAdminGroup Properties Members page](images/Dn436325.7638055d-22ac-4909-914d-1966f5623909(OCS.15).png "LRSSupportAdminGroup Properties Members page")</span></span>  
    
     

7.  <span data-ttu-id="f8a0a-123">Установите ASP.NET MVC 4 для Visual Studio 2010 с пакетом обновления 1 (SP1) и Visual Web Developer 2010 SP1, [http://go.microsoft.com/fwlink/p/?LinkId=323967](http://go.microsoft.com/fwlink/p/?linkid=323967)который можно найти в центре загрузки Майкрософт по адресу.</span><span class="sxs-lookup"><span data-stu-id="f8a0a-123">Install ASP.NET MVC 4 for Visual Studio 2010 SP1 and Visual Web Developer 2010 SP1, available in the Microsoft Download Center at [http://go.microsoft.com/fwlink/p/?LinkId=323967](http://go.microsoft.com/fwlink/p/?linkid=323967).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

