---
title: Изменение действия по умолчанию для клиентов, которые не поддерживаются явно или запрещены
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Modify the default action for clients not explicitly supported or restricted
ms:assetid: 548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520994(v=OCS.15)
ms:contentKeyID: 48184137
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 97b364253a87f1cbff1ef60322c65780b6497880
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826845"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-the-default-action-for-clients-not-explicitly-supported-or-restricted-in-lync-server-2013"></a><span data-ttu-id="56548-102">Изменение действия по умолчанию для клиентов, которые не поддерживаются явным образом или не ограничены в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="56548-102">Modify the default action for clients not explicitly supported or restricted in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="56548-103">_**Тема последнего изменения:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="56548-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="56548-104">Кроме того, чтобы указать версию клиентов, которую вы хотите поддерживать в среде Lync Server 2013, вы также можете задать действие по умолчанию для клиентов, у которых еще не определена политика версий.</span><span class="sxs-lookup"><span data-stu-id="56548-104">In addition to specifying the version of clients that you want to support in your Lync Server 2013 environment, you can also specify a default action for clients that do not already have a version policy defined.</span></span> <span data-ttu-id="56548-105">Это позволяет ограничить количество версий клиента, используемых в среде Lync Server, которое поможет вам управлять затратами, связанными с поддержкой нескольких клиентских версий.</span><span class="sxs-lookup"><span data-stu-id="56548-105">This enables you to restrict which client versions are used in your Lync Server environment, which can help you control the costs associated with supporting multiple client versions.</span></span>

<div>

## <a name="to-modify-the-default-action-for-clients-not-explicitly-supported-or-restricted"></a><span data-ttu-id="56548-106">Изменение действия по умолчанию для клиентов, которые не поддерживаются явно или запрещены</span><span class="sxs-lookup"><span data-stu-id="56548-106">To modify the default action for clients not explicitly supported or restricted</span></span>

1.  <span data-ttu-id="56548-107">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="56548-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="56548-108">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="56548-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="56548-109">Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="56548-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="56548-110">На панели навигации слева выберите пункт **Клиенты**, а затем — **Конфигурация клиентской версии**.</span><span class="sxs-lookup"><span data-stu-id="56548-110">In the left navigation bar, click **Clients**, and then click **Client Version Configuration**.</span></span>

4.  <span data-ttu-id="56548-111">На странице **Configuration Version (версия клиента** ) дважды щелкните **глобальную** конфигурацию в списке.</span><span class="sxs-lookup"><span data-stu-id="56548-111">On the **Client Version Configuration** page, double-click the **Global** configuration in the list.</span></span>

5.  <span data-ttu-id="56548-112">В диалоговом окне **изменение конфигурации клиента** убедитесь, что установлен флажок **включить управление версиями** , а затем в разделе **действие по умолчанию**выберите один из указанных ниже вариантов.</span><span class="sxs-lookup"><span data-stu-id="56548-112">In the **Edit Client Version Configuration** dialog box, verify that the **Enable version control** check box is selected and then, under **Default action**, select one of the following:</span></span>
    
      - <span data-ttu-id="56548-113">**Разрешить**   клиенту входить в систему, если клиентская версия не совпадает ни с одним фильтром в списке **политик версии клиента** .</span><span class="sxs-lookup"><span data-stu-id="56548-113">**Allow**   Allows the client to log on if the client version does not match any filter in the **Client version policies** list.</span></span>
    
      - <span data-ttu-id="56548-114">**Блокировать**   , если клиент не может войти в систему, если версия клиента не соответствует ни одному фильтру в списке **политики версии клиента** .</span><span class="sxs-lookup"><span data-stu-id="56548-114">**Block**   Prevents the client from logging on if the client version does not match any filter in the **Client version policies** list.</span></span>
    
      - <span data-ttu-id="56548-115">**Блокировать с URL-адресом**   запрещает клиенту входить в систему, если клиентская версия не соответствует ни одному фильтру в списке **политики версии клиента** , и содержит сообщение об ошибке с URL-адресом, по которому можно скачать более новый клиент.</span><span class="sxs-lookup"><span data-stu-id="56548-115">**Block with URL**   Prevents the client from logging on if the client version does not match any filter in the **Client version policies** list, and include an error message containing a URL where a newer client can be downloaded.</span></span>
    
      - <span data-ttu-id="56548-116">**Разрешить с помощью URL-адреса**   позволяет клиенту входить в систему, если клиентская версия не совпадает ни с одним фильтром в списке **политик версии клиента** , и содержит сообщение об ошибке с URL-адресом, по которому можно скачать более новый клиент.</span><span class="sxs-lookup"><span data-stu-id="56548-116">**Allow with URL**   Allows the client to log on if the client version does not match any filter in the **Client version policies** list, and include an error message containing a URL where a newer client can be downloaded.</span></span>

6.  <span data-ttu-id="56548-117">Если вы выбрали **блок с URL-адресом**, введите URL-адрес скачивания клиента, который нужно добавить в сообщение об ошибке в поле **URL-адрес** .</span><span class="sxs-lookup"><span data-stu-id="56548-117">If you selected **Block with URL**, type the client download URL to include in the error message in the **URL** box.</span></span>

7.  <span data-ttu-id="56548-118">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="56548-118">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-disable-client-version-control"></a><span data-ttu-id="56548-119">Отключение управления версиями клиента</span><span class="sxs-lookup"><span data-stu-id="56548-119">To disable client version control</span></span>

  - <span data-ttu-id="56548-120">Чтобы отключить управление версиями, чтобы разрешить вход всем клиентам вне зависимости от версии клиента, снимите флажок **включить управление версиями** и нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="56548-120">To disable version control to allow all clients to log on regardless of the client version, clear the **Enable version control** check box, and then click **Commit**.</span></span>

</div>

<div>

## <a name="modifying-the-default-action-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="56548-121">Изменение действия по умолчанию с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="56548-121">Modifying the Default Action by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="56548-122">Действие по умолчанию, выполняемое при попытке входа в систему с помощью клиентов, которые не поддерживаются явно или не ограничивается политикой версии клиента, можно управлять с помощью интерфейса командной строки Windows PowerShell и командлета **Set-ксклиентверсионполици** .</span><span class="sxs-lookup"><span data-stu-id="56548-122">The default action to be taken when users try to sign on using clients that are not explicitly supported or restricted by a client version policy can be managed by using Windows PowerShell command-line interface and the **Set-CsClientVersionPolicy** cmdlet.</span></span> <span data-ttu-id="56548-123">Этот командлет можно выполнить либо из управляющей оболочки Lync Server 2013, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="56548-123">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="56548-124">Подробнее об использовании удаленной оболочки Windows PowerShell для подключения к серверу Lync Server можно найти в статье "Краткое руководство по работе с Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" на [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)веб-сервере Lync Server Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="56548-124">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-configure-the-default-action-to-block-access"></a><span data-ttu-id="56548-125">Настройка действия по умолчанию для блокировки доступа</span><span class="sxs-lookup"><span data-stu-id="56548-125">To configure the default action to block access</span></span>

  - <span data-ttu-id="56548-126">Следующая команда задает действие по умолчанию для блока сайта Redmond.</span><span class="sxs-lookup"><span data-stu-id="56548-126">The following command sets the default action for the Redmond site Block.</span></span> <span data-ttu-id="56548-127">Это заблокирует регистрацию для любого клиента, для которого не существует правило конфигурации версии клиента.</span><span class="sxs-lookup"><span data-stu-id="56548-127">This will block registration for any client for which no client version configuration rule exists.</span></span>
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -DefaultAction Block

</div>

<div>

## <a name="to-configure-the-default-action-to-allow-access"></a><span data-ttu-id="56548-128">Настройка действия по умолчанию для разрешения доступа</span><span class="sxs-lookup"><span data-stu-id="56548-128">To configure the default action to allow access</span></span>

  - <span data-ttu-id="56548-129">В этом примере действие по умолчанию для сайта Redmond имеет значение Разрешить.</span><span class="sxs-lookup"><span data-stu-id="56548-129">In this example, the default action for the Redmond site is set to Allow.</span></span> <span data-ttu-id="56548-130">Это позволит зарегистрировать для любого клиента, для которого правило конфигурации для версии клиента не существует.</span><span class="sxs-lookup"><span data-stu-id="56548-130">This will allow registration for any client for which no client version configuration rule exists.</span></span>
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -DefaultAction Allow

</div>

<span data-ttu-id="56548-131">Дополнительные сведения можно найти в разделе справки по командлету [Set-ксклиентверсионполици](https://technet.microsoft.com/en-us/library/Gg398876(v=OCS.15)) .</span><span class="sxs-lookup"><span data-stu-id="56548-131">For details, see the Help topic for the [Set-CsClientVersionPolicy](https://technet.microsoft.com/en-us/library/Gg398876(v=OCS.15)) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="56548-132">См. также</span><span class="sxs-lookup"><span data-stu-id="56548-132">See Also</span></span>


[<span data-ttu-id="56548-133">Управление устройствами, телефонами и клиентскими приложениями в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="56548-133">Managing devices, phones, and client applications in Lync Server 2013</span></span>](lync-server-2013-managing-devices-phones-and-client-applications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

