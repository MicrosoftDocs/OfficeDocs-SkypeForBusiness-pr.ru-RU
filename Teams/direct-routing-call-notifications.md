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
description: Уведомление о переадресации прямых звонков
appliesto:
- Microsoft Teams
localization_priority: Normal
ms.openlocfilehash: 3d53245d241435e869dbdbeb15dcb1c81e18ff96
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41837599"
---
# <a name="manage-call-notifications"></a><span data-ttu-id="44ea8-103">Управление уведомлениями о звонках</span><span class="sxs-lookup"><span data-stu-id="44ea8-103">Manage call notifications</span></span>

<span data-ttu-id="44ea8-104">В этой статье описано, как управлять уведомлениями о звонках для пользователей.</span><span class="sxs-lookup"><span data-stu-id="44ea8-104">This article describes how to manage call notifications for your users.</span></span> <span data-ttu-id="44ea8-105">Вы можете настроить конечные точки звонков для Teams и с помощью УАТС или контроллера границ сеанса (SBC) стороннего поставщика.</span><span class="sxs-lookup"><span data-stu-id="44ea8-105">You can configure call endpoints to both Teams and to a third-party Private Branch Exchange (PBX) or Session Border Controller (SBC).</span></span>  <span data-ttu-id="44ea8-106">Это полезно, например, если вы хотите отправить звонок на мобильные и стационарные телефоны пользователей одновременно.</span><span class="sxs-lookup"><span data-stu-id="44ea8-106">This is useful, for example, if you want to send a call to a user's mobile and desk phones at the same time.</span></span>   

<span data-ttu-id="44ea8-107">На приведенной ниже схеме пользователь Ирена имеет две конечные точки:</span><span class="sxs-lookup"><span data-stu-id="44ea8-107">In the following diagram, user Irena has two endpoints:</span></span>

- <span data-ttu-id="44ea8-108">Конечная точка Teams</span><span class="sxs-lookup"><span data-stu-id="44ea8-108">A Teams endpoint</span></span>
- <span data-ttu-id="44ea8-109">Телефон SIP, связанный с односторонним SBC</span><span class="sxs-lookup"><span data-stu-id="44ea8-109">A SIP phone connected to a third-party SBC</span></span>

<span data-ttu-id="44ea8-110">При появлении звонка объект SBC разделяет звонок между прямой маршрутизацией телефонной системы и сторонним SBC.</span><span class="sxs-lookup"><span data-stu-id="44ea8-110">When a call arrives, the SBC forks the call between Phone System Direct Routing and the third-party SBC.</span></span>


![Диаграмма, на которой показаны конечные точки разветвленных групп](media/direct-routing-call-notification-1.png)

<span data-ttu-id="44ea8-112">Если звонок будет принят на вилке 2 (третьим SBC-сторонним), Teams создаст уведомление "Пропущенный Звонок".</span><span class="sxs-lookup"><span data-stu-id="44ea8-112">If the call is accepted on Fork 2 (by the third-party SBC), Teams will generate a “Missed Call” notification.</span></span>  

<span data-ttu-id="44ea8-113">Вы можете запретить уведомление "Пропущенный Звонок", настроив SBC таким образом, чтобы он отправлял команду "отменить" на вилке 1, как описано ниже.</span><span class="sxs-lookup"><span data-stu-id="44ea8-113">You can prevent the “Missed Call” notification by configuring the SBC to send a Cancel on Fork 1 as follows:</span></span>

<span data-ttu-id="44ea8-114">ПРИЧИНА: SIP; Причина = 200; текст "вызов завершен в другом месте"</span><span class="sxs-lookup"><span data-stu-id="44ea8-114">REASON: SIP; cause=200;text”Call completed elsewhere”</span></span> 

<span data-ttu-id="44ea8-115">Обратите внимание, что при успешном звонке звонок не будет регистрироваться в записях с подробными сведениями о звонке в Microsoft Phone System.</span><span class="sxs-lookup"><span data-stu-id="44ea8-115">Note that the call will not be registered in the call detail records of Microsoft Phone System as a successful call.</span></span> <span data-ttu-id="44ea8-116">Этот звонок будет зарегистрирован как "попытка" с окончательным кодом SIP "487", окончательная версия Microsoft "540200" и окончательная кодовая фраза SIP "вызов завершен в другом месте".</span><span class="sxs-lookup"><span data-stu-id="44ea8-116">The call will be registered as an “Attempt” with Final SIP Code “487”, Final Microsoft subcode “540200”, and Final SIP Code Phrase “Call completed elsewhere”.</span></span>   <span data-ttu-id="44ea8-117">(Чтобы просмотреть записи с подробными сведениями о звонке, перейдите на портал администрирования группы, анализ и отчеты, отчеты об использовании и выберите использование КТСОП.)</span><span class="sxs-lookup"><span data-stu-id="44ea8-117">(To view the call detail records, go the Teams Admin portal, Analytics and Reports, Usage Reports, and select PSTN Usage.)</span></span>


<span data-ttu-id="44ea8-118">На приведенной ниже схеме показана лестница SIP для вилки 1, объясняется поток вызова и ожидаемая причина в сообщении об отмене.</span><span class="sxs-lookup"><span data-stu-id="44ea8-118">The diagram below illustrates the SIP ladder for Fork 1, explains the call flow, and the expected REASON in the Cancel message.</span></span> 

![Диаграмма, на которой показаны конечные точки разветвленных групп](media/direct-routing-call-notification-2.png)
