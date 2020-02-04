---
title: 'Lync Server 2013: Включение управления допуском звонков'
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
ms.openlocfilehash: 1776cc173d7ddec50aae34e8316844d14f67b009
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729359"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="ea611-102">Включение управления допуском звонков в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ea611-102">Enable call admission control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ea611-103">_**Тема последнего изменения:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="ea611-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="ea611-104">Чтобы политики пропускной способности сети вступили в силу, необходимо включить службу контроля допуска звонков (после настройки параметров сети для развертывания этой службы).</span><span class="sxs-lookup"><span data-stu-id="ea611-104">After you have configured your network settings for call admission control deployment, you must enable CAC to put your bandwidth policies into effect.</span></span>

<span data-ttu-id="ea611-105">Дополнительные сведения можно найти в документации по оболочке управления Lync Server для следующих командлетов:</span><span class="sxs-lookup"><span data-stu-id="ea611-105">For details, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="ea611-106">Get-Кснетворкконфигуратион</span><span class="sxs-lookup"><span data-stu-id="ea611-106">Get-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkConfiguration)

  - [<span data-ttu-id="ea611-107">Set-CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="ea611-107">Set-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkConfiguration)

  - [<span data-ttu-id="ea611-108">Remove-CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="ea611-108">Remove-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkConfiguration)

<div>

## <a name="to-enable-call-admission-control-by-using-management-shell"></a><span data-ttu-id="ea611-109">Включение управления допуском звонков с помощью оболочки управления</span><span class="sxs-lookup"><span data-stu-id="ea611-109">To enable call admission control by using Management Shell</span></span>

1.  <span data-ttu-id="ea611-110">Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="ea611-110">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="ea611-p101">Чтобы включить службу контроля допуска звонков в сети, выполните командлет Set-CsNetworkConfiguration. Пример:</span><span class="sxs-lookup"><span data-stu-id="ea611-p101">Run the Set-CsNetworkConfiguration cmdlet to enable CAC in your network. For example, run:</span></span>
    
        Set-CsNetworkConfiguration -EnableBandwidthPolicyCheck 1
    
    <span data-ttu-id="ea611-113">Чтобы отключить службу контроля допуска звонков в сети, выполните следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="ea611-113">If you want to disable CAC in your network, run the following:</span></span>
    
        Set-CsNetworkConfiguration -EnableBandwidthPolicyCheck 0

</div>

<div>

## <a name="to-enable-call-admission-control-by-using-lync-server-control-panel"></a><span data-ttu-id="ea611-114">Включение управления допуском звонков с помощью панели управления Lync Server</span><span class="sxs-lookup"><span data-stu-id="ea611-114">To enable call admission control by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="ea611-115">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ea611-115">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="ea611-116">Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="ea611-116">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="ea611-117">В левой области навигации щелкните элемент **Конфигурация сети**.</span><span class="sxs-lookup"><span data-stu-id="ea611-117">In the left navigation bar, click **Network Configuration**.</span></span>

3.  <span data-ttu-id="ea611-118">Нажмите кнопку навигации **Глобальные**.</span><span class="sxs-lookup"><span data-stu-id="ea611-118">Click the **Global** navigation button.</span></span>

4.  <span data-ttu-id="ea611-119">Выберите **Глобальные** в списке и затем в меню **Изменить** выберите **Показать сведения**.</span><span class="sxs-lookup"><span data-stu-id="ea611-119">Click **Global** in the list, and then select **Show Details** on the **Edit** menu.</span></span>

5.  <span data-ttu-id="ea611-120">На странице **Изменение глобальных параметров** установите флажок **Включить контроль допуска звонков**.</span><span class="sxs-lookup"><span data-stu-id="ea611-120">On the **Edit Global Settings** page, select the **Enable call admission control** check box.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ea611-121">Чтобы отключить службу контроля допуска звонков во всем развертывании, снимите этот флажок.</span><span class="sxs-lookup"><span data-stu-id="ea611-121">If you want to disable call admission control throughout your deployment, clear this check box.</span></span>

    
    </div>

6.  <span data-ttu-id="ea611-122">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="ea611-122">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

