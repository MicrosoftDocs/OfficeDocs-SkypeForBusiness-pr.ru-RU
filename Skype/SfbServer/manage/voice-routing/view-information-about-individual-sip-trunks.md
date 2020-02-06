---
title: Просмотр сведений об отдельных магистральных линиях SIP в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: В Skype для бизнеса Server для одного шлюза PSTN может быть назначено несколько каналов. Это означает, что шлюзы и магистральные линии не являются одними и теми же, а администраторы должны использовать командлет Get-Кструнк для просмотра сведений о отдельной внешней магистрали SIP.
ms.openlocfilehash: d7db7eebfc409b0f79bd562606368d434ba47f0c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816928"
---
# <a name="view-information-about-individual-sip-trunks-in-skype-for-business-server"></a><span data-ttu-id="bbf18-103">Просмотр сведений об отдельных магистральных линиях SIP в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="bbf18-103">View information about individual SIP trunks in Skype for Business Server</span></span>

<span data-ttu-id="bbf18-104">В Skype для бизнеса Server для одного шлюза PSTN может быть назначено несколько каналов. Это означает, что шлюзы и магистральные линии — это не один и тот же, и что администраторы должны использовать командлет [Get-кструнк](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsTrunk) для просмотра сведений о отдельной внешней магистрали SIP.</span><span class="sxs-lookup"><span data-stu-id="bbf18-104">In Skype for Business Server, multiple trunks can be assigned to a single PSTN gateway; this means that gateways and trunks are not one and the same, and that administrators must use the [Get-CsTrunk](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsTrunk) cmdlet to view information about an individual SIP trunk.</span></span>

<span data-ttu-id="bbf18-105">Командлет Get-Кструнк можно выполнить либо из командной консоли Skype для бизнеса Server, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bbf18-105">The Get-CsTrunk cmdlet can be run either from the  Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span>

<span data-ttu-id="bbf18-106">**Просмотр сведений о всех магистралях SIP**</span><span class="sxs-lookup"><span data-stu-id="bbf18-106">**To view information for all your SIP trunks**</span></span>

<span data-ttu-id="bbf18-107">Следующая команда возвращает сведения о всех магистралях SIP, используемых в организации.</span><span class="sxs-lookup"><span data-stu-id="bbf18-107">The following command returns information about all the SIP trunks in use in your organization:</span></span>

`Get-CsTrunk`

<span data-ttu-id="bbf18-108">**Просмотр сведений об определенной магистрали SIP**</span><span class="sxs-lookup"><span data-stu-id="bbf18-108">**To view information for a specific SIP trunk**</span></span>

<span data-ttu-id="bbf18-109">Эта команда возвращает сведения только о магистрали SIP с идентификатором PstnGateway:192.168.0.240:</span><span class="sxs-lookup"><span data-stu-id="bbf18-109">This command returns information only for the SIP trunk with the Identity PstnGateway:192.168.0.240:</span></span>

`Get-CsTrunk -Identity "PstnGateway:192.168.0.240"`

<span data-ttu-id="bbf18-110">**Просмотр сведений для всех магистральных каналов SIP, назначенных пулу**</span><span class="sxs-lookup"><span data-stu-id="bbf18-110">**Viewing Information for All the SIP Trunks Assigned to a Pool**</span></span>

<span data-ttu-id="bbf18-111">В этом примере возвращаются сведения о всех магистралях SIP, назначенных пулу atl-cs-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="bbf18-111">In this example, information is returned for all the SIP trunks assigned to the pool atl-cs-001.litwareinc.com:</span></span>

`Get-CsTrunk -PoolFqdn "atl-cs-001.litwareinc.com"`
