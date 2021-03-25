---
title: Настройка собрания без ПИН-кода в Skype для бизнеса Server
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
ms.assetid: c21e8861-bb75-45e8-8485-38daa3b8121c
description: Сводка. Сведения о настройке параметра присоединиться к собранию без ПИН-кода в Skype для бизнеса Server.
ms.openlocfilehash: 76a2fb401c684e0eb685b733cb1b0a63ecbd9907
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119398"
---
# <a name="configure-pin-less-meeting-join-in-skype-for-business-server"></a><span data-ttu-id="a148c-103">Настройка собрания без ПИН-кода в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="a148c-103">Configure PIN-less meeting join in Skype for Business Server</span></span>
 
<span data-ttu-id="a148c-104">**Сводка:** Узнайте, как настроить параметр присоединиться к собранию без ПИН-кода в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="a148c-104">**Summary:** Learn how to configure the PIN-less meeting join option in Skype for Business Server.</span></span>
  
<span data-ttu-id="a148c-105">Когда звонивая по телефону пытается присоединиться к собранию, служба конференции автосекретарь (CAA) помещает вызываемого в удерживаемую ручку, которая отличается от службы &#x2014;, если телеведуарь еще не на вызове, а звонивщик не вошел в ПИН-код лидера.</span><span class="sxs-lookup"><span data-stu-id="a148c-105">When a dial-in caller attempts to join a meeting, the Conference Auto Attendant (CAA) service places the caller in a holding pen that is different from the Lobby &#x2014; if a presenter is not already on a call, and the dial-in caller has not entered a leader PIN.</span></span> <span data-ttu-id="a148c-106">Возможность присоединиться к собранию без ПИН-кода позволяет звонителям присоединиться к собранию, не вступая в ПИН-код лидера, даже если они являются первым лицом на вызове.</span><span class="sxs-lookup"><span data-stu-id="a148c-106">The PIN-less meeting join option allows dial-in callers to join a meeting without entering a leader PIN even if they are the first person on a call.</span></span> 
  
<span data-ttu-id="a148c-107">При настройке этой функции следует помнить следующее:</span><span class="sxs-lookup"><span data-stu-id="a148c-107">Keep the following in mind when configuring this feature:</span></span>
  
- <span data-ttu-id="a148c-108">Применяется только к закрытым собраниям.</span><span class="sxs-lookup"><span data-stu-id="a148c-108">Applies to private meetings only.</span></span>
    
- <span data-ttu-id="a148c-109">Позволяет вызывателям ТСОП находиться на закрытых собраниях без присутствия пользователей с проверкой подлинности.</span><span class="sxs-lookup"><span data-stu-id="a148c-109">Allows PSTN callers to stay in private meetings without the presence of authenticated users.</span></span>
    
- <span data-ttu-id="a148c-110">После изменения параметра он применяется ко всем существующим и новым закрытым собраниям.</span><span class="sxs-lookup"><span data-stu-id="a148c-110">After the setting is changed, it applies to all existing and new private meetings.</span></span>
    
- <span data-ttu-id="a148c-111">Можно включить на сайте организатора или на глобальном уровне.</span><span class="sxs-lookup"><span data-stu-id="a148c-111">Can be enabled either at the site of the organizer or at the global level.</span></span>
    
- <span data-ttu-id="a148c-112">Параметры, которые могут обойти вестибюль, можно задать для любого из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="a148c-112">Options for who can bypass the lobby can be set for either of the following:</span></span> 
    
  - <span data-ttu-id="a148c-113">**Все, кто из моей Организации с вызывателями, получают непосредственно**</span><span class="sxs-lookup"><span data-stu-id="a148c-113">**Anyone from my Organization with Callers get in directly**</span></span>
    
  - <span data-ttu-id="a148c-114">**Все (без ограничений) с вызывателями получают** непосредственно (это параметр по умолчанию.)</span><span class="sxs-lookup"><span data-stu-id="a148c-114">**Anyone (no restrictions) with Callers get in directly** (This is the default setting.)</span></span>
    
- <span data-ttu-id="a148c-115">При настройке, чтобы включить pin-код, служба CAA по-прежнему подсказываю пин-код лидера.</span><span class="sxs-lookup"><span data-stu-id="a148c-115">When configured to enable PIN-less join, the CAA service still prompts for a leader PIN.</span></span> <span data-ttu-id="a148c-116">Пользователи могут присоединиться к собранию вне зависимости от того, вошел ПИН-код или нет.</span><span class="sxs-lookup"><span data-stu-id="a148c-116">Users can join the meeting whether or not a PIN is entered.</span></span> <span data-ttu-id="a148c-117">Однако сохранение возможности ввода ПИН-кода лидера позволяет вызываемой в диалоговом окантовке проверить подлинность в качестве лидера и при необходимости управлять собранием.</span><span class="sxs-lookup"><span data-stu-id="a148c-117">However, retaining the ability to enter a leader PIN allows a dial-in caller to authenticate as a leader and manage the meeting if necessary.</span></span>
    
## <a name="configure-pin-less-meeting-join"></a><span data-ttu-id="a148c-118">Настройка присоединиться к собранию без ПИН-кода</span><span class="sxs-lookup"><span data-stu-id="a148c-118">Configure PIN-less meeting join</span></span>

<span data-ttu-id="a148c-119">Чтобы включить участие в собраниях без ПИН-кода для пользователей, используйте комлет [Set-CsDialInConferencingConfiguration](/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps) с параметром AllowAnonymousPstnActivation следующим образом:</span><span class="sxs-lookup"><span data-stu-id="a148c-119">To enable PIN-less meeting join for your users, use the [Set-CsDialInConferencingConfiguration](/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps) cmdlet with the AllowAnonymousPstnActivation parameter as follows:</span></span>
  
```PowerShell
Set-CsDialInConferencingConfiguration -Identity  < global or site:sitename>  -AllowAnonymousPstnActivation $True
```

<span data-ttu-id="a148c-120">Например, следующая команда позволяет присоединиться к собранию без ПИН-кода для сайта Redmond:</span><span class="sxs-lookup"><span data-stu-id="a148c-120">For example, the following command enables PIN-less meeting join for the site Redmond:</span></span>
  
```PowerShell
Set-CsDialInConferencingConfiguration -Identity site:Redmond -AllowAnonymousPstnActivation $True
```

<span data-ttu-id="a148c-121">В целях безопасности при включенном включаемом собрании без ПИН-кода может потребоваться запретить анонимным пользователям звонить, обеспечив, чтобы значение ConferencingPolicy было установлено следующим образом:</span><span class="sxs-lookup"><span data-stu-id="a148c-121">For security purposes, when PIN-less meeting join is turned on, you might want to restrict anonymous users from dialing out by ensuring the ConferencingPolicy is set as follows:</span></span>
  
```PowerShell
Set-CsConferencingPolicy [-Identity <XdsIdentity>] -AllowAnonymousUsersToDialOut $False
```

<span data-ttu-id="a148c-122">Дополнительные сведения см. в дополнительных сведениях [в set-CsConferencingPolicy.](/powershell/module/skype/set-csconferencingpolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="a148c-122">For more information, see [Set-CsConferencingPolicy](/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).</span></span>
