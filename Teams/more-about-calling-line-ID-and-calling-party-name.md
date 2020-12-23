---
title: Дополнительные сведения об ИД линии вызова и имени вызывающей стороны
ms.author: mikeplum
author: MikePlumleyMSFT
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
f1.keywords:
- CSH
ms.custom:
- Calling Plans
description: Узнайте, зачем добавлять в учетную запись уполномоченного лица, который может вносить изменения при использовании мастера заказов на перенос нового номера.
ms.openlocfilehash: db64a5d1a7e7a5969f66d67d6b056ec6947d44bb
ms.sourcegitcommit: 2874aec7768bb46ed4506c1a2d431841f47190bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/26/2020
ms.locfileid: "47255402"
---
# <a name="more-about-calling-line-id-and-calling-party-name"></a><span data-ttu-id="06c51-103">Дополнительные сведения об ИД линии вызова и имени вызывающей стороны</span><span class="sxs-lookup"><span data-stu-id="06c51-103">More about Calling Line ID and Calling Party Name</span></span>

<span data-ttu-id="06c51-104">Как правило, "ИД вызываемого звонка" состоит из двух идентифицируемых пользователем фрагментов данных:</span><span class="sxs-lookup"><span data-stu-id="06c51-104">CallerID, as it is typically referred to, actually consists of two user-facing identifiable pieces of information:</span></span>
    - <span data-ttu-id="06c51-105">Номер телефона (обычно он называется CLID или ИД телефонной строки)</span><span class="sxs-lookup"><span data-stu-id="06c51-105">A phone number (typically referred to as CLID or calling line ID)</span></span> 
    - <span data-ttu-id="06c51-106">Имя вызываемой стороны (обычно называется CNAM) длиной до 15 знаков.</span><span class="sxs-lookup"><span data-stu-id="06c51-106">Calling party name (typically referred to as CNAM) which can be up to 15 characters in length.</span></span> 

<span data-ttu-id="06c51-107">После звонка clID (номер телефона) перенаправлен в оператор назначения (который также называется оператором, который завершает работу).</span><span class="sxs-lookup"><span data-stu-id="06c51-107">When a call is made, the CLID (phone number) is routed to the destination's carrier (also known as the terminating carrier).</span></span> <span data-ttu-id="06c51-108">Данные CNAM для звонка могут быть перенаадваны с помощью звонка, так как это зависит от того, как в стране реализована CNAM (если она реализована).</span><span class="sxs-lookup"><span data-stu-id="06c51-108">The CNAM info for the call may or may not be routed with the call as this depends on how the country has implemented CNAM (if at all).</span></span> <span data-ttu-id="06c51-109">Надежность доставки CNAM с вызовом зависит от страны и операторов, которые обрабатывают звонок как промежуточный и/или о конечного оператора связи.</span><span class="sxs-lookup"><span data-stu-id="06c51-109">The reliability of CNAM delivery with the call varies depending on the country and carriers which handle the call either as an intermediary and/or a terminating carrier.</span></span> 

<span data-ttu-id="06c51-110">ClID & CNAM — это ответственность о концевом операторе, который должен поддерживать функции CLID & CNAM, а также предоставлять последние записи для обоих значений.</span><span class="sxs-lookup"><span data-stu-id="06c51-110">CLID & CNAM transmission is the responsibility of the terminating carrier insofar as the terminating carrier must support CLID & CNAM functionality as well as provide up to date records for both values.</span></span> <span data-ttu-id="06c51-111">Корпорация Майкрософт надежно предоставляет значения CLID при звонках, но они могут не сохраниться без изменений, если они проходят через промежуточного оператора связи или о концевую службу.</span><span class="sxs-lookup"><span data-stu-id="06c51-111">Microsoft reliably provides CLID values when originating calls, but those values may not be kept intact once they pass through an intermediary carrier or the terminating carrier.</span></span> <span data-ttu-id="06c51-112">К сожалению, в случае изменения, усечения или усечения значения CLID промежуточным или завершаенным оператором, корпорация Майкрософт практически не имеет прав на исправление таких проблем в телефонной сети.</span><span class="sxs-lookup"><span data-stu-id="06c51-112">Unfortunately, in the event the CLID value is changed, omitted or truncated by the intermediary or terminating carrier, Microsoft has little to no recourse in correcting such problems in the public telephone network.</span></span>

<span data-ttu-id="06c51-113">Несоответствия в CNAM могут быть вызваны задержками промежуточного или завершающегося обновления данных CNAM в полном базах данных, как в случае с США.</span><span class="sxs-lookup"><span data-stu-id="06c51-113">Inconsistencies in CNAM can be caused by delays in intermediate or terminating carriers refreshing CNAM info in authoritative databases as in the case of the United States.</span></span> <span data-ttu-id="06c51-114">В странах, где нет полномочного базы данных для CNAM, отдельные методики связи также могут привести к проблемам с данными CNAM, поступающими во время звонка.</span><span class="sxs-lookup"><span data-stu-id="06c51-114">In countries where there is no authoritative database for CNAM, individual carrier practices can also cause problems with CNAM information arriving intact with the call.</span></span> <span data-ttu-id="06c51-115">В настоящее время корпорация Майкрософт не поддерживает данные CNAM в других странах, кроме США".</span><span class="sxs-lookup"><span data-stu-id="06c51-115">Microsoft currently does not support originating CNAM information in countries other than the United States."</span></span>

## <a name="related-topics"></a><span data-ttu-id="06c51-116">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="06c51-116">Related topics</span></span>


