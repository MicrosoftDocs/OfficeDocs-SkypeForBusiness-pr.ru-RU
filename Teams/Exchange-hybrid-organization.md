---
title: Настройка гибридной организации для работы с Microsoft Teams
author: dstrome
ms.author: dstrome
manager: serdars
ms.date: 09/25/2017
ms.topic: article
audience: admin
ms.service: msteams
ms.reviewer: dstrome
description: Сведения о настройке гибридной организации для работы с Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: bd18381a8d889a1cebad04234e56bf11def9197e
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2019
ms.locfileid: "37563897"
---
<a name="configure-an-exchange-hybrid-organization-for-use-with-microsoft-teams"></a><span data-ttu-id="c77e2-103">Настройка гибридной организации для работы с Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c77e2-103">Configure an Exchange hybrid organization for use with Microsoft Teams</span></span>
======================================================================

<span data-ttu-id="c77e2-104">В общем случае настраивать какие-либо функции Exchange Online для работы с Microsoft Teams не требуется.</span><span class="sxs-lookup"><span data-stu-id="c77e2-104">Generally, you should not have to configure any Exchange Online functionality for use with Microsoft Teams.</span></span> <span data-ttu-id="c77e2-105">Однако в гибридной среде Exchange нужно принять определенные меры, чтобы синхронизировать членства в группах между Exchange Server (в локальной среде) и Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="c77e2-105">However, for Exchange Hybrid scenarios, there are steps necessary to ensure Group memberships are synchronized between Exchange Server (on-premises) and Exchange Online.</span></span> <span data-ttu-id="c77e2-106">Это включает возможность включения функции обратной записи в Azure AD Connect вместе с различными сценариями инициализации: [Настройка групп Office 365 с помощью локального гибридного развертывания Exchange](https://go.microsoft.com/fwlink/?linkid=854389).</span><span class="sxs-lookup"><span data-stu-id="c77e2-106">This involves enablement of Group Writeback functionality in Azure AD Connect along with various initialization scripts: [Configure Office 365 Groups with on-premises Exchange hybrid](https://go.microsoft.com/fwlink/?linkid=854389).</span></span>
