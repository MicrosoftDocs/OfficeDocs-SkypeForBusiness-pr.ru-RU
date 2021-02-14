---
title: Просмотр сведений об отдельных магистрали SIP в Skype для бизнеса Server
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
description: В Skype для бизнеса Server одному шлюзу STN может быть назначено несколько магистральных магистральных звонков; это означает, что шлюзы и магистрали не являются одинаковыми, и администраторы должны использовать Get-CsTrunk для просмотра сведений об отдельной магистрали SIP.
ms.openlocfilehash: b49846ed7244dec2f51f51f262becc440662026c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826179"
---
# <a name="view-information-about-individual-sip-trunks-in-skype-for-business-server"></a><span data-ttu-id="d76ea-103">Просмотр сведений об отдельных магистрали SIP в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="d76ea-103">View information about individual SIP trunks in Skype for Business Server</span></span>

<span data-ttu-id="d76ea-104">В Skype для бизнеса Server одному шлюзу STN может быть назначено несколько магистральных магистральных звонков; это означает, что шлюзы и магистрали не являются одинаковыми и администраторы должны использовать для просмотра сведений об отдельной магистрали SIP с помощью [get-CsTrunk.](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunk)</span><span class="sxs-lookup"><span data-stu-id="d76ea-104">In Skype for Business Server, multiple trunks can be assigned to a single PSTN gateway; this means that gateways and trunks are not one and the same, and that administrators must use the [Get-CsTrunk](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunk) cmdlet to view information about an individual SIP trunk.</span></span>

<span data-ttu-id="d76ea-105">The Get-CsTrunk cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d76ea-105">The Get-CsTrunk cmdlet can be run either from the  Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span>

<span data-ttu-id="d76ea-106">**Просмотр сведений о всех магистрали SIP**</span><span class="sxs-lookup"><span data-stu-id="d76ea-106">**To view information for all your SIP trunks**</span></span>

<span data-ttu-id="d76ea-107">Следующая команда возвращает сведения о всех магистралях SIP, используемых в организации.</span><span class="sxs-lookup"><span data-stu-id="d76ea-107">The following command returns information about all the SIP trunks in use in your organization:</span></span>

`Get-CsTrunk`

<span data-ttu-id="d76ea-108">**Просмотр сведений для определенной магистрали SIP**</span><span class="sxs-lookup"><span data-stu-id="d76ea-108">**To view information for a specific SIP trunk**</span></span>

<span data-ttu-id="d76ea-109">Эта команда возвращает сведения только о магистрали SIP с идентификатором PstnGateway:192.168.0.240:</span><span class="sxs-lookup"><span data-stu-id="d76ea-109">This command returns information only for the SIP trunk with the Identity PstnGateway:192.168.0.240:</span></span>

`Get-CsTrunk -Identity "PstnGateway:192.168.0.240"`

<span data-ttu-id="d76ea-110">**Просмотр сведений о всех магистралях SIP, назначенных пулу**</span><span class="sxs-lookup"><span data-stu-id="d76ea-110">**Viewing Information for All the SIP Trunks Assigned to a Pool**</span></span>

<span data-ttu-id="d76ea-111">В этом примере возвращаются сведения о всех магистралях SIP, назначенных пулу atl-cs-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="d76ea-111">In this example, information is returned for all the SIP trunks assigned to the pool atl-cs-001.litwareinc.com:</span></span>

`Get-CsTrunk -PoolFqdn "atl-cs-001.litwareinc.com"`
