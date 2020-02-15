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
ms.openlocfilehash: d86fc41847485cbe797da9e9c9ace4a0a8794280
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42042546"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-client-versioning-in-lync-server-2013"></a><span data-ttu-id="fc4ea-102">Включение или отключение управления версиями клиентов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fc4ea-102">Enable or disable client versioning in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fc4ea-103">_**Последнее изменение темы:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="fc4ea-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="fc4ea-104">Параметры конфигурации версий клиентов используются для включения или отключения управления версиями клиентов (глобально или для определенных сайтов).</span><span class="sxs-lookup"><span data-stu-id="fc4ea-104">Client version configuration settings are used to turn client version control on or off, either globally or for particular sites.</span></span> <span data-ttu-id="fc4ea-105">Конфигурация глобальной версии клиента устанавливается вместе с Lync Server 2013 и используется для включения или отключения управления версиями клиентов для всего развертывания сервера.</span><span class="sxs-lookup"><span data-stu-id="fc4ea-105">The global client version configuration installs with Lync Server 2013 and is used to enable or disable client version control for the entire server deployment.</span></span> <span data-ttu-id="fc4ea-106">Когда Глобальная конфигурация включена, все политики версий клиентов, которые вы используете, вступят в силу при попытке пользователей войти в систему.</span><span class="sxs-lookup"><span data-stu-id="fc4ea-106">When the global configuration is enabled, any client version policies you have in place will take effect when users attempt to log on.</span></span> <span data-ttu-id="fc4ea-107">Вы можете отключить конфигурацию глобальной версии клиента, если не хотите, чтобы клиентский элемент управления версии не выполнялся.</span><span class="sxs-lookup"><span data-stu-id="fc4ea-107">You can disable the global client version configuration if you do not want any client version control to occur.</span></span> <span data-ttu-id="fc4ea-108">Вы можете включить или отключить управление версиями клиентов с помощью панели управления Lync Server 2013 или командной консоли Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fc4ea-108">You can enable or disable client versioning from Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="fc4ea-109">Поскольку анонимные пользователи не сопоставлены с пользователем, сайтом или службой, они управляются только политиками глобального уровня.</span><span class="sxs-lookup"><span data-stu-id="fc4ea-109">Because anonymous users are not associated with a user, site, or service, anonymous users are affected by global-level policies only.</span></span>



</div>

<div>

## <a name="to-enable-or-disable-client-versioning-by-using-lync-server-control-panel"></a><span data-ttu-id="fc4ea-110">Включение и выключение управления версиями клиентов с помощью панели управления Lync Server</span><span class="sxs-lookup"><span data-stu-id="fc4ea-110">To enable or disable client versioning by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="fc4ea-111">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="fc4ea-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="fc4ea-112">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="fc4ea-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="fc4ea-113">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="fc4ea-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="fc4ea-114">В левой панели навигации щелкните элемент **Клиенты**, а затем нажмите кнопку навигации **Конфигурация версии клиента** .</span><span class="sxs-lookup"><span data-stu-id="fc4ea-114">In the left navigation bar, click **Clients**, and then click the **Client Version Configuration** navigation button.</span></span>

4.  <span data-ttu-id="fc4ea-115">Выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="fc4ea-115">Do the following:</span></span>
    
      - <span data-ttu-id="fc4ea-116">Чтобы глобально включить или отключить управление версиями клиентов, дважды щелкните **глобальную** конфигурацию, а затем измените параметры.</span><span class="sxs-lookup"><span data-stu-id="fc4ea-116">To globally enable or disable client versioning, double-click the **Global** configuration, and then modify the settings.</span></span>
    
      - <span data-ttu-id="fc4ea-117">Чтобы включить или отключить управление версиями клиентов для определенного сайта, нажмите кнопку **создать**, выберите сайт, нажмите кнопку **ОК**, а затем измените параметры сайта.</span><span class="sxs-lookup"><span data-stu-id="fc4ea-117">To enable or disable client versioning for a particular site, click **New**, select the site, click **OK**, and then modify the settings for the site.</span></span>

</div>

<div>

## <a name="enabling-or-disabling-client-versioning-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="fc4ea-118">Включение или отключение управления версиями клиентов с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="fc4ea-118">Enabling or Disabling Client Versioning by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="fc4ea-119">Вы можете включить или отключить управление версиями клиентов с помощью командлета **Set – CsClientVersionConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="fc4ea-119">You can enable or disable client versioning by using the **Set-CsClientVersionConfiguration** cmdlet.</span></span> <span data-ttu-id="fc4ea-120">Этот командлет можно запустить либо из командной консоли Lync Server 2013, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fc4ea-120">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="fc4ea-121">Сведения об использовании удаленной оболочки Windows PowerShell для подключения к Lync Server приведены в статье "Краткое руководство по управлению Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" в [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)статье Lync Server Windows PowerShell в блоге.</span><span class="sxs-lookup"><span data-stu-id="fc4ea-121">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-client-versioning"></a><span data-ttu-id="fc4ea-122">Включение управления версиями клиентов</span><span class="sxs-lookup"><span data-stu-id="fc4ea-122">To enable client versioning</span></span>

  - <span data-ttu-id="fc4ea-123">Можно включить управление версиями клиентов, задав для свойства **Enabled** значение True ($true).</span><span class="sxs-lookup"><span data-stu-id="fc4ea-123">You can enable client versioning by setting the **Enabled** property to True ($True).</span></span>
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -Enabled $True

</div>

<div>

## <a name="to-disable-client-versioning"></a><span data-ttu-id="fc4ea-124">Отключение управления версиями клиентов</span><span class="sxs-lookup"><span data-stu-id="fc4ea-124">To disable client versioning</span></span>

  - <span data-ttu-id="fc4ea-125">Вы можете отключить управление версиями клиентов, задав для свойства **Enabled** значение False ($false).</span><span class="sxs-lookup"><span data-stu-id="fc4ea-125">You can disable client versioning by setting the **Enabled** property to False ($False).</span></span>
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -Enabled $True

</div>

<span data-ttu-id="fc4ea-126">Дополнительные сведения см. в разделе справки для командлета [Set – CsClientVersionConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsClientVersionConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="fc4ea-126">For details, see the Help topic for the [Set-CsClientVersionConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsClientVersionConfiguration) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

