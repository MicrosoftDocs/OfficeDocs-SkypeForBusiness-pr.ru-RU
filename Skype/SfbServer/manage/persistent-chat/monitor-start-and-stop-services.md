---
title: Мониторинг, запуск и остановка служб сохраняемого чата в Skype для бизнеса Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b6b28595-f702-4ecf-8115-e4104b87da89
description: 'Сводка: Узнайте, как для запуска, остановки и отслеживать службы Persistent Chat в Скайп для Business Server 2015.'
ms.openlocfilehash: ee817dc5ed76ca5981ab0429da82f74ee5327583
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30890236"
---
# <a name="monitor-start-and-stop-the-persistent-chat-services-in-skype-for-business-server-2015"></a><span data-ttu-id="de627-103">Мониторинг, запуск и остановка служб сохраняемого чата в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="de627-103">Monitor, start, and stop the Persistent Chat services in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="de627-104">**Сводка:** Узнайте, как для запуска, остановки и отслеживать службы Persistent Chat в Скайп для Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="de627-104">**Summary:** Learn how to start, stop, and monitor the Persistent Chat services in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="de627-105">Сохраняемый чат служб и соответствие сохраняемого чата являются частью Скайп для топологии Business Server и могут таким образом отслеживать, остановлена и работы с помощью следующих командлетов:</span><span class="sxs-lookup"><span data-stu-id="de627-105">The Persistent Chat services and Persistent Chat Compliance services are part of the Skype for Business Server topology and can therefore be monitored, stopped, and started by using the following cmdlets:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="de627-106">get-CsWindowsService</span><span class="sxs-lookup"><span data-stu-id="de627-106">get-CsWindowsService</span></span>  <br/> |<span data-ttu-id="de627-107">Возвращает подробные сведения о Скайп для компонентов Business Server 2015, на которых выполняется как службы Windows.</span><span class="sxs-lookup"><span data-stu-id="de627-107">Returns detailed information about Skype for Business Server 2015 components that run as Windows services.</span></span>  <br/> |
|<span data-ttu-id="de627-108">start-CsWindowsService</span><span class="sxs-lookup"><span data-stu-id="de627-108">start-CsWindowsService</span></span>  <br/> |<span data-ttu-id="de627-109">Запуск службы.</span><span class="sxs-lookup"><span data-stu-id="de627-109">Starts the service.</span></span>  <br/> |
|<span data-ttu-id="de627-110">stop-CsWindowsService</span><span class="sxs-lookup"><span data-stu-id="de627-110">stop-CsWindowsService</span></span>  <br/> |<span data-ttu-id="de627-111">Остановка службы.</span><span class="sxs-lookup"><span data-stu-id="de627-111">Stops the service.</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="de627-112">Сохраняемый чат доступна в Скайп для Business Server 2015, но больше не поддерживается в Скайп для Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="de627-112">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="de627-113">Те же функциональные возможности доступны в группах.</span><span class="sxs-lookup"><span data-stu-id="de627-113">The same functionality is available in Teams.</span></span> <span data-ttu-id="de627-114">Для получения дополнительных сведений см [Реализация из Скайп для бизнеса для групп Майкрософт](/microsoftteams/journey-skypeforbusiness-teams).</span><span class="sxs-lookup"><span data-stu-id="de627-114">For more information, see [Journey from Skype for Business to Microsoft Teams](/microsoftteams/journey-skypeforbusiness-teams).</span></span> <span data-ttu-id="de627-115">Если необходимо использовать сохраняемого чата, возможны либо перенос пользователей, которым требуется эта функция групп, или для дальнейшего использования Скайп для Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="de627-115">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 

<span data-ttu-id="de627-116">Подробные сведения об использовании командлетов см. в разделе [Skype for Business Server 2015 Management Shell](../management-shell.md).</span><span class="sxs-lookup"><span data-stu-id="de627-116">For detailed information about how to use the cmdlets, see [Skype for Business Server 2015 Management Shell](../management-shell.md).</span></span>
  

