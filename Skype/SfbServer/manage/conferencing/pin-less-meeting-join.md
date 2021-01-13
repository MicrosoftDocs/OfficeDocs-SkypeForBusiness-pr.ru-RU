---
title: Настройка присоединить к собранию без ПИН-кода в Skype для бизнеса Server
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
description: Сводка. Узнайте, как настроить параметр присоединить к собранию без ПИН-кода в Skype для бизнеса Server.
ms.openlocfilehash: 794bf13d92857a18254f903a1c5dcca98d0a1ec0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827989"
---
# <a name="configure-pin-less-meeting-join-in-skype-for-business-server"></a><span data-ttu-id="ab744-103">Настройка присоединить к собранию без ПИН-кода в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="ab744-103">Configure PIN-less meeting join in Skype for Business Server</span></span>
 
<span data-ttu-id="ab744-104">**Сводка:** Learn how to configure the PIN-less meeting join option in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="ab744-104">**Summary:** Learn how to configure the PIN-less meeting join option in Skype for Business Server.</span></span>
  
<span data-ttu-id="ab744-105">Когда звоня из телефонного номера пытается присоединиться к собранию, служба conference автосекретарь (CAA) помещает вызываемого в перо для удержания, которое отличается от номера "Зал залов" &#x2014; если он еще не звонит, а вызываемая служба не введет ПИН-код руководителя.</span><span class="sxs-lookup"><span data-stu-id="ab744-105">When a dial-in caller attempts to join a meeting, the Conference Auto Attendant (CAA) service places the caller in a holding pen that is different from the Lobby &#x2014; if a presenter is not already on a call, and the dial-in caller has not entered a leader PIN.</span></span> <span data-ttu-id="ab744-106">Параметр присоединиться к собранию без ПИН-кода позволяет звонятелям с телефонным звонякой присоединяться к собранию без ввода ПИН-кода руководителя, даже если они являются первым звоня лицом.</span><span class="sxs-lookup"><span data-stu-id="ab744-106">The PIN-less meeting join option allows dial-in callers to join a meeting without entering a leader PIN even if they are the first person on a call.</span></span> 
  
<span data-ttu-id="ab744-107">При настройке этой функции следует иметь в виду следующее:</span><span class="sxs-lookup"><span data-stu-id="ab744-107">Keep the following in mind when configuring this feature:</span></span>
  
- <span data-ttu-id="ab744-108">Применяется только к частным собраниям.</span><span class="sxs-lookup"><span data-stu-id="ab744-108">Applies to private meetings only.</span></span>
    
- <span data-ttu-id="ab744-109">Позволяет звонятелям ТСОП оставаться на частных собраниях без присутствия пользователей, подлинность в которые прошла.</span><span class="sxs-lookup"><span data-stu-id="ab744-109">Allows PSTN callers to stay in private meetings without the presence of authenticated users.</span></span>
    
- <span data-ttu-id="ab744-110">После изменения параметра он применяется ко всем существующим и новым частным собраниям.</span><span class="sxs-lookup"><span data-stu-id="ab744-110">After the setting is changed, it applies to all existing and new private meetings.</span></span>
    
- <span data-ttu-id="ab744-111">Может быть включен на сайте организатора или на глобальном уровне.</span><span class="sxs-lookup"><span data-stu-id="ab744-111">Can be enabled either at the site of the organizer or at the global level.</span></span>
    
- <span data-ttu-id="ab744-112">Параметры для тех, кто может обходить "lobby", можно настроить для одного из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="ab744-112">Options for who can bypass the lobby can be set for either of the following:</span></span> 
    
  - <span data-ttu-id="ab744-113">**Все, кто из моей организации с вызывателями, получают прямой звонок**</span><span class="sxs-lookup"><span data-stu-id="ab744-113">**Anyone from my Organization with Callers get in directly**</span></span>
    
  - <span data-ttu-id="ab744-114">**Все (без ограничений) с вызывателями получают** прямой ввод (это параметр по умолчанию).)</span><span class="sxs-lookup"><span data-stu-id="ab744-114">**Anyone (no restrictions) with Callers get in directly** (This is the default setting.)</span></span>
    
- <span data-ttu-id="ab744-115">Если для этого настроено участие без ПИН-кода, служба CAA по-прежнему запросит ПИН-код руководителя.</span><span class="sxs-lookup"><span data-stu-id="ab744-115">When configured to enable PIN-less join, the CAA service still prompts for a leader PIN.</span></span> <span data-ttu-id="ab744-116">Пользователи могут присоединяться к собранию независимо от того, введен ли ПИН-код.</span><span class="sxs-lookup"><span data-stu-id="ab744-116">Users can join the meeting whether or not a PIN is entered.</span></span> <span data-ttu-id="ab744-117">Тем не менее, сохранение возможности ввода ПИН-кода руководителя позволяет вызываемой по телефонной телефонии проходить проверку подлинности в качестве руководителя и при необходимости управлять собранием.</span><span class="sxs-lookup"><span data-stu-id="ab744-117">However, retaining the ability to enter a leader PIN allows a dial-in caller to authenticate as a leader and manage the meeting if necessary.</span></span>
    
## <a name="configure-pin-less-meeting-join"></a><span data-ttu-id="ab744-118">Настройка присоединить к собранию без ПИН-кода</span><span class="sxs-lookup"><span data-stu-id="ab744-118">Configure PIN-less meeting join</span></span>

<span data-ttu-id="ab744-119">Чтобы разрешить пользователям присоединяться к собранию без ПИН-кода, используйте с параметром AllowAnonymousPstnActivation с помощью параметра [Set-CsDialInConferencingConfiguration:](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="ab744-119">To enable PIN-less meeting join for your users, use the [Set-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps) cmdlet with the AllowAnonymousPstnActivation parameter as follows:</span></span>
  
```PowerShell
Set-CsDialInConferencingConfiguration -Identity  < global or site:sitename>  -AllowAnonymousPstnActivation $True
```

<span data-ttu-id="ab744-120">Например, следующая команда позволяет присоединяться к собранию без ПИН-кода для сайта Redmond:</span><span class="sxs-lookup"><span data-stu-id="ab744-120">For example, the following command enables PIN-less meeting join for the site Redmond:</span></span>
  
```PowerShell
Set-CsDialInConferencingConfiguration -Identity site:Redmond -AllowAnonymousPstnActivation $True
```

<span data-ttu-id="ab744-121">В целях безопасности, если включено присоединяние к собранию без ПИН-кода, может потребоваться запретить анонимным пользователям набор номера, убедившись, что для conferencingPolicy установлено значение:</span><span class="sxs-lookup"><span data-stu-id="ab744-121">For security purposes, when PIN-less meeting join is turned on, you might want to restrict anonymous users from dialing out by ensuring the ConferencingPolicy is set as follows:</span></span>
  
```PowerShell
Set-CsConferencingPolicy [-Identity <XdsIdentity>] -AllowAnonymousUsersToDialOut $False
```

<span data-ttu-id="ab744-122">Дополнительные сведения [см. в подстроке Set-CsConferencingPolicy.](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="ab744-122">For more information, see [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).</span></span>
  

