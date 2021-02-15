---
title: API данных для панели мониторинга качества звонков (CQD) в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 25c2450a-f7b3-4dd2-987d-64f4246dd019
description: Сводка. Сведения об API данных для панели мониторинга качества вызовов. Панель мониторинга качества звонков — это инструмент для Skype для бизнеса Server.
ms.openlocfilehash: 367aa1bf1103863fff37fbcd4f8d9fa379de7c1d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832699"
---
# <a name="data-api-for-call-quality-dashboard-cqd-in-skype-for-business-server"></a><span data-ttu-id="f65c7-104">API данных для панели мониторинга качества звонков (CQD) в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="f65c7-104">Data API for Call Quality Dashboard (CQD) in Skype for Business Server</span></span>
 
<span data-ttu-id="f65c7-105">**Сводка:** Сведения об API данных для панели мониторинга качества вызовов.</span><span class="sxs-lookup"><span data-stu-id="f65c7-105">**Summary:** Learn about the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="f65c7-106">Панель мониторинга качества звонков — это инструмент для Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="f65c7-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="f65c7-107">API данных предоставляет программный доступ к панели мониторинга качества звонков для Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="f65c7-107">The Data API provides programmatic access for Call Quality Dashboard for Skype for Business Server.</span></span>
  
## <a name="data-api-for-call-quality-dashboard"></a><span data-ttu-id="f65c7-108">API данных для панели мониторинга качества вызовов</span><span class="sxs-lookup"><span data-stu-id="f65c7-108">Data API for Call Quality Dashboard</span></span>

<span data-ttu-id="f65c7-109">API данных предоставляет интерфейс запроса кубу QoE.</span><span class="sxs-lookup"><span data-stu-id="f65c7-109">The Data API offers a query interface to the QoE Cube.</span></span> <span data-ttu-id="f65c7-110">API данных — это REST API для работы с многомерной базой данных, которая предоставляет сводные показатели качества качества связи на основе указанных измерений и фильтров.</span><span class="sxs-lookup"><span data-stu-id="f65c7-110">The Data API is a REST API for working with multi-dimensional database that provides aggregated QoE metrics based on specified dimensions and filters.</span></span>
  
<span data-ttu-id="f65c7-111">Операции REST включены в следующую таблицу.</span><span class="sxs-lookup"><span data-stu-id="f65c7-111">The REST operations are included in the following table.</span></span>
  

|<span data-ttu-id="f65c7-112">**Операция**</span><span class="sxs-lookup"><span data-stu-id="f65c7-112">**Operation**</span></span>|<span data-ttu-id="f65c7-113">**Описание**</span><span class="sxs-lookup"><span data-stu-id="f65c7-113">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="f65c7-114">Получение куба</span><span class="sxs-lookup"><span data-stu-id="f65c7-114">Get Cube</span></span>](get-cube.md) <br/> |<span data-ttu-id="f65c7-115">Получите список доступных измерений и измерений.</span><span class="sxs-lookup"><span data-stu-id="f65c7-115">Get the list of available dimensions and measurements.</span></span>  <br/> |
|[<span data-ttu-id="f65c7-116">Получение элементов измерений</span><span class="sxs-lookup"><span data-stu-id="f65c7-116">Get Dimension Members</span></span>](get-dimension-members.md) <br/> |<span data-ttu-id="f65c7-117">Операция "Получить члены измерения" возвращает список членов определенного измерения.</span><span class="sxs-lookup"><span data-stu-id="f65c7-117">Get Dimension Members operation returns the list of members of a specific dimension.</span></span> <span data-ttu-id="f65c7-118">Кроме того, это позволяет фильтровать список участников и получать подмножество, чтобы сократить затраты на передачу данных по проводной сети.</span><span class="sxs-lookup"><span data-stu-id="f65c7-118">It also give the ability to filter the member list and get a subset, to reduce the wire transfer cost.</span></span>  <br/> |
|[<span data-ttu-id="f65c7-119">Выполнение запроса</span><span class="sxs-lookup"><span data-stu-id="f65c7-119">Run Query</span></span>](run-query.md) <br/> |<span data-ttu-id="f65c7-120">Операция "Выполнить запрос" позволяет выполнять запрос к кубу на основе указанных измерений, измерений и фильтров, а также возвращать данные.</span><span class="sxs-lookup"><span data-stu-id="f65c7-120">Run Query operation provides the ability to run a query on the cube based on specified dimensions, measurements, and filters and return back the data.</span></span>  <br/> |
|[<span data-ttu-id="f65c7-121">Очистка кэша</span><span class="sxs-lookup"><span data-stu-id="f65c7-121">Clear Cache</span></span>](clear-cache.md) <br/> |<span data-ttu-id="f65c7-122">Операция очистки кэша удаляет кэш на сервере для запросов и данных.</span><span class="sxs-lookup"><span data-stu-id="f65c7-122">Clear Cache operation deletes the cache on server for queries and data.</span></span> <span data-ttu-id="f65c7-123">После этого будет сброшен кэш, и мы будем получать новые данные из куба QoE для новых запросов.</span><span class="sxs-lookup"><span data-stu-id="f65c7-123">This will reset the cache and we will get fresh data from QoE Cube afterward for new requests.</span></span>  <br/> |
|[<span data-ttu-id="f65c7-124">Получение журнала интеграции</span><span class="sxs-lookup"><span data-stu-id="f65c7-124">Get Integration Log</span></span>](get-integration-log.md) <br/> |<span data-ttu-id="f65c7-125">Операция "Получить журнал интеграции" возвращает список записей журнала, описывающих действия в обработке куба QoE.</span><span class="sxs-lookup"><span data-stu-id="f65c7-125">Get Integration Log operation returns a list of log entries describing the activities in QoE Cube processing.</span></span>  <br/> |
|[<span data-ttu-id="f65c7-126">Получение последних данных интеграции</span><span class="sxs-lookup"><span data-stu-id="f65c7-126">Get Last Integration Data</span></span>](get-last-integration-data.md) <br/> |<span data-ttu-id="f65c7-127">Получите последние данные интеграции из куба.</span><span class="sxs-lookup"><span data-stu-id="f65c7-127">Get the last integration data from the cube.</span></span>  <br/> |
   
 <span data-ttu-id="f65c7-128">**Поддержка общего доступа к ресурсам между источниками (CORS) для API данных**</span><span class="sxs-lookup"><span data-stu-id="f65c7-128">**Cross-Origin Resource Sharing (CORS) Support for Data API**</span></span>
  
<span data-ttu-id="f65c7-129">API данных поддерживает общий доступ к ресурсам между источниками (CORS).</span><span class="sxs-lookup"><span data-stu-id="f65c7-129">Data API supports Cross-Origin Resource Sharing (CORS).</span></span> <span data-ttu-id="f65c7-130">CORS — это функция HTTP, которая позволяет веб-приложению под одним доменом получать доступ к ресурсам в другом домене.</span><span class="sxs-lookup"><span data-stu-id="f65c7-130">CORS is an HTTP feature that enables a web application running under one domain to access resources in another domain.</span></span> <span data-ttu-id="f65c7-131">Веб-браузеры реализуют ограничение безопасности, известное как политика одинакового источника, которая не позволяет [веб-странице](https://www.w3.org/Security/wiki/Same_Origin_Policy) вызывать API в другом домене.</span><span class="sxs-lookup"><span data-stu-id="f65c7-131">Web browsers implement a security restriction known as [Same-Origin Policy](https://www.w3.org/Security/wiki/Same_Origin_Policy) same-origin policy that prevents a web page from calling APIs in a different domain.</span></span> <span data-ttu-id="f65c7-132">CORS предоставляет безопасный способ разрешить одному домену (домену источника) вызывать API в другом домене.</span><span class="sxs-lookup"><span data-stu-id="f65c7-132">CORS provides a secure way to allow one domain (the origin domain) to call APIs in another domain.</span></span> <span data-ttu-id="f65c7-133">Подробные [сведения о CORS](https://www.w3.org/TR/cors/) см. в спецификации CORS.</span><span class="sxs-lookup"><span data-stu-id="f65c7-133">See the [CORS specification](https://www.w3.org/TR/cors/) for details on CORS.</span></span>
  
 <span data-ttu-id="f65c7-134">**Включение CORS для API данных**</span><span class="sxs-lookup"><span data-stu-id="f65c7-134">**Enabling CORS for Data API**</span></span>
  
 <span data-ttu-id="f65c7-135">Далее приводится фрагмент списка API данных, web.config двух доменов, перечисленных в параметрах приложения corsTrustedOrigin.</span><span class="sxs-lookup"><span data-stu-id="f65c7-135">The following is an excerpt of Data API web.config, showing two domains listed in corsTrustedOrigin application settings.</span></span> <span data-ttu-id="f65c7-136">API данных доверяет всем запросам, сделанным скриптами, загруженными с этих серверов.</span><span class="sxs-lookup"><span data-stu-id="f65c7-136">All requests made by the scripts loaded from these servers are trusted by Data API.</span></span>
  
<span data-ttu-id="f65c7-137">Не забудьте включить точный протокол, имя хоста и порт (если таковые есть).</span><span class="sxs-lookup"><span data-stu-id="f65c7-137">Remember to include the exact protocol, host name, and port (if any).</span></span> <span data-ttu-id="f65c7-138">Не помещай косую черту (/) в конце.</span><span class="sxs-lookup"><span data-stu-id="f65c7-138">Do not to put any forward slash character (/) at the end.</span></span> <span data-ttu-id="f65c7-139">Несколько записей можно уделить запятой.</span><span class="sxs-lookup"><span data-stu-id="f65c7-139">Multiple entries can be specified by separating with commas.</span></span>
  
```xml
<configuration>
  <appSettings>
    <add key="corsTrustedOrigin" value="https://<trusted-server>,http://<another-trusted-domain>:8080" /> <!-- Domains which are trusted to get the data -->
    <add key="QoEDataLib.DebugMode" value="True" /> <!-- Setting this to True, allows seeing of the detail logs in status page -->
…  </appSettings>
</configuration>
```


