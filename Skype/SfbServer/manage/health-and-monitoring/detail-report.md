---
title: Подробный отчет по конференции в Скайп для Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1d61cd81-dcfe-40b4-9a41-a73b038bc216
description: 'Сводка: Сведения о подробный отчет по конференции используется в Скайп для Business Server.'
ms.openlocfilehash: 122cd3b8bdc69342b4d0f55c9fe5168fdc44757d
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32225337"
---
# <a name="conference-detail-report-in-skype-for-business-server"></a><span data-ttu-id="e0aad-103">Подробный отчет по конференции в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="e0aad-103">Conference Detail Report in Skype for Business Server</span></span>

<span data-ttu-id="e0aad-104">**Сводка:** Узнайте о подробный отчет по конференции используется в Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="e0aad-104">**Summary:** Learn about the Conference Detail Report used in Skype for Business Server.</span></span>

<span data-ttu-id="e0aad-p101">Подробный отчет по конференции содержит подробную информацию обо всех пользователях, принимавших участие в конференции. Например, вы можете просматривать такую информацию, как дата и время присоединения пользователя к конференции, дата и время покидания конференции, а также агент пользователя конечной точки, использованный для подключения этого пользователя к конференции. Вы также можете просмотреть информацию о роли пользователя в каждой конференции (например, выступающий или участник). Возможно, еще важнее то, что вы можете быстро просмотреть, какие пользователи успешно присоединились к конференции и участвовали в ней и какие пользователи не смогли этого сделать.</span><span class="sxs-lookup"><span data-stu-id="e0aad-p101">The Conference Detail Report provides detailed information about all the users who participated in a conference. For example, you can see such information as the date and time that a user joined the conference, the date and time that the user left the conference, and the user agent of the endpoint that was used to connect that user to the conference. You can also see information the user's role in each conference (for example, Presenter or Attendee). Perhaps most important, you get quickly see which users successfully join and complete the conference, and which users were not able to successfully join and complete the conference.</span></span>

## <a name="accessing-the-conference-detail-report"></a><span data-ttu-id="e0aad-109">Доступ к подробному отчету по конференции</span><span class="sxs-lookup"><span data-stu-id="e0aad-109">Accessing the Conference Detail Report</span></span>

<span data-ttu-id="e0aad-110">Подробный отчет по конференции можно открыть из следующих отчетов:</span><span class="sxs-lookup"><span data-stu-id="e0aad-110">The Conference Detail Report can be accessed from the following reports:</span></span>

- <span data-ttu-id="e0aad-111">[Call Admission Control Report](call-admission-control-report.md) (щелкнув метрику сведений для конференции)</span><span class="sxs-lookup"><span data-stu-id="e0aad-111">The [Call Admission Control Report](call-admission-control-report.md) (by clicking the Detail metric for a conference)</span></span>

- <span data-ttu-id="e0aad-112">[Failure List Report](failure-list-report.md) (щелкнув метрику конференции)</span><span class="sxs-lookup"><span data-stu-id="e0aad-112">The [Failure List Report](failure-list-report.md) (by clicking the Conference metric)</span></span>

- <span data-ttu-id="e0aad-113">[User Activity Report](call-diagnostic-reports-per-user.md) (щелкнув метрику URI конференции)</span><span class="sxs-lookup"><span data-stu-id="e0aad-113">The [User Activity Report](call-diagnostic-reports-per-user.md) (by clicking the Conference URI metric)</span></span>

<span data-ttu-id="e0aad-114">Из подробного отчета по конференции можно получить доступ к [Диагностики Repor](diagnostic-report.md) , щелкнув метрику диагностического отчета (сведений).</span><span class="sxs-lookup"><span data-stu-id="e0aad-114">From the Conference Detail Report you can access the [Diagnostic Repor](diagnostic-report.md) by clicking the Diagnostic Report (Detail) metric.</span></span>

## <a name="filters"></a><span data-ttu-id="e0aad-115">Фильтры</span><span class="sxs-lookup"><span data-stu-id="e0aad-115">Filters</span></span>

<span data-ttu-id="e0aad-p102">Нет. Вы не можете фильтровать подробный отчет по конференции.</span><span class="sxs-lookup"><span data-stu-id="e0aad-p102">None. You cannot filter on the Conference Detail Report.</span></span>

## <a name="metrics"></a><span data-ttu-id="e0aad-118">Показатели</span><span class="sxs-lookup"><span data-stu-id="e0aad-118">Metrics</span></span>

<span data-ttu-id="e0aad-119">В следующей таблице приведены сведения из раздела информации о конференции, входящего в подробный отчет по конференции.</span><span class="sxs-lookup"><span data-stu-id="e0aad-119">The following table lists the information provided in the Conference Information section of the Conference Detail Report.</span></span>

<span data-ttu-id="e0aad-120">**Метрики информации о конференции**</span><span class="sxs-lookup"><span data-stu-id="e0aad-120">**Conference Information Metrics**</span></span>


| <span data-ttu-id="e0aad-121">**Имя**.</span><span class="sxs-lookup"><span data-stu-id="e0aad-121">**Name**</span></span>                 | <span data-ttu-id="e0aad-122">**Описание**</span><span class="sxs-lookup"><span data-stu-id="e0aad-122">**Description**</span></span>                                                                                                            |
|:-------------------------|:---------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="e0aad-123">**Идентификатор URI конференции**</span><span class="sxs-lookup"><span data-stu-id="e0aad-123">**Conference URI**</span></span> <br/> | <span data-ttu-id="e0aad-p103">URI, назначенный конференции. Например:</span><span class="sxs-lookup"><span data-stu-id="e0aad-p103">URI assigned to the conference. For example:</span></span>  <br/> <span data-ttu-id="e0aad-126">sip:kmyer@litwareinc.com;gruu;opaque=app:conf:focus:id:drg2y8v4</span><span class="sxs-lookup"><span data-stu-id="e0aad-126">sip:kmyer@litwareinc.com;gruu;opaque=app:conf:focus:id:drg2y8v4</span></span>  <br/> |
| <span data-ttu-id="e0aad-127">**Полное доменное имя пула**</span><span class="sxs-lookup"><span data-stu-id="e0aad-127">**Pool FQDN**</span></span> <br/>      | <span data-ttu-id="e0aad-128">Полное доменное имя пула Регистратора или участвующего в сеансе пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="e0aad-128">Fully-qualified domain name of the Registrar pool or Edge Server involved in a session.</span></span>  <br/>                             |
| <span data-ttu-id="e0aad-129">**Время начала**</span><span class="sxs-lookup"><span data-stu-id="e0aad-129">**Start time**</span></span> <br/>     | <span data-ttu-id="e0aad-130">Дата и время начала конференции.</span><span class="sxs-lookup"><span data-stu-id="e0aad-130">Date and time that the conference started.</span></span>  <br/>                                                                          |
| <span data-ttu-id="e0aad-131">**Организатор**</span><span class="sxs-lookup"><span data-stu-id="e0aad-131">**Organizer**</span></span> <br/>      | <span data-ttu-id="e0aad-132">SIP-адрес пользователя, организовавшего конференцию.</span><span class="sxs-lookup"><span data-stu-id="e0aad-132">SIP address of the user who organized the conference.</span></span>  <br/>                                                               |
| <span data-ttu-id="e0aad-133">**Время окончания**</span><span class="sxs-lookup"><span data-stu-id="e0aad-133">**End time**</span></span> <br/>       | <span data-ttu-id="e0aad-134">Дата и время завершения конференции.</span><span class="sxs-lookup"><span data-stu-id="e0aad-134">Date and time that the conference ended.</span></span>  <br/>                                                                            |

<span data-ttu-id="e0aad-135">В следующей таблице приведены сведения из раздела участия в конференции, входящего в подробный отчет по конференции.</span><span class="sxs-lookup"><span data-stu-id="e0aad-135">The following table lists the information provided in the Conference Participation Section of the Conference Detail Report.</span></span>

<span data-ttu-id="e0aad-136">**Метрики участия в конференции**</span><span class="sxs-lookup"><span data-stu-id="e0aad-136">**Conference Participation Metrics**</span></span>

|<span data-ttu-id="e0aad-137">**Имя**.</span><span class="sxs-lookup"><span data-stu-id="e0aad-137">**Name**</span></span>|<span data-ttu-id="e0aad-138">**Описание**</span><span class="sxs-lookup"><span data-stu-id="e0aad-138">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="e0aad-139">**Пользователь**</span><span class="sxs-lookup"><span data-stu-id="e0aad-139">**User**</span></span> <br/> |<span data-ttu-id="e0aad-140">SIP-адрес пользователя, участвовавшего в конференции.</span><span class="sxs-lookup"><span data-stu-id="e0aad-140">SIP address of the user who participated in the conference.</span></span>  <br/> |
|<span data-ttu-id="e0aad-141">**Роль**</span><span class="sxs-lookup"><span data-stu-id="e0aad-141">**Role**</span></span> <br/> |<span data-ttu-id="e0aad-142">Роль (например, докладчик), которую играл участник конференции.</span><span class="sxs-lookup"><span data-stu-id="e0aad-142">Role (for example, Presenter) played by the conference participant.</span></span>  <br/> |
|<span data-ttu-id="e0aad-143">**Подключение**</span><span class="sxs-lookup"><span data-stu-id="e0aad-143">**Connectivity**</span></span> <br/> |<span data-ttu-id="e0aad-144">Подключение участника к сети, обычно из внутренней сети или из внешней сети.</span><span class="sxs-lookup"><span data-stu-id="e0aad-144">Network connectivity (typically From Internal or From External) for the participant.</span></span>  <br/> |
|<span data-ttu-id="e0aad-145">**Время присоединения**</span><span class="sxs-lookup"><span data-stu-id="e0aad-145">**Join time**</span></span> <br/> |<span data-ttu-id="e0aad-146">Дата и время присоединения участника к конференции.</span><span class="sxs-lookup"><span data-stu-id="e0aad-146">Date and time that the participant joined the conference.</span></span>  <br/> |
|<span data-ttu-id="e0aad-147">**Время выхода**</span><span class="sxs-lookup"><span data-stu-id="e0aad-147">**Leave time**</span></span> <br/> |<span data-ttu-id="e0aad-148">Дата и время, когда участник покинул конференцию.</span><span class="sxs-lookup"><span data-stu-id="e0aad-148">Date and time that the participant left the conference.</span></span>  <br/> |
|<span data-ttu-id="e0aad-149">**Агент пользователя**</span><span class="sxs-lookup"><span data-stu-id="e0aad-149">**User agent**</span></span> <br/> |<span data-ttu-id="e0aad-150">Идентификатор для программного обеспечения, используемого конечной точкой участника.</span><span class="sxs-lookup"><span data-stu-id="e0aad-150">Identifier for the software used by the participant's endpoint.</span></span>  <br/> |
|<span data-ttu-id="e0aad-151">**Диагностический отчет**</span><span class="sxs-lookup"><span data-stu-id="e0aad-151">**Diagnostic reports**</span></span> <br/> |<span data-ttu-id="e0aad-p104">Предоставляет сведения о диагностике и о поиске и устранении неполадок, включая коды отклика SIP, диагностические заголовки, значения времени присоединения к конференции и диагностические идентификаторы для неудачных сеансов.</span><span class="sxs-lookup"><span data-stu-id="e0aad-p104">Provides diagnostic and troubleshooting information. Including SIP response codes, diagnostic headers, conference join times, and diagnostic IDs for failed sessions.</span></span>  <br/> |

<span data-ttu-id="e0aad-154">В следующей таблице перечислены сведения, приведенные в разделе модальностей конференции подробный отчет по конференции.</span><span class="sxs-lookup"><span data-stu-id="e0aad-154">The following table lists the information provided in the Conference Modalities section of the Conference Detail Report.</span></span>

<span data-ttu-id="e0aad-155">**Метрики модальностей конференции**</span><span class="sxs-lookup"><span data-stu-id="e0aad-155">**Conference Modalities Metrics**</span></span>

|<span data-ttu-id="e0aad-156">**Имя**.</span><span class="sxs-lookup"><span data-stu-id="e0aad-156">**Name**</span></span>|<span data-ttu-id="e0aad-157">**Описание**</span><span class="sxs-lookup"><span data-stu-id="e0aad-157">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="e0aad-158">**Пользователь**</span><span class="sxs-lookup"><span data-stu-id="e0aad-158">**User**</span></span> <br/> |<span data-ttu-id="e0aad-159">SIP-адрес пользователя, участвовавшего в конференции.</span><span class="sxs-lookup"><span data-stu-id="e0aad-159">SIP address of the user who participated in the conference.</span></span>  <br/> |
|<span data-ttu-id="e0aad-160">**Время присоединения**</span><span class="sxs-lookup"><span data-stu-id="e0aad-160">**Join time**</span></span> <br/> |<span data-ttu-id="e0aad-161">Дата и время присоединения участника к конференции.</span><span class="sxs-lookup"><span data-stu-id="e0aad-161">Date and time that the participant joined the conference.</span></span>  <br/> |
|<span data-ttu-id="e0aad-162">**Время ухода**</span><span class="sxs-lookup"><span data-stu-id="e0aad-162">**Leave time**</span></span> <br/> |<span data-ttu-id="e0aad-163">Дата и время покидания участником конференции.</span><span class="sxs-lookup"><span data-stu-id="e0aad-163">Date and time that a participant left the conference.</span></span>  <br/> |
|<span data-ttu-id="e0aad-164">**URI сервера конференций**</span><span class="sxs-lookup"><span data-stu-id="e0aad-164">**Conferencing server URI**</span></span> <br/> |<span data-ttu-id="e0aad-165">URI для используемого в конференции сервера конференций.</span><span class="sxs-lookup"><span data-stu-id="e0aad-165">URI for the Conferencing server used in the conference.</span></span>  <br/> |
|<span data-ttu-id="e0aad-166">**Диагностический отчет**</span><span class="sxs-lookup"><span data-stu-id="e0aad-166">**Diagnostic reports**</span></span> <br/> |<span data-ttu-id="e0aad-p105">Предоставляет сведения о диагностике и о поиске и устранении неполадок, включая коды отклика SIP, диагностические заголовки, значения времени присоединения к конференции и диагностические идентификаторы для неудачных сеансов.</span><span class="sxs-lookup"><span data-stu-id="e0aad-p105">Provides diagnostic and troubleshooting information. Including SIP response codes, diagnostic headers, conference join times, and diagnostic IDs for failed sessions.</span></span>  <br/> |


