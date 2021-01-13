---
title: Просмотр сведений о сетевом интерфейсе
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Сведения о сетевом интерфейсе можно просмотреть с помощью Windows PowerShell и Get-CsNetworkInterface управления. Вы можете запустить этот командлет из командной консоли Skype для бизнеса Server или из удаленного сеанса Windows PowerShell.
ms.openlocfilehash: 26876fe6f7d8ac6989c88e8247d28a72e78ff903
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815139"
---
# <a name="viewing-network-interface-information-in-skype-for-business-server"></a><span data-ttu-id="5d896-104">Просмотр сведений о сетевом интерфейсе в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="5d896-104">Viewing network interface information in Skype for Business Server</span></span>

<span data-ttu-id="5d896-105">Сведения о сетевом интерфейсе можно просмотреть с Windows PowerShell **командлета Get-CsNetworkInterface.**</span><span class="sxs-lookup"><span data-stu-id="5d896-105">You can view network interface information by using Windows PowerShell and the **Get-CsNetworkInterface** cmdlet.</span></span> <span data-ttu-id="5d896-106">Вы можете запустить этот командлет из командной консоли Skype для бизнеса Server или из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5d896-106">You can run this cmdlet from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

## <a name="to-view-network-interface-information"></a><span data-ttu-id="5d896-107">Просмотр сведений о сетевом интерфейсе</span><span class="sxs-lookup"><span data-stu-id="5d896-107">To view network interface information</span></span>

  - <span data-ttu-id="5d896-108">Чтобы просмотреть сведения о сетевом интерфейсе, введите следующую команду в командной оболочке Skype для бизнеса Server и нажмите ввод:</span><span class="sxs-lookup"><span data-stu-id="5d896-108">To view network interface information, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsNetworkInterface
    
    <span data-ttu-id="5d896-109">Эта команда возвращает сведения, подобные приведенным ниже, для каждого сетевого интерфейса:</span><span class="sxs-lookup"><span data-stu-id="5d896-109">This command returns information similar to the following for each network interface:</span></span>
    
        Identity              : dc.vdomain.com/Primary/1
        ComputerFqdn          : dc.vdomain.com
        IPAddress             : 0.0.0.0
        IPv6Address           :
        Interface             : Primary
        InterfaceNumber       : 1
        ConfiguredFqdn        :
        ConfiguredIPAddress   :
        ConfiguredIPv6Address :
    
    <span data-ttu-id="5d896-110">Дополнительные сведения см. в разделе [Get-CsNetworkInterface](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterface).</span><span class="sxs-lookup"><span data-stu-id="5d896-110">For details, see [Get-CsNetworkInterface](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterface).</span></span>


