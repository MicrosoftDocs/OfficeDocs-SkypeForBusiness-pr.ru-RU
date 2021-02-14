---
title: Мониторинг, запуск и остановка служб сохраняемой беседы в Skype для бизнеса Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b6b28595-f702-4ecf-8115-e4104b87da89
description: Сводка. Узнайте, как запускать, останавливать и отслеживать службы сохраняемой беседы в Skype для бизнеса Server 2015.
ms.openlocfilehash: 31285fe5f7eefaa6579f2891a4b29111324de22d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814139"
---
# <a name="monitor-start-and-stop-the-persistent-chat-services-in-skype-for-business-server-2015"></a><span data-ttu-id="6d566-103">Мониторинг, запуск и остановка служб сохраняемой беседы в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="6d566-103">Monitor, start, and stop the Persistent Chat services in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="6d566-104">**Сводка:** Узнайте, как запускать, останавливать и отслеживать службы сохраняемой беседы в Skype для бизнеса Server 2015.</span><span class="sxs-lookup"><span data-stu-id="6d566-104">**Summary:** Learn how to start, stop, and monitor the Persistent Chat services in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="6d566-105">Службы сохраняемого чата и службы соответствия сохраняемого чата являются частью топологии Skype для бизнеса Server и поэтому могут отслеживаться, остановлены и запущены с помощью следующих cmdlets:</span><span class="sxs-lookup"><span data-stu-id="6d566-105">The Persistent Chat services and Persistent Chat Compliance services are part of the Skype for Business Server topology and can therefore be monitored, stopped, and started by using the following cmdlets:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="6d566-106">get-CsWindowsService</span><span class="sxs-lookup"><span data-stu-id="6d566-106">get-CsWindowsService</span></span>  <br/> |<span data-ttu-id="6d566-107">Возвращает подробные сведения о компонентах Skype для бизнеса Server 2015, которые работают как службы Windows.</span><span class="sxs-lookup"><span data-stu-id="6d566-107">Returns detailed information about Skype for Business Server 2015 components that run as Windows services.</span></span>  <br/> |
|<span data-ttu-id="6d566-108">start-CsWindowsService</span><span class="sxs-lookup"><span data-stu-id="6d566-108">start-CsWindowsService</span></span>  <br/> |<span data-ttu-id="6d566-109">Запускает службу.</span><span class="sxs-lookup"><span data-stu-id="6d566-109">Starts the service.</span></span>  <br/> |
|<span data-ttu-id="6d566-110">stop-CsWindowsService</span><span class="sxs-lookup"><span data-stu-id="6d566-110">stop-CsWindowsService</span></span>  <br/> |<span data-ttu-id="6d566-111">Останавливает службу.</span><span class="sxs-lookup"><span data-stu-id="6d566-111">Stops the service.</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="6d566-112">Сохраняемая беседа доступна в Skype для бизнеса Server 2015, но больше не поддерживается в Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="6d566-112">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="6d566-113">Такие же функции доступны в Teams.</span><span class="sxs-lookup"><span data-stu-id="6d566-113">The same functionality is available in Teams.</span></span> <span data-ttu-id="6d566-114">Дополнительные сведения [см. в сведениях о том,](/microsoftteams/upgrade-start-here)как начать обновление Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="6d566-114">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="6d566-115">Если необходимо использовать сохраняемого чата, вы можете либо перенести пользователей, которым требуются эти функции, в Teams, либо продолжить использование Skype для бизнеса Server 2015.</span><span class="sxs-lookup"><span data-stu-id="6d566-115">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 

<span data-ttu-id="6d566-116">Подробные сведения об использовании этих cmdlets см. в описании [skype для бизнеса Server 2015 Management Shell.](../management-shell.md)</span><span class="sxs-lookup"><span data-stu-id="6d566-116">For detailed information about how to use the cmdlets, see [Skype for Business Server 2015 Management Shell](../management-shell.md).</span></span>
  

