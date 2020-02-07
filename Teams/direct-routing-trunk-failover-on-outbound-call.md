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
description: В этой статье рассказывается о том, как обрабатывать переходные запросы на магистральные линии по исходящим звонкам из Teams на контроллер границ сеансов (SBC).
ms.openlocfilehash: c88394cba0a98316ac272901a6ab2972e9eaf3c8
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41836181"
---
# <a name="trunk-failover-on-outbound-calls"></a><span data-ttu-id="be86b-103">Отработка отказа канала связи при исходящих звонках</span><span class="sxs-lookup"><span data-stu-id="be86b-103">Trunk failover on outbound calls</span></span>

<span data-ttu-id="be86b-104">В этой статье описано, как избежать переходных на магистральные перемещения по исходящим вызовам — от Teams до контроллера границ сеансов (SBC).</span><span class="sxs-lookup"><span data-stu-id="be86b-104">This topic describes how to avoid trunk failovers on outbound calls--from Teams to the Session Border Controller (SBC).</span></span>

## <a name="failover-on-network-errors"></a><span data-ttu-id="be86b-105">Отработка отказа при ошибках сети</span><span class="sxs-lookup"><span data-stu-id="be86b-105">Failover on network errors</span></span>

<span data-ttu-id="be86b-106">Если магистраль не может быть подключено по какой-либо причине, подключение к одной и той же магистрали будет выполняться из другого центра обработки данных Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="be86b-106">If a trunk cannot be connected for any reason, the connection to the same trunk will be tried from a different Microsoft Datacenter.</span></span> <span data-ttu-id="be86b-107">Канал связи может не подключаться, например, в случае отказа в соединении, в случае превышения времени ожидания TLS или в случае наличия других проблем на уровне сети.</span><span class="sxs-lookup"><span data-stu-id="be86b-107">A trunk might not be connected, for example, if a connection is refused, if there is a TLS timeout, or if there are any other network level issues.</span></span>
<span data-ttu-id="be86b-108">Например, подключение может завершиться с ошибкой, если администратор ограничивает доступ к SBC только по известным IP-адресам, но при этом вы забываете IP-адреса всех центров обработки данных Microsoft Direct Routing в списке управления доступом (ACL) SBC.</span><span class="sxs-lookup"><span data-stu-id="be86b-108">For example, a connection might fail if an administrator limits access to the SBC only from well-known IP addresses, but forgets to put the IP addresses of all Microsoft Direct Routing datacenters on the Access Control List (ACL) of the SBC.</span></span> 

## <a name="failover-of-specific-sip-codes-received-from-the-session-border-controller-sbc"></a><span data-ttu-id="be86b-109">Отработка отказа определенных кодов SIP, полученных от контроллера границ сеанса (SBC)</span><span class="sxs-lookup"><span data-stu-id="be86b-109">Failover of specific SIP codes received from the Session Border Controller (SBC)</span></span>

<span data-ttu-id="be86b-110">Если прямая маршрутизация получает коды ошибок SIP 4xx или 6xx в ответ на исходящий приглашение, вызов считается завершенным по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="be86b-110">If Direct Routing receives any 4xx or 6xx SIP error codes in response to an outgoing Invite, the call is considered completed by default.</span></span> <span data-ttu-id="be86b-111">"Исходящие" — вызов из клиента Teams в коммутируемую телефонную сеть общего пользования (КТСОП) с потоком трафика: клиент Teams — > прямая маршрутизация — > SBC > телефонной сети.</span><span class="sxs-lookup"><span data-stu-id="be86b-111">Outgoing means a call from a Teams client to the Public Switched Telephone Network (PSTN) with the following traffic flow: Teams Client -> Direct Routing -> SBC -> Telephony network.</span></span>

<span data-ttu-id="be86b-112">Список кодов SIP можно найти в [RFC по протоколу SIP](https://tools.ietf.org/html/rfc3261).</span><span class="sxs-lookup"><span data-stu-id="be86b-112">The list of SIP Codes can be found in [Session Initiation Protocol (SIP) RFC](https://tools.ietf.org/html/rfc3261).</span></span>

<span data-ttu-id="be86b-113">Предположим, что SBC ответил на входящее приглашение с кодом "408. тайм-аут запроса: сервер не может получить ответ в течение подходящего промежутка времени, например, если ему не удалось определить расположение пользователя в определенный момент времени.</span><span class="sxs-lookup"><span data-stu-id="be86b-113">Assume a situation where an SBC replied on an incoming invite with the code "408 Request Timeout: The server could not produce a response within a suitable amount of time, for example, if it could not determine the location of the user in time.</span></span> <span data-ttu-id="be86b-114">Клиент может повторять запрос без изменений позже.</span><span class="sxs-lookup"><span data-stu-id="be86b-114">The client MAY repeat the request without modifications at any later time."</span></span>

<span data-ttu-id="be86b-115">Этот конкретный SBC может испытывать трудности при подключении к вызываемому абоненту, возможно, из-за ошибки настройки сети или других ошибок.</span><span class="sxs-lookup"><span data-stu-id="be86b-115">This particular SBC might be having difficulties connecting to the callee--perhaps because of a network misconfiguration or other error.</span></span> <span data-ttu-id="be86b-116">Тем не менее, в маршруте есть еще один SBC, который может достичь вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="be86b-116">However, there is one more SBC in the route which might be able to reach the callee.</span></span>

<span data-ttu-id="be86b-117">На приведенной ниже схеме, когда пользователь выполняет звонок на номер телефона, в маршруте есть два типа SBCs, которые могут привести к появлении этого звонка.</span><span class="sxs-lookup"><span data-stu-id="be86b-117">In the following diagram, when a user makes a call to a phone number, there are two SBCs in the route that can potentially deliver this call.</span></span> <span data-ttu-id="be86b-118">Первоначально для звонка SBC1.contoso.com выбрано, но SBC1.contoso.com не может подключиться к сети ОКТС из-за проблемы с сетью.</span><span class="sxs-lookup"><span data-stu-id="be86b-118">Initially, SBC1.contoso.com is selected for the call, but SBC1.contoso.com isn't able to reach a PTSN network due to a network issue.</span></span>
<span data-ttu-id="be86b-119">По умолчанию в данный момент звонок будет завершен.</span><span class="sxs-lookup"><span data-stu-id="be86b-119">By default, the call will be completed at this moment.</span></span> 
 
![Схема, показывающая, что SBC не может достичь КТСОП из-за ошибки сети](media/direct-routing-failover-response-codes1.png)

<span data-ttu-id="be86b-121">Но в маршруте есть еще один SBC, который потенциально может допустить звонок.</span><span class="sxs-lookup"><span data-stu-id="be86b-121">But there is one more SBC in the route which potentially can deliver the call.</span></span>
<span data-ttu-id="be86b-122">Если вы настроили `Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com -FailoverResponseCodes "408"`параметр, второй одноранговый элемент SBC будет пытаться получить SBC2.contoso.com на следующей схеме:</span><span class="sxs-lookup"><span data-stu-id="be86b-122">If you configure the parameter `Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com -FailoverResponseCodes "408"`, the second SBC will be tried-- SBC2.contoso.com in the following diagram:</span></span>

![Схема, показывающая маршрут к второму SBC](media/direct-routing-failover-response-codes2.png)

<span data-ttu-id="be86b-124">Установка параметра-Фаиловерреспонсекодес и указание кода помогает настроить маршрутизацию и избежать потенциальных проблем, когда SBC не может вызвать из-за сети или других проблем.</span><span class="sxs-lookup"><span data-stu-id="be86b-124">Setting the parameter -FailoverResponseCodes and specifying the codes helps you fine tune your routing and avoid potential issues when an SBC cannot make a call due to network or other issues.</span></span>

<span data-ttu-id="be86b-125">Значения по умолчанию: 408, 503, 504</span><span class="sxs-lookup"><span data-stu-id="be86b-125">Default values:  408, 503, 504</span></span>

