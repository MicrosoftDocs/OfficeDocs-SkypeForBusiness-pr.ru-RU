---
title: Данные представлений о качестве взаимодействия
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6a658318-a317-4546-a44c-a9c473d8e86a
description: Представления охватывают наиболее распространенные сценарии для возвращения данных из базы данных SQL качества взаимодействия. Рекомендуется представления, используемые для создания настраиваемых отчетов вместо прямой доступ к таблиц базы данных; Вот так как представления, скорее всего, для обеспечения обратной совместимости с будущими версиями.
ms.openlocfilehash: f384f75ecc0c8a0dfdb2cdaedacdcef81bdba9b4
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212146"
---
# <a name="qoe-view-details"></a><span data-ttu-id="76597-104">Данные представлений о качестве взаимодействия</span><span class="sxs-lookup"><span data-stu-id="76597-104">QoE view details</span></span>
 
<span data-ttu-id="76597-105">Представления охватывают наиболее распространенные сценарии для возвращения данных из базы данных SQL качества взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="76597-105">Views cover the most common scenarios for returning data from the QoE SQL database.</span></span> <span data-ttu-id="76597-106">Рекомендуется представления, используемые для создания настраиваемых отчетов вместо прямой доступ к таблиц базы данных; Вот так как представления, скорее всего, для обеспечения обратной совместимости с будущими версиями.</span><span class="sxs-lookup"><span data-stu-id="76597-106">It is recommended views used for building custom reports instead of directly accessing the database tables; that's because views are more likely to maintain backwards compatibility with future releases.</span></span>
  
|<span data-ttu-id="76597-107">**Имя представления**</span><span class="sxs-lookup"><span data-stu-id="76597-107">**View Name**</span></span>|<span data-ttu-id="76597-108">**Описание**</span><span class="sxs-lookup"><span data-stu-id="76597-108">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="76597-109">Представление audiostreamdetail</span><span class="sxs-lookup"><span data-stu-id="76597-109">AudioStreamDetail view</span></span>](audiostreamdetail.md) <br/> |<span data-ttu-id="76597-110">Сохранение информации о каждом аудиопотоке в базе данных.</span><span class="sxs-lookup"><span data-stu-id="76597-110">Stores information about each audio stream in the database.</span></span>  <br/> |
|[<span data-ttu-id="76597-111">Представление MediaLine</span><span class="sxs-lookup"><span data-stu-id="76597-111">MediaLine view</span></span>](medialine.md) <br/> |<span data-ttu-id="76597-112">Сохранение информации о каждом канале передачи мультимедиа в базе данных.</span><span class="sxs-lookup"><span data-stu-id="76597-112">Stores information about each media line in the database.</span></span> <span data-ttu-id="76597-113">Один аудиосеанса обычно содержит одну строку аудио.</span><span class="sxs-lookup"><span data-stu-id="76597-113">One audio session typically contains one audio media line.</span></span> <span data-ttu-id="76597-114">Один аудио- и видеоконференций (A / V) сеанса обычно содержит одну строку аудио и одну строку видео; Тем не менее сеанс может содержать две строки видео при использовании устройства конференц-связи или при использовании представления галереи.</span><span class="sxs-lookup"><span data-stu-id="76597-114">One audio and video (A/V) session typically contains one audio media line and one video media line; however, the session might contain two video media lines if a conferencing device is used or if Gallery View is used.</span></span>  <br/> |
|[<span data-ttu-id="76597-115">Представление networkconfigurationsettings</span><span class="sxs-lookup"><span data-stu-id="76597-115">NetworkConfigurationSettings view</span></span>](networkconfigurationsettings.md) <br/> |<span data-ttu-id="76597-116">Сохранение информации о конфигурации сети.</span><span class="sxs-lookup"><span data-stu-id="76597-116">Stores information about the network configuration.</span></span>  <br/> |
|[<span data-ttu-id="76597-117">Просмотр сеанса</span><span class="sxs-lookup"><span data-stu-id="76597-117">Session view</span></span>](session-0.md) <br/> |<span data-ttu-id="76597-118">Сохранение информации о сеансах с записями в базе данных.</span><span class="sxs-lookup"><span data-stu-id="76597-118">Stores information about sessions that have records in the database.</span></span>  <br/> |
|[<span data-ttu-id="76597-119">Представление UserAgent</span><span class="sxs-lookup"><span data-stu-id="76597-119">UserAgent view</span></span>](useragent-0.md) <br/> |<span data-ttu-id="76597-120">Хранит информацию об агентах пользователя, участвовавших в сеансах с записями в базе данных.</span><span class="sxs-lookup"><span data-stu-id="76597-120">Stores information about the user agents that have been involved in sessions that have records in the database.</span></span>  <br/> |
|[<span data-ttu-id="76597-121">Представление videostreamdetail</span><span class="sxs-lookup"><span data-stu-id="76597-121">VideoStreamDetail view</span></span>](videostreamdetail.md) <br/> |<span data-ttu-id="76597-122">Сохранение информации о каждом видеопотоке в базе данных.</span><span class="sxs-lookup"><span data-stu-id="76597-122">Stores information about each video stream in the database.</span></span>  <br/> |
   

