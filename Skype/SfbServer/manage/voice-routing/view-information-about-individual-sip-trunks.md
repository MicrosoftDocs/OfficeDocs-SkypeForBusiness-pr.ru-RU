---
title: Просмотр сведений об отдельных магистралях SIP в Скайп для Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: В Скайп для Business Server несколько магистралей можно назначить один шлюз ТСОП; Это означает, что шлюзов и магистральных линий связи не одной и той же, что администраторы должны использовать командлет Get-CsTrunk для просмотра сведений об отдельных канала SIP.
ms.openlocfilehash: 4c57bdfb8671c8aee3f0bb3dbc48fdc5cb920b07
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30885179"
---
# <a name="view-information-about-individual-sip-trunks-in-skype-for-business-server"></a><span data-ttu-id="05bfe-103">Просмотр сведений об отдельных магистралях SIP в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="05bfe-103">View information about individual SIP trunks in Skype for Business Server</span></span>

<span data-ttu-id="05bfe-104">В Скайп для Business Server несколько магистралей можно назначить один шлюз ТСОП; Это означает, что шлюзов и магистральных линий связи не одной и той же и, что администраторы должны использовать командлет [Get-CsTrunk](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsTrunk) для просмотра сведений об отдельных канала SIP.</span><span class="sxs-lookup"><span data-stu-id="05bfe-104">In Skype for Business Server, multiple trunks can be assigned to a single PSTN gateway; this means that gateways and trunks are not one and the same, and that administrators must use the [Get-CsTrunk](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsTrunk) cmdlet to view information about an individual SIP trunk.</span></span>

<span data-ttu-id="05bfe-105">Командлет Get-CsTrunk можно запустить из Скайп для консоли Business Server или из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="05bfe-105">The Get-CsTrunk cmdlet can be run either from the  Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span>

<span data-ttu-id="05bfe-106">**Просмотр сведений о всех магистралях SIP**</span><span class="sxs-lookup"><span data-stu-id="05bfe-106">**To view information for all your SIP trunks**</span></span>

<span data-ttu-id="05bfe-107">Следующая команда возвращает сведения о всех магистралях SIP, используемых в организации.</span><span class="sxs-lookup"><span data-stu-id="05bfe-107">The following command returns information about all the SIP trunks in use in your organization:</span></span>

`Get-CsTrunk`

<span data-ttu-id="05bfe-108">**Просмотр сведений об определенной магистрали SIP**</span><span class="sxs-lookup"><span data-stu-id="05bfe-108">**To view information for a specific SIP trunk**</span></span>

<span data-ttu-id="05bfe-109">Эта команда возвращает сведения только о магистрали SIP с идентификатором PstnGateway:192.168.0.240:</span><span class="sxs-lookup"><span data-stu-id="05bfe-109">This command returns information only for the SIP trunk with the Identity PstnGateway:192.168.0.240:</span></span>

`Get-CsTrunk -Identity "PstnGateway:192.168.0.240"`

<span data-ttu-id="05bfe-110">**Просмотр сведений о всех магистралях SIP, назначенных пулу**</span><span class="sxs-lookup"><span data-stu-id="05bfe-110">**Viewing Information for All the SIP Trunks Assigned to a Pool**</span></span>

<span data-ttu-id="05bfe-111">В этом примере возвращаются сведения о всех магистралях SIP, назначенных пулу atl-cs-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="05bfe-111">In this example, information is returned for all the SIP trunks assigned to the pool atl-cs-001.litwareinc.com:</span></span>

`Get-CsTrunk -PoolFqdn "atl-cs-001.litwareinc.com"`
