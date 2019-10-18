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
appliesto:
- Microsoft Teams
ms.openlocfilehash: c6df8ee654696ceef89c36a354d943c97139bf8b
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2019
ms.locfileid: "37568679"
---
# <a name="powershell-script-to-test-direct-routing-session-border-controller-connections"></a><span data-ttu-id="404ac-103">Сценарий PowerShell для проверки соединения с контроллером границ между прямыми сеансами маршрутизации</span><span class="sxs-lookup"><span data-stu-id="404ac-103">PowerShell script to test Direct Routing Session Border Controller connections</span></span>

<span data-ttu-id="404ac-104">Клиент тестеров SIP — это образец сценария PowerShell, который можно использовать для тестирования подключений между однонаправленными контроллерами границ (SBC) для связи в Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="404ac-104">SIP Tester client is a sample PowerShell script that you can use to test Direct Routing Session Border Controller (SBC) connections in Microsoft Teams.</span></span> <span data-ttu-id="404ac-105">Этот сценарий проверяет основные функциональные возможности магистрального протокола SIP с прямой маршрутизацией.</span><span class="sxs-lookup"><span data-stu-id="404ac-105">This script tests basic functionality of a customer-paired Session Initiation Protocol (SIP) trunk with Direct Routing.</span></span>

<span data-ttu-id="404ac-106">Сценарий отправляет тест SIP в средство выполнения тестов, ждет результата, а затем представляет его в удобочитаемом формате.</span><span class="sxs-lookup"><span data-stu-id="404ac-106">The script submits an SIP test to the test runner, waits for the result, and then presents it in a human-readable format.</span></span> <span data-ttu-id="404ac-107">Вы можете использовать этот сценарий, чтобы протестировать указанные ниже сценарии.</span><span class="sxs-lookup"><span data-stu-id="404ac-107">You can use this script to test the following scenarios:</span></span>

- <span data-ttu-id="404ac-108">Входящие и исходящие звонки</span><span class="sxs-lookup"><span data-stu-id="404ac-108">Outbound and inbound calls</span></span>
- <span data-ttu-id="404ac-109">Одновременный звонок</span><span class="sxs-lookup"><span data-stu-id="404ac-109">Simultaneous ring</span></span>
- <span data-ttu-id="404ac-110">Эскалация мультимедиа</span><span class="sxs-lookup"><span data-stu-id="404ac-110">Media escalation</span></span>
- <span data-ttu-id="404ac-111">Передача консултативе</span><span class="sxs-lookup"><span data-stu-id="404ac-111">Consultative transfer</span></span>

## <a name="download-the-script-and-documentation"></a><span data-ttu-id="404ac-112">Скачайте сценарий и документацию</span><span class="sxs-lookup"><span data-stu-id="404ac-112">Download the script and documentation</span></span>

<span data-ttu-id="404ac-113">Скачайте [клиентский сценарий тестеров SIP и документацию](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/sip-tester-client/siptesterclient.zip?raw=true).</span><span class="sxs-lookup"><span data-stu-id="404ac-113">Download the [SIP Tester client script and documentation](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/sip-tester-client/siptesterclient.zip?raw=true).</span></span>