---
title: Планирование внешнего вида общих строк в Skype для бизнеса Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/21/2016
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6356aad4-700d-495c-8fc8-58eb1d4f6f18
description: В этом разделе вы узнаете, как спланировать общий вид линии (SLA) в накопительном обновлении Skype для бизнеса Server 2015 за ноябрь 2015 г.
ms.openlocfilehash: d7fa13b36c232e37c79e8509de71b4ac29ceff72
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813349"
---
# <a name="plan-for-shared-line-appearance-in-skype-for-business-server-2015"></a><span data-ttu-id="811b7-103">Планирование внешнего вида общих строк в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="811b7-103">Plan for Shared Line Appearance in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="811b7-104">В этом разделе вы узнаете, как спланировать общий вид линии (SLA) в накопительном обновлении Skype для бизнеса Server 2015 за ноябрь 2015 г.</span><span class="sxs-lookup"><span data-stu-id="811b7-104">Read this topic to learn how to plan for Shared Line Appearance (SLA) in Skype for Business Server 2015, November 2015 Cumulative Update.</span></span> 
  
<span data-ttu-id="811b7-105">Внешний вид общей линии — это функция в Skype для бизнеса для обработки нескольких вызовов на определенный номер, называемый общим номером.</span><span class="sxs-lookup"><span data-stu-id="811b7-105">Shared Line Appearance is a feature in Skype for Business for handling multiple calls on a specific number called a shared number.</span></span> <span data-ttu-id="811b7-106">SLA может настроить любого пользователя Skype для бизнеса с поддержкой корпоративной голосовой связи в качестве общего номера с несколькими строками для ответа на несколько вызовов.</span><span class="sxs-lookup"><span data-stu-id="811b7-106">SLA can configure any enterprise voice enabled Skype for Business user as a shared number with multiple lines to respond to multiple calls.</span></span> <span data-ttu-id="811b7-107">Вызовы фактически не получаются по общему номеру, а перенаададовыются пользователям, которые выступают в качестве делегатов общего номера.</span><span class="sxs-lookup"><span data-stu-id="811b7-107">The calls are not actually received on the shared number, instead they are forwarded to users that act as delegates for the shared number.</span></span> <span data-ttu-id="811b7-108">Любой из делегатов может получить вызов, а остальные делегаты получают на своем телефоне уведомление о том, кто и какая строка была занята в результате.</span><span class="sxs-lookup"><span data-stu-id="811b7-108">Any one of the delegates can pick up the call while the rest of the delegates get a notification on their phone about who picked up the call and which line has become busy as a result.</span></span> <span data-ttu-id="811b7-109">Количество строк и делегатов можно настроить для общего номера в SLA.</span><span class="sxs-lookup"><span data-stu-id="811b7-109">Both the number of lines and the delegates are configurable for a shared number in SLA.</span></span> <span data-ttu-id="811b7-110">Кроме того, дополнительные параметры, такие как BusyOption (что происходит в ситуации, когда все линии заняты) и MissedCallOption (в случае, когда ни один из делегатов не берет вызов), также можно настроить для общего номера.</span><span class="sxs-lookup"><span data-stu-id="811b7-110">In addition, advanced options, such as BusyOption (what happens in a situation when all lines are busy) and MissedCallOption (the case in which none of the delegates pick up a call), can also be configured for a shared number.</span></span>
  
<span data-ttu-id="811b7-111">SLA поддерживается только на следующих телефонных устройствах (оно не поддерживается для клиентов Skype для бизнеса на компьютерах, мобильных телефонах и других устройствах):</span><span class="sxs-lookup"><span data-stu-id="811b7-111">SLA is supported only on the following phone devices (it is not supported for Skype for Business clients on computers, mobile phones, or other devices):</span></span> 
  
- <span data-ttu-id="811b7-112">Polycom VVX300 с обновлением микропрограмм 5.4.1</span><span class="sxs-lookup"><span data-stu-id="811b7-112">Polycom VVX300 with firmware update 5.4.1</span></span>
    
- <span data-ttu-id="811b7-113">Polycom VVX400 с обновлением микропрограммы 5.4.1</span><span class="sxs-lookup"><span data-stu-id="811b7-113">Polycom VVX400 with firmware update 5.4.1</span></span>
    
- <span data-ttu-id="811b7-114">Polycom VVX500 с обновлением микропрограммы 5.4.1</span><span class="sxs-lookup"><span data-stu-id="811b7-114">Polycom VVX500 with firmware update 5.4.1</span></span>
    
- <span data-ttu-id="811b7-115">Polycom VVX600 с обновлением микропрограммы 5.4.1</span><span class="sxs-lookup"><span data-stu-id="811b7-115">Polycom VVX600 with firmware update 5.4.1</span></span>
    
<span data-ttu-id="811b7-116">SLA — это новая функция в Skype для бизнеса Server, накопительное обновление за ноябрь 2015 г.</span><span class="sxs-lookup"><span data-stu-id="811b7-116">SLA is a new feature in Skype for Business Server, November 2015 Cumulative Update.</span></span> 
  
<span data-ttu-id="811b7-117">For information about deploying SLA, see [Deploy Shared Line Appearance in Skype for Business Server 2015.](../../deploy/deploy-enterprise-voice/deploy-shared-line-appearance.md)</span><span class="sxs-lookup"><span data-stu-id="811b7-117">For information about deploying SLA, see [Deploy Shared Line Appearance in Skype for Business Server 2015](../../deploy/deploy-enterprise-voice/deploy-shared-line-appearance.md).</span></span>
  
## <a name="feature-list"></a><span data-ttu-id="811b7-118">Список функций</span><span class="sxs-lookup"><span data-stu-id="811b7-118">Feature List</span></span>

<span data-ttu-id="811b7-119">Настройка группы SLA включает следующие возможности:</span><span class="sxs-lookup"><span data-stu-id="811b7-119">Setting up an SLA group enables the following:</span></span>
  
- <span data-ttu-id="811b7-120">Все делегаты в группе могут отвечать на входящие вызовы на один общий номер.</span><span class="sxs-lookup"><span data-stu-id="811b7-120">All delegates in the group can answer inbound calls to the same shared number.</span></span> <span data-ttu-id="811b7-121">Вызовы могут быть основаны на STN или SIP.</span><span class="sxs-lookup"><span data-stu-id="811b7-121">The calls can be PSTN-based or SIP-based.</span></span>
    
- <span data-ttu-id="811b7-122">Делегаты могут удерживать и выбирать вызовы.</span><span class="sxs-lookup"><span data-stu-id="811b7-122">Delegates can hold and pick up calls.</span></span>
    
- <span data-ttu-id="811b7-123">Делегаты могут переводить звонки на номер вне группы SLA.</span><span class="sxs-lookup"><span data-stu-id="811b7-123">Delegates can transfer calls to a number outside of the SLA group.</span></span>
    
- <span data-ttu-id="811b7-124">Делегаты могут просмотреть, сколько вызовов в настоящее время находится на общем номере, и просмотреть состояние каждого из этих вызовов.</span><span class="sxs-lookup"><span data-stu-id="811b7-124">Delegates can see how many calls are currently on the shared number, and view the status of each of those calls.</span></span>
    
- <span data-ttu-id="811b7-125">Можно настроить максимальное количество одновременно звонков для общего номера.</span><span class="sxs-lookup"><span data-stu-id="811b7-125">You can configure a maximum number of concurrent calls for the shared number.</span></span> <span data-ttu-id="811b7-126">Вы также можете настроить, как будут обрабатываться дополнительные вызовы после того, как будет достигнуто это максимальное значение.</span><span class="sxs-lookup"><span data-stu-id="811b7-126">You can also set how you want additional calls to be handled after this maximum is reached.</span></span> <span data-ttu-id="811b7-127">Лишние вызовы можно отклонить с сигналом "занято", переадлить на другой номер или перенаададовать на голосовую почту.</span><span class="sxs-lookup"><span data-stu-id="811b7-127">Excess calls can be rejected with a busy signal, forwarded to an alternate number, or forwarded to voice mail.</span></span>
    
- <span data-ttu-id="811b7-128">Вы можете настроить обработку пропущенных вызовов (вызовы, которые не были обработаны через определенное время).</span><span class="sxs-lookup"><span data-stu-id="811b7-128">You can configure how you want missed calls (calls not picked up after a certain time) to be handled.</span></span> <span data-ttu-id="811b7-129">Если включить голосовую почту для удостоверения группы, пропущенные звонки автоматически будут переходить на голосовую почту.</span><span class="sxs-lookup"><span data-stu-id="811b7-129">If you enable voice mail for the group identity, missed calls automatically go to voice mail.</span></span> <span data-ttu-id="811b7-130">Если голосовая почта для удостоверения группы (общий номер) не включена, можно отклонить пропущенные вызовы с сигналом "занято", переадлиться на другой номер или отключиться.</span><span class="sxs-lookup"><span data-stu-id="811b7-130">If you do not have voice mail enabled for the group identity (shared number), you can choose for missed calls to be rejected with a busy signal, forwarded to an alternate number, or disconnected.</span></span>
    

