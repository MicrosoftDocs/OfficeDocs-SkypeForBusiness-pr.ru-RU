---
title: 'Lync Server 2013: включение контроля допуска звонков'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable call admission control
ms:assetid: 80201105-18f7-4c02-9c71-8df5a952f6c7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398642(v=OCS.15)
ms:contentKeyID: 48184650
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e181c0fbc4c3794d14b364f6fd2affa4e4358f4f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136296"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enable-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="61832-102">Включение контроля допуска звонков в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="61832-102">Enable call admission control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="61832-103">_**Последнее изменение темы:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="61832-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="61832-104">Чтобы политики пропускной способности сети вступили в силу, необходимо включить службу контроля допуска звонков (после настройки параметров сети для развертывания этой службы).</span><span class="sxs-lookup"><span data-stu-id="61832-104">After you have configured your network settings for call admission control deployment, you must enable CAC to put your bandwidth policies into effect.</span></span>

<span data-ttu-id="61832-105">Для получения дополнительных сведений обратитесь к документации по командной консоли Lync Server для следующих командлетов:</span><span class="sxs-lookup"><span data-stu-id="61832-105">For details, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="61832-106">Get — CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="61832-106">Get-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkConfiguration)

  - [<span data-ttu-id="61832-107">Set — CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="61832-107">Set-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkConfiguration)

  - [<span data-ttu-id="61832-108">Remove — CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="61832-108">Remove-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkConfiguration)

<div>

## <a name="to-enable-call-admission-control-by-using-management-shell"></a><span data-ttu-id="61832-109">Включение службы контроля допуска звонков с помощью командной консоли Lync Server</span><span class="sxs-lookup"><span data-stu-id="61832-109">To enable call admission control by using Management Shell</span></span>

1.  <span data-ttu-id="61832-110">Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="61832-110">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="61832-p101">Чтобы включить службу контроля допуска звонков в сети, выполните командлет Set-CsNetworkConfiguration. Пример:</span><span class="sxs-lookup"><span data-stu-id="61832-p101">Run the Set-CsNetworkConfiguration cmdlet to enable CAC in your network. For example, run:</span></span>
    
        Set-CsNetworkConfiguration -EnableBandwidthPolicyCheck 1
    
    <span data-ttu-id="61832-113">Чтобы отключить службу контроля допуска звонков в сети, выполните следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="61832-113">If you want to disable CAC in your network, run the following:</span></span>
    
        Set-CsNetworkConfiguration -EnableBandwidthPolicyCheck 0

</div>

<div>

## <a name="to-enable-call-admission-control-by-using-lync-server-control-panel"></a><span data-ttu-id="61832-114">Включение службы контроля допуска звонков с помощью панели управления Lync Server</span><span class="sxs-lookup"><span data-stu-id="61832-114">To enable call admission control by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="61832-115">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="61832-115">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="61832-116">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="61832-116">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="61832-117">В левой панели навигации щелкните **Network Configuration** (Параметры сети).</span><span class="sxs-lookup"><span data-stu-id="61832-117">In the left navigation bar, click **Network Configuration**.</span></span>

3.  <span data-ttu-id="61832-118">Нажмите кнопку навигации **Global** (Глобальные).</span><span class="sxs-lookup"><span data-stu-id="61832-118">Click the **Global** navigation button.</span></span>

4.  <span data-ttu-id="61832-119">Выберите **Global** (Глобальные) в списке и затем в меню **Edit** (Изменить) выберите **Show Details** (Показать сведения).</span><span class="sxs-lookup"><span data-stu-id="61832-119">Click **Global** in the list, and then select **Show Details** on the **Edit** menu.</span></span>

5.  <span data-ttu-id="61832-120">На странице **Edit Global Settings** (Изменение глобальных параметров) установите флажок **Enable call admission control** (Включить службу контроля допуска звонков).</span><span class="sxs-lookup"><span data-stu-id="61832-120">On the **Edit Global Settings** page, select the **Enable call admission control** check box.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="61832-121">Чтобы отключить службу контроля допуска звонков во всем развертывании, снимите этот флажок.</span><span class="sxs-lookup"><span data-stu-id="61832-121">If you want to disable call admission control throughout your deployment, clear this check box.</span></span>

    
    </div>

6.  <span data-ttu-id="61832-122">Щелкните **Commit** (Применить).</span><span class="sxs-lookup"><span data-stu-id="61832-122">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

