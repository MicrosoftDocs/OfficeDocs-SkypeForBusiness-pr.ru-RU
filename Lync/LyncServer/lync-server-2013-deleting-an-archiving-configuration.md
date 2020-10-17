---
title: 'Lync Server 2013: Удаление конфигурации архивации'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting an Archiving configuration
ms:assetid: a8744d39-5cf2-474c-9a99-a0f3a37f846f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205167(v=OCS.15)
ms:contentKeyID: 48185093
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: acca3c362a5e0a2a8a6198d156c24be47884d70a
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48525446"
---
# <a name="deleting-an-archiving-configuration-in-lync-server-2013"></a><span data-ttu-id="d3cfe-102">Удаление конфигурации архивации в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d3cfe-102">Deleting an Archiving configuration in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d3cfe-103">_**Последнее изменение темы:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="d3cfe-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="d3cfe-104">Вы можете удалить конфигурацию сайта или пула.</span><span class="sxs-lookup"><span data-stu-id="d3cfe-104">You can delete a site configuration or pool configuration.</span></span> <span data-ttu-id="d3cfe-105">Однако, нельзя удалить глобальную конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="d3cfe-105">The global configuration cannot be removed.</span></span> <span data-ttu-id="d3cfe-106">Если вы все же удалите глобальную конфигурацию, параметрам будут автоматически присвоены значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="d3cfe-106">If you delete the global configuration, it is automatically reset to the default values.</span></span> <span data-ttu-id="d3cfe-107">Для получения дополнительных сведений о способах реализации конфигурации архивации, в том числе о том, какие параметры можно указать и иерархию конфигураций архивации, посмотрите, [как работает архивация в Lync Server 2013](lync-server-2013-how-archiving-works.md) в документации по планированию, документации по развертыванию или документации по операциям.</span><span class="sxs-lookup"><span data-stu-id="d3cfe-107">For details about how Archiving configurations are implemented, including which options you can specify and the hierarchy of Archiving configurations, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>

## <a name="to-delete-a-site-or-pool-configuration-for-archiving"></a><span data-ttu-id="d3cfe-108">Удаление конфигурации сайта или пула для архивации</span><span class="sxs-lookup"><span data-stu-id="d3cfe-108">To delete a site or pool configuration for archiving</span></span>

1.  <span data-ttu-id="d3cfe-109">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsArchivingAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="d3cfe-109">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="d3cfe-110">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d3cfe-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="d3cfe-111">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="d3cfe-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="d3cfe-112">В левой панели навигации щелкните **мониторинг и архивация**, а затем щелкните **Конфигурация архивации**.</span><span class="sxs-lookup"><span data-stu-id="d3cfe-112">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>

4.  <span data-ttu-id="d3cfe-113">В списке конфигураций архивации щелкните конфигурацию сайта или пула, которую необходимо удалить, а затем щелкните **Edit** (Изменить) и **Delete** (Удалить).</span><span class="sxs-lookup"><span data-stu-id="d3cfe-113">In the list of archiving configurations, click the site or pool configuration that you want to delete, click **Edit**, and then click **Delete**.</span></span>

5.  <span data-ttu-id="d3cfe-114">Щелкните **Commit** (Сохранить).</span><span class="sxs-lookup"><span data-stu-id="d3cfe-114">Click **Commit**.</span></span>

</div>

<div>

## <a name="removing-archiving-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="d3cfe-115">Удаление параметров конфигурации архивации с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d3cfe-115">Removing Archiving Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="d3cfe-116">Параметры конфигурации архивации можно удалить с помощью Windows PowerShell и командлета **Remove – CsArchivingConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="d3cfe-116">Archiving configuration settings can be deleted by using Windows PowerShell and the **Remove-CsArchivingConfiguration** cmdlet.</span></span> <span data-ttu-id="d3cfe-117">Этот командлет можно запустить либо из командной консоли Lync Server 2013, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d3cfe-117">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="d3cfe-118">Сведения об использовании удаленной оболочки Windows PowerShell для подключения к Lync Server приведены в статье "Краткое руководство по управлению Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" в статье Lync Server Windows PowerShell в блоге [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="d3cfe-118">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-specified-collection-of-archiving-configuration-settings"></a><span data-ttu-id="d3cfe-119">Удаление указанной коллекции параметров конфигурации архивации</span><span class="sxs-lookup"><span data-stu-id="d3cfe-119">To remove a specified collection of archiving configuration settings</span></span>

  - <span data-ttu-id="d3cfe-120">Следующая команда удаляет параметры конфигурации архивации, применяемые к сайту Redmond.</span><span class="sxs-lookup"><span data-stu-id="d3cfe-120">The following command removes the archiving configuration settings applied to the Redmond site:</span></span>
    
        Remove-CsArchivingConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-the-archiving-configuration-settings-applied-to-the-site-scope"></a><span data-ttu-id="d3cfe-121">Удаление всех параметров конфигурации архивации, применяемых на уровне сайта</span><span class="sxs-lookup"><span data-stu-id="d3cfe-121">To remove all the archiving configuration settings applied to the site scope</span></span>

  - <span data-ttu-id="d3cfe-122">Эта команда удаляет все параметры конфигурации архивации, применяемые на уровне службы.</span><span class="sxs-lookup"><span data-stu-id="d3cfe-122">This command removes all the archiving configuration settings applied to the service scope:</span></span>
    
        Get-CsArchivingConfiguration -Filter "site:*" | Remove-CsArchivingConfiguration

</div>

<div>

## <a name="to-remove-archiving-configuration-settings-based-on-a-specified-property-value"></a><span data-ttu-id="d3cfe-123">Удаление параметров конфигурации архивации на основе указанного значения свойства</span><span class="sxs-lookup"><span data-stu-id="d3cfe-123">To remove archiving configuration settings based on a specified property value</span></span>

  - <span data-ttu-id="d3cfe-124">Эта команда удаляет все параметры конфигурации архивации, в которых отключена служба архивации Exchange.</span><span class="sxs-lookup"><span data-stu-id="d3cfe-124">This command removes all the archiving configuration settings where Exchange archiving has been disabled:</span></span>
    
        Get-CsArchivingConfiguration | Where-Object {$_.EnableExchangeArchiving -eq $False} | Remove-CsArchivingConfiguration

</div>

<span data-ttu-id="d3cfe-125">Для получения дополнительных сведений обратитесь к разделу "Справка" для командлета [Remove – CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsArchivingConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="d3cfe-125">For more information, see the help topic for the [Remove-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsArchivingConfiguration) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d3cfe-126">См. также</span><span class="sxs-lookup"><span data-stu-id="d3cfe-126">See Also</span></span>


[<span data-ttu-id="d3cfe-127">Принцип работы архивации в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d3cfe-127">How Archiving works in Lync Server 2013</span></span>](lync-server-2013-how-archiving-works.md)  


[<span data-ttu-id="d3cfe-128">Управление архивацией внутренних и внешних коммуникаций в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d3cfe-128">Managing the Archiving of internal and external communications in Lync Server 2013</span></span>](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

