---
title: Детальный отчет о конференциях в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1d61cd81-dcfe-40b4-9a41-a73b038bc216
description: 'Сводка: сведения об отчете "сведения о конференции", используемом в Skype для бизнеса Server.'
ms.openlocfilehash: 5b88ae62c7d06437b3502bd72dd965fc26fbfcb6
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34305789"
---
# <a name="conference-detail-report-in-skype-for-business-server"></a><span data-ttu-id="bf93d-103">Детальный отчет о конференциях в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="bf93d-103">Conference Detail Report in Skype for Business Server</span></span>

<span data-ttu-id="bf93d-104">**Сводка:** Сведения об отчете "сведения о конференции", используемом в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="bf93d-104">**Summary:** Learn about the Conference Detail Report used in Skype for Business Server.</span></span>

<span data-ttu-id="bf93d-p101">Подробный отчет по конференции содержит подробную информацию обо всех пользователях, принимавших участие в конференции. Например, вы можете просматривать такую информацию, как дата и время присоединения пользователя к конференции, дата и время покидания конференции, а также агент пользователя конечной точки, использованный для подключения этого пользователя к конференции. Вы также можете просмотреть информацию о роли пользователя в каждой конференции (например, выступающий или участник). Возможно, еще важнее то, что вы можете быстро просмотреть, какие пользователи успешно присоединились к конференции и участвовали в ней и какие пользователи не смогли этого сделать.</span><span class="sxs-lookup"><span data-stu-id="bf93d-p101">The Conference Detail Report provides detailed information about all the users who participated in a conference. For example, you can see such information as the date and time that a user joined the conference, the date and time that the user left the conference, and the user agent of the endpoint that was used to connect that user to the conference. You can also see information the user's role in each conference (for example, Presenter or Attendee). Perhaps most important, you get quickly see which users successfully join and complete the conference, and which users were not able to successfully join and complete the conference.</span></span>

## <a name="accessing-the-conference-detail-report"></a><span data-ttu-id="bf93d-109">Доступ к подробному отчету по конференции</span><span class="sxs-lookup"><span data-stu-id="bf93d-109">Accessing the Conference Detail Report</span></span>

<span data-ttu-id="bf93d-110">Подробный отчет по конференции можно открыть из следующих отчетов:</span><span class="sxs-lookup"><span data-stu-id="bf93d-110">The Conference Detail Report can be accessed from the following reports:</span></span>

- <span data-ttu-id="bf93d-111">[Call Admission Control Report](call-admission-control-report.md) (щелкнув метрику сведений для конференции)</span><span class="sxs-lookup"><span data-stu-id="bf93d-111">The [Call Admission Control Report](call-admission-control-report.md) (by clicking the Detail metric for a conference)</span></span>

- <span data-ttu-id="bf93d-112">[Failure List Report](failure-list-report.md) (щелкнув метрику конференции)</span><span class="sxs-lookup"><span data-stu-id="bf93d-112">The [Failure List Report](failure-list-report.md) (by clicking the Conference metric)</span></span>

- <span data-ttu-id="bf93d-113">[User Activity Report](call-diagnostic-reports-per-user.md) (щелкнув метрику URI конференции)</span><span class="sxs-lookup"><span data-stu-id="bf93d-113">The [User Activity Report](call-diagnostic-reports-per-user.md) (by clicking the Conference URI metric)</span></span>

<span data-ttu-id="bf93d-114">В отчете сведения о конференции вы можете получить доступ к [репозиторию диагностики](diagnostic-report.md) , щелкнув метрику диагностического отчета (подробности).</span><span class="sxs-lookup"><span data-stu-id="bf93d-114">From the Conference Detail Report you can access the [Diagnostic Repor](diagnostic-report.md) by clicking the Diagnostic Report (Detail) metric.</span></span>

## <a name="filters"></a><span data-ttu-id="bf93d-115">Фильтры</span><span class="sxs-lookup"><span data-stu-id="bf93d-115">Filters</span></span>

<span data-ttu-id="bf93d-p102">Нет. Вы не можете фильтровать подробный отчет по конференции.</span><span class="sxs-lookup"><span data-stu-id="bf93d-p102">None. You cannot filter on the Conference Detail Report.</span></span>

## <a name="metrics"></a><span data-ttu-id="bf93d-118">Показатели</span><span class="sxs-lookup"><span data-stu-id="bf93d-118">Metrics</span></span>

<span data-ttu-id="bf93d-119">В следующей таблице приведены сведения из раздела информации о конференции, входящего в подробный отчет по конференции.</span><span class="sxs-lookup"><span data-stu-id="bf93d-119">The following table lists the information provided in the Conference Information section of the Conference Detail Report.</span></span>

<span data-ttu-id="bf93d-120">**Метрики информации о конференции**</span><span class="sxs-lookup"><span data-stu-id="bf93d-120">**Conference Information Metrics**</span></span>


| <span data-ttu-id="bf93d-121">**Имя**.</span><span class="sxs-lookup"><span data-stu-id="bf93d-121">**Name**</span></span>                 | <span data-ttu-id="bf93d-122">**Описание**</span><span class="sxs-lookup"><span data-stu-id="bf93d-122">**Description**</span></span>                                                                                                            |
|:-------------------------|:---------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="bf93d-123">**Идентификатор URI конференции**</span><span class="sxs-lookup"><span data-stu-id="bf93d-123">**Conference URI**</span></span> <br/> | <span data-ttu-id="bf93d-p103">URI, назначенный конференции. Например:</span><span class="sxs-lookup"><span data-stu-id="bf93d-p103">URI assigned to the conference. For example:</span></span>  <br/> <span data-ttu-id="bf93d-126">sip:kmyer@litwareinc.com;gruu;opaque=app:conf:focus:id:drg2y8v4</span><span class="sxs-lookup"><span data-stu-id="bf93d-126">sip:kmyer@litwareinc.com;gruu;opaque=app:conf:focus:id:drg2y8v4</span></span>  <br/> |
| <span data-ttu-id="bf93d-127">**Полное доменное имя пула**</span><span class="sxs-lookup"><span data-stu-id="bf93d-127">**Pool FQDN**</span></span> <br/>      | <span data-ttu-id="bf93d-128">Полное доменное имя пула Регистратора или участвующего в сеансе пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="bf93d-128">Fully-qualified domain name of the Registrar pool or Edge Server involved in a session.</span></span>  <br/>                             |
| <span data-ttu-id="bf93d-129">**Время начала**</span><span class="sxs-lookup"><span data-stu-id="bf93d-129">**Start time**</span></span> <br/>     | <span data-ttu-id="bf93d-130">Дата и время начала конференции.</span><span class="sxs-lookup"><span data-stu-id="bf93d-130">Date and time that the conference started.</span></span>  <br/>                                                                          |
| <span data-ttu-id="bf93d-131">**Организатор**</span><span class="sxs-lookup"><span data-stu-id="bf93d-131">**Organizer**</span></span> <br/>      | <span data-ttu-id="bf93d-132">SIP-адрес пользователя, организовавшего конференцию.</span><span class="sxs-lookup"><span data-stu-id="bf93d-132">SIP address of the user who organized the conference.</span></span>  <br/>                                                               |
| <span data-ttu-id="bf93d-133">**Время окончания**</span><span class="sxs-lookup"><span data-stu-id="bf93d-133">**End time**</span></span> <br/>       | <span data-ttu-id="bf93d-134">Дата и время завершения конференции.</span><span class="sxs-lookup"><span data-stu-id="bf93d-134">Date and time that the conference ended.</span></span>  <br/>                                                                            |

<span data-ttu-id="bf93d-135">В следующей таблице приведены сведения из раздела участия в конференции, входящего в подробный отчет по конференции.</span><span class="sxs-lookup"><span data-stu-id="bf93d-135">The following table lists the information provided in the Conference Participation Section of the Conference Detail Report.</span></span>

<span data-ttu-id="bf93d-136">**Метрики участия в конференции**</span><span class="sxs-lookup"><span data-stu-id="bf93d-136">**Conference Participation Metrics**</span></span>

|<span data-ttu-id="bf93d-137">**Имя**.</span><span class="sxs-lookup"><span data-stu-id="bf93d-137">**Name**</span></span>|<span data-ttu-id="bf93d-138">**Описание**</span><span class="sxs-lookup"><span data-stu-id="bf93d-138">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="bf93d-139">**Пользователь**</span><span class="sxs-lookup"><span data-stu-id="bf93d-139">**User**</span></span> <br/> |<span data-ttu-id="bf93d-140">SIP-адрес пользователя, участвовавшего в конференции.</span><span class="sxs-lookup"><span data-stu-id="bf93d-140">SIP address of the user who participated in the conference.</span></span>  <br/> |
|<span data-ttu-id="bf93d-141">**Роль**</span><span class="sxs-lookup"><span data-stu-id="bf93d-141">**Role**</span></span> <br/> |<span data-ttu-id="bf93d-142">Роль (например, докладчик), которую играл участник конференции.</span><span class="sxs-lookup"><span data-stu-id="bf93d-142">Role (for example, Presenter) played by the conference participant.</span></span>  <br/> |
|<span data-ttu-id="bf93d-143">**Подключение**</span><span class="sxs-lookup"><span data-stu-id="bf93d-143">**Connectivity**</span></span> <br/> |<span data-ttu-id="bf93d-144">Подключение участника к сети, обычно из внутренней сети или из внешней сети.</span><span class="sxs-lookup"><span data-stu-id="bf93d-144">Network connectivity (typically From Internal or From External) for the participant.</span></span>  <br/> |
|<span data-ttu-id="bf93d-145">**Время присоединения**</span><span class="sxs-lookup"><span data-stu-id="bf93d-145">**Join time**</span></span> <br/> |<span data-ttu-id="bf93d-146">Дата и время присоединения участника к конференции.</span><span class="sxs-lookup"><span data-stu-id="bf93d-146">Date and time that the participant joined the conference.</span></span>  <br/> |
|<span data-ttu-id="bf93d-147">**Время выхода**</span><span class="sxs-lookup"><span data-stu-id="bf93d-147">**Leave time**</span></span> <br/> |<span data-ttu-id="bf93d-148">Дата и время, когда участник покинул конференцию.</span><span class="sxs-lookup"><span data-stu-id="bf93d-148">Date and time that the participant left the conference.</span></span>  <br/> |
|<span data-ttu-id="bf93d-149">**Агент пользователя**</span><span class="sxs-lookup"><span data-stu-id="bf93d-149">**User agent**</span></span> <br/> |<span data-ttu-id="bf93d-150">Идентификатор программного обеспечения, используемого конечной точкой участника.</span><span class="sxs-lookup"><span data-stu-id="bf93d-150">Identifier for the software used by the participant's endpoint.</span></span>  <br/> |
|<span data-ttu-id="bf93d-151">**Диагностический отчет**</span><span class="sxs-lookup"><span data-stu-id="bf93d-151">**Diagnostic reports**</span></span> <br/> |<span data-ttu-id="bf93d-p104">Предоставляет сведения о диагностике и о поиске и устранении неполадок, включая коды отклика SIP, диагностические заголовки, значения времени присоединения к конференции и диагностические идентификаторы для неудачных сеансов.</span><span class="sxs-lookup"><span data-stu-id="bf93d-p104">Provides diagnostic and troubleshooting information. Including SIP response codes, diagnostic headers, conference join times, and diagnostic IDs for failed sessions.</span></span>  <br/> |

<span data-ttu-id="bf93d-154">В таблице ниже приведены сведения, указанные в разделе Conference модальностей в отчете "сведения о конференции".</span><span class="sxs-lookup"><span data-stu-id="bf93d-154">The following table lists the information provided in the Conference Modalities section of the Conference Detail Report.</span></span>

<span data-ttu-id="bf93d-155">**Метрики модальностей конференции**</span><span class="sxs-lookup"><span data-stu-id="bf93d-155">**Conference Modalities Metrics**</span></span>

|<span data-ttu-id="bf93d-156">**Имя**.</span><span class="sxs-lookup"><span data-stu-id="bf93d-156">**Name**</span></span>|<span data-ttu-id="bf93d-157">**Описание**</span><span class="sxs-lookup"><span data-stu-id="bf93d-157">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="bf93d-158">**Пользователь**</span><span class="sxs-lookup"><span data-stu-id="bf93d-158">**User**</span></span> <br/> |<span data-ttu-id="bf93d-159">SIP-адрес пользователя, участвовавшего в конференции.</span><span class="sxs-lookup"><span data-stu-id="bf93d-159">SIP address of the user who participated in the conference.</span></span>  <br/> |
|<span data-ttu-id="bf93d-160">**Время присоединения**</span><span class="sxs-lookup"><span data-stu-id="bf93d-160">**Join time**</span></span> <br/> |<span data-ttu-id="bf93d-161">Дата и время присоединения участника к конференции.</span><span class="sxs-lookup"><span data-stu-id="bf93d-161">Date and time that the participant joined the conference.</span></span>  <br/> |
|<span data-ttu-id="bf93d-162">**Время ухода**</span><span class="sxs-lookup"><span data-stu-id="bf93d-162">**Leave time**</span></span> <br/> |<span data-ttu-id="bf93d-163">Дата и время покидания участником конференции.</span><span class="sxs-lookup"><span data-stu-id="bf93d-163">Date and time that a participant left the conference.</span></span>  <br/> |
|<span data-ttu-id="bf93d-164">**URI сервера конференций**</span><span class="sxs-lookup"><span data-stu-id="bf93d-164">**Conferencing server URI**</span></span> <br/> |<span data-ttu-id="bf93d-165">URI для используемого в конференции сервера конференций.</span><span class="sxs-lookup"><span data-stu-id="bf93d-165">URI for the Conferencing server used in the conference.</span></span>  <br/> |
|<span data-ttu-id="bf93d-166">**Диагностический отчет**</span><span class="sxs-lookup"><span data-stu-id="bf93d-166">**Diagnostic reports**</span></span> <br/> |<span data-ttu-id="bf93d-p105">Предоставляет сведения о диагностике и о поиске и устранении неполадок, включая коды отклика SIP, диагностические заголовки, значения времени присоединения к конференции и диагностические идентификаторы для неудачных сеансов.</span><span class="sxs-lookup"><span data-stu-id="bf93d-p105">Provides diagnostic and troubleshooting information. Including SIP response codes, diagnostic headers, conference join times, and diagnostic IDs for failed sessions.</span></span>  <br/> |


