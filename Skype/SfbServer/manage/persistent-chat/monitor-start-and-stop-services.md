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
localization_priority: Normal
ms.assetid: b6b28595-f702-4ecf-8115-e4104b87da89
description: 'Сводка: сведения о запуске, остановке и мониторинге служб сохраняемого чата в Skype для бизнеса Server 2015.'
ms.openlocfilehash: 161bda3cb02bf6208b4db9f1c6825d3fe433eeca
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279293"
---
# <a name="monitor-start-and-stop-the-persistent-chat-services-in-skype-for-business-server-2015"></a><span data-ttu-id="ffadb-103">Мониторинг, запуск и остановка служб сохраняемого чата в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="ffadb-103">Monitor, start, and stop the Persistent Chat services in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="ffadb-104">**Сводка:** Инструкции по запуску, остановке и мониторингу служб сохраняемого чата в Skype для бизнеса Server 2015.</span><span class="sxs-lookup"><span data-stu-id="ffadb-104">**Summary:** Learn how to start, stop, and monitor the Persistent Chat services in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="ffadb-105">Службы постоянной видеосвязи и проверки соответствия требованиям в чате входят в топологию сервера Skype для бизнеса и поэтому могут быть отслеживаемы, остановлены и запущены с помощью следующих командлетов:</span><span class="sxs-lookup"><span data-stu-id="ffadb-105">The Persistent Chat services and Persistent Chat Compliance services are part of the Skype for Business Server topology and can therefore be monitored, stopped, and started by using the following cmdlets:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="ffadb-106">get-CsWindowsService</span><span class="sxs-lookup"><span data-stu-id="ffadb-106">get-CsWindowsService</span></span>  <br/> |<span data-ttu-id="ffadb-107">Возвращает подробные сведения о компонентах Skype для бизнеса Server 2015, которые выполняются в качестве служб Windows.</span><span class="sxs-lookup"><span data-stu-id="ffadb-107">Returns detailed information about Skype for Business Server 2015 components that run as Windows services.</span></span>  <br/> |
|<span data-ttu-id="ffadb-108">start-CsWindowsService</span><span class="sxs-lookup"><span data-stu-id="ffadb-108">start-CsWindowsService</span></span>  <br/> |<span data-ttu-id="ffadb-109">Запуск службы.</span><span class="sxs-lookup"><span data-stu-id="ffadb-109">Starts the service.</span></span>  <br/> |
|<span data-ttu-id="ffadb-110">stop-CsWindowsService</span><span class="sxs-lookup"><span data-stu-id="ffadb-110">stop-CsWindowsService</span></span>  <br/> |<span data-ttu-id="ffadb-111">Остановка службы.</span><span class="sxs-lookup"><span data-stu-id="ffadb-111">Stops the service.</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="ffadb-112">Сохраняемый чат доступен в Skype для бизнеса Server 2015, но больше не поддерживается в Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="ffadb-112">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="ffadb-113">Эта функция доступна в Teams.</span><span class="sxs-lookup"><span data-stu-id="ffadb-113">The same functionality is available in Teams.</span></span> <span data-ttu-id="ffadb-114">Дополнительные сведения можно найти в разделе [путешествие из Skype для бизнеса в Microsoft Teams](/microsoftteams/journey-skypeforbusiness-teams).</span><span class="sxs-lookup"><span data-stu-id="ffadb-114">For more information, see [Journey from Skype for Business to Microsoft Teams](/microsoftteams/journey-skypeforbusiness-teams).</span></span> <span data-ttu-id="ffadb-115">Если вы хотите использовать сохраняемый чат, вы можете либо перенести пользователей, которым требуются эти функции, в Teams, либо продолжить работу с Skype для бизнеса Server 2015.</span><span class="sxs-lookup"><span data-stu-id="ffadb-115">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 

<span data-ttu-id="ffadb-116">Подробные сведения об использовании командлетов см. в разделе [Skype for Business Server 2015 Management Shell](../management-shell.md).</span><span class="sxs-lookup"><span data-stu-id="ffadb-116">For detailed information about how to use the cmdlets, see [Skype for Business Server 2015 Management Shell](../management-shell.md).</span></span>
  

