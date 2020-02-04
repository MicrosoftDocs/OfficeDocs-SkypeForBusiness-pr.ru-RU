---
title: Создание или изменение коллекции параметров конфигурации клиентской версии
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a collection of client version configuration settings
ms:assetid: 4e6faffd-a36f-40f1-8734-78d84b7df921
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ898477(v=OCS.15)
ms:contentKeyID: 50873757
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7fc50696444ddd0602bbf21fd9e05b5bba6eddde
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722573"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-collection-of-client-version-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="643cf-102">Создание и изменение семейства параметров конфигурации клиентской версии в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="643cf-102">Create or modify a collection of client version configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="643cf-103">_**Тема последнего изменения:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="643cf-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="643cf-104">Параметры конфигурации используются для включения и отключения управления версиями клиентов.</span><span class="sxs-lookup"><span data-stu-id="643cf-104">Client version configuration settings are used to turn client version control on or off.</span></span> <span data-ttu-id="643cf-105">Конфигурация глобальной клиентской версии устанавливается вместе с Lync Server и используется для включения или отключения управления версиями на клиенте для всего развертывания сервера.</span><span class="sxs-lookup"><span data-stu-id="643cf-105">The global client version configuration installs with Lync Server and is used to enable or disable client version control for the entire server deployment.</span></span> <span data-ttu-id="643cf-106">Вы также можете настроить параметры конфигурации клиента для отдельных сайтов.</span><span class="sxs-lookup"><span data-stu-id="643cf-106">You can also configure client version configuration settings for individual sites.</span></span> <span data-ttu-id="643cf-107">Вы можете создавать и изменять параметры конфигурации клиентской версии из панели управления Lync Server 2013 или оболочки управления Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="643cf-107">You can create or modify client version configuration settings from Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="643cf-108">Поскольку анонимные пользователи не связаны с пользователями, сайтами или службами, к ним могут применяться только политики глобального уровня.</span><span class="sxs-lookup"><span data-stu-id="643cf-108">Because anonymous users are not associated with a user, site, or service, anonymous users are affected by global-level policies only.</span></span>



</div>

<div>

## <a name="to-create-or-modify-client-version-configuration-settings-by-using-lync-server-control-panel"></a><span data-ttu-id="643cf-109">Создание и изменение параметров конфигурации клиентской версии с помощью панели управления Lync Server</span><span class="sxs-lookup"><span data-stu-id="643cf-109">To create or modify client version configuration settings by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="643cf-110">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="643cf-110">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="643cf-111">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="643cf-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="643cf-112">Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="643cf-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="643cf-113">На панели навигации слева выберите пункт **Клиенты**, а затем нажмите кнопку Навигация по **конфигурации версии клиента** .</span><span class="sxs-lookup"><span data-stu-id="643cf-113">In the left navigation bar, click **Clients**, and then click the **Client Version Configuration** navigation button.</span></span>

4.  <span data-ttu-id="643cf-114">На странице **Configuration Version (версия клиента** ) выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="643cf-114">On the **Client Version Configuration** page, do the following:</span></span>
    
      - <span data-ttu-id="643cf-115">Чтобы создать новую конфигурацию, нажмите кнопку **создать**, выберите сайт, нажмите кнопку **ОК** и обновите параметры.</span><span class="sxs-lookup"><span data-stu-id="643cf-115">To create a new configuration, click **New**, select a site, click **OK** name, and update the settings.</span></span>
    
      - <span data-ttu-id="643cf-116">Чтобы изменить конфигурацию, выберите ее, нажмите кнопку **изменить**, щелкните **Показать подробности**и внесите изменения в параметры.</span><span class="sxs-lookup"><span data-stu-id="643cf-116">To modify a configuration, select the configuration, click **Edit**, click **Show details**, and make changes to the settings.</span></span>

</div>

<div>

## <a name="creating-or-modifying-client-version-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="643cf-117">Создание и изменение параметров конфигурации клиентской версии с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="643cf-117">Creating or Modifying Client Version Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="643cf-118">Вы можете создать параметры конфигурации клиентской версии с помощью командлета **New-ксклиентверсионконфигуратион** и изменить их с помощью командлета **Set-ксклиентверсионконфигуратион** .</span><span class="sxs-lookup"><span data-stu-id="643cf-118">You can create client version configuration settings by using the **New-CsClientVersionConfiguration** cmdlet, and modify them by using the **Set-CsClientVersionConfiguration** cmdlet.</span></span> <span data-ttu-id="643cf-119">Эти командлеты можно запускать либо из командной консоли Lync Server 2013, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="643cf-119">These cmdlets can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="643cf-120">Подробнее об использовании удаленной оболочки Windows PowerShell для подключения к серверу Lync Server можно найти в статье "Краткое руководство по работе с Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" на [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)веб-сервере Lync Server Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="643cf-120">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-create-a-new-collection-of-client-version-configuration-settings"></a><span data-ttu-id="643cf-121">Создание коллекции параметров конфигурации клиентской версии</span><span class="sxs-lookup"><span data-stu-id="643cf-121">To create a new collection of client version configuration settings</span></span>

  - <span data-ttu-id="643cf-122">Следующая команда создает новую коллекцию параметров конфигурации для версии клиента, примененную к сайту Redmond.</span><span class="sxs-lookup"><span data-stu-id="643cf-122">The following command creates a new collection of client version configuration settings applied to the Redmond site.</span></span> <span data-ttu-id="643cf-123">В этом примере управление версиями клиента отключено для сайта Redmond.</span><span class="sxs-lookup"><span data-stu-id="643cf-123">In this example, client versioning is disabled for the Redmond site.</span></span>
    
        New-CsClientVersionConfiguration -Identity "site:Redmond" -Enabled $False

</div>

<div>

## <a name="to-enable-client-versioning-for-a-site"></a><span data-ttu-id="643cf-124">Включение управления версиями на сайте</span><span class="sxs-lookup"><span data-stu-id="643cf-124">To enable client versioning for a site</span></span>

  - <span data-ttu-id="643cf-125">Эта команда включает управление версиями клиентов для сайта Redmond.</span><span class="sxs-lookup"><span data-stu-id="643cf-125">This command enables client versioning for the Redmond site.</span></span>
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -Enabled $True

</div>

<div>

## <a name="to-disable-client-versioning-throughout-the-organization"></a><span data-ttu-id="643cf-126">Отключение управления версиями клиента во всей Организации</span><span class="sxs-lookup"><span data-stu-id="643cf-126">To disable client versioning throughout the organization</span></span>

  - <span data-ttu-id="643cf-127">В этом примере управление версиями клиента отключено для всех параметров конфигурации клиентской версии, используемых в Организации.</span><span class="sxs-lookup"><span data-stu-id="643cf-127">In this example, client versioning is disabled for all the client version configuration settings in use in the organization.</span></span>
    
        Get-CsClientVersionConfiguration | Set-CsClientVersionConfiguration  -Enabled $False

</div>

<span data-ttu-id="643cf-128">Дополнительные сведения можно найти в разделе справки по командлетам [New-ксклиентверсионконфигуратион](https://technet.microsoft.com/en-us/library/Gg399029(v=OCS.15)) и [ксклиентверсионконфигуратион](https://technet.microsoft.com/en-us/library/Gg398623(v=OCS.15)) .</span><span class="sxs-lookup"><span data-stu-id="643cf-128">For details, see the Help topic for the [New-CsClientVersionConfiguration](https://technet.microsoft.com/en-us/library/Gg399029(v=OCS.15)) and [Set-CsClientVersionConfiguration](https://technet.microsoft.com/en-us/library/Gg398623(v=OCS.15)) cmdlets.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

