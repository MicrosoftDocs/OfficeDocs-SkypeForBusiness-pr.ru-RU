---
title: Планирование распределенной линии для Skype для бизнеса Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/21/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6356aad4-700d-495c-8fc8-58eb1d4f6f18
description: Прочтите этот раздел, чтобы узнать о планировании для общих строки внешний вид (SLA) в Скайп Business Server 2015, 2015 ноября накопительного обновления.
ms.openlocfilehash: fa0d8923c234773e3b21ec43bca4c4d7aafde4df
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33913457"
---
# <a name="plan-for-shared-line-appearance-in-skype-for-business-server-2015"></a><span data-ttu-id="747fb-103">Планирование распределенной линии для Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="747fb-103">Plan for Shared Line Appearance in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="747fb-104">Прочтите этот раздел, чтобы узнать о планировании для общих строки внешний вид (SLA) в Скайп Business Server 2015, 2015 ноября накопительного обновления.</span><span class="sxs-lookup"><span data-stu-id="747fb-104">Read this topic to learn how to plan for Shared Line Appearance (SLA) in Skype for Business Server 2015, November 2015 Cumulative Update.</span></span> 
  
<span data-ttu-id="747fb-105">Общий вид линии — это функция Скайп для бизнеса для обработки нескольких звонки от конкретных номер, называемый общей номер.</span><span class="sxs-lookup"><span data-stu-id="747fb-105">Shared Line Appearance is a feature in Skype for Business for handling multiple calls on a specific number called a shared number.</span></span> <span data-ttu-id="747fb-106">Соглашение об уровне ОБСЛУЖИВАНИЯ можно настроить любые корпоративной голосовой связи включены Скайп для корпоративных пользователей виде общего числа с несколькими строками реагировать на различных вызовов.</span><span class="sxs-lookup"><span data-stu-id="747fb-106">SLA can configure any enterprise voice enabled Skype for Business user as a shared number with multiple lines to respond to multiple calls.</span></span> <span data-ttu-id="747fb-107">Фактически вызовы не принимаются общим номером, а направляются пользователям, выступающим в роли делегатов общего номера.</span><span class="sxs-lookup"><span data-stu-id="747fb-107">The calls are not actually received on the shared number, instead they are forwarded to users that act as delegates for the shared number.</span></span> <span data-ttu-id="747fb-108">Любой из делегатов может принять вызов, после чего остальные делегаты получать уведомление на телефон о том, кто принял вызов и какая линия теперь занята.</span><span class="sxs-lookup"><span data-stu-id="747fb-108">Any one of the delegates can pick up the call while the rest of the delegates get a notification on their phone about who picked up the call and which line has become busy as a result.</span></span> <span data-ttu-id="747fb-109">Количество линий и делегатов можно настроить для общего номера в SLA.</span><span class="sxs-lookup"><span data-stu-id="747fb-109">Both the number of lines and the delegates are configurable for a shared number in SLA.</span></span> <span data-ttu-id="747fb-110">Кроме того, для общего номера можно настроить такие расширенные параметры, как опции "Занято" (используется в ситуации, когда все линии заняты) и "Пропущенный вызов" (используется, когда ни один из делегатов не ответил на звонок).</span><span class="sxs-lookup"><span data-stu-id="747fb-110">In addition, advanced options, such as BusyOption (what happens in a situation when all lines are busy) and MissedCallOption (the case in which none of the delegates pick up a call), can also be configured for a shared number.</span></span>
  
<span data-ttu-id="747fb-111">Соглашение об уровне ОБСЛУЖИВАНИЯ поддерживается только следующие устройства телефона (он не поддерживается для Скайп пользователей на компьютеры, мобильные телефоны и другие устройства):</span><span class="sxs-lookup"><span data-stu-id="747fb-111">SLA is supported only on the following phone devices (it is not supported for Skype for Business clients on computers, mobile phones, or other devices):</span></span> 
  
- <span data-ttu-id="747fb-112">Polycom VVX300 с обновлением встроенного ПО 5.4.1</span><span class="sxs-lookup"><span data-stu-id="747fb-112">Polycom VVX300 with firmware update 5.4.1</span></span>
    
- <span data-ttu-id="747fb-113">Polycom VVX400 с обновлением встроенного ПО 5.4.1</span><span class="sxs-lookup"><span data-stu-id="747fb-113">Polycom VVX400 with firmware update 5.4.1</span></span>
    
- <span data-ttu-id="747fb-114">Polycom VVX500 с обновлением встроенного ПО 5.4.1</span><span class="sxs-lookup"><span data-stu-id="747fb-114">Polycom VVX500 with firmware update 5.4.1</span></span>
    
- <span data-ttu-id="747fb-115">Polycom VVX600 с обновлением встроенного ПО 5.4.1</span><span class="sxs-lookup"><span data-stu-id="747fb-115">Polycom VVX600 with firmware update 5.4.1</span></span>
    
<span data-ttu-id="747fb-116">Соглашение об уровне ОБСЛУЖИВАНИЯ — это новая возможность в Скайп для Business Server 2015 ноября накопительного обновления.</span><span class="sxs-lookup"><span data-stu-id="747fb-116">SLA is a new feature in Skype for Business Server, November 2015 Cumulative Update.</span></span> 
  
<span data-ttu-id="747fb-117">Дополнительные сведения о развертывании SLA см. в разделе [Deploy Shared Line Appearance in Skype for Business Server 2015](../../deploy/deploy-enterprise-voice/deploy-shared-line-appearance.md).</span><span class="sxs-lookup"><span data-stu-id="747fb-117">For information about deploying SLA, see [Deploy Shared Line Appearance in Skype for Business Server 2015](../../deploy/deploy-enterprise-voice/deploy-shared-line-appearance.md).</span></span>
  
## <a name="feature-list"></a><span data-ttu-id="747fb-118">Список функций</span><span class="sxs-lookup"><span data-stu-id="747fb-118">Feature List</span></span>

<span data-ttu-id="747fb-119">Настройка группы SLA предоставляет следующие возможности.</span><span class="sxs-lookup"><span data-stu-id="747fb-119">Setting up an SLA group enables the following:</span></span>
  
- <span data-ttu-id="747fb-p102">Все делегаты в группы могут отвечать на входящие вызовы, поступающие на один общий номер. Эти вызовы могут быть как на базе ТСОП, так и на базе SIP.</span><span class="sxs-lookup"><span data-stu-id="747fb-p102">All delegates in the group can answer inbound calls to the same shared number. The calls can be PSTN-based or SIP-based.</span></span>
    
- <span data-ttu-id="747fb-122">Делегаты могут переводить вызовы в режим удержания и затем принимать их.</span><span class="sxs-lookup"><span data-stu-id="747fb-122">Delegates can hold and pick up calls.</span></span>
    
- <span data-ttu-id="747fb-123">Делегаты могут передавать вызовы за пределы группы SLA.</span><span class="sxs-lookup"><span data-stu-id="747fb-123">Delegates can transfer calls to a number outside of the SLA group.</span></span>
    
- <span data-ttu-id="747fb-124">Делегаты могут посмотреть количество вызовов, одновременно поступающих на общий номер, а также состояние каждого из этих вызовов.</span><span class="sxs-lookup"><span data-stu-id="747fb-124">Delegates can see how many calls are currently on the shared number, and view the status of each of those calls.</span></span>
    
- <span data-ttu-id="747fb-p103">Можно настроить максимальное количество одновременных вызов для общего номера. Кроме того, можно определить способ обработки дополнительных вызовов после достижения максимального значения. Лишние вызовы могут быть отклонены сигналом "занято", перенаправлены на другой номер или в голосовую почту.</span><span class="sxs-lookup"><span data-stu-id="747fb-p103">You can configure a maximum number of concurrent calls for the shared number. You can also set how you want additional calls to be handled after this maximum is reached. Excess calls can be rejected with a busy signal, forwarded to an alternate number, or forwarded to voice mail.</span></span>
    
- <span data-ttu-id="747fb-p104">Можно настроить способ обработки пропущенных вызовов (вызовы, на которые не ответили в течение определенного времени). Если включить голосовую почту для идентификатора группы, пропущенные звонки автоматически отправляются на голосовую почту. Если голосовая почта не включена для идентификатора группы (общий номер), пропущенный вызов можно отклонить сигналом "занято", переадресовать на другой номер или отсоединить.</span><span class="sxs-lookup"><span data-stu-id="747fb-p104">You can configure how you want missed calls (calls not picked up after a certain time) to be handled. If you enable voice mail for the group identity, missed calls automatically go to voice mail. If you do not have voice mail enabled for the group identity (shared number), you can choose for missed calls to be rejected with a busy signal, forwarded to an alternate number, or disconnected.</span></span>
    

