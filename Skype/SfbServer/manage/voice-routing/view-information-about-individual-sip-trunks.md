---
title: Просмотр сведений об отдельных магистральных серверах SIP в Skype для бизнеса Server
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
description: В Skype для бизнеса Server несколько магистральных серверов могут быть назначены одному шлюзу PSTN; это означает, что шлюзы и магистрали не одно и то же, и администраторы должны использовать Get-CsTrunk для просмотра сведений об отдельном стволе SIP.
ms.openlocfilehash: eebba2982a6f574ca2af99609f19ba5426139acb
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103005"
---
# <a name="view-information-about-individual-sip-trunks-in-skype-for-business-server"></a><span data-ttu-id="6b3cc-103">Просмотр сведений об отдельных магистральных серверах SIP в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="6b3cc-103">View information about individual SIP trunks in Skype for Business Server</span></span>

<span data-ttu-id="6b3cc-104">В Skype для бизнеса Server несколько магистральных серверов могут быть назначены одному шлюзу PSTN; это означает, что шлюзы и магистрали не одно и то же, и администраторы должны использовать [cmdlet Get-CsTrunk](/powershell/module/skype/Get-CsTrunk) для просмотра сведений об отдельном магистрали SIP.</span><span class="sxs-lookup"><span data-stu-id="6b3cc-104">In Skype for Business Server, multiple trunks can be assigned to a single PSTN gateway; this means that gateways and trunks are not one and the same, and that administrators must use the [Get-CsTrunk](/powershell/module/skype/Get-CsTrunk) cmdlet to view information about an individual SIP trunk.</span></span>

<span data-ttu-id="6b3cc-105">Этот Get-CsTrunk можно запускать из оболочки управления Skype для бизнес-серверов или удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6b3cc-105">The Get-CsTrunk cmdlet can be run either from the  Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span>

<span data-ttu-id="6b3cc-106">**Просмотр сведений для всех магистральных SIP**</span><span class="sxs-lookup"><span data-stu-id="6b3cc-106">**To view information for all your SIP trunks**</span></span>

<span data-ttu-id="6b3cc-107">Следующая команда возвращает сведения о всех магистралях SIP, используемых в организации.</span><span class="sxs-lookup"><span data-stu-id="6b3cc-107">The following command returns information about all the SIP trunks in use in your organization:</span></span>

`Get-CsTrunk`

<span data-ttu-id="6b3cc-108">**Просмотр сведений для определенного магистрали SIP**</span><span class="sxs-lookup"><span data-stu-id="6b3cc-108">**To view information for a specific SIP trunk**</span></span>

<span data-ttu-id="6b3cc-109">Эта команда возвращает сведения только о магистрали SIP с идентификатором PstnGateway:192.168.0.240:</span><span class="sxs-lookup"><span data-stu-id="6b3cc-109">This command returns information only for the SIP trunk with the Identity PstnGateway:192.168.0.240:</span></span>

`Get-CsTrunk -Identity "PstnGateway:192.168.0.240"`

<span data-ttu-id="6b3cc-110">**Просмотр сведений о всех магистралях SIP, назначенных пулу**</span><span class="sxs-lookup"><span data-stu-id="6b3cc-110">**Viewing Information for All the SIP Trunks Assigned to a Pool**</span></span>

<span data-ttu-id="6b3cc-111">В этом примере возвращаются сведения о всех магистралях SIP, назначенных пулу atl-cs-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="6b3cc-111">In this example, information is returned for all the SIP trunks assigned to the pool atl-cs-001.litwareinc.com:</span></span>

`Get-CsTrunk -PoolFqdn "atl-cs-001.litwareinc.com"`