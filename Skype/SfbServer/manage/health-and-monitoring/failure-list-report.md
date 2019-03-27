---
title: FAILURE List Report в Скайп для Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b6f3a605-e0c6-461e-b17a-41d8039ace9d
description: 'Сводка: Сведения об отчете списка сбоев в Скайп Business Server.'
ms.openlocfilehash: f286dfe288b82b1e8ab0f5b4956c4f75c5bd72a2
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30899612"
---
# <a name="failure-list-report-in-skype-for-business-server"></a><span data-ttu-id="878f4-103">FAILURE List Report в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="878f4-103">Failure List Report in Skype for Business Server</span></span> 
 
<span data-ttu-id="878f4-104">**Сводка:** Сведения об отчете списка сбоев в Скайп Business Server.</span><span class="sxs-lookup"><span data-stu-id="878f4-104">**Summary:** Learn about the Failure List Report in Skype for Business Server.</span></span>
  
<span data-ttu-id="878f4-p101">Отчет Failure List (Список ошибок) предоставляет сведения об участниках однорангового сеанса (конференции), завершившегося с ошибкой. Эти сведения содержат URI пользователя, у которого возникла ошибка, а также код ответа SIP и ИД диагностики, связанные с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="878f4-p101">The Failure List report provides information about the individual participants who took part in a failed peer-to-peer or conferencing session. This information includes the URI of the user who experienced the problem, as well as the SIP Response code and Diagnostic ID associated with the failure.</span></span>
  
## <a name="accessing-the-failure-list-report"></a><span data-ttu-id="878f4-107">Доступ к отчету Failure List (Список ошибок)</span><span class="sxs-lookup"><span data-stu-id="878f4-107">Accessing the Failure List Report</span></span>

<span data-ttu-id="878f4-108">Failure List Report открыть, щелкнув какую-либо из следующих показателей [Отчета о распределении сбоев в Скайп для Business Server](failure-distribution-report.md):</span><span class="sxs-lookup"><span data-stu-id="878f4-108">The Failure List Report is accessed by clicking any of the following metrics on the [Failure Distribution Report in Skype for Business Server](failure-distribution-report.md):</span></span>
  
- <span data-ttu-id="878f4-109">Top diagnostic reasons (sessions) (Основные причины диагностики (сеансы))</span><span class="sxs-lookup"><span data-stu-id="878f4-109">Top diagnostic reasons (sessions)</span></span>
    
- <span data-ttu-id="878f4-110">Top modalities (sessions) (Основные условия (сеансы))</span><span class="sxs-lookup"><span data-stu-id="878f4-110">Top modalities (sessions)</span></span>
    
- <span data-ttu-id="878f4-111">Top pools (sessions) (Основные пулы (сеансы))</span><span class="sxs-lookup"><span data-stu-id="878f4-111">Top pools (sessions)</span></span>
    
- <span data-ttu-id="878f4-112">Top sources (sessions) (Основные источники (сеансы))</span><span class="sxs-lookup"><span data-stu-id="878f4-112">Top sources (sessions)</span></span>
    
- <span data-ttu-id="878f4-113">Top components (sessions) (Основные компоненты (сеансы))</span><span class="sxs-lookup"><span data-stu-id="878f4-113">Top components (sessions)</span></span>
    
- <span data-ttu-id="878f4-114">Top from users (sessions) (Основные пользователи с ошибками исходящей связи (сеансы))</span><span class="sxs-lookup"><span data-stu-id="878f4-114">Top from users (sessions)</span></span>
    
- <span data-ttu-id="878f4-115">Top to users (sessions) (Основные пользователи с ошибками входящей связи (сеансы))</span><span class="sxs-lookup"><span data-stu-id="878f4-115">Top to users (sessions)</span></span>
    
- <span data-ttu-id="878f4-116">Top from user agents (sessions) (Основные агенты пользователей, используемые в сеансах, завершившихся с ошибками (сеансы))</span><span class="sxs-lookup"><span data-stu-id="878f4-116">Top from user agents (sessions)</span></span>
    
<span data-ttu-id="878f4-117">Из Failure List Report, щелкнув метрику сведений о сеансе для сеанса peer-to-peer можно вызвать [Peer-to-Peer сеанса подробный отчет в Скайп для Business Server](peer-to-peer-session-detail-report.md) .</span><span class="sxs-lookup"><span data-stu-id="878f4-117">From the Failure List Report you can access the [Peer-to-Peer Session Detail Report in Skype for Business Server](peer-to-peer-session-detail-report.md) by clicking the Session detail metric for a peer-to-peer session.</span></span> <span data-ttu-id="878f4-118">Чтобы открыть отчет сведений о конференции, нажмите показатель «Конференция» для конференции.</span><span class="sxs-lookup"><span data-stu-id="878f4-118">You can also access the Conference Detail Report by clicking the Conference metric for a conference.</span></span>
  
## <a name="making-the-best-use-of-the-failure-list-report"></a><span data-ttu-id="878f4-119">Рекомендации по использованию отчета Failure List (Список ошибок)</span><span class="sxs-lookup"><span data-stu-id="878f4-119">Making the Best Use of the Failure List Report</span></span>

<span data-ttu-id="878f4-p103">Чтобы просмотреть описание кода ответа или ИД диагностики, наведите указатель мыши на значение. Например, если вы наведете указатель мыши на Diagnostic ID (ИД диагностики) 7 025, то вы увидите следующую всплывающую подсказку:</span><span class="sxs-lookup"><span data-stu-id="878f4-p103">In the Failure List Report, you can view a description for each Response code or each Diagnostic ID simply by holding your mouse over that value. For example, if you hold your mouse over Diagnostic ID 7025 you'll see the following displayed in a tooltip:</span></span>
  
<span data-ttu-id="878f4-122">Internal server error creating media for user (Внутренняя ошибка сервера при создании среды для пользователя).</span><span class="sxs-lookup"><span data-stu-id="878f4-122">Internal server error creating media for user.</span></span>
  
<span data-ttu-id="878f4-123">Важно отметить, что отчет по списку ошибок не предоставляет прямой способ получения списка всех пользователей, принимавших участие в хотя бы одном сеансе, закончившемся с ошибкой, или способ определения пользователей, которые наиболее часто участвовали в сеансах, закончившихся с ошибками.</span><span class="sxs-lookup"><span data-stu-id="878f4-123">It's important to note that the Failure List Report does not provide a straightforward way to directly retrieve a list of all the users who participated in at least one failed session, nor does it provide a way to determine which users were most-often involved in a failed session.</span></span> <span data-ttu-id="878f4-124">(Всего, Failure List Report равно нет возможности фильтрации). Тем не менее если экспортировать данные, а затем преобразовать его в файл с разделителями-запятыми, чтобы найти ответы на вопросы, например, можно использовать Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="878f4-124">(For one thing, the Failure List Report has no filtering capabilities.) However, if you export the data and then convert it to a comma-separated values file, you can use Windows PowerShell to find the answers to questions like those.</span></span> <span data-ttu-id="878f4-125">Предположим, что вы сохранили данные в CSV-файле C:\Data\Failure_List.csv.</span><span class="sxs-lookup"><span data-stu-id="878f4-125">For example, suppose you save the data to a .CSV file named C:\Data\Failure_List.csv.</span></span> <span data-ttu-id="878f4-126">Чтобы получить список пользователей, принимавших участие в хотя бы одном сеансе, закончившемся с ошибкой, используйте следующие команды:</span><span class="sxs-lookup"><span data-stu-id="878f4-126">Based on the data saved in that file, this command lists all the users who were involved in at least one failed session:</span></span> 
  
```
$failures = Import-Csv -Path " C:\Data\Failure_List.csv"
$failure |Sort-Object "From user" | Select-Object "From user" -Unique
```

<span data-ttu-id="878f4-127">Эти команды возвращают сведения, схожие со следующими:</span><span class="sxs-lookup"><span data-stu-id="878f4-127">That command will return a list similar to this:</span></span>
  
<pre>
    From user
    ----
    Pilar.Ackerman@litwareinc.com
    Henrik.Jensen@litwareinc.com
    Gilead.Amosnino@litwareinc.com
    David.Ahs@litwareinc.com
    Ken.Myer@litwareinc.com
</pre>

<span data-ttu-id="878f4-128">Следующие команды возвращают общее число сеансов каждого пользователя, завершившихся с ошибкой:</span><span class="sxs-lookup"><span data-stu-id="878f4-128">These two commands report back the total number of failed sessions that each user was involved in:</span></span>
  
```
$failures = Import-Csv -Path "C:\Data\Failure_List.csv"
$failures | Group-Object "From user" | Select-Object Count, Name | Sort-Object -Property Count -Descending
```

<span data-ttu-id="878f4-129">Эти команды возвращают сведения, схожие со следующими:</span><span class="sxs-lookup"><span data-stu-id="878f4-129">That will return data similar to this:</span></span>
  
<pre>
Count    Name
 -----    ----
    20    Pilar.Ackerman@litwareinc.com
    20    David.Ahs@litwareinc.com
    16    Gilead.Amosnino@litwareinc.com
    16    Ken.Myero@litwareinc.com
    14    Henrik.Jensen@litwareinc.com
</pre>

## <a name="filters"></a><span data-ttu-id="878f4-130">Фильтры</span><span class="sxs-lookup"><span data-stu-id="878f4-130">Filters</span></span>

<span data-ttu-id="878f4-p105">Нет. В отчете Failure List (Список ошибок) нельзя использовать фильтр.</span><span class="sxs-lookup"><span data-stu-id="878f4-p105">None. You cannot filter the Failure List Report.</span></span>
  
## <a name="metrics"></a><span data-ttu-id="878f4-133">Показатели</span><span class="sxs-lookup"><span data-stu-id="878f4-133">Metrics</span></span>

<span data-ttu-id="878f4-134">В следующей таблице приведены сведения, содержащиеся в отчете Failure List (Список ошибок) для каждого звонка, завершившегося с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="878f4-134">The following table lists the information provided in the Failure List Report for each failed call.</span></span>
  
<span data-ttu-id="878f4-135">**Показатели отчета Failure List (Список ошибок)**</span><span class="sxs-lookup"><span data-stu-id="878f4-135">**Failure List Report Metrics**</span></span>

|<span data-ttu-id="878f4-136">**Имя**.</span><span class="sxs-lookup"><span data-stu-id="878f4-136">**Name**</span></span>|<span data-ttu-id="878f4-137">**Поддержка сортировки**</span><span class="sxs-lookup"><span data-stu-id="878f4-137">**Can you sort on this item?**</span></span>|<span data-ttu-id="878f4-138">**Описание**.</span><span class="sxs-lookup"><span data-stu-id="878f4-138">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="878f4-139">**Время создания отчета**</span><span class="sxs-lookup"><span data-stu-id="878f4-139">**Reported time**</span></span> <br/> |<span data-ttu-id="878f4-140">Нет</span><span class="sxs-lookup"><span data-stu-id="878f4-140">No</span></span>  <br/> |<span data-ttu-id="878f4-141">Дата и время создания отчета.</span><span class="sxs-lookup"><span data-stu-id="878f4-141">Date and time the report was recorded.</span></span>  <br/> |
|<span data-ttu-id="878f4-142">**Запрос**</span><span class="sxs-lookup"><span data-stu-id="878f4-142">**Request**</span></span> <br/> |<span data-ttu-id="878f4-143">Нет</span><span class="sxs-lookup"><span data-stu-id="878f4-143">No</span></span>  <br/> |<span data-ttu-id="878f4-p106">Тип запроса SIP, завершившегося с ошибкой. Например, INVITE или BYE.</span><span class="sxs-lookup"><span data-stu-id="878f4-p106">SIP request type that failed. For example, INVITE or BYE.</span></span>  <br/> |
|<span data-ttu-id="878f4-146">**Код ответа**</span><span class="sxs-lookup"><span data-stu-id="878f4-146">**Response code**</span></span> <br/> |<span data-ttu-id="878f4-147">Нет</span><span class="sxs-lookup"><span data-stu-id="878f4-147">No</span></span>  <br/> |<span data-ttu-id="878f4-148">Код ответа SIP, отправленный при сбое конференции.</span><span class="sxs-lookup"><span data-stu-id="878f4-148">SIP response code sent when the conference failed.</span></span>  <br/> |
|<span data-ttu-id="878f4-149">**ИД диагностики**</span><span class="sxs-lookup"><span data-stu-id="878f4-149">**Diagnostic ID**</span></span> <br/> |<span data-ttu-id="878f4-150">Нет</span><span class="sxs-lookup"><span data-stu-id="878f4-150">No</span></span>  <br/> |<span data-ttu-id="878f4-151">Прикрепленный к SIP-сообщению уникальный идентификатор (в форме заголовка ms-diagnostics), который часто содержит информацию, полезную при поиске и устранении ошибок.</span><span class="sxs-lookup"><span data-stu-id="878f4-151">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span>  <br/> |
|<span data-ttu-id="878f4-152">**Время присоединения (мс)**</span><span class="sxs-lookup"><span data-stu-id="878f4-152">**Join cost time (ms)**</span></span> <br/> |<span data-ttu-id="878f4-153">Нет</span><span class="sxs-lookup"><span data-stu-id="878f4-153">No</span></span>  <br/> |<span data-ttu-id="878f4-154">Период времени (в миллисекундах), требуемый для присоединения пользователя к конференции.</span><span class="sxs-lookup"><span data-stu-id="878f4-154">Amount of time (in milliseconds) required for the user to join the conference.</span></span>  <br/> |
|<span data-ttu-id="878f4-155">**Пользователь-отправитель**</span><span class="sxs-lookup"><span data-stu-id="878f4-155">**From user**</span></span> <br/> |<span data-ttu-id="878f4-156">Нет</span><span class="sxs-lookup"><span data-stu-id="878f4-156">No</span></span>  <br/> |<span data-ttu-id="878f4-157">SIP-адрес пользователя, инициировавшего вызов.</span><span class="sxs-lookup"><span data-stu-id="878f4-157">SIP address of the user who initiated the call.</span></span>  <br/> |
|<span data-ttu-id="878f4-158">**Агент пользователя, инициатора сеанса**</span><span class="sxs-lookup"><span data-stu-id="878f4-158">**From user agent**</span></span> <br/> |<span data-ttu-id="878f4-159">Нет</span><span class="sxs-lookup"><span data-stu-id="878f4-159">No</span></span>  <br/> |<span data-ttu-id="878f4-160">Программное обеспечение, используемое конечной точкой пользователя, инициировавшего звонок.</span><span class="sxs-lookup"><span data-stu-id="878f4-160">Software used by the endpoint of the user who initiated the call.</span></span>  <br/> |
|<span data-ttu-id="878f4-161">**Пользователь-получатель**</span><span class="sxs-lookup"><span data-stu-id="878f4-161">**To user**</span></span> <br/> |<span data-ttu-id="878f4-162">Нет</span><span class="sxs-lookup"><span data-stu-id="878f4-162">No</span></span>  <br/> |<span data-ttu-id="878f4-163">SIP-адрес пользователя, принявшего звонок.</span><span class="sxs-lookup"><span data-stu-id="878f4-163">SIP address of the user who was being called.</span></span>  <br/> |
   

