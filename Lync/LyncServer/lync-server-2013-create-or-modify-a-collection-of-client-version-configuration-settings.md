---
title: Создание или изменение коллекции параметров конфигурации версий клиентов
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
ms.openlocfilehash: 38f70e1d29cd6cd8de3a323829772eab1f9c3452
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035625"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-collection-of-client-version-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="af2cf-102">Создание или изменение коллекции параметров конфигурации версий клиентов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="af2cf-102">Create or modify a collection of client version configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="af2cf-103">_**Последнее изменение темы:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="af2cf-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="af2cf-104">Параметры конфигурации используются для включения и отключения управления версиями клиентов.</span><span class="sxs-lookup"><span data-stu-id="af2cf-104">Client version configuration settings are used to turn client version control on or off.</span></span> <span data-ttu-id="af2cf-105">Конфигурация глобальной версии клиента устанавливается вместе с Lync Server и используется для включения или отключения управления версиями клиентов для всего развертывания сервера.</span><span class="sxs-lookup"><span data-stu-id="af2cf-105">The global client version configuration installs with Lync Server and is used to enable or disable client version control for the entire server deployment.</span></span> <span data-ttu-id="af2cf-106">Кроме того, можно настроить параметры конфигурации версий клиентов для отдельных сайтов.</span><span class="sxs-lookup"><span data-stu-id="af2cf-106">You can also configure client version configuration settings for individual sites.</span></span> <span data-ttu-id="af2cf-107">Вы можете создавать или изменять параметры конфигурации версий клиентов с помощью панели управления Lync Server 2013 или командной консоли Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="af2cf-107">You can create or modify client version configuration settings from Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="af2cf-108">Поскольку анонимные пользователи не сопоставлены с пользователем, сайтом или службой, они управляются только политиками глобального уровня.</span><span class="sxs-lookup"><span data-stu-id="af2cf-108">Because anonymous users are not associated with a user, site, or service, anonymous users are affected by global-level policies only.</span></span>



</div>

<div>

## <a name="to-create-or-modify-client-version-configuration-settings-by-using-lync-server-control-panel"></a><span data-ttu-id="af2cf-109">Создание или изменение параметров конфигурации версий клиентов с помощью панели управления Lync Server</span><span class="sxs-lookup"><span data-stu-id="af2cf-109">To create or modify client version configuration settings by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="af2cf-110">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="af2cf-110">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="af2cf-111">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="af2cf-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="af2cf-112">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="af2cf-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="af2cf-113">В левой панели навигации щелкните элемент **Клиенты**, а затем нажмите кнопку навигации **Конфигурация версии клиента** .</span><span class="sxs-lookup"><span data-stu-id="af2cf-113">In the left navigation bar, click **Clients**, and then click the **Client Version Configuration** navigation button.</span></span>

4.  <span data-ttu-id="af2cf-114">На странице **Конфигурация версии клиента** выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="af2cf-114">On the **Client Version Configuration** page, do the following:</span></span>
    
      - <span data-ttu-id="af2cf-115">Чтобы создать новую конфигурацию, нажмите кнопку **создать**, выберите сайт, нажмите кнопку **ОК** и обновите параметры.</span><span class="sxs-lookup"><span data-stu-id="af2cf-115">To create a new configuration, click **New**, select a site, click **OK** name, and update the settings.</span></span>
    
      - <span data-ttu-id="af2cf-116">Чтобы изменить конфигурацию, выберите конфигурацию, нажмите кнопку **изменить**, щелкните **Показать сведения**и внесите изменения в параметры.</span><span class="sxs-lookup"><span data-stu-id="af2cf-116">To modify a configuration, select the configuration, click **Edit**, click **Show details**, and make changes to the settings.</span></span>

</div>

<div>

## <a name="creating-or-modifying-client-version-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="af2cf-117">Создание или изменение параметров конфигурации версий клиентов с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="af2cf-117">Creating or Modifying Client Version Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="af2cf-118">Вы можете создать параметры конфигурации версий клиентов с помощью командлета **New – CsClientVersionConfiguration** и изменить их с помощью командлета **Set – CsClientVersionConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="af2cf-118">You can create client version configuration settings by using the **New-CsClientVersionConfiguration** cmdlet, and modify them by using the **Set-CsClientVersionConfiguration** cmdlet.</span></span> <span data-ttu-id="af2cf-119">Эти командлеты можно запускать из командной консоли Lync Server 2013 или из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="af2cf-119">These cmdlets can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="af2cf-120">Сведения об использовании удаленной оболочки Windows PowerShell для подключения к Lync Server приведены в статье "Краткое руководство по управлению Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" в [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)статье Lync Server Windows PowerShell в блоге.</span><span class="sxs-lookup"><span data-stu-id="af2cf-120">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-create-a-new-collection-of-client-version-configuration-settings"></a><span data-ttu-id="af2cf-121">Создание новой коллекции параметров конфигурации версий клиентов</span><span class="sxs-lookup"><span data-stu-id="af2cf-121">To create a new collection of client version configuration settings</span></span>

  - <span data-ttu-id="af2cf-122">Следующая команда создает новую коллекцию параметров конфигурации версий клиентов, применяемых к сайту Redmond.</span><span class="sxs-lookup"><span data-stu-id="af2cf-122">The following command creates a new collection of client version configuration settings applied to the Redmond site.</span></span> <span data-ttu-id="af2cf-123">В этом примере управление версиями клиентов отключено для сайта Redmond.</span><span class="sxs-lookup"><span data-stu-id="af2cf-123">In this example, client versioning is disabled for the Redmond site.</span></span>
    
        New-CsClientVersionConfiguration -Identity "site:Redmond" -Enabled $False

</div>

<div>

## <a name="to-enable-client-versioning-for-a-site"></a><span data-ttu-id="af2cf-124">Включение управления версиями клиентов для сайта</span><span class="sxs-lookup"><span data-stu-id="af2cf-124">To enable client versioning for a site</span></span>

  - <span data-ttu-id="af2cf-125">Эта команда включает управление версиями клиентов для сайта Redmond.</span><span class="sxs-lookup"><span data-stu-id="af2cf-125">This command enables client versioning for the Redmond site.</span></span>
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -Enabled $True

</div>

<div>

## <a name="to-disable-client-versioning-throughout-the-organization"></a><span data-ttu-id="af2cf-126">Отключение управления версиями клиентов во всей Организации</span><span class="sxs-lookup"><span data-stu-id="af2cf-126">To disable client versioning throughout the organization</span></span>

  - <span data-ttu-id="af2cf-127">В этом примере управление версиями клиентов отключено для всех параметров конфигурации версий клиентов, используемых в Организации.</span><span class="sxs-lookup"><span data-stu-id="af2cf-127">In this example, client versioning is disabled for all the client version configuration settings in use in the organization.</span></span>
    
        Get-CsClientVersionConfiguration | Set-CsClientVersionConfiguration  -Enabled $False

</div>

<span data-ttu-id="af2cf-128">Для получения дополнительных сведений обратитесь к разделу "Справка" для командлетов [New – CsClientVersionConfiguration](https://technet.microsoft.com/library/Gg399029(v=OCS.15)) и [Set CsClientVersionConfiguration](https://technet.microsoft.com/library/Gg398623(v=OCS.15)) .</span><span class="sxs-lookup"><span data-stu-id="af2cf-128">For details, see the Help topic for the [New-CsClientVersionConfiguration](https://technet.microsoft.com/library/Gg399029(v=OCS.15)) and [Set-CsClientVersionConfiguration](https://technet.microsoft.com/library/Gg398623(v=OCS.15)) cmdlets.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

