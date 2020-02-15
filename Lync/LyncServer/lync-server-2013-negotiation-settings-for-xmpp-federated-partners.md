---
title: 'Lync Server 2013: параметры согласования для федеративных партнеров XMPP'
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
ms.openlocfilehash: c190e4a45a70bd527aa8fc6323a671d481f04872
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42039101"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="negotiation-settings-for-xmpp-federated-partners-in-lync-server-2013"></a><span data-ttu-id="cc9d7-102">Параметры согласования для федеративных партнеров XMPP в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cc9d7-102">Negotiation settings for XMPP federated partners in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cc9d7-103">_**Последнее изменение темы:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="cc9d7-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="cc9d7-104">В конфигурации XMPP-партнера доступно значительное количество возможных комбинаций параметров для типов согласования.</span><span class="sxs-lookup"><span data-stu-id="cc9d7-104">The settings for the negotiation types in the configuration of an XMPP Partner have a wide variety of possible combinations.</span></span> <span data-ttu-id="cc9d7-105">Но не все эти комбинации являются допустимыми.</span><span class="sxs-lookup"><span data-stu-id="cc9d7-105">Not all of these combinations are valid.</span></span> <span data-ttu-id="cc9d7-106">В приведенной здесь таблице подробно описывается, какие параметры являются допустимыми, а какие — нет.</span><span class="sxs-lookup"><span data-stu-id="cc9d7-106">The table detailed in this topic will define the valid and not valid settings.</span></span> <span data-ttu-id="cc9d7-107">Распространенные конфигурации представлены в первой таблице, во второй таблице приведены все возможные комбинации.</span><span class="sxs-lookup"><span data-stu-id="cc9d7-107">Common configurations are presented in the first table, the second table detailing all possible combinations.</span></span> <span data-ttu-id="cc9d7-108">Обратите внимание на то, что вы не можете использовать *простую проверку подлинности и уровень безопасности* (SASL), **если** также не доступен протокол TLS ( *Transport Layer Security* ).</span><span class="sxs-lookup"><span data-stu-id="cc9d7-108">Note that you cannot have *Simple Authentication and Security Layer* (SASL) **unless** *Transport Layer Security* (TLS) is also available.</span></span> <span data-ttu-id="cc9d7-109">Данные SASL отправляются в незашифрованном (пригодном для чтения) формате, поэтому при их передаче следует использовать другие средства защиты, такие как TLS.</span><span class="sxs-lookup"><span data-stu-id="cc9d7-109">SASL is sent in an unencrypted (readable) format and should never be transmitted unless protected by another means, such as TLS.</span></span>

### <a name="common-xmpp-federation-negotiation-methods"></a><span data-ttu-id="cc9d7-110">Распространенные методы согласования федерации XMPP</span><span class="sxs-lookup"><span data-stu-id="cc9d7-110">Common XMPP Federation Negotiation Methods</span></span>

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
<th><span data-ttu-id="cc9d7-111">TLS (Transport Layer Security)</span><span class="sxs-lookup"><span data-stu-id="cc9d7-111">Transport Layer Security (TLS)</span></span></th>
<th><span data-ttu-id="cc9d7-112">SASL (Simple Authentication and Security Layer)</span><span class="sxs-lookup"><span data-stu-id="cc9d7-112">Simple Authentication and Security Layer (SASL)</span></span></th>
<th><span data-ttu-id="cc9d7-113">Проверка подлинности с обратным вызовом</span><span class="sxs-lookup"><span data-stu-id="cc9d7-113">Dialback Authentication</span></span></th>
<th><span data-ttu-id="cc9d7-114">Ожидаемые методы проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="cc9d7-114">Expected Authentication Method(s)</span></span></th>
<th><span data-ttu-id="cc9d7-115">Notes</span><span class="sxs-lookup"><span data-stu-id="cc9d7-115">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cc9d7-116">Обязательный</span><span class="sxs-lookup"><span data-stu-id="cc9d7-116">Required</span></span></p></td>
<td><p><span data-ttu-id="cc9d7-117">Обязательный</span><span class="sxs-lookup"><span data-stu-id="cc9d7-117">Required</span></span></p></td>
<td><p><span data-ttu-id="cc9d7-118">False</span><span class="sxs-lookup"><span data-stu-id="cc9d7-118">False</span></span></p></td>
<td><p><span data-ttu-id="cc9d7-119">SASL через TLS</span><span class="sxs-lookup"><span data-stu-id="cc9d7-119">SASL over TLS</span></span></p></td>
<td><p><span data-ttu-id="cc9d7-p102">Обязательное использование TLS и SASL помогает обеспечить безопасность потока сообщений SASL. Обратный вызов недоступен и не может применяться в качестве резервного метода, если федеративный XMPP-партнер не установил обязательное или необязательное использование TLS.</span><span class="sxs-lookup"><span data-stu-id="cc9d7-p102">TLS and SASL required helps to ensure that the SASL message stream is secure. Dialback is not available and cannot be used for a fallback method if the XMPP federated partner has not set TLS to required or optional.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc9d7-122">Обязательна</span><span class="sxs-lookup"><span data-stu-id="cc9d7-122">Required</span></span></p></td>
<td><p><span data-ttu-id="cc9d7-123">Необязательный</span><span class="sxs-lookup"><span data-stu-id="cc9d7-123">Optional</span></span></p></td>
<td><p><span data-ttu-id="cc9d7-124">Верно</span><span class="sxs-lookup"><span data-stu-id="cc9d7-124">True</span></span></p></td>
<td><p><span data-ttu-id="cc9d7-125">SASL через TLS, обратный вызов TLS, обратный вызов TCP</span><span class="sxs-lookup"><span data-stu-id="cc9d7-125">SASL over TLS, TLS Dialback, TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="cc9d7-p103">Если федеративный XMPP-партнер установил обязательное или необязательное использование SASL, в случае обязательного использования TLS применяется SASL. Если SASL недоступен, используется обратный вызов через TLS.</span><span class="sxs-lookup"><span data-stu-id="cc9d7-p103">By requiring TLS, if the XMPP federated partner has set SASL to optional or required SASL is used. If SASL is not available, Dialback over TLS will be used.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc9d7-128">Необязательный</span><span class="sxs-lookup"><span data-stu-id="cc9d7-128">Optional</span></span></p></td>
<td><p><span data-ttu-id="cc9d7-129">Необязательна</span><span class="sxs-lookup"><span data-stu-id="cc9d7-129">Optional</span></span></p></td>
<td><p><span data-ttu-id="cc9d7-130">Верно</span><span class="sxs-lookup"><span data-stu-id="cc9d7-130">True</span></span></p></td>
<td><p><span data-ttu-id="cc9d7-131">SASL через TLS, обратный вызов TLS, обратный вызов TCP</span><span class="sxs-lookup"><span data-stu-id="cc9d7-131">SASL over TLS, TLS Dialback, TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="cc9d7-p104">Хотя эти параметры и обеспечивают гибкость с точки зрения доступных методов согласования, они основаны на параметрах XMPP-партнера федерации. Если партнер задает обязательное или необязательное использование TLS, но SASL не поддерживается, будет доступен обратный вызов через TLS. Если партнер задает обязательное или необязательное использование TLS и SASL, используется оптимальный вариант TLS через SASL.</span><span class="sxs-lookup"><span data-stu-id="cc9d7-p104">While very flexible in the negotiation methods offered, these settings rely on the XMPP federation partner’s settings. If the partner has TLS optional or required but SASL is not supported, TLS Dialback will be available. If the partner has TLS and SASL set to optional or required, the optimal selection of TLS over SASL is used.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc9d7-135">Не поддерживается</span><span class="sxs-lookup"><span data-stu-id="cc9d7-135">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="cc9d7-136">Не поддерживается</span><span class="sxs-lookup"><span data-stu-id="cc9d7-136">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="cc9d7-137">Верно</span><span class="sxs-lookup"><span data-stu-id="cc9d7-137">True</span></span></p></td>
<td><p><span data-ttu-id="cc9d7-138">Обратный вызов TCP</span><span class="sxs-lookup"><span data-stu-id="cc9d7-138">TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="cc9d7-p105">Во многих случаях обратный вызов TCP является единственным возможным решением и обеспечивает некоторый уровень доверия, хотя желательно использовать другие варианты.</span><span class="sxs-lookup"><span data-stu-id="cc9d7-p105">In many cases, TCP Dialback is the only possible solution. Less desirable than other options, it does provide some level of trust.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="xmpp-federation-negotiation-methods-matrix---complete"></a><span data-ttu-id="cc9d7-141">Полная матрица методов согласования федерации XMPP</span><span class="sxs-lookup"><span data-stu-id="cc9d7-141">XMPP Federation Negotiation Methods Matrix - Complete</span></span>

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
<th><span data-ttu-id="cc9d7-142">TLS (Transport Layer Security)</span><span class="sxs-lookup"><span data-stu-id="cc9d7-142">Transport Layer Security (TLS)</span></span></th>
<th><span data-ttu-id="cc9d7-143">SASL (Simple Authentication and Security Layer)</span><span class="sxs-lookup"><span data-stu-id="cc9d7-143">Simple Authentication and Security Layer (SASL)</span></span></th>
<th><span data-ttu-id="cc9d7-144">Проверка подлинности с обратным вызовом</span><span class="sxs-lookup"><span data-stu-id="cc9d7-144">Dialback Authentication</span></span></th>
<th><span data-ttu-id="cc9d7-145">Ожидаемый метод проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="cc9d7-145">Expected Authentication Method</span></span></th>
<th><span data-ttu-id="cc9d7-146">Примечания, предупреждение или ошибка для недействительной конфигурации</span><span class="sxs-lookup"><span data-stu-id="cc9d7-146">Notes, Warning or Error for Not Valid Configuration</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cc9d7-147">Обязательный</span><span class="sxs-lookup"><span data-stu-id="cc9d7-147">Required</span></span></p></td>
<td><p><span data-ttu-id="cc9d7-148">Обязательный</span><span class="sxs-lookup"><span data-stu-id="cc9d7-148">Required</span></span></p></td>
<td><p><span data-ttu-id="cc9d7-149">Верно</span><span class="sxs-lookup"><span data-stu-id="cc9d7-149">True</span></span></p></td>
<td><p><span data-ttu-id="cc9d7-150">SASL через TLS</span><span class="sxs-lookup"><span data-stu-id="cc9d7-150">SASL over TLS</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="cc9d7-151">Обратный вызов не будет работать, если требуется как SASL, так и TLS.</span><span class="sxs-lookup"><span data-stu-id="cc9d7-151">Dialback will not operate if both SASL and TLS are required.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc9d7-152">Обязательный</span><span class="sxs-lookup"><span data-stu-id="cc9d7-152">Required</span></span></p></td>
<td><p><span data-ttu-id="cc9d7-153">Обязательный</span><span class="sxs-lookup"><span data-stu-id="cc9d7-153">Required</span></span></p></td>
<td><p><span data-ttu-id="cc9d7-154">False</span><span class="sxs-lookup"><span data-stu-id="cc9d7-154">False</span></span></p></td>
<td><p><span data-ttu-id="cc9d7-155">SASL через TLS</span><span class="sxs-lookup"><span data-stu-id="cc9d7-155">SASL over TLS</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc9d7-156">Необязательна</span><span class="sxs-lookup"><span data-stu-id="cc9d7-156">Optional</span></span></p></td>
<td><p><span data-ttu-id="cc9d7-157">Обязательна</span><span class="sxs-lookup"><span data-stu-id="cc9d7-157">Required</span></span></p></td>
<td><p><span data-ttu-id="cc9d7-158">Верно</span><span class="sxs-lookup"><span data-stu-id="cc9d7-158">True</span></span></p></td>
<td><p><span data-ttu-id="cc9d7-159">SASL через TLS, обратный вызов TLS, обратный вызов TCP</span><span class="sxs-lookup"><span data-stu-id="cc9d7-159">SASL over TLS, TLS Dialback, TCP Dialback</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="cc9d7-160">Для SASL требуется TLS.</span><span class="sxs-lookup"><span data-stu-id="cc9d7-160">SASL requires TLS.</span></span> <span data-ttu-id="cc9d7-161">Включение необязательного использования TLS может привести к сбою согласования сеансов.</span><span class="sxs-lookup"><span data-stu-id="cc9d7-161">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc9d7-162">Необязательна</span><span class="sxs-lookup"><span data-stu-id="cc9d7-162">Optional</span></span></p></td>
<td><p><span data-ttu-id="cc9d7-163">Обязательна</span><span class="sxs-lookup"><span data-stu-id="cc9d7-163">Required</span></span></p></td>
<td><p><span data-ttu-id="cc9d7-164">False</span><span class="sxs-lookup"><span data-stu-id="cc9d7-164">False</span></span></p></td>
<td><p><span data-ttu-id="cc9d7-165">SASL через TLS</span><span class="sxs-lookup"><span data-stu-id="cc9d7-165">SASL over TLS</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="cc9d7-166">Для SASL требуется TLS.</span><span class="sxs-lookup"><span data-stu-id="cc9d7-166">SASL requires TLS.</span></span> <span data-ttu-id="cc9d7-167">Включение необязательного использования TLS может привести к сбою согласования сеансов.</span><span class="sxs-lookup"><span data-stu-id="cc9d7-167">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc9d7-168">Не поддерживается</span><span class="sxs-lookup"><span data-stu-id="cc9d7-168">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="cc9d7-169">Обязательна</span><span class="sxs-lookup"><span data-stu-id="cc9d7-169">Required</span></span></p></td>
<td><p><span data-ttu-id="cc9d7-170">Верно</span><span class="sxs-lookup"><span data-stu-id="cc9d7-170">True</span></span></p></td>
<td><p><span data-ttu-id="cc9d7-171">Обратный вызов TCP</span><span class="sxs-lookup"><span data-stu-id="cc9d7-171">TCP Dialback</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="cc9d7-172">Для SASL требуется TLS.</span><span class="sxs-lookup"><span data-stu-id="cc9d7-172">SASL requires TLS.</span></span> <span data-ttu-id="cc9d7-173">Включение необязательного использования TLS может привести к сбою согласования сеансов.</span><span class="sxs-lookup"><span data-stu-id="cc9d7-173">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc9d7-174">Не поддерживается</span><span class="sxs-lookup"><span data-stu-id="cc9d7-174">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="cc9d7-175">Обязательна</span><span class="sxs-lookup"><span data-stu-id="cc9d7-175">Required</span></span></p></td>
<td><p><span data-ttu-id="cc9d7-176">False</span><span class="sxs-lookup"><span data-stu-id="cc9d7-176">False</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="cc9d7-177">Недопустимая конфигурация</span><span class="sxs-lookup"><span data-stu-id="cc9d7-177">Not Valid Configuration</span></span>


</div></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="cc9d7-p109">Поскольку для SASL требуется TLS, который недоступен, комбинация SASL/TLS не работает. Для обратного вызова TCP устанавливается недопустимое состояние, и данный метод использовать нельзя.</span><span class="sxs-lookup"><span data-stu-id="cc9d7-p109">Because SASL requires TLS, and TLS is not available, SASL/TLS cannot succeed. TCP Dialback is set to false, and cannot be used.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc9d7-180">Обязательна</span><span class="sxs-lookup"><span data-stu-id="cc9d7-180">Required</span></span></p></td>
<td><p><span data-ttu-id="cc9d7-181">Необязательный</span><span class="sxs-lookup"><span data-stu-id="cc9d7-181">Optional</span></span></p></td>
<td><p><span data-ttu-id="cc9d7-182">Верно</span><span class="sxs-lookup"><span data-stu-id="cc9d7-182">True</span></span></p></td>
<td><p><span data-ttu-id="cc9d7-183">SASL через TLS, обратный вызов TLS</span><span class="sxs-lookup"><span data-stu-id="cc9d7-183">SASL over TLS, TLS Dialback</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc9d7-184">Обязательна</span><span class="sxs-lookup"><span data-stu-id="cc9d7-184">Required</span></span></p></td>
<td><p><span data-ttu-id="cc9d7-185">Необязательный</span><span class="sxs-lookup"><span data-stu-id="cc9d7-185">Optional</span></span></p></td>
<td><p><span data-ttu-id="cc9d7-186">False</span><span class="sxs-lookup"><span data-stu-id="cc9d7-186">False</span></span></p></td>
<td><p><span data-ttu-id="cc9d7-187">SASL через TLS</span><span class="sxs-lookup"><span data-stu-id="cc9d7-187">SASL over TLS</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc9d7-188">Необязательный</span><span class="sxs-lookup"><span data-stu-id="cc9d7-188">Optional</span></span></p></td>
<td><p><span data-ttu-id="cc9d7-189">Необязательна</span><span class="sxs-lookup"><span data-stu-id="cc9d7-189">Optional</span></span></p></td>
<td><p><span data-ttu-id="cc9d7-190">Верно</span><span class="sxs-lookup"><span data-stu-id="cc9d7-190">True</span></span></p></td>
<td><p><span data-ttu-id="cc9d7-191">SASL через TLS, обратный вызов TLS, обратный вызов TCP</span><span class="sxs-lookup"><span data-stu-id="cc9d7-191">SASL over TLS, TLS Dialback, TCP Dialback</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="cc9d7-192">Для SASL требуется TLS.</span><span class="sxs-lookup"><span data-stu-id="cc9d7-192">SASL requires TLS.</span></span> <span data-ttu-id="cc9d7-193">Включение необязательного использования TLS может привести к сбою согласования сеансов.</span><span class="sxs-lookup"><span data-stu-id="cc9d7-193">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc9d7-194">Необязательный</span><span class="sxs-lookup"><span data-stu-id="cc9d7-194">Optional</span></span></p></td>
<td><p><span data-ttu-id="cc9d7-195">Необязательна</span><span class="sxs-lookup"><span data-stu-id="cc9d7-195">Optional</span></span></p></td>
<td><p><span data-ttu-id="cc9d7-196">False</span><span class="sxs-lookup"><span data-stu-id="cc9d7-196">False</span></span></p></td>
<td><p><span data-ttu-id="cc9d7-197">SASL через TLS</span><span class="sxs-lookup"><span data-stu-id="cc9d7-197">SASL over TLS</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="cc9d7-198">Для SASL требуется TLS.</span><span class="sxs-lookup"><span data-stu-id="cc9d7-198">SASL requires TLS.</span></span> <span data-ttu-id="cc9d7-199">Включение необязательного использования TLS может привести к сбою согласования сеансов.</span><span class="sxs-lookup"><span data-stu-id="cc9d7-199">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc9d7-200">Не поддерживается</span><span class="sxs-lookup"><span data-stu-id="cc9d7-200">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="cc9d7-201">Необязательна</span><span class="sxs-lookup"><span data-stu-id="cc9d7-201">Optional</span></span></p></td>
<td><p><span data-ttu-id="cc9d7-202">Верно</span><span class="sxs-lookup"><span data-stu-id="cc9d7-202">True</span></span></p></td>
<td><p><span data-ttu-id="cc9d7-203">Обратный вызов TCP</span><span class="sxs-lookup"><span data-stu-id="cc9d7-203">TCP Dialback</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="cc9d7-204">Для SASL требуется TLS.</span><span class="sxs-lookup"><span data-stu-id="cc9d7-204">SASL requires TLS.</span></span> <span data-ttu-id="cc9d7-205">Включение необязательного использования TLS может привести к сбою согласования сеансов.</span><span class="sxs-lookup"><span data-stu-id="cc9d7-205">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc9d7-206">Не поддерживается</span><span class="sxs-lookup"><span data-stu-id="cc9d7-206">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="cc9d7-207">Необязательна</span><span class="sxs-lookup"><span data-stu-id="cc9d7-207">Optional</span></span></p></td>
<td><p><span data-ttu-id="cc9d7-208">False</span><span class="sxs-lookup"><span data-stu-id="cc9d7-208">False</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="cc9d7-209">Недопустимая конфигурация</span><span class="sxs-lookup"><span data-stu-id="cc9d7-209">Not Valid Configuration</span></span>


</div></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="cc9d7-p113">Для SASL требуется TLS. Включение необязательного использования TLS может привести к сбою согласования сеансов.</span><span class="sxs-lookup"><span data-stu-id="cc9d7-p113">SASL requires TLS. Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc9d7-212">Обязательна</span><span class="sxs-lookup"><span data-stu-id="cc9d7-212">Required</span></span></p></td>
<td><p><span data-ttu-id="cc9d7-213">Не поддерживается</span><span class="sxs-lookup"><span data-stu-id="cc9d7-213">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="cc9d7-214">Верно</span><span class="sxs-lookup"><span data-stu-id="cc9d7-214">True</span></span></p></td>
<td><p><span data-ttu-id="cc9d7-215">Обратный вызов TCP</span><span class="sxs-lookup"><span data-stu-id="cc9d7-215">TLS Dialback</span></span></p></td>
<td><p><span data-ttu-id="cc9d7-216">Конфигурация допускает использование обратного вызова TLS.</span><span class="sxs-lookup"><span data-stu-id="cc9d7-216">Configuration allows for TLS Dialback.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc9d7-217">Обязательна</span><span class="sxs-lookup"><span data-stu-id="cc9d7-217">Required</span></span></p></td>
<td><p><span data-ttu-id="cc9d7-218">Не поддерживается</span><span class="sxs-lookup"><span data-stu-id="cc9d7-218">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="cc9d7-219">False</span><span class="sxs-lookup"><span data-stu-id="cc9d7-219">False</span></span></p></td>
<td><p><span data-ttu-id="cc9d7-220">Недопустимая конфигурация</span><span class="sxs-lookup"><span data-stu-id="cc9d7-220">Not Valid Configuration</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="cc9d7-221">Необходимо включить SASL или обратный вызов.</span><span class="sxs-lookup"><span data-stu-id="cc9d7-221">SASL or Dialback must be enabled.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc9d7-222">Необязательна</span><span class="sxs-lookup"><span data-stu-id="cc9d7-222">Optional</span></span></p></td>
<td><p><span data-ttu-id="cc9d7-223">Не поддерживается</span><span class="sxs-lookup"><span data-stu-id="cc9d7-223">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="cc9d7-224">Верно</span><span class="sxs-lookup"><span data-stu-id="cc9d7-224">True</span></span></p></td>
<td><p><span data-ttu-id="cc9d7-225">Обратный вызов TLS, обратный вызов TCP</span><span class="sxs-lookup"><span data-stu-id="cc9d7-225">TLS Dialback, TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="cc9d7-226">В соответствии с вариантами согласования, включенными для другой конечной точки, будет принят обратный вызов TCP или TLS.</span><span class="sxs-lookup"><span data-stu-id="cc9d7-226">Based on negotiation choices of the other end point, TCP or TLS Dialback will be accepted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc9d7-227">Необязательна</span><span class="sxs-lookup"><span data-stu-id="cc9d7-227">Optional</span></span></p></td>
<td><p><span data-ttu-id="cc9d7-228">Не поддерживается</span><span class="sxs-lookup"><span data-stu-id="cc9d7-228">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="cc9d7-229">False</span><span class="sxs-lookup"><span data-stu-id="cc9d7-229">False</span></span></p></td>
<td><p><span data-ttu-id="cc9d7-230">Недопустимая конфигурация</span><span class="sxs-lookup"><span data-stu-id="cc9d7-230">Not Valid Configuration</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="cc9d7-231">Необходимо включить SASL или обратный вызов.</span><span class="sxs-lookup"><span data-stu-id="cc9d7-231">SASL or Dialback must be enabled.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc9d7-232">Не поддерживается</span><span class="sxs-lookup"><span data-stu-id="cc9d7-232">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="cc9d7-233">Не поддерживается</span><span class="sxs-lookup"><span data-stu-id="cc9d7-233">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="cc9d7-234">Верно</span><span class="sxs-lookup"><span data-stu-id="cc9d7-234">True</span></span></p></td>
<td><p><span data-ttu-id="cc9d7-235">Обратный вызов TCP</span><span class="sxs-lookup"><span data-stu-id="cc9d7-235">TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="cc9d7-236">Обратный вызов TCP является единственным доступным методом согласования</span><span class="sxs-lookup"><span data-stu-id="cc9d7-236">TCP Dialback is the only negotiation method available</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc9d7-237">Не поддерживается</span><span class="sxs-lookup"><span data-stu-id="cc9d7-237">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="cc9d7-238">Не поддерживается</span><span class="sxs-lookup"><span data-stu-id="cc9d7-238">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="cc9d7-239">False</span><span class="sxs-lookup"><span data-stu-id="cc9d7-239">False</span></span></p></td>
<td><p><span data-ttu-id="cc9d7-240">Недопустимая конфигурация</span><span class="sxs-lookup"><span data-stu-id="cc9d7-240">Not Valid Configuration</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="cc9d7-241">Необходимо включить SASL или обратный вызов.</span><span class="sxs-lookup"><span data-stu-id="cc9d7-241">SASL or Dialback must be enabled.</span></span>


</div></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

