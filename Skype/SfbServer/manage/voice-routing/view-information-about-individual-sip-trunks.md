---
title: Просмотр сведений об отдельных магистральных магистральных каналах SIP в Skype для бизнеса Server
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
description: В Skype для бизнеса Server несколько магистральных каналов можно назначить одному шлюзу PSTN; Это означает, что шлюзы и магистрали не относятся к одному и тому же, а администраторы должны использовать командлет Get – CsTrunk для просмотра сведений об отдельной магистральной магистральной сети SIP.
ms.openlocfilehash: c5288e676f546e07504f4d8609fcea63913b6457
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048182"
---
# <a name="view-information-about-individual-sip-trunks-in-skype-for-business-server"></a><span data-ttu-id="498ab-103">Просмотр сведений об отдельных магистральных магистральных каналах SIP в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="498ab-103">View information about individual SIP trunks in Skype for Business Server</span></span>

<span data-ttu-id="498ab-104">В Skype для бизнеса Server несколько магистральных каналов можно назначить одному шлюзу PSTN; Это означает, что шлюзы и магистральные линии не относятся к одному и тому же, а администраторы должны использовать командлет [Get – CsTrunk](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunk) для просмотра сведений об отдельной магистральной магистральной сети SIP.</span><span class="sxs-lookup"><span data-stu-id="498ab-104">In Skype for Business Server, multiple trunks can be assigned to a single PSTN gateway; this means that gateways and trunks are not one and the same, and that administrators must use the [Get-CsTrunk](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunk) cmdlet to view information about an individual SIP trunk.</span></span>

<span data-ttu-id="498ab-105">Командлет Get-CsTrunk можно выполнить из командной консоли Skype для бизнеса Server или из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="498ab-105">The Get-CsTrunk cmdlet can be run either from the  Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span>

<span data-ttu-id="498ab-106">**Просмотр сведений обо всех магистральных магистральных каналах SIP**</span><span class="sxs-lookup"><span data-stu-id="498ab-106">**To view information for all your SIP trunks**</span></span>

<span data-ttu-id="498ab-107">Следующая команда возвращает сведения о всех магистралях SIP, используемых в организации.</span><span class="sxs-lookup"><span data-stu-id="498ab-107">The following command returns information about all the SIP trunks in use in your organization:</span></span>

`Get-CsTrunk`

<span data-ttu-id="498ab-108">**Просмотр сведений об определенной магистрали SIP**</span><span class="sxs-lookup"><span data-stu-id="498ab-108">**To view information for a specific SIP trunk**</span></span>

<span data-ttu-id="498ab-109">Эта команда возвращает сведения только о магистрали SIP с идентификатором PstnGateway:192.168.0.240:</span><span class="sxs-lookup"><span data-stu-id="498ab-109">This command returns information only for the SIP trunk with the Identity PstnGateway:192.168.0.240:</span></span>

`Get-CsTrunk -Identity "PstnGateway:192.168.0.240"`

<span data-ttu-id="498ab-110">**Просмотр сведений о всех магистралях SIP, назначенных пулу**</span><span class="sxs-lookup"><span data-stu-id="498ab-110">**Viewing Information for All the SIP Trunks Assigned to a Pool**</span></span>

<span data-ttu-id="498ab-111">В этом примере возвращаются сведения о всех магистралях SIP, назначенных пулу atl-cs-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="498ab-111">In this example, information is returned for all the SIP trunks assigned to the pool atl-cs-001.litwareinc.com:</span></span>

`Get-CsTrunk -PoolFqdn "atl-cs-001.litwareinc.com"`
