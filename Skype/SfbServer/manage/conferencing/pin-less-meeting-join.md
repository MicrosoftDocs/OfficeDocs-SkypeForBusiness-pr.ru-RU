---
title: Настройка присоединения к собранию без ПИН-кода в Skype для бизнеса Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c21e8861-bb75-45e8-8485-38daa3b8121c
description: 'Сводка: Сведения о настройке ПИН-кода меньше собраний вариант присоединиться в Скайп для Business Server.'
ms.openlocfilehash: 843ea92a331391faa47e4cbc32191312c6dfbc6b
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2018
ms.locfileid: "20985965"
---
# <a name="configure-pin-less-meeting-join-in-skype-for-business-server"></a><span data-ttu-id="6ed41-103">Настройка присоединения к собранию без ПИН-кода в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="6ed41-103">Configure PIN-less meeting join in Skype for Business Server</span></span>
 
<span data-ttu-id="6ed41-104">**Сводка:** Сведения о настройке ПИН-кода меньше собраний вариант присоединиться в Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="6ed41-104">**Summary:** Learn how to configure the PIN-less meeting join option in Skype for Business Server.</span></span>
  
<span data-ttu-id="6ed41-105">При попытке присоединиться к собранию вызывающего-связь, служба Attendant автоматически конференции (CAA) помещает вызывающего абонента в перо удержания, отличается от зал ожидания & #x 2014 г.; Если выступающим еще не на вызов и вызывающего абонента-связь не вошел лидера ПИН-кода.</span><span class="sxs-lookup"><span data-stu-id="6ed41-105">When a dial-in caller attempts to join a meeting, the Conference Auto Attendant (CAA) service places the caller in a holding pen that is different from the Lobby &#x2014; if a presenter is not already on a call, and the dial-in caller has not entered a leader PIN.</span></span> <span data-ttu-id="6ed41-106">ПИН-код меньше вариант присоединения к собранию позволяет присоединиться к собранию без ввода ПИН-код ведущего даже в том случае, если они находятся на первого лица на вызов вызывающей-связь.</span><span class="sxs-lookup"><span data-stu-id="6ed41-106">The PIN-less meeting join option allows dial-in callers to join a meeting without entering a leader PIN even if they are the first person on a call.</span></span> 
  
<span data-ttu-id="6ed41-107">При настройке этого компонента следует учитывать следующие сведения.</span><span class="sxs-lookup"><span data-stu-id="6ed41-107">Keep the following in mind when configuring this feature:</span></span>
  
- <span data-ttu-id="6ed41-108">Применяется только к частным собраниям.</span><span class="sxs-lookup"><span data-stu-id="6ed41-108">Applies to private meetings only.</span></span>
    
- <span data-ttu-id="6ed41-109">Позволяет вызывающим абонентам ТСОП оставаться в частых собраниях при отсутствии прошедших проверку пользователей.</span><span class="sxs-lookup"><span data-stu-id="6ed41-109">Allows PSTN callers to stay in private meetings without the presence of authenticated users.</span></span>
    
- <span data-ttu-id="6ed41-110">Измененные настройки применяются ко всем существующим и новым частным собраниям.</span><span class="sxs-lookup"><span data-stu-id="6ed41-110">After the setting is changed, it applies to all existing and new private meetings.</span></span>
    
- <span data-ttu-id="6ed41-111">Можно включить либо на сайте организатора, либо на глобальном уровне.</span><span class="sxs-lookup"><span data-stu-id="6ed41-111">Can be enabled either at the site of the organizer or at the global level.</span></span>
    
- <span data-ttu-id="6ed41-112">Можно установить следующие варианты обхода зала ожидания:</span><span class="sxs-lookup"><span data-stu-id="6ed41-112">Options for who can bypass the lobby can be set for either of the following:</span></span> 
    
  - <span data-ttu-id="6ed41-113">**Все вызывающие абоненты из моей организации попадают напрямую**</span><span class="sxs-lookup"><span data-stu-id="6ed41-113">**Anyone from my Organization with Callers get in directly**</span></span>
    
  - <span data-ttu-id="6ed41-114">**Все вызывающие абоненты попадают напрямую** (Эта настройка используется по умолчанию.)</span><span class="sxs-lookup"><span data-stu-id="6ed41-114">**Anyone (no restrictions) with Callers get in directly** (This is the default setting.)</span></span>
    
- <span data-ttu-id="6ed41-115">Если присоединение без ПИН-кода включено, служба CAA по-прежнему запрашивает ПИН-код ведущего.</span><span class="sxs-lookup"><span data-stu-id="6ed41-115">When configured to enable PIN-less join, the CAA service still prompts for a leader PIN.</span></span> <span data-ttu-id="6ed41-116">Пользователи могут присоединиться к собранию независимо от того, введен ли ПИН-код.</span><span class="sxs-lookup"><span data-stu-id="6ed41-116">Users can join the meeting whether or not a PIN is entered.</span></span> <span data-ttu-id="6ed41-117">Тем не менее сохраняя возможность вводить ПИН-код ведущего позволяет телефонные вызывающей стороне проверку в качестве лидера и управление ими собрания, если это необходимо.</span><span class="sxs-lookup"><span data-stu-id="6ed41-117">However, retaining the ability to enter a leader PIN allows a dial-in caller to authenticate as a leader and manage the meeting if necessary.</span></span>
    
## <a name="configure-pin-less-meeting-join"></a><span data-ttu-id="6ed41-118">Настройка присоединения к собранию без ПИН-кода</span><span class="sxs-lookup"><span data-stu-id="6ed41-118">Configure PIN-less meeting join</span></span>

<span data-ttu-id="6ed41-119">Чтобы включить присоединения к собранию без использования ПИН-кода для пользователей, используйте командлет [Set-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps) с параметром AllowAnonymousPstnActivation следующим образом:</span><span class="sxs-lookup"><span data-stu-id="6ed41-119">To enable PIN-less meeting join for your users, use the [Set-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps) cmdlet with the AllowAnonymousPstnActivation parameter as follows:</span></span>
  
```
Set-CsDialInConferencingConfiguration -Identity  < global or site:sitename>  -AllowAnonymousPstnActivation $True
```

<span data-ttu-id="6ed41-120">Например, следующая команда включает присоединение к собранию без ПИН-кода для сайта Redmond:</span><span class="sxs-lookup"><span data-stu-id="6ed41-120">For example, the following command enables PIN-less meeting join for the site Redmond:</span></span>
  
```
Set-CsDialInConferencingConfiguration -Identity site:Redmond -AllowAnonymousPstnActivation $True
```

<span data-ttu-id="6ed41-121">Когда присоединение к собранию без ПИН-кода включено, в целях безопасности можно запретить анонимным пользователям присоединяться к собранию обратным звонком. Для этого политику конференц-связи следует настроить следующим образом.</span><span class="sxs-lookup"><span data-stu-id="6ed41-121">For security purposes, when PIN-less meeting join is turned on, you might want to restrict anonymous users from dialing out by ensuring the ConferencingPolicy is set as follows:</span></span>
  
```
Set-CsConferencingPolicy [-Identity <XdsIdentity>] -AllowAnonymousUsersToDialOut $False
```

<span data-ttu-id="6ed41-122">Для получения дополнительных сведений см [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="6ed41-122">For more information, see [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).</span></span>
  

