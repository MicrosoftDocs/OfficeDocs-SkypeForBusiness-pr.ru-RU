---
title: Репозиторий API для панели мониторинга качества звонков (CQD) в Скайп для Business Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d53e990f-1c5f-46d1-9eb1-8396782c2753
description: 'Сводка: Сведения об API репозитория для панели мониторинга качества звонков. Панель мониторинга качества звонков — это средство для Скайп для Business Server 2015.'
ms.openlocfilehash: 083a7b3a9a539757769ba0a2d2fcf0d3ea2f9b1b
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/05/2018
ms.locfileid: "19570194"
---
# <a name="repository-api-for-call-quality-dashboard-cqd-in-skype-for-business-server-2015"></a><span data-ttu-id="b0d64-104">Репозиторий API для панели мониторинга качества звонков (CQD) в Скайп для Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="b0d64-104">Repository API for Call Quality Dashboard (CQD) in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="b0d64-105">**Сводка:** Сведения об API репозитория для панели мониторинга качества звонков.</span><span class="sxs-lookup"><span data-stu-id="b0d64-105">**Summary:** Learn about the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="b0d64-106">Панель мониторинга качества звонков — это средство для Скайп для Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="b0d64-106">Call Quality Dashboard is a tool for Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="b0d64-107">API репозитория предоставляет программный доступ к панели мониторинга качества звонков для Скайп для Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="b0d64-107">The Repository API provides programmatic access for Call Quality Dashboard for Skype for Business Server 2015.</span></span>
  
## <a name="repository-api-for-call-quality-dashboard"></a><span data-ttu-id="b0d64-108">Репозиторий API для панели мониторинга качества звонка</span><span class="sxs-lookup"><span data-stu-id="b0d64-108">Repository API for Call Quality Dashboard</span></span>

<span data-ttu-id="b0d64-109">API репозитория предоставляет интерфейс доступа к данным для базы данных репозитория.</span><span class="sxs-lookup"><span data-stu-id="b0d64-109">Repository API offers a data access interface to repository database.</span></span> <span data-ttu-id="b0d64-110">Репозиторий позволяет содержимое, организованных в виде дерева или график таким образом, чтобы пользователи можно сгруппировать их таким образом, имеет смысла для пользователей.</span><span class="sxs-lookup"><span data-stu-id="b0d64-110">The repository allows the contents to be organized in a tree or graph structure such that users can group them in the ways that make sense to the users.</span></span> <span data-ttu-id="b0d64-111">Репозиторий поддерживает два типа пользователей: системы пользователя, который является встроенной пользователя, представляющее репозитория и обычных пользователей, которые представляют авторизованные пользователи репозитория.</span><span class="sxs-lookup"><span data-stu-id="b0d64-111">The repository supports two general types of users: system user, which is a built-in user representing the repository, and regular users that represent the authorized users of the repository.</span></span>
  
<span data-ttu-id="b0d64-112">API репозитория состоит из трех общих служб.</span><span class="sxs-lookup"><span data-stu-id="b0d64-112">Repository API consists of three general services:</span></span> 
  
- <span data-ttu-id="b0d64-113">[Служба пользователей для CQD](user-service.md) — для доступа к пользователям.</span><span class="sxs-lookup"><span data-stu-id="b0d64-113">[User Service for CQD](user-service.md) - for accessing Users.</span></span>
    
- <span data-ttu-id="b0d64-114">[Элемент службы для вызова панели мониторинга качества (CQD)](item-service.md) — для доступа к элементы и содержимое, хранимых в элементах.</span><span class="sxs-lookup"><span data-stu-id="b0d64-114">[Item Service for Call Quality Dashboard (CQD)](item-service.md) - for accessing Items and the contents stored in Items.</span></span>
    
- <span data-ttu-id="b0d64-115">[Служба параметров пользователя для вызова панели мониторинга качества (CQD)](user-settings-service.md) — для доступа к параметрам пользователя.</span><span class="sxs-lookup"><span data-stu-id="b0d64-115">[User Settings Service for Call Quality Dashboard (CQD)](user-settings-service.md) - for accessing User Settings.</span></span>
    
<span data-ttu-id="b0d64-116">Панель мониторинга качества звонков использует API репозитория для управления со следующими сведениями:</span><span class="sxs-lookup"><span data-stu-id="b0d64-116">Call Quality Dashboard uses Repository API to manage the following information:</span></span> 
  
- <span data-ttu-id="b0d64-117">**Пользователь** - представление пользователей, имеющих доступ к репозиторию.</span><span class="sxs-lookup"><span data-stu-id="b0d64-117">**User** - representation of Users who have access to the repository.</span></span>
    
- <span data-ttu-id="b0d64-118">**Отчет** - содержится список запросов, сохраненных в виде контента в хранилище элементов.</span><span class="sxs-lookup"><span data-stu-id="b0d64-118">**Report** - contains a list of Queries, stored as a content in repository items.</span></span>
    
- <span data-ttu-id="b0d64-119">**Запрос** - используется для извлечения данных из интерфейса API данных, сохраненных в виде контента в хранилище элементов.</span><span class="sxs-lookup"><span data-stu-id="b0d64-119">**Query** - used to retrieve data from Data API, stored as a content in repository items.</span></span>
    
- <span data-ttu-id="b0d64-120">**Параметр пользователя** - описываются функциональные возможности приложений необязательно для пользователя.</span><span class="sxs-lookup"><span data-stu-id="b0d64-120">**User Setting** - describes an optional application behavior for the user.</span></span>
    
 <span data-ttu-id="b0d64-121">**Совместное использование (CORS) поддержка API репозитория междоменных ресурсов**</span><span class="sxs-lookup"><span data-stu-id="b0d64-121">**Cross-Origin Resource Sharing (CORS) Support for Repository API**</span></span>
  
<span data-ttu-id="b0d64-122">Репозиторий API поддерживает общий доступ к междоменных ресурсов (CORS).</span><span class="sxs-lookup"><span data-stu-id="b0d64-122">Repository API supports Cross-Origin Resource Sharing (CORS).</span></span> <span data-ttu-id="b0d64-123">CORS — это функция HTTP, который позволяет в рамках одного домена под управлением веб-приложения для доступа к ресурсам в другом домене.</span><span class="sxs-lookup"><span data-stu-id="b0d64-123">CORS is an HTTP feature that enables a web application running under one domain to access resources in another domain.</span></span> <span data-ttu-id="b0d64-124">Веб-браузеры реализации ограничения безопасности, известных как политики единого происхождения [Политики единого происхождения](https://www.w3.org/Security/wiki/Same_Origin_Policy) , не позволяющей веб-страницы из вызова API в другом домене.</span><span class="sxs-lookup"><span data-stu-id="b0d64-124">Web browsers implement a security restriction known as [Same-Origin Policy](https://www.w3.org/Security/wiki/Same_Origin_Policy) same-origin policy that prevents a web page from calling APIs in a different domain.</span></span> <span data-ttu-id="b0d64-125">CORS предоставляет безопасный способ разрешить один домене (источник) вызов API-интерфейсы в другой домен.</span><span class="sxs-lookup"><span data-stu-id="b0d64-125">CORS provides a secure way to allow one domain (the origin domain) to call APIs in another domain.</span></span> <span data-ttu-id="b0d64-126">[Спецификация CORS](https://www.w3.org/TR/cors/) для получения дополнительных сведений см на CORS.</span><span class="sxs-lookup"><span data-stu-id="b0d64-126">See the [CORS specification](https://www.w3.org/TR/cors/) for details on CORS.</span></span>
  
 <span data-ttu-id="b0d64-127">**Включение CORS для API репозитория**</span><span class="sxs-lookup"><span data-stu-id="b0d64-127">**Enabling CORS for Repository API**</span></span>
  
 <span data-ttu-id="b0d64-128">Ниже приведен фрагмент файла Web.config API репозитория, отражающая двух доменов, перечисленных в параметрах приложения corsTrustedOrigin.</span><span class="sxs-lookup"><span data-stu-id="b0d64-128">The following is an excerpt of Repository API web.config, showing two domains listed in corsTrustedOrigin application settings.</span></span> <span data-ttu-id="b0d64-129">Все запросы, выполненные с скрипты, загруженными из этих серверов являются доверенными API репозитория.</span><span class="sxs-lookup"><span data-stu-id="b0d64-129">All requests made by the scripts loaded from these servers are trusted by Repository API.</span></span>
  
<span data-ttu-id="b0d64-130">Не забудьте включить точное протокол, имя узла и порта (если они имеются).</span><span class="sxs-lookup"><span data-stu-id="b0d64-130">Remember to include the exact protocol, host name, and port (if any).</span></span> <span data-ttu-id="b0d64-131">Не следует поместить какие-либо прямая косая черта (/) знаков в конце.</span><span class="sxs-lookup"><span data-stu-id="b0d64-131">Do not to put any forward slash character (/) at the end.</span></span> <span data-ttu-id="b0d64-132">Несколько записей можно указать, разделив их запятыми.</span><span class="sxs-lookup"><span data-stu-id="b0d64-132">Multiple entries can be specified by separating with commas.</span></span>
  
```
<repositoryConfiguration>
    <service corsTrustedOrigin="https://<trusted-server>,http://<another-trusted-domain>:8080"" />
    <diagnostics eventLevel="Verbose" systemLoggedEventLevel="Error">
      <traceLog enabled="true" fileName="repository_trace.log" />
    </diagnostics>
 </repositoryConfiguration>
```


