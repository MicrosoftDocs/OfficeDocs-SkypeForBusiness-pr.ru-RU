---
title: Просмотр сведений о сетевом интерфейсе
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Можно просмотреть сведений о сетевом интерфейсе с помощью командлета Get-CsNetworkInterface и Windows PowerShell. Этот командлет можно запустить из Скайп для консоли Business Server или из удаленного сеанса Windows PowerShell.
ms.openlocfilehash: df4424e33cb42f3c1b2311cc822c762a2c4878f1
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30888031"
---
# <a name="viewing-network-interface-information-in-skype-for-business-server"></a><span data-ttu-id="0d61a-104">Просмотр сведений о сетевом интерфейсе в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="0d61a-104">Viewing network interface information in Skype for Business Server</span></span>

<span data-ttu-id="0d61a-105">Можно просмотреть сведений о сетевом интерфейсе с помощью командлета **Get-CsNetworkInterface** и Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0d61a-105">You can view network interface information by using Windows PowerShell and the **Get-CsNetworkInterface** cmdlet.</span></span> <span data-ttu-id="0d61a-106">Этот командлет можно запустить из Скайп для консоли Business Server или из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0d61a-106">You can run this cmdlet from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

## <a name="to-view-network-interface-information"></a><span data-ttu-id="0d61a-107">Для просмотра сведений о сетевом интерфейсе</span><span class="sxs-lookup"><span data-stu-id="0d61a-107">To view network interface information</span></span>

  - <span data-ttu-id="0d61a-108">Для просмотра сведений о сетевом интерфейсе, введите следующую команду в Скайп для консоли Business Server и нажмите клавишу ВВОД:</span><span class="sxs-lookup"><span data-stu-id="0d61a-108">To view network interface information, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsNetworkInterface
    
    <span data-ttu-id="0d61a-109">Эта команда возвращает сведения, подобные приведенным ниже, для каждого сетевого интерфейса:</span><span class="sxs-lookup"><span data-stu-id="0d61a-109">This command returns information similar to the following for each network interface:</span></span>
    
        Identity              : dc.vdomain.com/Primary/1
        ComputerFqdn          : dc.vdomain.com
        IPAddress             : 0.0.0.0
        IPv6Address           :
        Interface             : Primary
        InterfaceNumber       : 1
        ConfiguredFqdn        :
        ConfiguredIPAddress   :
        ConfiguredIPv6Address :
    
    <span data-ttu-id="0d61a-110">Дополнительные сведения см [Get-CsNetworkInterface](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterface).</span><span class="sxs-lookup"><span data-stu-id="0d61a-110">For details, see [Get-CsNetworkInterface](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterface).</span></span>


