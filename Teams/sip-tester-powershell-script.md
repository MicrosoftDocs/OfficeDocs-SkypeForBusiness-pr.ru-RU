---
title: Сценарий PowerShell для проверки соединения с контроллером границ между прямыми сеансами маршрутизации
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.reviewer: filippse
ms.service: msteams
audience: admin
description: Используйте этот пример сценария PowerShell для тестирования подключений между контроллерами границ для сеансов прямого маршрутизации в Microsoft Teams.
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
# <a name="powershell-script-to-test-direct-routing-session-border-controller-connections"></a><span data-ttu-id="ca3dd-103">Сценарий PowerShell для проверки соединения с контроллером границ между прямыми сеансами маршрутизации</span><span class="sxs-lookup"><span data-stu-id="ca3dd-103">PowerShell script to test Direct Routing Session Border Controller connections</span></span>

<span data-ttu-id="ca3dd-104">Клиент тестеров SIP — это образец сценария PowerShell, который можно использовать для тестирования подключений между однонаправленными контроллерами границ (SBC) для связи в Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="ca3dd-104">SIP Tester client is a sample PowerShell script that you can use to test Direct Routing Session Border Controller (SBC) connections in Microsoft Teams.</span></span> <span data-ttu-id="ca3dd-105">Этот сценарий проверяет основные функциональные возможности магистрального протокола SIP с прямой маршрутизацией.</span><span class="sxs-lookup"><span data-stu-id="ca3dd-105">This script tests basic functionality of a customer-paired Session Initiation Protocol (SIP) trunk with Direct Routing.</span></span>

<span data-ttu-id="ca3dd-106">Сценарий отправляет тест SIP в средство выполнения тестов, ждет результата, а затем представляет его в удобочитаемом формате.</span><span class="sxs-lookup"><span data-stu-id="ca3dd-106">The script submits an SIP test to the test runner, waits for the result, and then presents it in a human-readable format.</span></span> <span data-ttu-id="ca3dd-107">Вы можете использовать этот сценарий, чтобы протестировать указанные ниже сценарии.</span><span class="sxs-lookup"><span data-stu-id="ca3dd-107">You can use this script to test the following scenarios:</span></span>

- <span data-ttu-id="ca3dd-108">Входящие и исходящие звонки</span><span class="sxs-lookup"><span data-stu-id="ca3dd-108">Outbound and inbound calls</span></span>
- <span data-ttu-id="ca3dd-109">Одновременный звонок</span><span class="sxs-lookup"><span data-stu-id="ca3dd-109">Simultaneous ring</span></span>
- <span data-ttu-id="ca3dd-110">Эскалация мультимедиа</span><span class="sxs-lookup"><span data-stu-id="ca3dd-110">Media escalation</span></span>
- <span data-ttu-id="ca3dd-111">Передача consultative</span><span class="sxs-lookup"><span data-stu-id="ca3dd-111">Consultative transfer</span></span>

## <a name="download-the-script-and-documentation"></a><span data-ttu-id="ca3dd-112">Скачайте сценарий и документацию</span><span class="sxs-lookup"><span data-stu-id="ca3dd-112">Download the script and documentation</span></span>

<span data-ttu-id="ca3dd-113">Скачайте [клиентский сценарий тестеров SIP и документацию](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/sip-tester-client/siptesterclient.zip?raw=true).</span><span class="sxs-lookup"><span data-stu-id="ca3dd-113">Download the [SIP Tester client script and documentation](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/sip-tester-client/siptesterclient.zip?raw=true).</span></span>

  > [!NOTE]
  > <span data-ttu-id="ca3dd-114">Клиентский сценарий тестера SIP поддерживает только adal.ps версии 3.19.8.1.</span><span class="sxs-lookup"><span data-stu-id="ca3dd-114">SIP Tester client script only supports adal.ps version 3.19.8.1.</span></span> <span data-ttu-id="ca3dd-115">Если используется более поздняя версия adal.ps, будет возвращена ошибка.</span><span class="sxs-lookup"><span data-stu-id="ca3dd-115">An error will be returned if a later version of the adal.ps is used.</span></span>
  
  
