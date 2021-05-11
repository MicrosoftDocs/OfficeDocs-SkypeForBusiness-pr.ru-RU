---
title: Дополнительные сведения об ИД линии вызова и имени вызывающей стороны
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: roykuntz, jenstr
ms.topic: article
ms.tgt.pltfrm: cloud
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business Online
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Calling Plans
ms.service: msteams
description: Узнайте о том, как узнать ИД строки звонков и имя вызываемой стороны.
ms.openlocfilehash: dd68327c8fb3f63bf17e0736f9d41b727efc1ff8
ms.sourcegitcommit: 83f14c4c79559ef28357ff076938e52b369fc0c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/10/2021
ms.locfileid: "52308318"
---
# <a name="more-about-calling-line-id-and-calling-party-name"></a><span data-ttu-id="cf231-103">Дополнительные сведения об ИД линии вызова и имени вызывающей стороны</span><span class="sxs-lookup"><span data-stu-id="cf231-103">More about Calling Line ID and Calling Party Name</span></span>

<span data-ttu-id="cf231-104">ИД звонящая состоит из двух пользовательских сведений:</span><span class="sxs-lookup"><span data-stu-id="cf231-104">CallerID consists of two user-facing pieces of information:</span></span>

- <span data-ttu-id="cf231-105">Номер телефона (обычно он называется CLID или ИД строки звонков).</span><span class="sxs-lookup"><span data-stu-id="cf231-105">A phone number (typically referred to as CLID or calling line ID).</span></span>

- <span data-ttu-id="cf231-106">Имя вызываемой стороны (обычно называется CNAM).</span><span class="sxs-lookup"><span data-stu-id="cf231-106">Calling party name (typically referred to as CNAM).</span></span> 

<span data-ttu-id="cf231-107">После звонка clID (номер телефона) перенаправлен на номер оператора назначения (который также называется оператором, который завершает работу).</span><span class="sxs-lookup"><span data-stu-id="cf231-107">When a call is made, the CLID (phone number) is routed to the destination's carrier (also known as the terminating carrier).</span></span> <span data-ttu-id="cf231-108">Данные CNAM для звонка могут быть перена которые могут быть переначены вместе с звоним, так как они зависят от того, как в стране реализована CNAM (если она реализована).</span><span class="sxs-lookup"><span data-stu-id="cf231-108">The CNAM information for the call may or may not be routed with the call because as this information depends on how the country has implemented CNAM (if at all).</span></span> <span data-ttu-id="cf231-109">Надежность доставки CNAM с помощью звонка зависит от страны и операторов, которые обрабатывают звонок, как промежуточного, так и конечного оператора.</span><span class="sxs-lookup"><span data-stu-id="cf231-109">The reliability of CNAM delivery with the call varies depending on the country and carriers that handle the call--either as an intermediary or a terminating carrier.</span></span> 

<span data-ttu-id="cf231-110">ClID & CNAM — это ответственность оператора, который завершает работу.</span><span class="sxs-lookup"><span data-stu-id="cf231-110">CLID & CNAM transmission is the responsibility of the terminating carrier.</span></span> <span data-ttu-id="cf231-111">Завершающий оператор должен поддерживать функции CLID & CNAM, а также предоставлять последние записи для обоих значений.</span><span class="sxs-lookup"><span data-stu-id="cf231-111">The terminating carrier must support CLID & CNAM functionality as well as provide up-to-date records for both values.</span></span> <span data-ttu-id="cf231-112">Корпорация Майкрософт надежно предоставляет значения CLID при исходяющих звонках, но эти значения могут не сохраниться, если они проходят через промежуточного оператора или оператора.</span><span class="sxs-lookup"><span data-stu-id="cf231-112">Microsoft reliably provides CLID values when originating calls, but those values may not be kept intact once they pass through an intermediary carrier or the terminating carrier.</span></span> <span data-ttu-id="cf231-113">Если значение CLID изменено, опущено или усечено промежуточным оператором или оператором связи, у корпорации Майкрософт практически нет необходимости исправлять такие проблемы в телефонной сети общего транспорта.</span><span class="sxs-lookup"><span data-stu-id="cf231-113">If the CLID value is changed, omitted, or truncated by the intermediary or terminating carrier, Microsoft has little to no recourse in correcting such problems in the public telephone network.</span></span>

<span data-ttu-id="cf231-114">Несоответствия в CNAM могут быть вызваны тем, что промежуточные или завершающие операторы задерживают обновление данных CNAM в до полномочного базах данных, как в случае с США.</span><span class="sxs-lookup"><span data-stu-id="cf231-114">Inconsistencies in CNAM can be caused when the intermediate or terminating carriers delay refreshing the CNAM information in authoritative databases--as in the case of the United States.</span></span> <span data-ttu-id="cf231-115">В странах, где нет достилаемой базы данных для CNAM, отдельные методы связи также могут привести к проблемам с данными CNAM, поступающими во время звонка.</span><span class="sxs-lookup"><span data-stu-id="cf231-115">In countries where there are no authoritative databases for CNAM, individual carrier practices can also cause problems with CNAM information arriving intact with the call.</span></span> <span data-ttu-id="cf231-116">В настоящее время корпорация Майкрософт не поддерживает исходя из CNAM-информации в других странах, кроме США.</span><span class="sxs-lookup"><span data-stu-id="cf231-116">Microsoft currently does not support originating CNAM information in countries other than the United States.</span></span>

## <a name="related-topics"></a><span data-ttu-id="cf231-117">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="cf231-117">Related topics</span></span>


