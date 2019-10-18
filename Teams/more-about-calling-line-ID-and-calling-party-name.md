---
title: Дополнительные сведения об ИД линии вызова и имени вызывающей стороны
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Calling Plans
description: Сведения о том, почему необходимо добавить уполномоченного пользователя, который может вносить изменения в учетную запись при использовании мастера создания заказа на перенос локальных номеров.
ms.openlocfilehash: 833bb27aa34b16601485437be9e25e2e41c2bf4e
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2019
ms.locfileid: "37573383"
---
# <a name="more-about-calling-line-id-and-calling-party-name"></a><span data-ttu-id="6350a-103">Дополнительные сведения об ИД линии вызова и имени вызывающей стороны</span><span class="sxs-lookup"><span data-stu-id="6350a-103">More about Calling Line ID and Calling Party Name</span></span>

<span data-ttu-id="6350a-104">Каллерид, как правило, говорят, что она состоит из двух понятных пользователю данных:</span><span class="sxs-lookup"><span data-stu-id="6350a-104">CallerID, as it is typically referred to, actually consists of two user-facing identifiable pieces of information:</span></span>
    - <span data-ttu-id="6350a-105">Номер телефона (обычно он называется CLID или ИДЕНТИФИКАТОРом строки вызова)</span><span class="sxs-lookup"><span data-stu-id="6350a-105">A phone number (typically referred to as CLID or calling line ID)</span></span> 
    - <span data-ttu-id="6350a-106">Имя вызывающего абонента (обычно называется КНАМ), которое может иметь длину до 15 символов.</span><span class="sxs-lookup"><span data-stu-id="6350a-106">Calling party name (typically referred to as CNAM) which can be up to 15 characters in length.</span></span> 

<span data-ttu-id="6350a-107">После совершения звонка CLID (номер телефона) перенаправляется на перевозчик назначения (также называемый оконечным перевозчиком).</span><span class="sxs-lookup"><span data-stu-id="6350a-107">When a call is made, the CLID (phone number) is routed to the destination's carrier (also known as the terminating carrier).</span></span> <span data-ttu-id="6350a-108">Сведения о КНАМ звонках могут перенаправляться с помощью звонка, так как она зависит от того, как страна реализовалась КНАМ (если вообще есть).</span><span class="sxs-lookup"><span data-stu-id="6350a-108">The CNAM info for the call may or may not be routed with the call as this depends on how the country has implemented CNAM (if at all).</span></span> <span data-ttu-id="6350a-109">Надежность КНАМ доставки с звонком зависит от страны и абонентов, которые обрабатывают звонок либо как посредник, либо как оконечный оператор.</span><span class="sxs-lookup"><span data-stu-id="6350a-109">The reliability of CNAM delivery with the call varies depending on the country and carriers which handle the call either as an intermediary and/or a terminating carrier.</span></span> 

<span data-ttu-id="6350a-110">CLID & КНАМ передача является обязанностью оконечного перевозчика, так как оконечный перевозчик должен поддерживать CLID & КНАМ функции, а также предоставлять актуальные записи для обоих значений.</span><span class="sxs-lookup"><span data-stu-id="6350a-110">CLID & CNAM transmission is the responsibility of the terminating carrier insofar as the terminating carrier must support CLID & CNAM functionality as well as provide up to date records for both values.</span></span> <span data-ttu-id="6350a-111">Корпорация Microsoft надежно обеспечивает значения CLID при создании вызовов, но эти значения могут не изменяться после прохождения через промежуточные салазки или оконечные салазки.</span><span class="sxs-lookup"><span data-stu-id="6350a-111">Microsoft reliably provides CLID values when originating calls, but those values may not be kept intact once they pass through an intermediary carrier or the terminating carrier.</span></span> <span data-ttu-id="6350a-112">К сожалению, в случае, если значение CLID изменено, пропущено или не обрезается промежуточной или завершающей несущей, корпорация Майкрософт не может устранить проблему, описанную в устранении подобных проблем в общедоступной телефонной сети.</span><span class="sxs-lookup"><span data-stu-id="6350a-112">Unfortunately, in the event the CLID value is changed, omitted or truncated by the intermediary or terminating carrier, Microsoft has little to no recourse in correcting such problems in the public telephone network.</span></span>

<span data-ttu-id="6350a-113">Несоответствия в КНАМ могут быть вызваны задержкой в промежуточных или оконечных перевозчиках обновлять информацию о КНАМ в удостоверяющих базах данных, как в случае США.</span><span class="sxs-lookup"><span data-stu-id="6350a-113">Inconsistencies in CNAM can be caused by delays in intermediate or terminating carriers refreshing CNAM info in authoritative databases as in the case of the United States.</span></span> <span data-ttu-id="6350a-114">В странах, где нет удостоверяющих баз данных для КНАМ, индивидуальные методики также могут привести к проблемам с КНАМ сведениями, которые поступают с этим звонком.</span><span class="sxs-lookup"><span data-stu-id="6350a-114">In countries where there is no authoritative database for CNAM, individual carrier practices can also cause problems with CNAM information arriving in tact with the call.</span></span> <span data-ttu-id="6350a-115">Microsoft в настоящее время не поддерживает первоначальную информацию о КНАМ в странах, отличных от Соединенных Штатов. "</span><span class="sxs-lookup"><span data-stu-id="6350a-115">Microsoft currently does not support originating CNAM information in countries other than the United States."</span></span>

## <a name="related-topics"></a><span data-ttu-id="6350a-116">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="6350a-116">Related topics</span></span>


