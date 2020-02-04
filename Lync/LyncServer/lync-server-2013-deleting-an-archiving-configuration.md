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
ms.openlocfilehash: 9e4a0c1acf9f605fc927d7006ff50b1f4470c68d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763123"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deleting-an-archiving-configuration-in-lync-server-2013"></a><span data-ttu-id="76bf1-102">Удаление конфигурации архивации в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="76bf1-102">Deleting an Archiving configuration in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="76bf1-103">_**Тема последнего изменения:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="76bf1-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="76bf1-104">Вы можете удалить конфигурацию сайта или конфигурацию пула.</span><span class="sxs-lookup"><span data-stu-id="76bf1-104">You can delete a site configuration or pool configuration.</span></span> <span data-ttu-id="76bf1-105">Невозможно удалить глобальную конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="76bf1-105">The global configuration cannot be removed.</span></span> <span data-ttu-id="76bf1-106">При удалении глобальной конфигурации она автоматически восстанавливает значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="76bf1-106">If you delete the global configuration, it is automatically reset to the default values.</span></span> <span data-ttu-id="76bf1-107">Сведения о том, как работают конфигурации архивации, в том числе о параметрах, которые можно указать и в иерархии конфигураций архивации, описаны в разделе [Использование архивации в Lync Server 2013](lync-server-2013-how-archiving-works.md) в документации по планированию, документации по развертыванию или документации по операциям.</span><span class="sxs-lookup"><span data-stu-id="76bf1-107">For details about how Archiving configurations are implemented, including which options you can specify and the hierarchy of Archiving configurations, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>

## <a name="to-delete-a-site-or-pool-configuration-for-archiving"></a><span data-ttu-id="76bf1-108">Удаление конфигурации сайта или пула для архивации</span><span class="sxs-lookup"><span data-stu-id="76bf1-108">To delete a site or pool configuration for archiving</span></span>

1.  <span data-ttu-id="76bf1-109">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsArchivingAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="76bf1-109">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="76bf1-110">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="76bf1-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="76bf1-111">Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="76bf1-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="76bf1-112">На левой панели навигации щелкните **Мониторинг и архивация**, а затем щелкните **Конфигурация архивации**.</span><span class="sxs-lookup"><span data-stu-id="76bf1-112">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>

4.  <span data-ttu-id="76bf1-113">В списке конфигураций архивирования нажмите конфигурацию сайта или пула, которую необходимо удалить, затем выберите **Изменить** и **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="76bf1-113">In the list of archiving configurations, click the site or pool configuration that you want to delete, click **Edit**, and then click **Delete**.</span></span>

5.  <span data-ttu-id="76bf1-114">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="76bf1-114">Click **Commit**.</span></span>

</div>

<div>

## <a name="removing-archiving-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="76bf1-115">Удаление параметров конфигурации архивации с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="76bf1-115">Removing Archiving Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="76bf1-116">Параметры конфигурации архивации можно удалить с помощью Windows PowerShell и командлета **Remove-ксарчивингконфигуратион** .</span><span class="sxs-lookup"><span data-stu-id="76bf1-116">Archiving configuration settings can be deleted by using Windows PowerShell and the **Remove-CsArchivingConfiguration** cmdlet.</span></span> <span data-ttu-id="76bf1-117">Этот командлет можно выполнить либо из управляющей оболочки Lync Server 2013, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="76bf1-117">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="76bf1-118">Подробнее об использовании удаленной оболочки Windows PowerShell для подключения к серверу Lync Server можно найти в статье "Краткое руководство по работе с Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" на [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)веб-сервере Lync Server Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="76bf1-118">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-specified-collection-of-archiving-configuration-settings"></a><span data-ttu-id="76bf1-119">Удаление заданной коллекции параметров конфигурации архивации</span><span class="sxs-lookup"><span data-stu-id="76bf1-119">To remove a specified collection of archiving configuration settings</span></span>

  - <span data-ttu-id="76bf1-120">Следующая команда удаляет параметры конфигурации архивации, примененные к сайту Redmond.</span><span class="sxs-lookup"><span data-stu-id="76bf1-120">The following command removes the archiving configuration settings applied to the Redmond site:</span></span>
    
        Remove-CsArchivingConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-the-archiving-configuration-settings-applied-to-the-site-scope"></a><span data-ttu-id="76bf1-121">Удаление всех параметров конфигурации архивации, примененных к области сайта</span><span class="sxs-lookup"><span data-stu-id="76bf1-121">To remove all the archiving configuration settings applied to the site scope</span></span>

  - <span data-ttu-id="76bf1-122">Эта команда удаляет все параметры конфигурации архивации, примененные к области служб.</span><span class="sxs-lookup"><span data-stu-id="76bf1-122">This command removes all the archiving configuration settings applied to the service scope:</span></span>
    
        Get-CsArchivingConfiguration -Filter "site:*" | Remove-CsArchivingConfiguration

</div>

<div>

## <a name="to-remove-archiving-configuration-settings-based-on-a-specified-property-value"></a><span data-ttu-id="76bf1-123">Удаление параметров конфигурации архивации на основе заданного значения свойства</span><span class="sxs-lookup"><span data-stu-id="76bf1-123">To remove archiving configuration settings based on a specified property value</span></span>

  - <span data-ttu-id="76bf1-124">Эта команда удаляет все параметры конфигурации архивации, в которых отключено архивирование Exchange.</span><span class="sxs-lookup"><span data-stu-id="76bf1-124">This command removes all the archiving configuration settings where Exchange archiving has been disabled:</span></span>
    
        Get-CsArchivingConfiguration | Where-Object {$_.EnableExchangeArchiving -eq $False} | Remove-CsArchivingConfiguration

</div>

<span data-ttu-id="76bf1-125">Дополнительные сведения можно найти в разделе справки по командлету [Remove-ксарчивингконфигуратион](https://docs.microsoft.com/powershell/module/skype/Remove-CsArchivingConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="76bf1-125">For more information, see the help topic for the [Remove-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsArchivingConfiguration) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="76bf1-126">См. также</span><span class="sxs-lookup"><span data-stu-id="76bf1-126">See Also</span></span>


[<span data-ttu-id="76bf1-127">Как работает архивация в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="76bf1-127">How Archiving works in Lync Server 2013</span></span>](lync-server-2013-how-archiving-works.md)  


[<span data-ttu-id="76bf1-128">Управление архивированием внутренней и внешней связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="76bf1-128">Managing the Archiving of internal and external communications in Lync Server 2013</span></span>](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

