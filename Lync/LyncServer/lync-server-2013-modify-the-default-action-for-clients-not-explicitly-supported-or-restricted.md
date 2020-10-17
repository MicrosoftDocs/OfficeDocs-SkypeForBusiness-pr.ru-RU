---
title: Изменение действия по умолчанию для клиентов, которые явно не поддерживаются или не ограничены
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify the default action for clients not explicitly supported or restricted
ms:assetid: 548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520994(v=OCS.15)
ms:contentKeyID: 48184137
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 213e42a7477202cf40a0b06c79edde49976f0bbc
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48515276"
---
# <a name="modify-the-default-action-for-clients-not-explicitly-supported-or-restricted-in-lync-server-2013"></a><span data-ttu-id="71a66-102">Изменение действия по умолчанию для клиентов, которые явно не поддерживаются или не ограничены в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="71a66-102">Modify the default action for clients not explicitly supported or restricted in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="71a66-103">_**Последнее изменение темы:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="71a66-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="71a66-104">В дополнение к указанию версии клиентов, которые вы хотите поддерживать в среде Lync Server 2013, можно также задать действие по умолчанию для клиентов, у которых еще не определена политика версий.</span><span class="sxs-lookup"><span data-stu-id="71a66-104">In addition to specifying the version of clients that you want to support in your Lync Server 2013 environment, you can also specify a default action for clients that do not already have a version policy defined.</span></span> <span data-ttu-id="71a66-105">Это позволяет ограничить версии клиентов, используемые в среде Lync Server, которые могут помочь управлять затратами, связанными с поддержкой нескольких версий клиентов.</span><span class="sxs-lookup"><span data-stu-id="71a66-105">This enables you to restrict which client versions are used in your Lync Server environment, which can help you control the costs associated with supporting multiple client versions.</span></span>

<div>

## <a name="to-modify-the-default-action-for-clients-not-explicitly-supported-or-restricted"></a><span data-ttu-id="71a66-106">Изменение действия по умолчанию для клиентов, которые явно не поддерживаются или ограничены</span><span class="sxs-lookup"><span data-stu-id="71a66-106">To modify the default action for clients not explicitly supported or restricted</span></span>

1.  <span data-ttu-id="71a66-107">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="71a66-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="71a66-108">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="71a66-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="71a66-109">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="71a66-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="71a66-110">В левой панели навигации щелкните **Клиенты**, а затем щелкните **Конфигурация версии клиента**.</span><span class="sxs-lookup"><span data-stu-id="71a66-110">In the left navigation bar, click **Clients**, and then click **Client Version Configuration**.</span></span>

4.  <span data-ttu-id="71a66-111">На странице **Конфигурация версии клиента** дважды щелкните **Глобальная** в списке конфигураций.</span><span class="sxs-lookup"><span data-stu-id="71a66-111">On the **Client Version Configuration** page, double-click the **Global** configuration in the list.</span></span>

5.  <span data-ttu-id="71a66-112">В диалоговом окне **Конфигурация версии клиента** убедитесь, что флажок **Включить управление версиями** установлен, а затем в поле **Действие по умолчанию** выберите один из следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="71a66-112">In the **Edit Client Version Configuration** dialog box, verify that the **Enable version control** check box is selected and then, under **Default action**, select one of the following:</span></span>
    
      - <span data-ttu-id="71a66-113">**Разрешить**     Позволяет клиенту входить в систему, если версия клиента не отвечает какому бы то ни было фильтру в списке **политик версий клиентов** .</span><span class="sxs-lookup"><span data-stu-id="71a66-113">**Allow**   Allows the client to log on if the client version does not match any filter in the **Client version policies** list.</span></span>
    
      - <span data-ttu-id="71a66-114">**Block (блокировать**     ) Запрещает клиенту входить в систему, если версия клиента не отвечает ни одному фильтру в списке **политик версий клиентов** .</span><span class="sxs-lookup"><span data-stu-id="71a66-114">**Block**   Prevents the client from logging on if the client version does not match any filter in the **Client version policies** list.</span></span>
    
      - <span data-ttu-id="71a66-115">**Блокировать с URL-адресом**     Запрещает клиенту входить в систему, если версия клиента не отвечает ни одному фильтру в списке **политик версий клиентов** , и включает сообщение об ошибке с URL-адресом, по которому можно загрузить более новую версию клиента.</span><span class="sxs-lookup"><span data-stu-id="71a66-115">**Block with URL**   Prevents the client from logging on if the client version does not match any filter in the **Client version policies** list, and include an error message containing a URL where a newer client can be downloaded.</span></span>
    
      - <span data-ttu-id="71a66-116">**Разрешить с URL-адресом**     Позволяет клиенту выполнить вход, если версия клиента не отвечает какому-либо фильтру в списке **политик версий клиентов** , и добавить сообщение об ошибке с URL-адресом, по которому можно загрузить более новую версию клиента.</span><span class="sxs-lookup"><span data-stu-id="71a66-116">**Allow with URL**   Allows the client to log on if the client version does not match any filter in the **Client version policies** list, and include an error message containing a URL where a newer client can be downloaded.</span></span>

6.  <span data-ttu-id="71a66-117">Если выбран параметра **Блокировать с URL-адресом** введите URL-адрес загрузки клиента, который нужно включить в сообщение об ошибке, в поле \*\* URL-адрес\*\*.</span><span class="sxs-lookup"><span data-stu-id="71a66-117">If you selected **Block with URL**, type the client download URL to include in the error message in the **URL** box.</span></span>

7.  <span data-ttu-id="71a66-118">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="71a66-118">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-disable-client-version-control"></a><span data-ttu-id="71a66-119">Отключение управления версиями клиента</span><span class="sxs-lookup"><span data-stu-id="71a66-119">To disable client version control</span></span>

  - <span data-ttu-id="71a66-120">Чтобы отключить управление версиями и разрешить всем клиентам входить в систему независимо от версии клиента, снимите флажок **Включить управление версиями** флажок, а затем нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="71a66-120">To disable version control to allow all clients to log on regardless of the client version, clear the **Enable version control** check box, and then click **Commit**.</span></span>

</div>

<div>

## <a name="modifying-the-default-action-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="71a66-121">Изменение действия по умолчанию с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="71a66-121">Modifying the Default Action by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="71a66-122">Действие по умолчанию, выполняемое при попытке пользователя выполнить вход с использованием клиентов, которые не поддерживаются явно или запрещено политикой версий клиентов, может управляться с помощью интерфейса командной строки Windows PowerShell и командлета **Set – CsClientVersionPolicy** .</span><span class="sxs-lookup"><span data-stu-id="71a66-122">The default action to be taken when users try to sign on using clients that are not explicitly supported or restricted by a client version policy can be managed by using Windows PowerShell command-line interface and the **Set-CsClientVersionPolicy** cmdlet.</span></span> <span data-ttu-id="71a66-123">Этот командлет можно запустить либо из командной консоли Lync Server 2013, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="71a66-123">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="71a66-124">Сведения об использовании удаленной оболочки Windows PowerShell для подключения к Lync Server приведены в статье "Краткое руководство по управлению Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" в статье Lync Server Windows PowerShell в блоге [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="71a66-124">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-configure-the-default-action-to-block-access"></a><span data-ttu-id="71a66-125">Настройка действия по умолчанию для блокировки доступа</span><span class="sxs-lookup"><span data-stu-id="71a66-125">To configure the default action to block access</span></span>

  - <span data-ttu-id="71a66-p104">Следующая команда определяет действие по умолчанию для сайта Redmond как блокировку. Это приведет к блокировке регистрации любого клиента, для которого не существует правила конфигурации клиентской версии.</span><span class="sxs-lookup"><span data-stu-id="71a66-p104">The following command sets the default action for the Redmond site Block. This will block registration for any client for which no client version configuration rule exists.</span></span>
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -DefaultAction Block

</div>

<div>

## <a name="to-configure-the-default-action-to-allow-access"></a><span data-ttu-id="71a66-128">Настройка действия по умолчанию для разрешения доступа</span><span class="sxs-lookup"><span data-stu-id="71a66-128">To configure the default action to allow access</span></span>

  - <span data-ttu-id="71a66-p105">В этом примере действием по умолчанию для сайта Redmond является разрешение. Это приведет к разрешению регистрации любого клиента, для которого не существует правила конфигурации клиентской версии.</span><span class="sxs-lookup"><span data-stu-id="71a66-p105">In this example, the default action for the Redmond site is set to Allow. This will allow registration for any client for which no client version configuration rule exists.</span></span>
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -DefaultAction Allow

</div>

<span data-ttu-id="71a66-131">Дополнительные сведения см. в разделе справки для командлета [Set – CsClientVersionPolicy](https://technet.microsoft.com/library/Gg398876(v=OCS.15)) .</span><span class="sxs-lookup"><span data-stu-id="71a66-131">For details, see the Help topic for the [Set-CsClientVersionPolicy](https://technet.microsoft.com/library/Gg398876(v=OCS.15)) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="71a66-132">См. также</span><span class="sxs-lookup"><span data-stu-id="71a66-132">See Also</span></span>


[<span data-ttu-id="71a66-133">Управление устройствами, телефонами и клиентскими приложениями в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="71a66-133">Managing devices, phones, and client applications in Lync Server 2013</span></span>](lync-server-2013-managing-devices-phones-and-client-applications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

