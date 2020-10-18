---
title: Создание или изменение коллекции параметров конфигурации версий клиентов
description: Создание или изменение коллекции параметров конфигурации версий клиентов.
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
ms.openlocfilehash: 0082b618b8417c9d0da44599f1606cd238dfd7e8
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48578315"
---
# <a name="create-or-modify-a-collection-of-client-version-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="65659-103">Создание или изменение коллекции параметров конфигурации версий клиентов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="65659-103">Create or modify a collection of client version configuration settings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="65659-104">_**Последнее изменение темы:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="65659-104">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="65659-105">Параметры конфигурации используются для включения и отключения управления версиями клиентов.</span><span class="sxs-lookup"><span data-stu-id="65659-105">Client version configuration settings are used to turn client version control on or off.</span></span> <span data-ttu-id="65659-106">Конфигурация глобальной версии клиента устанавливается вместе с Lync Server и используется для включения или отключения управления версиями клиентов для всего развертывания сервера.</span><span class="sxs-lookup"><span data-stu-id="65659-106">The global client version configuration installs with Lync Server and is used to enable or disable client version control for the entire server deployment.</span></span> <span data-ttu-id="65659-107">Кроме того, можно настроить параметры конфигурации версий клиентов для отдельных сайтов.</span><span class="sxs-lookup"><span data-stu-id="65659-107">You can also configure client version configuration settings for individual sites.</span></span> <span data-ttu-id="65659-108">Вы можете создавать или изменять параметры конфигурации версий клиентов с помощью панели управления Lync Server 2013 или командной консоли Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="65659-108">You can create or modify client version configuration settings from Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="65659-109">Поскольку анонимные пользователи не сопоставлены с пользователем, сайтом или службой, они управляются только политиками глобального уровня.</span><span class="sxs-lookup"><span data-stu-id="65659-109">Because anonymous users are not associated with a user, site, or service, anonymous users are affected by global-level policies only.</span></span>



</div>

<div>

## <a name="to-create-or-modify-client-version-configuration-settings-by-using-lync-server-control-panel"></a><span data-ttu-id="65659-110">Создание или изменение параметров конфигурации версий клиентов с помощью панели управления Lync Server</span><span class="sxs-lookup"><span data-stu-id="65659-110">To create or modify client version configuration settings by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="65659-111">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="65659-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="65659-112">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="65659-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="65659-113">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="65659-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="65659-114">В левой панели навигации щелкните элемент **Клиенты**, а затем нажмите кнопку навигации **Конфигурация версии клиента** .</span><span class="sxs-lookup"><span data-stu-id="65659-114">In the left navigation bar, click **Clients**, and then click the **Client Version Configuration** navigation button.</span></span>

4.  <span data-ttu-id="65659-115">На странице **Конфигурация версии клиента** выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="65659-115">On the **Client Version Configuration** page, do the following:</span></span>
    
      - <span data-ttu-id="65659-116">Чтобы создать новую конфигурацию, нажмите кнопку **создать**, выберите сайт, нажмите кнопку **ОК** и обновите параметры.</span><span class="sxs-lookup"><span data-stu-id="65659-116">To create a new configuration, click **New**, select a site, click **OK** name, and update the settings.</span></span>
    
      - <span data-ttu-id="65659-117">Чтобы изменить конфигурацию, выберите конфигурацию, нажмите кнопку **изменить**, щелкните **Показать сведения**и внесите изменения в параметры.</span><span class="sxs-lookup"><span data-stu-id="65659-117">To modify a configuration, select the configuration, click **Edit**, click **Show details**, and make changes to the settings.</span></span>

</div>

<div>

## <a name="creating-or-modifying-client-version-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="65659-118">Создание или изменение параметров конфигурации версий клиентов с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="65659-118">Creating or Modifying Client Version Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="65659-119">Вы можете создать параметры конфигурации версий клиентов с помощью командлета **New – CsClientVersionConfiguration** и изменить их с помощью командлета **Set – CsClientVersionConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="65659-119">You can create client version configuration settings by using the **New-CsClientVersionConfiguration** cmdlet, and modify them by using the **Set-CsClientVersionConfiguration** cmdlet.</span></span> <span data-ttu-id="65659-120">Эти командлеты можно запускать из командной консоли Lync Server 2013 или из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="65659-120">These cmdlets can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="65659-121">Сведения об использовании удаленной оболочки Windows PowerShell для подключения к Lync Server приведены в статье "Краткое руководство по управлению Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" в статье Lync Server Windows PowerShell в блоге [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="65659-121">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-create-a-new-collection-of-client-version-configuration-settings"></a><span data-ttu-id="65659-122">Создание новой коллекции параметров конфигурации версий клиентов</span><span class="sxs-lookup"><span data-stu-id="65659-122">To create a new collection of client version configuration settings</span></span>

  - <span data-ttu-id="65659-123">Следующая команда создает новую коллекцию параметров конфигурации версий клиентов, применяемых к сайту Redmond.</span><span class="sxs-lookup"><span data-stu-id="65659-123">The following command creates a new collection of client version configuration settings applied to the Redmond site.</span></span> <span data-ttu-id="65659-124">В этом примере управление версиями клиентов отключено для сайта Redmond.</span><span class="sxs-lookup"><span data-stu-id="65659-124">In this example, client versioning is disabled for the Redmond site.</span></span>
    
        New-CsClientVersionConfiguration -Identity "site:Redmond" -Enabled $False

</div>

<div>

## <a name="to-enable-client-versioning-for-a-site"></a><span data-ttu-id="65659-125">Включение управления версиями клиентов для сайта</span><span class="sxs-lookup"><span data-stu-id="65659-125">To enable client versioning for a site</span></span>

  - <span data-ttu-id="65659-126">Эта команда включает управление версиями клиентов для сайта Redmond.</span><span class="sxs-lookup"><span data-stu-id="65659-126">This command enables client versioning for the Redmond site.</span></span>
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -Enabled $True

</div>

<div>

## <a name="to-disable-client-versioning-throughout-the-organization"></a><span data-ttu-id="65659-127">Отключение управления версиями клиентов во всей Организации</span><span class="sxs-lookup"><span data-stu-id="65659-127">To disable client versioning throughout the organization</span></span>

  - <span data-ttu-id="65659-128">В этом примере управление версиями клиентов отключено для всех параметров конфигурации версий клиентов, используемых в Организации.</span><span class="sxs-lookup"><span data-stu-id="65659-128">In this example, client versioning is disabled for all the client version configuration settings in use in the organization.</span></span>
    
        Get-CsClientVersionConfiguration | Set-CsClientVersionConfiguration  -Enabled $False

</div>

<span data-ttu-id="65659-129">Для получения дополнительных сведений обратитесь к разделу "Справка" для командлетов [New – CsClientVersionConfiguration](https://technet.microsoft.com/library/Gg399029(v=OCS.15)) и [Set CsClientVersionConfiguration](https://technet.microsoft.com/library/Gg398623(v=OCS.15)) .</span><span class="sxs-lookup"><span data-stu-id="65659-129">For details, see the Help topic for the [New-CsClientVersionConfiguration](https://technet.microsoft.com/library/Gg399029(v=OCS.15)) and [Set-CsClientVersionConfiguration](https://technet.microsoft.com/library/Gg398623(v=OCS.15)) cmdlets.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

