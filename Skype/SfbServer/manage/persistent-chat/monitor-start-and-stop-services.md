---
title: Мониторинг, запуск и остановка служб сохраняемого чата в Skype для бизнеса Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b6b28595-f702-4ecf-8115-e4104b87da89
description: 'Сводка: сведения о запуске, остановке и мониторинге служб сохраняемого чата в Skype для бизнеса Server 2015.'
ms.openlocfilehash: 846d7376e1a3e9bd06ae74c20ee0812c8c78bbeb
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817478"
---
# <a name="monitor-start-and-stop-the-persistent-chat-services-in-skype-for-business-server-2015"></a><span data-ttu-id="bc68b-103">Мониторинг, запуск и остановка служб сохраняемого чата в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="bc68b-103">Monitor, start, and stop the Persistent Chat services in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="bc68b-104">**Сводка:** Инструкции по запуску, остановке и мониторингу служб сохраняемого чата в Skype для бизнеса Server 2015.</span><span class="sxs-lookup"><span data-stu-id="bc68b-104">**Summary:** Learn how to start, stop, and monitor the Persistent Chat services in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="bc68b-105">Службы постоянной видеосвязи и проверки соответствия требованиям в чате входят в топологию сервера Skype для бизнеса и поэтому могут быть отслеживаемы, остановлены и запущены с помощью следующих командлетов:</span><span class="sxs-lookup"><span data-stu-id="bc68b-105">The Persistent Chat services and Persistent Chat Compliance services are part of the Skype for Business Server topology and can therefore be monitored, stopped, and started by using the following cmdlets:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="bc68b-106">get-CsWindowsService</span><span class="sxs-lookup"><span data-stu-id="bc68b-106">get-CsWindowsService</span></span>  <br/> |<span data-ttu-id="bc68b-107">Возвращает подробные сведения о компонентах Skype для бизнеса Server 2015, которые выполняются в качестве служб Windows.</span><span class="sxs-lookup"><span data-stu-id="bc68b-107">Returns detailed information about Skype for Business Server 2015 components that run as Windows services.</span></span>  <br/> |
|<span data-ttu-id="bc68b-108">start-CsWindowsService</span><span class="sxs-lookup"><span data-stu-id="bc68b-108">start-CsWindowsService</span></span>  <br/> |<span data-ttu-id="bc68b-109">Запуск службы.</span><span class="sxs-lookup"><span data-stu-id="bc68b-109">Starts the service.</span></span>  <br/> |
|<span data-ttu-id="bc68b-110">stop-CsWindowsService</span><span class="sxs-lookup"><span data-stu-id="bc68b-110">stop-CsWindowsService</span></span>  <br/> |<span data-ttu-id="bc68b-111">Остановка службы.</span><span class="sxs-lookup"><span data-stu-id="bc68b-111">Stops the service.</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="bc68b-112">Сохраняемый чат доступен в Skype для бизнеса Server 2015, но больше не поддерживается в Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="bc68b-112">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="bc68b-113">Такие же функции доступны в Teams.</span><span class="sxs-lookup"><span data-stu-id="bc68b-113">The same functionality is available in Teams.</span></span> <span data-ttu-id="bc68b-114">Дополнительные сведения см. в статье [Начало перехода на Microsoft Teams](/microsoftteams/upgrade-start-here).</span><span class="sxs-lookup"><span data-stu-id="bc68b-114">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="bc68b-115">Если вам нужно использовать сохраняемый чат, то вы можете либо перенести пользователей, которым нужна эта функция, в Teams, либо продолжать использовать Skype для бизнеса Server 2015.</span><span class="sxs-lookup"><span data-stu-id="bc68b-115">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 

<span data-ttu-id="bc68b-116">Подробные сведения об использовании командлетов см. в разделе [Skype for Business Server 2015 Management Shell](../management-shell.md).</span><span class="sxs-lookup"><span data-stu-id="bc68b-116">For detailed information about how to use the cmdlets, see [Skype for Business Server 2015 Management Shell](../management-shell.md).</span></span>
  

