---
title: Данные представлений о качестве взаимодействия
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 6a658318-a317-4546-a44c-a9c473d8e86a
description: В представлениях рассматриваются наиболее распространенные сценарии возврата данных из базы данных SQL QoE. Рекомендуется использовать представления для создания настраиваемых отчетов вместо прямого доступа к таблицам базы данных; Это связано с тем, что представления более удобны для обеспечения обратной совместимости с будущими выпусками.
ms.openlocfilehash: d207c2cff86c398fed62023b30d193e974cbca7a
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41807177"
---
# <a name="qoe-view-details"></a><span data-ttu-id="fc775-104">Данные представлений о качестве взаимодействия</span><span class="sxs-lookup"><span data-stu-id="fc775-104">QoE view details</span></span>
 
<span data-ttu-id="fc775-105">В представлениях рассматриваются наиболее распространенные сценарии возврата данных из базы данных SQL QoE.</span><span class="sxs-lookup"><span data-stu-id="fc775-105">Views cover the most common scenarios for returning data from the QoE SQL database.</span></span> <span data-ttu-id="fc775-106">Рекомендуется использовать представления для создания настраиваемых отчетов вместо прямого доступа к таблицам базы данных; Это связано с тем, что представления более удобны для обеспечения обратной совместимости с будущими выпусками.</span><span class="sxs-lookup"><span data-stu-id="fc775-106">It is recommended views used for building custom reports instead of directly accessing the database tables; that's because views are more likely to maintain backwards compatibility with future releases.</span></span>
  
|<span data-ttu-id="fc775-107">**Имя представления**</span><span class="sxs-lookup"><span data-stu-id="fc775-107">**View Name**</span></span>|<span data-ttu-id="fc775-108">**Описание**</span><span class="sxs-lookup"><span data-stu-id="fc775-108">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="fc775-109">Представление Аудиостреамдетаил</span><span class="sxs-lookup"><span data-stu-id="fc775-109">AudioStreamDetail view</span></span>](audiostreamdetail.md) <br/> |<span data-ttu-id="fc775-110">Хранит сведения о каждом звуковом потоке в базе данных.</span><span class="sxs-lookup"><span data-stu-id="fc775-110">Stores information about each audio stream in the database.</span></span>  <br/> |
|[<span data-ttu-id="fc775-111">Представление Медиалине</span><span class="sxs-lookup"><span data-stu-id="fc775-111">MediaLine view</span></span>](medialine.md) <br/> |<span data-ttu-id="fc775-112">Хранит сведения о каждой строке мультимедиа в базе данных.</span><span class="sxs-lookup"><span data-stu-id="fc775-112">Stores information about each media line in the database.</span></span> <span data-ttu-id="fc775-113">Один звуковой сеанс обычно состоит из одной линии звукового файла.</span><span class="sxs-lookup"><span data-stu-id="fc775-113">One audio session typically contains one audio media line.</span></span> <span data-ttu-id="fc775-114">Один из звуковых и видеофайлов (A/V) обычно состоит из одной линии звукового файла и одной линии видеоклипа; Тем не менее, в этом сеансе могут содержаться две строки видеофайла, если используется устройство конференц-связи или если используется представление коллекции.</span><span class="sxs-lookup"><span data-stu-id="fc775-114">One audio and video (A/V) session typically contains one audio media line and one video media line; however, the session might contain two video media lines if a conferencing device is used or if Gallery View is used.</span></span>  <br/> |
|[<span data-ttu-id="fc775-115">Представление Нетворкконфигуратионсеттингс</span><span class="sxs-lookup"><span data-stu-id="fc775-115">NetworkConfigurationSettings view</span></span>](networkconfigurationsettings.md) <br/> |<span data-ttu-id="fc775-116">Хранит сведения о конфигурации сети.</span><span class="sxs-lookup"><span data-stu-id="fc775-116">Stores information about the network configuration.</span></span>  <br/> |
|[<span data-ttu-id="fc775-117">Представление сеанса</span><span class="sxs-lookup"><span data-stu-id="fc775-117">Session view</span></span>](session-0.md) <br/> |<span data-ttu-id="fc775-118">Хранит сведения о сеансах с записями в базе данных.</span><span class="sxs-lookup"><span data-stu-id="fc775-118">Stores information about sessions that have records in the database.</span></span>  <br/> |
|[<span data-ttu-id="fc775-119">Представление "UserAgent"</span><span class="sxs-lookup"><span data-stu-id="fc775-119">UserAgent view</span></span>](useragent-0.md) <br/> |<span data-ttu-id="fc775-120">Хранит сведения об агентах пользователей, вовлеченных в сеансы с записями в базе данных.</span><span class="sxs-lookup"><span data-stu-id="fc775-120">Stores information about the user agents that have been involved in sessions that have records in the database.</span></span>  <br/> |
|[<span data-ttu-id="fc775-121">Представление Видеостреамдетаил</span><span class="sxs-lookup"><span data-stu-id="fc775-121">VideoStreamDetail view</span></span>](videostreamdetail.md) <br/> |<span data-ttu-id="fc775-122">Хранит сведения о каждом видеопотоке в базе данных.</span><span class="sxs-lookup"><span data-stu-id="fc775-122">Stores information about each video stream in the database.</span></span>  <br/> |
   

