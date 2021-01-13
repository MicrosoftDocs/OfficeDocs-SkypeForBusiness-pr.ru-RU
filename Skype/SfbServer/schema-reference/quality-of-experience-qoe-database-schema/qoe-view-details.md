---
title: Данные представлений о качестве взаимодействия
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 6a658318-a317-4546-a44c-a9c473d8e86a
description: Представления охватывают наиболее распространенные сценарии возврата данных из базы данных QoE SQL данных. Рекомендуется использовать представления для создания настраиваемого отчета, а не для прямого доступа к таблицам баз данных; это потому, что представления с большей вероятностью будут поддерживать обратную совместимость с будущими выпусками.
ms.openlocfilehash: cabe483da624d801b9b87d51ba61caed7a22f7d4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834479"
---
# <a name="qoe-view-details"></a><span data-ttu-id="ae575-104">Данные представлений о качестве взаимодействия</span><span class="sxs-lookup"><span data-stu-id="ae575-104">QoE view details</span></span>
 
<span data-ttu-id="ae575-105">Представления охватывают наиболее распространенные сценарии возврата данных из базы данных QoE SQL данных.</span><span class="sxs-lookup"><span data-stu-id="ae575-105">Views cover the most common scenarios for returning data from the QoE SQL database.</span></span> <span data-ttu-id="ae575-106">Рекомендуется использовать представления для создания настраиваемого отчета вместо прямого доступа к таблицам баз данных; это потому, что представления с большей вероятностью будут поддерживать обратную совместимость с будущими выпусками.</span><span class="sxs-lookup"><span data-stu-id="ae575-106">It is recommended views used for building custom reports instead of directly accessing the database tables; that's because views are more likely to maintain backwards compatibility with future releases.</span></span>
  
|<span data-ttu-id="ae575-107">**Имя представления**</span><span class="sxs-lookup"><span data-stu-id="ae575-107">**View Name**</span></span>|<span data-ttu-id="ae575-108">**Описание**</span><span class="sxs-lookup"><span data-stu-id="ae575-108">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="ae575-109">Представление AudioStreamDetail</span><span class="sxs-lookup"><span data-stu-id="ae575-109">AudioStreamDetail view</span></span>](audiostreamdetail.md) <br/> |<span data-ttu-id="ae575-110">Хранение информации о каждом аудиопотоке в базе данных.</span><span class="sxs-lookup"><span data-stu-id="ae575-110">Stores information about each audio stream in the database.</span></span>  <br/> |
|[<span data-ttu-id="ae575-111">Представление MediaLine</span><span class="sxs-lookup"><span data-stu-id="ae575-111">MediaLine view</span></span>](medialine.md) <br/> |<span data-ttu-id="ae575-112">Хранит сведения о каждой строке мультимедиа в базе данных.</span><span class="sxs-lookup"><span data-stu-id="ae575-112">Stores information about each media line in the database.</span></span> <span data-ttu-id="ae575-113">Один сеанс аудиосвязи обычно содержит одну строку мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="ae575-113">One audio session typically contains one audio media line.</span></span> <span data-ttu-id="ae575-114">Один сеанс аудио- и видеосвязи обычно содержит одну аудио- и видеомагимичную линию; Однако сеанс может содержать две видеомайки, если используется устройство для работы с видеоконференцией или используется представление галереи.</span><span class="sxs-lookup"><span data-stu-id="ae575-114">One audio and video (A/V) session typically contains one audio media line and one video media line; however, the session might contain two video media lines if a conferencing device is used or if Gallery View is used.</span></span>  <br/> |
|[<span data-ttu-id="ae575-115">Представление NetworkConfigurationSettings</span><span class="sxs-lookup"><span data-stu-id="ae575-115">NetworkConfigurationSettings view</span></span>](networkconfigurationsettings.md) <br/> |<span data-ttu-id="ae575-116">Хранит сведения о конфигурации сети.</span><span class="sxs-lookup"><span data-stu-id="ae575-116">Stores information about the network configuration.</span></span>  <br/> |
|[<span data-ttu-id="ae575-117">Представление сеанса</span><span class="sxs-lookup"><span data-stu-id="ae575-117">Session view</span></span>](session-0.md) <br/> |<span data-ttu-id="ae575-118">Хранит информацию о сеансах с записями в базе данных.</span><span class="sxs-lookup"><span data-stu-id="ae575-118">Stores information about sessions that have records in the database.</span></span>  <br/> |
|[<span data-ttu-id="ae575-119">Представление UserAgent</span><span class="sxs-lookup"><span data-stu-id="ae575-119">UserAgent view</span></span>](useragent-0.md) <br/> |<span data-ttu-id="ae575-120">Хранит информацию об агентах пользователя, участвовавших в сеансах с записями в базе данных.</span><span class="sxs-lookup"><span data-stu-id="ae575-120">Stores information about the user agents that have been involved in sessions that have records in the database.</span></span>  <br/> |
|[<span data-ttu-id="ae575-121">Представление VideoStreamDetail</span><span class="sxs-lookup"><span data-stu-id="ae575-121">VideoStreamDetail view</span></span>](videostreamdetail.md) <br/> |<span data-ttu-id="ae575-122">Хранит информацию о каждом видеопотоке в базе данных.</span><span class="sxs-lookup"><span data-stu-id="ae575-122">Stores information about each video stream in the database.</span></span>  <br/> |
   

