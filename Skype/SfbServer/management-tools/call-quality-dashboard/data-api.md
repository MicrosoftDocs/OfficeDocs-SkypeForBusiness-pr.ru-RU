---
title: Данные API для панели мониторинга качества звонков (CQD) в Скайп для Business Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 25c2450a-f7b3-4dd2-987d-64f4246dd019
description: 'Сводка: Сведения о была исчерпана при использовании API для панели мониторинга качества звонков. Панель мониторинга качества звонков — это средство для Скайп для Business Server 2015.'
ms.openlocfilehash: 038324064177c110c0736092985e9da1b330ea8b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="data-api-for-call-quality-dashboard-cqd-in-skype-for-business-server-2015"></a><span data-ttu-id="00dc2-104">Данные API для панели мониторинга качества звонков (CQD) в Скайп для Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="00dc2-104">Data API for Call Quality Dashboard (CQD) in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="00dc2-105">**Сводка:** Сведения о была исчерпана при использовании API для панели мониторинга качества звонков.</span><span class="sxs-lookup"><span data-stu-id="00dc2-105">**Summary:** Learn about the Rata API for Call Quality Dashboard.</span></span> <span data-ttu-id="00dc2-106">Панель мониторинга качества звонков — это средство для Скайп для Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="00dc2-106">Call Quality Dashboard is a tool for Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="00dc2-107">Data API предоставляет программный доступ к панели мониторинга качества звонков для Скайп для Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="00dc2-107">The Data API provides programmatic access for Call Quality Dashboard for Skype for Business Server 2015.</span></span>
  
## <a name="data-api-for-call-quality-dashboard"></a><span data-ttu-id="00dc2-108">Данные API для панели мониторинга качества звонка</span><span class="sxs-lookup"><span data-stu-id="00dc2-108">Data API for Call Quality Dashboard</span></span>

<span data-ttu-id="00dc2-109">Интерфейс API данных предоставляет интерфейс запросов к кубу качества взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="00dc2-109">The Data API offers a query interface to the QoE Cube.</span></span> <span data-ttu-id="00dc2-110">Интерфейс API данных является интерфейса API REST для работы с многомерная база данных, который предоставляет сводные показатели качества взаимодействия на основе указанного измерения и фильтры.</span><span class="sxs-lookup"><span data-stu-id="00dc2-110">The Data API is a REST API for working with multi-dimensional database that provides aggregated QoE metrics based on specified dimensions and filters.</span></span>
  
<span data-ttu-id="00dc2-111">В следующей таблице включены операции REST.</span><span class="sxs-lookup"><span data-stu-id="00dc2-111">The REST operations are included in the following table.</span></span>
  

|<span data-ttu-id="00dc2-112">**Операция**</span><span class="sxs-lookup"><span data-stu-id="00dc2-112">**Operation**</span></span>|<span data-ttu-id="00dc2-113">**Описание**</span><span class="sxs-lookup"><span data-stu-id="00dc2-113">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="00dc2-114">Получение куба</span><span class="sxs-lookup"><span data-stu-id="00dc2-114">Get Cube</span></span>](get-cube.md) <br/> |<span data-ttu-id="00dc2-115">Получите список доступных измерений и измерения.</span><span class="sxs-lookup"><span data-stu-id="00dc2-115">Get the list of available dimensions and measurements.</span></span>  <br/> |
|[<span data-ttu-id="00dc2-116">Получение элементов измерения</span><span class="sxs-lookup"><span data-stu-id="00dc2-116">Get Dimension Members</span></span>](get-dimension-members.md) <br/> |<span data-ttu-id="00dc2-117">Элементы измерения операции Get возвращает список элементов конкретного измерения.</span><span class="sxs-lookup"><span data-stu-id="00dc2-117">Get Dimension Members operation returns the list of members of a specific dimension.</span></span> <span data-ttu-id="00dc2-118">Также дают возможность фильтрации элементов списка и получение подмножества, сократить расходы на перемещение проводов.</span><span class="sxs-lookup"><span data-stu-id="00dc2-118">It also give the ability to filter the member list and get a subset, to reduce the wire transfer cost.</span></span>  <br/> |
|[<span data-ttu-id="00dc2-119">Выполнение запроса</span><span class="sxs-lookup"><span data-stu-id="00dc2-119">Run Query</span></span>](run-query.md) <br/> |<span data-ttu-id="00dc2-120">Выполнить запрос, операция предоставляет возможность выполнения запроса в кубе, на основе указанного измерения, измерения и фильтры и возвращать данные обратно.</span><span class="sxs-lookup"><span data-stu-id="00dc2-120">Run Query operation provides the ability to run a query on the cube based on specified dimensions, measurements, and filters and return back the data.</span></span>  <br/> |
|[<span data-ttu-id="00dc2-121">Очистить кэш</span><span class="sxs-lookup"><span data-stu-id="00dc2-121">Clear Cache</span></span>](clear-cache.md) <br/> |<span data-ttu-id="00dc2-122">Операция очистки кэша удаляет кэш на сервере для запросов и данных.</span><span class="sxs-lookup"><span data-stu-id="00dc2-122">Clear Cache operation deletes the cache on server for queries and data.</span></span> <span data-ttu-id="00dc2-123">Эта команда сбросит кэша и мы получите новые данные из куба качества взаимодействия впоследствии для новых запросов.</span><span class="sxs-lookup"><span data-stu-id="00dc2-123">This will reset the cache and we will get fresh data from QoE Cube afterward for new requests.</span></span>  <br/> |
|[<span data-ttu-id="00dc2-124">Получение журнала интеграции</span><span class="sxs-lookup"><span data-stu-id="00dc2-124">Get Integration Log</span></span>](get-integration-log.md) <br/> |<span data-ttu-id="00dc2-125">Получение журнала интеграции операция возвращает список записей журнала, описывающий действия в кубе качества взаимодействия обработки.</span><span class="sxs-lookup"><span data-stu-id="00dc2-125">Get Integration Log operation returns a list of log entries describing the activities in QoE Cube processing.</span></span>  <br/> |
|[<span data-ttu-id="00dc2-126">Получите последние интеграции данных</span><span class="sxs-lookup"><span data-stu-id="00dc2-126">Get Last Integration Data</span></span>](get-last-integration-data.md) <br/> |<span data-ttu-id="00dc2-127">Получите последние интеграции данных из куба.</span><span class="sxs-lookup"><span data-stu-id="00dc2-127">Get the last integration data from the cube.</span></span>  <br/> |
   
 <span data-ttu-id="00dc2-128">**Общий доступ к поддержке (CORS) для данных API междоменных ресурсов**</span><span class="sxs-lookup"><span data-stu-id="00dc2-128">**Cross-Origin Resource Sharing (CORS) Support for Data API**</span></span>
  
<span data-ttu-id="00dc2-129">Данные API поддерживает общий доступ к междоменных ресурсов (CORS).</span><span class="sxs-lookup"><span data-stu-id="00dc2-129">Data API supports Cross-Origin Resource Sharing (CORS).</span></span> <span data-ttu-id="00dc2-130">CORS — это функция HTTP, который позволяет в рамках одного домена под управлением веб-приложения для доступа к ресурсам в другом домене.</span><span class="sxs-lookup"><span data-stu-id="00dc2-130">CORS is an HTTP feature that enables a web application running under one domain to access resources in another domain.</span></span> <span data-ttu-id="00dc2-131">Веб-браузеры реализации ограничения безопасности, известных как политики единого происхождения [Политики единого происхождения](https://www.w3.org/Security/wiki/Same_Origin_Policy) , не позволяющей веб-страницы из вызова API в другом домене.</span><span class="sxs-lookup"><span data-stu-id="00dc2-131">Web browsers implement a security restriction known as [Same-Origin Policy](https://www.w3.org/Security/wiki/Same_Origin_Policy) same-origin policy that prevents a web page from calling APIs in a different domain.</span></span> <span data-ttu-id="00dc2-132">CORS предоставляет безопасный способ разрешить один домене (источник) вызов API-интерфейсы в другой домен.</span><span class="sxs-lookup"><span data-stu-id="00dc2-132">CORS provides a secure way to allow one domain (the origin domain) to call APIs in another domain.</span></span> <span data-ttu-id="00dc2-133">[Спецификация CORS](https://www.w3.org/TR/cors/) для получения дополнительных сведений см на CORS.</span><span class="sxs-lookup"><span data-stu-id="00dc2-133">See the [CORS specification](https://www.w3.org/TR/cors/) for details on CORS.</span></span>
  
 <span data-ttu-id="00dc2-134">**Включение CORS для данных API**</span><span class="sxs-lookup"><span data-stu-id="00dc2-134">**Enabling CORS for Data API**</span></span>
  
 <span data-ttu-id="00dc2-135">Ниже приведен фрагмент файла Web.config Data API, отражающая двух доменов, перечисленных в параметрах приложения corsTrustedOrigin.</span><span class="sxs-lookup"><span data-stu-id="00dc2-135">The following is an excerpt of Data API web.config, showing two domains listed in corsTrustedOrigin application settings.</span></span> <span data-ttu-id="00dc2-136">Все запросы, выполненные с скрипты, загруженными из этих серверов являются доверенными Data API.</span><span class="sxs-lookup"><span data-stu-id="00dc2-136">All requests made by the scripts loaded from these servers are trusted by Data API.</span></span>
  
<span data-ttu-id="00dc2-137">Не забудьте включить точное протокол, имя узла и порта (если они имеются).</span><span class="sxs-lookup"><span data-stu-id="00dc2-137">Remember to include the exact protocol, host name, and port (if any).</span></span> <span data-ttu-id="00dc2-138">Не следует поместить какие-либо прямая косая черта (/) знаков в конце.</span><span class="sxs-lookup"><span data-stu-id="00dc2-138">Do not to put any forward slash character (/) at the end.</span></span> <span data-ttu-id="00dc2-139">Несколько записей можно указать, разделив их запятыми.</span><span class="sxs-lookup"><span data-stu-id="00dc2-139">Multiple entries can be specified by separating with commas.</span></span>
  
```
<configuration>
  <appSettings>
    <add key="corsTrustedOrigin" value="https://<trusted-server>,http://<another-trusted-domain>:8080" /> <!-- Domains which are trusted to get the data -->
    <add key="QoEDataLib.DebugMode" value="True" /> <!-- Setting this to True, allows seeing of the detail logs in status page -->
…  </appSettings>
</configuration>

```


