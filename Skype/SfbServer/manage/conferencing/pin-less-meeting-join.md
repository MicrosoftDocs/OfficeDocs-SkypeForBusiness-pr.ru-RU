---
title: Настройка присоединения к собранию без ПИН-кода в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c21e8861-bb75-45e8-8485-38daa3b8121c
description: 'Сводка: сведения о том, как настроить параметр присоединения к собранию без контактов в Skype для бизнеса Server.'
ms.openlocfilehash: ecd1d2bf184dd6b9e1ff78e16c2ca1eb8da73ef9
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280385"
---
# <a name="configure-pin-less-meeting-join-in-skype-for-business-server"></a><span data-ttu-id="7e811-103">Настройка присоединения к собранию без ПИН-кода в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="7e811-103">Configure PIN-less meeting join in Skype for Business Server</span></span>
 
<span data-ttu-id="7e811-104">**Сводка:** Сведения о том, как настроить параметр присоединения к собранию без контактов в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="7e811-104">**Summary:** Learn how to configure the PIN-less meeting join option in Skype for Business Server.</span></span>
  
<span data-ttu-id="7e811-105">Когда вызывающий абонент пытается присоединиться к собранию, служба автосекретаря конференции (Каа) помещает вызывающий объект на перо, отличное от &#x2014;, если выступающее еще не наступило на вызов, а вызывающий абонент не ввел заполнитель.</span><span class="sxs-lookup"><span data-stu-id="7e811-105">When a dial-in caller attempts to join a meeting, the Conference Auto Attendant (CAA) service places the caller in a holding pen that is different from the Lobby &#x2014; if a presenter is not already on a call, and the dial-in caller has not entered a leader PIN.</span></span> <span data-ttu-id="7e811-106">Параметр присоединиться к собранию с неконтактным подключением позволяет присоединиться к собранию с помощью абонентов, не вводя ведущий контакт, даже если он является первым абонентом в звонке.</span><span class="sxs-lookup"><span data-stu-id="7e811-106">The PIN-less meeting join option allows dial-in callers to join a meeting without entering a leader PIN even if they are the first person on a call.</span></span> 
  
<span data-ttu-id="7e811-107">При настройке этого компонента следует учитывать следующие сведения.</span><span class="sxs-lookup"><span data-stu-id="7e811-107">Keep the following in mind when configuring this feature:</span></span>
  
- <span data-ttu-id="7e811-108">Применяется только к частным собраниям.</span><span class="sxs-lookup"><span data-stu-id="7e811-108">Applies to private meetings only.</span></span>
    
- <span data-ttu-id="7e811-109">Позволяет вызывающим абонентам ТСОП оставаться в частых собраниях при отсутствии прошедших проверку пользователей.</span><span class="sxs-lookup"><span data-stu-id="7e811-109">Allows PSTN callers to stay in private meetings without the presence of authenticated users.</span></span>
    
- <span data-ttu-id="7e811-110">Измененные настройки применяются ко всем существующим и новым частным собраниям.</span><span class="sxs-lookup"><span data-stu-id="7e811-110">After the setting is changed, it applies to all existing and new private meetings.</span></span>
    
- <span data-ttu-id="7e811-111">Можно включить либо на сайте организатора, либо на глобальном уровне.</span><span class="sxs-lookup"><span data-stu-id="7e811-111">Can be enabled either at the site of the organizer or at the global level.</span></span>
    
- <span data-ttu-id="7e811-112">Можно установить следующие варианты обхода зала ожидания:</span><span class="sxs-lookup"><span data-stu-id="7e811-112">Options for who can bypass the lobby can be set for either of the following:</span></span> 
    
  - <span data-ttu-id="7e811-113">**Все вызывающие абоненты из моей организации попадают напрямую**</span><span class="sxs-lookup"><span data-stu-id="7e811-113">**Anyone from my Organization with Callers get in directly**</span></span>
    
  - <span data-ttu-id="7e811-114">**Все вызывающие абоненты попадают напрямую** (Эта настройка используется по умолчанию.)</span><span class="sxs-lookup"><span data-stu-id="7e811-114">**Anyone (no restrictions) with Callers get in directly** (This is the default setting.)</span></span>
    
- <span data-ttu-id="7e811-115">Если присоединение без ПИН-кода включено, служба CAA по-прежнему запрашивает ПИН-код ведущего.</span><span class="sxs-lookup"><span data-stu-id="7e811-115">When configured to enable PIN-less join, the CAA service still prompts for a leader PIN.</span></span> <span data-ttu-id="7e811-116">Пользователи могут присоединиться к собранию независимо от того, введен ли ПИН-код.</span><span class="sxs-lookup"><span data-stu-id="7e811-116">Users can join the meeting whether or not a PIN is entered.</span></span> <span data-ttu-id="7e811-117">Однако сохранение возможности ввода ведущего PIN-кода позволяет вызывающему абоненту войти в качестве лидера, а при необходимости управлять собранием.</span><span class="sxs-lookup"><span data-stu-id="7e811-117">However, retaining the ability to enter a leader PIN allows a dial-in caller to authenticate as a leader and manage the meeting if necessary.</span></span>
    
## <a name="configure-pin-less-meeting-join"></a><span data-ttu-id="7e811-118">Настройка присоединения к собранию без ПИН-кода</span><span class="sxs-lookup"><span data-stu-id="7e811-118">Configure PIN-less meeting join</span></span>

<span data-ttu-id="7e811-119">Чтобы включить присоединение к собранию без контактов для пользователей, используйте командлет [Set-ксдиалинконференЦингконфигуратион](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps) с параметром аллованонимауспстнактиватион, как описано ниже.</span><span class="sxs-lookup"><span data-stu-id="7e811-119">To enable PIN-less meeting join for your users, use the [Set-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps) cmdlet with the AllowAnonymousPstnActivation parameter as follows:</span></span>
  
```
Set-CsDialInConferencingConfiguration -Identity  < global or site:sitename>  -AllowAnonymousPstnActivation $True
```

<span data-ttu-id="7e811-120">Например, следующая команда включает присоединение к собранию без ПИН-кода для сайта Redmond:</span><span class="sxs-lookup"><span data-stu-id="7e811-120">For example, the following command enables PIN-less meeting join for the site Redmond:</span></span>
  
```
Set-CsDialInConferencingConfiguration -Identity site:Redmond -AllowAnonymousPstnActivation $True
```

<span data-ttu-id="7e811-121">Когда присоединение к собранию без ПИН-кода включено, в целях безопасности можно запретить анонимным пользователям присоединяться к собранию обратным звонком. Для этого политику конференц-связи следует настроить следующим образом.</span><span class="sxs-lookup"><span data-stu-id="7e811-121">For security purposes, when PIN-less meeting join is turned on, you might want to restrict anonymous users from dialing out by ensuring the ConferencingPolicy is set as follows:</span></span>
  
```
Set-CsConferencingPolicy [-Identity <XdsIdentity>] -AllowAnonymousUsersToDialOut $False
```

<span data-ttu-id="7e811-122">Дополнительные сведения можно найти в разделе [Set-ксконференЦингполици](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="7e811-122">For more information, see [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).</span></span>
  

