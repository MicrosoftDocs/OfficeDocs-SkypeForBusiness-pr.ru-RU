---
title: Отработка отказа линии связи на исходящих вызовов
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: article
ms.service:
- msteams
- skype-for-business-online
ms.prod: skype-for-business-itpro
localization_priority: Normal
search.appverid: MET150
ms.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
description: Прочтите этот раздел, чтобы узнать, как обрабатывать магистрали отработки отказа при исходящих вызовах из рабочих групп для пограничный контроллер сеансов (SBC).
ms.openlocfilehash: 1f8e7dfd5064b9c3d857165a9a4e2d39565dfeef
ms.sourcegitcommit: a3181bc3707b09c1e3f87c343b38259fdc6dabd2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/14/2018
ms.locfileid: "27271151"
---
# <a name="trunk-failover-on-outbound-calls"></a><span data-ttu-id="cc78e-103">Отработка отказа линии связи на исходящие звонки</span><span class="sxs-lookup"><span data-stu-id="cc78e-103">Trunk failover on outbound calls</span></span>

<span data-ttu-id="cc78e-104">В этом разделе описываются методы, позволяющие избежать магистрали отработки отказа при исходящих звонках--из рабочих групп для пограничный контроллер сеансов (SBC).</span><span class="sxs-lookup"><span data-stu-id="cc78e-104">This topic describes how to avoid trunk failovers on outbound calls--from Teams to the Session Border Controller (SBC).</span></span>

## <a name="failover-on-network-errors"></a><span data-ttu-id="cc78e-105">Отработка отказа на сетевые ошибки</span><span class="sxs-lookup"><span data-stu-id="cc78e-105">Failover on network errors</span></span>

<span data-ttu-id="cc78e-106">Если магистраль не может быть подключена по любой причине, подключение к магистрали же будет попытка из разных центре обработки данных Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="cc78e-106">If a trunk cannot be connected for any reason, the connection to the same trunk will be tried from a different Microsoft Datacenter.</span></span> <span data-ttu-id="cc78e-107">Магистраль не подключен, например, если отказано в подключении к, если время ожидания TLS или наличие ошибок других сетевого уровня.</span><span class="sxs-lookup"><span data-stu-id="cc78e-107">A trunk might not be connected, for example, if a connection is refused, if there is a TLS timeout, or if there are any other network level issues.</span></span>
<span data-ttu-id="cc78e-108">Например подключения не удается Если ограничения доступа администратора SBC только из известных IP-адресов, но забудет для помещения в список управления доступом (ACL) из SBC IP-адреса всех прямой маршрутизации Microsoft центров обработки данных.</span><span class="sxs-lookup"><span data-stu-id="cc78e-108">For example, a connection might fail if an administrator limits access to the SBC only from well-known IP addresses, but forgets to put the IP addresses of all Microsoft Direct Routing datacenters on the Access Control List (ACL) of the SBC.</span></span> 

## <a name="failover-of-specific-sip-codes-received-from-the-session-border-controller-sbc"></a><span data-ttu-id="cc78e-109">Отработка отказа определенных кодов SIP, полученных от пограничный контроллер сеансов (SBC)</span><span class="sxs-lookup"><span data-stu-id="cc78e-109">Failover of specific SIP codes received from the Session Border Controller (SBC)</span></span>

<span data-ttu-id="cc78e-110">Если прямой маршрутизации получает коды ошибок 4xx или 6xx SIP в ответ на приглашение исходящей, вызов считается завершения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="cc78e-110">If Direct Routing receives any 4xx or 6xx SIP error codes in response to an outgoing Invite, the call is considered completed by default.</span></span> <span data-ttu-id="cc78e-111">Исходящий означает, что вызов из группы клиента для общедоступных переключения телефонной сети общего пользования (PSTN) с помощью следующих трафик: клиент групп -> прямой маршрутизации -> SBC -> телефонной сетью.</span><span class="sxs-lookup"><span data-stu-id="cc78e-111">Outgoing means a call from a Teams client to the Public Switched Telephone Network (PSTN) with the following traffic flow: Teams Client -> Direct Routing -> SBC -> Telephony network.</span></span>

<span data-ttu-id="cc78e-112">Список SIP-кодов можно найти в [Session Initiation Protocol (SIP) RFC](https://tools.ietf.org/html/rfc3261).</span><span class="sxs-lookup"><span data-stu-id="cc78e-112">The list of SIP Codes can be found in [Session Initiation Protocol (SIP) RFC](https://tools.ietf.org/html/rfc3261).</span></span>

<span data-ttu-id="cc78e-113">Предположим, ситуации, где SBC дан ответ на входящие приглашения на код «408: время ожидания запроса: серверу не удалось предоставить ответ в рамках подходящее количество времени, например если он не может определить местонахождение пользователя в времени.</span><span class="sxs-lookup"><span data-stu-id="cc78e-113">Assume a situation where an SBC replied on an incoming invite with the code "408 Request Timeout: The server could not produce a response within a suitable amount of time, for example, if it could not determine the location of the user in time.</span></span> <span data-ttu-id="cc78e-114">Клиент может повторить запрос без изменений в любой момент позже.»</span><span class="sxs-lookup"><span data-stu-id="cc78e-114">The client MAY repeat the request without modifications at any later time."</span></span>

<span data-ttu-id="cc78e-115">В этом определенного SBC может возникли неполадки, подключение к вызываемому--возможно из-за неправильной настройкой сети или другая ошибка.</span><span class="sxs-lookup"><span data-stu-id="cc78e-115">This particular SBC might be having difficulties connecting to the callee--perhaps because of a network misconfiguration or other error.</span></span> <span data-ttu-id="cc78e-116">Однако существует один дополнительные SBC в маршрут, который может иметь возможность связаться вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="cc78e-116">However, there is one more SBC in the route which might be able to reach the callee.</span></span>

<span data-ttu-id="cc78e-117">На следующей схеме выполняется вызов на номер телефона, при их изготовителей два маршрута, которые потенциально могут предоставить этот вызов.</span><span class="sxs-lookup"><span data-stu-id="cc78e-117">In the following diagram, when a user makes a call to a phone number, there are two SBCs in the route that can potentially deliver this call.</span></span> <span data-ttu-id="cc78e-118">Изначально SBC1.contoso.com выбран для вызова, но SBC1.contoso.com не смогут получать сетевой PTSN из-за сетевой проблемы.</span><span class="sxs-lookup"><span data-stu-id="cc78e-118">Initially, SBC1.contoso.com is selected for the call, but SBC1.contoso.com isn't able to reach a PTSN network due to a network issue.</span></span>
<span data-ttu-id="cc78e-119">По умолчанию вызов будет завершен в данный момент.</span><span class="sxs-lookup"><span data-stu-id="cc78e-119">By default, the call will be completed at this moment.</span></span> 
 
![Показывает SBC не удается подключиться к ТСОП из-за сетевой проблемы](media/direct-routing-failover-response-codes1.png)

<span data-ttu-id="cc78e-121">Однако это не имеет один дополнительные SBC в маршрут, который потенциально могут обеспечить вызова.</span><span class="sxs-lookup"><span data-stu-id="cc78e-121">But there is one more SBC in the route which potentially can deliver the call.</span></span>
<span data-ttu-id="cc78e-122">Если задан параметр Set-CSOnlinePSTNGateway-Identity sbc1.contoso.com - ReinviteResponceCode «408», будет второй SBC попытка--SBC2.contoso.com на следующей схеме:</span><span class="sxs-lookup"><span data-stu-id="cc78e-122">If you configure the parameter Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com -ReinviteResponceCode "408", the second SBC will be tried-- SBC2.contoso.com in the following diagram:</span></span>

![Показывает маршрутизации для второй SBC](media/direct-routing-failover-response-codes2.png)

<span data-ttu-id="cc78e-124">Установка для параметра - FailoverResponceCodes, указав коды помогает точной настройки маршрута и избежать потенциальных проблем при SBC нельзя сделать звонок из-за сетевой или другие проблемы.</span><span class="sxs-lookup"><span data-stu-id="cc78e-124">Setting the parameter -FailoverResponceCodes and specifying the codes helps you fine tune your routing and avoid potential issues when an SBC cannot make a call due to network or other issues.</span></span>

<span data-ttu-id="cc78e-125">Значения по умолчанию: 408, 503, 504</span><span class="sxs-lookup"><span data-stu-id="cc78e-125">Default values:  408, 503, 504</span></span>

