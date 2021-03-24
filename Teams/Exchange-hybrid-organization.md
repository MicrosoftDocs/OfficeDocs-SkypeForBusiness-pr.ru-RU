---
title: Настройка гибридной организации Exchange
author: dstrome
ms.author: dstrome
manager: serdars
ms.date: 09/25/2017
ms.topic: article
audience: admin
ms.service: msteams
ms.reviewer: dstrome
description: Узнайте, как настроить гибридную организацию Exchange для использования с Microsoft Teams, чтобы обеспечить синхронизацию членства в группах.
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 90250b3d3f3593990d356843bebea324060d6f8b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094611"
---
<a name="configure-an-exchange-hybrid-organization-for-use-with-microsoft-teams"></a><span data-ttu-id="b74f4-103">Настройка гибридной организации для работы с Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b74f4-103">Configure an Exchange hybrid organization for use with Microsoft Teams</span></span>
======================================================================

<span data-ttu-id="b74f4-104">В общем случае настраивать какие-либо функции Exchange Online для работы с Microsoft Teams не требуется.</span><span class="sxs-lookup"><span data-stu-id="b74f4-104">Generally, you should not have to configure any Exchange Online functionality for use with Microsoft Teams.</span></span> <span data-ttu-id="b74f4-105">Однако в гибридной среде Exchange нужно принять определенные меры, чтобы синхронизировать членства в группах между Exchange Server (в локальной среде) и Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="b74f4-105">However, for Exchange Hybrid scenarios, there are steps necessary to ensure Group memberships are synchronized between Exchange Server (on-premises) and Exchange Online.</span></span> <span data-ttu-id="b74f4-106">Это включает функцию записи групп в Azure AD Connect, а также различные сценарии инициализации: настройка групп [Microsoft 365](/exchange/hybrid-deployment/set-up-microsoft-365-groups)с использованием локального гибридного решения Exchange.</span><span class="sxs-lookup"><span data-stu-id="b74f4-106">This involves enablement of Group Writeback functionality in Azure AD Connect along with various initialization scripts: [Configure Microsoft 365 Groups with on-premises Exchange hybrid](/exchange/hybrid-deployment/set-up-microsoft-365-groups).</span></span>