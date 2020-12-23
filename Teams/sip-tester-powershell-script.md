---
title: Сценарий PowerShell для тестирования подключений к контроллеру границ прямого сеанса маршрутинга
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.reviewer: filippse
ms.service: msteams
audience: admin
description: Используйте этот пример сценария PowerShell, чтобы протестировать прямое подключение к контроллеру границ сеанса маршрутинга в Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 43d1514eff811461ac8b6ad73f7c2a215205f4e3
ms.sourcegitcommit: 69ff557c79d6b1a3d1089fe5c8f5c8ed8ff7431e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/30/2020
ms.locfileid: "43951264"
---
# <a name="powershell-script-to-test-direct-routing-session-border-controller-connections"></a><span data-ttu-id="a7d68-103">Сценарий PowerShell для тестирования подключений к контроллеру границ прямого сеанса маршрутинга</span><span class="sxs-lookup"><span data-stu-id="a7d68-103">PowerShell script to test Direct Routing Session Border Controller connections</span></span>

<span data-ttu-id="a7d68-104">Клиент SIP Tester — это пример сценария PowerShell, который можно использовать для проверки подключений граничного контроллера SBC к прямой маршрутике в Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="a7d68-104">SIP Tester client is a sample PowerShell script that you can use to test Direct Routing Session Border Controller (SBC) connections in Microsoft Teams.</span></span> <span data-ttu-id="a7d68-105">Этот сценарий проверяет основные функции связи SIP с прямой маршрутицией, сопряженной с клиентом.</span><span class="sxs-lookup"><span data-stu-id="a7d68-105">This script tests basic functionality of a customer-paired Session Initiation Protocol (SIP) trunk with Direct Routing.</span></span>

<span data-ttu-id="a7d68-106">Сценарий сообщает тест SIP тест-тесту, ждет результат, а затем представляет его в учитываемом для человека формате.</span><span class="sxs-lookup"><span data-stu-id="a7d68-106">The script submits an SIP test to the test runner, waits for the result, and then presents it in a human-readable format.</span></span> <span data-ttu-id="a7d68-107">Этот сценарий можно использовать для проверки следующих сценариев:</span><span class="sxs-lookup"><span data-stu-id="a7d68-107">You can use this script to test the following scenarios:</span></span>

- <span data-ttu-id="a7d68-108">Исходящие и входящие звонки</span><span class="sxs-lookup"><span data-stu-id="a7d68-108">Outbound and inbound calls</span></span>
- <span data-ttu-id="a7d68-109">Одновременный звонок</span><span class="sxs-lookup"><span data-stu-id="a7d68-109">Simultaneous ring</span></span>
- <span data-ttu-id="a7d68-110">Медианаука</span><span class="sxs-lookup"><span data-stu-id="a7d68-110">Media escalation</span></span>
- <span data-ttu-id="a7d68-111">Консультация и передача</span><span class="sxs-lookup"><span data-stu-id="a7d68-111">Consultative transfer</span></span>

## <a name="download-the-script-and-documentation"></a><span data-ttu-id="a7d68-112">Скачивание сценария и документации</span><span class="sxs-lookup"><span data-stu-id="a7d68-112">Download the script and documentation</span></span>

<span data-ttu-id="a7d68-113">Скачайте сценарий клиента [SIP Tester и документацию.](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/sip-tester-client/siptesterclient.zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="a7d68-113">Download the [SIP Tester client script and documentation](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/sip-tester-client/siptesterclient.zip?raw=true).</span></span>

  > [!NOTE]
  > <span data-ttu-id="a7d68-114">Сценарий клиента SIP Tester поддерживает только adal.ps версии 3.19.8.1.</span><span class="sxs-lookup"><span data-stu-id="a7d68-114">SIP Tester client script only supports adal.ps version 3.19.8.1.</span></span> <span data-ttu-id="a7d68-115">Если используется более поздней версии adal.ps возвращается ошибка.</span><span class="sxs-lookup"><span data-stu-id="a7d68-115">An error will be returned if a later version of the adal.ps is used.</span></span>
  
  
