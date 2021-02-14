---
title: API репозитория для панели мониторинга качества звонков (CQD) в Skype для бизнеса Server
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
ms.assetid: d53e990f-1c5f-46d1-9eb1-8396782c2753
description: Сводка. Сведения об API репозитория для панели мониторинга качества вызовов. Панель мониторинга качества звонков — это инструмент для Skype для бизнеса Server.
ms.openlocfilehash: 982ec0932f0a57958e1929a6ae2413ada0b5c9fa
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49803129"
---
# <a name="repository-api-for-call-quality-dashboard-cqd-in-skype-for-business-server"></a><span data-ttu-id="490e1-104">API репозитория для панели мониторинга качества звонков (CQD) в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="490e1-104">Repository API for Call Quality Dashboard (CQD) in Skype for Business Server</span></span>
 
<span data-ttu-id="490e1-105">**Сводка:** Узнайте об API репозитория для панели мониторинга качества вызовов.</span><span class="sxs-lookup"><span data-stu-id="490e1-105">**Summary:** Learn about the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="490e1-106">Панель мониторинга качества звонков — это инструмент для Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="490e1-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="490e1-107">API репозитория предоставляет программный доступ к панели мониторинга качества звонков для Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="490e1-107">The Repository API provides programmatic access for Call Quality Dashboard for Skype for Business Server.</span></span>
  
## <a name="repository-api-for-call-quality-dashboard"></a><span data-ttu-id="490e1-108">API репозитория для панели мониторинга качества вызовов</span><span class="sxs-lookup"><span data-stu-id="490e1-108">Repository API for Call Quality Dashboard</span></span>

<span data-ttu-id="490e1-109">API репозитория предоставляет интерфейс доступа к данным для базы данных репозитория.</span><span class="sxs-lookup"><span data-stu-id="490e1-109">Repository API offers a data access interface to repository database.</span></span> <span data-ttu-id="490e1-110">Репозиторий позволяет организовать содержимое в виде дерева или структуры графа, чтобы пользователи могли группировать их так, как это имеет смысл для пользователей.</span><span class="sxs-lookup"><span data-stu-id="490e1-110">The repository allows the contents to be organized in a tree or graph structure such that users can group them in the ways that make sense to the users.</span></span> <span data-ttu-id="490e1-111">Репозиторий поддерживает два общих типа пользователей: системный пользователь, который является встроенным пользователем, представляющим репозиторий, и обычных пользователей, представляющих авторизованного пользователя репозитория.</span><span class="sxs-lookup"><span data-stu-id="490e1-111">The repository supports two general types of users: system user, which is a built-in user representing the repository, and regular users that represent the authorized users of the repository.</span></span>
  
<span data-ttu-id="490e1-112">API репозитория состоит из трех общих служб:</span><span class="sxs-lookup"><span data-stu-id="490e1-112">Repository API consists of three general services:</span></span> 
  
- <span data-ttu-id="490e1-113">[Служба пользователей для CQD](user-service.md) — для доступа к пользователям.</span><span class="sxs-lookup"><span data-stu-id="490e1-113">[User Service for CQD](user-service.md) - for accessing Users.</span></span>
    
- <span data-ttu-id="490e1-114">[Item Service for Call Quality Dashboard (CQD)](item-service.md) - for accessing Items and the contents stored in Items.</span><span class="sxs-lookup"><span data-stu-id="490e1-114">[Item Service for Call Quality Dashboard (CQD)](item-service.md) - for accessing Items and the contents stored in Items.</span></span>
    
- <span data-ttu-id="490e1-115">Служба параметров пользователя для панели мониторинга качества вызовов [(CQD)](user-settings-service.md) для доступа к пользовательским настройкам.</span><span class="sxs-lookup"><span data-stu-id="490e1-115">[User Settings Service for Call Quality Dashboard (CQD)](user-settings-service.md) - for accessing User Settings.</span></span>
    
<span data-ttu-id="490e1-116">Панель мониторинга качества вызовов использует API репозитория для управления следующими сведениями:</span><span class="sxs-lookup"><span data-stu-id="490e1-116">Call Quality Dashboard uses Repository API to manage the following information:</span></span> 
  
- <span data-ttu-id="490e1-117">**Пользователь** — представление пользователей, у которых есть доступ к репозиторию.</span><span class="sxs-lookup"><span data-stu-id="490e1-117">**User** - representation of Users who have access to the repository.</span></span>
    
- <span data-ttu-id="490e1-118">**Отчет** содержит список запросов, хранимый в качестве контента в элементов репозитория.</span><span class="sxs-lookup"><span data-stu-id="490e1-118">**Report** - contains a list of Queries, stored as a content in repository items.</span></span>
    
- <span data-ttu-id="490e1-119">**Запрос** — используется для получения данных из API данных, хранимого в качестве контента в элементов репозитория.</span><span class="sxs-lookup"><span data-stu-id="490e1-119">**Query** - used to retrieve data from Data API, stored as a content in repository items.</span></span>
    
- <span data-ttu-id="490e1-120">**Параметр пользователя** — описывает необязательное поведение приложения для пользователя.</span><span class="sxs-lookup"><span data-stu-id="490e1-120">**User Setting** - describes an optional application behavior for the user.</span></span>
    
  <span data-ttu-id="490e1-121">**Поддержка общего доступа к ресурсам между источниками (CORS) для API репозитория**</span><span class="sxs-lookup"><span data-stu-id="490e1-121">**Cross-Origin Resource Sharing (CORS) Support for Repository API**</span></span>
  
<span data-ttu-id="490e1-122">API репозитория поддерживает общий доступ к ресурсам между источниками (CORS).</span><span class="sxs-lookup"><span data-stu-id="490e1-122">Repository API supports Cross-Origin Resource Sharing (CORS).</span></span> <span data-ttu-id="490e1-123">CORS — это функция HTTP, которая позволяет веб-приложению под одним доменом получать доступ к ресурсам в другом домене.</span><span class="sxs-lookup"><span data-stu-id="490e1-123">CORS is an HTTP feature that enables a web application running under one domain to access resources in another domain.</span></span> <span data-ttu-id="490e1-124">Веб-браузеры реализуют ограничение безопасности, известное как политика одинакового источника, которая не позволяет [веб-странице](https://www.w3.org/Security/wiki/Same_Origin_Policy) вызывать API в другом домене.</span><span class="sxs-lookup"><span data-stu-id="490e1-124">Web browsers implement a security restriction known as [Same-Origin Policy](https://www.w3.org/Security/wiki/Same_Origin_Policy) same-origin policy that prevents a web page from calling APIs in a different domain.</span></span> <span data-ttu-id="490e1-125">CORS предоставляет безопасный способ разрешить одному домену (домену источника) вызывать API в другом домене.</span><span class="sxs-lookup"><span data-stu-id="490e1-125">CORS provides a secure way to allow one domain (the origin domain) to call APIs in another domain.</span></span> <span data-ttu-id="490e1-126">Подробные [сведения о CORS](https://www.w3.org/TR/cors/) см. в спецификации CORS.</span><span class="sxs-lookup"><span data-stu-id="490e1-126">See the [CORS specification](https://www.w3.org/TR/cors/) for details on CORS.</span></span>
  
 <span data-ttu-id="490e1-127">**Включение CORS для API репозитория**</span><span class="sxs-lookup"><span data-stu-id="490e1-127">**Enabling CORS for Repository API**</span></span>
  
 <span data-ttu-id="490e1-128">Далее приводится фрагмент API репозитория web.config с двумя доменами, перечисленными в параметрах приложения corsTrustedOrigin.</span><span class="sxs-lookup"><span data-stu-id="490e1-128">The following is an excerpt of Repository API web.config, showing two domains listed in corsTrustedOrigin application settings.</span></span> <span data-ttu-id="490e1-129">API репозитория доверяет всем запросам, сделанным скриптами, загруженными с этих серверов.</span><span class="sxs-lookup"><span data-stu-id="490e1-129">All requests made by the scripts loaded from these servers are trusted by Repository API.</span></span>
  
<span data-ttu-id="490e1-130">Не забудьте включить точный протокол, имя хоста и порт (если таковые есть).</span><span class="sxs-lookup"><span data-stu-id="490e1-130">Remember to include the exact protocol, host name, and port (if any).</span></span> <span data-ttu-id="490e1-131">Не помещай косую черту (/) в конце.</span><span class="sxs-lookup"><span data-stu-id="490e1-131">Do not to put any forward slash character (/) at the end.</span></span> <span data-ttu-id="490e1-132">Несколько записей можно уделить запятой.</span><span class="sxs-lookup"><span data-stu-id="490e1-132">Multiple entries can be specified by separating with commas.</span></span>
  
```xml
<repositoryConfiguration>
    <service corsTrustedOrigin="https://<trusted-server>,http://<another-trusted-domain>:8080"" />
    <diagnostics eventLevel="Verbose" systemLoggedEventLevel="Error">
      <traceLog enabled="true" fileName="repository_trace.log" />
    </diagnostics>
 </repositoryConfiguration>
```


