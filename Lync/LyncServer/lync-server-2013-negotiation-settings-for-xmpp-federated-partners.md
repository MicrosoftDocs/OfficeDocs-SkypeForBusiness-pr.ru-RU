---
title: 'Lync Server 2013: параметры согласования для федеративных партнеров XMPP'
description: 'Lync Server 2013: параметры согласования для федеративных партнеров XMPP.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Negotiation settings for XMPP federated partners
ms:assetid: ef773942-ef92-4f71-85a1-738dfebdfa00
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552456(v=OCS.15)
ms:contentKeyID: 48679567
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6ac3d9c69d407dc750a1afb35f0a448869a88f09
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48578645"
---
# <a name="negotiation-settings-for-xmpp-federated-partners-in-lync-server-2013"></a><span data-ttu-id="acfb4-103">Параметры согласования для федеративных партнеров XMPP в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="acfb4-103">Negotiation settings for XMPP federated partners in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="acfb4-104">_**Последнее изменение темы:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="acfb4-104">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="acfb4-105">В конфигурации XMPP-партнера доступно значительное количество возможных комбинаций параметров для типов согласования.</span><span class="sxs-lookup"><span data-stu-id="acfb4-105">The settings for the negotiation types in the configuration of an XMPP Partner have a wide variety of possible combinations.</span></span> <span data-ttu-id="acfb4-106">Но не все эти комбинации являются допустимыми.</span><span class="sxs-lookup"><span data-stu-id="acfb4-106">Not all of these combinations are valid.</span></span> <span data-ttu-id="acfb4-107">В приведенной здесь таблице подробно описывается, какие параметры являются допустимыми, а какие — нет.</span><span class="sxs-lookup"><span data-stu-id="acfb4-107">The table detailed in this topic will define the valid and not valid settings.</span></span> <span data-ttu-id="acfb4-108">Распространенные конфигурации представлены в первой таблице, во второй таблице приведены все возможные комбинации.</span><span class="sxs-lookup"><span data-stu-id="acfb4-108">Common configurations are presented in the first table, the second table detailing all possible combinations.</span></span> <span data-ttu-id="acfb4-109">Обратите внимание на то, что вы не можете использовать *простую проверку подлинности и уровень безопасности* (SASL), **если** также не доступен протокол TLS ( *Transport Layer Security* ).</span><span class="sxs-lookup"><span data-stu-id="acfb4-109">Note that you cannot have *Simple Authentication and Security Layer* (SASL) **unless** *Transport Layer Security* (TLS) is also available.</span></span> <span data-ttu-id="acfb4-110">Данные SASL отправляются в незашифрованном (пригодном для чтения) формате, поэтому при их передаче следует использовать другие средства защиты, такие как TLS.</span><span class="sxs-lookup"><span data-stu-id="acfb4-110">SASL is sent in an unencrypted (readable) format and should never be transmitted unless protected by another means, such as TLS.</span></span>

### <a name="common-xmpp-federation-negotiation-methods"></a><span data-ttu-id="acfb4-111">Распространенные методы согласования федерации XMPP</span><span class="sxs-lookup"><span data-stu-id="acfb4-111">Common XMPP Federation Negotiation Methods</span></span>

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="acfb4-112">TLS (Transport Layer Security)</span><span class="sxs-lookup"><span data-stu-id="acfb4-112">Transport Layer Security (TLS)</span></span></th>
<th><span data-ttu-id="acfb4-113">SASL (Simple Authentication and Security Layer)</span><span class="sxs-lookup"><span data-stu-id="acfb4-113">Simple Authentication and Security Layer (SASL)</span></span></th>
<th><span data-ttu-id="acfb4-114">Проверка подлинности с обратным вызовом</span><span class="sxs-lookup"><span data-stu-id="acfb4-114">Dialback Authentication</span></span></th>
<th><span data-ttu-id="acfb4-115">Ожидаемые методы проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="acfb4-115">Expected Authentication Method(s)</span></span></th>
<th><span data-ttu-id="acfb4-116">Примечания</span><span class="sxs-lookup"><span data-stu-id="acfb4-116">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="acfb4-117">Обязательный</span><span class="sxs-lookup"><span data-stu-id="acfb4-117">Required</span></span></p></td>
<td><p><span data-ttu-id="acfb4-118">Обязательный</span><span class="sxs-lookup"><span data-stu-id="acfb4-118">Required</span></span></p></td>
<td><p><span data-ttu-id="acfb4-119">False</span><span class="sxs-lookup"><span data-stu-id="acfb4-119">False</span></span></p></td>
<td><p><span data-ttu-id="acfb4-120">SASL через TLS</span><span class="sxs-lookup"><span data-stu-id="acfb4-120">SASL over TLS</span></span></p></td>
<td><p><span data-ttu-id="acfb4-p102">Обязательное использование TLS и SASL помогает обеспечить безопасность потока сообщений SASL. Обратный вызов недоступен и не может применяться в качестве резервного метода, если федеративный XMPP-партнер не установил обязательное или необязательное использование TLS.</span><span class="sxs-lookup"><span data-stu-id="acfb4-p102">TLS and SASL required helps to ensure that the SASL message stream is secure. Dialback is not available and cannot be used for a fallback method if the XMPP federated partner has not set TLS to required or optional.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="acfb4-123">Обязательна</span><span class="sxs-lookup"><span data-stu-id="acfb4-123">Required</span></span></p></td>
<td><p><span data-ttu-id="acfb4-124">Необязательный</span><span class="sxs-lookup"><span data-stu-id="acfb4-124">Optional</span></span></p></td>
<td><p><span data-ttu-id="acfb4-125">Верно</span><span class="sxs-lookup"><span data-stu-id="acfb4-125">True</span></span></p></td>
<td><p><span data-ttu-id="acfb4-126">SASL через TLS, обратный вызов TLS, обратный вызов TCP</span><span class="sxs-lookup"><span data-stu-id="acfb4-126">SASL over TLS, TLS Dialback, TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="acfb4-p103">Если федеративный XMPP-партнер установил обязательное или необязательное использование SASL, в случае обязательного использования TLS применяется SASL. Если SASL недоступен, используется обратный вызов через TLS.</span><span class="sxs-lookup"><span data-stu-id="acfb4-p103">By requiring TLS, if the XMPP federated partner has set SASL to optional or required SASL is used. If SASL is not available, Dialback over TLS will be used.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="acfb4-129">Необязательный</span><span class="sxs-lookup"><span data-stu-id="acfb4-129">Optional</span></span></p></td>
<td><p><span data-ttu-id="acfb4-130">Необязательна</span><span class="sxs-lookup"><span data-stu-id="acfb4-130">Optional</span></span></p></td>
<td><p><span data-ttu-id="acfb4-131">Верно</span><span class="sxs-lookup"><span data-stu-id="acfb4-131">True</span></span></p></td>
<td><p><span data-ttu-id="acfb4-132">SASL через TLS, обратный вызов TLS, обратный вызов TCP</span><span class="sxs-lookup"><span data-stu-id="acfb4-132">SASL over TLS, TLS Dialback, TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="acfb4-p104">Хотя эти параметры и обеспечивают гибкость с точки зрения доступных методов согласования, они основаны на параметрах XMPP-партнера федерации. Если партнер задает обязательное или необязательное использование TLS, но SASL не поддерживается, будет доступен обратный вызов через TLS. Если партнер задает обязательное или необязательное использование TLS и SASL, используется оптимальный вариант TLS через SASL.</span><span class="sxs-lookup"><span data-stu-id="acfb4-p104">While very flexible in the negotiation methods offered, these settings rely on the XMPP federation partner’s settings. If the partner has TLS optional or required but SASL is not supported, TLS Dialback will be available. If the partner has TLS and SASL set to optional or required, the optimal selection of TLS over SASL is used.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="acfb4-136">Не поддерживается</span><span class="sxs-lookup"><span data-stu-id="acfb4-136">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="acfb4-137">Не поддерживается</span><span class="sxs-lookup"><span data-stu-id="acfb4-137">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="acfb4-138">Верно</span><span class="sxs-lookup"><span data-stu-id="acfb4-138">True</span></span></p></td>
<td><p><span data-ttu-id="acfb4-139">Обратный вызов TCP</span><span class="sxs-lookup"><span data-stu-id="acfb4-139">TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="acfb4-p105">Во многих случаях обратный вызов TCP является единственным возможным решением и обеспечивает некоторый уровень доверия, хотя желательно использовать другие варианты.</span><span class="sxs-lookup"><span data-stu-id="acfb4-p105">In many cases, TCP Dialback is the only possible solution. Less desirable than other options, it does provide some level of trust.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="xmpp-federation-negotiation-methods-matrix---complete"></a><span data-ttu-id="acfb4-142">Полная матрица методов согласования федерации XMPP</span><span class="sxs-lookup"><span data-stu-id="acfb4-142">XMPP Federation Negotiation Methods Matrix - Complete</span></span>

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="acfb4-143">TLS (Transport Layer Security)</span><span class="sxs-lookup"><span data-stu-id="acfb4-143">Transport Layer Security (TLS)</span></span></th>
<th><span data-ttu-id="acfb4-144">SASL (Simple Authentication and Security Layer)</span><span class="sxs-lookup"><span data-stu-id="acfb4-144">Simple Authentication and Security Layer (SASL)</span></span></th>
<th><span data-ttu-id="acfb4-145">Проверка подлинности с обратным вызовом</span><span class="sxs-lookup"><span data-stu-id="acfb4-145">Dialback Authentication</span></span></th>
<th><span data-ttu-id="acfb4-146">Ожидаемый метод проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="acfb4-146">Expected Authentication Method</span></span></th>
<th><span data-ttu-id="acfb4-147">Примечания, предупреждение или ошибка для недействительной конфигурации</span><span class="sxs-lookup"><span data-stu-id="acfb4-147">Notes, Warning or Error for Not Valid Configuration</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="acfb4-148">Обязательный</span><span class="sxs-lookup"><span data-stu-id="acfb4-148">Required</span></span></p></td>
<td><p><span data-ttu-id="acfb4-149">Обязательный</span><span class="sxs-lookup"><span data-stu-id="acfb4-149">Required</span></span></p></td>
<td><p><span data-ttu-id="acfb4-150">Верно</span><span class="sxs-lookup"><span data-stu-id="acfb4-150">True</span></span></p></td>
<td><p><span data-ttu-id="acfb4-151">SASL через TLS</span><span class="sxs-lookup"><span data-stu-id="acfb4-151">SASL over TLS</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="acfb4-152">Обратный вызов не будет работать, если требуется как SASL, так и TLS.</span><span class="sxs-lookup"><span data-stu-id="acfb4-152">Dialback will not operate if both SASL and TLS are required.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="acfb4-153">Обязательный</span><span class="sxs-lookup"><span data-stu-id="acfb4-153">Required</span></span></p></td>
<td><p><span data-ttu-id="acfb4-154">Обязательный</span><span class="sxs-lookup"><span data-stu-id="acfb4-154">Required</span></span></p></td>
<td><p><span data-ttu-id="acfb4-155">False</span><span class="sxs-lookup"><span data-stu-id="acfb4-155">False</span></span></p></td>
<td><p><span data-ttu-id="acfb4-156">SASL через TLS</span><span class="sxs-lookup"><span data-stu-id="acfb4-156">SASL over TLS</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="acfb4-157">Необязательный</span><span class="sxs-lookup"><span data-stu-id="acfb4-157">Optional</span></span></p></td>
<td><p><span data-ttu-id="acfb4-158">Обязательный</span><span class="sxs-lookup"><span data-stu-id="acfb4-158">Required</span></span></p></td>
<td><p><span data-ttu-id="acfb4-159">Верно</span><span class="sxs-lookup"><span data-stu-id="acfb4-159">True</span></span></p></td>
<td><p><span data-ttu-id="acfb4-160">SASL через TLS, обратный вызов TLS, обратный вызов TCP</span><span class="sxs-lookup"><span data-stu-id="acfb4-160">SASL over TLS, TLS Dialback, TCP Dialback</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="acfb4-p106">Для SASL требуется TLS. Включение необязательного использования TLS может привести к сбою согласования сеансов.</span><span class="sxs-lookup"><span data-stu-id="acfb4-p106">SASL requires TLS. Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="acfb4-163">Необязательный</span><span class="sxs-lookup"><span data-stu-id="acfb4-163">Optional</span></span></p></td>
<td><p><span data-ttu-id="acfb4-164">Обязательный</span><span class="sxs-lookup"><span data-stu-id="acfb4-164">Required</span></span></p></td>
<td><p><span data-ttu-id="acfb4-165">False</span><span class="sxs-lookup"><span data-stu-id="acfb4-165">False</span></span></p></td>
<td><p><span data-ttu-id="acfb4-166">SASL через TLS</span><span class="sxs-lookup"><span data-stu-id="acfb4-166">SASL over TLS</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="acfb4-p107">Для SASL требуется TLS. Включение необязательного использования TLS может привести к сбою согласования сеансов.</span><span class="sxs-lookup"><span data-stu-id="acfb4-p107">SASL requires TLS. Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="acfb4-169">Не поддерживается</span><span class="sxs-lookup"><span data-stu-id="acfb4-169">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="acfb4-170">Обязательный</span><span class="sxs-lookup"><span data-stu-id="acfb4-170">Required</span></span></p></td>
<td><p><span data-ttu-id="acfb4-171">Верно</span><span class="sxs-lookup"><span data-stu-id="acfb4-171">True</span></span></p></td>
<td><p><span data-ttu-id="acfb4-172">Обратный вызов TCP</span><span class="sxs-lookup"><span data-stu-id="acfb4-172">TCP Dialback</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="acfb4-p108">Для SASL требуется TLS. Включение необязательного использования TLS может привести к сбою согласования сеансов.</span><span class="sxs-lookup"><span data-stu-id="acfb4-p108">SASL requires TLS. Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="acfb4-175">Не поддерживается</span><span class="sxs-lookup"><span data-stu-id="acfb4-175">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="acfb4-176">Обязательный</span><span class="sxs-lookup"><span data-stu-id="acfb4-176">Required</span></span></p></td>
<td><p><span data-ttu-id="acfb4-177">False</span><span class="sxs-lookup"><span data-stu-id="acfb4-177">False</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="acfb4-178">Недопустимая конфигурация</span><span class="sxs-lookup"><span data-stu-id="acfb4-178">Not Valid Configuration</span></span>


</div></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="acfb4-p109">Поскольку для SASL требуется TLS, который недоступен, комбинация SASL/TLS не работает. Для обратного вызова TCP устанавливается недопустимое состояние, и данный метод использовать нельзя.</span><span class="sxs-lookup"><span data-stu-id="acfb4-p109">Because SASL requires TLS, and TLS is not available, SASL/TLS cannot succeed. TCP Dialback is set to false, and cannot be used.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="acfb4-181">Обязательна</span><span class="sxs-lookup"><span data-stu-id="acfb4-181">Required</span></span></p></td>
<td><p><span data-ttu-id="acfb4-182">Необязательный</span><span class="sxs-lookup"><span data-stu-id="acfb4-182">Optional</span></span></p></td>
<td><p><span data-ttu-id="acfb4-183">Верно</span><span class="sxs-lookup"><span data-stu-id="acfb4-183">True</span></span></p></td>
<td><p><span data-ttu-id="acfb4-184">SASL через TLS, обратный вызов TLS</span><span class="sxs-lookup"><span data-stu-id="acfb4-184">SASL over TLS, TLS Dialback</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="acfb4-185">Обязательна</span><span class="sxs-lookup"><span data-stu-id="acfb4-185">Required</span></span></p></td>
<td><p><span data-ttu-id="acfb4-186">Необязательный</span><span class="sxs-lookup"><span data-stu-id="acfb4-186">Optional</span></span></p></td>
<td><p><span data-ttu-id="acfb4-187">False</span><span class="sxs-lookup"><span data-stu-id="acfb4-187">False</span></span></p></td>
<td><p><span data-ttu-id="acfb4-188">SASL через TLS</span><span class="sxs-lookup"><span data-stu-id="acfb4-188">SASL over TLS</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="acfb4-189">Необязательный</span><span class="sxs-lookup"><span data-stu-id="acfb4-189">Optional</span></span></p></td>
<td><p><span data-ttu-id="acfb4-190">Необязательна</span><span class="sxs-lookup"><span data-stu-id="acfb4-190">Optional</span></span></p></td>
<td><p><span data-ttu-id="acfb4-191">Верно</span><span class="sxs-lookup"><span data-stu-id="acfb4-191">True</span></span></p></td>
<td><p><span data-ttu-id="acfb4-192">SASL через TLS, обратный вызов TLS, обратный вызов TCP</span><span class="sxs-lookup"><span data-stu-id="acfb4-192">SASL over TLS, TLS Dialback, TCP Dialback</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="acfb4-p110">Для SASL требуется TLS. Включение необязательного использования TLS может привести к сбою согласования сеансов.</span><span class="sxs-lookup"><span data-stu-id="acfb4-p110">SASL requires TLS. Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="acfb4-195">Необязательный</span><span class="sxs-lookup"><span data-stu-id="acfb4-195">Optional</span></span></p></td>
<td><p><span data-ttu-id="acfb4-196">Необязательна</span><span class="sxs-lookup"><span data-stu-id="acfb4-196">Optional</span></span></p></td>
<td><p><span data-ttu-id="acfb4-197">False</span><span class="sxs-lookup"><span data-stu-id="acfb4-197">False</span></span></p></td>
<td><p><span data-ttu-id="acfb4-198">SASL через TLS</span><span class="sxs-lookup"><span data-stu-id="acfb4-198">SASL over TLS</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="acfb4-p111">Для SASL требуется TLS. Включение необязательного использования TLS может привести к сбою согласования сеансов.</span><span class="sxs-lookup"><span data-stu-id="acfb4-p111">SASL requires TLS. Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="acfb4-201">Не поддерживается</span><span class="sxs-lookup"><span data-stu-id="acfb4-201">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="acfb4-202">Необязательный</span><span class="sxs-lookup"><span data-stu-id="acfb4-202">Optional</span></span></p></td>
<td><p><span data-ttu-id="acfb4-203">Верно</span><span class="sxs-lookup"><span data-stu-id="acfb4-203">True</span></span></p></td>
<td><p><span data-ttu-id="acfb4-204">Обратный вызов TCP</span><span class="sxs-lookup"><span data-stu-id="acfb4-204">TCP Dialback</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="acfb4-p112">Для SASL требуется TLS. Включение необязательного использования TLS может привести к сбою согласования сеансов.</span><span class="sxs-lookup"><span data-stu-id="acfb4-p112">SASL requires TLS. Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="acfb4-207">Не поддерживается</span><span class="sxs-lookup"><span data-stu-id="acfb4-207">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="acfb4-208">Необязательный</span><span class="sxs-lookup"><span data-stu-id="acfb4-208">Optional</span></span></p></td>
<td><p><span data-ttu-id="acfb4-209">False</span><span class="sxs-lookup"><span data-stu-id="acfb4-209">False</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="acfb4-210">Недопустимая конфигурация</span><span class="sxs-lookup"><span data-stu-id="acfb4-210">Not Valid Configuration</span></span>


</div></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="acfb4-p113">Для SASL требуется TLS. Включение необязательного использования TLS может привести к сбою согласования сеансов.</span><span class="sxs-lookup"><span data-stu-id="acfb4-p113">SASL requires TLS. Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="acfb4-213">Обязательный</span><span class="sxs-lookup"><span data-stu-id="acfb4-213">Required</span></span></p></td>
<td><p><span data-ttu-id="acfb4-214">Не поддерживается</span><span class="sxs-lookup"><span data-stu-id="acfb4-214">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="acfb4-215">Верно</span><span class="sxs-lookup"><span data-stu-id="acfb4-215">True</span></span></p></td>
<td><p><span data-ttu-id="acfb4-216">Обратный вызов TCP</span><span class="sxs-lookup"><span data-stu-id="acfb4-216">TLS Dialback</span></span></p></td>
<td><p><span data-ttu-id="acfb4-217">Конфигурация допускает использование обратного вызова TLS.</span><span class="sxs-lookup"><span data-stu-id="acfb4-217">Configuration allows for TLS Dialback.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="acfb4-218">Обязательный</span><span class="sxs-lookup"><span data-stu-id="acfb4-218">Required</span></span></p></td>
<td><p><span data-ttu-id="acfb4-219">Не поддерживается</span><span class="sxs-lookup"><span data-stu-id="acfb4-219">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="acfb4-220">False</span><span class="sxs-lookup"><span data-stu-id="acfb4-220">False</span></span></p></td>
<td><p><span data-ttu-id="acfb4-221">Недопустимая конфигурация</span><span class="sxs-lookup"><span data-stu-id="acfb4-221">Not Valid Configuration</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="acfb4-222">Необходимо включить SASL или обратный вызов.</span><span class="sxs-lookup"><span data-stu-id="acfb4-222">SASL or Dialback must be enabled.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="acfb4-223">Необязательный</span><span class="sxs-lookup"><span data-stu-id="acfb4-223">Optional</span></span></p></td>
<td><p><span data-ttu-id="acfb4-224">Не поддерживается</span><span class="sxs-lookup"><span data-stu-id="acfb4-224">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="acfb4-225">Верно</span><span class="sxs-lookup"><span data-stu-id="acfb4-225">True</span></span></p></td>
<td><p><span data-ttu-id="acfb4-226">Обратный вызов TLS, обратный вызов TCP</span><span class="sxs-lookup"><span data-stu-id="acfb4-226">TLS Dialback, TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="acfb4-227">В соответствии с вариантами согласования, включенными для другой конечной точки, будет принят обратный вызов TCP или TLS.</span><span class="sxs-lookup"><span data-stu-id="acfb4-227">Based on negotiation choices of the other end point, TCP or TLS Dialback will be accepted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="acfb4-228">Необязательный</span><span class="sxs-lookup"><span data-stu-id="acfb4-228">Optional</span></span></p></td>
<td><p><span data-ttu-id="acfb4-229">Не поддерживается</span><span class="sxs-lookup"><span data-stu-id="acfb4-229">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="acfb4-230">False</span><span class="sxs-lookup"><span data-stu-id="acfb4-230">False</span></span></p></td>
<td><p><span data-ttu-id="acfb4-231">Недопустимая конфигурация</span><span class="sxs-lookup"><span data-stu-id="acfb4-231">Not Valid Configuration</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="acfb4-232">Необходимо включить SASL или обратный вызов.</span><span class="sxs-lookup"><span data-stu-id="acfb4-232">SASL or Dialback must be enabled.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="acfb4-233">Не поддерживается</span><span class="sxs-lookup"><span data-stu-id="acfb4-233">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="acfb4-234">Не поддерживается</span><span class="sxs-lookup"><span data-stu-id="acfb4-234">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="acfb4-235">Верно</span><span class="sxs-lookup"><span data-stu-id="acfb4-235">True</span></span></p></td>
<td><p><span data-ttu-id="acfb4-236">Обратный вызов TCP</span><span class="sxs-lookup"><span data-stu-id="acfb4-236">TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="acfb4-237">Обратный вызов TCP является единственным доступным методом согласования</span><span class="sxs-lookup"><span data-stu-id="acfb4-237">TCP Dialback is the only negotiation method available</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="acfb4-238">Не поддерживается</span><span class="sxs-lookup"><span data-stu-id="acfb4-238">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="acfb4-239">Не поддерживается</span><span class="sxs-lookup"><span data-stu-id="acfb4-239">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="acfb4-240">False</span><span class="sxs-lookup"><span data-stu-id="acfb4-240">False</span></span></p></td>
<td><p><span data-ttu-id="acfb4-241">Недопустимая конфигурация</span><span class="sxs-lookup"><span data-stu-id="acfb4-241">Not Valid Configuration</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="acfb4-242">Необходимо включить SASL или обратный вызов.</span><span class="sxs-lookup"><span data-stu-id="acfb4-242">SASL or Dialback must be enabled.</span></span>


</div></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

