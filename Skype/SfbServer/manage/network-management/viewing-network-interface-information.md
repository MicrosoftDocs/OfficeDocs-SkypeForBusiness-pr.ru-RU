---
title: Просмотр сведений о сетевом интерфейсе
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Вы можете просматривать сведения о сетевом интерфейсе с помощью Windows PowerShell и командлета Get-Кснетворкинтерфаце. Вы можете запустить этот командлет из командной консоли Skype для бизнеса Server или из удаленного сеанса Windows PowerShell.
ms.openlocfilehash: ac0df8450b938a377e1325f9c3179b4650b31bdf
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279391"
---
# <a name="viewing-network-interface-information-in-skype-for-business-server"></a><span data-ttu-id="95756-104">Просмотр сведений о сетевом интерфейсе в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="95756-104">Viewing network interface information in Skype for Business Server</span></span>

<span data-ttu-id="95756-105">Вы можете просматривать сведения о сетевом интерфейсе с помощью Windows PowerShell и командлета **Get-кснетворкинтерфаце** .</span><span class="sxs-lookup"><span data-stu-id="95756-105">You can view network interface information by using Windows PowerShell and the **Get-CsNetworkInterface** cmdlet.</span></span> <span data-ttu-id="95756-106">Вы можете запустить этот командлет из командной консоли Skype для бизнеса Server или из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="95756-106">You can run this cmdlet from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

## <a name="to-view-network-interface-information"></a><span data-ttu-id="95756-107">Просмотр сведений о сетевом интерфейсе</span><span class="sxs-lookup"><span data-stu-id="95756-107">To view network interface information</span></span>

  - <span data-ttu-id="95756-108">Чтобы просмотреть сведения о сетевом интерфейсе, введите в командной консоли Skype для Business Server указанную ниже команду и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="95756-108">To view network interface information, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsNetworkInterface
    
    <span data-ttu-id="95756-109">Эта команда возвращает сведения о каждом сетевом интерфейсе, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="95756-109">This command returns information similar to the following for each network interface:</span></span>
    
        Identity              : dc.vdomain.com/Primary/1
        ComputerFqdn          : dc.vdomain.com
        IPAddress             : 0.0.0.0
        IPv6Address           :
        Interface             : Primary
        InterfaceNumber       : 1
        ConfiguredFqdn        :
        ConfiguredIPAddress   :
        ConfiguredIPv6Address :
    
    <span data-ttu-id="95756-110">Подробности можно найти в [статьях Get-кснетворкинтерфаце](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterface).</span><span class="sxs-lookup"><span data-stu-id="95756-110">For details, see [Get-CsNetworkInterface](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterface).</span></span>


