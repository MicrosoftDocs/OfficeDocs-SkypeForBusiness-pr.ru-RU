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
ms.collection:
- M365-voice
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 344bf59d401e43c40c6f643b334c2f34311d6cbe
ms.sourcegitcommit: 8665603fae8408ccbc083dd59cb01936ebe96c58
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2020
ms.locfileid: "43116695"
---
# <a name="powershell-script-to-test-direct-routing-session-border-controller-connections"></a><span data-ttu-id="8e629-103">Сценарий PowerShell для проверки соединения с контроллером границ между прямыми сеансами маршрутизации</span><span class="sxs-lookup"><span data-stu-id="8e629-103">PowerShell script to test Direct Routing Session Border Controller connections</span></span>

<span data-ttu-id="8e629-104">Клиент тестеров SIP — это образец сценария PowerShell, который можно использовать для тестирования подключений между однонаправленными контроллерами границ (SBC) для связи в Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="8e629-104">SIP Tester client is a sample PowerShell script that you can use to test Direct Routing Session Border Controller (SBC) connections in Microsoft Teams.</span></span> <span data-ttu-id="8e629-105">Этот сценарий проверяет основные функциональные возможности магистрального протокола SIP с прямой маршрутизацией.</span><span class="sxs-lookup"><span data-stu-id="8e629-105">This script tests basic functionality of a customer-paired Session Initiation Protocol (SIP) trunk with Direct Routing.</span></span>

<span data-ttu-id="8e629-106">Сценарий отправляет тест SIP в средство выполнения тестов, ждет результата, а затем представляет его в удобочитаемом формате.</span><span class="sxs-lookup"><span data-stu-id="8e629-106">The script submits an SIP test to the test runner, waits for the result, and then presents it in a human-readable format.</span></span> <span data-ttu-id="8e629-107">Вы можете использовать этот сценарий, чтобы протестировать указанные ниже сценарии.</span><span class="sxs-lookup"><span data-stu-id="8e629-107">You can use this script to test the following scenarios:</span></span>

- <span data-ttu-id="8e629-108">Входящие и исходящие звонки</span><span class="sxs-lookup"><span data-stu-id="8e629-108">Outbound and inbound calls</span></span>
- <span data-ttu-id="8e629-109">Одновременный звонок</span><span class="sxs-lookup"><span data-stu-id="8e629-109">Simultaneous ring</span></span>
- <span data-ttu-id="8e629-110">Эскалация мультимедиа</span><span class="sxs-lookup"><span data-stu-id="8e629-110">Media escalation</span></span>
- <span data-ttu-id="8e629-111">Передача consultative</span><span class="sxs-lookup"><span data-stu-id="8e629-111">Consultative transfer</span></span>

## <a name="download-the-script-and-documentation"></a><span data-ttu-id="8e629-112">Скачайте сценарий и документацию</span><span class="sxs-lookup"><span data-stu-id="8e629-112">Download the script and documentation</span></span>

<span data-ttu-id="8e629-113">Скачайте [клиентский сценарий тестеров SIP и документацию](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/sip-tester-client/siptesterclient.zip?raw=true).</span><span class="sxs-lookup"><span data-stu-id="8e629-113">Download the [SIP Tester client script and documentation](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/sip-tester-client/siptesterclient.zip?raw=true).</span></span>

  > [!NOTE]
  > <span data-ttu-id="8e629-114">Клиентский сценарий тестера SIP поддерживает только adal.ps версии 3.19.8.1.</span><span class="sxs-lookup"><span data-stu-id="8e629-114">SIP Tester client script only supports adal.ps version 3.19.8.1.</span></span> <span data-ttu-id="8e629-115">Если используется более поздняя версия adal.ps, будет возвращена ошибка.</span><span class="sxs-lookup"><span data-stu-id="8e629-115">An error will be returned if a later version of the adal.ps is used.</span></span>
  
  
