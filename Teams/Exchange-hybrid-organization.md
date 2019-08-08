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
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 68b2fee13668db8ba3986302d58bc16b0fa89080
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/07/2019
ms.locfileid: "36235205"
---
<a name="configure-an-exchange-hybrid-organization-for-use-with-microsoft-teams"></a><span data-ttu-id="de105-103">Настройка гибридной организации для работы с Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="de105-103">Configure an Exchange hybrid organization for use with Microsoft Teams</span></span>
======================================================================

<span data-ttu-id="de105-104">В общем случае настраивать какие-либо функции Exchange Online для работы с Microsoft Teams не требуется.</span><span class="sxs-lookup"><span data-stu-id="de105-104">Generally, you should not have to configure any Exchange Online functionality for use with Microsoft Teams.</span></span> <span data-ttu-id="de105-105">Однако в гибридной среде Exchange нужно принять определенные меры, чтобы синхронизировать членства в группах между Exchange Server (в локальной среде) и Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="de105-105">However, for Exchange Hybrid scenarios, there are steps necessary to ensure Group memberships are synchronized between Exchange Server (on-premises) and Exchange Online.</span></span> <span data-ttu-id="de105-106">Это включает возможность включения функции обратной записи в Azure AD Connect вместе с различными сценариями инициализации: [Настройка групп Office 365 с помощью локального гибридного развертывания Exchange](https://go.microsoft.com/fwlink/?linkid=854389).</span><span class="sxs-lookup"><span data-stu-id="de105-106">This involves enablement of Group Writeback functionality in Azure AD Connect along with various initialization scripts: [Configure Office 365 Groups with on-premises Exchange hybrid](https://go.microsoft.com/fwlink/?linkid=854389).</span></span>
