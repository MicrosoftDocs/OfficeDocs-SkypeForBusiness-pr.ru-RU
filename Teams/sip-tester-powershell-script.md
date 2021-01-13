---
title: Сценарий PowerShell для тестирования подключений к граничным контроллерам прямого маршрутинга сеанса
author: cichur
ms.author: v-cichur
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
ms.openlocfilehash: c52febae3d734af49d1b23c7c65ceb0c2f746f7a
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834279"
---
# <a name="powershell-script-to-test-direct-routing-session-border-controller-connections"></a><span data-ttu-id="13813-103">Сценарий PowerShell для тестирования подключений к граничным контроллерам прямого маршрутинга сеанса</span><span class="sxs-lookup"><span data-stu-id="13813-103">PowerShell script to test Direct Routing Session Border Controller connections</span></span>

<span data-ttu-id="13813-104">Клиент SIP Tester — это пример сценария PowerShell, который можно использовать для проверки подключений граничного контроллера SBC к прямой маршрутике в Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="13813-104">SIP Tester client is a sample PowerShell script that you can use to test Direct Routing Session Border Controller (SBC) connections in Microsoft Teams.</span></span> <span data-ttu-id="13813-105">Этот сценарий проверяет основные функции связи SIP с прямой маршрутицией, сопряженной с клиентом.</span><span class="sxs-lookup"><span data-stu-id="13813-105">This script tests basic functionality of a customer-paired Session Initiation Protocol (SIP) trunk with Direct Routing.</span></span>

<span data-ttu-id="13813-106">Сценарий сообщает тест SIP тест-тесту, ждет результат, а затем представляет его в учитываемом для человека формате.</span><span class="sxs-lookup"><span data-stu-id="13813-106">The script submits an SIP test to the test runner, waits for the result, and then presents it in a human-readable format.</span></span> <span data-ttu-id="13813-107">С помощью этого сценария можно проверить следующие сценарии:</span><span class="sxs-lookup"><span data-stu-id="13813-107">You can use this script to test the following scenarios:</span></span>

- <span data-ttu-id="13813-108">Исходящие и входящие звонки</span><span class="sxs-lookup"><span data-stu-id="13813-108">Outbound and inbound calls</span></span>
- <span data-ttu-id="13813-109">Одновременный звонок</span><span class="sxs-lookup"><span data-stu-id="13813-109">Simultaneous ring</span></span>
- <span data-ttu-id="13813-110">Медианаука</span><span class="sxs-lookup"><span data-stu-id="13813-110">Media escalation</span></span>
- <span data-ttu-id="13813-111">Консультация и передача</span><span class="sxs-lookup"><span data-stu-id="13813-111">Consultative transfer</span></span>

## <a name="download-the-script-and-documentation"></a><span data-ttu-id="13813-112">Скачивание сценария и документации</span><span class="sxs-lookup"><span data-stu-id="13813-112">Download the script and documentation</span></span>

<span data-ttu-id="13813-113">Скачайте сценарий клиента [SIP Tester и документацию.](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/sip-tester-client/siptesterclient.zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="13813-113">Download the [SIP Tester client script and documentation](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/sip-tester-client/siptesterclient.zip?raw=true).</span></span>

  > [!NOTE]
  > <span data-ttu-id="13813-114">Сценарий клиента SIP Tester поддерживает только adal.ps версии 3.19.8.1.</span><span class="sxs-lookup"><span data-stu-id="13813-114">SIP Tester client script only supports adal.ps version 3.19.8.1.</span></span> <span data-ttu-id="13813-115">Если используется более поздней версии adal.ps возвращается ошибка.</span><span class="sxs-lookup"><span data-stu-id="13813-115">An error will be returned if a later version of the adal.ps is used.</span></span>
  
  
