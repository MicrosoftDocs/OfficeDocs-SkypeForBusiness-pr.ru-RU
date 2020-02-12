---
title: API репозитория для панели мониторинга качества звонков (CQD) в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d53e990f-1c5f-46d1-9eb1-8396782c2753
description: 'Сводка: сведения о API репозитория для панели мониторинга качества звонков. Панель мониторинга качества звонков — это средство для Skype для бизнеса Server.'
ms.openlocfilehash: 283ef7544435c3954898b2d5ae9e5f5b38762f3c
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888788"
---
# <a name="repository-api-for-call-quality-dashboard-cqd-in-skype-for-business-server"></a><span data-ttu-id="389b7-104">API репозитория для панели мониторинга качества звонков (CQD) в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="389b7-104">Repository API for Call Quality Dashboard (CQD) in Skype for Business Server</span></span>
 
<span data-ttu-id="389b7-105">**Сводка:** Сведения о API репозитория для панели мониторинга качества звонков.</span><span class="sxs-lookup"><span data-stu-id="389b7-105">**Summary:** Learn about the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="389b7-106">Панель мониторинга качества звонков — это средство для Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="389b7-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="389b7-107">API репозитория обеспечивает программный доступ к панели мониторинга качества звонков в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="389b7-107">The Repository API provides programmatic access for Call Quality Dashboard for Skype for Business Server.</span></span>
  
## <a name="repository-api-for-call-quality-dashboard"></a><span data-ttu-id="389b7-108">API репозитория для панели мониторинга качества звонков</span><span class="sxs-lookup"><span data-stu-id="389b7-108">Repository API for Call Quality Dashboard</span></span>

<span data-ttu-id="389b7-109">API репозитория предоставляют интерфейс доступа к данным в базу данных репозитория.</span><span class="sxs-lookup"><span data-stu-id="389b7-109">Repository API offers a data access interface to repository database.</span></span> <span data-ttu-id="389b7-110">Репозиторий позволяет упорядочить содержимое в древовидной структуре или графике таким образом, чтобы пользователи могли группировать их по тем, кто имеет смысл.</span><span class="sxs-lookup"><span data-stu-id="389b7-110">The repository allows the contents to be organized in a tree or graph structure such that users can group them in the ways that make sense to the users.</span></span> <span data-ttu-id="389b7-111">Репозиторий поддерживает двух типов пользователей: Системный пользователь, который является встроенным пользователем, представляющим репозиторий, и обычные пользователи, которые представляют авторизованных пользователей репозитория.</span><span class="sxs-lookup"><span data-stu-id="389b7-111">The repository supports two general types of users: system user, which is a built-in user representing the repository, and regular users that represent the authorized users of the repository.</span></span>
  
<span data-ttu-id="389b7-112">API репозитория состоит из трех общих служб.</span><span class="sxs-lookup"><span data-stu-id="389b7-112">Repository API consists of three general services:</span></span> 
  
- <span data-ttu-id="389b7-113">[Пользовательская служба для CQD](user-service.md) для доступа к пользователям.</span><span class="sxs-lookup"><span data-stu-id="389b7-113">[User Service for CQD](user-service.md) - for accessing Users.</span></span>
    
- <span data-ttu-id="389b7-114">[Служба элементов для панели мониторинга качества звонков (CQD)](item-service.md) — для доступа к элементам и содержимому, хранящимся в элементах.</span><span class="sxs-lookup"><span data-stu-id="389b7-114">[Item Service for Call Quality Dashboard (CQD)](item-service.md) - for accessing Items and the contents stored in Items.</span></span>
    
- <span data-ttu-id="389b7-115">[Служба параметров пользователя для панели мониторинга качества звонков (CQD)](user-settings-service.md) — для доступа к параметрам пользователей.</span><span class="sxs-lookup"><span data-stu-id="389b7-115">[User Settings Service for Call Quality Dashboard (CQD)](user-settings-service.md) - for accessing User Settings.</span></span>
    
<span data-ttu-id="389b7-116">Панель мониторинга качества звонков использует API репозитория для управления следующими данными:</span><span class="sxs-lookup"><span data-stu-id="389b7-116">Call Quality Dashboard uses Repository API to manage the following information:</span></span> 
  
- <span data-ttu-id="389b7-117">**Пользовательское** представление пользователей, у которых есть доступ к хранилищу.</span><span class="sxs-lookup"><span data-stu-id="389b7-117">**User** - representation of Users who have access to the repository.</span></span>
    
- <span data-ttu-id="389b7-118">**Отчет** — включает список запросов, сохраненный в виде содержимого в элементах репозитория.</span><span class="sxs-lookup"><span data-stu-id="389b7-118">**Report** - contains a list of Queries, stored as a content in repository items.</span></span>
    
- <span data-ttu-id="389b7-119">**Query** — используется для получения данных из API данных, сохраненных в виде содержимого в элементах репозитория.</span><span class="sxs-lookup"><span data-stu-id="389b7-119">**Query** - used to retrieve data from Data API, stored as a content in repository items.</span></span>
    
- <span data-ttu-id="389b7-120">**Параметр пользователя** — описание необязательного поведения приложения для пользователя.</span><span class="sxs-lookup"><span data-stu-id="389b7-120">**User Setting** - describes an optional application behavior for the user.</span></span>
    
  <span data-ttu-id="389b7-121">**Поддержка средства общего разделения ресурсов (CORS) для API репозитория**</span><span class="sxs-lookup"><span data-stu-id="389b7-121">**Cross-Origin Resource Sharing (CORS) Support for Repository API**</span></span>
  
<span data-ttu-id="389b7-122">API репозитория поддерживает межисточниковый доступ к ресурсам (CORS).</span><span class="sxs-lookup"><span data-stu-id="389b7-122">Repository API supports Cross-Origin Resource Sharing (CORS).</span></span> <span data-ttu-id="389b7-123">CORS — это функция HTTP, которая позволяет веб-приложению, работающему в рамках одного домена, получать доступ к ресурсам другого домена.</span><span class="sxs-lookup"><span data-stu-id="389b7-123">CORS is an HTTP feature that enables a web application running under one domain to access resources in another domain.</span></span> <span data-ttu-id="389b7-124">Веб-браузеры реализуют ограничение безопасности, известное как политика на основе [одной и](https://www.w3.org/Security/wiki/Same_Origin_Policy) той же исходной политики, которая предотвращает вызов API на веб-странице другого домена.</span><span class="sxs-lookup"><span data-stu-id="389b7-124">Web browsers implement a security restriction known as [Same-Origin Policy](https://www.w3.org/Security/wiki/Same_Origin_Policy) same-origin policy that prevents a web page from calling APIs in a different domain.</span></span> <span data-ttu-id="389b7-125">CORS обеспечивает безопасный способ вызова API для одного домена (исходного домена) для другого домена.</span><span class="sxs-lookup"><span data-stu-id="389b7-125">CORS provides a secure way to allow one domain (the origin domain) to call APIs in another domain.</span></span> <span data-ttu-id="389b7-126">Подробнее об CORS см. в [спецификации CORS](https://www.w3.org/TR/cors/) .</span><span class="sxs-lookup"><span data-stu-id="389b7-126">See the [CORS specification](https://www.w3.org/TR/cors/) for details on CORS.</span></span>
  
 <span data-ttu-id="389b7-127">**Включение CORS для API репозитория**</span><span class="sxs-lookup"><span data-stu-id="389b7-127">**Enabling CORS for Repository API**</span></span>
  
 <span data-ttu-id="389b7-128">Ниже приведена выдержка из Web. config API репозитория, в которой показаны два домена, перечисленные в параметрах приложения Корструстедоригин.</span><span class="sxs-lookup"><span data-stu-id="389b7-128">The following is an excerpt of Repository API web.config, showing two domains listed in corsTrustedOrigin application settings.</span></span> <span data-ttu-id="389b7-129">Все запросы, отправленные сценариями, загруженными с этих серверов, являются надежными с помощью API репозитория.</span><span class="sxs-lookup"><span data-stu-id="389b7-129">All requests made by the scripts loaded from these servers are trusted by Repository API.</span></span>
  
<span data-ttu-id="389b7-130">Не забудьте включить точный протокол, имя узла и порт (если есть).</span><span class="sxs-lookup"><span data-stu-id="389b7-130">Remember to include the exact protocol, host name, and port (if any).</span></span> <span data-ttu-id="389b7-131">Не следует размещать в конце символа прямой косой черты (/).</span><span class="sxs-lookup"><span data-stu-id="389b7-131">Do not to put any forward slash character (/) at the end.</span></span> <span data-ttu-id="389b7-132">Несколько записей можно задать, разделяя их запятыми.</span><span class="sxs-lookup"><span data-stu-id="389b7-132">Multiple entries can be specified by separating with commas.</span></span>
  
```xml
<repositoryConfiguration>
    <service corsTrustedOrigin="https://<trusted-server>,http://<another-trusted-domain>:8080"" />
    <diagnostics eventLevel="Verbose" systemLoggedEventLevel="Error">
      <traceLog enabled="true" fileName="repository_trace.log" />
    </diagnostics>
 </repositoryConfiguration>
```


