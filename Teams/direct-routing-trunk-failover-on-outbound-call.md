---
title: Отработка отказа канала связи при исходящих звонках
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Из этой темы вы узнаете, как обрабатывать отработки сбойов связи при исходяльных звонках из Teams на контроллер границы сеанса (SBC).
ms.openlocfilehash: c88394cba0a98316ac272901a6ab2972e9eaf3c8
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41836181"
---
# <a name="trunk-failover-on-outbound-calls"></a><span data-ttu-id="b290c-103">Отработка отказа канала связи при исходящих звонках</span><span class="sxs-lookup"><span data-stu-id="b290c-103">Trunk failover on outbound calls</span></span>

<span data-ttu-id="b290c-104">В этой статье описано, как избежать отката на магистрали при исходяльных звонках — от Teams до граничного контроллера сеанса (SBC).</span><span class="sxs-lookup"><span data-stu-id="b290c-104">This topic describes how to avoid trunk failovers on outbound calls--from Teams to the Session Border Controller (SBC).</span></span>

## <a name="failover-on-network-errors"></a><span data-ttu-id="b290c-105">Отбой в сети</span><span class="sxs-lookup"><span data-stu-id="b290c-105">Failover on network errors</span></span>

<span data-ttu-id="b290c-106">Если по какой-либо причине не удается подключение к той же самой связи, будет попросят подключение к той же самой связи из другого центра обработки данных Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="b290c-106">If a trunk cannot be connected for any reason, the connection to the same trunk will be tried from a different Microsoft Datacenter.</span></span> <span data-ttu-id="b290c-107">Например, при отклонении подключения, при ином времени tLS или других проблемах на уровне сети связь может быть не соединена.</span><span class="sxs-lookup"><span data-stu-id="b290c-107">A trunk might not be connected, for example, if a connection is refused, if there is a TLS timeout, or if there are any other network level issues.</span></span>
<span data-ttu-id="b290c-108">Например, подключение может быть со сбой, если администратор ограничивает доступ к SBC только с хорошо известных IP-адресов, но забудет поместить IP-адреса всех центрах обработки данных Microsoft Direct Routing в список управления доступом (ACL) SBC.</span><span class="sxs-lookup"><span data-stu-id="b290c-108">For example, a connection might fail if an administrator limits access to the SBC only from well-known IP addresses, but forgets to put the IP addresses of all Microsoft Direct Routing datacenters on the Access Control List (ACL) of the SBC.</span></span> 

## <a name="failover-of-specific-sip-codes-received-from-the-session-border-controller-sbc"></a><span data-ttu-id="b290c-109">Отбой определенных кодов SIP, полученных с контроллера границы сеанса (SBC)</span><span class="sxs-lookup"><span data-stu-id="b290c-109">Failover of specific SIP codes received from the Session Border Controller (SBC)</span></span>

<span data-ttu-id="b290c-110">Если direct Routing получает коды ошибок SIP с кодами 4xx или 6xx в ответ на исходяющие приглашения, вызов считается завершенным по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="b290c-110">If Direct Routing receives any 4xx or 6xx SIP error codes in response to an outgoing Invite, the call is considered completed by default.</span></span> <span data-ttu-id="b290c-111">Исходятая означает звонок из клиента Teams в телефонную сеть общего перейти на телефонную сеть (STN) со следующим потоком трафика: Клиент Teams -> Прямая маршрутия -> SBC -> телефонная сеть.</span><span class="sxs-lookup"><span data-stu-id="b290c-111">Outgoing means a call from a Teams client to the Public Switched Telephone Network (PSTN) with the following traffic flow: Teams Client -> Direct Routing -> SBC -> Telephony network.</span></span>

<span data-ttu-id="b290c-112">Список кодов SIP можно найти в [RFC SIP.](https://tools.ietf.org/html/rfc3261)</span><span class="sxs-lookup"><span data-stu-id="b290c-112">The list of SIP Codes can be found in [Session Initiation Protocol (SIP) RFC](https://tools.ietf.org/html/rfc3261).</span></span>

<span data-ttu-id="b290c-113">Предположим, что сервер SBC ответил на входящее приглашение с кодом "408 Запрос времени и времени: сервер не смог получить ответ в течение подходящего времени, например, если не смог определить местоположение пользователя вовремя".</span><span class="sxs-lookup"><span data-stu-id="b290c-113">Assume a situation where an SBC replied on an incoming invite with the code "408 Request Timeout: The server could not produce a response within a suitable amount of time, for example, if it could not determine the location of the user in time.</span></span> <span data-ttu-id="b290c-114">Клиент может повторить запрос без изменений в любой момент".</span><span class="sxs-lookup"><span data-stu-id="b290c-114">The client MAY repeat the request without modifications at any later time."</span></span>

<span data-ttu-id="b290c-115">Возможно, у конкретного запроса SBC возникли сложности при подключении к звонясу, например из-за неправильной оценки сети или другой ошибки.</span><span class="sxs-lookup"><span data-stu-id="b290c-115">This particular SBC might be having difficulties connecting to the callee--perhaps because of a network misconfiguration or other error.</span></span> <span data-ttu-id="b290c-116">Тем не менее, в маршруте есть еще одна SBC, которая может иметь возможность связаться с вызываемой.</span><span class="sxs-lookup"><span data-stu-id="b290c-116">However, there is one more SBC in the route which might be able to reach the callee.</span></span>

<span data-ttu-id="b290c-117">На следующей схеме, когда пользователь звонит на номер телефона, в маршруте могут быть две БСК, которые могут доставить этот звонок.</span><span class="sxs-lookup"><span data-stu-id="b290c-117">In the following diagram, when a user makes a call to a phone number, there are two SBCs in the route that can potentially deliver this call.</span></span> <span data-ttu-id="b290c-118">Изначально SBC1.contoso.com для звонка, но SBC1.contoso.com не может связаться с сетью ТСТС из-за проблемы с сетью.</span><span class="sxs-lookup"><span data-stu-id="b290c-118">Initially, SBC1.contoso.com is selected for the call, but SBC1.contoso.com isn't able to reach a PTSN network due to a network issue.</span></span>
<span data-ttu-id="b290c-119">По умолчанию звонок будет завершен на данный момент.</span><span class="sxs-lookup"><span data-stu-id="b290c-119">By default, the call will be completed at this moment.</span></span> 
 
![Схема, показывающая, что SBC не удается связаться с STN из-за проблемы с сетью](media/direct-routing-failover-response-codes1.png)

<span data-ttu-id="b290c-121">Но в маршруте есть еще один SBC, который может доставить звонок.</span><span class="sxs-lookup"><span data-stu-id="b290c-121">But there is one more SBC in the route which potentially can deliver the call.</span></span>
<span data-ttu-id="b290c-122">Если вы настроили параметр, будет попробована вторая SBC — SBC2.contoso.com `Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com -FailoverResponseCodes "408"` на следующей схеме:</span><span class="sxs-lookup"><span data-stu-id="b290c-122">If you configure the parameter `Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com -FailoverResponseCodes "408"`, the second SBC will be tried-- SBC2.contoso.com in the following diagram:</span></span>

![Схема, на которой показана маршрутия ко второму SBC](media/direct-routing-failover-response-codes2.png)

<span data-ttu-id="b290c-124">Установка параметра -FailoverResponseCodes и указание кодов помогает настроить маршрутику и избежать потенциальных проблем, когда SBC не может позвонить из-за сетевых или других проблем.</span><span class="sxs-lookup"><span data-stu-id="b290c-124">Setting the parameter -FailoverResponseCodes and specifying the codes helps you fine tune your routing and avoid potential issues when an SBC cannot make a call due to network or other issues.</span></span>

<span data-ttu-id="b290c-125">Значения по умолчанию: 408, 503, 504</span><span class="sxs-lookup"><span data-stu-id="b290c-125">Default values:  408, 503, 504</span></span>

