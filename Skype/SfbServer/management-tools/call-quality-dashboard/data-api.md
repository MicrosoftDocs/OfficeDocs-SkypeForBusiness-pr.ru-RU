---
title: API данных для панели мониторинга качества звонков (CQD) в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 25c2450a-f7b3-4dd2-987d-64f4246dd019
description: 'Сводка: сведения об API данных для панели мониторинга качества звонков. Панель мониторинга качества звонков — это средство для Skype для бизнеса Server.'
ms.openlocfilehash: 016cc1be9f5cd5506f8ee7d8ddbe2765e0015ffd
ms.sourcegitcommit: 100ba1409bf0af58e4430877c1d29622d793d23f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/01/2019
ms.locfileid: "36571923"
---
# <a name="data-api-for-call-quality-dashboard-cqd-in-skype-for-business-server"></a><span data-ttu-id="a5c31-104">API данных для панели мониторинга качества звонков (CQD) в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="a5c31-104">Data API for Call Quality Dashboard (CQD) in Skype for Business Server</span></span>
 
<span data-ttu-id="a5c31-105">**Сводка:** Сведения об API данных для панели мониторинга качества звонков.</span><span class="sxs-lookup"><span data-stu-id="a5c31-105">**Summary:** Learn about the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="a5c31-106">Панель мониторинга качества звонков — это средство для Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="a5c31-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="a5c31-107">API данных обеспечивает программный доступ к панели мониторинга качества звонков для Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="a5c31-107">The Data API provides programmatic access for Call Quality Dashboard for Skype for Business Server.</span></span>
  
## <a name="data-api-for-call-quality-dashboard"></a><span data-ttu-id="a5c31-108">API данных для панели мониторинга качества звонков</span><span class="sxs-lookup"><span data-stu-id="a5c31-108">Data API for Call Quality Dashboard</span></span>

<span data-ttu-id="a5c31-109">API данных предоставляют интерфейс запроса для куба QoE.</span><span class="sxs-lookup"><span data-stu-id="a5c31-109">The Data API offers a query interface to the QoE Cube.</span></span> <span data-ttu-id="a5c31-110">API данных — это интерфейс API для работы с многомерной базой данных, который обеспечивает агрегированные метрики QoE на основе указанных размеров и фильтров.</span><span class="sxs-lookup"><span data-stu-id="a5c31-110">The Data API is a REST API for working with multi-dimensional database that provides aggregated QoE metrics based on specified dimensions and filters.</span></span>
  
<span data-ttu-id="a5c31-111">Операции RESTFUL включены в таблицу ниже.</span><span class="sxs-lookup"><span data-stu-id="a5c31-111">The REST operations are included in the following table.</span></span>
  

|<span data-ttu-id="a5c31-112">**Операция**</span><span class="sxs-lookup"><span data-stu-id="a5c31-112">**Operation**</span></span>|<span data-ttu-id="a5c31-113">**Описание**</span><span class="sxs-lookup"><span data-stu-id="a5c31-113">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="a5c31-114">Получение куба</span><span class="sxs-lookup"><span data-stu-id="a5c31-114">Get Cube</span></span>](get-cube.md) <br/> |<span data-ttu-id="a5c31-115">Получение списка доступных размеров и размеров.</span><span class="sxs-lookup"><span data-stu-id="a5c31-115">Get the list of available dimensions and measurements.</span></span>  <br/> |
|[<span data-ttu-id="a5c31-116">Получение элементов измерений</span><span class="sxs-lookup"><span data-stu-id="a5c31-116">Get Dimension Members</span></span>](get-dimension-members.md) <br/> |<span data-ttu-id="a5c31-117">Функция "получить элементы измерения" возвращает список элементов определенного измерения.</span><span class="sxs-lookup"><span data-stu-id="a5c31-117">Get Dimension Members operation returns the list of members of a specific dimension.</span></span> <span data-ttu-id="a5c31-118">Кроме того, она дает возможность отфильтровать список участников и получить подмножество, чтобы снизить стоимость передачи данных в сети.</span><span class="sxs-lookup"><span data-stu-id="a5c31-118">It also give the ability to filter the member list and get a subset, to reduce the wire transfer cost.</span></span>  <br/> |
|[<span data-ttu-id="a5c31-119">Выполнение запроса</span><span class="sxs-lookup"><span data-stu-id="a5c31-119">Run Query</span></span>](run-query.md) <br/> |<span data-ttu-id="a5c31-120">Операция выполнения запроса предоставляет возможность выполнения запроса для куба на основе указанных размеров, измерений и фильтров, а также возврата данных.</span><span class="sxs-lookup"><span data-stu-id="a5c31-120">Run Query operation provides the ability to run a query on the cube based on specified dimensions, measurements, and filters and return back the data.</span></span>  <br/> |
|[<span data-ttu-id="a5c31-121">Очистка кэша</span><span class="sxs-lookup"><span data-stu-id="a5c31-121">Clear Cache</span></span>](clear-cache.md) <br/> |<span data-ttu-id="a5c31-122">Операция очистки кэша удаляет кэш на сервере для запросов и данных.</span><span class="sxs-lookup"><span data-stu-id="a5c31-122">Clear Cache operation deletes the cache on server for queries and data.</span></span> <span data-ttu-id="a5c31-123">Это приведет к сбросу кэша, и мы постараемся получать новые данные из куба QoE для новых запросов.</span><span class="sxs-lookup"><span data-stu-id="a5c31-123">This will reset the cache and we will get fresh data from QoE Cube afterward for new requests.</span></span>  <br/> |
|[<span data-ttu-id="a5c31-124">Получение журнала интеграции</span><span class="sxs-lookup"><span data-stu-id="a5c31-124">Get Integration Log</span></span>](get-integration-log.md) <br/> |<span data-ttu-id="a5c31-125">Операция Get Integration log возвращает список записей журнала, описывающих действия в обработке куба QoE.</span><span class="sxs-lookup"><span data-stu-id="a5c31-125">Get Integration Log operation returns a list of log entries describing the activities in QoE Cube processing.</span></span>  <br/> |
|[<span data-ttu-id="a5c31-126">Получение последних данных интеграции</span><span class="sxs-lookup"><span data-stu-id="a5c31-126">Get Last Integration Data</span></span>](get-last-integration-data.md) <br/> |<span data-ttu-id="a5c31-127">Получение данных о последней интеграции из куба.</span><span class="sxs-lookup"><span data-stu-id="a5c31-127">Get the last integration data from the cube.</span></span>  <br/> |
   
 <span data-ttu-id="a5c31-128">**Поддержка средства общего разделения ресурсов (CORS) для API данных**</span><span class="sxs-lookup"><span data-stu-id="a5c31-128">**Cross-Origin Resource Sharing (CORS) Support for Data API**</span></span>
  
<span data-ttu-id="a5c31-129">API данных поддерживает межисточниковый доступ к ресурсам (CORS).</span><span class="sxs-lookup"><span data-stu-id="a5c31-129">Data API supports Cross-Origin Resource Sharing (CORS).</span></span> <span data-ttu-id="a5c31-130">CORS — это функция HTTP, которая позволяет веб-приложению, работающему в рамках одного домена, получать доступ к ресурсам другого домена.</span><span class="sxs-lookup"><span data-stu-id="a5c31-130">CORS is an HTTP feature that enables a web application running under one domain to access resources in another domain.</span></span> <span data-ttu-id="a5c31-131">Веб-браузеры реализуют ограничение безопасности, известное как политика на основе [одной и](https://www.w3.org/Security/wiki/Same_Origin_Policy) той же исходной политики, которая предотвращает вызов API на веб-странице другого домена.</span><span class="sxs-lookup"><span data-stu-id="a5c31-131">Web browsers implement a security restriction known as [Same-Origin Policy](https://www.w3.org/Security/wiki/Same_Origin_Policy) same-origin policy that prevents a web page from calling APIs in a different domain.</span></span> <span data-ttu-id="a5c31-132">CORS обеспечивает безопасный способ вызова API для одного домена (исходного домена) для другого домена.</span><span class="sxs-lookup"><span data-stu-id="a5c31-132">CORS provides a secure way to allow one domain (the origin domain) to call APIs in another domain.</span></span> <span data-ttu-id="a5c31-133">Подробнее об CORS см. в [спецификации CORS](https://www.w3.org/TR/cors/) .</span><span class="sxs-lookup"><span data-stu-id="a5c31-133">See the [CORS specification](https://www.w3.org/TR/cors/) for details on CORS.</span></span>
  
 <span data-ttu-id="a5c31-134">**Включение CORS для API данных**</span><span class="sxs-lookup"><span data-stu-id="a5c31-134">**Enabling CORS for Data API**</span></span>
  
 <span data-ttu-id="a5c31-135">Ниже приведено фрагмент интерфейса API данных Web. config, в котором показаны два домена, перечисленных в разделе Параметры приложения Корструстедоригин.</span><span class="sxs-lookup"><span data-stu-id="a5c31-135">The following is an excerpt of Data API web.config, showing two domains listed in corsTrustedOrigin application settings.</span></span> <span data-ttu-id="a5c31-136">Все запросы, отправленные сценариями, загруженными с этих серверов, являются надежными через API данных.</span><span class="sxs-lookup"><span data-stu-id="a5c31-136">All requests made by the scripts loaded from these servers are trusted by Data API.</span></span>
  
<span data-ttu-id="a5c31-137">Не забудьте включить точный протокол, имя узла и порт (если есть).</span><span class="sxs-lookup"><span data-stu-id="a5c31-137">Remember to include the exact protocol, host name, and port (if any).</span></span> <span data-ttu-id="a5c31-138">Не следует размещать в конце символа прямой косой черты (/).</span><span class="sxs-lookup"><span data-stu-id="a5c31-138">Do not to put any forward slash character (/) at the end.</span></span> <span data-ttu-id="a5c31-139">Несколько записей можно задать, разделяя их запятыми.</span><span class="sxs-lookup"><span data-stu-id="a5c31-139">Multiple entries can be specified by separating with commas.</span></span>
  
```
<configuration>
  <appSettings>
    <add key="corsTrustedOrigin" value="https://<trusted-server>,http://<another-trusted-domain>:8080" /> <!-- Domains which are trusted to get the data -->
    <add key="QoEDataLib.DebugMode" value="True" /> <!-- Setting this to True, allows seeing of the detail logs in status page -->
…  </appSettings>
</configuration>
```


