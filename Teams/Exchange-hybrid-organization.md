---
title: "Настройка гибридной организации для работы с Microsoft Teams | Служба поддержки Майкрософт"
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "Сведения о настройке гибридной организации для работы с Microsoft Teams."
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: 9a046dd3eb2c36e84da913c2aad8b5606f019b04
ms.sourcegitcommit: 2e557e90b4e30fe99ff9df3897b8e54f38ea2f2e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2017
---
<a name="configure-an-exchange-hybrid-organization-for-use-with-microsoft-teams"></a><span data-ttu-id="2dc7d-103">Настройка гибридной организации для работы с Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2dc7d-103">Configure an Exchange hybrid organization for use with Microsoft Teams</span></span>
======================================================================

<span data-ttu-id="2dc7d-104">В общем случае настраивать какие-либо функции Exchange Online для работы с Microsoft Teams не требуется.</span><span class="sxs-lookup"><span data-stu-id="2dc7d-104">Generally, you should not have to configure any Exchange Online functionality for use with Microsoft Teams.</span></span> <span data-ttu-id="2dc7d-105">Однако в гибридной среде Exchange нужно принять определенные меры, чтобы синхронизировать членства в группах между Exchange Server (в локальной среде) и Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="2dc7d-105">However, for Exchange Hybrid scenarios, there are steps necessary to ensure Group memberships are synchronized between Exchange Server (on-premises) and Exchange Online.</span></span> <span data-ttu-id="2dc7d-106">Эта процедура включает в себя активацию обратной записи групп в Azure AD Connect, а также выполнение различных сценариев инициализации: [Настройка Групп Office 365 для локальной гибридной среды Exchange](https://go.microsoft.com/fwlink/?linkid=854389)</span><span class="sxs-lookup"><span data-stu-id="2dc7d-106">This involves enablement of Group Writeback functionality in Azure AD Connect along with various initialization scripts: [Configure Office 365 Groups with on-premises Exchange hybrid](https://go.microsoft.com/fwlink/?linkid=854389)</span></span>
