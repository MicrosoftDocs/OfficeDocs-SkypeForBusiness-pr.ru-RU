---
title: Прямая маршрутизация телефонной системы
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 10/17/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
ms.reviewer: nmurav
search.appverid: MET150
f1.keywords:
- NOCSH
description: Уведомление о прямом маршрутинге звонка
appliesto:
- Microsoft Teams
localization_priority: Normal
ms.openlocfilehash: 0320ebc6abfc0e3f3d720fbab03abc698b26849c
ms.sourcegitcommit: 6cfaadec5782ca7316db36472bd0be20217da693
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/29/2020
ms.locfileid: "42341808"
---
# <a name="manage-call-notifications"></a><span data-ttu-id="437e9-103">Управление уведомлениями о звонках</span><span class="sxs-lookup"><span data-stu-id="437e9-103">Manage call notifications</span></span>

<span data-ttu-id="437e9-104">В этой статье описано, как управлять уведомлениями о звонках для пользователей.</span><span class="sxs-lookup"><span data-stu-id="437e9-104">This article describes how to manage call notifications for your users.</span></span> <span data-ttu-id="437e9-105">Конечные точки звонка можно настроить как для Teams, так и для сторонней частной ветви Exchange (УАКС) или контроллера границы сеанса (SBC).</span><span class="sxs-lookup"><span data-stu-id="437e9-105">You can configure call endpoints to both Teams and to a third-party Private Branch Exchange (PBX) or Session Border Controller (SBC).</span></span>  <span data-ttu-id="437e9-106">Это полезно, например, если вы хотите одновременно отправить звонок на мобильные и настольные телефоны пользователя.</span><span class="sxs-lookup"><span data-stu-id="437e9-106">This is useful, for example, if you want to send a call to a user's mobile and desk phones at the same time.</span></span>   

<span data-ttu-id="437e9-107">На следующей схеме У Ирены есть две конечные точки:</span><span class="sxs-lookup"><span data-stu-id="437e9-107">In the following diagram, user Irena has two endpoints:</span></span>

- <span data-ttu-id="437e9-108">Конечная Teams</span><span class="sxs-lookup"><span data-stu-id="437e9-108">A Teams endpoint</span></span>
- <span data-ttu-id="437e9-109">Телефон SIP, подключенный к стороне SBC</span><span class="sxs-lookup"><span data-stu-id="437e9-109">A SIP phone connected to a third-party SBC</span></span>

<span data-ttu-id="437e9-110">Когда поступает звонок, SBC разнонаправка звонка между телефонная система Прямой маршрутизов и сторонним SBC.</span><span class="sxs-lookup"><span data-stu-id="437e9-110">When a call arrives, the SBC forks the call between Phone System Direct Routing and the third-party SBC.</span></span>


![Диаграмма, на которой показаны Teams конечные точки](media/direct-routing-call-notification-1.png)

<span data-ttu-id="437e9-112">Если звонок принимается на fork 2 (сторонним SBC), Teams создает уведомление о пропущенных звонках.</span><span class="sxs-lookup"><span data-stu-id="437e9-112">If the call is accepted on Fork 2 (by the third-party SBC), Teams will generate a “Missed Call” notification.</span></span>  

<span data-ttu-id="437e9-113">Вы можете отключить уведомление "Пропущенный звонок", настроив SBC для отправки отмены в fork 1 следующим образом:</span><span class="sxs-lookup"><span data-stu-id="437e9-113">You can prevent the “Missed Call” notification by configuring the SBC to send a Cancel on Fork 1 as follows:</span></span>

<span data-ttu-id="437e9-114">ПРИЧИНА: SIP; cause=200;text"Звонок завершен в другом месте"</span><span class="sxs-lookup"><span data-stu-id="437e9-114">REASON: SIP; cause=200;text”Call completed elsewhere”</span></span> 

<span data-ttu-id="437e9-115">Обратите внимание, что звонок не будет зарегистрирован в записях сведений о звонках Телефон (Майкрософт) Система в качестве успешного звонка.</span><span class="sxs-lookup"><span data-stu-id="437e9-115">Note that the call will not be registered in the call detail records of Microsoft Phone System as a successful call.</span></span> <span data-ttu-id="437e9-116">Звонок будет зарегистрирован как "Попытка" с итоговым кодом SIP "487", итоговым подкодомом Майкрософт "540200" и итоговой фразой кода SIP "Звонок выполнен в другом месте".</span><span class="sxs-lookup"><span data-stu-id="437e9-116">The call will be registered as an “Attempt” with Final SIP Code “487”, Final Microsoft subcode “540200”, and Final SIP Code Phrase “Call completed elsewhere”.</span></span>  <span data-ttu-id="437e9-117">(Чтобы просмотреть записи о звонках, перейдите на портал администрирования Teams, аналитику и отчеты, отчеты об использовании, а затем выберите Использование ОКП.)</span><span class="sxs-lookup"><span data-stu-id="437e9-117">(To view the call detail records, go the Teams Admin portal, Analytics and Reports, Usage Reports, and select PSTN Usage.)</span></span>


<span data-ttu-id="437e9-118">На приведенной ниже схеме показано, как выглядит SIP для Fork 1, объясняется поток зова и ожидаемая ПРИЧИНА в сообщении об отмене.</span><span class="sxs-lookup"><span data-stu-id="437e9-118">The diagram below illustrates the SIP ladder for Fork 1, explains the call flow, and the expected REASON in the Cancel message.</span></span> 

![Диаграмма, на которой показаны Teams конечные точки](media/direct-routing-call-notification-2.png)
