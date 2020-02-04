---
title: 'Lync Server 2013: Включение и отключение управления версиями клиентов'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable or disable client versioning
ms:assetid: 33a98cb9-a979-4bb6-afb2-512f601d7ac5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ898475(v=OCS.15)
ms:contentKeyID: 50873755
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f413df3ec1d35438155492a32d9fdff449aec3c3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736199"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-client-versioning-in-lync-server-2013"></a><span data-ttu-id="dbc37-102">Включение и отключение управления версиями на клиентских компьютерах в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dbc37-102">Enable or disable client versioning in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dbc37-103">_**Тема последнего изменения:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="dbc37-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="dbc37-104">Параметры конфигурации клиентской версии используются для включения или выключения системы управления версиями на уровне клиента или для конкретных сайтов.</span><span class="sxs-lookup"><span data-stu-id="dbc37-104">Client version configuration settings are used to turn client version control on or off, either globally or for particular sites.</span></span> <span data-ttu-id="dbc37-105">Конфигурация глобальной версии клиента устанавливается вместе с Lync Server 2013 и используется для включения или отключения управления версиями для всего развертывания сервера.</span><span class="sxs-lookup"><span data-stu-id="dbc37-105">The global client version configuration installs with Lync Server 2013 and is used to enable or disable client version control for the entire server deployment.</span></span> <span data-ttu-id="dbc37-106">При включении глобальной конфигурации любые политики версий на вашем компьютере вступят в силу при попытке входа пользователя в систему.</span><span class="sxs-lookup"><span data-stu-id="dbc37-106">When the global configuration is enabled, any client version policies you have in place will take effect when users attempt to log on.</span></span> <span data-ttu-id="dbc37-107">Если вы не хотите, чтобы клиентский элемент управления версии не появлялся, вы можете отключить конфигурацию глобальной версии клиента.</span><span class="sxs-lookup"><span data-stu-id="dbc37-107">You can disable the global client version configuration if you do not want any client version control to occur.</span></span> <span data-ttu-id="dbc37-108">Вы можете включать и отключать клиентскую версию с помощью панели управления Lync Server 2013 или оболочки управления Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="dbc37-108">You can enable or disable client versioning from Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="dbc37-109">Поскольку анонимные пользователи не связаны с пользователями, сайтами или службами, к ним могут применяться только политики глобального уровня.</span><span class="sxs-lookup"><span data-stu-id="dbc37-109">Because anonymous users are not associated with a user, site, or service, anonymous users are affected by global-level policies only.</span></span>



</div>

<div>

## <a name="to-enable-or-disable-client-versioning-by-using-lync-server-control-panel"></a><span data-ttu-id="dbc37-110">Включение и отключение управления версиями на клиентских компьютерах с помощью панели управления Lync Server</span><span class="sxs-lookup"><span data-stu-id="dbc37-110">To enable or disable client versioning by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="dbc37-111">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="dbc37-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="dbc37-112">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="dbc37-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="dbc37-113">Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="dbc37-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="dbc37-114">На панели навигации слева выберите пункт **Клиенты**, а затем нажмите кнопку Навигация по **конфигурации версии клиента** .</span><span class="sxs-lookup"><span data-stu-id="dbc37-114">In the left navigation bar, click **Clients**, and then click the **Client Version Configuration** navigation button.</span></span>

4.  <span data-ttu-id="dbc37-115">Выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="dbc37-115">Do the following:</span></span>
    
      - <span data-ttu-id="dbc37-116">Чтобы включить или отключить управление версиями клиента, дважды щелкните **глобальную** конфигурацию и измените параметры.</span><span class="sxs-lookup"><span data-stu-id="dbc37-116">To globally enable or disable client versioning, double-click the **Global** configuration, and then modify the settings.</span></span>
    
      - <span data-ttu-id="dbc37-117">Чтобы включить или отключить клиентскую версию для определенного сайта, нажмите кнопку **создать**, выберите сайт, нажмите кнопку **ОК**, а затем измените параметры сайта.</span><span class="sxs-lookup"><span data-stu-id="dbc37-117">To enable or disable client versioning for a particular site, click **New**, select the site, click **OK**, and then modify the settings for the site.</span></span>

</div>

<div>

## <a name="enabling-or-disabling-client-versioning-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="dbc37-118">Включение и отключение управления версиями клиента с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="dbc37-118">Enabling or Disabling Client Versioning by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="dbc37-119">Вы можете включить или отключить управление версиями клиента с помощью командлета **Set-ксклиентверсионконфигуратион** .</span><span class="sxs-lookup"><span data-stu-id="dbc37-119">You can enable or disable client versioning by using the **Set-CsClientVersionConfiguration** cmdlet.</span></span> <span data-ttu-id="dbc37-120">Этот командлет можно выполнить либо из управляющей оболочки Lync Server 2013, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="dbc37-120">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="dbc37-121">Подробнее об использовании удаленной оболочки Windows PowerShell для подключения к серверу Lync Server можно найти в статье "Краткое руководство по работе с Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" на [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)веб-сервере Lync Server Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="dbc37-121">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-client-versioning"></a><span data-ttu-id="dbc37-122">Включение управления версиями на клиентских компьютерах</span><span class="sxs-lookup"><span data-stu-id="dbc37-122">To enable client versioning</span></span>

  - <span data-ttu-id="dbc37-123">Вы можете включить управление версиями клиентов, установив для свойства **Enabled** значение True ($true).</span><span class="sxs-lookup"><span data-stu-id="dbc37-123">You can enable client versioning by setting the **Enabled** property to True ($True).</span></span>
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -Enabled $True

</div>

<div>

## <a name="to-disable-client-versioning"></a><span data-ttu-id="dbc37-124">Отключение управления версиями на клиентских компьютерах</span><span class="sxs-lookup"><span data-stu-id="dbc37-124">To disable client versioning</span></span>

  - <span data-ttu-id="dbc37-125">Чтобы отключить управление версиями клиента, задайте для свойства **Enabled** значение False ($false).</span><span class="sxs-lookup"><span data-stu-id="dbc37-125">You can disable client versioning by setting the **Enabled** property to False ($False).</span></span>
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -Enabled $True

</div>

<span data-ttu-id="dbc37-126">Дополнительные сведения можно найти в разделе справки по командлету [Set-ксклиентверсионконфигуратион](https://docs.microsoft.com/powershell/module/skype/Set-CsClientVersionConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="dbc37-126">For details, see the Help topic for the [Set-CsClientVersionConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsClientVersionConfiguration) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

