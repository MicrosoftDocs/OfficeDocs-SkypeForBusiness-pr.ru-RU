---
title: Дополнительные сведения об идентификаторе вызывающей линии и имени вызывающего абонента
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Calling Plans
description: Узнайте, почему необходимо добавить авторизованного пользователя, который можно внести изменения в учетную запись, при использовании мастера новый локальный заказ номер порта.
ms.openlocfilehash: 846abfd5b6973a02ad1a7388b45a79ec709695a0
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "23865280"
---
# <a name="more-about-calling-line-id-and-calling-party-name"></a><span data-ttu-id="44570-103">Дополнительные сведения об идентификаторе вызывающей линии и имени вызывающего абонента</span><span class="sxs-lookup"><span data-stu-id="44570-103">More about Calling Line ID and Calling Party Name</span></span>

<span data-ttu-id="44570-104">CallerID, как оно обычно используется для ссылки, фактически состоит из подключенных пользователей идентифицируемый следующая информация:</span><span class="sxs-lookup"><span data-stu-id="44570-104">CallerID, as it is typically referred to, actually consists of two user-facing identifiable pieces of information:</span></span>
    - <span data-ttu-id="44570-105">Номер телефона (обычно обозначается как CLID или телефонной линии идентификатор)</span><span class="sxs-lookup"><span data-stu-id="44570-105">A phone number (typically referred to as CLID or calling line ID)</span></span> 
    - <span data-ttu-id="44570-106">Вызов имени субъекта (обычно называется CNAM), который может быть не более 15 символов в длину.</span><span class="sxs-lookup"><span data-stu-id="44570-106">Calling party name (typically referred to as CNAM) which can be up to 15 characters in length.</span></span> 

<span data-ttu-id="44570-107">При вызове CLID (номер телефона) перенаправляется в целевой поставщика (также известной как прерывающие передающую).</span><span class="sxs-lookup"><span data-stu-id="44570-107">When a call is made, the CLID (phone number) is routed to the destination's carrier (also known as the terminating carrier).</span></span> <span data-ttu-id="44570-108">Сведения о CNAM для вызова может отображаться или не может перенаправляться на вызов, как это зависит от того, как страны производитель реализовал CNAM (если вообще).</span><span class="sxs-lookup"><span data-stu-id="44570-108">The CNAM info for the call may or may not be routed with the call as this depends on how the country has implemented CNAM (if at all).</span></span> <span data-ttu-id="44570-109">Надежности CNAM доставки с помощью вызова может отличаться в зависимости от страны и связи, которые либо в качестве посредника обработки вызова и/или выполнения определенного поставщика.</span><span class="sxs-lookup"><span data-stu-id="44570-109">The reliability of CNAM delivery with the call varies depending on the country and carriers which handle the call either as an intermediary and/or a terminating carrier.</span></span> 

<span data-ttu-id="44570-110">CLID & CNAM передачи несет ответственность за прерывающие передающую предположить, что прерывающие оператор должен поддерживать CLID & CNAM функциональные возможности, а также предоставляют последних записей для оба значения.</span><span class="sxs-lookup"><span data-stu-id="44570-110">CLID & CNAM transmission is the responsibility of the terminating carrier insofar as the terminating carrier must support CLID & CNAM functionality as well as provide up to date records for both values.</span></span> <span data-ttu-id="44570-111">Корпорация Майкрософт предоставляет значения CLID надежно при вызовов, но эти значения могут не будет поддерживаться без изменений после их проходить через промежуточный поставщика или выполнения определенного поставщика.</span><span class="sxs-lookup"><span data-stu-id="44570-111">Microsoft reliably provides CLID values when originating calls, but those values may not be kept intact once they pass through an intermediary carrier or the terminating carrier.</span></span> <span data-ttu-id="44570-112">К сожалению в том случае, если значение CLID изменен, опущен или по передающую промежуточных или прерывающие усекаются, практически не ресурсов устранении таких проблем в телефонной сети общего корпорацией Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="44570-112">Unfortunately, in the event the CLID value is changed, omitted or truncated by the intermediary or terminating carrier, Microsoft has little to no recourse in correcting such problems in the public telephone network.</span></span>

<span data-ttu-id="44570-113">Несоответствия в CNAM может быть вызвана задержки в связи промежуточных или выполнения определенного обновления CNAM сведения в достоверности баз данных, как в случае в США.</span><span class="sxs-lookup"><span data-stu-id="44570-113">Inconsistencies in CNAM can be caused by delays in intermediate or terminating carriers refreshing CNAM info in authoritative databases as in the case of the United States.</span></span> <span data-ttu-id="44570-114">В странах, где есть база данных не достоверных CNAM, рекомендациям отдельного поставщика также может вызвать проблемы с CNAM данные, поступающие в списке с помощью вызова.</span><span class="sxs-lookup"><span data-stu-id="44570-114">In countries where there is no authoritative database for CNAM, individual carrier practices can also cause problems with CNAM information arriving in tact with the call.</span></span> <span data-ttu-id="44570-115">Microsoft в настоящее время не поддерживает отправляющего CNAM сведения только в США в стране.»</span><span class="sxs-lookup"><span data-stu-id="44570-115">Microsoft currently does not support originating CNAM information in countries other than the United States."</span></span>

## <a name="related-topics"></a><span data-ttu-id="44570-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="44570-116">Related topics</span></span>


