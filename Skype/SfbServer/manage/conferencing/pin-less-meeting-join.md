---
title: Настройка присоединения к собранию без ПИН-кода в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c21e8861-bb75-45e8-8485-38daa3b8121c
description: 'Сводка: Сведения о настройке ПИН-кода меньше собраний вариант присоединиться в Скайп для Business Server.'
ms.openlocfilehash: c865d234b58b29890957a2c895a91d84b9a31bb0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33888109"
---
# <a name="configure-pin-less-meeting-join-in-skype-for-business-server"></a><span data-ttu-id="a5ef9-103">Настройка присоединения к собранию без ПИН-кода в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="a5ef9-103">Configure PIN-less meeting join in Skype for Business Server</span></span>
 
<span data-ttu-id="a5ef9-104">**Сводка:** Сведения о настройке ПИН-кода меньше собраний вариант присоединиться в Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="a5ef9-104">**Summary:** Learn how to configure the PIN-less meeting join option in Skype for Business Server.</span></span>
  
<span data-ttu-id="a5ef9-105">При попытке присоединиться к собранию вызывающего-связь, служба Attendant автоматически конференции (CAA) помещает вызывающего абонента в перо удержания, отличается от & зал ожидания #x 2014 г.; Если выступающим еще не на вызов и вызывающего абонента-связь не вошел лидера ПИН-кода.</span><span class="sxs-lookup"><span data-stu-id="a5ef9-105">When a dial-in caller attempts to join a meeting, the Conference Auto Attendant (CAA) service places the caller in a holding pen that is different from the Lobby &#x2014; if a presenter is not already on a call, and the dial-in caller has not entered a leader PIN.</span></span> <span data-ttu-id="a5ef9-106">ПИН-код меньше вариант присоединения к собранию позволяет присоединиться к собранию без ввода ПИН-код ведущего даже в том случае, если они находятся на первого лица на вызов вызывающей-связь.</span><span class="sxs-lookup"><span data-stu-id="a5ef9-106">The PIN-less meeting join option allows dial-in callers to join a meeting without entering a leader PIN even if they are the first person on a call.</span></span> 
  
<span data-ttu-id="a5ef9-107">При настройке этого компонента следует учитывать следующие сведения.</span><span class="sxs-lookup"><span data-stu-id="a5ef9-107">Keep the following in mind when configuring this feature:</span></span>
  
- <span data-ttu-id="a5ef9-108">Применяется только к частным собраниям.</span><span class="sxs-lookup"><span data-stu-id="a5ef9-108">Applies to private meetings only.</span></span>
    
- <span data-ttu-id="a5ef9-109">Позволяет вызывающим абонентам ТСОП оставаться в частых собраниях при отсутствии прошедших проверку пользователей.</span><span class="sxs-lookup"><span data-stu-id="a5ef9-109">Allows PSTN callers to stay in private meetings without the presence of authenticated users.</span></span>
    
- <span data-ttu-id="a5ef9-110">Измененные настройки применяются ко всем существующим и новым частным собраниям.</span><span class="sxs-lookup"><span data-stu-id="a5ef9-110">After the setting is changed, it applies to all existing and new private meetings.</span></span>
    
- <span data-ttu-id="a5ef9-111">Можно включить либо на сайте организатора, либо на глобальном уровне.</span><span class="sxs-lookup"><span data-stu-id="a5ef9-111">Can be enabled either at the site of the organizer or at the global level.</span></span>
    
- <span data-ttu-id="a5ef9-112">Можно установить следующие варианты обхода зала ожидания:</span><span class="sxs-lookup"><span data-stu-id="a5ef9-112">Options for who can bypass the lobby can be set for either of the following:</span></span> 
    
  - <span data-ttu-id="a5ef9-113">**Все вызывающие абоненты из моей организации попадают напрямую**</span><span class="sxs-lookup"><span data-stu-id="a5ef9-113">**Anyone from my Organization with Callers get in directly**</span></span>
    
  - <span data-ttu-id="a5ef9-114">**Все вызывающие абоненты попадают напрямую** (Эта настройка используется по умолчанию.)</span><span class="sxs-lookup"><span data-stu-id="a5ef9-114">**Anyone (no restrictions) with Callers get in directly** (This is the default setting.)</span></span>
    
- <span data-ttu-id="a5ef9-115">Если присоединение без ПИН-кода включено, служба CAA по-прежнему запрашивает ПИН-код ведущего.</span><span class="sxs-lookup"><span data-stu-id="a5ef9-115">When configured to enable PIN-less join, the CAA service still prompts for a leader PIN.</span></span> <span data-ttu-id="a5ef9-116">Пользователи могут присоединиться к собранию независимо от того, введен ли ПИН-код.</span><span class="sxs-lookup"><span data-stu-id="a5ef9-116">Users can join the meeting whether or not a PIN is entered.</span></span> <span data-ttu-id="a5ef9-117">Тем не менее сохраняя возможность вводить ПИН-код ведущего позволяет телефонные вызывающей стороне проверку в качестве лидера и управление ими собрания, если это необходимо.</span><span class="sxs-lookup"><span data-stu-id="a5ef9-117">However, retaining the ability to enter a leader PIN allows a dial-in caller to authenticate as a leader and manage the meeting if necessary.</span></span>
    
## <a name="configure-pin-less-meeting-join"></a><span data-ttu-id="a5ef9-118">Настройка присоединения к собранию без ПИН-кода</span><span class="sxs-lookup"><span data-stu-id="a5ef9-118">Configure PIN-less meeting join</span></span>

<span data-ttu-id="a5ef9-119">Чтобы включить присоединения к собранию без использования ПИН-кода для пользователей, используйте командлет [Set-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps) с параметром AllowAnonymousPstnActivation следующим образом:</span><span class="sxs-lookup"><span data-stu-id="a5ef9-119">To enable PIN-less meeting join for your users, use the [Set-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps) cmdlet with the AllowAnonymousPstnActivation parameter as follows:</span></span>
  
```
Set-CsDialInConferencingConfiguration -Identity  < global or site:sitename>  -AllowAnonymousPstnActivation $True
```

<span data-ttu-id="a5ef9-120">Например, следующая команда включает присоединение к собранию без ПИН-кода для сайта Redmond:</span><span class="sxs-lookup"><span data-stu-id="a5ef9-120">For example, the following command enables PIN-less meeting join for the site Redmond:</span></span>
  
```
Set-CsDialInConferencingConfiguration -Identity site:Redmond -AllowAnonymousPstnActivation $True
```

<span data-ttu-id="a5ef9-121">Когда присоединение к собранию без ПИН-кода включено, в целях безопасности можно запретить анонимным пользователям присоединяться к собранию обратным звонком. Для этого политику конференц-связи следует настроить следующим образом.</span><span class="sxs-lookup"><span data-stu-id="a5ef9-121">For security purposes, when PIN-less meeting join is turned on, you might want to restrict anonymous users from dialing out by ensuring the ConferencingPolicy is set as follows:</span></span>
  
```
Set-CsConferencingPolicy [-Identity <XdsIdentity>] -AllowAnonymousUsersToDialOut $False
```

<span data-ttu-id="a5ef9-122">Для получения дополнительных сведений см [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="a5ef9-122">For more information, see [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).</span></span>
  

